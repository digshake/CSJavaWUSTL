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
   if (guess < answer)
   =====
   {   
       System.out.println("Your guess is too low");
   }
   =====
   else if (guess == answer)
   =====
   {       
       System.out.println("You are right!");
   }
   =====
   else 
   =====
   {
        System.out.println("Your guess is too high");
   }
      
.. parsonsprob:: q3_9_2
   :numbered: left
   :practice: T
   :adaptive:
   :noindent:

   The following program segment should print 
   either "You can go out" if you don't have any homework and have cleaned and 
   otherwise should print "You can not go out". But the blocks have been mixed up and includes <b>one extra block</b> that is not needed in a correct solution.  Drag the needed blocks from the left and put them in the correct order on the right. 
   -----
   public class Test1
   {
   =====
       public static void main(String[] args)
       {
   =====
           boolean homeworkLeft = false; 
           boolean cleaned = true;
   =====
           if (!homeworkLeft && cleaned)
   =====
           if (homeworkLeft && cleaned) #paired
   =====
               System.out.println("You can go out");
   =====
           else 
   =====
               System.out.println("You can not go out");
   =====
       }
   }

   
.. parsonsprob:: q3_9_3
   :numbered: left
   :practice: T
   :adaptive:
   :noindent:

   The main method in the following class should print if x is in the range of 1 to 10 (inclusive) or not. But, the blocks have been mixed up and includes <b>an extra block</b> that isn't needed in the solution.  Drag the needed blocks from the left and put them in the correct order on the right.  
   
   -----
   public class Test1
   {
   =====
       public static void main(String[] args)
       {
   =====
           int x = 3;
   =====
           if (x >= 1 && x <= 10) 
   =====
           if (x >= 1 || x <= 10) #paired
   =====
               System.out.println("1 <= x <= 10");
   =====
           else 
   =====
               System.out.println("x is not in range");
   =====
       }
   }
           
  
.. parsonsprob:: q3_9_4
   :numbered: left
   :practice: T
   :adaptive:
   :noindent:

   The main method in the following class should print out if a string has the word "ringing" in it or not. But, the blocks have been mixed up and includes <b>an extra block</b> that isn't needed in the solution.  Drag the needed blocks from the left and put them in the correct order on the right.  
  
   -----
   public class Test1
   {
   =====
       public static void main(String[] args)
       {
   =====    
          String message = "Is that the phone ringing?";
   =====
          if (message.indexOf("ringing") >= 0)
   =====
          if (message.indexof("ringing") >= 0) #paired
   =====
              System.out.println("Answer the phone!");
   =====
          else
   =====
              System.out.println("I don't hear anything.");
   =====
       }
   }
        
   
.. parsonsprob:: q3_9_5
   :numbered: left
   :practice: T
   :adaptive:
   :noindent:

   The main method in the following class should print if your favorite food is junk food (pizza or wings) or not. But, the blocks have been mixed up and includes <b>an extra block</b> that is not needed in a correct solution.  Drag the needed blocks from the left and put them in the correct order on the right.  
   
   -----
   public class Test1
   {
       public static void main(String[] args)
       {
   =====
           String favFood = "kale";
           boolean favPizza = favFood.equals("pizza");
           boolean favWings = favFood.equals("wings");
   =====
           if (favPizza || favWings)
   =====
           if (favPizza && favWings) #paired
   =====
               System.out.println("Your fav is junk food");
   =====
           else
   =====
               System.out.println("Your fav is not junk");
   =====
       } 
   }
           
               
.. parsonsprob:: q3_9_6
   :numbered: left
   :practice: T
   :adaptive:
   :noindent:

   The main method in the following class should print your fine if you are speeding.  If you are going over 65 but less than 75 the fine is 50.  If you are going at least 75 and less than 85 the fine is 100.  Over that the fine is 200.   But, the blocks have been mixed up and includes <b>two extra blocks</b> that aren't needed in the solution.  Drag the needed blocks from the left and put them in the correct order on the right.  
   
   -----
   public class Test1
   {
       public static void main(String[] args)
       {
   =====
           int speed = 90;
   =====
           if (speed > 65 && speed < 75)
   =====
           if (speed > 65 || speed < 75) #paired
   =====
               System.out.println("50");
   =====
           else if (speed >= 75 && speed < 85)
   =====
           else if (speed >= 75 || speed < 85) #paired
   =====
               System.out.println("100");
   =====
           else
               System.out.println("200");
   =====
       }
   }

           
.. parsonsprob:: q3_9_7
   :numbered: left
   :practice: T
   :adaptive:
   :noindent:

   The main method in the following class should print the alarm time.  If it is a weekday you should get up at 7:00am and if not get up at 10:00am. But, the blocks have been mixed up.  Drag the needed blocks from the left and put them in the correct order on the right.  

   -----
   public class Test1
   {
   =====
       public static void main(String[] args)
       {
   =====
           boolean weekend = false;
   =====
           if (!weekend)
   =====
               System.out.println("7:00am");
   =====
           else
   =====
               System.out.println("10:00am");
   =====
       }
   }

       
