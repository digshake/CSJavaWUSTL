==============================
Assignment 1: Grade Calculator
==============================

Assignment Setup
================

To create your repository, `go here <https://classroom.github.com/a/k0RoehD7>`_ and follow the same accept/import process described in `the setup instructions <../Module0-Introduction/software.html>`_.

Grade Calculator
================

In this assignment, you will develop a tool that can help you compute your final course grade. By completing this assignment, you will demonstrate that you can:

* Create a Java class on your own

* Arrange for the class to take inputs of interest

* Compute output values of interest

* Produce meaningful output based on your computations

* Work with Java expressions

Procedure
================

When you open the ``src`` folder, you'll see the ``assignment01`` package, but it will be empty. Your first task is to create the class! Here is how:

1. Right click on ``assignment01``, then click New, and then Class.
2. Type ``GradeCalculator`` in the ``Name:`` field. Please use the given capitalization and spelling.
3. Click the box that says ``public static void main(String[] args)``
4. Click the ``Finish`` button. After you click the button, you should see the created file pop up in your Package Explorer.

For this calculator to work, we need to get information from the user. To start getting user input, we need to create a Scanner object and put it in a variable we can use like so:

1. Inside of ``GradeCalculator``'s ``main`` method curly braces, write ``Scanner in = new Scanner(System.in);``. (You can get rid of the "TODO" comment.)
2. If you didn't use autocomplete, you will notice an error. Try to remember how you fixed this error in Studio 1. In case you don't remember, these are the instructions:
	1. Hover over (put your cursor on) the red underline
	2. Click on the first suggestion that pops up (specifically, the one that says to import java.util's Scanner)

You now have the variable ``in``, which you can use to get Strings from the user (``in.next()``), ints from the user (``in.nextInt()``), and doubles from the user (``in.nextDouble()``).

Warning, the next section is going to be throwing a lot of information at you. Instead of trying to tackle it all at once, you are encouraged to develop iteratively, which means to make small changes and check often if it's working how you anticipate. We'll guide you through iterative development for this assignment.

First, the information (no need to take action yet).

These are the inputs that you should ask for from the user, plus the names of the variables you should store that information in:

	+------------------------+--------------------------------------------------------------------------------------------------------------------------+
	| Variable               | Value                                                                                                                    |
	+========================+==========================================================================================================================+
	| name                   | The name of the student taking this course, as a String                                                                  |
	+------------------------+--------------------------------------------------------------------------------------------------------------------------+
	| averageAssignmentGrade | The average grade on all assignments, as a percentage between 0 and 100                                                  |
	+------------------------+--------------------------------------------------------------------------------------------------------------------------+
	| extensionPoints        | The number of points earned during extension batches 1 and 2 as a value between 0 and 30                                 |
	+------------------------+--------------------------------------------------------------------------------------------------------------------------+
	| studiosAttended        | The total number of studio sessions attended, as a value between 0 and 8                                                 |
	+------------------------+--------------------------------------------------------------------------------------------------------------------------+
	| averageQuizGrade       | The average grade on all quizzes after the two lowest quiz grades have been dropped, as a percentage between 0 and 100   |
	+------------------------+--------------------------------------------------------------------------------------------------------------------------+
	| studioPrepsCompleted   | The total number of pre-studio preps completed, as a value between 0 and 10                                              |
	+------------------------+--------------------------------------------------------------------------------------------------------------------------+
	| averageExamGrade       | The average grade on all exams, as a percentage between 0 and 100                                                        |
	+------------------------+--------------------------------------------------------------------------------------------------------------------------+

This is an example of what your program should output:

``CSE131 Grade for: Doug Shook``

``Average assignment grade: 85.4%``

``Weighted assignment grade (out of 30): 25.62%``

``Number of extension points: 27``

``Weighted extension grade (out of 10): 9.00%``

``Number of studios attended: 7``

``Weighted studio grade (out of 10): 8.75%``

``Average quiz grade: 97.3%``

``Weighted quiz grade (out of 2): 1.95%``

``Studio preps completed: 10``

``Weighted studio prep grade (out of 2): 2.0%``

``Average exam grade: 93.5%``

``Weighted exam grade (out of 45): 42.08%``
	
``Completed course review: false``

``Total Grade: 89.40%``

How do we write this program? Let's start one step at a time. What's the simplest, easily checkable change you can make?

One option is to ask the user for a name, store the input in the ``name`` variable, and then print out the ``name`` variable. You could then try running that code, and then if it's working as you expect, you could change it to be styled like the output (with "CSE131 Grade..." etc).

Note: if you don't remember how to prompt for user input, check out the `prompt examples from Studio 1 <https://131text.com/ns/books/published/csjava/Module1-Types-and-Names/studio.html#average>`_.

You can continue like this, taking changes one step at a time and checking the output as you go.

Here are a few issues we anticipate you will come across. Read the bullet point when you think it's relevant to what you're working on.

* Data types of variables/user input: Think about what the expected values are. What data type works best?

* Making sure users don't put in invalid values: 150% is not a valid average assignment grade. In the future, we'll learn how to force programs to only accept valid inputs. For now, just assume the user will always put in valid inputs.

* Weights: Check out the `course policies page <https://wustl.instructure.com/courses/102124/pages/course-policies>`_ for the weighting on different components of the grade.

* Rounding: You must round the weighted grade percentages to two digits after the decimal point so that they get printed with the right number of decimal places. In order to round, you may use the math operations we learned (``+``, ``-``, ``*``, ``/``), casting (``(int)``, ``(double)``) and/or ``Math.round()`` and nothing else. Think about what information ``Math.random()`` "loses" and how you would need to change the input so it only loses the information you want to get rid of.

* Course review: The course review should simulate a coin flip. Review how ``Math.random()`` works and assign the value of a variable ``boolean courseReview`` by comparing a random number to ``0.5``. What kind of comparison will simulate a coin flip? You can then print the value of ``courseReview`` directly.

* Total grade: Make sure you keep as much precision as possible in all the components when you're calculating the final grade, and then you can round the final grade. Rounding early will result in an incorrect final grade value.

Prepare for demoing your work by trying out various combinations of grade values and making sure that your program computes and prints them correctly.

Submitting your work
====================

Check the rubric (which is at the very bottom of the Canvas page for this assignment).

Get your assignment graded by going to office hours or by going to class on an "Assignment day" (non-studio day) and signing up for a demo via `wustl-cse.help <https://wustl-cse.help/>`_.