.. qnum::
   :prefix: 3-11-
   :start: 1

   
Multiple Choice Exercises
=================================

Easier Multiple Choice Questions
----------------------------------

.. mchoice:: q3_11_1
   :practice: T
   :answer_a: x is negative
   :answer_b: x is zero
   :answer_c: x is positive
   :correct: c
   :feedback_a: This will only print if x has been set to a number less than zero. Has it? 
   :feedback_b: This will only print if x has been set to 0.  Has it?
   :feedback_c: The first condition is false and x is not equal to zero so the else will execute.  

   What does the following code print when x has been set to 187?
   
   .. code-block:: java 

     if (x < 0) {
        System.out.println("x is negative");
     }
     else if (x == 0) {
         System.out.println("x is zero"); 
     }
     else {
         System.out.println("x is positive");
     }
      
.. mchoice:: q3_11_2
   :practice: T
   :answer_a: first case
   :answer_b: second case 
   :correct: b
   :feedback_a: This will print if x is greater than or equal 3 and y is less than or equal 2.  In this case x is greater than 3 so the first condition is true, but the second condition is false.
   :feedback_b: This will print if x is less than 3 or y is greater than 2.  

   What is printed when the following code executes and x equals 4 and y equals 3?   
   
   .. code-block:: java 

     if (!(x < 3 || y > 2)) {
        System.out.println("first case");
		
     } else {
        System.out.println("second case");
	 }


.. mchoice:: q3_11_4
   :practice: T
   :answer_a: first case
   :answer_b: second case
   :answer_c: You will get a error because you can't divide by zero.  
   :correct: c
   :feedback_a: This will print if either of the two conditions are true.  The first isn't true but the second will cause an error.
   :feedback_b: This will print if both of the conditions are false.  But, an error will occur when testing the second condition.   
   :feedback_c: The first condition will be false so the second one will be executed and lead to an error since you can't divide by zero.

   What is printed when the following code executes and x has been set to zero and y is set to 3?  
   
   .. code-block:: java 

     if (x > 0 || (y / x) == 3) {
        System.out.println("first case");
     } else { 
        System.out.println("second case");
	 }

.. mchoice:: q4_9_1
   :practice: T
   :answer_a: 5 6 7 8 9
   :answer_b: 4 5 6 7 8 9 10 11 12 
   :answer_c: 3 5 7 9 11
   :answer_d: 3 4 5 6 7 8 9 10 11 12
   :correct: d
   :feedback_a: What is i set to in the initialization area? 
   :feedback_b: What is i set to in the initialization area? 
   :feedback_c: This loop changes i by 1 each time in the change area.  
   :feedback_d: The value of i starts at 3 and this loop will execute until i equals 12.  The last time through the loop the value of i is 12 at the begininng and then it will be incremented to 13 which stops the loop since 13 is not less than or equal to 12.  

   What does the following code print?
   
   .. code-block:: java 

     for (int i = 3; i <= 12; i++) {  
        System.out.print(i + " ");
     }


.. mchoice:: q4_9_2
   :practice: T
   :answer_a: 9
   :answer_b: 7
   :answer_c: 6
   :answer_d: 10
   :correct: c
   :feedback_a: This would be true if i started at 0.
   :feedback_b: Note that it stops when i is 9.    
   :feedback_c: Since i starts at 3 and the last time through the loop it is 8 the loop executes 8 - 3 + 1 times = 6 times.
   :feedback_d: This would be true if i started at 0 and ended when i was 10.  Does it?

   How many times does the following method print a ``*``?  
   
   .. code-block:: java 

     for (int i = 3; i < 9; i++) {  
        System.out.print("*"); 
     }


.. mchoice:: q4_9_3
   :practice: T
   :answer_a: 5 4 3 2 1
   :answer_b: -5 -4 -3 -2 -1
   :answer_c: -4 -3 -2 -1 0
   :correct: c
   :feedback_a: x is initialized (set) to -5 to start. 
   :feedback_b: x is incremented (x++) before the print statement executes.
   :feedback_c: x is set to -5 to start but then incremented by 1 so it first prints -4.

   What does the following code print?
   
   .. code-block:: java 

     int x = -5;
     while (x < 0) { 
        x++; 
        System.out.print(x + " ");
     }

 
