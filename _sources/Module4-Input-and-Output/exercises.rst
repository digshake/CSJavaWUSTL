=====================
Module 4 Exercises
=====================



Exercise : 4.3.0 Statistics for a list of numbers 
:::::::::::::::::::::::::::::::::::::::::::::::::::

* Find and open the ``Stats`` Java program in the ``exercises4`` package of the ``exercises`` source folder.

* Write code as directed to compute the specified statistics for the numbers that you read in.

  * Compute the sum

  * Compute the average

  * Compute the count (i.e., how many numbers are in the file)

  * Find the maximum value 

  * Find the minimum value


Exercise : 4.50. Permuting an array
:::::::::::::::::::::::::::::::::::::::::::::::::::

* Find and open the ``WaitPoint`` Java program in the ``exercises4`` package of the ``exercises`` source folder.


* Write code that does the following:

  * Waits until the mouse has been pressed

  * Waits until the mouse has been released

  * Draws a visible point at the spot where the mouse was released

  * Waits until the user has typed a ``q`` (all other keys are ignored)

  * Writes text on the graphic screen that says goodbye

   Do this a step at a time, testing your code. Look at the solution video intermittently as necessary.

Exercise : 4.60. Example of animation
:::::::::::::::::::::::::::::::::::::::::::::::::::

* Find and open the ``MouseFollower`` Java program in the ``exercises4`` package of the ``exercises`` source folder.

* That code already contains the standard animation loop:

  * ``StdDraw.clear()`` at the beginning, to wipe the graphics display clean

  * Your code will then paint one frame of the animation

  * ``StdDraw.show(10)`` produces what you have drawn on the screen and waits 10 milliseconds before continuing. VS Code may draw a line through the show(10) command and underline it in yellow. You can ignore this (it’s a warning that ``show(...)`` may not be available in future updates of the ``StdDraw`` functions. It’s being replaced with another approach).

By using ``show(..)``, the drawing you do is not actually ``shown`` between calls to show. Instead, the drawing is done in memory, off the screen, which is much faster.

When you call ``show()``, the work you have done off screen is put on screen all at once.

The program also pauses for the specified time, usually 10 to 50 milliseconds. Pausing allows your computer to do something else for a while, which will make your computer feel more responsive in the other applications that are running.

* First try to get a ball on the screen to follow your mouse. This consists of reading the mouse's coordinates, and painting a ball at that spot.

* When you have that working, try to think of how you could make the ball appear to lag in its mouse-following activities.

   As a hint, think about keeping some history of where the mouse has been. You can then have the ball go to locations in the mouse's past.

