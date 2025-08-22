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

Object Equality
==========================

What does it mean for two things to be equal? For primitive types (int, double, etc.) this is a simple concept. The two values are either equivalent or not. For objects, this is not always as straightforward. Consider the following code:: 

	Person p1 = new Person("John", "Smith");
	Person p2 = new Person("John", "Smith");
	
Are the two ``Person`` objects created above equal? This is not a simple question to answer. In one sense we can see the equality: the name "John Smith" is being used for each person that's being created. On the other hand, we also know that it is possible for two people to have the same name, so it is possible that the above code is intended to represent two similarly named individuals.

|CodingEx| **Coding Exercise**

In this exercise, you use VS Code to *auto-generate* useful parts of a class. 

1. Find and open the ``Point`` class.
2. Based on the comment you see there concerning *has-a*, declare the instance variables for this class, calling them ``x`` and ``y``.
3. Auto-generate the constructor by right clicking the code and then selecting ``Source Action -> Generate Constructors``
4. Choose the fields ``x`` and ``y``, then generate the constructor.
6. Now use VS Code to generate the *getters* for ``x`` and ``y`` by doing another ``Source Action`` and selecting the appropriate option.
7. In the ``main()`` method, construct and print a ``Point`` or two and verify that things look good.
   
They should not look so good. When you print a ``Point``, you getan ugly and uninformative ``String``. To get something better, we must override the ``toString()`` method.

8. Use VS Code similarly to generate a simple ``toString()`` method.

This, and the subsequent work below, is accomplished also via the ``Source Action`` menu.

9. Now let's use VS Code to generate ``hashCode()`` and ``equals(Object other)`` methods.

You must pick the attributes (instance variable names) upon which you wish equality to be based.

``equals()`` vs. ``==``
------------------------------

We have now seen two ways of determining equality: ``==`` and ``equals()``. Why are there two ways for determining equality? And how do you know which one to use?

For primitive types (ints, doubles, etc.), the answer is simple: always use ``==``. This will work every time for these simple values.

For objects, you need to think a bit more about what it is that you are trying to determine. ``equals()`` will examine the contents (instance variables) of the objects being compared and use that to make its determination. This means that **two separate** objects can be considered equal if some or all of their instance variables are equal, as defined by the ``equals()`` method.

When comparing objects, ``==`` will result in true only if the objects on the left and right side **are the same object**.

|CodingEx| **Coding Exercise**

Open the ``Person`` program, and work through the provided examples. Make sure that you understand the difference between ``equals()`` and ``==`` before moving on!
