=====================
Assignment 7: Students and Courses
=====================

Assignment Setup
=====================

To create your repository go `here <https://classroom.github.com/a/4zpKPVmh>`_. Then follow the same accept/import process described in `the setup instructions <../Module0-Introduction/software.html>`_.



Creating Student and Course class
=====================


Your task is to generate two classes ``Student`` and ``Course`` using a `test driven development approach <https://en.wikipedia.org/wiki/Test-driven_development>`_ . This means that your goal is to get the unit tests to pass, and you develop your code incrementally to get more of the tests to pass.

First, take a look at the ``StudentAndCourseTestSuite.java`` file. Unfortunately, none of the tests will currently pass. You use these tests as you develop your classes to verify whether they are working as intended. You are also encouraged to write some additional tests of your own. Be sure to test often!

Getting Started
=====================

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

Creating a Student class
=====================

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

``int getTotalAttemptedCredits()`` - returns the number of attempted credits (that is, credits for all submitted grades).

``int getTotalPassingCredits()`` - returns the number of passing credits (that is, credits for which the student received at least a 1.7 grade).

``double calculateGradePointAverage()`` - **GPA can be computed by the following formula**:


Take the number of credits for a course and multiply it by the grade for that course. This is called the *quality points*. GPA is computed as the sum of all of the quality points for each course the student has taken divided by the total number of *attempted credits*. **Hint: Think carefully about the choice of type for quality points**

``void submitGrade(double grade, int credits)`` - this method takes in a course grade (as a value between 0 and 4) and the number of credits for a course, and updates the student's credits and GPA points accordingly. For the purposes of this assignment a grade greater than or equal to 1.7 is considered passing and you can think about it as the final, overall grade for the course.

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

``double cashOutBearBucks()`` - Zero out the Bear Bucks balance and return the appropriate amount as follows:

* Remaining balance will be refunded, minus a $10 administrative fee.

* Balances of $10 or less will be forfeited.

For example:

if your balance was $42 and your “cashed out” you would receive $32 (via the return value) and your balance would be $0.

if your balance was $9 and your “cashed out” you would receive $0 (via the return value) and your balance would be $0.

::

   **To reiterate:**  the student's Bear Bucks balance should be zeroed out as a result of calling this method.


``Student createLegacy(String firstName, Student otherParent, boolean isHyphenated, int id)`` - it is not unusual for two students to meet at college and eventually start a family, and send their children to the same school. Imagine that in an effort to incentivize alums to send their children to their alma mater, WashU will transfer unused Bear Bucks to a legacy. The administrative fees, of course, still apply (and sadly to both parents).

This method should take parameters for a first name, the other parent, whether the last name should be hyphenated, and a student id number to create and return a new ``Student`` object as described below. Note: there are three participants in this method:

* ``this`` parent

* the other parent

* the child ``Student`` that is created and returned by the method.

The newly-created legacy’s state will be determined by:

* The legacy’s first name and id (as you might have imagined) will determined by the ``firstName`` and ``id`` parameters.

* The legacy’s last name with either be the last name of ``this`` or a hyphenated combination of this-other depending on the value of ``isHyphenated``.

* The legacy should have the amount of money that results from cashing out its parents.

``String toString()`` - returns the students full name and student ID

3. Before moving on, make sure that all of the tests for ``Student`` pass! There are other tests referenced by ``CourseTestSuite`` (for the ``Course`` class that you develop below) that won’t pass yet.

4. Now go back and think again about the instance variables of this class and their getters and setters. Beyond just the getters we dictated for testing purposes, which of the instance variables should have getters, and which should have setters?

To reason about this, you need to think about what the unit test is doing, and you must provide getters or setters so that it can work. But beyond that, think about how this class will be used.

* Should the student ID have a setter? That is, do we want to provision for the student ID of a ``Student`` object to change? What does the initial story of a ``Student`` object say about that?

* How about the name? Washington University allows students to change their names.

* Should the number of credits be settable directly outside the class? Or should access be more carefully controlled?

The TAs will discuss this with you when you demo.

Creating a Course class
=====================

The ``Course`` class should contain the following properties:

* Name

* Credits a student earns by taking this course

* Roster of enrolled Students

1. Add these properties to your class, and create a constructor. Write getters for the name, credits, number of "seats remaining" (unfilled seats) and capacity (total number of seats). You do not need one instance variable for every getter, but you may set your class up that way if you'd like.

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

Comprehensive Unit Test
=====================

When you’re completely done run all the tests in ``StudentAndCourseTestSuite.java``, which runs both the ``Student`` and ``Course`` tests. If you’ve successfully implemented all the required methods to behave as expected, all the tests should pass.

Submitting your work
=====================

To submit your work come to office hours or class on an “Assignment day” and sign up for a demo via `wustl-cse.help <https://wustl-cse.help/>`_. Be prepared to show them the work that you have done and answer their questions about it!






















