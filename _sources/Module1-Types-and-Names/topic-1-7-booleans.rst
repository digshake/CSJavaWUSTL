.. qnum::
   :prefix: 3-1-
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
	single: Boolean
	pair: Variable; boolean
	pair: boolean; variable


Boolean Expressions
===================


**Boolean** variables or expressions can only have **true** or **false** values.  

Testing Equality (==)
----------------------

Primitive values like ints and reference values like Strings can be compared 
using the operators == and != (not equal) to return boolean values.   
The expression ``x == 4`` evaluates to
``true`` if the memory location for variable x currently stores the value 4, otherwise the expression is ``false``.
Note that ``x == 4`` does not assign a value to variable x, rather it simply compares the value of x to 4.


.. note::

    The operator `=` changes the value of a variable. The operator `==` tests if a variable holds a certain value, without changing its value!

|CodingEx| **Coding Exercise**


   What will the ``E01Equality`` program print out? 
   Try to guess before you run it! 
   Note that 1 equal sign (=) is used for assigning a value 
   and 2 equal signs (==) for testing equality between values.  The != operator tests for inequality.
  
   
Relational Operators (<, >)
----------------------------

The **Relational Operators** below in Java are used to compare numeric values or arithmetic expressions. Although some programming languages allow using relational operators like < to compare strings, Java only uses these operators for numbers, and uses the string methods compareTo() and equals() for comparing String values.

- < Less Than
- > Greater Than
- <= Less than or equal to
- >= Greater than or equal to
- == Equals
- != Does not equal

With <= and >=, remember to write the two symbols in the order that you would say them "less than" followed by "or equal to". 

|CodingEx| **Coding Exercise**

   
   Try to guess what the ``E02RelationalOperators`` program will print out before you run it.  
  

|Exercise| **Check your understanding**

.. dragndrop:: q3_1_1
    :feedback: Review the relational operators above.
    :match_1: x > 0|||x is positive
    :match_2: x == y|||x equals y
    :match_3: x < 0|||x is negative
    :match_4: x != y|||x does not equal y
    :match_5: x < y |||x is less than y
    :match_6: x > y |||x is greater than y
    :match_7: x >= y |||x is greater than or equal to y
    
    Drag the boolean expression from the left and drop it on what it is testing on the right.  Click the "Check Me" button to see if you are correct.
 



Testing with mod (%)
---------------------

Here are some boolean expressions that are very useful in coding:

.. code-block:: java 

  // Test if a number is positive
  (number > 0)
  //Test if a number is negative
  (number < 0)
  //Test if a number is even by seeing if the remainder is 0 when divided by 2 
  (number % 2 == 0)
  //Test if a number is odd by seeing if there is a remainder when divided by 2
  (number % 2 > 0)
  //Test if a number is a multiple of x (or divisible by x with no remainder)
  (number % x == 0)
  
  



   
Open the ``E03BooleanMod`` program. Try the expressions containing the % operator below to see how they can be used to check for even or odd numbers. All even numbers are divisible (with no remainder) by 2.
   
The **modulo** operator has a lot of great uses:
    
-  Use it to check for odd or even numbers ``(num % 2 == 1) is odd`` and ``(num % 2 == 0) is even``.  Actually, you can use it to check if any number is evenly divisible by another (``num1 % num2 == 0``)

-  Use it to get the last digit from an integer number (``num % 10 = last digit on right``).  

-  Use it to get the number of minutes left when you convert to hours (``num % 60``).  

- Use it whenever you have limited storage and you need to wrap around to the front if the value goes over the limit (``num % limit``).


Negation ! 
---------------------

You can use the ``!`` operator to negate 
the value of a Boolean expression.  When you see ``!``, think of the word "not".  

   
   Try to guess what the ``BooleanExpressions`` program will print out before you run it.  
  



|Exercise| **Check your understanding**

.. mchoice:: q3_1_2
   :answer_a: true
   :answer_b: false
   :correct: a
   :feedback_a: Correct.  !false == true 
   :feedback_b: Incorrect.  !false == true   

   What is printed?

   .. code-block:: java 

        boolean isHappy = false;
        System.out.println( !isHappy );



.. mchoice:: q3_1_3
   :answer_a: true
   :answer_b: false
   :correct: b
   :feedback_a: Incorrect.  5 > 10 is false 
   :feedback_b: Correct.  5 > 10 is false

   What is printed?

   .. code-block:: java 

        int num1 = 5;
        int num2 = 10;
        boolean isGt =  num1 > num2;
        System.out.println( isGt );
 
    
Summary
-------------------  


- Primitive values and reference values can be compared using relational operators (i.e., == and !=) in Java.
- Arithmetic expression values can be compared using relational operators (i.e., <, >, <=, >=) in Java.
- An expression involving relational operators evaluates to a Boolean value of true or false.


