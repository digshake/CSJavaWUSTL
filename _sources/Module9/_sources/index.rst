=====================
Module 9
=====================

.. Here is were you specify the content and order of your new book.

.. Each section heading (e.g. "SECTION 1: A Random Section") will be
   a heading in the table of contents. Source files that should be
   generated and included in that section should be placed on individual
   lines, with one line separating the first source filename and the
   :maxdepth: line.

.. Sources can also be included from subfolders of this directory.
   (e.g. "DataStructures/queues.rst").

Studio 9: Recursive Puzzles 
::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::

**Studio activities should not be started before class! Come to the session and work on the activity with other students!**

* `Studio Setup and Procedure`_

  * `Code To Use`_

  * `Videos To Watch`_

  * `Map Name to Height Warmup`_

  * `Word Count`_

  * `University Database`_

* `Demo`_


.. _Studio Setup and Procedure:

**Studio Setup and Procedure**

* Form a group of 2-3 students and find a TA or instructor to work with.

* All but one member of your group should have this web page open so you can follow along and see the instructions as you work.

* Plan to work on one computer (using Eclipse).

  * Initially, one of you will be in charge of typing at that computer.

  * Throughout the studio you should trade who is in charge of the keyboard.

**READ THE FOLLOWING FULLY BEFORE PROCEEDING**

1. Have **one person** in your group create a new team by `Logo <https://classroom.github.com/g/n3TfYnGC>`_ here and going to the ``OR Create a new team`` box at the bottom of the page. The team name should include the last names of all your group members. For example, if Xia and Smith are working together, the team name should be something like “XiaSmith”.

2. **After the team is created**, all other members of your team should click on the same link and follow the instructions to join the team.

   1. **Be careful to join the right team!** You won’t be able to change teams yourself and will have to contact instructors if there’s a problem.

   2. **Be sure everyone else joins the team!** If grades don’t get entered correctly we will use the team to help verify credit for a particular studio.

3. Finally, one person should import the studio repository into Eclipse, as described in `Assignment 0’s Add the assignment to Eclipse <https://classes.engineering.wustl.edu/2021/fall/cse131//modules/0/assignment#4-add-the-assignment-to-eclipse>`_

   * All team members will have access to the work pushed to GitHub. Be sure to ``Commit and Push`` at the end of the day so everyone can refer back to the work later as needed.

.. _Code To Use:

**Code To Use**

* interface `Map<K,V> <https://docs.oracle.com/en/java/javase/13/docs/api/java.base/java/util/Map.html>`__

  * `put(key, value) <https://docs.oracle.com/en/java/javase/13/docs/api/java.base/java/util/Map.html#put(K,V)>`_

  * `get(key) <https://docs.oracle.com/en/java/javase/13/docs/api/java.base/java/util/Map.html#get(java.lang.Object)>`_

  * `getOrDefault(key, defaultValue) <https://docs.oracle.com/en/java/javase/13/docs/api/java.base/java/util/Map.html#getOrDefault(java.lang.Object,V)>`_

  * `size() <https://docs.oracle.com/en/java/javase/13/docs/api/java.base/java/util/Map.html#size()>`_

  * `keySet() <https://docs.oracle.com/en/java/javase/13/docs/api/java.base/java/util/Map.html#keySet()>`_

  * `entrySet() <https://docs.oracle.com/en/java/javase/13/docs/api/java.base/java/util/Map.html#entrySet()>`_

* class `HashMap<K, V> <https://docs.oracle.com/en/java/javase/13/docs/api/java.base/java/util/HashMap.html>`_

  * `new HashMap() <https://docs.oracle.com/en/java/javase/13/docs/api/java.base/java/util/HashMap.html#%3Cinit%3E()>`_

.. _Videos To Watch:

**Videos To Watch**

You should have already watched these videos in preparation for the studio, but they are repeated here for your reference.

.. youtube:: MwPrMAG4bLg

.. youtube:: De-S0bYg_-4

.. _Map Name to Height Warmup:

**Map Name to Height Warmup**

1. Open the Java file NameToHeight in the studio9 package and edit the main method.

2. Create a new instance of a Map from key type String to value type Integer.
Note: `Map<K,V> <https://docs.oracle.com/javase/8/docs/api/java/util/Map.html>`__ is an interface so you will need to create an instance of a `class which implements it <https://docs.oracle.com/javase/8/docs/api/java/util/HashMap.html>`_.

3. Associate each member of your team’s name with their height (use inches or centimeters at your preference).