.. mchoice:: q4_9_4
   :practice: T
   :answer_a: 7
   :answer_b: 8
   :answer_c: 12
   :answer_d: 13
   :correct: b
   :feedback_a: This would be true if it stopped when i was 12, but it loops when i is 12.
   :feedback_b: Note that it stops when i is 13 so 13 - 5 is 8.   
   :feedback_c: This would be true if i started at 1.  
   :feedback_d: This would be true if i started at 0.  

   How many times does the following method print a ``*``?  
   
   .. code-block:: java 

     for (int i = 5; i <= 12; i++) {  
        System.out.print("*"); 
     }

    
.. mchoice:: q4_9_5
   :practice: T
   :answer_a: 4
   :answer_b: 5
   :answer_c: 6
   :correct: a
   :feedback_a: The loop starts with i = 1 and loops as long as it is less than 5 so i is 1, 2, 3, 4.  
   :feedback_b: This would be true if the condition was i <= 5.  
   :feedback_c: This would be true if i started at 0 and ended when it reached 6 (i <= 5). 

   How many times does the following method print a ``*``?  
   
   .. code-block:: java 

     for (int i = 1; i < 5; i++) {  
        System.out.print("*"); 
     }


.. mchoice:: q4_9_6
   :practice: T
   :answer_a: 7
   :answer_b: 8
   :answer_c: 9
   :correct: c
   :feedback_a: This would be true if i started at 1 and ended when it reached 8.  
   :feedback_b: This would be true if the loop ended when i reached 8. 
   :feedback_c: This loop starts with i = 0 and continues till it reaches 9 so (9 - 0 = 9).  

   How many times does the following method print a ``*``?  
   
   .. code-block:: java 

     for (int i = 0; i <= 8; i++) {  
        System.out.print("*"); 
     }


.. mchoice:: q4_9_7
   :practice: T
   :answer_a: 4
   :answer_b: 5
   :answer_c: 6
   :correct: b
   :feedback_a: This would be true if x started at 1 instead of 0.   
   :feedback_b: The loop starts with x = 0 and ends when it reaches 5 so 5 - 0 = 5.  
   :feedback_c: This would be true if the condition was x <= 5 instead of x = 5.

   How many times does the following method print a ``*``?  
   
   .. code-block:: java 

     for (int x = 0; x < 5; x++) {  
        System.out.print("*"); 
     }


.. mchoice:: q4_9_8
   :practice: T
   :answer_a: 6
   :answer_b: 7
   :answer_c: 8
   :correct: a
   :feedback_a: This loop starts with x = 2 and continues while it is less than 8 so 8 - 2 = 6.  
   :feedback_b: This would be true if the loop ended when x was 9 instead of 8 (x <= 8).  
   :feedback_c: This would be true if the loop started with x = 0.

   How many times does the following method print a ``*``?  
   
   .. code-block:: java 

     for (int x = 2; x < 8; x++) {  
        System.out.print("*"); 
     }


.. mchoice:: q4_9_9
   :practice: T
   :answer_a: 1 2 3 4 
   :answer_b: 1 2 3 4 5
   :answer_c: 0 1 2 3 4
   :answer_d: 0 1 2 3 4 5
   :correct: d
   :feedback_a: This would be true if x started at 1 and ended when x was 5. 
   :feedback_b: This would be true if x started at 1.
   :feedback_c: This would be true if the loop ended when x was 5.
   :feedback_d: This loop starts with x = 0 and ends when it reaches 6.  

   What does the following code print?
   
   .. code-block:: java 

     int x = 0;
     while (x <= 5) { 
        System.out.print(x + " ");
        x++;
     }


