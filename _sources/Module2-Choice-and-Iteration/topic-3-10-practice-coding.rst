.. qnum::
   :prefix: 3-10-
   :start: 1
   
Coding Practice 
==============================

.. tabbed:: ch5Ex1

        .. tab:: Question 
           
           .. activecode::  ch5Ex1q
              :language: java
              :autograde: unittest
              :practice: T   
              
              The following code should print ``x is greater than 0``.  However, the code has errors.  Fix the code so that it compiles and runs correctly.
              Run the program several times with different values of x to test both if and else branches. 
              ~~~~
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      int x = 3;
                      if (x > 0
                          System.out.println("x is greater than 0")
                      else 
                          System.out.println(x is less than or equal 0");
                  }
              }
              ====
              import static org.junit.Assert.*;
                import org.junit.*;;
                import java.io.*;
                
                public class RunestoneTests extends CodeTestHelper
                {
                  @Test
                  public void testIf() throws IOException
                  {
                    String target = "if (x > 0)";
                    boolean passed = checkCodeContains("if boolean expression nested within pair of parentheses", target);
                    assertTrue(passed);
                  }  
                }


        .. tab:: Answer
        
           Line 6 is missing a final ``)``.  Line 7 is missing a semicolon at the end.  Line 9 is missing the starting ``"``.
        
           .. activecode::  ch5Ex1a
              :language: java
              :optional:
   
              This is the answer to the previous question.
              ~~~~
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      int x = 3;
                      if (x > 0)
                          System.out.println("x is greater than 0");
                      else 
                          System.out.println("x is less than or equal 0");
                  }
              }
              

.. activecode::  ch5Ex2qb
              :language: java
              :autograde: unittest
              :practice: T   
   
              The following code should generate a random number and print if it is evenly divisible by 2.  However, the code has an error and always prints "Your number is even", even if the random number is odd.
              Fix the code so that it only prints the message when the number is even.
              ~~~~
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      int num = (int) (Math.random() * 10);
                      System.out.println(num);
                      if (num % 2 == 0) ;
                      {
                          System.out.println("Your number is even");
                      }
                  }
              }
              ====
              import static org.junit.Assert.*;
                import org.junit.*;;
                import java.io.*;
                
                public class RunestoneTests extends CodeTestHelper
                {
                  @Test
                  public void testIf() throws IOException
                  {
                    String target = "if (num % 2 == 0) ;";
                    boolean passed = checkCodeNotContains("remove semicolon after boolean condition in if statement", target);
                    assertTrue(passed);
                  }  
                }            

.. activecode::  ch5Ex2q
              :language: java
              :autograde: unittest
              :practice: T   
   
              The following code should check your guess against the answer and print that it is too low, correct, or too high.  However, the code has errors.  Fix the code so that it compiles and runs correctly.
              ~~~~
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      int guess = 7;
                      int answer = 9;
                      if guess < answer)
                          System.out.println("Your guess is too low);
                      else if (guess = answer)
                          System.out.println("You are right!");
                      else 
                          System.println("Your guess is too high");
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
                        String expect = "Your guess is too low\n";
                        boolean passed = getResults(expect, output, "Expected output from main");
                        assertTrue(passed);
                    }
                }


..        .. tab:: Answer
        
           Line 7 is missing the starting ``(``.  Line 8 is missing the closing ``"``.  Line 9 should be ``==`` rather than ``=`` to test for equality.  Line 12 should be ``System.out.println``.
           
           .. activecode::  ch5Ex2a
              :language: java
              :optional:
   
              This is the answer to the previous question.
              ~~~~
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      int guess = 7;
                      int answer = 9;
                      if (guess < answer)
                          System.out.println("Your guess is too low");
                      else if (guess == answer)
                          System.out.println("You are right!");
                      else 
                          System.out.println("Your guess is too high");
                  }
              }


.. activecode::  ch5Ex3q
              :language: java
              :autograde: unittest
              :practice: T   
                         
              The following code should print "You can go out" if you have done your homework and cleaned your room. However, the code has errors.  Fix the code so that it compiles and runs correctly.  
              ~~~~
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      boolean doneHomework = True;
                      boolean cleanedRoom = true;
                      if (doneHomework && cleanedRoom)
                           System.out.println("You cannot go out");
                      else 
                          System.out.println("You can go out");
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
                        String expect = "You can go out\n";
                        boolean passed = getResults(expect, output, "Expected output from main");
                        assertTrue(passed);
                    }
                }


..        .. tab:: Answer
        
           Line 5 should be ``true`` not ``True``.  Lines 10 and 8 should be swapped.
           
           .. activecode::  ch5Ex3a
              :language: java
              :optional:
   
              This is the answer to the previous question.
              ~~~~   
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      boolean doneHomework = true;
                      boolean cleanedRoom = true;
                      if (doneHomework && cleanedRoom)
                          System.out.println("You can go out");
                      else 
                          System.out.println("You cannot go out");
                  }
              }
              
           
.. activecode::  ch5Ex4q
              :language: java
              :autograde: unittest
              :practice: T   
                         
              The following code should print if x is in the range of 0 to 10 (including 0 and 10). However, the code has errors.  Fix the errors so that the code runs as intended.
              ~~~~
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      int x = 0
                      if (x > 0 && x <= 10)
                          System.out.println("x is between 0 and 10 inclusive");
                      otherwise 
                          System.out.println("x is either less than 0 or greater than 10");
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
                        String expect = "x is between 0 and 10 inclusive\n";
                        boolean passed = getResults(expect, output, "Expected output from main");
                        assertTrue(passed);
                    }
                }


