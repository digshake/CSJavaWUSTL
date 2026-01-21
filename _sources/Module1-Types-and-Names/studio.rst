===========================
Studio 1: The Type is Right
===========================

**Studio activities should not be started before class! Come to the session and work on the activity with other students!**
 
Studio Sessions Overview
========================

Studios are a chance to learn the module's topics by actively solving problems with other students.

Credit is based on active, good faith participation (not correctness or completion):

* If you arrive late (more than 15 minutes) or don't actively contribute to the work, you will not be given credit.
* Be a constructive member of group:

	* Complete the prep materials.
	* Ask questions and discuss as a group/with your TA. Studio is a great time to further your big-picture understanding.
	* Be polite and respectful of your group members!
	* Make sure every member of your group understands your group's work and the topics being used.

Studio Setup and Procedure
==========================

1. Form a group of 2-3 students. This can be the same group as last week or a new group! Now is the time to switch things around as you see fit.
2. Find a TA to work with (TAs may be working with 2-3 groups at a time)
3. If you haven't already, complete the `software setup <software.html>`_.
4. Choose one group member to open VS Code. They will be in charge of typing code for the first part of the studio. You will rotate this responsibility throughout the studio, but the initial person will have to be comfortable with others typing on their computer.
5. Everyone else, open the studio instructions on your own computer.
6. Choose one group member to complete the following instructions:

	1. Click `here <https://classroom.github.com/a/R96eVuOP>`_
	2. Go to the bottom of the page, where it says `OR Create a new team`.
	3. Enter your group's last names and "Studio1" into the text field. Ex: "XiaSmith-Studio1"
	4. Click the button to create the team.
7. After the team is created, all other members of your team should complete the following instructions:

	1. Click `here <https://classroom.github.com/a/R96eVuOP>`_
	2. Find the team your groupmate created.
	3. Join the team. 
	
	* If you join the wrong team, you will need to contact one of the instructors or Head TAs to fix it.
8. VS Code person: import the studio repository as described in `the software setup <setup.html>`_

Studio 1: Activity
=====================

You will complete a series of simple Java programs and run each program to ensure it performs its task correctly.

In VS Code, open ``src/studio1``. Unless stated otherwise, most code in this class will be in a ``src`` folder.

Some of the following exercises are adapted from Princeton University's `COS126 course <http://www.cs.princeton.edu/courses/archive/spring12/cos126/precepts.php>`_, based a textbook by Sedgewick and Wayne.

For each of the following exercises, find the file in your studio repository and complete it to do the assigned task.

HiOne
=====================

Say hello to the name supplied as input to this program.

   Sample output: ``Hi Bill. How are you?`` (assuming ``Bill`` was supplied as input) Feel free to end the output with punctuation that indicates the level of enthusiasm associated with your greeting.

HiFour
=====================

Expand your hospitality to the four names supplied to this program.

   Sample output: ``Greetings Cormen, Leiserson, Rivest, and Stein``. Be sure to put in `proper punctuation <http://en.wikipedia.org/wiki/Serial_comma>`_ to separate the names.

Conceptual Checkpoint 1:

This is one of many conceptual checkpoints. Consider this a time to mentally check in on your big-picture understanding of the concepts. We'll give you a question and ask you to discuss it with your TA. The expectation is that you discuss the question for ~2 minutes and your TA will chime in with clarifications, but if you're curious about anything, this is a great time to ask about what you're wondering.

Chat with your group and TA about the following question: What do "class" and "main method" refer to? How are we using them?

Ordered
=====================

Choose a new group member to type.

Define a ``boolean`` variable ``isOrdered`` whose value is ``true`` if the three values are either in strictly ascending order ``(x < y < z)`` or in strictly descending order ``(x > y > z)``, and ``false`` otherwise. Print out the variable ``isOrdered`` using ``System.out.println(isOrdered)``.

   Some of you may already know some Java. We have not yet covered the if statement. You must use what has been taught so far (simple expressions and assignment) to accomplish this task.