.. mchoice:: q4_9_10
   :practice: T
   :answer_a: 3 4 5 6 7 8 
   :answer_b: 3 4 5 6 7 8 9
   :answer_c: 0 1 2 3 4 5 6 7 8
   :answer_d: 0 1 2 3 4 5 6 7 8 9
   :answer_e: It is an infinite loop 
   :correct: e
   :feedback_a: Notice that x isn't changed in the loop.
   :feedback_b: Notice that x isn't changed in the loop.
   :feedback_c: Notice that x isn't changed in the loop.
   :feedback_d: Notice that x isn't changed in the loop.
   :feedback_e: Since x is never changed in the loop this is an infinite loop.  

   What does the following code print?
   
   .. code-block:: java 

     int x = 3;
     while (x < 9) { 
        System.out.print(x + " ");
     }



Medium Multiple Choice Questions
----------------------------------


.. mchoice:: q3_11_5
   :practice: T
   :answer_a: (!c) && (!d)
   :answer_b: (c || d)
   :answer_c: (c && d)
   :answer_d: !(c && d)
   :answer_e: (!c) || (!d)
   :correct: a
   :feedback_a: NOTing (negating) an OR expression is the same as the AND of the individual values NOTed (negated). See DeMorgans laws.
   :feedback_b: NOTing an OR expression does not result in the same values ORed.  
   :feedback_c: You do negate the OR to AND, but you also need to negate the values of c and d. 
   :feedback_d: This would be equivalent to (!c || !d)
   :feedback_e: This would be equivalent to !(c && d)

   Which of the following expressions is equivalent to !(c || d) ?  
   

 .. mchoice:: q4_9_11
   :practice: T
   :answer_a: 10
   :answer_b: 5
   :answer_c: 25
   :answer_d: 50
   :answer_e: 15
   :correct: c
   :feedback_a: The second loop executes 5 times for each of the 5 times the first loop executes, so the answer should be 5 * 5.
   :feedback_b: The second loop executes 5 times for each of the 5 times the first loop executes, so the answer should be 5 * 5. 
   :feedback_c: The first loop will execute 5 times, and for each time through, the second loop will execute 5 times. So the answer is the number of times through the first loop times the number of times through the second.  
   :feedback_d: The second loop executes 5 times for each of the 5 times the first loop executes, so the answer should be 5 * 5.
   :feedback_e: The second loop executes 5 times for each of the 5 times the first loop executes, so the answer should be 5 * 5.

   How many stars are output when the following code is executed?  
   
   .. code-block:: java

     for (int i = 0; i < 5; i++) {
        for (int j = 0; j < 5; j++) {
           System.out.println("*");
		}
     }


.. mchoice:: q4_9_12
   :practice: T
   :answer_a: I
   :answer_b: II
   :answer_c: III
   :answer_d: IV
   :answer_e: V
   :correct: a
   :feedback_a: This will loop with i changing from 1 to 5 and then for each i, j will loop from i to 0 printing the value of i and then a new line.
   :feedback_b: This will loop i from 0 to 4 and j from 0 to i, neglecting to ouput 5.
   :feedback_c: This will loop with i changing from 1 to 4 and j from i to 0. 
   :feedback_d: This will loop with i changing from 1 to 5 and j from 0 to i but it will print each value on a different line.
   :feedback_e: This will loop with i changing from 0 to 4 and j from 0 to i.  

   Which of the following code segments will produce the displayed output?  
   
   .. code-block:: java

     1
     22
     333
     4444
     55555


     I.   for (int i = 1; i <= 5; i++) {
             for (int j = i; j > 0; j--) {
                System.out.print(i);
             }
             System.out.println();
          }

     II.  for (int i = 0; i < 5; i++) {
             for (int j = 0; j < i; j++) {
                System.out.print(i);
             }
             System.out.println();
          }

     III. for (int i = 1; i < 5; i++) {
             for (int j = i; j > 0; j--) {
                System.out.print(i);
             }
             System.out.println();
          }

     IV.  for (int i = 1; i < 6; i++) {
             for (int j = 0; j < i; j++) {
                System.out.println(i);
             }
          }

     V.   for (int i = 0; i < 5; i++) {
             for (int j = 0; j < i; j++) {
                System.out.print(i+1);
             }
             System.out.println();
          }


