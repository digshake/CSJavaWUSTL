.. qnum::
   :prefix: 8-1-
   :start: 1
   
.. |CodingEx| image:: ../../_static/codingExercise.png
    :width: 30px
    :align: middle
    :alt: coding exercise
    
    
.. |Exercise| image:: ../../_static/exercise.png
    :width: 35
    :align: middle
    :alt: exercise
    
    
.. |Groupwork| image:: ../../_static/groupwork.png
    :width: 35
    :align: middle
    :alt: groupwork

Abstract Data Types
==========================

We have already talked about the idea of abstraction: we use methods to abstract out repetitive code so that we can reuse that code over and over again. This provides us the ability to reuse code and perform the same actions with a higher consistency than if we simply copied and pasted the code over and over again.

In this module we are again going to speak of abstraction, but this time we'll try to abstract out the methods themselves. Consider that we already do this all the time with our own human language. A Vehicle is a term we use to describe things that go. There are many different types of vehicles but most people would agree that all vehicles have some common behaviors, such as the ability to move, to be driven, and to carry passengers. The way that specific vehicles accompish these tasks are very different, however. Cars are driven in a particular way that is different from trucks or boats or airplanes.

Sometimes it is useful to talk about how to drive a car or how to drive an airplane, but other times it is useful for us to speak about vehicles in the abstract sense: you know that vehicles can drive but **how** that happens is unknown and perhaps irrelevant.

We have the ability to perform this abstraction in code as well. **Interfaces** are used to abstract out behaviors that are common to many **classes**. In this sense we now have the ability to speak about these more abstract Interface types, which can be useful! Following the example from before, a ``Vehicle`` interface could easily be created and then applied to ``Car``, ``Plane``, and ``Boat`` classes.

In this module, we are going to examine some abstract data types that are useful to use within the field of computer science: ``List`` and ``Set``. There are many different kinds of lists that we can create, just as there are many kind of vehicles that can be created, however all lists share the same basic functionality. If we as programmers are aware of this functionality then it gives us the ability to use these useful data structures without necessarily caring about how they work, much like you can drive a car without knowing how the engine works or learn how to fly a plane without understanding all of the complicated internals of the aircraft.

As you continue your computer science career, you will be introduced to many of these abstract data types, and one of our most important jobs as programmers becomes selecting the appropriate data type for the task at hand. With that in mind, let's start to explore these two new abstract data types!

Lists
=====

A ``List`` is an ordered collection of objects. Lists also allow for duplicate elements to be included. Most people are familiar with lists in the form of a todo list, or a list of items to pick up from the store. Note that the list preserves the order of the items whether or not that order is important: the order of the things on our todo list could be very important but the order of our grocery list probably doesn't matter as much. These lists will maintain an order, regardless, in this case perhaps the order only represents the order that things were added to the list.

In code, we refer to Lists (as well as the other ADTs that we are going to look at) as **parametric types**. This means that in order to use our ``List`` we have to specify an additional type as well: what type of objects do we expect our list to contain? The syntax would look something like this:

``List<Color>``
``List<String>``
``List<Double>``

Notice that the type of object contains the list goes inbetween ``<>`` which are called **angle brackets**. Also notice that the primitive types that we used before like ``int`` and ``double`` must be replaced by the object types of ``Integer`` and ``Double`` if they are to be used with ``List`` s.

|Exercise| **Exercise**

You do not write code in this exercise. Instead, consider each numbered question below and write down some responses that come to mind. You are at this point quite new to lists, so take your time and try to think of the best responses you can.

1. What are some examples of lists? For example, I might use a ``List<String>`` to record the books that I've read this year and the order that I read them in.

Think of possible applications of the other two types of lists mentioned:

* ``List<Color>``

* ``List<Double>``

For each of the above, try to find an example where at least one of the following is true:

* The order of elements in the list is important.

* There can be duplicates in the list.

2. Suppose we spin a `Roulette <https://en.wikipedia.org/wiki/Roulette>`_ wheel some number of times, and we must report the numbers that show on the wheel when it stops. Note that:

* The same number may appear multiple times.

* The order of the numbers' appearance is important.

Thus, we need a ``List<?>``, but what type of element should be in this list?

3. Can you think of a problem where having ``List<Boolean>`` would be useful?

4. Suppose we have some kind of a ``List``. What kinds of operations might we want to perform on that ``List``?

