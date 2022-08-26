.. qnum::
   :prefix: 1-2-
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
   

.. |Java JDK| raw:: html

   <a href="https://www.oracle.com/technetwork/java/javase/downloads/index.html" target="_blank">Java JDK</a>

.. |javadoc| raw:: html

   <a href="https://www.tutorialspoint.com/java/java_documentation.htm" target="_blank">javadoc</a>

.. |String class| raw:: html

   <a href="http://docs.oracle.com/javase/7/docs/api/java/lang/String.html" target="_blank">String class</a>

    
Why Programming? Why Java?
============================

..	index::
	single: Java
	single: javac
	single: compile
	single: programming language
	pair: programming; language
	pair: Java; source file
	pair: Java; class file

What do Android phones, Minecraft, and Netflix have in common? 
They're all programmed in Java! Many of the apps you use in an Android phone 
or tablet are written in Java. 
Java is a **programming language** that is used worldwide to 
create software that we all use.
    
First Java Program
-------------------

..	index::
	single: class
	single: keyword
	pair: class; field
	pair: class; constructor
	pair: class; method
	pair: class; main method
	
Every program in Java is written as a **class**. Java is an **object-oriented language** and 
we'll learn more about classes and objects in Unit 2. Inside the class, 
there can be a **main method** that starts the program. When you ask the 
Java environment to *run* a class, it will always start execution in the main method. 
Here is the template for a simple Java program with a main method:

.. code-block:: java 

   public class MyClass
   {
      public static void main(String[] args)
      {
         // Put your code here!
      }
   }
   
.. note::

   In Java every open curly brace ``{`` must have a matched close curly brace ``}``.  
   These are used to start and end class definitions and method definitions.  

   The special characters ``//`` are used to mark the rest of the line as a comment.
   Comments can be helpful in describing what the code is doing.


|CodingEx| **Coding Exercise**: 

Click on the ``Save & Run`` button below to have the 
computer execute the ``main`` method in the following class. 
``System.out.println("Hi there!");`` prints out the characters between the first ``"`` and the 
second ``"`` followed by a new line.  
The ``"Hi there!"`` is called a **string literal**, and it can have zero to many characters 
enclosed in starting and ending double quotes. 
Then, 
change the code  to print your name.  
Be sure to keep the starting ``"`` and ending ``"``.  
Run the modified code to test your changes. If you revisit this page later and login, 
click on ``Load History`` button and move the bar above it to see your previous code changes.
 
.. activecode:: code1_2_1
   :language: java
   :autograde: unittest    

   Run this code to see the output below it. 
   Then change the code to print your name, for example "Hi Pat!", and run again. 
   If you mess up the code, hit the "Load History" button and use the slider to go back to a previous version.
   ~~~~    
   public class HelloExample
   {
      public static void main(String[] args)
      {
         System.out.println("Hi there!");
      }
   }
     
   ====
   // should pass if/when they run code
   import static org.junit.Assert.*;
   import org.junit.*;;
   import java.io.*;

   public class RunestoneTests extends CodeTestHelper
   {
        @Test
        public void testMain() throws IOException
        {
            String output = getMethodOutput("main");
            String expect = "Hi there!";
            boolean passed = getResults(expect, output, "Expected output from main", true);
            assertTrue(passed);
        }
   }



You can copy the Java source code shown in this book into a file and save 
it if you want to run it in an integrated development environment (IDE) 
on your local computer (see section 1.7 for different IDEs).  
You must name the file the same name as the class name with ".java" as the extension.  
All code (programs) in Java must be defined inside a class in a source file, 
and the name of the class must match the file name. 


.. activecode:: code1_2_2
   :language: java
   :autograde: unittest    

   Run this code to see the output below it. 
   Then change the code to add two more lines to the poem: "Java is interesting," followed by "And so are you!".
   ~~~~    
   public class PoemExample
   {
      public static void main(String[] args)
      {
         System.out.println("Roses are red,");
         System.out.println("Violets are blue,");
      }
   }
     
   ====
   // should pass if/when they run code
   import static org.junit.Assert.*;
   import org.junit.*;;
   import java.io.*;

   public class RunestoneTests extends CodeTestHelper
   {
        @Test
        public void testMain() throws IOException
        {
            String output = getMethodOutput("main");
            String expect = "Roses are red,\nViolets are blue,\nJava is interesting,\nAnd so are you!";
            boolean passed = getResults(expect, output, "Expected output from main");
            assertTrue(passed);
        }
   }


