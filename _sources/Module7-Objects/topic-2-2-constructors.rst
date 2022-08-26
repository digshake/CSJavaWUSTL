.. qnum::
   :prefix: 2-2-
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
	pair: class; constructor

.. |repl link| raw:: html

   <a href="https://repl.it/@LindaMM/Java-Swing-Turtle" target="_blank" style="text-decoration:underline">repl.it link</a>

.. |github| raw:: html

   <a href="https://github.com/bhoffman0/APCSA-2019/tree/master/_sources/Unit2-Using-Objects/TurtleJavaSwingCode.zip" target="_blank" style="text-decoration:underline">here</a>

Creating and Initializing Objects: Constructors
================================================

A Java class defines the data (attributes) and behavior (methods) of a set of similar objects. 
Each class has a special type of method called a 
**constructor**  that is used to initialize the attributes in a newly created object.

.. note::

  A constructor is a special method that has the same name as the class and is used to initialize attributes of a new object. 


A new object is created with the ``new`` keyword followed by the class name.
For example, ``new World()`` calls the World constructor to initialize a new object of the ``World`` class, 
which results in the creation of a graphical window used for drawing.
The code ``new Turtle(world)`` calls the Turtle constructor to initialize the 
attributes of a new ``Turtle`` object that is placed within the drawing window of the specified world.

.. code-block:: java

    // To create a new object and call a constructor write:
    // ClassName variableName = new ClassName(parameters);
    World world = new World();    // create a new World object
    Turtle t = new Turtle(world); // create a new Turtle object 

World Class Constructors
---------------------------

The ``World`` class has 2 constructors, which means there are two different ways to create a World object.
You can create a World using default values for the size of the graphical window, or you can provide 
a specific width and height.  


In Java, **formal parameters** are variables that act as value placeholders that you 
define for a method.  When you place values between the
parentheses of a method call, the values get copied into the formal parameter variables.
The values placed between the parentheses of a method call are called **arguments** or **actual parameters**.

.. code-block:: java

    World world1 = new World();        // creates a 640x480 world
    World world2 = new World(300,400); // creates a 300x400 world

The first ``World()`` constructor has no parameters (there is nothing between the parentheses) and 
initializes a graphical window with a default size of 640x480 pixels.   

The second constructor ``World(int width, int height)``  has two formal parameters to initialize the 
graphical window to a specific width and height.  When you call the second constructor, you must provide actual integer values
for the width and height. 
For example, ``new World(300,400)`` creates a world with a graphical window sized 300x400  pixels.

.. figure:: Figures/worldConstructors.png
    :width: 350px
    :align: center
    :alt: Two World constructors
    :figclass: align-center

    Figure 1: Two World constructors
    

Classes frequently have more
than one constructor, which is called **constructor overloading**. 
There is usually a constructor that has no parameters like the ``World()`` constructor above.  This is also 
called the **no-argument constructor** and it sets the 
attributes to default values.   There can also be  constructors with formal parameters to 
initialize the attributes, such as the ``World(int width, int height)``  constructor.  The World constructor is overloaded
since there are two versions available, each with a different parameter list.


|Exercise| **Check your understanding**

.. mchoice:: q2_2_1
   :practice: T
   :answer_a: When a constructor takes one parameter.
   :answer_b: When a constructor takes more than one parameter.
   :answer_c: When one constructor is defined in a class.
   :answer_d: When more than one constructor is defined in a class.
   :correct: d
   :feedback_a: For a constructor to be overloaded there must be more than one constructor.
   :feedback_b: For a constructor to be overloaded there must be more than one constructor.
   :feedback_c: For a constructor to be overloaded there must be more than one constructor.
   :feedback_d: Overloading means that there is more than one constructor.  The parameter lists must differ in either number, order, or type of parameters.

   Which of these is overloading?

.. mchoice:: q2_2_2
   :practice: T
   :answer_a: World w = null;
   :answer_b: World w = new World;
   :answer_c: World w = new World();
   :answer_d: World w = World();
   :correct: c
   :feedback_a: This declares a variable w that refers to a World object, but it doesn't create a World object or initialize it.
   :feedback_b: You must include parentheses () to call a constructor.
   :feedback_c: Use the new keyword followed by the classname and parentheses to create a new object and call the constructor.
   :feedback_d: You must use the new keyword to create a new object.

   Which of these is valid syntax for creating and initializing a World object?

