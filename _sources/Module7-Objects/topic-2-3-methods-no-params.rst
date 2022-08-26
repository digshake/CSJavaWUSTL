.. qnum::
   :prefix: 2-3-
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


.. |github| raw:: html

   <a href="https://github.com/bhoffman0/APCSA-2019/tree/master/_sources/Unit2-Using-Objects/TurtleJavaSwingCode.zip" target="_blank" style="text-decoration:underline">here</a>

.. |repl link| raw:: html

   <a href="https://repl.it/@LindaMM/Java-Swing-Turtle" target="_blank" style="text-decoration:underline">repl.it link</a>


Calling Object Methods Without Parameters
===========================================

Methods define common behavior for all objects of the class.
In the ``Turtle`` class, methods 
like ``forward()`` and ``turnRight()`` give turtle objects the ability to 
move forward 100 pixels and turn 90 degrees right.

The methods written for the Turtle class are called **object methods** or **non-static methods**. 
An object method *must* be called on an object of the class.  
Object methods work with the **attributes** of the object, such as the 
direction the turtle is heading or its position.  

To call an object method, you must use a variable that references an object, along with the dot (.) operator followed 
by the method name.  For example, ``yertle.forward();`` calls the "forward" method on the turtle referenced
by the variable "yertle", which results in a change to yertle's location.  
On the other hand, ``myrtle.turnRight()`` calls the "turnRight" method on a different turtle object
referenced by the "myrtle" variable, resulting in a change to myrtle's heading. 

Every method call is followed by parentheses. 
The parentheses ``()`` after method names are there in case you need to give the 
method parameters (data) to do its job. 
You must always include the parentheses after the method name.


|Exercise| **Check Your Understanding: Mixed-up Code**

.. parsonsprob:: q2_3_1
   :practice: T
   :numbered: left
   :adaptive:
   :noindent:

   The following code uses a turtle to draw the digital number 7, but the lines are mixed up.  
   Drag the code blocks to the right and put them in the correct order to first 
   draw the line going up (towards the top of the page) and then turn and draw a 
   line to the left to make a 7. Remember that the turtle is facing the top of the 
   page when it is first created. 
   -----
   public class Draw7
   {
   =====
       public static void main(String[] args)
       {
   =====
           World world = new World(300,300);
   =====
           Turtle yertle = new Turtle(world);
   =====
           yertle.forward();
   =====
           yertle.turnLeft();
           yertle.forward();
   =====
           world.show(true);
   =====
       } // end main
   =====
   } // end class


|CodingEx| **Coding Exercise:**

.. activecode:: code2_3_1
    :language: java
    :autograde: unittest
    :datafile: turtleClasses.jar

    Can you make yertle draw the digital number 8, as 2 squares on top of each other?
    ~~~~
   
    public class TurtleDraw8
    {
      public static void main(String[] args)
      {
          World world = new World(300,300);
          Turtle yertle = new Turtle(world);
          // Make yertle draw an 8 with 2 squares
          yertle.forward();


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
            super("TurtleDraw8");
        }

        @Test
        public void test1()
        {
            String orig = "public class TurtleDraw8\n{\n  public static void main(String[] args)\n  {\n      World world = new World(300,300);\n      Turtle yertle = new Turtle(world);\n      // Make yertle draw an 8 with 2 squares\n      yertle.forward();\n\n\n      world.show(true);\n  }\n}\n";
            boolean passed = codeChanged(orig);
            assertTrue(passed);
        }

        @Test
        public void test2() {
            String code = getCode();
            int numForward = countOccurences(code, "forward()");

            boolean passed = numForward >= 7;

            passed = getResults("7 or more", ""+numForward, "Calls to forward()", passed);
            assertTrue(passed);
        }

        @Test
        public void test3() {
            String code = getCode();
            int numTurn = countOccurences(code, ".turn");

            boolean passed = numTurn >= 5;

            passed = getResults("5 or more", ""+numTurn, "Calls to turnRight() or turnLeft()", passed);
            assertTrue(passed);
        }
    }

|Groupwork| Programming Challenge : Draw two letters
----------------------------------------------------

Write code in the editor window below (or use the |repl link|) to create  2 turtles to draw 
a pair of simple block-style letters that use just straight lines (no curves or diagonals). 
Each turtle should draw a different letter at a different location.  
Go back to the previous lesson and look over the various Turtle constructors if you forget how to create a turtle at a particular x,y location.

Here are some simple turtle methods that you can use:

- ``forward();``
- ``turnLeft();``
- ``turnRight();``
- ``backward();``
- ``penUp();``
- ``penDown();``


.. activecode:: code2_3_2
    :language: java
    :autograde: unittest
    :datafile: turtleClasses.jar

    You can make the world larger if you need more space to draw.
    ~~~~
    
    public class Turtle2Letters
    {
      public static void main(String[] args)
      {
          World world = new World(500,500);



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
            super("Turtle2Letters");
        }

        @Test
        public void test1()
        {
            String code = getCode();
            String expect = "new Turtle(";

            int count = countOccurences(code, expect);

            boolean passed = count >= 2;
            passed = getResults("2+ Turtles", "" + count  + " Turtles", "Add two Turtles", passed);
            assertTrue(passed);
        }

        @Test
        public void test2()
        {
            String code = getCode();
            String[] lines = code.split("\n");

            boolean passed = lines.length >= 20;
            passed = getResults("20 or more lines", lines.length + " lines", "Adding a reasonable amount of lines to code", passed);
            assertTrue(passed);
        }
    }


You may notice that it is challenging to have your turtles draw with these simple methods, which do
not have formal parameters (there is nothing between the left and right parenthesis). 
In the next lesson, we will use more complex methods that include formal parameters,
where you can indicate how many pixels the turtle should move or what angle to turn!


Summary
-------------------

- **Methods** are a set of instructions that define the behaviors for objects of the class.

- Use **dot notation** to execute an object's method.  This is the object's name followed by the dot (.) operator followed by the method name and parentheses: **object.method();**

- A **method signature** is the method name followed by the parameter list which gives the type and name for each parameter. 

- If a method has no parameters, you still need the parentheses after the name when you call the method.

- An **object method** or **non-static method** is one that must be called on an object of a class.  It usually works with the object's attributes.

- A **static method** or **class method** method is one that doesn't need to be called on an object of a class.
