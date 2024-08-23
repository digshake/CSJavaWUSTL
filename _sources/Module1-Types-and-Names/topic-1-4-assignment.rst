.. qnum::
   :prefix: 1-4-
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

.. |visualizer| raw:: html

   <a href="https://cscircles.cemc.uwaterloo.ca/java_visualize/">Java Visualizer</a>    
 
.. |cup| raw:: html

   <a href="https://cscircles.cemc.uwaterloo.ca/java_visualize/"><img width="20" title="Based on icons by Jacob Halton and Francesco Terzini of the Noun Project" src="../_static/cup.png">Java Visualizer</a>    

    
Expressions and Assignment Statements
=====================================

In this lesson, you will learn about assignment statements and expressions 
that contain math operators and variables. 

Assignment Statements
---------------------

Remember that a variable holds a value that can change or 
vary.  **Assignment statements** initialize or change the value stored 
in a variable using the assignment operator ``=``.  An assignment statement always has a 
single variable on the left hand side of the = sign. The **value of the 
expression**  on the right hand side of 
the = sign (which can contain math operators and other variables) is copied 
into the memory location of the variable on the left hand side.

.. figure:: Figures/assignment.png
    :width: 300px
    :figclass: align-center
    :alt: Assignment statement
    
    Figure 1: Assignment Statement (variable = expression)

Instead of saying equals for the ``=`` operator in an assignment statement, 
say “gets” or “is assigned” to 
remember that the variable on the left hand side gets or is assigned the value on the right. 
In the figure above, score is assigned the value of 10 times points 
(which is another variable) plus 5.

The following video by Dr. Colleen Lewis shows how variables can change values in 
memory using assignment statements.

.. youtube:: MZwIgM__5C8
    :width: 700
    :align: center


As we saw in the video, 
we can set one variable to a copy of the value of another variable like y = x;. 
This won’t change the value of the variable that you are copying from.

|CodingEx| **Coding Exercise:** 

Run the code in the ``E01VariableAssignment`` class and see how the values of the variables change.
   
   The ``E02CalculateMoney`` program is supposed to figure out the total money value given the number of dimes, quarters and nickels.
   There is an error in the calculation of the total.  Fix the error to compute the correct amount.

  
   
   The ``E03SalaryExample`` program is supposed to calculate and print the total pay given the weekly salary and the number of weeks worked.  
   Use
   string concatenation with the totalPay variable to produce the output ``Total Pay = $3000``.
   Don't hardcode the number 3000 in your print statement.
  
|Exercise| **Check your understanding**
   

.. |codeq| image:: Figures/assignmentq.png
    :align: middle
    

.. fillintheblank:: q1_4_1

   |codeq|
   The code above shows the variable state in memory after line 9 is executed. What is printed when line 10 is executed?

   -    :12: Correct.
        :.*: num3 - num1 = 19 - 7 = 12 
  

Incrementing the value of a variable
------------------------------------

If you use a variable to keep score you would probably increment it 
(add one to the current value) whenever score should go up.  
You can do this by setting the variable to the current value of the 
variable plus one (score = score + 1) as shown below. The formula 
looks a little crazy in math class, but it makes sense in coding 
because the variable on the left is set to the value of the arithmetic 
expression on the right. So, the score variable is set to the 
previous value of score + 1.


|CodingEx| **Coding Exercise:** 

Run the code in ``UpdateScore`` and see how the score value changes.

   
|Exercise| **Check your understanding**

.. mchoice:: q1_4_4
   :practice: T
   :answer_a: b = 5
   :answer_b: b = 2
   :answer_c: b = 7
   :answer_d: b = 10
   :correct: d
   :feedback_a: It sets the value for the variable on the left to the value from evaluating the right side.  What is 5 * 2?
   :feedback_b: It sets the value for the variable on the left to the value from evaluating the right side.  What is 5 * 2?
   :feedback_c: It sets the value for the variable on the left to the value from evaluating the right side.  What is 5 * 2?
   :feedback_d: Correct. 5 * 2 is 10. 

   What is the value of b after the following code executes?  

   .. code-block:: java 

       int b = 5;
       b = b * 2;



