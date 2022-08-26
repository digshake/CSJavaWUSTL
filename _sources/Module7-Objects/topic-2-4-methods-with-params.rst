.. qnum::
   :prefix: 2-4-
   :start: 1

.. |CodingEx| image:: ../../_static/codingExercise.png
    :width: 30px
    :align: middle
    :alt: coding exercise
    
    
.. |Exercise| image:: ../../_static/exercise.png
    :width: 35
    :align: middle
    :alt: exercise
    
    
.. |Groupwork| image:: ../../_static/groupwork.png
    :width: 35
    :align: middle
    :alt: groupwork
    
..	index::
	single: method
    single: parameter
    single: argument

.. |repl link| raw:: html

   <a href="https://repl.it/@LindaMM/Java-Swing-Turtle" target="_blank" style="text-decoration:underline">repl.it link</a>



.. |github| raw:: html

   <a href="https://github.com/bhoffman0/APCSA-2019/tree/master/_sources/Unit2-Using-Objects/TurtleJavaSwingCode.zip" target="_blank" style="text-decoration:underline">here</a>

    
.. |runbutton| image:: Figures/run-button.png
    :height: 30px
    :align: top
    :alt: run button
   



Calling Methods With Parameters
===========================================

In the last lesson, we used methods like forward() and turnRight() to make the turtle draw lines. 
You may have noticed that forward() and backward() always move the same number of 
pixels (100 pixels), and turnRight() and turnLeft() always turn at right angles (90 degrees). 
This is a little limiting. What if we wanted to draw a triangle or the letter A? 
These require smaller angles to draw diagonal lines and different length lines. 

Luckily, there are more complex methods in the Turtle class that let you specify the number of 
pixels to move forward or the number of degrees to turn.  For example, we can use ``forward(25)`` to make the turtle go 
forward 25 pixels or ``turn(30)`` to make the turtle turn 30 degrees. 
The methods signatures define **formal parameters**, which are placeholders for values that will be passed into the 
method when it is called.  The values passed in are **arguments** or **actual parameters**.



Although some people use the words parameters and arguments interchangeably, there is a subtle difference. 
When a method is defined, the method signature will list the formal parameters.  The method implementation will
use the formal parameters to customize the object behavior. The code below
shows the signature for the forward method, which has a 
parameter variable called pixels (the method implementation is not shown).  The subsequent code block
shows the method call forward(25).  The actual parameter 
value 25  will get copied into the formal parameter variable pixels. 

.. code-block:: java 

    // The method signature has one formal parameter of type int.
    public void forward(int pixels) // parameter pixels


.. code-block:: java 
    
    // Method call must pass an argument (also called actual parameter) that is an int value
    yertle.forward(25); 


|Exercise| **Check your understanding**

.. dragndrop:: q2_4_1
    :feedback: Review the vocabulary above.
    :match_1: an object's behaviors or functions that can be used or called to do its job|||methods
    :match_2: the values or data passed to an object's method|||arguments or actual parameters
    :match_3: the variables in a method's definition that hold the arguments|||formal parameters
    :match_4: asking to run the method|||method call    
    
    Drag the definition from the left and drop it on the correct word on the right.  Click the "Check Me" button to see if you are correct.

	
The Turtle class inherits many attributes and methods from another class called SimpleTurtle.  You will learn about
inheritance in a later lesson.  But for now you can look at the  Turtle class diagram listed in the figure below that shows 
some (not all) of the attributes and methods inherited from the SimpleTurtle class.    The formal parameters
are shown between the parentheses that follow the method name, and list the type after the parameter name.   
While the notation might be different that what you are used to for Java code,  
the class model should give you some ideas about new ways to move your turtle objects. 
You can see all the methods that are inherited in Turtle in this |javadoc (documentation) file|. 

.. figure:: Figures/turtleUMLClassDiagram.png
    :align: center
    :alt: Turtle class diagram
    :figclass: align-center

    Figure 1: Turtle Class Diagram
    
.. |Color| raw:: html

   <a href= "https://docs.oracle.com/javase/7/docs/api/java/awt/Color.html" target="_blank">Color</a>
   