.. mchoice:: q2_2_3
   :practice: T
   :answer_a: World w = (300,400);
   :answer_b: World w = new World(300,400);
   :answer_c: World w = World(300,400);
   :answer_d: World  = new World(300,400);
   :correct: b
   :feedback_a: This is missing the keyword new and the constructor method name World.
   :feedback_b: Use the new keyword followed by the classname and parentheses to create a new object and call the constructor.
   :feedback_c: This is missing the keyword new.
   :feedback_d: The lefthand size of the assignment is missing the variable name.

   Which of these is valid syntax for creating and initializing a World object with size 300x400?


.. note ::
   The turtle world does not use the cartesian coordinate system.  
   The origin (0,0) is in the **top left corner**, x increases to the right, and y increases 
   as you go **down** the screen rather than up.   
   This unusual coordinate system is due to historical reasons. When physical devices were
   first built, they would scan from left to right and then top to bottom.

.. figure:: Figures/coords.png
    :width: 200px
    :align: center
    :figclass: align-center

    Figure 2: The coordinate (0,0) is at the top left of the Turtle world.

The Turtle Class Constructors
----------------------------------------------------------

.. |turtle documentation| raw:: html

   <a href="https://www2.cs.uic.edu/~i101/doc/Turtle.html" target="_blank" style="text-decoration:underline">documentation</a>

When you use a class that someone has already written for you in a **library**  like the ``Turtle`` class, you can look up how to use the constructors and 
methods in the |turtle documentation| for that class.  The documentation will 
list the **signatures** (or headers) of the constructors or methods which will tell you 
their name and parameter list. The **parameter list**, in the **header** of a constructor, 
lists the **formal parameters**, declaring the variables that will be passed in as values and their data types. 
A no-arguments constructor will have an empty parameter list.

.. figure:: Figures/TurtleClassDefn.png
    :width: 600px
    :align: center
    :alt: Turtle Class Constructor Signatures and Parameters
    :figclass: align-center

    Figure 3: Turtle Class Constructor Signatures and Parameters


The ``Turtle`` class has multiple constructors, although it always requires a World as a parameter 
in order to have a place to draw.  The first constructor places the turtle in a default location in the middle of the world.
The second constructor places the turtle at a certain (x,y) location in the world.


.. code-block:: java

    World world = new World();
    Turtle t1 = new Turtle(world);           //place in center of world     
    Turtle t2 = new Turtle(50, 100, world);  //place at 50, 100


.. note::
   The order of the argument values matter. 
   The ``Turtle`` constructor takes ``(x,y,world)`` as parameters in that order. 
   If you mix up the order of the parameters it will cause an error, because the parameters will not be the data types that it expects. This is one reason why programming languages have data types -- to allow for error-checking.


|Exercise| **Check your understanding**

.. mchoice:: q2_2_4
   :practice: T
   :answer_a: Turtle t = Turtle(world);
   :answer_b: Turtle t = new Turtle();
   :answer_c: Turtle t = new Turtle(world);
   :answer_d: World t = new Turtle(world);
   :correct: c
   :feedback_a: You must use the new keyword to create a new Turtle.
   :feedback_b: All turtle constructors must take a world as a parameter.
   :feedback_c: This creates a Turtle object and places it in the center of the world.
   :feedback_d: You can not assign a Turtle object to a variable declared to have type World.

   Which of these is valid syntax for creating and initializing a Turtle object in the center of the world?


.. mchoice:: q2_2_5
   :practice: T
   :answer_a: Turtle t = new Turtle();
   :answer_b: Turtle t = new Turtle(50,75);
   :answer_c: Turtle t = new Turtle(world1);
   :answer_d: Turtle t = new Turtle(world1,50,75);
   :answer_e: Turtle t = new Turtle(50,75,world1);
   :correct: e
   :feedback_a: There is no Turtle constructor that takes no parameters according to the figure above.
   :feedback_b: There is no Turtle constructor that takes 2 parameters according to the figure above.
   :feedback_c: This would initialize the Turtle to the middle of the world, not necessarily coordinates (50,150).
   :feedback_d: Make sure the order of the parameters match the constructor signature above.
   :feedback_e: This matches the second constructor above with the parameters of x, y, and world.

   Given the Turtle class and a World object referenced by variable world1, 
   which of the following code segments will correctly create an instance of a 
   Turtle object at (x,y) coordinates (50,75)?


