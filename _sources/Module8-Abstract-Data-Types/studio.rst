=====================
Module 8 Studio
=====================

Studio 8: Objects, Equality, ADTs, and Collections
:::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::

Studio activities should not be started before class! Come to the session and work on the activity with other students!



Studio Setup and Procedure
============================

* Form a group of 2-3 students and find a TA or instructor to work with.

* All but one member of your group should have this web page open so you can follow along and see the instructions as you work.

* Plan to work on one computer (using Eclipse).

  * Initially, one of you will be in charge of typing at that computer.

  * Throughout the studio you should trade who is in charge of the keyboard.

**READ THE FOLLOWING FULLY BEFORE PROCEEDING**

1. Have **one person** in your group create a new team by `clicking here <https://classroom.github.com/a/Pl4vBTun>`_ and going to the ``OR Create a new team`` box at the bottom of the page. The team name should include the last names of all your group members. For example, if Xia and Smith are working together, the team name should be something like “XiaSmith”.

2. **After the team is created**, all other members of your team should click on the same link and follow the instructions to join the team.

   1. **Be careful to join the right team!** You won’t be able to change teams yourself and will have to contact instructors if there’s a problem.

   2. **Be sure everyone else joins the team!** If grades don’t get entered correctly we will use the team to help verify credit for a particular studio.

3. Finally, one person should import the studio repository into Eclipse, as described in `Assignment 0’s Add the assignment to Eclipse <https://classes.engineering.wustl.edu/2021/fall/cse131//modules/0/assignment#4-add-the-assignment-to-eclipse>`_

   * All team members will have access to the work pushed to GitHub. Be sure to ``Commit and Push`` at the end of the day so everyone can refer back to the work later as needed.



Objects, Equality, and Composition
============================

Design and implement the classes described based on the story given. Follow the instructions carefully. Don’t rush ahead until you have successfully completed the specified work.

1. Read the following:

   * A ``Date`` has-a month, day, and year. It also has-a field that indicates whether the date is a holiday or not. (To simplify your work you may assume that all months have 31 days)

   * A ``Time`` has-an hour (0 to 23) and a minute (0 to 59). It also has-a field that indicates whether the time should be shown in 12- or 24-hour format (this dictates how ``toString()`` behaves) .

   * You can assume that only legitimate input values are specified for anything your constructor requires.

   * Think carefully about what your constructor for ``Time`` should retain. Assume all times are in 24-hour format.

     * What is the essence of such a Time object?

     * What instance variables are required to capture its essence?

2. Create JavaDoc comments for your constructors that explain the expected parameter values.

3. Now implement ``toString()`` for each of these classes, returning a ``String`` that is appropriately descriptive.

4. Create a few instances and print them out in the ``main()`` method of the each class.

5. We next equip our two classes with the ability to tell whether they do or do not *equal* a given ``Object``.

For each of the two classes, let’s make Eclipse generate the ``equals()`` and ``hashCode()`` methods.

1. While editing each class, go to the ``Source`` menu and select ``Generate hashCode() and equals()...``

2. You are presented with a menu of instance variables to use for ``equals()`` and ``hashCode()``.

This is an important step. Decide *which* of the instance variables (fields) should be used to compare two objects of this kind.

These classes were specified such that **not all** of the fields are relevant for this comparison. Talk this over, make your choices, and then….

1. Click ``Generate``

2. Take a look at the code that is generated. Parts of it may not make sense, but there should be some familiar parts too.

* ``hashCode()`` is a way to assign an integer to a complex object. Hash Codes are used for a variety of important things. One of the requirements for them to work is that any items that are considered equal (via ``equals()``) have the same ``hashCode()`` value. This requirement only goes in the direction stated, so one possible legal implementation is simply:

::

   public int hashCode() {
      return 0;
   }

However, you can see that the code Eclipse generated is much more complicated than that.

For now, imagine that you have before you lots of lockers, each labeled with an integer. Think of ``hashCode()`` as returning an integer that represents the only locker in which this object could be found. Thus, if you want to see if the object exists in all of the lockers, you really need only check one locker.

Convince yourself that if two objects of the same type (for example, ``Date``) equal each other, then their ``hashCode()`` values are the same as computed by the Eclipse-generated code.