You'll need a new tool to accomplish this! These will be useful operators:

``&&`` (pronounced "and") compares two booleans and returns whether they are BOTH true. (``true && true`` makes ``true`` but ``true && false`` makes ``false``)

``||`` (pronounce "or") compares two booleans and returns whether EITHER boolean is true. (``true || true`` and ``false || true`` both make ``true``, but ``false || false`` makes ``false``)

Average
=====================

Choose a new group member to type.

We aren’t giving you the class for this one, but we will instruct you how to create your own from scratch:

1. Right- (control-) click on the ``studio1`` package, select ``New Java File > Class``

2. Use the name ``Average`` for the new class.

3. In the new file that was created, insert the code for main (feel free to copy from another file if you want): ``public static void main(String[] args) {``

5. At the top of the ``main`` method, you need to insert the ``Scanner`` code to accept two integers: ``n1`` and ``n2`` .

      Refer to other studio code to see how this is done. You will also need to copy the import statement found at the top of the file to use the Scanner. Pay special attention to the ``{ }`` curly braces and how they are used in other code you have worked with so far to make sure everything is in the proper place. If you get stuck, ask a TA for help!

      **A not so nice prompt:**

      ``System.out.println("Yo, sup?");``
	  ``int n1 = in.nextInt();``

      **And a nice  prompt:**

      ``System.out.println("The first of two integers to be averaged?");``

      Run your program and makes sure it prompts you correctly for its values and ask a TA to check your work at this point.
	  ``int n1 = in.nextInt();``

6. Finish the class so it prints out the average of its two integer inputs.

      Sample output:

      ``Average of 5 and 6 is 5.5.``

      Note that the output is a ``double``, because the average of two integers is not necessarily an integer.

Conceptual Checkpoint 2:

Chat with your group and TA: Why have separate data types for int and double when they are both numbers?

Leap Year
=====================

Choose a new group member to type.

You’ll need to make a ``LeapYear class``, just as you made the ``Average`` class in the previous step. You should again insert the ``Scanner`` code, this time to take in an integer that represents a year.

Your task is to determine whether the given year is a leap year or not. A value is a leap year if it meets the following criteria:

* It is evenly divisible by four

* It is not evenly divisible by 100

* An exception to this rule is if the year is evenly divisble by 400. These years are leap years.

So for example, 2020 is a leap year because it is evenly divisible by 4. The year 1900 is evenly divisible by 4, but since it is also evenly divisible by 100 it is not a leap year. The year 2000 is evenly divisible by 4 and 100 but it is also divisible by 400 so it is a leap year.

Once you have determined whether the given year is a leap year print out a message with the result:

   Sample output: ``2020 is a leap year: true``

   ``2000 is a leap year: true``


   Some of you may already know some Java. We have not yet covered the ``if`` statement. You must use what has been taught so far (simple expressions and assignment) to accomplish this task.

Conceptual Checkpoint 3:

Which operations result in which data type? (Example: you just created a boolean by comparing ints. What else can you do with the operations you've learned so far?)

Creative Exercise - Ice Cream
=============================

As a group, brainstorm the best data type to represent the following situations:

   Often, there is no *right* or *wrong* answer. Be prepared to defend your choices.

* The number of times you have been to Ted Drewes

* Whether you like Ted Drewes’ vanilla frozen custard or not

* The number of people you can take in your car

* The price of a regular size concrete vanilla frozen custard

* The name of your favorite flavor from Ted Drewes

* The address of the Ted Drewes

* The probability that you will see a friend at Ted Drewes

Demo (get credit for) your work:
=====================================

**Commit and Push your work.** Be sure that any file you worked on is updated on `GitHub <https://github.com/>`_. This way the other members of your team will be able to access the code that you worked on.

To get participation credit for your work talk to the TA you’ve been working with and complete the demo/review process. Be prepared to show them the work that you have done and answer their questions about it!