..        .. tab:: Answer
        
           Line 5 is missing an end  ``;``.  Line 6 should be ``x >= 0``.  Line 8 should be ``else`` instead of ``otherwise``.		
           
           .. activecode::  ch5Ex4a
              :language: java
              :optional:
   
              This is the answer to the previous question.
              ~~~~               
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      int x = 3;
                      if (x >= 0 && x <= 10)
                          System.out.println("x is between 0 and 10 inclusive");
                      else 
                          System.out.println("x is either less than 0 or greater than 10");
                  }
              }
              
 
           
.. activecode::  ch5Ex5q
              :language: java
              :autograde: unittest
              :practice: T   
                         
              The following code should print if x is less than 0, equal to 0, or greater than 0.  Finish it to work correctly. 
              ~~~~
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      int x = -3;
                      if (x > 0) 
                          System.out.println("x is less than 0");
                      
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
                      String expect = "x is less than 0";
                      boolean passed = getResults(expect, output, "Expected output from main if x = -3");
                      assertTrue(passed);
                    }

                    @Test
                    public void testCheckCodeContains()
                    {
                        boolean outputLess = checkCodeContains("if (x < 0)");
                        assertTrue(outputLess);
                    }
                    @Test
                    public void testCheckCodeContains2()
                    {
                        String code = getCode();
                        boolean ifGreater = code.contains("if (x > 0)");
                        boolean ifEqual = code.contains("if (x == 0)");
                        boolean passed = getResults("Test if x greater than 0 or test if x is equal to 0", "Greater than: " + ifGreater + ", Equal to: " + ifEqual, "Test if x greater than 0 or if x equal to 0", ifGreater || ifEqual );
                        assertTrue(passed);
                    }
                }



..        .. tab:: Answer
        
           One way to solve this is to add an ``else if`` and then print out if x is equal to 0 and an ``else`` to print that x is greater than 0 as shown below.
        
           .. activecode::  ch5Ex5a
              :language: java
              :optional:
   
              This is the answer to the previous question.
              ~~~~              
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      int x = -3;
                      if (x < 0) 
                          System.out.println("x is less than 0");
                      else if (x == 0)
                          System.out.println("x is equal to 0");
                      else 
                          System.out.println("x is greater than 0");
                      
                  }
                      
              }
              
                
.. activecode::  ch5Ex6q
              :language: java
              :autograde: unittest
              :practice: T   
   
              Finish the code below so that it prints ``You can go out`` if you have a ride or if you can walk and otherwise prints ``You can't go out``.  Use a logical or to create a complex conditional.
              ~~~~
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      boolean canWalk = true;
                      boolean haveRide = false;
                      
                  }
              }
              ====
              import static org.junit.Assert.*;
                import org.junit.*;;
                import java.io.*;
                
                public class RunestoneTests extends CodeTestHelper
                {
                    @Test
                    public void testCheckCodeContains()
                    {
                        boolean output1 = checkCodeContains("print statement You can go out", "System.out.println(\"You can go out\")");
                        assertTrue(output1);
                    }

                    @Test
                    public void testCheckCodeContains2()
                    {
                        boolean output2 = checkCodeContains("print statement You can't go out", "System.out.println(\"You can't go out\")");
                        assertTrue(output2);
                    }

                    @Test
                    public void testCheckCodeContains3()
                    {
                        boolean output3 = checkCodeContains("or", "||");
                        assertTrue(output3);
                    }

                      @Test
                    public void testChangedCode() {
                        String origCode = "public class Test1 { public static void main(String[] args) { boolean canWalk = true; boolean haveRide = false; } }";

                        boolean changed = codeChanged(origCode);

                        assertTrue(changed);

                    }
                }


..        .. tab:: Answer
        
           Add an ``if`` statement and use a logical or (``||``) to join the conditions and print the one message.  Also add an ``else`` statement and print the other message.
        
           .. activecode::  ch5Ex6a
              :language: java
              :optional:
   
              This is the answer to the previous question.
              ~~~~              
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      boolean canWalk = true;
                      boolean haveRide = false;
                      if (canWalk || haveRide)
                          System.out.println("You can go out");
                      else
                          System.out.println("You can't go out"); 
                  }
              }
              
           
.. activecode::  ch5Ex7q
              :language: java
              :autograde: unittest
              :practice: T   
   
              Finish the code below to print you can go out if you don't have homework and you have done the dishes.
              ~~~~
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      boolean haveHomework = false;
                      boolean didDishes = true;
                      
                  }
              }
              ====
              import static org.junit.Assert.*;
                import org.junit.*;;
                import java.io.*;
                
                public class RunestoneTests extends CodeTestHelper
                {
                    @Test
                    public void testCheckCodeContains()
                    {
                        boolean output1 = checkCodeContains("print statement You can go out", "System.out.println(\"You can go out\")");
                        assertTrue(output1);
                    }

                    @Test
                    public void testCheckCodeContains2()
                    {
                        boolean output2 = checkCodeContains("and", "&&");
                        assertTrue(output2);
                    }

                    @Test
                    public void testCheckCodeContains3()
                    {
                        boolean output2 = checkCodeContains("not", "!");
                        assertTrue(output2);
                    }

                     @Test
                    public void testChangedCode() {
                        String origCode = "public class Test1 { public static void main(String[] args) { boolean haveHomework = false; boolean didDishes = true; } }";
                        boolean changed = codeChanged(origCode);
                        assertTrue(changed);
                    }
                }


..        .. tab:: Answer
        
           Add a conditional with a negation ``!`` for haveHomework and a logical and to create a complex conditional.   
           
           .. activecode::  ch5Ex7a
              :language: java
              :optional:
   
              This is the answer to the previous question.
              ~~~~
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      boolean haveHomework = false;
                      boolean didDishes = true;
                      if (!haveHomework && didDishes)
                          System.out.println("You can go out");
                      else
                          System.out.println("You can't go out");
                      
                  }
              }
              
          