.. mchoice:: q4_9_13
   :practice: T
   :answer_a: 0 2 4 6 8 10 12 14 16 18
   :answer_b: 4 16
   :answer_c: 0 6 12 18
   :answer_d: 1 4 7 10 13 16 19
   :answer_e: 4 10 16
   :correct: e
   :feedback_a: This would be correct if we were printing out all of the values of k, not just the ones that have a remainder of 1 when divided by 3.
   :feedback_b: This is missing the value 10 (10 divided by 3 does have a remainder of 1).
   :feedback_c: None of these answers have a remainder of 1 when divided by 3.
   :feedback_d: This answer would be correct if k was incremented by 1 instead of 2. K will be 0, 2, 4, 6, 8, 10, 12, 14, 16, 18 in this loop.
   :feedback_e: This will loop with k having a value of 0 to 18 (it will stop when k = 20). It will print out the value of k followed by a space when the remainder of dividing k by 3 is 1.

   What is printed as a result of the following code segment?  
   
   .. code-block:: java

     for (int k = 0; k < 20; k+=2) {
        if (k % 3 == 1) {
           System.out.print(k + " ");
		}
     }


.. mchoice:: q4_9_14
   :practice: T
   :answer_a: I
   :answer_b: II
   :answer_c: III
   :answer_d: IV
   :answer_e: V
   :correct: a
   :feedback_a: This will loop with j from 1 to 5 and k from 5 to j and print out the value of j and a space. So the first time through the loop it will print 1 five times and the next time it will print out 2 four times and so on.
   :feedback_b: This will print out each value from 1 to 5 five times.
   :feedback_c: This will loop with j from 1 to 5 and k from 1 times.
   :feedback_d: This will loop j from 1 to 5 and k from 1 to 5, printing each number 5 times.
   :feedback_e: This loops with j from 1 to 5 and k from j to 5 and prints out the value of k, printing 1 through 5 on the first line, 2 through 5 on the next, and so on.

   Which of the following code segments will produce the displayed output?  
   
   .. code-block:: java

     11111
     2222
     333
     44
     5


     I.   for (int j = 1; j <= 5; j++) {
             for (int k = 5; k >= j; k--) {
                System.out.print(j + " ");
             }
             System.out.println();
          }

     II.  for (int j = 1; j <= 5; j++) {
             for (int k = 5; k >= 1; k--) {
                System.out.print(j + " ");
             }
             System.out.println();
          }

     III. for (int j = 1; j <= 5; j++) {
             for (int k = 1; k <= j; k++) {
                System.out.print(j + " ");
             }
             System.out.println();
          }

     IV.  for (int j = 1; j <= 5; j++) {
             for (int k = 1; k <= 5; k++) {
                System.out.println(j + " ");
             }
          }

     V.   for (int j = 1; j <= 5; j++) {
             for (int k = j; k <= 5; k++) {
                System.out.print(k + " ");
             }
             System.out.println();
          }


.. mchoice:: q4_9_15
   :practice: T
   :answer_a: var1 = 0, var2 = 2
   :answer_b: var1 = 1, var2 = 1
   :answer_c: var1 = 3, var2 = -1
   :answer_d: var1 = 2, var2 = 0
   :answer_e: The loop won't finish executing because of a division by zero.
   :correct: d
   :feedback_a: This would be true if the body of the while loop never executed. This would have happened if the while check was if var1 != 0 instead of var2 != 0
   :feedback_b: This would be true if the body of the while loop only execued one time, but it executes twice.
   :feedback_c: This would be true if the body of the while loop executed 3 times, but it executes twice.
   :feedback_d: The loop starts with var1=0 and var2=2. The while checks that var2 isn't 0 and that var1/var2 is greater than or equal to zero (0/2=0) so this is equal to zero and the body of the while loop will execute. The variable var1 has 1 added to it for a new value of 1. The variable var2 has 1 subtracted from it for a value of 1. At this point var1=1 and var2=1. The while condition is checked again. Since var2 isn't 0 and var1/var2 (1/1=1) is >=0 so the body of the loop will execute a second time. The variable var1 has 1 added to it for a new value of 2. The variable var2 has 1 subtracted from it for a value of 0. At this point var1=2 and var2=0. The while condition is checked again. Since var2 is zero the while loop stops and the value of var1 is 2 and var2 is 0.
   :feedback_e: 0/2 won't cause a division by zero. The result is just zero.

   What are the values of var1 and var2 after the following code segment is executed and the while loop finishes?
   
   .. code-block:: java

     int var1 = 0;
     int var2 = 2;

     while ((var2 != 0) && ((var1 / var2) >= 0)) {
        var1 = var1 + 1;
        var2 = var2 - 1;
     }
	 