|CodingEx| **Coding Exercise:**

.. activecode:: code2_2_1
    :language: java
    :autograde: unittest
    :nocodelens: 
    :datafile: turtleClasses.jar

    Try changing the code below to create a ``World`` object with 300x400 pixels. 
    Where is the turtle placed by default? What parameters do you need to 
    pass to the ``Turtle`` constructor to put the turtle near the top right corner? Recall that (0,0) is 
    the top left corner and y increases as you go down the window. Experiment with different initial locations for the turtle. What happens if you mix up the order of the parameters?

    (If the code below does not work in your browser, you can also copy the code into  
    this |repl link| (refresh page after forking if it gets stuck) or download the files |github| to use 
    in your own IDE.)
    ~~~~
 
    public class TurtleConstructorTest
    {
      public static void main(String[] args)
      {
          // Change the World constructor to 300x400
          World world = new World(300,300);

          // Change the Turtle constructor to put the turtle in the top right corner
          Turtle t1 = new Turtle(world);

          t1.turnLeft();
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
            super("TurtleConstructorTest");
        }

        @Test
        public void test1()
        {
            String code = getCode();
            String expect = "new World(300,400)";

            int count = countOccurences(code, expect);

            boolean passed = count >= 1;

            passed = getResults("1 new World(300,400)", "" + count  + " new World(300,400)", "Create 300x400 World", passed);
            assertTrue(passed);
        }


        @Test
        public void test2()
        {
            String code = getCode();
            String expect = ",world)";

            int count = countOccurences(code, expect);

            boolean passed = count >= 1;

            passed = getResults("1 new Turtle(x, y, world)", "" + count  + " new Turtle(x, y, world)", "Create Turtle at some x,y position", passed);
            assertTrue(passed);
        }


    }

Object Variables and References
---------------------------------

An object is created when you call a constructor. You need to declare an **object variable** to 
reference the newly created object.  An object variable has a type that is a class, rather than a primitive
such as int, double or boolean.  ``Turtle t1`` and ``World world`` are both object variable declarations since Turtle and World are classes and not primitive types.

You assign an object variable by calling a constructor on the right hand side of an equal sign, for example ``World world = new World();`` or
``Turtle t1 = new Turtle(world);``.


|CodingEx| **Coding Exercise:**

.. activecode:: code2_2_2
    :language: java
    :autograde: unittest
    :nocodelens: 
    :datafile: turtleClasses.jar

    Run the code below, which creates two instances of the Turtle class.  
    Add a third turtle object that draws a square by repeatedly turning left and moving forward.
    Make sure you give your new turtle a unique variable name.
    ~~~~
   
    public class TurtleTest3
    {
      public static void main(String[] args)
      {
          World world = new World(300,300);
          Turtle yertle = new Turtle(world);
          Turtle myrtle = new Turtle(world);

          yertle.forward();
          yertle.turnLeft();
          yertle.forward();

          myrtle.turnRight();
          myrtle.forward();

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
            super("TurtleTest3");
        }

        @Test
        public void test1()
        {
            String code = getCode();
            String expect = "new Turtle(world)";

            int count = countOccurences(code, expect);

            boolean passed = count >= 3;
            passed = getResults("3+ Turtles", "" + count  + " Turtles", "Add a new Turtle(s)", passed);
            assertTrue(passed);
        }
    }




Formal Parameters and Pass By Value
------------------------------------

In a later lesson you will learn to write your own classes. 
However, if you see a class definition like the one below for a class 
called ``Date``, you should be able to pick out the attributes (instance variables) 
and the constructors and know how to use them.

.. figure:: Figures/DateClass.png
    :width: 500px
    :align: center
    :alt: A Date class showing attributes and constructors
    :figclass: align-center

    Figure 4: A Date class showing attributes and constructors

|Exercise| **Check your understanding**

