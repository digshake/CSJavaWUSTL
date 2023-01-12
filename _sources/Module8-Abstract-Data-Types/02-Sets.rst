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

Sets
==========================

Unlike what we saw with lists, `Sets <https://docs.oracle.com/en/java/javase/13/docs/api/java.base/java/util/Set.html>`_ are **unordered** and **do not contain duplicates**. This has very important implications on when we might choose to use a set (as opposed to a list or other ADT).

Instead of introducing you to everything that a set can do, the next exercise asks you to experiment with ``Sets`` to get a feel for how they work.

|CodingEx| **Coding Exercise**

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
   
5. Open the ``UsingSet`` program.

   * Copy and paste the code from ``UsingList``, but change the type of the collection
     * from List to Set
     * from ``LinkedList`` to ``HashSet``
	 
	 
List or Set?
---------------

So far we have seen lists and sets which are two different types of ADTs. As programmers it is important to determine what data structure is most appropriate for the data being stored. Using what you know about lists and sets, determine the most appropriate data type to use for the following data sets:

* The books you've read in the past year

	* Can you think of reasons why both lists and sets may be appropriate for this data set?

* The toppings on a pizza

* The songs playing at a party

* A deck of cards

