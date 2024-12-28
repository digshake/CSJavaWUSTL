=====================
Studio 9: ADT Practice
=====================

**Studio activities should not be started before class! Come to the session and work on the activity with other students!**

Studio Setup and Procedure
=====================

* Form a group of 2-3 students and find a TA or instructor to work with.

* All but one member of your group should have this web page open so you can follow along and see the instructions as you work.

* Plan to work on one computer (using Eclipse).

  * Initially, one of you will be in charge of typing at that computer.

  * Throughout the studio you should trade who is in charge of the keyboard.

**READ THE FOLLOWING FULLY BEFORE PROCEEDING**

1. Have **one person** in your group create a new team by `clicking here <https://classroom.github.com/a/bxf7wTBS>`_ and going to the ``OR Create a new team`` box at the bottom of the page. The team name should include the last names of all your group members. For example, if Xia and Smith are working together, the team name should be something like “XiaSmith”.

2. **After the team is created**, all other members of your team should click on the same link and follow the instructions to join the team.

   1. **Be careful to join the right team!** You won’t be able to change teams yourself and will have to contact instructors if there’s a problem.

   2. **Be sure everyone else joins the team!** If grades don’t get entered correctly we will use the team to help verify credit for a particular studio.

3. Finally, one person should import the studio repository into Eclipse, as described in `the setup instructions <../Module0-Introduction/software.html>`_.

   * All team members will have access to the work pushed to GitHub. Be sure to ``Commit and Push`` at the end of the day so everyone can refer back to the work later as needed.



Polynomial
=====================
This section of the studio can be tested with ``PolynomialTest`` in the ``studio9`` package.

Our first goal is to implement an object that can be used to represent a `polynomial <https://en.wikipedia.org/wiki/Polynomial>`_. For the purposes of our studio, our polynomials will all be of the single variable type, and they will also be complete with no missing terms. A ``LinkedList`` will be used to store the coefficients. For example, if we were trying to represent the polynomial x :sup:`2` + 4, our list would contain the values [1, 0, 4]. Notice that the **order** of the coefficients combined with the **length** of the list can be used to determine the power of a term.

1. Open the Java file ``Polynomial`` in the ``studio9`` package.

2. Complete the constructor - it should create an empty list.

3. Complete ``addTerm()``. This simple method should assume that the incoming term will be added to the end of the polynomial.

4. Complete ``toString()``. After this point you should be able to run the tests and view some polynomials to make sure the code you have written so far is working.

5. Complete ``evaluate()`` to evaluate the polynomial for a given value. Use the provided tests to check your work.

6. Complete ``derivative()`` which creates a new ``Polynomial`` based on the `power rule <https://en.wikipedia.org/wiki/Power_rule>`_.

Check your work with a TA before moving on.

Word Count
=====================

This section of the studio can be tested with ``WordCountTestSuite`` in the ``studio9`` package.

1. Open the Java file ``WordCount`` in the ``studio9`` package.

2. Implement the ``countWords(words)`` method to meet this specification:

::

   /**
   * Constructs and returns a map of the distinct words in the specified list with
   * each word associated with its accumulated count (that is: the number of
   * occurrences of the word in the list).
   *
   * For example, if passed a List<String> containing:
   *
   * [to, be, or, not, to, be]
   *
   * the resulting Map<String,Integer> would contain
   *
   * key="to", value=2;
   * key="be", value=2;
   * key="or", value=1;
   * key="not", value=1;
   *
   * @param words
   * @return a map which contains all of the distinct words as keys, each
   *         associated with the number of occurrences of the word
   */

Once you have finished the method, turn your attention to the ``main`` method provided to you at the end of the file. Write code that will iterate over the generated map. Notice how you have to use a for each style loop when iterating with maps. Why is this?

Ensure that ``WordCountTest`` is working and you have explained your solution to your TA before moving on.

Demo
=====================

**Commit and Push** your work. Be sure that any file you worked on is updated on `GitHub <https://github.com/>`_.


To get participation credit for your work talk to the TA you’ve been working with and complete the demo/review process. Be prepared to show them the work that you have done and answer their questions about it!

*Before leaving check that everyone in your group has a grade recorded in Canvas!*