.. |javadoc (documentation) file| raw:: html

   <a href="https://www2.cs.uic.edu/~i101/doc/SimpleTurtle.html" target="_blank">javadoc (documentation) file</a>   

Methods are said to be **overloaded** when there
are multiple methods with the same name but a different number or type of parameters. 
For example, the Turtle class diagram lists two different forward methods, one with no parameters 
and one that has a formal parameter of type int that tells the turtle how much to move forward. 

.. note::

  A class diagram may list the parameter type after the variable name, such as ``pixels : int``. 
  However, when you write Java code you always list the type before the variable ``int pixels``.


|CodingEx| **Coding Exercise**

Experiment with using some turtle methods that take parameters. 
If the code below does not work in your browser, you can also use the Turtle code 
at this |repl link| (refresh page after forking and if it gets stuck) or download 
the files |github| to use in your own IDE.

.. activecode:: code2_4_1
    :language: java
    :autograde: unittest
    :nocodelens: 
    :datafile: turtleClasses.jar

    1. Can you make yertle draw a square and change the pen color for each side of the square? 
    Try something like: yertle.setColor(Color.red); 
    This uses the |Color| class in Java which has some colors predefined like 
    red, yellow, blue, magenta, cyan. 
    You can also use more specific methods like setPenColor, setBodyColor, and setShellColor.
    2. Can you draw a triangle? The turnRight() method always does 90 degree turns, but you'll need 60 degree angles for a equilateral triangle. Use the turn method which has a parameter for the angle of the turn in degrees. For example, turn(90) is the same as turnRight(). Try drawing a triangle with different colors. 
    ~~~~

    import java.awt.Color;   //import Color class

    public class TurtleTestMethods
    {
      public static void main(String[] args)
      {
          World world = new World(300,300);
          Turtle yertle = new Turtle(world);
          
          yertle.forward(100);
          yertle.turnLeft();
          yertle.forward(75);
          
          world.show(true); 
      }
    }
    ====
    import static org.junit.Assert.*;
    import org.junit.*;;
    import java.io.*;

    public class RunestoneTests extends CodeTestHelper
    {
        public RunestoneTests() {
            super("TurtleTestMethods");
        }

        @Test
        public void test1()
        {
            String orig = "public class TurtleTestMethods\n{\n  public static void main(String[] args)\n  {\n      World world = new World(300,300);\n      Turtle yertle = new Turtle(world);\n\n      yertle.forward(100);\n      yertle.turnLeft();\n      yertle.forward(75);\n\n      world.show(true);\n  }\n}\n";
            boolean passed = codeChanged(orig);
            assertTrue(passed);
        }

        @Test
        public void test2()
        {
            String code = getCode();
            int numColors = countOccurences(code, "Color(");

            boolean passed = numColors >= 4;
            passed = getResults("4 or more", ""+numColors, "Changing color at least 4 times", passed);
            assertTrue(passed);
        }

        @Test
        public void test3()
        {
            String code = getCode();
            int numTurns = countOccurences(code, ".turn");

            boolean passed = numTurns >= 4;
            passed = getResults("4 or more", ""+numTurns, "Number of turns", passed);
            assertTrue(passed);
        }

        @Test
        public void test4()
        {
            String code = getCode();
            int numTurns = countOccurences(code, ".turn(");

            boolean passed = numTurns >= 1;
            passed = getResults("1 or more", ""+numTurns, "Calls to turn(...)", passed);
            assertTrue(passed);
        }

        @Test
        public void test5()
        {
            String code = getCode();
            int numForward = countOccurences(code, ".forward(");

            boolean passed = numForward >= 4;
            passed = getResults("4 or more", ""+numForward, "Calls to forward()", passed);
            assertTrue(passed);
        }
    }



|Exercise| **Test your understanding - mixed up code**

Try the following mixed up code to draw a simple house made of a square and a triangle roof.

.. image:: Figures/house.png
    :width: 200px
    :align: left
    :alt: simple house
    
    