Most command keywords in Java must be in lowercase, 
but class names such as System and String are capitalized. 
Commands in Java must end with a semicolon ``;``. Think of the semicolon ``;``
in Java like a period in English. You use a semicolon ``;`` to show the 
end of a Java **statement**, just the way you use a period to show the end 
of an English sentence.   Your programs won't run if you forget the semicolon at the 
end of each statement.


Print Commands
-------------------

..	index::
	single: String
	single: String literal

Java has two different print commands to print output to the screen:

- **System.out.println(value)** : prints the value followed by a new line (ln) 
- **System.out.print(value)** : prints the value without advancing to the next line



|CodingEx| **Coding Exercise:**

.. activecode:: code1_2_3
   :language: java
   :autograde: unittest 

   Run this code to see the output below it. 
   How would you change it to print the ! on the same line as Hi there 
   keeping all 3 print statements?
   ~~~~    
   public class HelloExample2
   {
      public static void main(String[] args)
      {
         System.out.print("Hi ");
         System.out.println("there");
         System.out.print("!");
      }
   }
        
   ====
   // should pass if/when they run code
   import static org.junit.Assert.*;
   import org.junit.*;;
   import java.io.*;

   public class RunestoneTests extends CodeTestHelper
   {
        @Test
        public void testMain() throws IOException
        {
            String output = getMethodOutput("main");
            String expect = "Hi there!";
            boolean passed = getResults(expect, output, "Expected output from main");
            assertTrue(passed);
        }
        @Test
        public void testLineCount() throws IOException
        {
            String output = getMethodOutput("main");
            String expect = "1 output line";
            String actual = "  output line";

            if (output.length() > 0) {
               actual = output.split("\n").length + actual;
            } else {
               actual = output.length() + actual;
           }
           boolean passed = getResults(expect, actual, "Checking lines of output");
           assertTrue(passed);
        }
   }


|Exercise| **Check Your Understanding**


.. mchoice:: q1_2_1
    :practice: T
    
    Consider the following code segment.

    .. code-block:: java

       System.out.print("Java is ");
       System.out.println("fun ");
       System.out.print("and cool!");

    What is printed as a result of executing the code segment?       
    
    - .. raw:: html
    
         <pre>Java is fun and cool!</pre>

      - Notice the println in line 2.

    - .. raw:: html
    
         <pre>
         Java isfun 
         and cool!
         </pre>

      - Notice the space after is in the first line. 
      
    - .. raw:: html
      
         <pre>Java is
         fun 
         and cool!  </pre>

      - Notice that the first line is a print, not println.
      
    - .. raw:: html
      
         <pre>Java is fun
         and cool!  </pre>
      
      + Correct! Pay attention to which lines are print or println.


   

A print statement can also contain numeric values and arithmetic expressions.  Don't use double quotes for 
expressions that have a numeric value.


.. activecode:: code1_2_4
   :language: java
   :autograde: unittest 

   Run this code to see the output below it. 
   Can you change the last print statement to print the sum of the values from 1 to 10?
   ~~~~    
   public class CalculationExample
   {
      public static void main(String[] args)
      {
         System.out.println(570 * 23);
         System.out.println(12.34 / 5);
         System.out.println(1 + 2 + 3 + 4 + 5 );
      }
   }
          
   ====
   // should pass if/when they run code
   import static org.junit.Assert.*;
   import org.junit.*;;
   import java.io.*;

   public class RunestoneTests extends CodeTestHelper
   {
        @Test
        public void testMain() throws IOException
        {
            String output = getMethodOutput("main");
            String expect = "13110\n2.468\n55\n";
            boolean passed = getResults(expect, output, "Expected output from main");
            assertTrue(passed);
        }
        
   }


