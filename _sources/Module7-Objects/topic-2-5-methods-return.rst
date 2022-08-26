.. qnum::
   :prefix: 2-5-
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
    single: return
    
.. |repl link| raw:: html

   <a href="https://repl.it/@LindaMM/Java-Swing-Turtle" target="_blank" style="text-decoration:underline">repl.it link</a>

.. |github| raw:: html

   <a href="https://github.com/bhoffman0/APCSA-2019/tree/master/_sources/Unit2-Using-Objects/TurtleJavaSwingCode.zip" target="_blank" style="text-decoration:underline">here</a>
   
Calling Methods that Return Values
===================================

Formal parameters allow you to pass a value into a method.  A method can also pass a value out when it is finished.
If a method is a **void method**, 
like most of the methods we have seen so far, it does not return a value when called. 
But some methods **return** a value when called. 

.. |javadoc (documentation) file| raw:: html

   <a href="https://www2.cs.uic.edu/~i101/doc/SimpleTurtle.html" target="_blank">javadoc (documentation) file</a>   

You can see all the methods that are inherited in Turtle in this |javadoc (documentation) file|. 
The first column in the method summary indicates the **return type** of the method.
Most of the Turtle methods have a void return type.
A void method is often used to modify an object's attributes.  
For example, the ``forward()`` method changes the
turtle location, while the ``turnLeft()`` method changes the direction.  

Now look at the methods in the first column having a return type that is *not* void.  The non-void
methods tend to start
with the word "get" or "is". 
Rather than changing an object's attribute, these methods 
return an attribute value.
For example, the ``getXPos()`` method will return a turtle's x position. 
We refer to non-void methods that return an attribute value as **getter** methods. 


When you use a method that returns a value, you need to save what it 
returns in a variable or use the value in some way for example by printing it out. 
The data type of the variable must match the data type of the return value of the method. 
In the example below the ``getWidth()`` method returns an int, so we need to assign the result
into an int variable ``int width = yertle.getWidth();``.

Here are some examples of using getter methods for a particular turtle object.  Notice the value returned
from each getter method is either stored in a variable or used in a print statement.

.. code-block:: java 

    Turtle yertle = new Turtle(world);
    int width = yertle.getWidth();
    int height = yertle.getHeight();
    System.out.println("Yertle's width is: " + width);
    System.out.println("Yertle's height is: " + height);
    System.out.println("Yertle's x position is: " + yertle.getXPos() );
    System.out.println("Yertle's y position is: " + yertle.getYPos() );
    

.. note::

    A common error is forgetting to do something with the value returned from a method. 
    When you call a method that returns a value, you should do something with that value 
    like saving it into a variable or printing it out.  

|CodingEx| **Coding Exercise:**



.. activecode:: code2_5_1
    :language: java
    :autograde: unittest
    :datafile: turtleClasses.jar

    Try the code below that changes the turtle's width and height. How big or small can you make yertle?

    (If the code below does not work in your browser, you can also copy in the code below into the Turtle code at this |repl link| (refresh page after forking and if it gets stuck) or download the files |github| to use in your own IDE.)
    ~~~~
    public class TurtleTestGetSet
    {
      public static void main(String[] args)
      {
          World world = new World(300,300);
          Turtle yertle = new Turtle(world);           
          System.out.println("Yertle's original width is: " + yertle.getWidth()); 
          System.out.println("Yertle's original height is: " + yertle.getHeight()); 
          yertle.setWidth(200);
          yertle.setHeight(200);
          System.out.println("Yertle's new width is: " + yertle.getWidth());
          System.out.println("Yertle's new height is: " + yertle.getHeight()); 
          yertle.turnRight();
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
            super("TurtleTestGetSet");
        }

        @Test
        public void test1()
        {
            String orig = "public class TurtleTestGetSet\n{\n  public static void main(String[] args)\n  {\n      World world = new World(300,300);\n      Turtle yertle = new Turtle(world);\n      System.out.println(\"Yertle's width is: \" + yertle.getWidth());\n      yertle.setWidth(200);\n      yertle.setHeight(200);\n      System.out.println(\"Yertle's width is: \" + yertle.getWidth());\n      yertle.turnRight();\n      world.show(true);\n  }\n}\n";
            boolean passed = codeChanged(orig);
            assertTrue(passed);
        }
    }
    
|CodingEx| **Coding Exercise:**    

.. activecode:: code2_5_2
    :language: java
    :autograde: unittest
    :datafile: turtleClasses.jar

    Fix the errors in the code below so that it prints out the area of the space that the turtle occupies by multiplying its width and height. Remember that you have to do something with the values that the get methods return.
    ~~~~
    public class TurtleArea
    {
      public static void main(String[] args)
      {
          World world = new World(300,300);
          Turtle yertle = new Turtle(world);
          
          int area;
          yertle.getWidth() * getHeight;
          System.out.println("Yertle's area is: ");
      }
    }
    ====
    import static org.junit.Assert.*;
    import org.junit.*;;
    import java.io.*;

    public class RunestoneTests extends CodeTestHelper
    {
        public RunestoneTests() {
            super("TurtleArea");
        }

        @Test
        public void test1()
        {
            String actual = getMethodOutput("main");
            String expected = "Yertle's area is: 270";
            boolean passed = getResults(expected, actual, "Prints correct answer");
            assertTrue(passed);
        }
    }

