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
we'll learn more about classes and objects later in the semester. Inside the class, 
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

Open ``E01HelloExample.java`` in the ``module1`` package of the exercises repository in Eclipse that you loaded on the first day of class. Run this program by finding it in the File explorer, right-clicking it, then selecting ``Run As -> Java Application`` from the menu. 
``System.out.println("Hi there!");`` prints out the characters between the first ``"`` and the 
second ``"`` followed by a new line.  
The ``"Hi there!"`` is called a **string literal**, and it can have zero to many characters 
enclosed in starting and ending double quotes. 
Then, 
change the code  to print your name.  
Be sure to keep the starting ``"`` and ending ``"``.  
Run the modified code to test your changes.

Next, open the ``E02PoemExample.java`` file and run it. Then change the code to add two more lines to the poem: “Java is interesting,” followed by “And so are you!”. Run your code to make sure that it works.

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

Open and run ``E03HelloExample2.java`` to see the output. 
   How would you change it to print the ! on the same line as Hi there 
   keeping all 3 print statements?

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

Run ``E04CalculationExample.java`` to see the output. 
   Can you change the last print statement to print the sum of the values from 1 to 10?


   Run ``E05CalculationErrorPrint`` to see the output.  The output is not correct.  
   The second System.out.println statement should print the value resulting from the computation, not a literal string for the computation. 
   Get rid of the double quotes in the second println statement and run the program.
   
   Open the ``E06CalculateBillTotal.java`` file. Assume you have some bills to pay.  The individual bill amounts are 89.50, 14.75, 45.12, and 92.50.  
   Add another print statement to sum and print the total bill amount on a separate line.  Don't just add the numbers in
   your head and print the result. You must write the code to add up the numbers and print the result.


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

Open the ``E07Error1.java`` file and look for an error.  This is called a **compile time error** because it is an error detected by the compiler.  

What is wrong?  Can you fix it?  One good thing to check is that all ``{`` have a matching ``}`` and all ``(`` have a matching ``)`` and all starting ``"`` have a ending ``"`` as well. Try putting in the missing symbol and run again. This is called **debugging**.
    
|CodingEx| **Coding Exercise: Compile Time Error 2**


Open the ``E08Error2.java`` file. What is wrong this time?  Can you fix it?  
One good thing to check is that all ``{`` have a matching ``}`` and all ``(`` have a matching ``)`` and all starting ``"`` have a ending ``"`` as well. 
    
|CodingEx| **Coding Exercise: Compile Time Error 3**


Open the ``E09Error3.java`` file. What is wrong this time?  Can you fix it?  After you fix the first error, you may 
encounter a 2nd error! Fix that one too! 

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