.. activecode:: code1_2_5
   :language: java
   :autograde: unittest 

   Run this code to see the output below it.  The output is not correct.  
   The second System.out.println statement should print the value resulting from the computation, not a literal string for the computation. 
   Get rid of the double quotes in the second println statement and run the program.
   
   ~~~~    
   public class CalculationErrorPrint
   {
      public static void main(String[] args)
      {
         System.out.println("570 * 23 = ");
         System.out.println("570 * 23");
      }
   }
   ====
   // should pass if/when they run code
   import static org.junit.Assert.*;
   import org.junit.*;;
   import java.io.*;

   public class RunestoneTests extends CodeTestHelper
   {
        @Test
        public void testMain() throws IOException
        {
            String output = getMethodOutput("main");
            String expect = "570 * 23 = \n13110\n";
            boolean passed = getResults(expect, output, "Expected output from main");
            assertTrue(passed);
        }
        
   }


.. activecode:: code1_2_6
   :language: java
   :autograde: unittest 

   Assume you have some bills to pay.  The individual bill amounts are 89.50, 14.75, 45.12, and 92.50.  
   Add another print statement to sum and print the total bill amount on a separate line.  Don't just add the numbers in
   your head and print the result. You must write the code to add up the numbers and print the result.
   
   ~~~~    
   public class CalculateBillTotal
   {
      public static void main(String[] args)
      {
         System.out.println("Bill total:");
         
      }
   }
   ====
   // should pass if/when they run code
   import static org.junit.Assert.*;
   import org.junit.*;;
   import java.io.*;

   public class RunestoneTests extends CodeTestHelper
   {
        @Test
        public void testMain() throws IOException
        {
            String output = getMethodOutput("main");
            String expect = "Bill total:\n241.87\n";
            boolean passed = getResults(expect, output, "Expected output from main");
            assertTrue(passed);
        }

       @Test
       public void test2() throws IOException
       {
           String target1 = "System.out.println( 89.50 + 14.75 + 45.12 + 92.50";
           boolean passed1 = checkCodeContains("bill calculation", target1);
          
           assertTrue(passed1);
       }
        
   }



.. activecode:: code1_2_7
   :language: java
   :autograde: unittest 

   A bus starts out with no passengers.  Three people get on at the first stop.  
   Five people get on at the second stop.
   One person gets off and eight people get on at the third stop. 
   Three people get off at the fourth stop. How many people are left on the bus?
   Add another print statement to calculate and print the passengers remaining on the bus.

   ~~~~    
   public class PassengersOnBus
   {
      public static void main(String[] args)
      {
         System.out.print("Passengers remaining : ");
        
      }
   }
   ====
   // should pass if/when they run code
   import static org.junit.Assert.*;
   import org.junit.*;;
   import java.io.*;

   public class RunestoneTests extends CodeTestHelper
   {
        @Test
        public void testMain() throws IOException
        {
            String output = getMethodOutput("main");
            String expect = "Passengers remaining : 12\n";
            boolean passed = getResults(expect, output, "Expected output from main");
            assertTrue(passed);
        }

       @Test
       public void test2() throws IOException
       {
           String target1 = "3 + 5 - 1 + 8 -3";
           boolean passed1 = checkCodeContains("passenger calculation", target1);
          
           assertTrue(passed1);
       }
        
   }



Syntax Errors
---------------

Computers don't actually speak Java so we have to **compile** 
(translate) Java source files that we write into class files which is 
code that a computer can understand and run. In this e-book, the Java 
code is actually being sent to a Java server to compile and run, and the 
output is sent back to your browser to show on the same page. 

.. |Grace Hopper| raw:: html

   <a href="https://en.wikipedia.org/wiki/Grace_Hopper" target="_blank">Grace Hopper</a>
   
.. |Rubber duck debugging| raw:: html

   <a href="https://rubberduckdebugging.com/" target="_blank">Rubber duck debugging</a>
   
   
