=====================
Module 8 Exercises
=====================

Exercise : 8.25. Examples of a list
:::::::::::::::::::::::::::::::::::::::::::::::::::

You do not write code in this exercise. Instead, consider each numbered question below and write down some responses that come to mind. You are at this point quite new to lists, so take your time and try to think of the best responses you can.

To record your work here, create and edit a new Java class ``ThinkingAboutLists`` in the ``exercises8`` package of your ``exercises`` folder. You can enter the text in comments there.

1. What are some examples of lists? In the introductory video, I spoke about a list of books that I read this summer and a list of temperature readings. Those might be declared ast ``List<String>`` and ``List<Double>``, respectively. The ``String`` could represent the title of each book I read, and the ``Double`` could represent each temperature reading.

Think of possible applications of the other two types of lists covered in the video:

* ``List<Color>``

* ``List<Account>``

For each of the above, try to find an example where at least one of the following is true:

For each of the above, try to find an example where at least one of the following is true:


* The order of elements in the list is important.

* There can be duplicates in the list.

2. Suppose we spin a `Roulette <https://en.wikipedia.org/wiki/Roulette>`_ wheel some number of times, and we must report the numbers that show on the wheel when it stops. Note that:

* The same number may appear multiple times.

* The order of the numbers' appearance is important.

Thus, we need a ``List<?>``, but what type of element should be in this list?

3. Can you think of a problem where having ``List<Boolean>`` would be useful?

4. Suppose we have some kind of a ``List``. What kinds of operations might we want to perform on that ``List``?


Exercise : 8.33. Using List
:::::::::::::::::::::::::::::::::::::::::::::::::::

Let’s try using the code from the end of the video. If you get stuck, look at the solution video, but only as far as it takes you to get unstuck, then try going forward on your own again.

To get started, open the ``UsingLists`` class in the ``exercises8`` package of the ``exercises`` folder.

Some important points:

* We declare the list using the abstract type ``List``.

* We instantiate it using a concrete type, such as ``LinkedList`` or ``ArrayList``.

For now, use ``LinkedList``.

* IntelliJ will say it doesn’t know what those types are. You have to mouse-over the offensive code and allow IntelliJ to suggest what you should do.

The classes you want are found in ``java.util`` so be sure to choose those.

* The ``List`` needs a type parameter, which in this case should be ``String``.

* Using your list, add the following:

  * ``"open mouth"``

  * ``"insert food"``

  * ``"chew"``

  * ``"chew"``

  * ``"swallow"``

* Print the list and verify that it's right

* Add some more things to the list and print it again

* Delete one thing and print it again

Once you are done, change the implementation from ``LinkedList`` to ``ArrayList``, and verify that you see no difference in the program's behavior (this part is not on the video).


Exercise : 8.35. Investigate the Set ADT
:::::::::::::::::::::::::::::::::::::::::::::::::::

Often in designing or writing software, it helps to use code that others have written. We have done exactly that with the ``List`` interface and its ``LinkedList`` implementation.

In this exercise you will investigate the ``Set`` interface using `Javadoc <https://en.wikipedia.org/wiki/Javadoc>`_ documentation. You will then write code to use the ``Set`` interface via its ``HashSet`` implementation, and observe what happens with the ``eating`` example from the previous exercise.

You will no doubt find some of the documentation confusing, as it refers to concepts we have not studied. Nonetheless, browsing such documentation is commonplace at all levels when searching for code that may be of use as you develop software.

Try to skim over the confusing parts to pick up the essential parts of the documentation:

* What methods does this interface or class offer?

* What parameters do those methods need?

* What kind of return result can be expected?

The methods are listed alphabetically, which does not necessarily cover the most important methods first. Skim to get what you need.

1. Browse `this documentation <https://docs.oracle.com/en/java/javase/13/docs/api/java.base/java/util/Set.html>`_ for the ``Set`` interface.

   * Find methods that resemble those you used for ``List``.

Can you find the Javadoc documentation for the ``List`` interface on your own, using `Google <http://www.google.com/>`_? Such documentation is usually found by searching for the fully qualified class, as: ``java util list``.

2. Remind yourself of the differences between a ``Set`` and a ``List``:

   * Order is important in a ``List``. The elements of a ``Set`` occur in no particular order.

   * A ``List`` can have duplicates. Attempts to add an already present element to a ``Set`` do not succeed.

3. In the `documentation <https://docs.oracle.com/en/java/javase/13/docs/api/java.base/java/util/Set.html>`_, find the list of **All Known Implementing Classes**. All of these implement the ``Set`` interface, but:

   * The method of implementation will vary

   * The performance of the implementation will vary

   * Some implementations may *exceed* the **Set** interface by offering additional functionality.

4. Browse the documentation for ``HashSet``, an implementation of the ``Set`` interface.
   