toString() Methods
------------------

Another common method that returns a value is the **toString()** method. This method is called automatically to try to convert an object to a String when it is needed, for example in a print statement. In the Turtle class, the toString() method returns a String description of the turtle.

.. code-block:: java 

    Turtle yertle = new Turtle(world);
    yertle.setName("yertle"); // set name before you use toString()
    System.out.println(yertle.toString());
    // Or you can just use the object here and it will call toString() automatically!
    System.out.println(yertle);


|CodingEx| **Coding Exercise:**

.. activecode:: code2_5_3
    :language: java
    :autograde: unittest
    :datafile: turtleClasses.jar

    Try some of the get methods and the toString() method in the program below. Note that you have to print out what the get methods return in order to see what they do!
    ~~~~
    public class TurtleTestMethods2
    {
      public static void main(String[] args)
      {
          World world = new World(300,300);
          Turtle yertle = new Turtle(world);
           
          // Try some get methods here!
         
         
          
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
            super("TurtleTestMethods2");
        }

        @Test
        public void test1()
        {
            String code = getCode();
            int num = countOccurences(code, "getWidth()");

            boolean passed = num > 0;
            getResults(">=1", "" + num, "Calls to getWidth()");
            assertTrue(passed);
        }

        @Test
        public void test2()
        {
            String code = getCode();
            int num = countOccurences(code, "getHeight()");

            boolean passed = num > 0;
            getResults(">=1", "" + num, "Calls to getHeight()");
            assertTrue(passed);
        }

        @Test
        public void test3()
        {
            String code = getCode();
            int num = countOccurences(code, "toString()") + countOccurences(code, "System.out.println(yertle)");

            boolean passed = num > 0;
            getResults(">=1", "" + num, "Calls to toString()");
            assertTrue(passed);
        }
    }


Methods with Arguments and Return Values
-----------------------------------------

Methods that have argument values and return values are like mathematical functions. 
Given some input value, the functions computes and returns another value as a result. 

.. figure:: Figures/function.png
   :align: center
   :alt: function
   :figclass: align-center

   Figure 1: Method that takes arguments (actual parameters) and returns a value

For example, the Turtle class has a function method ``public double getDistance(int x, int y)``.  The  function computes the 
distance between the turtle's current location and  the location passed to the x and y formal parameters.
You will not write your own methods until Unit 5, but you should be able to trace through 
method calls that return a value such as the Turtle getter and function methods.
     
|Groupwork| Programming Challenge : Turtle Distances
----------------------------------------------------

1. The Turtle class has a method called getDistance(x,y) which will return the turtle's distance from a point (x,y). 
Can you find yertle's distance from the point (0,0)?   Keep in mind the signature for the function  ``public double getDistance(int x, int y)``.  
The function returns a double, so you need a variable to store the result.

2. Add another turtle named mertle and make both turtles move. Then find the distance between them. 
You must use the getXPos() and getYPos() methods as well as the getDistance() method.  Ask mertle for their x and y values, then 
call the getDistance on yertle passing in mertle's x and y values.  Keep in mind getXPos() and getYPos() both return an int.

.. activecode:: code2_5_4
    :language: java
    :autograde: unittest
    :datafile: turtleClasses.jar
    
    ~~~~ 
    public class TurtleTestDistance
    {
      public static void main(String[] args)
      {
          World world = new World(300,300);
          Turtle yertle = new Turtle(world);
           
          // Can you find yertle's distance from the point (0,0)? 
          
          // Can you find the distance between 2 turtles?
         
         
          
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
            super("TurtleTestDistance");
        }

        @Test
        public void test2()
        {
            String code = getCode();
            int num = countOccurences(code, ".getXPos()");

            boolean passed = num > 0;
            getResults(">=1", "" + num, "Calls to getXPos()");
            assertTrue(passed);
        }

        @Test
        public void test3()
        {
            String code = getCode();
            int num = countOccurences(code, ".getYPos()");

            boolean passed = num > 0;
            getResults(">=1", "" + num, "Calls to getYPos()");
            assertTrue(passed);
        }

        @Test
        public void test4()
        {
            String code = getCode();
            int num = countOccurences(code, ".getDistance(");

            boolean passed = num >= 2;
            getResults(">=2", "" + num, "Calls to getDistance(...)");
            assertTrue(passed);
        }

        @Test
        public void test1()
        {
            String code = getCode();
            int num = countOccurences(code, ".getDistance(0,0)");

            boolean passed = num >= 1;
            getResults(">=1", "" + num, "Calls getDistance(0,0)");
            assertTrue(passed);
        }
    }


Summary
-------------------

- Some methods return values.
- To use the return value when calling a method, it must be stored in a variable or used as part of an expression. The variable data type must match the return type of the method.