.. mchoice:: q1_4_5
   :practice: T
   :answer_a: x = 0, y = 1, z = 2
   :answer_b: x = 1, y = 2, z = 3
   :answer_c: x = 2, y = 2, z = 3
   :answer_d: x = 1, y = 0, z = 3
   :correct: b
   :feedback_a: These are the initial values in the variable, but the values are changed.
   :feedback_b: x changes to y's initial value, y's value is doubled, and z is set to 3
   :feedback_c: Remember that the equal sign doesn't mean that the two sides are equal.  It sets the value for the variable on the left to the value from evaluating the right side.
   :feedback_d: Remember that the equal sign doesn't mean that the two sides are equal.  It sets the value for the variable on the left to the value from evaluating the right side.

   What are the values of x, y, and z after the following code executes?  

   .. code-block:: java 

       int x = 0;
       int y = 1;
       int z = 2;
       x = y;
       y = y * 2;
       z = 3;






Operators
---------


..	index::
	single: operators
	pair: math; operators
	pair: operators; addition
	pair: operators; subtraction
	pair: operators; multiplication
    pair: operators; division
    pair: operators; equality
    pair: operators; inequality

Java uses the standard mathematical operators for addition (``+``), subtraction (``-``), multiplication (``*``), and division (``/``). Arithmetic expressions can be of type int or double. An arithmetic operation that uses two int values will evaluate to an int value. An arithmetic operation that uses at least one double value will evaluate to a double value.  (You may have noticed that + was also used to put text together in the input program above -- more on this when we talk about strings.)

Java uses the operator ``==`` to test if the value on the left is equal to the value on the right and ``!=`` to test if two items are not equal.   Don't get one equal sign ``=`` confused with two equal signs ``==``! They mean different things in Java. One equal sign is used to assign a value to a variable. Two equal signs are used to test a variable to see if it is a certain value and that returns true or false as you'll see below.  Use == and != only with int values and not doubles because double values are an approximation and 3.3333 will not equal 3.3334 even though they are very close.

|CodingEx| **Coding Exercise:** 
    
Run the code in ``E05OperatorExample`` to see all the operators in action. Do all of those operators do what you expected?  What about ``2 / 3``? Isn't surprising that it prints ``0``?  See the note below.

.. note::

   When Java sees you doing integer division (or any operation with integers) it assumes you want an integer result so it throws away anything after the decimal point in the answer, essentially rounding down the answer to a whole number. If you need a double answer, you should make at least one of the values in the expression a double like 2.0.

   
With division, another thing to watch out for is dividing by 0. An attempt to divide an integer by zero will result in an **ArithmeticException** error message. Try it in one of the active code windows above.

Operators can be used to create compound expressions with more than one operator. You can either use a literal value which is a fixed value like 2, or variables in them.  When compound expressions are evaluated, **operator precedence** rules are used, so that \*, /, and % are done before + and -. However, anything in parentheses is done first. It doesn't hurt to put in extra parentheses if you are unsure as to what will be done first.  

|CodingEx| **Coding Exercise:** 

Open the ``E06TestCompound.java`` file, try to guess what it will print out and then run it to see if you are right. Remember to consider **operator precedence**.

|Exercise| **Check Your Understanding**

.. mchoice:: q1_4_6
   :practice: T
   :answer_a: 0.666666666666667
   :answer_b: 9.0
   :answer_c: 10.0
   :answer_d: 11.5
   :answer_e: 14.0
   :correct: c
   :feedback_a: Don't forget that division and multiplication will be done first due to operator precedence. 
   :feedback_b: Don't forget that division and multiplication will be done first due to operator precedence.
   :feedback_c: Yes, this is equivalent to (5 + ((a/b)*c) - 1).   
   :feedback_d: Don't forget that division and multiplication will be done first due to operator precedence, and that an int/int gives an int result where it is rounded down to the nearest int.
   :feedback_e: Don't forget that division and multiplication will be done first due to operator precedence.
   
   Consider the following code segment.  Be careful about integer division.
   
   .. code-block:: java 
   
       int a = 5;
       int b = 2;
       double c = 3.0;
       System.out.println(5 + a / b * c - 1);
   
   What is printed when the code segment is executed?
   

.. mchoice:: q1_4_7
   :practice: T
   :answer_a: 5.5
   :answer_b: 5
   :answer_c: 6
   :answer_d: 5.0
   :correct: b
   :feedback_a: Dividing an integer by an integer results in an integer
   :feedback_b: Correct. Dividing an integer by an integer results in an integer
   :feedback_c: The value 5.5 will be rounded down to 5  
   :feedback_d: Dividing an integer by an integer results in an integer
    
   Consider the following code segment. 

   .. code-block:: java 
   
        (7 + 5 + 6 + 4) / 4 
   
   What is the value of the expression?