5. Open the ``UsingSet`` class of the ``exercises8`` package in the ``exercises`` folder.

   * Copy and paste the code from ``UsingList``, but change the type of the collection
     * from List to Set
     * from ``LinkedList`` to ``HashSet``


Exercise : 8.73. List and Set of Point
:::::::::::::::::::::::::::::::::::::::::::::::::::

In this exercise, you use Eclipse to *auto-generate* useful parts of a class. Try this on your own, but as you need help, run the solution video only as far as necessary for you to move forward again on your own.

1. Find and open the ``Point`` class in the ``exercises8`` package of the ``exercises`` folder.
2. Based on the comment you see there concerning *has-a*, declare the instance variables for this class, calling them ``x`` and ``y``.
3. Auto-generate the constructor by choosing ``Source``, then ``Generate Constructor using Fields``, then select ``Constructor`` from the pop-up menu.
4. Choose the fields ``x`` and ``y``, and ``OK`` to generate the constructor.
5. These fields will be *immutable*, so edit the declarations for ``x`` and ``y`` and add the ``final`` attribute. This ensures that the values of ``x`` and ``y`` can be set only by the constructor.
6. Now use Eclipse to generate the *getters* for ``x`` and ``y``.
7. In the ``main()`` method, construct and print a ``Point`` or two and verify that things look good.
   
They should not look so good. When you print a ``Point``, you getan ugly and uninformative ``String``. To get something better, we must override the ``toString()`` method.

8. Use Eclipse similarly to generate a simple ``toString()`` method.

This, and the subsequent work below, is accomplished also via the ``Source`` menu.

9. OK we are ready to make a ``Set`` of some points. Put the following code in the ``main`` method:

::

   Set<Point> set = new HashSet<Point>();
   set.add(new Point(131, 132));
   set.add(new Point(131,132));
   System.out.println("Set has " + set);

| 

1. Recalling that sets should have no duplicates, you the output from the above code should show the set having the same point twice.

2. This is because Java is using its built-in notion of *equality*: are two objects exactly the same object (as in, the same reference in memory)?

3. We need to change this behavior, so read on.

10. Now let's use Eclipse to generate ``hashCode()`` and ``equals(Object other)`` methods.

You must pick the attributes (instance variable names) upon which you wish equality to be based.

11. Rerun your code and make sure that two ``Point`` objects with the same coordinates cannot both be contained in the same set.

**Further exploration**

1. What happens if ``hashCode()`` returns a random integer? Try:

::

   public int hashCode() {
      return (int)(Math.random()*100000);
   }

* What behavior do you see in the set?

* Why do you see that behavior?

The above code makes ``hashCode()`` *inconsistent*, breaking a portion of the contract concerning object equality.

2. What happens if ``hashCode()`` always returns the same result?


::

   public int hashCode() {
      return 0;
   }

* Does this work?

* What impact does the above ``hashCode()`` have on performance?

**Now try lists**

Go back and change the ``Set`` and ``HashSet`` of your code to use ``List`` and ``LinkedList``, respectively.

1. You should see duplicates. But that's OK for lists.

2. Intentionally break ``.equals(Object other)`` by returning ``false`` always.

What aspect of the contract does this break for \`.equals(Object other)?

3. What behavior do you see?

Adding to a list does not consult ``.equals(Other object)``, so you should see no difference.

4. Now ask whether the list ``.contains(new Point(131,132))``.

Nothing should be found in the list with the broken ``.equals(Object other)``.

5. Revert the code back to its proper ``hashCode`` and ``.equals(Object other)``.


Exercise : 8.75. Design StockHolding from a user story
:::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::

OK now you are pretty much on your own:

* I will tell you a story.

* You will design an object.

* Create this object from scratch in the ``exercises8`` package of the ``exercises`` folder.

As usual, if stuck, consult portions of the solutions video.

**The story**

A ``StockHolding`` object:

``has-a``

* immutable ``String`` identifying its name (e.g., ``IBM``)

* immutable ``String`` identifying its owner (e.g., ``Ari``)

* number of share (``int``) that can change over time

* price per share (``int``) that can change over time

``and it needs:``

* A constructor

* A ``toString()``

* ``hashCode()`` and ``equals(Object other)``

You should generate the above automatically, not by hand!

Exercise : 8.85. Application of the interface
:::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::

Do your work in the ``exercises8`` package of the ``exercises`` folder.

**The story**

Define a ``PersonalProperty`` object:

``has-a``

* immutable ``int`` for its initial value

* immutable ``int`` representing the years since its initial value was established

``and it needs:``

* A constructor that takes in values for the two instance variables

* A method ``int depreciatedValue()`` that returns the value of the property according to the formula:

``initialValue`` * 0.80 \ :sup:`yearsOld`\

* A ``toString()``

**Your task**

After defining the above class, adapt it to implement the ``Valuable`` interface:

::

   public interface Valuable {
      public int getLiquidValue();
   }