**Syntax errors** are reported to you by the compiler if your Java code is not correctly 
written. Examples of syntax errors are a semicolon ``;`` missing or if the code 
has a open curly brace ``{`` or open quote ``"``, but no close curly brace ``}`` or 
close quote ``"``. Informally, a syntax error is called a **bug**, and the process of 
removing errors is called **debugging**. An early computer science pioneer |Grace Hopper| 
documented a real bug, a moth that flew into a computer in 1947!

.. figure:: Figures/firstbug.jpg
    :width: 300px
    :figclass: align-center
    :alt: First Bug
    
    Figure 1: Grace Hopper’s log showing a real bug, 1947.


The compiler tries to make sense of your code, but if your code has **syntax errors**, 
you will see error messages displayed below the code. Compiler error messages will 
tell the line number that the compiler found the error and the type of error.  
The error messages are not always easy to understand and sometimes the actual 
error is before the line that the compiler says is the problem. 
Debugging can be frustrating but you will get better at it with practice! 

Let's practice debugging some code! 

|Exercise| **Check Your Understanding: Mixed up programs**


.. parsonsprob:: q1_2_2
   :numbered: left
   :adaptive:
   :noindent:

   The following has all the correct code to print out "Hi my friend!" when the code is run, 
   but the code is mixed up.  Drag the blocks from left to right and put them in the 
   correct order.  You can go back and look at the previous programs if you
   are having trouble understanding how to order the blocks.
   
   Click on the "Check" button to check your solution. 
   You will be told if any of the blocks are in the wrong order or if you need to 
   remove one or more blocks. 
   
   After three incorrect attempts you will be able to use 
   the "Help me" button to make the problem easier.
   -----
   public class HelloExample3
   {
   =====
      public static void main(String[] args)
      {
      =====
         System.out.println("Hi my friend!");
         =====
      }
      =====
   }
   
.. parsonsprob:: q1_2_3
   :numbered: left
   :adaptive:
   :noindent:

   The following has all the correct code to print out "Hi there!" when the code is run, 
   but the code is mixed up and contains some extra blocks with errors.  
   Drag the needed blocks from left to right and put them in the correct order, then check your solution.
   -----
   public class HelloExample4
   {
   =====
   public Class HelloExample4
   {                         #paired
   =====
      public static void main(String[] args)
      {
      =====
      public static void main()
      {                         #paired
      =====
         System.out.println("Hi there!");
         =====
         System.out.println("Hi there!") #paired
         =====
      }
      =====
   }
    

|CodingEx| **Coding Exercise: Compile Time Error 1**

Run the following code.  Look for an error message after the code.  This is called a **compile time error** because it is an error detected by the compiler.  

What is wrong?  Can you fix it?  The error message will tell you the line number that it thinks is 
causing the error (``Error1.java:5: error: unclosed string literal``).  Check line 5 to make sure that everything looks correct.  One good thing to check is that all ``{`` have a matching ``}`` and all ``(`` have a matching ``)`` and all starting ``"`` have a ending ``"`` as well. Try putting in the missing symbol and run again. This is called **debugging**.

.. activecode:: code1_2_8
   :language: java
   :autograde: unittest 
   :practice: T

   Fix the code below.
   ~~~~
   public class Error1
   {
      public static void main(String[] args)
      {
         System.out.println("Hi there!);
      }
   }
           
   ====
   import static org.junit.Assert.*;
   import org.junit.*;;
   import java.io.*;

   public class RunestoneTests extends CodeTestHelper
   {
        @Test
        public void testMain() throws IOException
        {
            String output = getMethodOutput("main");
            String expect = "Hi there!";
            boolean passed = getResults(expect, output, "Expected output from main");
            assertTrue(passed);
        }
   }


    
|CodingEx| **Coding Exercise: Compile Time Error 2**


Try and run the following code.  
Look for an error message after the code. What is wrong this time?  Can you fix it?  
One good thing to check is that all ``{`` have a matching ``}`` and all ``(`` have a matching ``)`` and all starting ``"`` have a ending ``"`` as well.

.. activecode:: code1_2_9
   :language: java
   :autograde: unittest 
   :practice: T

   Fix the code below.
   ~~~~
   public class Error2
   {
      public static void main(String[] args)
      {
         System.out.println("Hi there!";
      }
   }
           
   ====
   // should pass if/when they run code
   import static org.junit.Assert.*;
   import org.junit.*;;
   import java.io.*;

   public class RunestoneTests extends CodeTestHelper
   {
        @Test
        public void testMain() throws IOException
        {
            String output = getMethodOutput("main");
            String expect = "Hi there!";
            boolean passed = getResults(expect, output, "Expected output from main");
            assertTrue(passed);
        }
   }

    
    
|CodingEx| **Coding Exercise: Compile Time Error 3**

Try and run the following code.  
What is wrong this time?  Can you fix it?  After you fix the first error, you may 
encounter a 2nd error! Fix that one too! 

.. activecode:: code1_2_10
   :language: java
   :autograde: unittest 
   :practice: T

   Fix the code below.
   ~~~~    
   public class Error3
   {
      public static void main(String[] args)
      {
         system.out.println("Hi there!")
      }
   }
           
   ====
   // should pass if/when they run code
   // This doesn't really work because it filters out the \n
   import static org.junit.Assert.*;
   import org.junit.*;;
   import java.io.*;

   public class RunestoneTests extends CodeTestHelper
   {
        @Test
        public void testMain() throws IOException
        {
            String output = getMethodOutput("main");
            String expect = "Hi there!";
            boolean passed = getResults(expect, output, "Expected output from main");
            assertTrue(passed);
        }
   }


Did you remember that System is capitalized in System.out.println? Did you find the missing semicolon? 
   
   

|Groupwork| Debugging Challenge
-----------------------------------

.. activecode:: code1_2_11
   :language: java
   :autograde: unittest 
   :practice: T

   Debug the following code. 
   Can you find all the bugs and get the code to run? 
   ~~~~
   public class Challenge1
   {
      public static void main(String[] args)
      {
         System.out.print("Good morning! ")
         system.out.print("Good afternoon!);
         System.Print " And good evening!";
      }
   }
           
   ====
   // should pass if/when they run code
   import static org.junit.Assert.*;
   import org.junit.*;;
   import java.io.*;

   public class RunestoneTests extends CodeTestHelper
   {
        @Test
        public void testMain() throws IOException
        {
            String output = getMethodOutput("main");
            String expect = "Good morning! Good afternoon! And good evening";
            boolean passed = getResults(expect, output, "Expected output from main");
            assertTrue(passed);
        }
   }

Comments
--------

Adding comments to your code helps to make it more readable and maintainable. 
In the commercial world, software development is usually a team effort where many 
programmers will use your code and maintain it for years. Commenting is essential in this kind of 
environment and a good habit to develop. Comments will also help you to remember what you 
were doing when you look back to your code a month or a year from now.

There are 3 types of comments in Java:

1. ``//`` Single line comment
2. ``/*`` Multiline comment ``*/``
3. ``/**`` Documentation comment ``*/``

In Java and many text-based coding languages, ``//`` is used to mark the beginning of a comment. 
Everything on the line that
follows the ``//`` is ignored by the compiler. 
For multi-line comments, use ``/*`` to start the comment and ``*/`` to end the comment. 
There is also a special version of the multi-line comment, ``/**``  ``*/``, called the documentation comment. 
Java has a cool tool called |javadoc| that will pull out all of these 
comments to make documentation of a class as a web page.  

The compiler will skip over comments. However, it is a good idea to use comments 
to make notes to yourself and other programmers working with you. Here is an example of commenting:

.. code-block:: java 

    /* MyClass.java
       Programmer: My Name
       Date: 
    */   
    
    int max = 10; // this keeps track of the max score
    

|Exercise| **Check your understanding**

.. dragndrop:: q1_2_4
    :feedback: Review the section above.
    :match_1: single-line comment|||//
    :match_2: multi-line comment|||/* */
    :match_3: Java documentation comment|||/** */
    
    Drag the definition from the left and drop it on the correct symbols on the right.  Click the "Check Me" button to see if you are correct.
    
The compiler will skip over comments, and they don't affect how your program runs. 
They are for you and other programmers working with you.  


Summary
-------------------

- A basic Java program looks like the following:

.. code-block:: java 

   public class MyClass
   {
      public static void main(String[] args)
      {
         System.out.println("Hi there!");
      }
   }
   
   
- A Java program starts with **public class NameOfClass { }**. If you are using your own files for your code, each class should be in a separate file that matches the class name inside it, for example NameOfClass.java.

- Most Java classes have a main method that will be run automatically. It looks like this: **public static void main(String[] args) { }**.

- The **System.out.print()** and **System.out.println()** methods display information given inside the parentheses on the computer monitor. 

- System.out.println moves the cursor to a new line after the information has been displayed, while System.out.print does not.

- A **string literal** is enclosed in double quotes ('' '').

- Java command lines end in ; (semicolon). { } are used to enclose blocks of code. ``//`` and ``/* */`` are used for comments.

- A **compiler** translates Java code into a class file that can be run on your computer. **Compiler or syntax errors** are reported to you by the compiler if the Java code is not correctly written. Some things to check for are ; at end of command lines, matching { }, (), and "". 