.. mchoice:: q1_4_8
   :practice: T
   :answer_a: 5.5
   :answer_b: 5
   :answer_c: 6
   :answer_d: 5.0
   :correct: a
   :feedback_a: Correct. Dividing a double by an integer results in a double
   :feedback_b: Dividing a double by an integer results in a double
   :feedback_c: Dividing a double by an integer results in a double
   :feedback_d: Dividing a double by an integer results in a double
    
   Consider the following code segment. 
   
   .. code-block:: java 
   
        (7 + 5.0 + 6 + 4) / 4 
   
   What is the value of the expression?

.. mchoice:: q1_4_9
   :practice: T
   :answer_a: 5.5
   :answer_b: 5
   :answer_c: 6
   :answer_d: 5.0
   :correct: a
   :feedback_a: Correct. Dividing an integer by an double results in a double
   :feedback_b: Dividing an integer by an double results in a double
   :feedback_c: Dividing an integer by an double results in a double
   :feedback_d: Dividing an integer by an double results in a double
    
   Consider the following code segment. 
   
   .. code-block:: java 
   
        (7 + 5 + 6 + 4) / 4.0
   
   What is the value of the expression?


   
The Modulo Operator
--------------------

The percent sign operator (``%``) is the **mod (modulo)** or **remainder** operator.  The mod operator (``x % y``) returns the remainder after you divide ``x`` (first number) by ``y`` (second number) so ``5 % 2`` will return 1 since 2 goes into 5 two times with a remainder of 1.  Remember long division when you had to specify how many times one number went into another evenly and the remainder?  That remainder is what is returned by the modulo operator.

.. figure:: Figures/mod-py.png
    :width: 150px
    :align: center
    :figclass: align-center
    
    Figure 2: Long division showing the whole number result and the remainder
    
.. youtube:: jp-T9lFISlI
    :width: 700
    :align: center

|CodingEx| **Coding Exercise:** 

    
   
   In ``E07ModExample`` program, try to guess what it will print out and then run it to see if you are right.
   


.. note::
   The result of ``x % y`` when ``x`` is smaller than ``y`` is always ``x``.  The value ``y`` can't go into ``x`` at all (goes in 0 times), since ``x`` is smaller than ``y``, so the result is just ``x``.  So if you see ``2 % 3`` the result is ``2``.  
  
..	index::
	single: modulo
	single: remainder
	pair: operators; modulo
	
|Exercise| **Check Your Understanding**
	
.. mchoice:: q1_4_10
   :practice: T
   :answer_a: 15
   :answer_b: 16
   :answer_c: 8
   :correct: c
   :feedback_a: This would be the result of 158 divided by 10.  modulo gives you the remainder.
   :feedback_b: modulo gives you the remainder after the division.
   :feedback_c: When you divide 158 by 10 you get a remainder of 8.  

   What is the result of 158 % 10?
   
.. mchoice:: q1_4_11
   :practice: T
   :answer_a: 3
   :answer_b: 2
   :answer_c: 8
   :correct: a
   :feedback_a: 8 goes into 3 no times so the remainder is 3.  The remainder of a smaller number divided by a larger number is always the smaller number!
   :feedback_b: This would be the remainder if the question was 8 % 3 but here we are asking for the reminder after we divide 3 by 8.
   :feedback_c: What is the remainder after you divide 3 by 8?  

   What is the result of 3 % 8?



FlowCharting
--------------


Assume you have 16 pieces of pizza and 5 people.  If everyone gets the same number of slices, how many slices does each person get?  Are there any leftover pieces?  

In industry, a **flowchart** is used to describe a process through symbols and text.  
A flowchart usually does not show variable declarations, but it can show assignment statements (drawn as rectangle) and output statements (drawn as rhomboid). 

The flowchart in figure 3 shows a process to compute the fair distribution of pizza slices among a number of people. 
The process relies on integer division to determine slices per person, and the mod operator to determine remaining slices.



.. figure:: Figures/flow_1.png
    :figclass: align-center
    :width: 300px
    :alt: Flow Chart
    
    Figure 3: Example Flow Chart

.. note::  

  A flowchart shows pseudo-code, which is like Java but not exactly the same.  Syntactic details like semi-colons are omitted, and input and output is described in abstract terms. 


|CodingEx| **Coding Exercise:** 
 
 
   
   Complete the program ``E08PizzaCalculator`` based on the process shown in the Figure 3 flowchart.  Note the first line of code declares all 4 variables as type int.
   Add assignment statements and print statements to compute and print the slices per person and leftover slices.    Use System.out.println for output.

Storing User Input in Variables
---------------------------------

.. |repl JavaIOExample| raw:: html

   <a href="https://repl.it/@BerylHoffman/JavaIOExample" target="_blank">repl JavaIOExample</a>


