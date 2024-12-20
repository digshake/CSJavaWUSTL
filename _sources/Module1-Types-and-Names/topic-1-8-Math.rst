.. qnum::
   :prefix: 2-9-
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

Using the Math Class
====================

..	index::
    single: Math methods
	single: random method
	pair: Math; random method

Games would be boring if the same thing happened each time you played the game.  Games often use random numbers
to generate different possibilities.  You need to know how to use the ``Math.random()`` method to generate a random number.

There are lots of mathematical methods
that you might want to use in your programs like ``Math.abs`` (absolute value).  These methods are in the **Math** class defined in the java.lang package. These are **static methods** which means you can call them by just using ``ClassName.methodName()`` without creating an object or just the method name if they are called from within the same class. 

.. note::

   **Static methods** (also called class methods) are called using the class name and the dot operator ``.`` followed by the method name, 
   for example ``Math.random()``. You do not need to create an object of the class to use them. 

The ``Math.random()`` method returns a number greater than or equal to 0.0, and less than 1.0. 


   Try out the ``E01Random`` program.  Run it several times to see what it prints each time.
 

   


You can use ``Math.random`` and a cast to integer to return a random integer between some starting and ending value.  The code below will create a random integer from 0 to 9. Remember that casting a double value to integer ``(int)`` will throw away any values after the decimal point.

|CodingEx| **Coding Exercise**

  

   Run the ``E02RandomRange`` program several times to see how the value changes each time. The program returns a random integer between 0 and 9, inclusive. 
   How could you change the code to return a random integer from 1 to 10, inclusive?  Modify the code and see if your answer is correct. 
  
  
.. note::

    - Math.random() returns a random number between 0.0-0.99. 
    
    - **(int)(Math.random()*range) + min** moves the random number into a range starting from a minimum number. 
    
    - The range is the **(max number - min number + 1)**. 
    
    
Here are some examples that move a random number into a specific range.

.. code-block:: java 

    // Math.random() returns a random number between 0.0-0.99.
    double rnd = Math.random();
    
    // rnd1 is an integer in the range 0-9 (including 9).
    int rnd1 = (int)(Math.random()*10);
   
    // rnd2 is in the range 1-10 (including 10). The parentheses are necessary!
    int rnd2 = (int)(Math.random()*10) + 1;
    
    // rnd3 is in the range 5-10 (including 10). The range is 10-5+1 = 6.
    int rnd3 = (int)(Math.random()*6) + 5;
    
    // rnd4 is in the range -10 up to 9 (including 9). The range is doubled (9 - -10 + 1 = 20) and the minimum is -10.
    int rnd4 = (int)(Math.random()*20) - 10;


|Exercise| **Check your understanding**

.. mchoice:: q2_9_1
   :practice: T
   :answer_a: Math.random() < 0.4
   :answer_b: Math.random() > 0.4
   :answer_c: Math.random() == 0.4
   :correct: a
   :feedback_a: This is true about 40% of the time since Math.random returns a value from 0 to not quite 1.
   :feedback_b: This will be true about 60% of the time. 
   :feedback_c: Do not use == with double values!  Remember that Math.random can return any number between 0 and not quite 1 (about .99999999).  

   Which of the following would be true about 40% of the time?
   
.. mchoice:: q2_9_2
   :practice: T
   :answer_a: ((int) (Math.random() * 5))
   :answer_b: ((int) (Math.random() * 6))
   :answer_c: ((int) (Math.random() * 5) + 1)
   :correct: c
   :feedback_a: This would be a number between 0 and 4. 
   :feedback_b: This would be a number between 0 and 5.
   :feedback_c: The first part would return a number between 0 and 4 and when you add 1 you get a number from 1 to 5 inclusive. 

   Which of the following would return a random number from 1 to 5 inclusive?
   
