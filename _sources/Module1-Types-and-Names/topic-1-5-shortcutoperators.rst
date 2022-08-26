.. qnum::
   :prefix: 1-5-
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

.. raw:: html

    <style>    td { text-align: left; } </style>
    
    
..	index::
	single: operators
	pair: math; operators
	pair: operators; addition
	pair: operators; subtraction
	pair: operators; multiplication
    pair: operators; division
    pair: operators; equality
    pair: operators; inequality

.. |ss| raw:: html

   <strike>

.. |se| raw:: html

   </strike>

.. |visualizer| raw:: html

   <a href="https://cscircles.cemc.uwaterloo.ca/java_visualize/">Java Visualizer</a>    

.. |cup| raw:: html

   <a href="https://cscircles.cemc.uwaterloo.ca/java_visualize/"><img width="20" title="Based on icons by Jacob Halton and Francesco Terzini of the Noun Project" src="../_static/cup.png">Java Visualizer</a>    


Compound Assignment Operators 
=============================

Compound assignment operators are shortcuts that do a math operation and assignment in one step. For example, ``x += 1`` adds 1 to x and assigns the sum to x. It is the same as ``x = x + 1``. This pattern is possible with any operator put in front of the = sign, as seen below.

+------------+------------+-----------+----------+----------+
|\+ shortcuts|\- shortcuts|\* shortcut|/ shortcut|% shortcut|
+============+============+===========+==========+==========+
|x = x + 1;  |x = x - 1;  |x = x * 2; |x = x / 2;|x = x % 2;|
+------------+------------+-----------+----------+----------+
|x += 1;     |x -= 1;     |x \*\= 2;  |x /= 2;   |x %= 2;   |
+------------+------------+-----------+----------+----------+
|x++;        |x\- \-;     |           |          |          |
+------------+------------+-----------+----------+----------+

The most common shortcut operator ``++``, the plus-plus or **increment** operator, is used to add 1 to the current value; ``x++`` is the same as ``x += 1`` and the same as ``x = x + 1``. It is a shortcut that is used a lot in loops. If you've heard of the programming language C++, the ++ in C++ is an inside joke that C has been incremented or improved to create C++. The ``--`` decrement operator is used to subtract 1 from the current value: ``y--`` is the same as ``y = y - 1``. These are the only two double operators; this shortcut pattern does not exist with other operators. Run the following code to see these shortcut operators in action!

|CodingEx| **Coding Exercise**

.. activecode:: code1_5_1
   :language: java
   :autograde: unittest    
  
   Run the code below to see what the ++ and shorcut operators do. 
   Use the Codelens to trace through the code and observe how the 
   variable values change. Try creating more compound assignment 
   statements with shortcut operators and guess what they would 
   print out before running the code.
   ~~~~
   public class Test2
   {
      public static void main(String[] args)
      {
        int score = 0;
        System.out.println(score);
        score++;
        System.out.println(score);
        score *= 2;
        System.out.println(score);
        int penalty = 5;
        score -= penalty/2;
        System.out.println(score);      
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
            String expect = "0\n1\n2\n0";

            boolean passed = getResults(expect, output, "Expected output from main",true);
            assertTrue(passed);
        }
    }

|Exercise| **Check Your Understanding**


.. mchoice:: q1_5_1
   :practice: T
   :answer_a: x = -1, y = 1, z = 4
   :answer_b: x = -1, y = 2, z = 3
   :answer_c: x = -1, y = 2, z = 2
   :answer_d: x = -1, y = 2, z = 2
   :answer_e: x = -1, y = 2, z = 4
   :correct: e
   :feedback_a: This code subtracts one from x, adds one to y, and then sets z to to the value in z plus the current value of y.
   :feedback_b: This code subtracts one from x, adds one to y, and then sets z to to the value in z plus the current value of y.
   :feedback_c: This code subtracts one from x, adds one to y, and then sets z to to the value in z plus the current value of y.
   :feedback_d: This code subtracts one from x, adds one to y, and then sets z to to the value in z plus the current value of y.
   :feedback_e: This code subtracts one from x, adds one to y, and then sets z to to the value in z plus the current value of y.

   What are the values of x, y, and z after the following code executes?
   
   .. code-block:: java 

     int x = 0;
     int y = 1;
     int z = 2;
     x--; 
     y++;
     z+=y;
     
