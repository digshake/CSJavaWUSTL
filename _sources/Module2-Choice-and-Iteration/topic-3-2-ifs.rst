.. qnum::
   :prefix: 3-2-
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
    

If Statements and Control Flow
===============================

..	index::
	single: conditional
	single: if
	pair: conditional; if


The statements in a Java main method normally run or execute one at a time in the order they are found.   
**If statements** (also called **conditionals** or **selection**) change the flow of control so that certain lines of code only run when something is true.  
An **if statement** checks a boolean condition that is either true or false.  A block of statements will execute if the condition is true and will be skipped if the condition is false. 


.. figure:: Figures/Condition.png
    :width: 200px
    :align: center
    :figclass: align-center

    Figure 1: The order that statements execute in a conditional


A conditional uses the keyword ``if`` followed by **Boolean expression** inside of  an 
open parenthesis ``(`` and a close parenthesis ``)`` and then followed by a single statement or block of statements.  
The single statement or block of statements are only executed if the condition is true.  
The open curly brace ``{`` and a close curly brace ``}`` are used to group a block of statements together.  
It is recommended to always put in the curly braces even if you have just one statement under the if statement. 


.. raw:: html

  <table >
  <tr >
  <th style="padding-right: 6em;">1 statement </th>
  <th style="padding-right: 6em;">1 statement </th>
  <th style="padding-right: 6em;">2+ statements </th>
  </tr>

  <tr style="margin-bottom:2em; border-bottom: 1px dashed black">
  <th >{} optional </th>
  <th >{} optional </th>
  <th >{} required </th>
  </tr>

  <tr>
  </tr>
  <tr >
  <td>if (x<10)</td>
  <td>if (x<10)</td>
  <td>if (x<10)</td>
  </tr>

  <tr>
  <td>&nbsp;&nbsp;&nbsp;count++;</td>
  <td>{</td>
  <td>{</td>
  </tr>

  <tr>
  <td> </td>
  <td>&nbsp;&nbsp;&nbsp;count++;</td>
  <td>&nbsp;&nbsp;&nbsp;count++;</td>
  </tr>

  <tr>
  <td> </td>
  <td>}</td>
  <td>&nbsp;&nbsp;&nbsp;System.out.println(count);</td>
  </tr>

  <tr>
  <td> </td>
  <td> </td>
  <td>}</td>
  </tr>


  </table>

.. note::

    Note that there is no semicolon (;) at the end of the boolean expression in an if statement even if it is the end of that line. The semicolon goes at the end of the whole if statement, often on the next line. Or { } are used to mark the beginning and end of the block of code under the if condition. 
    
Imagine that your cell phone wanted to remind you to take an umbrella if it was currently raining in your area when it detected that you were leaving the house.  This type of thing is going to become more common in the future and it is an area of research called Human Computer Interaction (HCI) or Ubiquitous Computing (computers are everywhere).  

Examine the code in the ``E01TestRaining`` program. Play with the ``isRaining`` variable and make sure you understand what is happening.
  
You can test for a false value using the ``!`` operator, which is read as "not".  We will see a better way to test for both
true and false in the next lesson.  However, the code below shows how to print different messages based on whether a value is true or false.

   
   The ``E02TestMidterm`` program reads in a boolean value from standard input and tests whether the value is true ``if (passedExam)`` or false ``if (!passedExam)``.  
   Use the debugger to step through the program.   Change the value in the standard input window to test the program with each possible boolean value.
   

.. note::

    In an ``if statement``, it is good style to indent the lines of code nested between the curly braces.
 

|Exercise| **Check your understanding**


.. mchoice:: q3_2_1
   :practice: T
   :answer_a: Because x < 2 is always true
   :answer_b: Because there is a semicolon ; at the end of the condition "if (x < 2) ;"
   :answer_c: Because Java makes a random decision
   :correct: b
   :feedback_a: Incorrect, 3 < 2 is always false so the print statement should never execute 
   :feedback_b: Correct.  Get rid of the ; at the end of the condition "if (x < 2) " 
   :feedback_c: Incorrect, 3 < 2 is always false so the print statement should never execute
   
   Consider the following code segment. Why does it always print "ERROR"?
   
   .. code-block:: java

     int x = 3;
     if (x < 2) ;
     {
         System.out.println("ERROR");
     }
     
  


Relational Operators in If Statements
---------------------------------------

Most if statements have a boolean condition that uses relational operators like ==, !=, <, >, <=, >=, as we saw in the last lesson. 