.. mchoice:: q2_9_3
   :practice: T
   :answer_a: ((int) (Math.random() * 10))
   :answer_b: ((int) (Math.random() * 11))
   :answer_c: ((int) (Math.random() * 10) + 1)
   :correct: b
   :feedback_a: This would be a number between 0 and 9.
   :feedback_b: This would be a number between 0 and 10.
   :feedback_c: The first part would return a number between 0 and 9 and when you add 1 you get a number from 1 to 10 inclusive. 

   Which of the following would return a random number from 0 to 10 inclusive?
   
.. mchoice:: q2_9_4
   :practice: T
   :answer_a: Math.random() < 0.25
   :answer_b: Math.random() > 0.25
   :answer_c: Math.random() == 0.25
   :correct: b
   :feedback_a: This is true about 25% of the time, since it will be a number from 0 to not quite 1.
   :feedback_b: This is true about 75% of the time, since it will be a number from 0 to not quite 1.
   :feedback_c: Do not use == with double values!  Remember that Math.random can return any number between 0 and not quite 1 (about .99999999).  

   Which of the following would be true about 75% of the time?

|Exercise| **Sample Problem**

.. mchoice:: q2_9_5
   :practice: T
   :answer_a: int rn = (int) (Math.random() * 25) + 36;
   :answer_b: int rn = (int) (Math.random() * 25) + 60;
   :answer_c: int rn = (int) (Math.random() * 26) + 60;
   :answer_d: int rn = (int) (Math.random() * 36) + 25;
   :answer_e: int rn = (int) (Math.random() * 60) + 25;
   :correct: d
   :feedback_a: Remember that (int)(Math.random()*range) + min moves the random number into a range starting from a minimum number. We want the minimum number to be 25, but the minimum number here would be 36. 
   :feedback_b: Remember that (int)(Math.random()*range) + min moves the random number into a range starting from a minimum number. We want the minimum number to be 25, but the minimum number here would be 60. 
   :feedback_c: Remember that (int)(Math.random()*range) + min moves the random number into a range starting from a minimum number. Here the min is 25. We want the minimum number to be 25, but the minimum number here would be 60. 
   :feedback_d: Yes, (int)(Math.random()*36) + 25 moves the random number into a range of 36 numbers starting from a minimum number 25 up to 60. The range is (max number - min number + 1) which is (60-25 +1) = 36.
   :feedback_e: This would give us random numbers from 25 to 85. Remember that you can compute the range you need with (max number - min number + 1).

   Which of the following statements assigns a random integer between 25 and 60, inclusive, to rn?
 
   
Other Math functions that you can use are:


- int abs(int) : Returns the absolute value of an int value (which is the value of a number without its sign, for example Math.abs(-4) = 4). 

- double abs(double) : Returns the absolute value of a double value.

- double pow(double, double) : Returns the value of the first parameter raised to the power of the second parameter.

- double sqrt(double) :  Returns the positive square root of a double value.

- double random() :  Returns a double value greater than or equal to 0.0 and less than 1.0 (not including 1.0!).
 

Summary
-------------------

- Static Math methods can be called using **Math**.method(); for each method.

- The following static Math methods are part of the Java Quick Reference:

  - **int abs(int)** : Returns the absolute value of an int value (which means no negatives).
  - **double abs(double)** : Returns the absolute value of a double value.
  - **double pow(double, double)** : Returns the value of the first parameter raised to the power of the second parameter. 
  - **double sqrt(double)** :  Returns the positive square root of a double value.
  - **double random()** :  Returns a double value greater than or equal to 0.0 and less than 1.0 (not including 1.0)!
  
- The values returned from Math.random can be manipulated to produce a random int or double in a defined range. 

- **(int)(Math.random()*range) + min** moves the random number into a range starting from a minimum number. The range is the **(max number - min number + 1)**. For example, to get a number in the range of 5 to 10, use the range 10-5+1 = 6 and the min number 5: (int)(Math.random()*6) + 5).


