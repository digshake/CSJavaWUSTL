.. qnum::
   :prefix: 3-5-
   :start: 1
   
.. highlight:: java
   :linenothreshold: 4
   
   
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
    
Compound Boolean Expressions
============================

..	index::
	single: and
	single: or
	single: truth table
	pair: logical; and
	pair: logical; or
	pair: conditional; complex

And (&&), Or (||), and Not (!)
--------------------------------

What if you want two things to be true before the body of the conditional is executed?  Use ``&&`` as a logical **and** to join 
two Boolean expressions and the body of the condition will only be executed  if both are true.  

|CodingEx| **Coding Exercise**


   What if you want to go out and your parents say you can go out if you clean your room and do your homework?  Run the ``E01Chores`` program and try different values for ``cleanedRoom`` and ``didHomework`` and see what they have to be for it to print ``You can go out``.
  
What if it is okay if only one of two things is true? Use ``||`` as a logical **or** to join two Boolean expressions and the body of the condition will be executed if one or both are true.  

|CodingEx| **Coding Exercise**


   For example, your parents might say you can go out if you can walk or they don't need the car.  Open the ``E02Transportation`` program. Try different values for ``walking`` and ``carIsAvailable`` and see what the values have to be to print ``You can go out``.
  

.. note::

    In English, we often use an exclusive-or like in the sentence "do you want to be player 1 *or* player 2?" where you can't be both player 1 and player 2. In programming, the or-operator is an inclusive-or which means that the whole expression is true if either one or the other or *both* conditions are true. 
    
With numerical values, the or-operator is often used to check for error conditions on different ends of the number line, while the and-operator is often used to see if a number is in an range. 

|CodingEx| **Coding Exercise**

   
   Explore how && and || are used with numbers in the ``E03ScoreRange`` program. Try different values for score like -10 and 110 in the code below.
   



The **not** (!) operator can be used to negate a boolean value. We've seen ! before in != (not equal).  
In Java, ! has precedence (is executed before) &&, and && has precedence over ||. Parentheses can be used to 
force the order of execution in a different way. If you mix ! with && and ||, be careful because the results are 
often the opposite of what you think. We'll see examples of this in the next lesson.  

|CodingEx| **Coding Exercise**
      
   The ``E04Homework`` program says if homework is not done, you can't go out. Try different values for ``homeworkDone``.
  

.. note::

    In Java, ! will be executed before &&, and && will be executed before ||, unless there are parentheses. Anything inside parentheses is executed first.
 

Truth Tables
------------

The following table (also called a **truth table**) shows the result for P && Q when P and Q are both expressions that can be true or false. An expression involving logical operators like (P && Q) evaluates to a Boolean value, true or false. As you can see below the result of P && Q is only true if both P and Q are true.  

+-------+-------+-----------+
| P     | Q     | P && Q    |
+=======+=======+===========+
|true   |true   |true       |
+-------+-------+-----------+
|false  |true   |false      |
+-------+-------+-----------+
|true   |false  |?          |
+-------+-------+-----------+
|false  |false  |false      |
+-------+-------+-----------+

|Exercise| **Check your understanding**

.. fillintheblank:: q3_5_1

   The truth table above is missing one result.  What is the result of P && Q when ``P=true`` and ``Q=false``?  

   -    :^false$: Correct.  Both values must be true for && to return true.
        :.*: Try it and see
 
The following table shows the result for P || Q when P and Q are both expressions that can be true or false.  As you can see below the result of P || Q is true if either P or Q is true.  It is also true when both of them are true.

+-------+-------+-----------+
| P     | Q     | P || Q    |
+=======+=======+===========+
|true   |true   |true       |
+-------+-------+-----------+
|false  |true   |?          |
+-------+-------+-----------+
|true   |false  |true       |
+-------+-------+-----------+
|false  |false  |false      |
+-------+-------+-----------+

|Exercise| **Check your understanding**

.. fillintheblank:: q3_5_2

   The truth table above is missing one result.  What is the result of ``P || Q`` when ``P=false`` and ``Q=true``? 

   -    :^true$: Correct.  Only one of the two has to be true with || so this will print true.
        :.*: Try it and see
 
        

|Exercise| **Check your understanding**


.. mchoice:: q3_5_3
   :practice: T
   :answer_a: first case
   :answer_b: second case
   :correct: a
   :feedback_a: first case will print if both of the conditions are true and they are.  
   :feedback_b: second case will print either of the conditions are false. 

   What is printed when the following code executes and x has been set to 3 and y has been set to 9?  
   
   .. code-block:: java 

     if (x > 0 && (y / x) == 3) {
        System.out.println("first case");
     } else {
        System.out.println("second case");
     }
     
     
.. mchoice:: q3_5_4
   :practice: T
   :answer_a: first case
   :answer_b: second case
   :correct: b
   :feedback_a: first case will print if both of the conditions are true, but the second is not. 
   :feedback_b: second case will print if either of the conditions are false and the second one is (6 / 3 == 2).

   What is printed when the following code executes and x has been set to 3 and y has been set to 6?  
   
   .. code-block:: java 

     if (x > 0 && (y / x) == 3) {
        System.out.println("first case");
     } else {
        System.out.println("second case");
     }
     