.. activecode::  ch5Ex8q
              :language: java
              :autograde: unittest
              :practice: T   
     
              Finish the following code so that it prints ``You have a fever`` if your temperature is above 100 and otherwise prints ``You don't have a fever``.
              ~~~~
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      double temp = 103.5;
                  }
              }
              ====
              import static org.junit.Assert.*;
                import org.junit.*;;
                import java.io.*;
                
                public class RunestoneTests extends CodeTestHelper
                {
                    @Test
                    public void testCheckCodeContains()
                    {
                        boolean output1 = checkCodeContains("print statement You have a fever", "System.out.println(\"You have a fever\")");
                        assertTrue(output1);
                    }

                    @Test
                    public void testCheckCodeContains2()
                    {
                        boolean output2 = checkCodeContains("print statement You don't have a fever", "System.out.println(\"You don't have a fever\")");
                        assertTrue(output2);
                    }

                    @Test
                    public void testCheckCodeContains3()
                    {
                        boolean output4 = checkCodeContains("if statement for temp greater than 100", "if (temp > 100)");
                        assertTrue(output4);
                    }

                     @Test
                    public void testChangedCode() {
                        String origCode = "public class Test1 { public static void main(String[] args) { double temp = 103.5; } }";
                        boolean changed = codeChanged(origCode);
                        assertTrue(changed);
                    }
                }


..        .. tab:: Answer
        
           Add a conditional and print the first message if the temp is above 100 and otherwise print the other message.
          
           .. activecode::  ch5Ex8a
              :language: java
              :optional:
   
              This is the answer to the previous question.
              ~~~~              
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      double temp = 103.5;
                      if (temp > 100)
                          System.out.println("You have a fever");
                      else
                          System.out.println("You don't have a fever");
                  }
              }

              
          
.. activecode::  ch5Ex9q
              :language: java
              :autograde: unittest
              :practice: T   
   
              Finish the code to print ``It is freezing`` if the temperature is below 30, ``It is cold`` if it is below 50, ``It is nice out`` if it is below 90, or ``It is hot`` using nested if else statements. 
              ~~~~
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      int temp = 100;
                      
                  }
              }
              ====
              import static org.junit.Assert.*;
                import org.junit.*;;
                import java.io.*;
                
                public class RunestoneTests extends CodeTestHelper
                {
                     @Test
                    public void testCountIfs()
                    {
                        String code = getCode();
                        int num = countOccurences(code, "if");
                        boolean passed = num >= 3;

                        getResults("3+", "" + num, "Number of if statements", passed);
                        assertTrue(passed);
                    }

                      @Test
                    public void testCountElses()
                    {
                        String code = getCode();
                        int num = countOccurences(code, "else");
                        boolean passed = num >= 3;

                        getResults("3+", "" + num, "Number of else statements", passed);
                        assertTrue(passed);
                    }

                      @Test
                    public void testCountPrints()
                    {
                        String code = getCode();
                        int num = countOccurences(code, "System.out.print");
                        boolean passed = num >= 4;

                        getResults("4+", "" + num, "Number of print statements", passed);
                        assertTrue(passed);
                    }

                    @Test
                    public void testMain() throws IOException
                    {
                      String expect = "It is hot";
                      String output = getMethodOutput("main");
                      boolean passed = getResults(expect, output, "Prints It is hot if temp = 100");
                      assertTrue(passed);
                    }    
                     @Test
                    public void testChangedCode() {
                        String origCode = "public class Test1 { public static void main(String[] args) {  int temp = 100; } }";
                        boolean changed = codeChanged(origCode);
                        assertTrue(changed);
                    }
                }

..        .. tab:: Answer
        
           Add a conditional with two ``else if`` statements and a final ``else``.
           
           .. activecode::  ch5Ex9a
              :language: java
              :optional:
   
              This is the answer to the previous question.
              ~~~~              
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      int temp = 100;
                      if (temp < 30)
                          System.out.println("It is freezing");
                      else if (temp < 50)
                          System.out.println("It is cold");
                      else if (temp < 90)
                          System.out.println("It is nice out");
                      else 
                          System.out.println("It is hot");
                  }
              }
              
.. activecode::  ch5Ex10q
              :language: java
              :autograde: unittest
              :practice: T   
   
                
              Finish the code below to print your grade based on your score.  The score is an A if you scored 92 or higher, a B if you scored 82 to 91, a C if you scored 72 to 81, a D if you scored a 62 to 71, or an E.
              ~~~~
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      double score = 67;
                      
                  }
              }
              ====
              import static org.junit.Assert.*;
                import org.junit.*;;
                import java.io.*;
                
                public class RunestoneTests extends CodeTestHelper
                {
                  @Test
                    public void testChangedCode() {
                        String origCode = "public class Test1 { public static void main(String[] args) {        double score = 67; } }";

                        boolean changed = codeChanged(origCode);

                        assertTrue(changed);

                    }

                  @Test
                    public void testCheckCodeContains()
                    {

                       boolean outputA = checkCodeContains("print statement - A", "System.out.println(\"A\")");
                       assertTrue(outputA);

                    }

                    @Test
                    public void testCheckCodeContains2()
                    {
                      boolean outputB = checkCodeContains("print statement - B", "System.out.println(\"B\")");
                      assertTrue(outputB);
                    }

                    @Test
                    public void testCheckCodeContains3()
                    {
                      boolean outputC = checkCodeContains("print statement - C", "System.out.println(\"C\")");
                      assertTrue(outputC);
                    }

                    @Test
                    public void testCheckCodeContains4()
                    {
                      boolean outputD = checkCodeContains("print statement - D", "System.out.println(\"D\")");
                      assertTrue(outputD);
                    }

                    @Test
                    public void testCheckCodeContains5()
                    {
                      boolean outputE = checkCodeContains("print statement - E", "System.out.println(\"E\")");
                      assertTrue(outputE);
                    }

                    @Test
                    public void testCheckCodeContains6(){
                      boolean output = checkCodeContains("if you scored 92 or higher", "if (score >= 92)");
                      assertTrue(output);
                    }

                    @Test
                    public void testCheckCodeContains7(){
                      boolean output = checkCodeContains("else if you scored 82 or higher", "else if (score >= 82)");
                      assertTrue(output);
                    }

                    @Test
                    public void testCheckCodeContains8(){
                      boolean output = checkCodeContains("else if you scored 72 or higher", "else if (score >= 72)");
                      assertTrue(output);
                    }

                    @Test
                    public void testCheckCodeContains9(){
                      boolean output = checkCodeContains("else if you scored 62 or higher", "else if (score >= 62)");
                      assertTrue(output);
                    } 
                }


