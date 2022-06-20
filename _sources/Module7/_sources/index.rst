=====================
This Is A New Project
=====================

.. Here is were you specify the content and order of your new book.

.. Each section heading (e.g. "SECTION 1: A Random Section") will be
   a heading in the table of contents. Source files that should be
   generated and included in that section should be placed on individual
   lines, with one line separating the first source filename and the
   :maxdepth: line.

.. Sources can also be included from subfolders of this directory.
   (e.g. "DataStructures/queues.rst").


Exercise : 7.25. Anaatomy of an object
:::::::::::::::::::::::::::::::::::::::::::::::::::

* In the ``exercises7`` package of the ``exercises`` source folder, open the ``Person`` class.

* Follow the instructions, using Java comments to designate the various parts of the object's definition.

Studio 7: Object Design
:::::::::::::::::::::::::::::::::::::::::::::::::::

* `Studio Setup and Procedure`_

* `Overview`_

  * `Cautions`_

  * `Design Problems`_

    * `Object Types`_

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

.. _Overview:

**Overview**

* This week’s studio is an exercise in design, so get your brains limbered up for some creative thinking.

* In design, there are no wrong or right answers. However, some designs are better than others for certain purposes. It will be important for each person in your group to be able to defend your team’s design.

  * If some member does not understand an aspect of your team’s design, the entire team may be docked studio credit. It is not necessary that all decisions be made with unanimity, but the issues that influence the design one way or the other must be understood by all members of your team.

* A rush to implement something fully will be a Bad Idea. The group’s goal this week is to arrive at a design, not an implementation.

* That said, we will be developing stubs in Eclipse to represent the design, with a bit of Javadoc above each class and method to help generate documentation.

* As you design, thank about the **has-a** idea presented in the videos and articulate the **behaviors** you want your object to have.

* The design problems are presented to you in the form of a `user story <http://www.extremeprogramming.org/rules/userstories.html>`_.

.. _Cautions:

**Cautions**

* Use rich data types where possible, both to document your design and to leverage Java’s type system to avoid bugs in your program.

   For example, instead of representing a given account using an integer, an actual object ``Account`` was defined. Similarly, an integer suffices to hold color information for a pixel, but a ``Color`` class (type) was defined to provide reliable functionality and to hide details of the implementation (the idea of hiding details is referred to as “encapsulation”).

* Avoid passing parameters of generic type that represent something that could have been its own class. For example, consider using ``x`` and ``y`` coordinates to represent a point, as shown below:

::

    public double distanceBetween(int x1, int y1, int x2, int y2) {
        ...
  }

It is easy to forget the order in which the integers must be passed to ``distanceBetween``() and accidentally mis-use it. To avoid such chaos and to make the program more readable, articulate a ``Point`` object that has an x and y coordinate. The method then becomes:

::

   public double distanceBetween(Point p1, Point p2) {
      ...
  }

* Every class should have its ``toString()`` method defined, so that the class can return a ``String`` with some meaningful information about the class. Generally, ``toString()`` methods should avoid invoking the ``toString()`` methods of any other class.

* Instance variables should be defined where necessary, but declared ``private`` to guard against accidental access or modification outside of the class holding the instance variables.

* Where necessary, each class should provide methods that get and set its local instance variables.

   Recall Eclipse can generate those for you automatically.

It is customary to base the name of such methods consistently on the name of the associated instance variable:

::

     public Person getPerson() {
      return person;
  }

  public void setPerson(Person person) {
      this.person = person;
  }

.. _Design Problems:

**Design Problems**

* A number of stories appear below about various object types.

* Pick an object type, read the story, and design and implement a class in your ``studio7`` workspace for the object type.

* Include Javadoc comments in your code, and if possible, generate the Javadoc using Eclipse.

   From the ``Project`` menu choose ``Generate Javadoc...``.