.. parsonsprob:: q2_4_2
   :numbered: left
   :practice: T
   :adaptive:
   :noindent:
   
   The following code uses a turtle to draw a simple house, but the lines are mixed up.  
   Note that the turtle variable name is "builder" 
   rather than "yertle" or "myrtle". Drag the code blocks to the right and put them in the correct order to first draw a square for the house and then a red triangle for the roof.  Click on the "Check Me" button to check your solution.  You can copy and paste this code in the Active Code window above to see it in action.
   -----

   import java.awt.Color;   //import Color class
   public class TurtleDrawHouse
   {
   =====
      public static void main(String[] args)
      {
      =====
         World world = new World(300,300);
         =====
         Turtle builder = new Turtle(world);
         =====
         // Draw a square
         builder.turnRight();
         builder.forward(100);
         builder.turnRight();
         builder.forward(100);
         builder.turnRight();
         builder.forward(100);
         builder.turnRight();
         builder.forward(100);
         =====
         builder.setColor(Color.red);
         =====
         // Draw a triangle
         builder.turn(30);
         builder.forward(100);
         builder.turn(120);
         builder.forward(100);
         builder.turn(120);
         builder.forward(100);
         =====
         world.show(true);
         =====
      }
      =====
   }
   =====  


|Groupwork| Programming Challenge : Turtle House
------------------------------------------------

.. image:: Figures/houseWithWindows.png
    :width: 200px
    :align: left
    :alt: simple house
    
Design a house and have the turtle draw it with different colors 
below (or with this |repl link|). Can you add windows and a door? 

To draw a window, you will need to do penUp() to walk the turtle into position.  For example, given a turtle named "builder":

.. code-block:: java 

   builder.penUp();
   builder.moveTo(120,200);
   builder.penDown();
   
It may help to act out the code pretending you are the turtle. 
Remember that the angles you turn depend on which direction you are facing, 
and the turtle begins facing up.


.. activecode:: code2_4_2
    :language: java
    :autograde: unittest
    :nocodelens: 
    :datafile: turtleClasses.jar

    import java.awt.Color;   //import Color class
    public class TurtleHouseChallenge
    {
      public static void main(String[] args)
      {
          World world = new World(300,300);
          
          
          
          world.show(true); 
      }
    }
    ====
    import static org.junit.Assert.*;
    import org.junit.*;;
    import java.io.*;

    public class RunestoneTests extends CodeTestHelper
    {
        public RunestoneTests() {
            super("TurtleHouseChallenge");
        }

        @Test
        public void test1()
        {
            String orig = "public class TurtleHouseChallenge\n{\n  public static void main(String[] args)\n  {\n      World world = new World(300,300);\n\n\n\n      world.show(true);\n  }\n}\n";
            boolean passed = codeChanged(orig);
            assertTrue(passed);
        }

        @Test
        public void test2()
        {
            String code = getCode();
            int num = countOccurences(code, "moveTo(");

            boolean passed = num >= 3;
            passed = getResults("3 or more", ""+num, "Calls moveTo(...)", passed);
            assertTrue(passed);
        }

        @Test
        public void test3()
        {
            String code = getCode();
            int num = countOccurences(code, ".penUp()");

            boolean passed = num >= 3;
            passed = getResults("3 or more", ""+num, "Calls penUp()", passed);
            assertTrue(passed);
        }

        @Test
        public void test4()
        {
            String code = getCode();
            int num = countOccurences(code, ".penDown(");

            boolean passed = num >= 3;
            passed = getResults("3 or more", ""+num, "Calls penDown()", passed);
            assertTrue(passed);
        }
        @Test
        public void test5()
        {
            String code = getCode();
            int numTurns = countOccurences(code, ".turn");

            boolean passed = numTurns >= 12;
            passed = getResults("12 or more", ""+numTurns, "turns", passed);
            assertTrue(passed);
        }

        @Test
        public void test6()
        {
            String code = getCode();
            int numForward = countOccurences(code, ".forward(");

            boolean passed = numForward >= 12;
            passed = getResults("12 or more", ""+numForward, "Calls to forward()", passed);
            assertTrue(passed);
        }
    }


Summary
-------------------

- **Methods** define the behaviors or functions for objects. 

- To use an object's method, you must use the object name and the dot (.) operator followed by the method name, for example **object.method();** 

- Some methods take parameters/arguments that are placed inside the parentheses **object.method(arguments)**.

- Values provided in the parameter list need to correspond to the order and type in the method signature.