.. mchoice:: q2_2_6
   :practice: T
   :answer_a: Date d = new Date();
   :answer_b: Date d = new Date(9,20);
   :answer_c: Date d = new Date(9,20,2020);
   :answer_d: Date d = new Date(2020,9,20);
   :answer_e: Date d = new Date(2020,20,9);
   :correct: d
   :feedback_a: This would initialize the date attributes to today's date according to the constructor comment above, which might not be Sept. 20, 2020.
   :feedback_b: There is no Date constructor that takes 2 parameters according to the figure above.
   :feedback_c: The comment for the second constructor in the Date class above says that the first parameter must be the year.
   :feedback_d: This matches the second constructor above with the parameters year, month, day.
   :feedback_e: Make sure the order of the parameters match the constructor signature above.

   Given the ``Date`` class in the figure above and assuming that months in the ``Date`` class are numbered starting at 1, which of the following code segments will create a ``Date`` object for the date September 20, 2020 using the correct constructor?



When a constructor like ``Date(2005,9,1)`` is called, the formal parameters, (year, month, day), are set 
to copies of the  actual parameters, which are (2005,9,1).  This is **pass by value** which means that 
copies of the actual parameter values are passed to the constructor.  
These values are used to initialize the object's attributes.

.. figure:: Figures/parameterMappingDate.png
    :width: 450px
    :align: center
    :alt: Parameter Mapping
    :figclass: align-center

    Figure 5: Parameter Mapping

The type of the values being passed in as arguments have to match the type of the formal parameter variables. 
We cannot give a constructor a ``String`` object when it is expecting an ``int``. 
The order of the arguments also matters. 
If you mix up the month and the day in the ``Date`` constructor, you will get a 
completely different date, for example January 9th (1/9) instead of Sept. 1st (9/1).

|Exercise| **Check your understanding**

.. mchoice:: q2_2_7
   :practice: T
   :answer_a: objects
   :answer_b: classes
   :answer_c: formal parameters
   :answer_d: actual parameters
   :correct: c
   :feedback_a: Objects have attributes and behavior.
   :feedback_b: A class defines the data and behavior for all objects of that type.
   :feedback_c: A formal parameter is in the constructor's signature.
   :feedback_d: A actual parameter (argument) is the value that is passed into the constructor.

   Given the constructor signature ``public World(int width, int height)``, what are ``width`` and ``height``?

.. mchoice:: q2_2_8
   :practice: T
   :answer_a: objects
   :answer_b: classes
   :answer_c: formal parameters
   :answer_d: actual parameters
   :correct: d
   :feedback_a: Objects have attributes and behavior.
   :feedback_b: A class defines the data and behavior for all objects of that type.
   :feedback_c: A formal parameter is in the constructor's signature.
   :feedback_d: A actual parameter (argument) is the value that is passed into the constructor.

   Given the constructor call ``new World(150, 200)``, what are ``150`` and ``200``?



This lesson introduces a lot of vocabulary, but don't worry if you don't 
understand everything about classes and constructors yet. 
You will learn more about how this all works in a later lesson when you write your 
own classes and constructors. 


Summary
-------------------


- **Constructors** initialize the attributes in newly created objects.  They have the same name as the class.

- A **constructor signature** is the constructor name followed by the parameter list which is a list of the types of the parameters and the variable names used to refer to them in the constructor.

- **Overloading** is when there is more than one constructor.  They must differ in the number, type, or order of parameters.

- **New** is a keyword that is used to create a new object of a class.  The syntax is ``new ClassName()``.  It creates a new object of the specified class and calls a constructor.

- A **no-argument constructor** is a constructor that doesn't take any passed in values (arguments).

- **Parameters** allow values to be passed to the constructor to initialize the newly created object's attributes.

- The **parameter list**, in the header of a constructor, is a list of the type of the value being passed and a variable name. These variables are called the **formal parameters**.

- **Actual parameters** are the values being passed to a constructor.  The formal parameters are set to a copy of the value of the actual parameters.

- **Formal parameters** are the specification of the parameters in the constructor header.  In Java this is a list of the type and name for each parameter (``World(int width, int height``).

- **Call by value** means that when you pass a value to a constructor or method it passes a copy of the value.
