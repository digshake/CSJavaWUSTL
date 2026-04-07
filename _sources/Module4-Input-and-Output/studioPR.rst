=====================
Studio PR: Peer Review
=====================

**Studio activities should not be started before class! Come to the session and work on the activity with other students!**

Studio Setup and Procedure
==========================

You know the drill by now! Here's `the Github link <https://classroom.github.com/a/9wvgobxL>`_.

Peer Review
===========

For this studio we will go through an exercise called Peer Review. Like many disciplines, computing often requires many people to work together to solve large, complex problems. Humans are prone to mistakes and biases, however, so by performing regular peer reviews we gain the perspective of others on our code which may catch problems that were otherwise missed. The act of peer review is very common in industry and professional programmers are regularly expected to have their code reviewed by their peers as well as to review their peers' code submissions.

For this peer review we want you to focus specifically on the style of the code. While there is some flexibility in how you can write your code, keeping your code files clean and consistent will make it easier for others to understand what your code is doing.

In particular, we want you to focus on the clean coding guidelines that were presented in class on Monday. Be sure to run the code after every change you make to ensure that the code is still working properly!

1. Start with the file called ``Entity.java``. This is a base class that will be inherited from by ``Projectile``, ``Enemy``, and ``Player``. Review the contents of the class, then focus in on the following areas:
    
    * Are the class components (methods, instance variables, etc.) in the proper order?
    * How can the if statement in the ``collidesWith`` method be simplified?

2. Next focus on the ``Projectile.java`` file:

    * Remove any magic numbers from the code
    * How can the if statement in ``isOutOfBounds`` be simplified?

3. Your next stop is the ``Player.java`` file:

    * Remove any magic numbers from the code
    * How can the if statement in ``isFiring`` be simplified?

4. The next file to examine is ``Enemy.java``:

    * Remove any magic numbers from the code
    * How can the if statements in ``bounceOffWall`` be simplified?
    * How can the if statement in ``isFiring`` be simplified?

5. Finally, turn your attention to the ``Game.java`` file. This file deserves the most attention:

    * Remove any magic numbers from the code
    * This file contains many traditional for loops, however many of them should be for each loops. Visit each loop in this file and determine whether or not it should be a for each loop.
    * The ``updatePositions`` method is quite long. Decide how this method could be broken up into smaller methods, then rewrite it.
    * The ``checkCollisions`` method is quite long. Decide how this method could be broken up into smaller methods, then rewrite it.

6. **Show your work to a TA**. It must pass TA approval (clean and functional!) before the studio is considered complete!

**To complete this studio:** Be sure to fill out the reflection questions on Canvas!