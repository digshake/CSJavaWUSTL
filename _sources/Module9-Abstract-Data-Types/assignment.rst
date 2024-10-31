=====================
Assignment 9: Snake
=====================

Assignment Setup
=====================

To create your repository go `here <https://classroom.github.com/a/FGlvnIYR>`_. Then follow the same accept/import process described in `the setup instructions <../Module0-Introduction/software.html>`_.

Overview
=====================

For this assignment, we will be asking you to create the classic game `Snake <https://g.co/kgs/aKNjEh>`_. This assignment is a bit more open ended than past assignments - no unit tests are given. This is to allow you a degree of creativity and flexibility. We expect some basic functionality from your game but you are otherwise encouraged you explore, expand, and improve upon the game to make it your own!

Questions to ask if you get stuck
=================================

Like all problems, this one can be tricky. Here are some common questions that we get from students regarding this assignment. Use these questions to gauge your own understanding of what we are asking you to do. Please ask these questions to a TA or an instructor if you are feeling stuck on a certain part of the assignment.

* What is a ``List``? How does it differ from an array?

* What are some common useful methods provided by ``List``s?

* How are ``List``s created? What does it mean for ``Lists`` to be parameterized?

* How do we determine the equality of two objects? What kinds of equality are there?

Requirements
=====================

To receive full credit you must:

* Have a Snake that is controlled by the keyboard and moves in a snake-like fashion across the screen. The expectation is that the movement will work like the game linked above. Moving the entire body of the snake in the same direction will not receive full credit.

* Randomly place food around the game screen

* Grow the snake whenever it eats a piece of food

* End the game once the snake collides with the edge of the screen

Code base
=====================

You will probably want to start with ``BodySegment`` and ``Food`` classes, as they are fairly simple. For ``Food`` you simply need to set the position of the food to a random spot within the boundary of the window. In ``BodySegment`` be sure to set the ``color`` instance variable, a ``ColorUtils`` class has been provided that you can use if you wish. Drawing each object as a circle makes collision detection a bit more straightforward, however you are welcome to draw each component in whatever way you wish.

``Game`` and ``Snake`` will be where most of the work of this assignment is done. Start by noticing that the code to handle keyboard input has been provided for you. If you run the provided ``Game`` class, you can test the keyboard using the WASD keys and the console. We need to get the information from the keyboard to the ``Snake`` which can be done with the provided ``changeDirection()`` method in the ``Snake`` class.

Start with the constructor to ``Snake``. We are using a ``LinkedList<BodySegment>`` to represent our ``Snake``, so this must be initialized in the ``Snake`` constructor. We also want our new ``Snake`` to have at least one ``BodySegment``, so within the constructor you should create a new ``BodySegment`` and add it to the list. Next, complete the ``draw()`` method in the ``Snake`` class by iterating through the list and telling each ``BodySegment`` to draw itself. Finally, start the ``move()`` method by retrieving the ``BodySegment`` representing the head of the snake from the ``LinkedList`` and updating its position by adding to the ``deltaX`` and ``deltaY`` values to its respective X and Y coordinates.

Moving to the ``Game`` class, within the constructor you should construct a new instance of ``Snake`` and ``Food`` and store them each in instance variables. Complete the ``updateDrawing()`` method such that it will clear the screen and redraw each of the game components. You can then update the loop within the ``play()`` method to incorporate your ``Snake``: pass the direction to the ``Snake`` and tell it to ``move()``, then ``updateDrawing()``. If all goes well, you should have a (small) moving ``Snake``!

The ``Food`` should cause your ``Snake`` to grow, but first you must complete the ``eat()`` method of the `Snake` class to determine if the **head** of the ``Snake`` overlaps the ``Food`` (refer to our previous Zombie assignments for a discussion of this concept). If the ``Snake`` successfully eats the ``Food`` then a new ``BodySegment`` should be added to the ``Snake``. This will require you to go back and revisit the ``move()`` method to update the position of **all** of the ``BodySegment`` s in the list, not just the head. Hint: you may want to consider starting to move the snake from the **back**. Don't forget to add your ``Food`` into the while loop in ``play()`` to make sure it works!

The final part of the game is to check whether the **head** of the ``Snake`` collides with the edge of the screen, which can be done with the ``isInbounds()`` method. Once this method is complete, update the while loop in ``play()`` to end the game appropriately.

Be Creative!
====================

There are many ways upon which this game could be completed, and many ways upon which this simple version can be expanded upon. To recieve full credit on this assignment, you must choose **one additional feature** to add to your game. It does not have to be a complicated feature but it must be something **functional**, so simply changing the colors and cosmetics (while encouraged!) will not count towards this goal. Some simple ideas would include:

* Intro / game over screens that display properly

* Some kind of score that gets updated

* Additional things the ``Snake`` can eat, perhaps to provide extra powers

* Extra collision checks so the snake can't collide with itself. Addition of walls to make the game more challenging.

This list is not intended to be exhaustive, we want you to be creative and pick something that interests you. Be sure to talk to an instructor or a TA if you have questions about this part!

Submitting your work
=====================

Get your assignment graded by bringing it to lab on Wednesday/Thursday or going to office hours and signing up for a demo via `wustl-cse.help <https://wustl-cse.help/>`_.

Confirm that your score is recorded in `Canvas <https://wustl.instructure.com/courses/133664>`_.  Mistakes can happen and you should always confirm credit is recorded before leaving class!