.. parsonsprob:: q3_9_8
   :numbered: left
   :practice: T
   :adaptive:
   :noindent:

   The main method in the following class should print if you can text now.  You can text if you are not driving and not eating. But, the blocks have been mixed up and includes <b>an extra block</b> that isn't needed in the solution.  Drag the needed blocks from the left and put them in the correct order on the right.  
   
   -----
   public class Test1
   {
   =====
       public static void main(String[] args)
       {
   =====
           boolean driving = true;
           boolean eating = false;
   =====
           if (!driving && !eating)
   =====
           if (!driving || !eating) #paired     
   =====
               System.out.println("Can text now");
   =====
           else 
   =====
               System.out.println("Can't text now");
   =====
       }
   }
          
.. parsonsprob:: q3_9_9
   :numbered: left
   :practice: T
   :adaptive:
   :noindent:

   The main method in the following class should print if your name starts with a vowel or not. But, the blocks have been mixed up.  Drag the blocks from the left and put them in the correct order on the right.  
   
   -----
   public class Test1
   {
   =====
       public static void main(String[] args)
       {
   =====
           String name = "Julian";
           String firstLetter = name.substring(0,1);
           String lowerFirst = firstLetter.toLowerCase();
   =====
           boolean aF = lowerFirst.equals("a");
           boolean eF = lowerFirst.equals("e");
           boolean iF = lowerFirst.equals("i");
           boolean oF = lowerFirst.equals("o");
           boolean uF = lowerFirst.equals("u");
           
   =====
           if (aF || eF || iF || oF || uF)
   =====
               System.out.println("Starts with a vowel");
   =====
           else
   =====
               System.out.println("Starts with a consonant");
   =====
       }
   }

          
.. parsonsprob:: q3_9_10
   :numbered: left
   :practice: T
   :adaptive:
   :noindent:

   The main method in the following class should print your grade for score. But, the blocks have been mixed up.  Drag the needed blocks from the left and put them in the correct order on the right.  
   
   -----
   public class Test1
   {
       public static void main(String[] args)
       {
   =====
           int score = 73;
   =====
           if (score >= 90)
   =====
               System.out.println("A");
   =====
           else if (score >= 80)
   =====
               System.out.println("B");
   =====
           else if (score >= 70)
               System.out.println("C");
   =====
           else if (score >= 60) 
               System.out.println("D");
   =====
           else 
               System.out.println("E");
   =====
       }
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
   public class Test1
   {
   =====
       public static void main(String[] args)
       {
   =====
           for (int i = 15; i >=0; i--) 
   =====
           for (int i = 15; i > 0; i--) #paired
   =====
               System.out.println(i);
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
   public class Test1
   {
   =====
       public static void main(String[] args)
       {
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
           
  
.. parsonsprob:: q4_7_4
   :numbered: left
   :practice: T
   :adaptive:
   :noindent:

   The main method in the following class should print out the values from 0 to 100 by 20's (0, 20, 40, .. 100). But, the blocks have been mixed up and include <b>an extra block</b> that isn't needed in the solution.  Drag the needed blocks from the left and put them in the correct order on the right. 
   
   -----
   public class Test1
   {
   =====
       public static void main(String[] args)
       {
   =====    
          for (int i = 0; i <= 100; i+=20) 
   =====
          for (int i = 100; i >= 0; i-=20) #paired
   =====
              System.out.println(i);
   =====
       }
   =====
   }
        
   
.. parsonsprob:: q4_7_5
   :numbered: left
   :practice: T
   :adaptive:
   :noindent:

   The main method in the following class should print out the values from 100 to 0 by 10's (100, 90, 80, ... 0). But, the blocks have been mixed up and include <b>an extra block</b> that is not needed in a correct solution.  Drag the needed blocks from the left and put them in the correct order on the right.  
   
   -----
   public class Test1
   {
   =====
       public static void main(String[] args)
       {
   =====
           for (int i = 100; i >= 0; i -= 10) 
   =====
           for (int i = 0; i <= 100; i += 10) #paired
   =====
               System.out.println(i);
   =====
       } 
   =====
   }
           
               

           
.. parsonsprob:: q4_7_6
   :numbered: left
   :practice: T
   :adaptive:
   :noindent:

   The main method in the following class should print 3 rows with 6 <code>*</code> in each row.  But, the blocks have been mixed up and include <b>two extra blocks</b> that aren't needed in the solution.  Drag the needed blocks from the left and put them in the correct order on the right.  
   
   -----
   public class Test1
   {
   =====
       public static void main(String[] args)
       {
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
   public class Test1
   {
   =====
       public static void main(String[] args)
       {
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
   public class Test1
   {
   =====
       public static void main(String[] args)
       {
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
   public class Test1
   {
   =====
       public static void main(String[] args)
       {
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
   



   