* ``equals(Object obj)``: With regard to the code automatically generated for ``equals(Object obj)``, the `contract in Java for equals <https://docs.oracle.com/en/java/javase/13/docs/api/java.base/java/lang/Object.html#equals(java.lang.Object)>`_ includes the following; read over the code and convince yourselves that the code enacts the proper contract:

  * If ``this`` and ``obj`` are physically the same object, then the result should be ``true``.

  * No instantiated object equals the ``null`` reference. The ``this`` reference is always to an actually instantiated object.

  * If ``this`` and ``obj`` are objects of different types, then the answer must be ``false``.

  * If none of the above rules applies, then equality can be based on any consistent comparison of any subset of the objects’ fields.

6. Instantiate some ``Date`` and ``Time`` objects (several of each) and ensure that they compare properly to each other.

Remember to use ``a.equals(b)`` to see if ``a`` and ``b`` equal each other! If you use ``==``, the comparison is restricted to whether the two objects are physically the same: the ``equals(Object obj)`` method is not run for that comparison.

7. Let’s now make some lists and sets of the objects we have created so far. We’ll focus on ``Date``.

   1. In the ``main`` method of each class you should already be creating and comparing instances of your objects.

   2. After you have instantiated 5 objects create a ``List`` of such objects by using the following code:

::
   
    LinkedList<Date> list = new LinkedList<Date>();


The angle bracket notation is used to specify parametric types. It may help to read the above line of code as:

Instantiate a new linked list of Date objects and assign that object to the variable named list.

You may have to use Eclipse suggestions to import the proper classes, which will come from the ``java.util`` package.

8. What can we do with a `LinkedList <https://docs.oracle.com/en/java/javase/13/docs/api/java.base/java/util/LinkedList.html>`_ object? Click on the link in the sentence before this one and check out the API.

Note that in the documentation, ``E`` refers to the type of element in the list you construct. In this running example, that would be a ``Date`` object.

9. Add some of your ``Date`` objects to the ``list`` list and print it out when you are done.

To print it you need only say:

::

   System.out.println(list);

10. Let’s see what happens when we add two ``Date`` objects to the list that ``equal`` each other:

::


   Date d1 = new Date(...stuff your constructor needs);
   Date d2 = new Date(...same info as above, so these will equal each other);
   list.add(d1);
   list.add(d2);
   list.add(d1);
   System.out.println(list);

What do you see? Does the same date appear three times in the list?

11. Let’s do the same thing but this time with a ``HashSet``. After the code you have written so far, add:

::

   HashSet<Date> set = new HashSet<Date>();
   set.add(d1);
   set.add(d2);
   set.add(d1);
   System.out.println(set);

Do you you see multiple occurrences of equal ``Date`` objects in the set?

**Based on your observations, what is the main difference between sets and lists?**

12. **Show your work to a TA.**

The story continues: Create an ``Appointment`` class. An ``Appointment`` has-a ``Date`` and a ``Time``.

1. Design and implement an ``Appointment`` object in the ``src`` folder.

2. Just as you did with ``Date`` and ``Time``, use Eclipse to generate the ``hashCode()`` and ``equals(Object obj)``. You should base these on equality of the contained ``Date`` and ``Time`` references.

3. Read over the code Eclipse generates. Note how it *delegates* equality to the contained objects, in which you have previously defined how you want equality treated for objects of those types.

4. Using the ``main()`` in your ``Appointment`` class, create some instances of ``Appointment`` objects using ``Date`` and ``Time`` objects.

5. In your opinion, what other *has-as* should an ``Appointment`` have?

Design a ``Calendar`` object in terms of a collection of ``Appointments``.

::

   * Should you use a list or a set?
   * What methods should your `Calendar` object offer?


6. Try to implement and test the methods of your ``Calendar`` object.


Demo
======



**Commit and Push** your work. Be sure that any file you worked on is updated on `GitHub <https://github.com/>`_.


To get participation credit for your work talk to the TA you’ve been working with and complete the demo/review process. Be prepared to show them the work that you have done and answer their questions about it!

*Before leaving check that everyone in your group has a grade recorded in Canvas!*