* Write a simple test or two to test your implementation. (I.e., add a ``main()`` that creates some instances of your objects, calls methods to test them, and provide enough information to verify that they are working as expected. If you’ve created description ``toString()`` methods, you can simply print the objects to get a sense of their value)

* Repeat this process with another object type until the end of class.

.. _Object Types:

**Object Types**

Create and test the following object types in the ``studio7`` folder:

``Rectangle``

A rectangle has a length and a width. A rectangle should be able to provide its area and perimeter. A rectangle can indicate whether it is smaller than another rectangle in terms of area. A rectangle can indicate whether it is in fact a square. (This is mainly about the concepts needed to represent a rectangle, but the ``StdDraw`` library is included in your repository. You can also provide a rectangle the ability to draw itself on the screen)

``Die``

When a ``Die`` is constructed it is specified to have **n** number of sides. Each time the die is thrown, a random *integer* is returned in the range [1.. **n**], inclusive.

``Fraction``

A fraction has a numerator and denominator. A fraction should be able to add itself to another fraction, returning a new fraction that represents the sum. A fraction should be able to multiply itself by another fraction, returning a new fraction as the product. A fraction should be able to take the reciprocal of itself, returning that value as a new fraction. A fraction should be able to simplify itself, returning a new fraction as that simplification.

``Complex``

A `complex number <http://en.wikipedia.org/wiki/Complex_number>`_ has a real and imaginary part, each represented as a ``double``. A complex should be able to add itself to another complex number, returning a new complex number as the sum (see below). Similarly, a complex number should be able to multiply itself by another complex number, returning a new complex number as the product.

* A complex number with real part a and imaginary part b is usually shown as ``a + bi``.

* The result of adding two complex numbers, *x* and *y* , is another complex number whose real part is the sum of the real parts of *x* and *y* and whose imaginary part is the sum of the imaginary parts of *x* and *y*.

* The product of two imaginary numbers, like *(a+bi)×(c+di), is (ac−bd)+(ad+bc)i*
  
``HockeyPlayer``

A hockey player has a name and a jersey number. Most players shoot either right or left, but some can shoot either way. A player can be right- or left-handed, but shoot either right or left. This object should be able to react when a player completes a game, recording how many goals and assists the player earned in that game. A player has a certain number of goals and assists he or she has recorded over all games played. Also, a player has a certain number of **points**, which is the sum of the goals and assists a player has earned. A player has a certain number of games he or she has played.


.. _Demo:

**Demo**

**Commit and Push** your work. Be sure that any file you worked on is updated on `GitHub <https://github.com/>`_.


To get participation credit for your work talk to the TA you’ve been working with and complete the demo/review process. Be prepared to show them the work that you have done and answer their questions about it!


*Before leaving check that everyone in your group has a grade recorded in Canvas!*

Assignment 7: Students and Courses
:::::::::::::::::::::::::::::::::::::::::::::::::::

* `Assignment Setup`_

* `Creating Student and Course class`_

  * `Synopsis`_

  * `Getting Started`_

  * `Creating a Student class`_

  * `Creating a Course class`_

* `Comprehensive Unit Test`_

* `Submitting your work`_


.. _Assignment Setup:

**Assignment Setup**

To create your repository go `here <https://classroom.github.com/a/Xeql2d4p>`__. Then follow the same accept/import process described in `Assignment 0 <https://classes.engineering.wustl.edu/2021/fall/cse131//modules/0/assignment>`_.


.. _Creating Student and Course class:

**Creating Student and Course class**

.. _Synopsis:

**Synopsis**

Your task is to generate two classes ``Student`` and ``Course`` using a `test driven development approach <https://en.wikipedia.org/wiki/Test-driven_development>`_ . This means that your goal is to get the unit tests to pass, and you develop your code incrementally to get more of the tests to pass.

First, take a look at the ``StudentAndCourseTestSuite.java`` file. Unfortunately, none of the tests will currently pass. You use these tests as you develop your classes to verify whether they are working as intended. You are also encouraged to write some additional tests of your own. Be sure to test often!

.. _Getting Started:

