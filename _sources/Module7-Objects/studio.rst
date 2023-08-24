=====================
Studio 7: Object Design
=====================

Studio Setup and Procedure
=====================

* Form a group of 2-3 students and find a TA or instructor to work with.

* All but one member of your group should have this web page open so you can follow along and see the instructions as you work.

* Plan to work on one computer (using Eclipse).

  * Initially, one of you will be in charge of typing at that computer.

  * Throughout the studio you should trade who is in charge of the keyboard.

**READ THE FOLLOWING FULLY BEFORE PROCEEDING**

1. Have **one person** in your group create a new team by `clicking here <https://classroom.github.com/a/Sp7ku98M>`_ and going to the ``OR Create a new team`` box at the bottom of the page. The team name should include the last names of all your group members. For example, if Xia and Smith are working together, the team name should be something like “XiaSmith”.

2. **After the team is created**, all other members of your team should click on the same link and follow the instructions to join the team.

   1. **Be careful to join the right team!** You won’t be able to change teams yourself and will have to contact instructors if there’s a problem.

   2. **Be sure everyone else joins the team!** If grades don’t get entered correctly we will use the team to help verify credit for a particular studio.

3. Finally, one person should import the studio repository into Eclipse, as described in `the setup instructions <../Module0-Introduction/software.html>`_.

   * All team members will have access to the work pushed to GitHub. Be sure to ``Commit and Push`` at the end of the day so everyone can refer back to the work later as needed.

Overview
=====================

* This week’s studio is an exercise in design, so get your brains limbered up for some creative thinking.

* In design, there are no wrong or right answers. However, some designs are better than others for certain purposes. It will be important for each person in your group to be able to defend your team’s design.

  * If some member does not understand an aspect of your team’s design, the entire team may be docked studio credit. It is not necessary that all decisions be made with unanimity, but the issues that influence the design one way or the other must be understood by all members of your team.

* A rush to implement something fully will be a Bad Idea. The group’s goal this week is to arrive at a design, not an implementation.

* That said, we will be developing stubs in Eclipse to represent the design, with a bit of Javadoc above each class and method to help generate documentation.

* As you design, thank about the **has-a** idea presented in the videos and articulate the **behaviors** you want your object to have.

* The design problems are presented to you in the form of a `user story <http://www.extremeprogramming.org/rules/userstories.html>`_.

Cautions
=====================

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


Design Problems
=====================

* A number of stories appear below about various object types.

* Pick an object type, read the story, and design and implement a class in your ``studio7`` workspace for the object type.

* Include Javadoc comments in your code, and if possible, generate the Javadoc using Eclipse.

   From the ``Project`` menu choose ``Generate Javadoc...``.

* Write a simple test or two to test your implementation. (I.e., add a ``main()`` that creates some instances of your objects, calls methods to test them, and provide enough information to verify that they are working as expected. If you’ve created description ``toString()`` methods, you can simply print the objects to get a sense of their value)

* Repeat this process with another object type until the end of class.


Object Types
=====================

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


Demo
=====================

**Commit and Push** your work. Be sure that any file you worked on is updated on `GitHub <https://github.com/>`_.


To get participation credit for your work talk to the TA you’ve been working with and complete the demo/review process. Be prepared to show them the work that you have done and answer their questions about it!


*Before leaving check that everyone in your group has a grade recorded in Canvas!*