4. Repeatedly prompt the user (via ArgsProcessor) for a name. If the users cancels by hitting the cancel button (``ArgsProcessor`` will return a ``null``) then stop prompting for more names. Otherwise, look up the name in the map for the associated height. Print out both the name and the height.
Be sure to handle the ``null`` case for names that are not in the map and print an appropriate message.

Explain your solution to your TA before moving on.

.. _Word Count:

**Word Count**

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

Ensure that ``WordCountTest`` is working and you have explained your solution to your TA before moving on.

.. _University Database:

**University Database**

This section of the studio can be tested with ``UniversityDatabaseTestSuite`` in the ``studio9`` package.

1. ``UniversityDatabase`` will rely on a working implementation of the ``Student`` class from Assignment 7. Copy the code from your Student class into the ``Student.java`` file in the ``studio9`` package and make sure any errors are resolved before proceeding. You may use which ever implementation you feel is best.

2. Open ``UniversityDatabase`` in the ``studio9`` package.

3. Declare a single ``private final`` instance variable of type ``Map<String, Student>``.

   * You’ll need to import that ``Map`` interface (``java.util.Map``).

4. Implement the default constructor (``UniversityDatabase()``) to initialize the map instance variable.

5. Implement ``public void addStudent(String accountName, Student student)`` which associates with the key ``accountName`` the value ``student`` in the map.

6. Implement public int ``getStudentCount()``

7. Implement ``public String lookupFullName(String accountName)`` by looking up the student and then using the ``getFullName()`` method on ``Student``. If the student is ``null``, you should return ``null`` as the full name.

8. Implement ``public double getTotalBearBucks()`` via iterating over the map.

Ensure that ``UniversityDatabaseTestSuite`` is working and you have explained your solution to your TA before moving on.

.. _Demo:

**Demo**

**Commit and Push** your work. Be sure that any file you worked on is updated on `GitHub <https://github.com/>`_.


To get participation credit for your work talk to the TA you’ve been working with and complete the demo/review process. Be prepared to show them the work that you have done and answer their questions about it!

*Before leaving check that everyone in your group has a grade recorded in Canvas!*


Assignment 9: Scene Composer
::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::

* `Assignment Setup`_

  * `Overview`_

  * `Requirements`_

  * `Code base`_

* `Submitting your work`_


.. _Assignment Setup:

**Assignment Setup**

To create your repository go `here <https://classroom.github.com/a/DDL1ilgU>`__. Then follow the same accept/import process described in `Assignment 0 <https://classes.engineering.wustl.edu/2021/fall/cse131//modules/0/assignment>`_.

This assignment is fairly creative in that:

* There is no unit test to guide your work

* The manner in which your solution works is up to you, although there is a video of Prof. Cytron’s solution

* The application you develop here allows creation of artistic images

.. _Overview:

**Overview**

The idea is to develop an application in which a user (presently, just yourself) can compose images.

Some of these images will be available already by names of your choosing. For example, the names ``f0``, ``f1``, …, ``f9`` represent 10 forest images that can be drawn on the screen.

You will allow users to record a sequence of images, and then select a name for that sequence, so that the sequence itself can be called up by its new name.

There is no limit to the fun that can be had here, because new sequences can be created at will and recorded to be known by name.

You can create your solution all in one ``main`` method as you did at the beginning of the semester. Or you can use objects as you have more recently been taught. How you construct your solution is up to you but it must meet the requirements stated below to earn credit.

The code base provided to you draws images using somewhat transparent colors, so that if you draw the same image twice, its intensity increases.

.. _Requirements:

**Requirements**

Before continuing, take a look at `this video <https://wustl.box.com/s/o0cnmrq5enboqsq2t3u8xapcatr511fz>`__.

To receive credit you must:

* Use a ``Map<String,Drawable>`` to allow users to recall existing scenes and create new ones.

* Use a ``List<Drawable>`` as needed to store a list of ``Drawables``.

* Create an initial scene with multiple objects and store it under the name "``init``".

* Prompt the user repeated for input (using ``ArgsProcessor``).

* Properly clear the screen when ``clear`` is typed.

* Cease prompting the user when ``end`` is typed.

* Allow the recording of a sequence of ``Drawables``, and the subsequent recall of that sequence for display.

.. _Code base:

**Code base**

Before continuing, take a look at `this video <https://wustl.box.com/s/s82qapv7gwtz6pw4fryrxjamqxp0nryo>`_.

Familiarize yourself with the code by watching the video and looking at the ``assignment9`` and contained packages.

OK! implement at least the features above and have fun with this!

.. _Submitting your work:

**Submitting your work**

To submit your work come to office hours or class on an “Assignment day” and sign up for a demo via `wustl-cse.help <https://wustl-cse.help/>`_. Be prepared to show them the work that you have done and answer their questions about it!