Hard Multiple Choice Questions
----------------------------------

.. .. mchoice:: qch_2
   :practice: T
   :answer_a: s == (m - 5) && (2 * s + 3) == (m + 3)
   :answer_b: (s == m - 5) && (s - 3 == 2 * (m - 3))
   :answer_c: (s == (m + 5)) && ((s + 3) == (2 * m + 3))
   :answer_d: s == m + 5 && s + 3 == 2 * m + 6
   :answer_e: None of the above is correct.
   :correct: d
   :feedback_a: This can't be right because Susan is 5 years older than Matt, so the first part is wrong. It has Susan equal to Matt's age minus 5, which would have Matt older than Susan.
   :feedback_b: This would be true if Susan was 5 years younger than Matt and three years ago she was twice his age. But, how could she be younger than him now and twice his age three years ago?
   :feedback_c: This is almost right. It has Susan as 5 years older than Matt now. But the second part is wrong. Multiplication will be done before addition so (2 * m + 3) won't be correct, for in 3 years Susan will be twice as old as Matt. It should be (2 * (m + 3)) or (2 * m + 6)
   :feedback_d: Susan is 5 years older than Matt so s == m + 5 should be true and in 3 years she will be twice as old, so s + 3 = 2 * (m + 3) = 2 * m + 6
   :feedback_e: s == m + 5 && s + 3 == 2 * m + 6 is correct

   Susan is 5 years older than Matt. Three years from now Susan's age will be twice Matt's age. What should be in place of the following condition to solve this problem?
   
   .. code-block:: java

     for (int s = 1; s <=100; s++) {
        for (int m = 1; m <= 100; m++) {
           if (condition) {
              System.out.println("Susan is " + s + " and Matt is " + m);
		   }
        }
     }


.. mchoice:: q3_11_9
   :practice: T
   :answer_a: (x > 15 && x < 18) && (x > 10)
   :answer_b: (y < 20) || (x > 15 && x < 18)
   :answer_c: ((x > 10) || (x > 15 && x < 18)) || (y < 20)
   :answer_d: (x < 10 && y > 20) && (x < 15 || x > 18) 
   :correct: c
   :feedback_a: This can't be right as it's only checking the x variable, however the original statement can solely depend on the y variable in some cases.
   :feedback_b: There's a third condition on x that can affect the output of the statement which is not considered in this solution.
   :feedback_c: The commutative property allows the terms to be switched around, while maintaining the value. In this case, the || symbol is used with the commutative property and the statement included the && must stay together to follow the laws of logic.
   :feedback_d: This is the negation of the original statement, thus returning incorrect values.

   Assuming that x and y have been declared as valid integer values, which of the following is equivalent to this statement?
   
   .. code-block:: java

     (x > 15 && x < 18) || (x > 10 || y < 20)
      


More Practice
--------------
     
For more practice with loops and strings see http://codingbat.com/java/Warmup-2.  For practice with loops and arrays see http://codingbat.com/java/Array-2.

Here are some recommended problems

* http://codingbat.com/prob/p142270
* http://codingbat.com/prob/p101475
* http://codingbat.com/prob/p165666
* http://codingbat.com/prob/p117334
* http://codingbat.com/prob/p121596  
   
   




