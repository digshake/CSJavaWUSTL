=====================
Module 8 Studio
=====================

Studio 8: Making a Quiz
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

1. Have **one person** in your group create a new team by `clicking here <https://classroom.github.com/a/C4S6I-Ty>`_ and going to the ``OR Create a new team`` box at the bottom of the page. The team name should include the last names of all your group members. For example, if Xia and Smith are working together, the team name should be something like “XiaSmith”.

2. **After the team is created**, all other members of your team should click on the same link and follow the instructions to join the team.

   1. **Be careful to join the right team!** You won’t be able to change teams yourself and will have to contact instructors if there’s a problem.

   2. **Be sure everyone else joins the team!** If grades don’t get entered correctly we will use the team to help verify credit for a particular studio.

3. Finally, one person should import the studio repository into Eclipse, as described in Assignment 0’s Add the assignment to Eclipse.

   * All team members will have access to the work pushed to GitHub. Be sure to ``Commit and Push`` at the end of the day so everyone can refer back to the work later as needed.



A Question Class
============================

Before we can construct a Quiz, we'll start by creating a few different types of questions. The first type of question will be similar to a fill in the blank style question, where a prompt is given and the user has to supply the correct answer.

Examine the ``Question`` class. This will be our **base class** so no inheritance will be used here, but these methods will be inherited and used by the **subclasses** later on in the studio.

Complete the constructor and getter methods for the Question class.

Take some time to familiarize yourself with this class. Make sure you understand what the fields are and how the constructor works. Make sure you understand what the ``displayPrompt()`` and ``checkAnswer()`` methods are doing.

Finally, create your own Question object in the main method in the ``Question`` class.

Run the test suite ``Studio8TestSuite.java`` to check your work before moving on.

Multiple Choice Questions
=========================

We now wish to construct a class for multiple choice questions. Notice that some of the fields and behaviors for a multiple choice question will be the same as our ``Question`` class. We would say that a ``MultipleChoiceQuestion`` **is a** ``Question``. This makes it a great candidate for inheritance.

By extending the ``Question`` class, our ``MultipleChoiceQuestion`` class gains access to the fields and methods from ``Question``. The biggest difference is a list of choices, which must be stored in a field and also displayed along with the question prompt.

Start by examining the ``MultipleChoiceQuestion`` constructor. Use the constructor from the base class to take care of the fields that the two classes have in common by calling ``super()``. Then, deal with any additional fields, creating them if necessary.

Next, you should **override** the ``displayPrompt()`` method, which has been started for you. You can use the ``displayPrompt()`` method from the base class to display the question prompt, then finish the method by displaying the choices in order. Your first choice should be labelled "1", second choice "2", etc. The output for this method should look like the following:

If the options are 131, 231, 425, and 1301, the ``displayPrompt()`` method should print:

1. 131

2. 231

3. 425

4. 1301

More abstractly, this method should print:

1. choices[0]

2. choices[1]

...

\ n. choices[n]

Finally, complete the getter method for the instance variable you have created.

Once you have finished, run the test suite (``Studio8TestSuite.java``) again to check your work. Make some MultipleChoiceQuestions in the main method and test your code to make sure it behaves in the way you expect.

Select All Questions
====================

Another type of question we would like to include presents multiple choices but then asks the user to select all of the correct answers. For this question type, it is possible for more than one of the choices to be correct. Notice again that there is some overlap between what a ``SelectAllQuestion`` and ``MultipleChoiceQuestion`` can do. We would say that a ``SelectAllQuestion`` **is a** ``MultipleChoiceQuestion`` (and also **is a** ``Question``).

First complete the constructor, making sure to call ``super()``.

Next, focus on the ``checkAnswer()`` method. Unlike the other question types, these kinds of questions allow for partial credit. Each choice is worth one point, with one point being deducted for each incorrect answer that is given and for each correct answer that isn't given. Use the provided methods ``findMissingCorrectAnswers()`` and ``findIncorrectGivenAnswers()`` to complete the ``checkAnswer()`` method. Note that you will not have to use the provided ``findMissingCharacters()`` method, though it is already being used in the other methods you have been given.

These methods from the ``String`` `API <https://docs.oracle.com/javase/8/docs/api/java/lang/String.html>`_ will likely be useful:

* `charAt <https://docs.oracle.com/javase/8/docs/api/java/lang/String.html#charAt-int->`_

* `contains <https://docs.oracle.com/javase/8/docs/api/java/lang/String.html#contains-java.lang.CharSequence->`_

* `indexOf <https://docs.oracle.com/javase/8/docs/api/java/lang/String.html#indexOf-int->`_

Be sure to run the test suite to check your work, then create some SelectAllQuestions in the main method to ensure it works how you'd expect.

Quiz
====

It is now time to put it all together. Examine the code that has been provided to you in the ``Quiz`` class. There is only one field, an array of ``Question`` objects. Because ``MultipleChoiceQuestion`` and ``SelectAllQuestion`` **are** ``Question`` s, they can be used anywhere that a ``Question`` is specified as the type. This is the concept known as **polymorphism**.

One method have been completed for you already: ``getUserAnswer()``. You will need this method in a moment, so familiarize yourself with it now.

Complete ``getTotalPoints()``.

Your task is to complete ``takeQuiz()``. This method should:

* Iterate through all of the questions:

  * Display the prompt for each question
  
  * Request a user answer for each question (using ``getUserAnswer()``)
  
  * Check the answer that the user gave
  
  * Display the points earned for each question
  
* Once all questions have been answered, it should display the points earned as well as the total number of points available (from ``getTotalPoints()``) in the format: You have earned ___ points.

Run the test suites to check your work and create a Quiz of your own in the main method!

Submitting
==========

**Commit and Push** your work. Be sure that any file you worked on is updated on `GitHub <https://github.com/>`_.


To get participation credit for your work talk to the TA you’ve been working with and complete the demo/review process. Be prepared to show them the work that you have done and answer their questions about it!

*Before leaving check that everyone in your group has a grade recorded in Canvas!*