**Getting Started**

Part of the reason that the unit tests do not pass is the classes being tested, ``Student`` and ``Course``, are empty. Your first task is to create bare bones versions of these classes with the methods that will be tested.

First, open the ``Student`` class in the assignment 7 package. Then, read the instructions below about what methods the ``Student`` class should contain. For each method, you should create what is called a `“stub.” <https://en.wikipedia.org/wiki/Method_stub>`_ A method stub is a like a placeholder for a method - you specify the method signature, but do not actually write the code for the method itself. For example, you’ll need to create a method to calculate the grade point average for a student. The tests expect a specific signature and return type. The name should be ``calculateGradePointAverage``, it won’t require any parameters, and the return type should be ``double``. A stub for it would look like:

::

   public double calculateGradePointAverage() {
      return 0.0; //FIXME write a method to compute GPA
   }


Returning 0 for this method is clearly the incorrect thing to do, but we are simply creating a placeholder for this method with the idea that we will come back and provide functionality at a later time.

Read the instructions below and create stubs for all of the ``Student`` class methods. As you do so, you should notice that the unit tests have fewer errors, since it is now able to find the class and the methods being tested. Since the methods don’t work, however, most tests will still fail.

Once you have done this for the ``Student`` class, repeat this process for the ``Course`` class. After you have done this for both classes, you should not see any more errors in any of the unit tests (however none of them will pass yet!). If you still see errors, examine the test to determine what method is missing, then include another method stub.

Once you have finished creating all the stubs, follow the directions below to implement the desired functionality for your methods.

.. _Creating a Student class:

**Creating a Student class**

1. Start crafting a ``Student`` class. Students have lots of wonderful properties, but we are primarily interested in these:

   * First Name
  
   * Last Name

   * Student ID Number

   * Attempted Credits

   * Passing Credits

   * Total Grade Quality Points

   * Bear Bucks Balance

How do you know what to name your instance variables? How do you name the getters and setters? Good questions, and this relates to encapsulation.

Your instance variables can, should, and must be declared ``private``. In this way, their names are not exposed outside the Student class, which protects them from unintended access.

On the other hand, the methods may be referenced by the unit test. The names and type signatures of your method must conform to their use in the unit test. For example, the ``test()`` method in the ``assignment7.tests.student`` package’s ``StudentFullNameTest.java``’s contains the constructor call:


::

   Student student = new Student(firstName, lastName, 1);
   String expected = firstName + " " + lastName;
   assertEquals(expected, student.getFullName());

From this line we can reason that the constructor takes in a ``String``, another ``String``, and an ``int``. We can also reason that the first parameter of the constructor is the student’s first name, and the second parameter is the student’s last name. You can similarly read the test code to see how the methods are named.


   Go ahead and create a stub for this constructor in ``Student.java``. Once you save your work. Check the ``test()`` method in ``StudentFullNameTest.java`` and confirm that it’s no longer underlined in red, which will verify that you’ve created a constructor with an appropriate signature.

   If you haven’t already done so, add any instance variables that you think you may need and ensure that the constructor initializes them appropriately.


But why all the fuss about encapsulation? Suppose you wanted to count the number of times a student’s ID is accessed. If the instance variable is public, then access to the variable’s value can occur in any other class, beyond the view of the ``Student`` class. By making the instance variable ``private``, and requiring a getter to access the value, the ``Student`` class can count the number of accesses to the value.

Suppose you wanted for some reason to change the representation of a student’s ID from an integer to a string, or suppose you really want to change the name of the instance variable. If you made the variable public, then other code may subsequently be written that requires the name and type of the instance variable to stay the same.

By making the instance variable ``private``, you encapsulate it within the ``Student`` class and you have control therefore over that instance variable’s future.

Suppose you decide that a student’s ID should not be a settable property of a Student, by any code outside the Student class. If you make the instance variable public, code outside of the Student class can read or write the instance variable. Only by making the variable private can you arrange for the value to be manipulable within the Student class, but not outside of that class.

