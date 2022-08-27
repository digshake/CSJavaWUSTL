=====================
Assignment 0: Robot
=====================

Objective
================

The assignment is intended to make sure that you've completed the setup materials necessary for the course, and get you some practice with demoing your work.

Assignment Setup
================

Before starting this assignment it is expected that you have completed the `software setup <software.html>`_ for the course as well as `Studio 0 <studio.html>`_)

To create your repository go `go here <https://classroom.github.com/a/tMzZOKT8>`_.  Then follow the same accept/import process described in `the setup instructions <software.html>`_.

Using Java to Control a Robot
================

Your project should now be open in Eclipse. You should have a pane called the `Package Explorer` on the screen (if not, go to the `Window` menu, select `Show View` and pick `Package Explorer`).  

1. Expand the `assignment-00` folder.
2. Expand the `src` folder.
3. Expand the `assignment0` folder and double click on the `RobotInstructions.java` file.  It should look something like this:<br /> .. image:: resources/lab0/Lab0_1_Files.png

4. Run the **other** file, the `RobotController.java`, by **right-clicking on it**, selecting `Run As`, and then selecting `Java Application`, like:<br /> .. image:: resources/lab0/Lab0_2_Run.png
5. A new window should now open. Click on the `Go` button and you'll see a simulated robot draw on the screen.  It's merely following the instructions that are being given in the `RobotInstructions.java` that you opened.
6. Close the robot simulation window (*not* Eclipse).
7. Review the contents of `RobotInstructions.java`, which should be shown in Eclipse. Make some changes:
   1. Change the `robot.forward(60);` to `robot.forward(120);`.  What do you think the robot will do differently?  
   2. Run the robot simulator again.  Now that you've configured Eclipse to run it, you can just select the `Play` button on the menu:<br /> .. image:: resources/lab0/Lab0_3_ReRun.png
   3. Did the robot do what you expected?  
   4. What if you removed the line that now says `robot.forward(120);` and replaced it with two lines that each say `robot.forward(60);`?  Before making any change be sure to close the simulator. Then make your changes and hit the `Play` button to see their impact.
   5. Try removing a semi-colon (`;`).  Eclipse should add red indicators in several places indicating there are errors with the file.  These are helpful cues that you should pay attention to in larger programs.  The circles in this picture show all the special indicators, which help programmers find the exact locations of this type of problem:<br /> .. image:: resources/lab0/Lab0_4_Error.png
   6. Try running the program with errors.  Eclipse should show a window warning you.  Do **not** hit the `Proceed` button.  
   7. Put the semi-colon back in and correct the errors.
   8. Add a new, empty line after a `robot.forward` line.  Type `robot` then `.`.  Notice that when you hit the `.` a window appears with a list of options.  Eclipse is letting you know the choice available to you here.  This is one benefit of using an IDE like Eclipse.
   9.  Experiment with changing / adding other commands.

Working With Code
-----------------

Now that you understand how to use Eclipse to modify and run the program, spend some time making the robot draw a picture of a house.

2. Commit and push your work
================

Follow the instructions from [studio 0]({{ site.baseurl }}/modules/0/studio) to commit and push your work.

After doing `Commit and Push` always check your work on GitHub.  Go to [the course page on GitHub](https://github.com/wustlcse131fl21), select the respository for the assignment, and then review the individual files.  

The TAs will be asking you some questions about GitHub (and debugging) as part of the submission process, so be sure to review the content of studio 0 before submitting this assignment.

3. Course Information
================

Review the course site on [Canvas]({{ site.canvasCourseURL }}).  Make sure you review:
1. [Course Policies]({{ site.canvasCourseURL }}/pages/course-policies)
2. Know where to go to find [Office Hours]({{ site.canvasCourseURL }}/pages/help-and-office-hours), which will be posted by the second week of class.
3. Know how to [browse the content and prepare for modules]({{site.canvasCourseURL}}).
4. Be sure you're signed up for the course's [Piazza forum]({{site.piazzaURL}}).


4. "Demo" your work to a TA!
================

To receive credit for an assignment in this course you must demo your work to an instructor or a TA. The person demoing you will walk you through the rubric for the assignment, which can be found on Canvas. It is a good idea to take a look at the rubric yourself and make sure that all parts of the assignment are completed before starting a demo!

1. Show the TA your work
2. Show them your final work on GitHub.
3. Ask any questions you have about the course.
4. *Confirm that your score is recorded in [Canvas]({{ site.canvasCourseURL }}/grades)*.  Mistakes can happen and you should always confirm credit is recorded before leaving class!
