.. qnum::
   :prefix: 1-6-
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
    
    
Casting and Ranges of Variables
===============================

In Java, **type casting** is used to convert variables from one type to another. By **casting** we don't mean something to do with fishing, but it is a similar idea to casting a pot in clay.  In Java when you cast you are changing the "shape" (or type) of the variable.

.. figure:: Figures/casting.jpg
    :width: 300px
    :figclass: align-center
    
    Figure 1: Casting a pot in clay. 


The casting operators (int) and (double) are used right next to a number or variable to create a temporary value converted to a different data type. For example,  ``(double) 1/3`` will give a double result instead of an int one. Run this code to find how Java handles division and what casting can do to the results. Notice what happens when you divide an int by an int or an int by a double or an int casted to a double divided by an int.


   
   Open the ``E01OperatorTest`` program. What happens when you divide an int by an int or with a double operand or with the type cast (double) on one of the operands?
   	
Java assumes that if you are doing division with integers that you want an integer result and it will truncate and throw away the part after the decimal point.  But, if you use a mixture of integers (int) and decimal (double) numbers Java will assume that you want a double result. If there is at least one double in the operation, Java will widen the type of the other operand to double too and return the result in a double. If you have integers and you want a double result from some mathematical operation **cast** one of the integers to a double using (double) as shown above.  

Values of type double can be rounded to the nearest integer by adding or subtracting .5 and 
casting with (int) using formulas like the following. 

.. note::  

   int nearestInt = (int)(number + 0.5); 
   
   int nearestNegInt = (int)(negNumber – 0.5);


For example, if you divide 5/3 using integer division, Java will truncate 1.67 to 1 to give an int result. However, we usually round up any answer .5 and above. Using the formula above, if we add 1.67 + 0.50, we get 2.17 and then casting it to an int throws away what's after the decimal point, just leaving 2.  


   
   Run the ``E02NearestInt`` program to see how the formula of adding or subtracting .5 and then casting with (int) rounds a positive or negative double number to the closest int.


..	index::
	pair: double; number of digits


What happens to repeating decimal numbers like 3.333333...?  Java limits the number of digits you can save for any ``double`` number to about 14-15 digits. You should be aware that the accuracy of any calculation on a computer is limited by the fact that computers can only hold a limited number of digits. 

For example, int values are stored in 4 bytes of memory. There is an Integer.MAX_VALUE defined as 2147483647 and an Integer.MIN_VALUE defined as -2147483648. If you try to store any number larger or smaller than these numbers in an int variable, it will result in an error called **integer overflow**. Try it below.

   
   Try the ``E03TestOverflow`` program to see two integer overflow errors for a positive and negative number. An int cannot hold that many digits! Fix the integer overflow error by deleting the last 0 in the numbers.
  
..	index::
	pair: double; precision format
   

|Exercise| **Check your understanding**

.. mchoice:: q1_6_1
   :practice: T
   :answer_a: true
   :answer_b: false
   :correct: b
   :feedback_a: Did you try this out in Active Code?  Does it work that way?
   :feedback_b: Java throws away any values after the decimal point if you do integer division.  It does not round up automatically.  

   True or false: Java rounds up automatically when you do integer division.  
   
.. mchoice:: q1_6_2
   :practice: T
   :answer_a: true
   :answer_b: false
   :correct: b
   :feedback_a: Try casting to int instead of double.  What does that do?  
   :feedback_b: Casting results in the type that you cast to. However, if you can't really cast the value to the specified type then you will get an error.  

   True or false: casting always results in a double type.  
   
.. mchoice:: q1_6_3
   :practice: T
   :answer_a: (double) (total / 3);
   :answer_b: total / 3;
   :answer_c: (double) total /  3;
   :correct: c
   :feedback_a: This does integer division before casting the result to double so it loses the fractional part.  
   :feedback_b: When you divide an integer by an integer you get an integer result and lose the fractional part.
   :feedback_c: This will convert total to a double value and then divide by 3 to return a double result.

   Which of the following returns the correct average for a total that is the sum of 3 int values?
   

Summary
-------------------

- **Type casting** is used to convert variables from one type to another.
- The casting operators (int) and (double) can be used to create a temporary value converted to a different data type.
- Casting a double value to an int causes the digits to the right of the decimal point to be truncated (cut off and thrown away).

- Some programming code causes int values to be automatically cast (widened) to double values.
- Values of type double can be rounded to the nearest integer by (int)(x + 0.5) or (int)(x – 0.5) for negative numbers.

- Integer values in Java are represented by values of type int, which are stored using a finite amount (4 bytes) of memory. Therefore, an int value must be in the range from Integer.MIN_VALUE to Integer.MAX_VALUE inclusive.

- If an expression would evaluate to an int value outside of the allowed range, an integer overflow occurs. This could result in an incorrect value within the allowed range.