List behaviors
==============

Regardless of the type of list we are using, we would expect all lists to have the same basic behaviors:

* Adding something to the list
* Finding the nth element in a list
* Finding what position an element is in on the list
* Removing something from the list
* Determining the length of the list

Since these behaviors are common to all lists, we would abstract them out into an ``interface`` . A partial interface for ``List`` might look like the following::

    public interface List<T> {
        public boolean add(T e);
        public T get(int i);
        public int indexOf(T e);
        public boolean remove(T e);
        public T remove(int i);
        public int size();
    }

Pay close attention to the syntax here. Notice that we are declaring an ``interface`` here instead of a ``class`` . Also note that an ``interface`` only contains method signatures, it does not describe how these methods should work. It will be up to the specific classes that implement the ``interface`` to make the determination as to how these methods should be implemented.

The method signatures in the ``interface`` correspond to the above behaviors that we expect all Lists to have. The ``T`` that you see in the angle brackets represents the **parametric type** of the list. Once this parametric type has been supplied to the list then all instances of ``T`` will be replaced with this type. For example, if we had a ``List<String>`` then the complete method signature for ``add`` becomes ``public boolean add(String e)``.

This is only a partial specification of the List ADT. You can see the full Java ``List`` interface and what it contains `in the documentation <https://docs.oracle.com/javase/8/docs/api/java/util/List.html>`_ .

Implementations
===============

Now that we have an idea of what behaviors a ``List`` can perform, let's turn our attention to some implementations. There are many implementations of ``List`` available, but two popular ones are `ArrayList <https://docs.oracle.com/javase/8/docs/api/java/util/ArrayList.html>`_ and `LinkedList <https://docs.oracle.com/javase/8/docs/api/java/util/LinkedList.html>`_ .

We would say that both of these classes ``implement`` the ``List`` interface. Implementing an interface is a lot like entering into a contract. Any class that implements an interface is required to implement **all** of the methods that the interface contains. This means that the ``ArrayList`` and ``LinkedList`` classes must contain ``add()``, ``remove()``, etc. Note, however that the way that these classes choose to implement these methods can and probably will be different. This allows us to easily swap out one ``List`` for another if we determine that there may be an advantage to doing so, since we know that all ``List`` implementations will contain the same behaviors and be able to perform the same kinds of functionality.

In this case, an ``ArrayList`` uses a simple array to keep track of our list, whereas a ``LinkedList`` uses something called links or pointers (a topic that we won't cover in this class). The effect of these choices is that ``ArrayLists`` are not as good at inserting or deleting values due to the fact that arrays are difficult to resize, whereas ``LinkedLists`` can be resized much more easily. On the other hand, looking up elements in an ``ArrayList`` is typically much faster as the pointers do not allow for the list to be searched as easily. This means that lists of relatively fixed size would likely benefit from using an ``ArrayList`` whereas lists that change in size often would probably benefit more from using ``LinkedList``. Again, note that because the behavior of ``ArrayList`` and ``LinkedList`` is the same, it is possible and convenient for us to refer to them by their interface (``List``) at times.

You can see this in the way that we create lists in our code:: 

    List<String> eating = new LinkedList<String>();

Notice that the type on the left side of the equals sign is left as ``List`` which is the interface type **not** the class type. This allows us to quickly and easily switch out what type of list we are using simply by changing the type of list on the right hand side of the equals sign (to ``ArrayList`` for example). Since both of these classes implement the ``List`` interface we know that any methods that are called on this list will still work even though we have change what type of list we are using!

To add values to our list we simply use the appropriate method:: 

    eating.add("open mouth");
    eating.add("insert food");
    eating.add("chew");
    eating.add("chew");
    eating.add("swallow");

|CodingEx| **Coding Exercise**

To get started, open the ``UsingLists`` class. Declare your list and add some things to it, using the code above as a guide. Print out your list after adding some values to it and verify that it looks reasonable.

If Eclipse complains about using ``List`` or ``LinkedList`` then let it help you import the appropriate types. Be sure to use the ones that start with ``java.util`` .

Now try the other methods: ``remove()``, ``get()``, etc. Practice them and print out the list to get a feel for how to use these kinds of objects.

Once you are done, change the implementation from ``LinkedList`` to ``ArrayList``, and verify that you see no difference in the program's behavior.