..        .. tab:: Answer
        
           Add a conditional with three ``else if`` statements and a final ``else``.  
           
           .. activecode::  ch5Ex10a
              :language: java
              :optional:
   
              This is the answer to the previous question.
              ~~~~
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      double score = 67;
                      if (score >= 92)
                          System.out.println("A");
                      else if (score >= 82)
                          System.out.println("B");
                      else if (score >= 72)
                          System.out.println("C");
                      else if (score >= 62)
                          System.out.println("D");
                      else 
                          System.out.println("E");
                      
                  }
              }
              
               

     
For more practice with conditionals, and especially complex conditionals, go to http://codingbat.com/java/Logic-1 and http://codingbat.com/java/Logic-2 

In particular we recommend solving the following problems

* http://codingbat.com/prob/p118290
* http://codingbat.com/prob/p183071
* http://codingbat.com/prob/p110973
* http://codingbat.com/prob/p103360
* http://codingbat.com/prob/p169213
* http://codingbat.com/prob/p178728
* http://codingbat.com/prob/p115233

.. tabbed:: tab4_8_1

        .. tab:: Question
           
           .. activecode::  code4_8_1
              :language: java
              :autograde: unittest
              :practice: T
   
              Rewrite the following code so that it uses a ``for`` loop instead of a ``while`` loop to print out all the integers from 5 to 1 (inclusive).  
              ~~~~
              public class TestLoop
              {
                  public static void main(String[] args)
                  {
                      int x = 5;
                      while (x > 0)
                      {
                          System.out.println(x);
                          x = x - 1;
                      }
                  }
              }
              ====
              import static org.junit.Assert.*;
                import org.junit.*;
                import java.io.*;
                
                public class RunestoneTests extends CodeTestHelper
                {
                    @Test
                    public void testMain() throws IOException
                    {
                        String output = getMethodOutput("main");
                        String expect = "5\n4\n3\n2\n1\n";

                        boolean passed = getResults(expect, output, "Expected output from main");
                        assertTrue(passed);
                    }

                    @Test
                    public void testForLoop() throws IOException
                    {
                        String target = "for(int x = 5;";
                        boolean passed = checkCodeContains("for loop", target);
                        assertTrue(passed);
                    }
                }



        .. tab:: Answer
        
           .. activecode::  ch6ex1a
              :language: java
              :optional:
   
              Answer: In a ``for`` loop you declare and initialize the variable(s), specify the condition, and specify how the loop variable(s) change in the header of the ``for`` loop as shown below.
              ~~~~
              public class TestLoop
              {
                  public static void main(String[] args)
                  {
                      for (int x = 5; x > 0; x = x - 1)
                          System.out.println(x);
                  }
              }

              
 
.. activecode::  code4_8_2
              :language: java
              :autograde: unittest
              :practice: T
   
              Rewrite the following code to use a ``while`` loop instead of a ``for`` loop to print out the numbers from 1 to 10 (inclusive).
              ~~~~
              public class TestLoop
              {
                  public static void main(String[] args)
                  {
                      for (int x = 1; x <= 10; x++)
                          System.out.println(x);
                  }
              }
              ====
              import static org.junit.Assert.*;
                import org.junit.*;
                import java.io.*;
                //import java.util.regex.*;
                /* Do NOT change Main or CodeTestHelper.java. */
                public class RunestoneTests extends CodeTestHelper
                {
                    @Test
                    public void testMain() throws IOException
                    {
                        String output = getMethodOutput("main");
                        String expect = "1\n2\n3\n4\n5\n6\n7\n8\n9\n10\n";

                        boolean passed = getResults(expect, output, "Expected output from main");
                        assertTrue(passed);
                    }

                    @Test
                    public void testForLoop() throws IOException
                    {
                        String target = "while (x";
                        boolean passed = checkCodeContains("while loop", target);
                        assertTrue(passed);
                    }
                }



..        .. tab:: Answer
        
           Answer: You need to specify the declarations and initializations of the loop variables(s) before the Boolean condition.  You need to do the change(s) at the end of the body of the loop.  
           
           .. activecode::  ch6ex2a
              :language: java
              :optional:
   
              public class TestLoop
              {
                  public static void main(String[] args)
                  {
                      int x = 1;
                      while (x <= 10)
                      {
                          System.out.println(x);
                          x++;
                      }
                  }  
              }
              
          
