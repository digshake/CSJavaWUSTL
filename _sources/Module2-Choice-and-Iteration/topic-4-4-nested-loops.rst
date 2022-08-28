.. qnum::
   :prefix: 4-4-
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

.. turtle snowflake patterns

Nested For Loops
================

..	index::
	single: nested for loop
	pair: loop; nested

A **nested loop** has one loop inside of another.  These are typically used for working with two dimensions such as printing stars in rows and columns as shown below.   When a loop is nested inside another loop, the inner loop is runs many times inside the outer loop. In each iteration of the outer loop, the inner loop will be re-started. The inner loop must finish all of its iterations before the outer loop can continue to its next iteration. 

.. figure:: Figures/nestedloops.png
    :width: 350px
    :align: center
    :figclass: align-center
    
    Figure 1: Nested Loops
    
.. |Java visualizer| raw:: html

   <a href="http://www.pythontutor.com/visualize.html#code=public%20class%20NestedLoops%0A%7B%0A%20%20%20public%20static%20void%20main%28String%5B%5D%20args%29%0A%20%20%20%7B%0A%20%20%20%20%20%20%20for%20%28int%20row%20%3D%201%3B%20row%20%3C%3D%203%3B%20row%2B%2B%29%0A%20%20%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20for%20%28int%20col%20%3D%201%3B%20col%20%3C%3D%205%3B%20col%2B%2B%29%0A%20%20%20%20%20%20%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20System.out.print%28%22*%22%29%3B%0A%20%20%20%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%20%20%20%20%20System.out.println%28%29%3B%0A%20%20%20%20%20%20%20%7D%0A%20%20%20%7D%0A%7D&cumulative=false&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=java&rawInputLstJSON=%5B%5D&textReferences=false&curInstr=0" target="_blank"  style="text-decoration:underline">Java visualizer</a>


|CodingEx| **Coding Exercises**

What does the ``NestedLoops`` program print out? Step through the code in the debugger. Notice how the inner loop is started over for each row. Can you predict how many rows and columns of stars there will be?

   
   Can you change the code to be a 10x8 rectangle? Try replacing line 14 with this print statement to see the rows and columns: System.out.print(row + "-" + col + " ");  
   
    
|Exercise| **Check your understanding**

.. mchoice:: q4_4_1
   :practice: T
   :answer_a: A rectangle of 7 rows with 5 stars per row.
   :answer_b: A rectangle of 7 rows with 4 stars per row.
   :answer_c: A rectangle of 6 rows with 5 stars per row.
   :answer_d: A rectangle of 6 rows with 4 stars per row.
   :correct: c
   :feedback_a: This would be true if i was initialized to 0.  
   :feedback_b: This would be true if i was initialized to 0 and the inner loop continued while <code>y < 5</code>.
   :feedback_c: The outer loop runs from 1 up to 7 but not including 7 so there are 6 rows and the inner loop runs 1 to 5 times including 5 so there are 5 columns.  
   :feedback_d: This would be true if the inner loop continued while <code>y < 5</code>.    

   What does the following code print?
   
   .. code-block:: java 

     for (int i = 1; i < 7; i++) 
     {  
         for (int y = 1; y <= 5; y++)
         {
             System.out.print("*");
         }
         System.out.println();
     }
     
.. mchoice:: q4_4_2
   :practice: T
   :answer_a: A rectangle of 4 rows with 3 star per row.
   :answer_b: A rectangle of 5 rows with 3 stars per row.
   :answer_c: A rectangle of 4 rows with 1 star per row.
   :answer_d: The loops have errors.
   :correct: b
   :feedback_a: This would be true if i was initialized to 1 or ended at 4.  
   :feedback_b: Yes, the outer loop runs from 0 up to 5 but not including 5 so there are 5 rows and the inner loop runs from 3 down to 1 so 3 times.  
   :feedback_c: The inner loop runs 3 times when j is 3, 2, and then 1, so there are 3 stars per row.  
   :feedback_d: Try the code in an Active Code window and you will see that it does run.    

   What does the following code print?
   
   .. code-block:: java 

     for (int i = 0; i < 5; i++) 
     {  
         for (int j = 3; j >= 1; j--)
         {
             System.out.print("*");
         }
         System.out.println();
     }

.. parsonsprob:: q4_4_3
   :numbered: left
   :practice: T
   :adaptive:
   :noindent:

   The main method in the following class should print 10 rows with 5 <code>*</code> in each row.   But, the blocks have been mixed up and include <b>one extra block</b> that isn't needed in the solution.  Drag the needed blocks from the left and put them in the correct order on the right.  Click the <i>Check Me</i> button to check your solution.</p>
   -----
   public class Test1
   {
       public static void main(String[] args)
       {
   =====
           for (int x = 0; x < 10; x++) 
           {
   =====
               for (int y = 0; y < 5; y++) 
               {
   =====
               for (int y = 0; y <= 5; y++) 
               { #paired
   =====
                   System.out.print("*");
   =====
               }
   =====
               System.out.println();
   =====
           }
   =====
       }
   }


Summary
-------

- Nested iteration statements are iteration statements that appear in the body of another iteration statement.

- When a loop is nested inside another loop, the inner loop must complete all its iterations before the outer loop can continue.


   