Variables are a powerful abstraction in programming because the same algorithm can be 
used with different input values saved in variables.  

.. figure:: Figures/iostream.png
    :figclass: align-center
    :alt: Program input and output
    
    Figure 4: Program input and output


A Java program can ask the user to type in one or more values.   
The Java class ``Scanner`` is used to read from
the keyboard input stream, which is referenced by ``System.in``. Normally the keyboard input is typed into a console window, but since this is running
in a browser you will type in a small textbox window displayed below the code. 
The code ``String name = scan.nextLine()`` 
gets the string value you enter as program input and then stores the value in a variable.  

|CodingEx| **Coding Exercise:** 


Run the ``E09NameReader`` program a few times, typing in a different name. The code works for any name: 
behold, the power of variables!



.. .. raw:: html

..    <iframe height="500px" width="100%" style="max-width:90%; margin-left:5%"  src="https://repl.it/@BerylHoffman/JavaIOExample?lite=true" scrolling="no" frameborder="no" allowtransparency="true" allowfullscreen="true" sandbox="allow-forms allow-pointer-lock allow-popups allow-same-origin allow-scripts allow-modals"></iframe>
    


The Scanner class has several useful methods for reading user input.  A token is a sequence of characters separated by white space.

.. table:: 
  :align: left
  :widths: auto

  =========================  ================================================
  Method                           Description             
  =========================  ================================================
  nextLine()                 Scans all input up to the line break as a String     
  next()                     Scans the next token of the input as a String    
  nextInt()                  Scans the next token of the input as an int                    
  nextDouble()               Scans the next token of the input as a double                      
  nextBoolean()              Scans the next token of the input as a boolean                     
  =========================  ================================================


|CodingEx| **Coding Exercise:** 

   
   Run the ``E10AgeReader`` program to read in an integer from the input stream. 
   You can type a different integer value in the input window shown below the code.




A rhomboid (slanted rectangle) is used in a flowchart to depict data flowing into and out of a program.  
The previous flowchart in Figure 3 used a rhomboid to indicate program output.  A rhomboid is
also used to denote reading a value from the input stream.  

.. figure:: Figures/flow_2.png
    :figclass: align-center
    :width: 300px
    :alt: Flow Chart
    
    Figure 5: Flow Chart Reading User Input

Figure 5 contains an updated version of the pizza calculator process.  
The first two steps have been altered to initialize the pizzaSlices and numPeople variables by reading two values from the input stream.
In Java this will be done using a Scanner object and reading from System.in.

   
   Complete the ``E11PizzaCalculatorInput`` program based on the process shown in the Figure 5 flowchart.  
   The program should scan two integer values to initialize pizzaSlices and numPeople.  Run the program a few times to experiment with different values for input.
   What happens if you enter 0 for the number of people?  The program will bomb due to division by zero! We will see how to prevent this in a later lesson.  
  


|CodingEx| **Coding Exercise:** 

The ``E12SumInput`` program reads two integer values from the input stream and attempts to print the sum.  Unfortunately there is a problem
with the last line of code that prints the sum.  
  
   Run the program and look at the result. When the input is ``5`` and ``7``, the output is ``Sum is 57``. 
   Both of the ``+`` operators in the print statement are performing string concatenation.  
   While the first ``+`` operator 
   should perform string concatenation, the second ``+`` operator should perform addition.   
   You can force the second ``+`` operator to perform addition by putting the arithmetic expression in parentheses ``( num1 + num2 )``.  
   

More information on using the Scanner class can be found here https://www.w3schools.com/java/java_user_input.asp 


Summary
-------------------

- Arithmetic expressions include expressions of type int and double.

- The arithmetic operators consist of +, -, \* , /, and % (modulo for the remainder in division).

- An arithmetic operation that uses two int values will evaluate to an int value. With integer division, any decimal part in the result will be thrown away, essentially rounding down the answer to a whole number.

- An arithmetic operation that uses at least one double value will evaluate to a double value.

- Operators can be used to construct compound expressions.

- During evaluation, operands are associated with operators according to **operator precedence** to determine how they are grouped. (\*, /, % have precedence over + and -, unless parentheses are used to group those.)

- An attempt to divide an integer by zero will result in an ArithmeticException to occur. 

- The assignment operator (=) allows a program to initialize or change the value stored in a variable.  The value of the expression on the right is stored in the variable on the left.

- During execution, expressions are evaluated to produce a single value.

- The value of an expression has a type based on the evaluation of the expression.


