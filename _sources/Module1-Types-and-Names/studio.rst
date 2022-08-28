=====================
Studio 1: The Type is Right
=====================

**Studio activities should not be started before class! Come to the session and work on the activity with other students!**
 
Studio Sessions Overview
=====================

Studios are a chance to work with other students to learn course material by actively trying to solve problems.

1.Form a group of 2-3 students and find a TA or instructor to work with (TAs/instructors may be working with 2-3 groups at a time)

2.Credit is based on good faith participation:

* The goal is to explore the module’s course topics by working on the given activity. Credit is not based on any specific solution nor do you even need to complete the activity.

* Credit is given based on your active participation in the activity. If you arrive late (more than 15 minutes) or don’t actively contribute to the work, you will not be given credit.

* Be a constructive member of group:

  + Prepare in advance by completing the prep materials.

  + Ask questions and discuss topics. Try to make sure your entire group completely understands the topics being used.

  + Be polite and respectful of your group members!

  + Each member of your team is responsible for ensuring that all members completely understand your work and the topics being used.


Academic Integrity Agreement
=====================


Today, course staff will guide you in completing an Academic Integrity Agreement.

Your group should review and discuss the `Examples <https://wustl.instructure.com/courses/90796/pages/course-policies#Examples>`_ of what you can and can’t do. When everyone is clear about what is allowed, the TA/instructor will tell you to proceed.

Studio Setup and Procedure
=====================

* All but one member of your group should have this web page open so you can follow along and see the instructions as you work.

* Plan to have one computer at which your team does its work (usually using Eclipse). Initially, one of you will be in charge of typing at that computer.

* Throughout the studio you should trade who is in charge of the keyboard.

**READ THE FOLLOWING FULLY BEFORE PROCEEDING**


1. Have **one person** in your group create a new team by clicking `here <https://classroom.github.com/a/fQdFUNfj>`_ and going to the ``OR Create a new team`` box at the bottom of the page.

   1. The team name should include the last names of all your group members. For example, if Xia and Smith are working together, the team name should be something like “XiaSmith”.



2. After the team is created, all *other* members of your team should click on the same link and follow the instructions to join the team.

   1. **Be careful to join the right team!** You won’t be able to change teams yourself and will have to contact instructors if there’s a problem.

   2. **Be sure everyone else joins the team!** If grades don’t get entered correctly we will use the team to help verify credit for a particular studio.


3. Finally, one person should import the studio repository into Eclipse, as described in `the setup instructions <../Module0-Introduction/software.html>`_.

   1.All team members will have access to the work pushed to GitHub. Be sure to ``Commit and Push`` at the end of the day so everyone can refer back to the work later as needed.


Studio 1: Activity
=====================

* You will complete a series of simple Java programs, and run each program to ensure it performs its task correctly.

* The files for this program are in the ``src/studio1`` package of the repository you loaded.

* To run a program just open the file in a tab and click on the green “Play” button on the menu. The program in the active/open tab will run.

**Some of the following exercises are adapted from Princeton University's** `COS126 course <http://www.cs.princeton.edu/courses/archive/spring12/cos126/precepts.php>`_, based a textbook by Sedgewick and Wayne.

For each of the following exercises, find the file in your studio repository and complete it to do the assigned task.

HiOne
=====================

Say hello to the name supplied as input to this program.

   Sample output: ``Hi Bill. How are you?`` (assuming ``Bill`` was supplied as input) Feel free to end the output with punctuation that indicates the level of enthusiasm associated with your greeting.

HiFour
=====================

**Switch who is “entering code”; Everyone should have equal time entering code**

Expand your hospitality to the four names supplied to this program.

   Sample output: ``Greetings Cormen, Leiserson, Rivest, and Stein``. Be sure to put in `proper punctuation <http://en.wikipedia.org/wiki/Serial_comma>`_ to separate the names.

Ordered
=====================

**Switch who is “entering code”; Everyone should have equal time entering code**

Define a ``boolean`` variable ``isOrdered`` whose value is ``true`` if the three values are either in strictly ascending order ``(x < y < z)`` or in strictly descending order ``(x > y > z)``, and ``false`` otherwise. Print out the variable ``isOrdered`` using ``System.out.println(isOrdered)``.

   Some of you may already know some Java. We have not yet covered the if statement. You must use what has been taught so far (simple expressions and assignment) to accomplish this task.

Average
=====================

**Switch who is “entering code”; Everyone should have equal time entering code**

We aren’t giving you the class for this one, but we will instruct you how to create your own from scratch:

1. Right- (control-) click on the ``studio1`` package, select ``New > Class``

2. Type the name ``Average`` in the ``Name:`` field

3. Click the box that says ``public static void main(String[] args)``

4. Click the ``Finish button``, which will create the new file

5. At the top of the ``main`` method, you need to insert the ``Scanner`` code to accept two integers: ``n1`` and ``n2`` .

      Refer to other studio code to see how this is done. Depending on how you add the code referring to the ``Scanner``, Eclipse may flag your code with an error. If so, you can get Eclipse to solve its own problem by mousing over the error (red underline), and using the first suggestion that pops up, namely to import ``Scanner``. Try to use meaningful messages to prompt for values.

      **A not so nice prompt:**

      ``int n1 = in.nextInt("Yo, sup?");``

      **And a nice  prompt:**

      ``int n1 = in.nextInt("The first of two integers to be averaged?");``

      Run your program and makes sure it prompts you correctly for its values and ask a TA to check your work at this point.

6. Finish the class so it prints out the average of its two integer inputs.

      Sample output:

      ``Average of 5 and 6 is 5.5.``

      Note that the output is a ``double``, because the average of two integers is not necessarily an integer.


Leap Year
=====================

You’ll need to make a ``LeapYear class``, just as you made the ``Average`` class in the previous step. You should again insert the ``Scanner`` code, this time to take in an integer that represents a year.

Your task is to determine whether the given year is a leap year or not. A value is a leap year if it meets the following criteria:

* It is evenly divisible by four

* It is not evenly divisble by 100

* An exception to this rule is if the year is evenly divisble by 400. These years are leap years.

So for example, 2020 is a leap year because it is evenly divisible by 4. The year 1900 is evenly divisible by 4, but since it is also evenly divisible by 100 it is not a leap year. The year 2000 is evenly divisible by 4 and 100 but it is also divisible by 400 so it is a leap year.

Once you have determined whether the given year is a leap year print out a message with the result:

   Sample output: ``2020 is a leap year: true``

   ``2000 is a leap year: true``


   Some of you may already know some Java. We have not yet covered the ``if`` statement. You must use what has been taught so far (simple expressions and assignment) to accomplish this task.


Creative Exercise - Ice Cream
=====================

As a group, brainstorm the best data type to represent the following situations:

   Often, there is no *right* or *wrong* answer. Be prepared to defend your choices.

* The number of times you have been to Ted Drewes

* Whether you like Ted Drewes’ vanilla frozen custard or not

* The number of people you can take in your car

* The price of a regular size concrete vanilla frozen custard

* The name of your favorite flavor from Ted Drewes

* The address of the Ted Drewes

* The probability that you will see a friend at Ted Drewes

Demo (get credit for your) your work:
=====================

**Commit and Push your work.** Be sure that any file you worked on is updated on `GitHub <https://github.com/>`_.

To get participation credit for your work talk to the TA you’ve been working with and complete the demo/review process. Be prepared to show them the work that you have done and answer their questions about it!