.. mchoice:: q1_5_2
   :practice: T
   :answer_a: x = 6, y = 2.5, z = 2
   :answer_b: x = 4, y = 2.5, z = 2
   :answer_c: x = 6, y = 2, z = 3
   :answer_d: x = 4, y = 2.5, z = 3
   :answer_e: x = 4, y = 2, z = 3
   :correct: e
   :feedback_a: This code sets x to z * 2 (4), y to y divided by 2 (5 / 2 = 2) and z = to z + 1 (2 + 1 = 3).
   :feedback_b: This code sets x to z * 2 (4), y to y divided by 2 (5 / 2 = 2) and z = to z + 1 (2 + 1 = 3).
   :feedback_c: This code sets x to z * 2 (4), y to y divided by 2 (5 / 2 = 2) and z = to z + 1 (2 + 1 = 3).
   :feedback_d: This code sets x to z * 2 (4), y to y divided by 2 (5 / 2 = 2) and z = to z + 1 (2 + 1 = 3).
   :feedback_e: This code sets x to z * 2 (4), y to y divided by 2 (5 / 2 = 2) and z = to z + 1 (2 + 1 = 3).

   What are the values of x, y, and z after the following code executes?
   
   .. code-block:: java 

     int x = 3;
     int y = 5;
     int z = 2;
     x = z * 2;
     y /= 2;
     z++;
     
|Groupwork| Code Tracing Challenge and Operators Maze
-----------------------------------------------------

**Code Tracing** is a technique used to simulate by hand a dry run through the code or pseudocode 
as if you are the computer executing the code. Tracing can be used for 
debugging or proving that your program runs correctly or for figuring out what the code 
actually does. 

Trace tables can be used to track the values of variables as they change throughout a program. 
To trace through code, write down a variable in each column or row in a table and keep 
track of its value throughout the program. Some trace tables also keep track of the output 
and the line number you are currently tracing.

For example, given the following code:

.. code-block:: java 

    x = 10;
    y = 15;
    z = x * y;
    z++;
    x = z * 2;

The corresponding trace table looks like this:

+-----+-----------+-----+-----+-----+
|Line |Statement  |  x  |  y  |  z  |
+=====+===========+=====+=====+=====+
|1    |x = 10;    | 10  |     |     |
+-----+-----------+-----+-----+-----+
|2    |y = 15;    |     |  15 |     |
+-----+-----------+-----+-----+-----+
|3    |z = x * y; |     |     | 150 |
+-----+-----------+-----+-----+-----+
|4    |z++;       |     |     | 151 |
+-----+-----------+-----+-----+-----+
|5    |x = z * 2; | 302 |     |     |
+-----+-----------+-----+-----+-----+


Alternatively, we can show a compressed trace by listing the sequence of values 
assigned to each variable as the program executes.  You might want to cross off the previous value
when you assign a new value to a variable.  The last value listed is the variable's final value.

.. figure:: Figures/compressedtrace2.png
    :width: 400px
    :figclass: align-center
    :alt: Compressed Trace


Use paper and pencil to trace through the following program to determine the 
values of the variables at the end.   Be careful, ``%`` is the remainder operator, not division.

|Exercise| **Check Your Understanding**



.. fillintheblank:: q1_5_3
   
   .. code-block:: java 

        int x = 0;
        int y = 5;
        int z = 1;
        x++;
        y -= 3;
        z = x + z;
        x = y * z;
        y %= 2;  
        z--;

   The final value for x is |blank| 

   The final value for y is |blank|

   The final value for z is |blank|

   -    :4: Correct.    
        :.*: Incorrect, go back and retrace the code.
   -    :0: Correct.  
        :.*: Incorrect, go back and retrace the code. 
   -    :1: Correct.  
        :.*: Incorrect, go back and retrace the code. 
   