|CodingEx| **Coding Exercise**
   
   Run the ``E03TestNumbers`` program a couple times until you see all the possible outputs. It prints out whether a random number is positive or equal to 0. Add another if statement that tests if it is a negative number.
   
.. note::

    A common mistake in if statements is using = instead of == in the condition by mistake. You should always **use ==**, not =, in the condition of an if statement to test a variable. One equal sign (=) assigns a value to a variable, and two equal signs (==) test if a variable has a certain value.
    
|Exercise| **Check your understanding**

.. mchoice:: q3_2_2
   :practice: T
   :answer_a: 3
   :answer_b: 6
   :answer_c: 0
   :answer_d: 4
   :answer_e: The code will not compile
   :correct: c
   :feedback_a: x is changed by the if statements.
   :feedback_b: What happens when x is greater than 2 and then greater than 4? Do both if statements.  
   :feedback_c: If x is greater than 2, it's always doubled, and then that result is always greater than 4, so it's set to 0 in the second if statement.  
   :feedback_d: x is changed by the if statements.
   :feedback_e: This code will compile.

   Consider the following code segment. What is printed as a result of executing the code segment?
   
   .. code-block:: java

     int x = 3;
     if (x > 2) 
     {
         x = x * 2;
     }
     if (x > 4) 
     {
        x = 0;
     }
     System.out.print(x);
     

.. More practice with if == and < > Active code.
    Note always use == not = in an if statement! Test not assign.

        
Conditional Control Flow
-------------------------------------

Recall the program to compute the number of pizza slices per person from Module 1.  
 

   Run the ``E04PizzaCalculatorInput`` program to confirm that it fails when a value of 0 is entered for numPeople (second input value). 
 

To avoid division by 0, the calculation for ``slicesPerPerson`` and ``leftoverSlices`` should be skipped when the number of people is 0.  
In fact, the calculation is nonsense if the number of people is a negative number so the program should check if a positive value is read from input.   
The program should actually ensure positive values are input for both the number of people and number of pizza slices, but for now you will only test the number of people.
You will see how to test compound boolean expressions in a later lesson. 

.. figure:: Figures/flow_3.png
    :width: 350px
    :align: center
    :figclass: align-center

    Figure 2: Conditional Control Flow

The flowchart in Figure 2 demonstrates the desired control flow based on an ``if`` statement, represented with a diamond symbol.
If the condition ``numPeople > 0`` is true, the process follows the path labelled **true**, which contains the 4 steps to calculate and 
print ``slicesPerPerson`` and ``leftoverSlices``.  
The 4 statements along the ``true`` branch must be nested within curly braces in a Java program otherwise only the first step would be considered part of the true branch.   
If the condition ``numPeople > 0`` is false, the **false** branch is followed and the 4 statements for calculating and printing are skipped.

   
   Update the ``E04PizzaCalculatorInput`` program based on the conditional control flow shown in Figure 2.  Add an if statement to test the value stored in numPeople.
   Don't forget curly braces around the 4 lines for computing and printing slicesPerPerson and leftoverSlices.

   Run the program multiple times with negative, 0, and positive values for number of people.  The program should no longer result in a divide by zero exception.  
   
   
Common Errors with If Statements
---------------------------------

Here are some rules to follow to avoid common errors:

- Always use curly brackets ``{`` and ``}`` to enclose the block of statements under the if condition. Java doesn't care if you indent the code -- it goes by the { }. 

- Don't put in a semicolon ``;`` after the first line of the if statement, if (test);. The if statement is a multiline block of code that starts with the if condition and then { the body of the if statement }. 

- Always use **==**, not =, in the condition of an if statement to test a variable. One = assigns, two == tests!


|CodingEx| **Coding Exercise**


   The ``E05TestCold`` program doesn't work as expected. It has 2 errors. 
   Run the program with input true, then change the input to false and run again.
   Even when the input is false, the program still prints both messages.
   Fix it to only print both "Wear a coat" and "Wear gloves" when isCold is true.
   Nothing should print when isCold is false.
   

Summary
-------------------  

- if statements test a boolean expression and if it is true, go on to execute the following statement or block of statements surrounded by curly brackets { } like below.

.. code-block:: java

    // A block if statement    
    if (boolean expression)
    {
       Do Statement1;
       Do Statement2;
       ...
       Do StatementN;
    }

- Java boolean expressions can compare primitive values and reference values with the relational operators == and != and arithmetic expression values with the relational operators (i.e., <, >, <=, >=).

- Conditional (if) statements affect the flow of control by executing different statements based on the value of a Boolean expression.


