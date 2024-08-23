.. qnum::
   :prefix: 3-9-
   :start: 1
   
Mixed Up Code Practice
======================

Try to solve each of the following. Click the *Check* button to check each solution.  
You will be told if your solution is too short, has a block in the wrong order, 
or you are using the wrong block.  Some of the problems have an extra block or 
two that aren't needed in the correct solution. 
                
.. parsonsprob:: q3_9_1
   :numbered: left
   :practice: T
   :adaptive:
   :noindent:

   The following program segment should print if your guess is too low, correct, or too high  But, the blocks have been mixed up.  Drag the blocks from the left and put them in the correct order on the right.  
   
   -----
   int guess = 10;
   int answer = 5;
   =====
   if (guess < answer) {
   =====
       System.out.println("Your guess is too low");
   =====
   } else if (guess == answer) {
   =====      
       System.out.println("You are right!");
   =====
   } else {
   =====
        System.out.println("Your guess is too high");
   }
      
   


         
               

  
   
.. parsonsprob:: q4_7_1
   :numbered: left
   :practice: T
   :adaptive:
   :noindent:

   The following program segment should print out all the values from 20 to 30 (20, 21, 22, ... 30). But, the blocks have been mixed up.  Drag the blocks from the left and put them in the correct order on the right.  
   
   -----
   int x = 20;
   =====
   while (x <= 30) {
   =====
       System.out.println(x);
   =====
       x++;
   =====
   }
                   
      
.. parsonsprob:: q4_7_2
   :numbered: left
   :practice: T
   :adaptive:
   :noindent:

   The following program segment should print a countdown from 15 to 0 (15, 14, 13, ... 0).  But the blocks have been mixed up and include <b>one extra block</b> that is not needed in a correct solution.  Drag the needed blocks from the left and put them in the correct order on the right.  

   -----
   public class Test1 {
   =====
       public static void main(String[] args) {
   =====
           for (int i = 15; i >=0; i--) {
   =====
           for (int i = 15; i > 0; i--) {#paired
   =====
               System.out.println(i);
   =====
           }
   =====
       }
   =====
   }

   
.. parsonsprob:: q4_7_3
   :numbered: left
   :practice: T
   :adaptive:
   :noindent:

   The main method in the following class should print up from 0 to 50 by 5 (0, 5, 10, 15 ... 50). But, the blocks have been mixed up and include <b>an extra block</b> that isn't needed in the solution.  Drag the needed blocks from the left and put them in the correct order on the right.  
  
   -----
   public class Test1 {
   =====
       public static void main(String[] args) {
   =====
           int x = 0;
   =====
           while (x <= 50) {
   =====
           while (x < 50) { #paired
   =====
               System.out.println(x);
   =====
               x = x + 5;
   =====
           }
   =====
       }
   }
           
  

          

           
.. parsonsprob:: q4_7_6
   :numbered: left
   :practice: T
   :adaptive:
   :noindent:

   The main method in the following class should print 3 rows with 6 <code>*</code> in each row.  But, the blocks have been mixed up and include <b>two extra blocks</b> that aren't needed in the solution.  Drag the needed blocks from the left and put them in the correct order on the right.  
   
   -----
   public class Test1 {
   =====
       public static void main(String[] args) {
   =====
           for (int x = 3; x > 0; x--) {
   =====
           for (int x = 0; x <= 3; x++) { #paired
   =====
               for (int y = 6; y > 0; y--) {
   =====
               for (int y = 0; y <= 6; y++) { #paired
   =====
                   System.out.print("*");
   =====
               }
   =====
               System.out.println();
   =====
           }   
       }
   }

       
.. parsonsprob:: q4_7_7
   :numbered: left
   :practice: T
   :adaptive:
   :noindent:

   The main method in the following class should print 1 (followed by a newline), then 22 (followed by a newline), and then 333 (followed by a newline).  But, the blocks have been mixed up and include <b>an extra block</b> that isn't needed in the solution.  Drag the needed blocks from the left and put them in the correct order on the right.  
   
   -----
   public class Test1 {
   =====
       public static void main(String[] args) {
   =====
           for (int x = 1; x <= 3; x++) {
   =====
           for (int x = 0; x < 3; x++) { #paired
   =====
               for (int y = 0; y < x; y++) {
   =====
                   System.out.print(x);
   =====
               }
               System.out.println(); 
           }
   =====
       }
   }
          
.. parsonsprob:: q4_7_8
   :numbered: left
   :practice: T
   :adaptive:
   :noindent:

   The main method in the following class should print 11111, 22222, 33333, 44444, and 55555. But, the blocks have been mixed up and contain <b>two extra blocks</b> that are not needed in a correct solution.  Drag the blocks from the left and put them in the correct order on the right.  
   
   -----
   public class Test1 {
   =====
       public static void main(String[] args) {
   =====
           for (int x = 1; x <= 5; x++) {
   =====
           for (int x = 1; x < 5; x++) { #paired
   =====
               for (int y = 0; y < 5; y++) {
   =====
                   System.out.print(x);
   =====
                   System.out.print(y); #paired
   =====
               } //end inner loop
               System.out.println(); 
   =====
           } //end outer loop
   =====
       }
   }
  

          
.. parsonsprob:: q4_7_9
   :numbered: left
   :practice: T
   :adaptive:
   :noindent:

   The main method in the following class should print 11111, 2222, 333, 44, 5.  But, the blocks have been mixed up and include <b>one extra block</b> that isn't needed in a correct solution.  Drag the needed blocks from the left and put them in the correct order on the right.  
   
   -----
   public class Test1 {
   =====
       public static void main(String[] args) {
   =====
           for (int x = 0; x < 5; x++) {
   =====
               for (int y = 5; y > x; y--) {
   =====
                   System.out.print(x+1);
   =====
                   System.out.print(x); #paired
   =====
               } //end inner loop
               System.out.println(); 
   =====
           } //end outer loop
   =====
       }
   }
   



   