.. activecode::  code4_8_3
              :language: java
              :autograde: unittest
              :practice: T
                         
              Rewrite the following code so that it uses a ``for`` loop instead of a ``while`` loop to print out all the integers from 5 to 15 (inclusive).  
              ~~~~
              public class TestLoop
              {
                  public static void main(String[] args)
                  {
                      int x = 5;
                      while (x <= 15)
                      {
                          System.out.println(x);
                          x = x + 1;
                      }
                  }
              }
              ====
              import static org.junit.Assert.*;
                import org.junit.*;
                import java.io.*;
                
                public class RunestoneTests extends CodeTestHelper
                {
                    @Test
                    public void testMain() throws IOException
                    {
                        String output = getMethodOutput("main");
                        String expect = "5\n6\n7\n8\n9\n10\n11\n12\n13\n14\n15\n";

                        boolean passed = getResults(expect, output, "Expected output from main");
                        assertTrue(passed);
                    }

                    @Test
                    public void testForLoop() throws IOException
                    {
                        String target = "for (int x = 5;";
                        boolean passed = checkCodeContains("for loop", target);
                        assertTrue(passed);
                    }
                }

..        .. tab:: Answer
        
           Answer: In a ``for`` loop you declare and initialize the variable(s), specify the condition, and specify how the loop variable(s) change in the header of the ``for`` loop as shown below.
           
           .. activecode::  ch6ex3a
              :language: java
              :optional:
   
              public class TestLoop
              {
                  public static void main(String[] args)
                  {
                      for (int x = 5; x <= 15; x++)
                      {
                          System.out.println(x);
                      }
                  }
              }
              
      
.. activecode::  code4_8_4
              :language: java
              :autograde: unittest
              :practice: T
                         
              Rewrite the following code to use a ``while`` loop instead of a ``for`` loop to print out the numbers from 10 to 100 by 10's (inclusive).
              ~~~~
              public class TestLoop
              {
                  public static void main(String[] args)
                  {
                      for (int x = 10; x <= 100; x=x+10)
                          System.out.println(x);
                  }
              }
              ====
              import static org.junit.Assert.*;
                import org.junit.*;
                import java.io.*;
                
                public class RunestoneTests extends CodeTestHelper
                {
                    @Test
                    public void testMain() throws IOException
                    {
                        String output = getMethodOutput("main");
                        String expect = "10\n20\n30\n40\n50\n60\n70\n80\n90\n100\n";

                        boolean passed = getResults(expect, output, "Expected output from main");
                        assertTrue(passed);
                    }

                    @Test
                    public void testForLoop() throws IOException
                    {
                        String target = "while (x";
                        boolean passed = checkCodeContains("while loop", target);
                        assertTrue(passed);
                    }
                }


..        .. tab:: Answer
        
           Answer: You need to specify the declarations and initializations of the loop variables(s) before the Boolean condition.  You need to do the change(s) at the end of the body of the loop.  		
           
           .. activecode::  ch6ex4a
              :language: java
              :optional:
   
               public class TestLoop
               {
                  public static void main(String[] args)
                  {
                      int x = 10;
                      while (x <= 100)
                      {
                          System.out.println(x);
                          x = x + 10;
                      }
                  }
              }
              
           
.. activecode::  code4_8_5
              :language: java
              :autograde: unittest
              :practice: T
              
              The following code should print the values from 1 to 10 (inclusive) but has errors.  Fix the errors so that the code works as intended. If the code is in an infinite loop you can refresh the page in the browser to stop the loop and then click on Load History and move the bar above it to see your last changes.
              ~~~~
              public class TestLoop
              {
                  public static void main(String[] args)
                  {
                      int x = 1;
                      while (x < 10)
                      {
                          System.out.println(x);
                      } 
                  }    
              }
              ====
              import static org.junit.Assert.*;
                import org.junit.*;
                import java.io.*;
                
                public class RunestoneTests extends CodeTestHelper
                {
                  @Test
                  public void testMain() throws IOException
                  {
                    String output = getMethodOutput("main");
                    String expect = "1\n2\n3\n4\n5\n6\n7\n8\n9\n10\n";

                    boolean passed = getResults(expect, output, "Expected output from main");
                    assertTrue(passed);
                  }

                  @Test
                    public void testWhileLoop() throws IOException
                    {
                        String code = getCode();
                        int num = countOccurences(code, "x = x + 1") + countOccurences(code, "x++");
                        boolean passed = num >= 1;

                        getResults("1", "" + num, "Increment loop variable", passed);
                        assertTrue(passed);
                    }
                }