Encapsulation allows us to retain control over some aspects of a class’s specification, while releasing only those portions that are necessary by design.

Add the above properties to your class, create a constructor, create some getters and setters, and test!

2. Now we want to add some functionality to our ``Student`` class. Below is a list of methods that we are asking you to implement. As you read through the methods below and consider their implementation, you may develop a feeling that your class should have something it does not yet have. Feel empowered to introduce other instance variables as necessary. Remember that they too deserve nice names, they should be initialized in your constructor(s), but they do not need (nor should they have) getters or setters. They are used to manage data within your class.

Once you have implemented a method run the tests again and pay attention to which tests pass.

``String getFullName()`` - returns the first and last names with a space between them.

``int getId()`` - returns the student id number.

``void submitGrade(double grade, int credits)`` - this method takes in a course grade (as a value between 0 and 4) and the number of credits for a course, and updates the students GPA accordingly. For the purposes of this assignment a grade greater than or equal to 1.7 is considered passing and you can think about it as the final, overall grade for the course. **You may want to read through the descriptions of the next three methods to get a sense of information you need to keep track of**.


   **Warning**: In a moment, you will be required to calculate the grade point average.
   Keeping track of what are called quality points (credits multiplied by the grade points) will likely prove useful.


``int getTotalAttemptedCredits()`` - returns the number of attempted credits (that is, credits for all submitted grades).

``int getTotalPassingCredits()`` - returns the number of passing credits (that is, credits for which the student received at least a 1.7 grade).

``double calculateGradePointAverage()`` - **GPA can be computed by the following formula**:


Take the number of credits for a course and multiply it by the grade for that course. This is called the *quality points*. GPA is computed as the sum of all of the quality points for each course the student has taken divided by the total number of *attempted credits*. **Hint: Think carefully about the choice of type for quality points**


``String getClassStanding()`` - returns the students class standing based on how many passing credits they have:

* Fewer than 30: First Year

* 30 or more but less than 60: Sophomore

* 60 or more but less than 90: Junior

* 90 or more: Senior

``boolean isEligibleForPhiBetaKappa()`` - The `Membership and Selection Process <https://pages.wustl.edu/pbk/membership-and-selection-process#overlay-context=pbk/membership-and-selection-process>`_ outlines the guidelines for eligibility. Let us ignore the College of Arts and Sciences requirement and focus only on the details we are tracking in this assignment.

* a student who has completed at least 98 credits with a cumulative GPA of at least 3.60 (here “completed” means that a final grade has been submitted)

* a student who has completed at least 75 credits with a cumulative GPA of at least 3.80

``void depositBearBucks(double amount)`` - increases the Bear Bucks balance by ``amount``

``void deductBearBucks(double amount)`` - decreases the Bear Bucks balance by ``amount``

``double getBearBucksBalance()`` - returns the Bear Bucks balance

double cashOutBearBucks() - Zero out the Bear Bucks balance and return the appropriate amount as (previously) specified in the Terms of Service for `Bear Bucks <https://card.wustl.edu/bear-bucks/>`_ :


* Remaining balance will be refunded, minus a $10 administrative fee.

* Balances of $10 or less will be forfeited.

For example:

if your balance was $1000 and your “cashed out” you would receive $990 (via the return value) and your balance would be $0.

if your balance was $42 and your “cashed out” you would receive $32 (via the return value) and your balance would be $0.

if your balance was $9 and your “cashed out” you would receive $0 (via the return value) and your balance would be $0.

::

   **Note:** since the creation of this assignment, WashU has changed the policy and you can no longer get refunded from your bear bucks account.

   **To reiterate:**  the student's Bear Bucks balance should be zeroed out as a result of calling this method.


``Student createLegacy(String firstName, Student other, boolean isHyphenated, int id)`` - it is not unusual for two students to meet at college and eventually start a family, and send their children to the same school. Imagine that in an effort to incentivize alums to send their children to their alma mater, WashU will transfer unused Bear Bucks to a legacy. The administrative fees, of course, still apply (and sadly to both parents).