.. |Java visualizer| raw:: html

    <a href="https://cscircles.cemc.uwaterloo.ca/java_visualize/">Java visualizer</a>



.. |Operators Maze game| raw:: html

   <a href="https://docs.google.com/document/d/1ZjA8oKeo8FYx2nXX4OOq5lUihopIQQ_HY-eoE5yZkk8/edit?usp=sharing" target="_blank" style="text-decoration:underline">Operators Maze game</a>
   

Prefix versus Postfix Operator
------------------------------

.. activecode:: code1_5_2
   :language: java
   
   What do you think is printed when the following code is executed?    
   Try to guess the output before running the code.  You might be surprised at the result.  
   Click on CodeLens to step through the  execution.  
   Notice that the second println prints the original value 7 even though the memory  
   location for variable ``count`` is updated to the value 8.
   ~~~~  
    public class Postfix_Example {
        public static void main(String[] args) {
            int count = 7;
            System.out.println(count);
            System.out.println(count++);
            System.out.println(count);
        }
    }
   ====

The code ``System.out.println(count++)`` adds one to the variable *after* the value is printed.  
Try changing the code to ``++count`` and run it again. This will result in one being added to
the variable *before* its value is printed.
When the ``++`` operator is placed before the variable, it is called **prefix** increment. 
When it is placed after, it is called **postfix** increment.

+----------------------------+---------------------------------------------------------+-------+
|Example                     |Description                                              |Type   |
+============================+=========================================================+=======+
|System.out.println(count++);|Print the current value of count, then add one to count  |Postfix|
+----------------------------+---------------------------------------------------------+-------+
|System.out.println(++count);|Add one to count, then print the new value               |Prefix |
+----------------------------+---------------------------------------------------------+-------+
|x = y++;                    |Copy the value of y into x, then add one to y            |Postfix|
+----------------------------+---------------------------------------------------------+-------+
|x = ++y;                    |Add one to y, then copy the value of y into x            |Prefix |
+----------------------------+---------------------------------------------------------+-------+
|x = y- -;                   |Copy the value of y into x, then subtract one from y     |Postfix|
+----------------------------+---------------------------------------------------------+-------+
|x = - -y;                   |Subtract one from y, then copy the value of y into x     |Prefix |
+----------------------------+---------------------------------------------------------+-------+

|Exercise| **Check Your Understanding**

.. dragndrop:: q1_5_4
   :feedback: Try again.
   :match_1: System.out.println(score++);|||Print the value 5, then assign score the value 6.
   :match_2: System.out.println(score--);|||Print the value 5, then assign score the value 4.
   :match_3: System.out.println(++score);|||Assign score the value 6, then print the value 6.
   :match_4: System.out.println(--score);|||Assign score the value 4, then print the value 4.

   Assume score=5 and each line of code is executed independent of the others.  Match each line of code to the correct result (drag the code block to the matching result).  



.. note::

    When you are new to programming, it is advisable to avoid mixing unary operators ``++`` and ``--`` with assignment or 
    print statements. Try to perform the increment or decrement operation on a separate line of code 
    from assignment or printing.  
    
    For example, instead of writing ``x=y++;`` or ``System.out.println(z--);``
    the code below makes it clear that the increment of *y* happens after the 
    assignment to *x*, and that the value of *z* is printed before it is decremented.

    .. code-block:: java 

        x=y;
        y++;

        System.out.println(z);
        z--;


|Exercise| **Check Your Understanding**

.. dragndrop:: q1_5_5
   :feedback: Try again.
   :match_1: System.out.println(score++);|||System.out.println(score);   score++;
   :match_2: System.out.println(score--);|||System.out.println(score);   score--;
   :match_3: System.out.println(++score);|||score++;     System.out.println(score);   
   :match_4: System.out.println(--score);|||score--;     System.out.println(score);

   Match each single line of code on the left to the equivalent pair of lines on the right.


Summary
-------------------

- Compound assignment operators (+=, -=, \*=, /=, %=) can be used in place of the assignment operator.
- The increment operator (++) and decrement operator (--) are used to add 1 or subtract 1 from the stored value of a variable. The new value is assigned to the variable.