..        .. tab:: Answer
        
           Answer: On line 6 it should be ``while (x <= 10)``.  Add line 9 at the end of the loop body to increment ``x`` so that the loop ends (isn't an infinite loop).    
        
           .. activecode::  ch6ex5a
              :language: java
              :optional:
   
              public class TestLoop
              {
                  public static void main(String[] args)
                  {
                      int x = 1;
                      while (x <= 10)
                      {
                          System.out.println(x);
                          x++;
                      } 
                  }    
              }


.. activecode::  code4_8_6
              :language: java
              :autograde: unittest
              :practice: T
   
              The following code should print the values from 10 to 5, but it has errors.  Fix the errors so that the code works as intended.
              ~~~~
              public class TestLoop
              {
                  public static void main(String[] args)
                  {
                      for (int x = 10; x >= 5; x--)
                      {
                         System.out.println(x);
                         x--;
                      }
                      
                  }
              }
              ====
              import static org.junit.Assert.*;
                import org.junit.*;
                import java.io.*;
                
                public class RunestoneTests extends CodeTestHelper
                {
                    @Test
                    public void testMain() throws IOException
                    {
                        String output = getMethodOutput("main");
                        String expect = "10\n9\n8\n7\n6\n5\n";

                        boolean passed = getResults(expect, output, "Expected output from main");
                        assertTrue(passed);
                    }
                }



..        .. tab:: Answer
        
           Answer: Remove the ``x--;`` at the end of the body of the loop.  The change area in the for loop decrements ``x`` by 1, so this line isn't needed. 
        
           .. activecode::  ch6ex6a
              :language: java
              :optional:
   
              public class TestLoop
              {
                  public static void main(String[] args)
                  {
                      for (int x = 10; x >= 5; x--)
                      {
                         System.out.println(x);
                      }
                      
                  }
              }
              
        
.. activecode::  code4_8_7
              :language: java
              :autograde: unittest
              :practice: T
   
              The following code should print the values from 10 to 1, but it has errors.  Fix the errors so that the code works as intended.
              ~~~~
              public class TestLoop
              {
                  public static void main(String[] args)
                  {
                      int x = 10;
                      while (x >= 0)
                      {
                         x--;
                         System.out.println(x);
                      } 
                  }
              }
              ====
              import static org.junit.Assert.*;
                import org.junit.*;
                import java.io.*;
               
                public class RunestoneTests extends CodeTestHelper
                {
                    @Test
                    public void testMain() throws IOException
                    {
                        String output = getMethodOutput("main");
                        String expect = "10\n9\n8\n7\n6\n5\n4\n3\n2\n1\n";

                        boolean passed = getResults(expect, output, "Expected output from main");
                        assertTrue(passed);
                    }
                }



..        .. tab:: Answer
        
           Answer: Move the ``x--;`` to the end of the loop body (after the ``System.out.println``.  Change the ``while`` to ``x > 0``.
           
           .. activecode::  ch6ex7na
              :language: java
              :optional:
   
              public class TestLoop
              {
                  public static void main(String[] args)
                  {
                      int x = 10;
                      while (x > 0)
                      {
                         System.out.println(x);
                         x--;
                      }
                  }
              }
              
           
.. activecode::  code4_8_8
              :language: java
              :autograde: unittest
              :practice: T
   
              Finish the code below to print a countdown from 100 to 0 by 10's using a for or while loop.
              ~~~~           
              public class TestLoop
              {
                  public static void main(String[] args)
                  {
                      
                      
                  }
              }
              ====
              import static org.junit.Assert.*;
                import org.junit.*;
                import java.io.*;
                
                public class RunestoneTests extends CodeTestHelper
                {
                  @Test
                  public void testMain() throws IOException
                  {
                    String output = getMethodOutput("main");
                    String expect = "100\n90\n80\n70\n60\n50\n40\n30\n20\n10\n0\n";

                    boolean passed = getResults(expect, output, "Expected output from main");
                    assertTrue(passed);
                    }

                     @Test
                    public void testForLoop() throws IOException
                    {
                       String code = getCode();
                       boolean passed = code.contains("for") || code.contains("while");
                       getResults("Expected loop",""+passed, "Checking for loop",passed);
                       assertTrue(passed);
                    }
                }

..        .. tab:: Answer
        
           Answer: You can use a ``for`` loop as shown below. Start ``x`` at 100, loop while it is greater or equal to 0, and subtract 10 each time after the body of the loop executes.
           
           .. activecode::  ch6ex8na
              :language: java
              :optional:
   
              public class TestLoop
              {
                  public static void main(String[] args)
                  {
                      for (int x = 100; x >= 0; x = x - 10)
                          System.out.println(x);
                  }
              }
         
.. activecode::  code4_8_9
              :language: java
              :autograde: unittest
              :practice: T   
  
              Finish the code to print the value of ``x`` and ``" is even"`` if ``x`` is even and ``" is odd"`` if it is odd for all values from 10 to 1. 
              ~~~~
              public class TestLoop
              {
                  public static void main(String[] args)
                  {
                      
                  }
              }
              ====
              import static org.junit.Assert.*;
                import org.junit.*;
                import java.io.*;
                
                public class RunestoneTests extends CodeTestHelper
                {
                    @Test
                    public void testMain() throws IOException
                    {
                        String output = getMethodOutput("main");
                        String expect = "10 is even\n9 is odd\n8 is even\n7 is odd\n6 is even\n5 is odd\n4 is even\n3 is odd\n2 is even\n1 is odd\n";

                        boolean passed = getResults(expect, output, "Expected output from main");
                        assertTrue(passed);
                    }

                     @Test
                    public void testIfLoop()
                    {
                       String code = getCode();
                       boolean passed = code.contains("if") && (code.contains("for") || code.contains("while"));
                       getResults("Expected loop and if",""+passed, "Checking for loop and if statement",passed);
                        assertTrue(passed);
                    }
                }

              


..        .. tab:: Answer
        
           Answer: Use a ``for`` loop to loop from 10 to 1.  Use a conditional to test if x is even (x % 2 == 0).  
           
           .. activecode::  ch6ex10na
              :language: java
              :optional:
   
              public class TestLoop
              {
                  public static void main(String[] args)
                  {
                      for (int x = 10; x >= 1; x--)
                      {
                          if (x % 2 == 0)
                              System.out.println(x + " is even");
                          else
                              System.out.println(x + " is odd");
                      }
                  }
              }
              
      
.. activecode::  code4_8_10
              :language: java
              :autograde: unittest
              :practice: T
     
              Finish the code below to print the values for ``10 * x`` where ``x`` changes from 0 to 10 using a loop.
              ~~~~
              public class TestLoop
              {
                  public static void main(String[] args)
                  {
                      
                  }
              }
              ====
              import static org.junit.Assert.*;
                import org.junit.*;
                import java.io.*;
                
                public class RunestoneTests extends CodeTestHelper
                {
                    @Test
                    public void testMain() throws IOException
                    {
                        String output = getMethodOutput("main");
                        String expect = "0\n10\n20\n30\n40\n50\n60\n70\n80\n90\n100\n";

                        boolean passed = getResults(expect, output, "Expected output from main");
                        assertTrue(passed);
                    }
                     @Test
                    public void testForLoop() 
                    {
                       // String target = "for (";
                       // boolean passed = checkCodeContains("for loop", target);
                       String code = getCode();
                       boolean passed = code.contains("for") || code.contains("while");
                       getResults("Expected loop",""+passed, "Checking for loop",passed);
                       assertTrue(passed);
                    }
                }



..        .. tab:: Answer
           
           .. activecode::  ch6ex11na
              :language: java
              :optional:
   
              Answer: Use a ``for`` loop with ``x`` changing from 0 to 10 and print the value of ``x`` and ``10 * x``. 
              ~~~~
              public class TestLoop
              {
                  public static void main(String[] args)
                  {
                      for (int x = 0; x <= 10; x++)
                      {
                         System.out.println(x * 10);             
                      }
                  }
              }
              
           
.. activecode::  code4_8_11
              :language: java
              :autograde: unittest
              :practice: T
  
              Finish the following code so that it prints a string message minus the last character 
              each time through the loop until there are no more characters in message.   
              The loop condition should test the length of the message.
              The loop body should print the message and then use substring to create a new message without the last character.  
              ~~~~       
              public class TestLoop
              {
                  public static void main(String[] args)
                  {
                         String message = "help";

                  }
              }
              ====
              import static org.junit.Assert.*;
                import org.junit.*;
                import java.io.*;

                public class RunestoneTests extends CodeTestHelper
                {
                    @Test
                    public void testMain() throws IOException
                    {
                        String output = getMethodOutput("main");
                        String expect = "help\nhel\nhe\nh\n";
                        boolean passed = getResults(expect, output, "Expected output from main");
                        assertTrue(passed);
                    }
                    @Test
                    public void testForLoop() 
                    {
                       String code = getCode();
                       boolean passed = code.contains("for") || code.contains("while");
                       getResults("Expected loop",""+passed, "Checking for loop",passed);
                       assertTrue(passed);
                    }
                }



..        .. tab:: Answer
        
           Answer: Add a ``while`` loop and loop while there is still at least one character in the string. At the end of the body of the loop reset the message to all characters except the last one.   
          
           .. activecode::  ch6ex9na
              :language: java
              :optional:
   
              public class TestLoop
              {
                  public static void main(String[] args)
                  {
                      String message = "help";
                      while (message.length() > 0)
                      {
                          System.out.println(message);
                          message = message.substring(0,message.length() - 1);
                      }
                  }
              }

              
           
.. activecode::  code4_8_12
              :language: java
              :autograde: unittest
              :practice: T
   
              Finish the code to loop printing the message each time through the loop and remove an ``x`` from the message until all the ``x``'s are gone. 
              ~~~~
              public class TestLoop
              {
                  public static void main(String[] args)
                  {
                      String message = "Ix lovex youxxx";
                      System.out.println(message);
                      
                      
                  }
              }
              ====
              import static org.junit.Assert.*;
                import org.junit.*;
                import java.io.*;
                //import java.util.regex.*;
                /* Do NOT change Main or CodeTestHelper.java. */
                public class RunestoneTests extends CodeTestHelper
                {
                    @Test
                    public void testMain() throws IOException
                    {
                        String output = getMethodOutput("main");
                        String expect = "Ix lovex youxxx\nI lovex youxxx\nI love youxxx\nI love youxx\nI love youx\nI love you\n";

                        boolean passed = getResults(expect, output, "Expected output from main");
                        assertTrue(passed);
                    }
                     @Test
                    public void testForLoop() 
                    {
                       String code = getCode();
                       boolean passed = code.contains("for") || code.contains("while");
                       getResults("Expected loop",""+passed, "Checking for loop",passed);
                       assertTrue(passed);
                    }
                }

..        .. tab:: Answer
        
           Answer: Use a ``while`` loop.  Loop while ``x`` has been found in the message (using ``indexOf``).  Remove the ``x`` (using substring). Use indexOf again to get the position of the next ``x`` or -1 if there are none left in the message. 
           
           .. activecode::  ch6ex12na
              :language: java
              :optional:
   
              public class TestLoop
              {
                  public static void main(String[] args)
                  {
                      String message = "Ix lovex youxxx";
                      System.out.println(message);
                      int pos = message.indexOf("x");
                      while (pos >= 0)
                      {
                         message = message.substring(0,pos) + message.substring(pos+1);
                         pos = message.indexOf("x");
                         System.out.println(message);
                      }
                  }
              }
              
          
.. activecode::  code4_8_13
              :language: java
              :autograde: unittest
              :practice: T
  
              Write a loop below to print the number of ``x``'s in the string message.  Use the ``indexOf`` and ``substring`` methods.
              ~~~~
              public class TestLoop
              {
                  public static void main(String[] args)
                  {
                      String message = "xyxxzax";
                  }
              }
              ====
              import static org.junit.Assert.*;
                import org.junit.*;
                import java.io.*;
               
                public class RunestoneTests extends CodeTestHelper
                {
                    @Test
                    public void testMain() throws IOException
                    {
                        String output = getMethodOutput("main");
                        String expect = "4";

                        boolean passed = output.contains(expect);
                        getResults(expect, output, "Expected output from main", passed);
                        assertTrue(passed);
                    }
                    @Test
                    public void testForLoop() 
                    {
                       String code = getCode();
                       boolean passed = code.contains("for") || code.contains("while");
                       getResults("Expected loop",""+passed, "Checking for loop",passed);
                       assertTrue(passed);
                    }
                }

..        .. tab:: Answer
        
           Answer: Use indexOf to find the next ``x``.  Loop while pos is greater than or equal to 0.  Use substring to reset message beyond the next ``x``.   
           
           .. activecode::  ch6ex16na
              :language: java
              :optional:
   
              public class TestLoop
              {
                  public static void main(String[] args)
                  {
                      
                      String message = "xyxxzax";
                      int pos = message.indexOf("x");
                      int count = 0;
                      while (pos >= 0)
                      {
                          count++;
                          message = message.substring(pos+1);
                          pos = message.indexOf("x");
                      }
                      System.out.println("There were " + count + " x's");
                  }
              }
              
.. activecode::  code4_8_14
              :language: java
              :autograde: unittest
              :practice: T
   
              Write the code below to print a rectangle of stars (``*``) with 5 rows of stars and 3 stars per row. Hint: use nested for loops.
              ~~~~
              public class TestLoop
              {
                  public static void main(String[] args)
                  {
                  }
              }
              ====
              import static org.junit.Assert.*;
                import org.junit.*;
                import java.io.*;
               
               public class RunestoneTests extends CodeTestHelper
               {
                    @Test
                    public void testMain() throws IOException
                    {
                        String output = getMethodOutput("main");
                        String expect = "***\n***\n***\n***\n***\n";

                        boolean passed = getResults(expect, output, "Expected output from main");
                        assertTrue(passed);
                    }
                     @Test
                    public void test2() {
                        String code = getCode();
                        String target = "for (int * = #; * ? *; *~)";

                        int num = countOccurencesRegex(code, target);

                        boolean passed = num == 2;

                        getResults("2", ""+num, "2 For loops (nested)", passed);
                        assertTrue(passed);
                    }
                }

..        .. tab:: Answer
        
           Answer: Use nested ``for`` loops.  Use the outer loop to control the number of rows and the inner loop to control the number of stars per row. 
           
           .. activecode::  ch6ex14na
              :language: java
              :optional:
   
              public class TestLoop
              {
                  public static void main(String[] args)
                  {
                      for (int row = 0; row < 5; row++)
                      {
                         for (int col = 0; col < 3; col++)
                         {
                             System.out.print("*");
                         }
                         System.out.println();
                      }
                  }
              }
              
           
.. activecode::  code4_8_15
              :language: java
              :autograde: unittest
              :practice: T
   
              Write the code below to print a rectangle of stars (``*``) with 3 rows of stars and 5 stars per row. 
              ~~~~
              public class TestLoop
              {
                  public static void main(String[] args)
                  {
                  }
              }
              ====
              import static org.junit.Assert.*;
                import org.junit.*;
                import java.io.*;
                
                public class RunestoneTests extends CodeTestHelper
                {
                    @Test
                    public void testMain() throws IOException
                    {
                        String output = getMethodOutput("main");
                        String expect = "*****\n*****\n*****\n";

                        boolean passed = getResults(expect, output, "Expected output from main");
                        assertTrue(passed);
                    }
                    @Test
                    public void test2() {
                        String code = getCode();
                        String target = "for (int * = #; * ? *; *~)";

                        int num = countOccurencesRegex(code, target);

                        boolean passed = num == 2;

                        getResults("2", ""+num, "2 For loops (nested)", passed);
                        assertTrue(passed);
                    }
                }



..        .. tab:: Answer
        
           Answer: Use nested ``for`` loops.  Use the outer loop to control the number of rows and the inner loop to control the number of stars per row. 
           
           .. activecode::  ch6ex15na
              :language: java
              :optional:
   
              public class TestLoop
              {
                  public static void main(String[] args)
                  {
                      for (int row = 0; row < 3; row++)
                      {
                         for (int col = 0; col < 5; col++)
                         {
                             System.out.print("*");
                         }
                         System.out.println();
                      }
                  }
              }
              

.. activecode::  code4_8_16
              :language: java
              :autograde: unittest
              :practice: T
   
              Write the code below to print 55555, 4444, 333, 22, 1 with each on a different line. 
              ~~~~
              public class TestLoop
              {
                  public static void main(String[] args)
                  {
                  }
              }    
              ====
              import static org.junit.Assert.*;
                import org.junit.*;
                import java.io.*;
                
                public class RunestoneTests extends CodeTestHelper
                {
                    @Test
                    public void testMain() throws IOException
                    {
                        String output = getMethodOutput("main");
                        String expect = "55555\n4444\n333\n22\n1\n";
                        boolean passed = getResults(expect, output, "Expected output from main");
                        assertTrue(passed);
                    }
                    @Test
                    public void test2() {
                        String code = getCode();
                        String target = "for (int * = #; * ? *; *~)";

                        int num = countOccurencesRegex(code, target);

                        boolean passed = num == 2;

                        getResults("2", ""+num, "2 For loops (nested)", passed);
                        assertTrue(passed);
                    }
                }



..        .. tab:: Answer
        
           Answer: Use nested ``for`` loops. The outer loop controls what is printed on each row and the number of rows.  The inner loop controls the number of values printer per row. 
           
           .. activecode::  ch6ex13na
              :language: java
              :optional:
   
              public class TestLoop
              {
                  public static void main(String[] args)
                  {
                      for (int x = 5; x >= 1; x--)
                      {
                         for (int y = x; y > 0; y--)
                         {
                             System.out.print(x);
                         }
                         System.out.println();
                      }
                  }
              }


  
   


   