This method should take parameters for a first name, the other parent, whether the last name should be hyphenated, and a student id number to create and return a new ``Student`` object as described below. Note: there are three particpants in this method:

* ``this`` parent

* the other parent

* the child ``Student`` that is created and returned by the method.

The newly-created legacy’s state will be determined by:

* The legacy’s first name and id (as you might have imagined) will determined by the ``firstName`` and ``id`` parameters.

* The legacy’s last name with either be the last name of ``this`` or a hyphenated combination of this-other depending on the value of ``isHyphenated``.

``String toString()`` - returns the students full name and student ID

3. Before moving on, make sure that all of the tests for ``Student`` pass! There are other tests referenced by ``CourseTestSuite`` (for the ``Course`` class that you develop below) that won’t pass yet.

4. Now go back and think again about the instance variables of this class and their getters and setters. Beyond just the getters we dictated for testing purposes, which of the instance variables should have getters, and which should have setters?

To reason about this, you need to think about what the unit test is doing, and you must provide getters or setters so that it can work. But beyond that, think about how this class will be used.

* Should the student ID have a setter? That is, do we want to provision for the student ID of a ``Student`` object to change? What does the initial story of a ``Student`` object say about that?

* How about the name? Washington University allows students to change their names.

* Should the number of credits be settable directly outside the class? Or should access be more carefully controlled?

The TAs will discuss this with you when you demo.

.. _Creating a Course class:

**Creating a Course class**

The ``Course`` class should contain the following properties:

* Name

* Credits a student earns by taking this course

* Roster of enrolled Students

* Number of seats in the classroom (the capacity)

1. Add these properties to your class, create a constructor, create some getters and setters, and test!

As before, drive your software development by the unit test. You may want to look at the way unit tests are “constructing” an instance of the class to identify the expected parameters.

Avoid creating extra functionality that is not demanded by the unit test or specifically required in this document. This approach saves you time and keeps the resulting code simple.

   Some of the Unit tests expect getters with specific names and parameters. As you work you may want to run tests in ``CourseTestSuite.java``. Double click on failed tests to be take to the code for the test. If there are methods that are underlined in red that you haven’t implemented, be sure to implement them. (There are 4 “getters” that are not explicitly listed in this description that you need!)

2. Next, implement the following functionality:

``boolean addStudent(Student s)`` - Check to make sure that the student has not already enrolled and that there is available space. Be sure to update all appropriate instance variables. Return ``true`` if ``s`` has been enrolled as a result of this call. Return false otherwise

How will you check that the student has not already enrolled? You’ll have to keep track of the students as they enroll. Fortunately, when a ``Course`` object is constructed, we know the maximum number of seats that the course offers, so we know the maximum number of enrolled students.


From what we have studied, what is the appropriate data type to keep track of enrolled ``Students`` in a ``Course``?

``Student getStudentAt(int index)`` - return the ``Student`` at the ``index`` added.

``String generateRoster()`` - Returns a String that represents a roster with all of the ``Students`` in the course. The roster should contain the ``Students’`` names. Make sure to omit *empty* seats!

``double calculateAverageGPA()`` - returns the average GPA of all students enrolled in the course. Make sure to omit *empty* seats from this calculation.

``String toString()`` - The returned ``String`` should contain the course name and credits.

.. _Comprehensive Unit Test:

**Comprehensive Unit Test**

When you’re completely done run all the tests in ``StudentAndCourseTestSuite.java``, which runs both the ``Student`` and ``Course`` tests. If you’ve successfully implemented all the required methods to behave as expected, all the tests should pass.

.. _Submitting your work:

**Submitting your work**

To submit your work come to office hours or class on an “Assignment day” and sign up for a demo via `wustl-cse.help <https://wustl-cse.help/>`_. Be prepared to show them the work that you have done and answer their questions about it!






