.. mchoice:: q3_5_5
   :practice: T
   :answer_a: first case
   :answer_b: second case
   :correct: a
   :feedback_a: first case will print if either of the two conditions are true.  The first condition is true, even though the second one isn't.
   :feedback_b: second case will print if both of the conditions are false, but the first condition is true.   

   What is printed when the following code executes and x has been set to 3 and y has been set to 6?  Notice that it is now an **or** (||) instead of and.
   
   .. code-block:: java 

     if (x > 0 || (y / x) == 3) {
        System.out.println("first case");
     } else {
        System.out.println("second case");
     }
     
Short Circuit Evaluation
------------------------

..	index::
	single: short circuit evaluation
	pair: conditional; short circuit evaluation
  
Both ``&&`` and ``||`` use **short circuit evaluation**.  That means that the second condition isn't necessarily checked if the result from the first condition is enough to tell if the result is true or false.   In a complex conditional with a logical and (``&&``) both conditions must be true, so if the first is false, then the second doesn't have to be evaluated.  If the complex conditional uses a logical or (``||``) and the first condition is true, then the second condition won't be executed, since only one of the conditions needs to be true.    

.. note::

   In a complex conditional using a logical and (``&&``) the evaluation will short circuit (not execute the second condition) if the first condition is false.  In a complex conditional using a logical or (``||``) the evaluation will short circuit if the first condition is true.  
 
|Exercise| **Check your understanding**

.. mchoice:: q3_5_6
   :practice: T
   :answer_a: first case
   :answer_b: second case
   :answer_c: You will get a error because you can't divide by zero.  
   :correct: b
   :feedback_a: first case will only print if x is greater than 0 and it is not.  
   :feedback_b: second case will print if x is less than or equal to zero or if y divided by x is not equal to 3.  
   :feedback_c: Since the first condition is false when x is equal to zero the second condition won't execute.  Execution moves to the else.    

   What is printed when the following code executes and x has been set to 0 and y to 3?  
   
   .. code-block:: java

     if (x > 0 && (y / x) == 3) {
        System.out.println("first case");
     } else {
        System.out.println("second case");
     }
     
.. mchoice:: q3_5_7
   :practice: T
   :answer_a: first case
   :answer_b: second case
   :answer_c: You will get a error because you can't divide by zero.  
   :correct: a
   :feedback_a: Since x is equal to zero the first expression in the complex conditional will be true and the (y / x) == 3 won't be evaluated, so it won't cause a divide by zero error.  It will print "first case".
   :feedback_b: Since x is equal to zero the first part of the complex conditional is true so it will print first case.
   :feedback_c: You won't get an error because of short circuit evaluation.  The (y / x) == 3 won't be evaluated since the first expression is true and an or is used.  

   What is printed when the following code executes and x has been set to zero and y is set to 3?  
   
   .. code-block:: java 

     if (x == 0 || (y / x) == 3) {
        System.out.println("first case");
     } else {
        System.out.println("second case");
     }

.. mchoice:: q3_5_8
   :practice: T
   :answer_a: first case
   :answer_b: second case
   :answer_c: You will get a error because you can't divide by zero.  
   :correct: c
   :feedback_a: Since (y / x) == 3 is the first expression it is executed, and x is 0 causing a divide by zero error. 
   :feedback_b: Since (y / x) == 3 is the first expression it is executed, and x is 0 causing a divide by zero error. 
   :feedback_c: Correct. Since (y / x) == 3 is the first expression it is executed, and x is 0 causing a divide by zero error.  

   What is printed when the following code executes and x has been set to zero and y is set to 3?  
   
   .. code-block:: java 

     if ((y / x) == 3 || x == 0 ) {
        System.out.println("first case");
     } else {
        System.out.println("second case");
     }
     
.. .. mchoice:: q3_5_9
   :practice: T
   :answer_a: first case
   :answer_b: second case
   :answer_c: You will get a error because you can't use a negative index with substring.   
   :correct: b
   :feedback_a: Since x is negative the complex conditional will be false and the second condition won't execute. Remember that with <code>&&</code> both parts of the condition must be true for the complex conditional to be true.  Using a negative substring index won't cause an error since that code will only be executed if x is greater than or equal to zero.
   :feedback_b: Since x is negative the second part of the complex conditional won't even execute so the else will be executed.  
   :feedback_c: This would be true if it wasn't using short circuit evaluation, but it is.  
   
   What is printed when the following code executes and x has been set to negative 1?   
   
   .. code-block:: java 

     String message = "help";
     if (x >= 0 && message.substring(x).equals("help")) System.out.println("first case");
     else System.out.println("second case");
     


   
Summary
--------

- Logical operators !(not), &&(and), and ||(or) are used with Boolean values. 

- (A && B) is true if both A and B are true.

- (A || B) is true if either A or B (or both) are true.

- !(A) is true if A is false.

- In Java, ! has precedence (is executed before) && which has precedence over ||. Parentheses can be used to force the order of execution in a different way.

- When the result of a logical expression using && or || can be determined by evaluating only the first Boolean operand, the second is not evaluated. This is known as **short-circuit evaluation**.