.. qnum::
   :prefix: 1-10-
   :start: 1

Unit 1 Coding Practice
=======================

.. activecode::  code1_10_0a
              :language: java
              :autograde: unittest
              :practice: T

              Update the main method to calculate and print the perimeter of a rectangle having width 7 and height 9.
              Add another statement to calculate and print the area of the rectangle on a separate line.
              ~~~~
              public class RectangleTest
              {
                  public static void main(String[] args)
                  {
                      
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
                        String expect = "32\n63";
                        boolean passed = getResults(expect, output, "Expected output from main");
                        assertTrue(passed);
                    }
                    @Test
                    public void testPrintStringsA() throws IOException
                    {
                      String target1 = "+";
                      boolean passed1 = checkCodeContains("addition", target1);
                      String target2 = "*";
                      boolean passed2 = checkCodeContains("multiplication", target2);
                      
                      assertTrue(passed1 && passed2);
                    }
                
                }




.. activecode::  code1_10_0b
              :language: java
              :autograde: unittest
              :practice: T

              Update the main method to calculate and print the area of a triangle with base 7 and height 9.
              Recall the formula is 1/2bh.  Your solution must contain at least one multiplication and one division.
              Watch out for integer division!  int/int results in an int, while  int/double results in a double.
              ~~~~
              public class TriangleTest
              {
                  public static void main(String[] args)
                  {
                      
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
                        String expect = "31.5";
                        boolean passed = getResults(expect, output, "Expected output from main");
                        assertTrue(passed);
                    }
                    @Test
                    public void testPrintStringsA() throws IOException
                    {
                      String target1 = "/";
                      boolean passed1 = checkCodeContains("division", target1);
                      String target2 = "*";
                      boolean passed2 = checkCodeContains("multiplication", target2);
                      
                      assertTrue(passed1 && passed2);
                    }
                
                }




.. activecode::  code1_10_0c
              :language: java
              :autograde: unittest
              :practice: T

              R0 (pronounced R-naught) is a measure for predicting and controlling the transmission of disease.  If R0 is 3, then each person that
              has a disease will spread it on average to 3 other people.  The program below shows 4 iterations in the spread of SmallPox, 
              which has an R0 of 3.    The first person spreads to 3 people, each of whom spread to 3 people, etc.
              Update the program with additional print statements to show the spread after 4 iterations of 
              HIV (R0 of 4) and Measles (R0 of 16). 
              
              In Unit 4 you will learn a better way to solve this problem using loops.
              
              ~~~~
              public class R0Spread
              {
                  public static void main(String[] args)
                  {
                      System.out.println(1*3*3*3*3);
                      
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
                        String expect = "81\n256\n65536";
                        boolean passed = getResults(expect, output, "Expected output from main");
                        assertTrue(passed);
                    }
                    @Test
                    public void testPrintStringsA() throws IOException
                    {
                      String target1 = "*4";
                      boolean passed1 = checkCodeContains("*4", target1);
                      String target2 = "*16";
                      boolean passed2 = checkCodeContains("*16", target2);
                      
                      assertTrue(passed1 && passed2);
                    }
                
                }


.. tabbed:: ch4Ex2

        .. tab:: Question

           .. activecode::  code1_10_1
              :language: java
              :autograde: unittest
              :practice: T

              The following code should print "Mary's favorite color is blue".  
              However, the code has errors.  Fix the code so that it compiles and runs correctly.
              It is not an error for System.out.println to perform string concatenation across 
              several lines of code, but there is a problem with one of the variables in the print statement.
              ~~~~
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      String name = Mary";
                      String color = "blue"
                      System.out.println(Name +
                                         "'s favorite color is " + color);
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
                        String expect = "Mary's favorite color is blue";
                        boolean passed = getResults(expect, output, "Expected output from main");
                        assertTrue(passed);
                    }
                    @Test
                    public void testPrintStringsA() throws IOException
                    {
                      String target1 = "println(name +";
                      boolean passed1 = checkCodeContains("System.out.println with name variable", target1);
                      
                      assertTrue(passed1);
                    }
                    @Test
                    public void testPrintStringsB() throws IOException
                    {

                     String code = getCode();
                     int count = countOccurences(code, "+ color") ;
                     boolean passed = count >= 1;

                     passed = getResults("1 count", "" + count  + " count", "System.out.println uses string concatenation with color variable", passed);
                     assertTrue(passed);
                    }
                }

        .. tab:: Answer

           Line 5 is missing a starting ``"``.  Line 6 is missing a ending ``;``.  Line 7 has ``Name`` when it should be ``name``.  Remember that variable names start with a lowercase letter.

           .. activecode::  ch4Ex2a
              :language: java
              :optional:
              
              This is the answer to the previous question.
              ~~~~              
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      String name = "Mary";
                      String color = "blue";
                      System.out.println(name +
                                         "'s favorite color is " + color);
                  }
              }




.. activecode::  code1_10_2
              :language: java
              :autograde: unittest
              :practice: T

              The following code should print "Gabby's favorite sport is soccer".  However, the code has errors.  Fix the code so that it compiles and runs correctly.
              ~~~~
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      String name "Gabby";
                      String sport = "soccer;
                      System.out.println(Name +
                                         "'s favorite sport is "
                                         sport);
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
                        String expect = "Gabby's favorite sport is soccer";
                        boolean passed = getResults(expect, output, "Expected output from main");
                        assertTrue(passed);
                    }
                    @Test
                    public void testPrintStringsA() throws IOException
                    {
                      String target1 = "println(name +";
                      boolean passed1 = checkCodeContains("System.out.println with name variable", target1);
                      
                      assertTrue(passed1);
                    }
                    @Test
                    public void testPrintStringsB() throws IOException
                    {

                     String code = getCode();
                     int count = countOccurences(code, "+ sport") ;
                     boolean passed = count >= 1;

                     passed = getResults("1 count", "" + count  + " count", "System.out.println uses string concatenation with sport variable", passed);
                     assertTrue(passed);
                    }
                }


..        .. tab:: Answer

           Line 5 is missing a ``=``.  Line 6 is missing the closing ``"``.  Line 7 has ``Name`` when it should be ``name``.  Remember that a variable name starts with a lowercase letter.  Line 8 is missing an ending ``+``.

           .. activecode::  ch4Ex3a
              :language: java
              :optional:

              public class Test1
              {
                  public static void main(String[] args)
                  {
                      String name = "Gabby";
                      String sport = "soccer";
                      System.out.println(name +
                                         "'s favorite sport is " +
                                         sport);
                  }
              }



.. activecode::  code1_10_3
              :language: java
              :autograde: unittest
              :practice: T

              The following code should print "Your name is Carly and your favorite color is red".  Finish the code so that it prints the output correctly using the variables provided.
              ~~~~
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      String name = "Carly";
                      String color = "red";
                      System.out.println();
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
                        String expect = "Your name is Carly and your favorite color is red";
                        boolean passed = getResults(expect, output, "Expected output from main");
                        assertTrue(passed);
                    }
                    @Test
                    public void testPrintStringsA() throws IOException
                    {

                     String code = getCode();
                     int count = countOccurences(code, "+ name") ;
                     boolean passed = count >= 1;

                     passed = getResults("1 count", "" + count  + " count", "System.out.println uses string concatenation with name variable", passed);
                     assertTrue(passed);
                    }
                    @Test
                    public void testPrintStringsB() throws IOException
                    {

                     String code = getCode();
                     int count = countOccurences(code, "+ color") ;
                     boolean passed = count >= 1;

                     passed = getResults("1 count", "" + count  + " count", "System.out.println uses string concatenation with color variable", passed);
                     assertTrue(passed);
                    }
                }


.. .. tab:: Answer

           Add the required strings using the ``+`` operator and be sure to include spaces as needed.

           .. activecode::  ch4Ex5a
              :language: java
              :optional:
              
              This is the answer to the previous question.
              ~~~~              
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      String name = "Carly";
                      String color = "red";
                      System.out.println("Your name is " +
                                         name +
                                         " and your favorite color is " +
                                         color);
                   }
              }




.. activecode::  code1_10_4
              :language: java
              :autograde: unittest
              :practice: T

              Finish the code below so that it prints "Your name is Justin and your age is 16" using the variables provided.
              ~~~~
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      String name = "Justin";
                      int age = 16;
                      System.out.println();

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
                        String expect = "Your name is Justin and your age is 16";
                        boolean passed = getResults(expect, output, "Expected output from main");
                        assertTrue(passed);
                    }
                    @Test
                    public void testPrintStringsA() throws IOException
                    {

                     String code = getCode();
                     int count = countOccurences(code, "+ name") ;
                     boolean passed = count >= 1;

                     passed = getResults("1 count", "" + count  + " count", "System.out.println uses string concatenation with name variable", passed);
                     assertTrue(passed);
                    }
                    @Test
                    public void testPrintStringsB() throws IOException
                    {

                     String code = getCode();
                     int count = countOccurences(code, "+ age") ;
                     boolean passed = count >= 1;

                     passed = getResults("1 count", "" + count  + " count", "System.out.println uses string concatenation with age variable", passed);
                     assertTrue(passed);
                    }
                }


.. .. tab:: Answer

           Use the ``+`` operator to append the strings.  Be sure to include spaces as needed.

           .. activecode::  ch4Ex6a
              :language: java
              :optional:
              
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      String name = "Justin";
                      int age = 16;
                      System.out.println("Your name is " +
                                         name +
                                         " and your age is " +
                                         age);

                  }
              }




.. activecode::  code1_10_5
              :language: java
              :autograde: unittest
              :practice: T

              Write the code to print "Julian's favorite color is green.  
              His favorite food is pizza." using the variables provided.
              Watch out for spaces and the period at the end of each sentence.
              ~~~~
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      String name = "Julian";
                      String color = "green";
                      String food = "pizza";
                      System.out.println();
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
                        String expect = "Julian's favorite color is green. His favorite food is pizza.";
                        boolean passed = getResults(expect, output, "Expected output from main");
                        assertTrue(passed);
                    }
                    @Test
                    public void testPrintStringsA() throws IOException
                    {

                     String code = getCode();
                     int count = countOccurences(code, "+ color") ;
                     boolean passed = count >= 1;

                     passed = getResults("1 count", "" + count  + " count", "System.out.println uses string concatenation with color variable", passed);
                     assertTrue(passed);
                    }
                    @Test
                    public void testPrintStringsB() throws IOException
                    {

                     String code = getCode();
                     int count = countOccurences(code, "+ food") ;
                     boolean passed = count >= 1;

                     passed = getResults("1 count", "" + count  + " count", "System.out.println uses string concatenation with food variable", passed);
                     assertTrue(passed);
                    }
                }


..        .. tab:: Answer

           Add the strings together using ``+``.  Don't forget to include spaces and periods at the end of the sentences.

           .. activecode::  ch4Ex7a
              :language: java
              :optional:
              
              This is the answer to the previous question.
              ~~~~
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      String name = "Julian";
                      String color = "green";
                      String food = "pizza";
                      System.out.println(name + "'s favorite color is " + color +
                                         ".  His favorite food is " + food + ".");
                  }
              }


.. activecode::  code1_10_6
              :language: java
              :autograde: unittest
              :practice: T

              Finish the code below to print your favorite movie and book.
              ~~~~
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      String movie = "";
                      String book = "";
                      System.out.println();

                  }
              }
              ====
              import static org.junit.Assert.*;
                import org.junit.*;
                import java.io.*;
                
                public class RunestoneTests extends CodeTestHelper
                {
                   @Test
                    public void testPrintStringsA() throws IOException
                    {

                     String code = getCode();
                     int count = countOccurences(code, "+ movie") ;
                     boolean passed = count >= 1;

                     passed = getResults("1 count", "" + count  + " count", "System.out.println uses string concatenation with movie variable", passed);
                     assertTrue(passed);
                    }

                    @Test
                    public void testPrintStringsB() throws IOException
                    {

                     String code = getCode();
                     int count = countOccurences(code, "+ book") ;
                     boolean passed = count >= 1;

                     passed = getResults("1 count", "" + count  + " count", "System.out.println uses string concatenation with book variable", passed);
                     assertTrue(passed);
                    }


                }



..        .. tab:: Answer

           Add the strings together using ``+``.  Don't forget to include spaces and periods at the end of the sentences.

           .. activecode::  ch4Ex9a
              :language: java
              :optional:
              
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      String movie = "The Princess Bride";
                      String book = "Harry Potter";
                      System.out.println("My favorite movie is " + movie + ".  " +
                                         "My favorite book is " + book + ".");

                  }
              }




              

.. activecode::  code1_10_7
              :language: java
              :autograde: unittest
              :practice: T
   
              The following code should calculate the cost of a trip that is 300 miles if gas is $2.50 a gallon and your car gets 36 miles per gallon.  However, the code has syntax errors, like missing semicolons, wrong case on names, or unmatched ``"`` or ``(``.  Fix the code so that it compiles and runs correctly.
              ~~~~
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      int tripMiles = 300
                      Double price = 2.50;
                      int milesPerGallon = 30;
                      double numberOfGallons = tripmiles / milesPerGallon;
                      double totalCost = numberOfGallons * price;
                      System.out.println(totalCost);
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
                        String expect = "25.0";
                        boolean passed = getResults(expect, output, "Expected output from main");
                        assertTrue(passed);
                    }
                    @Test
                    public void testPrintStringsB() throws IOException
                    {

                     String code = getCode();
                     int count = countOccurences(code, "double price") ;
                     boolean passed = count >= 1;

                     passed = getResults("1 count", "" + count  + " count", "Declare the variable using type double, not Double", passed);
                     assertTrue(passed);
                    }
                }



..        .. tab:: Answer
        
           Line 5 is missing a semicolon.  Line 6 has ``Double`` instead of ``double``.  Remember that the primitive types all start with a lowercase letter.  Line 8 has ``tripmiles`` instead of ``tripMiles``.  Remember that you should uppercase the first letter of each new word to make the variable name easier to read (use camel case).
        
           .. activecode::  ch3Ex1a
              :language: java
              :optional:
 
              This is the answer for the previous question.
              ~~~~   
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      int tripMiles = 300;
                      double price = 2.50;
                      int milesPerGallon = 30;
                      double numberOfGallons = tripMiles / milesPerGallon;
                      double totalCost = numberOfGallons * price;
                      System.out.println(totalCost);
                  }
              }
              

.. activecode::  code1_10_8
              :language: java
              :autograde: unittest
              :practice: T
   
              The following code should calculate the number of miles that you can drive when you have $8.00 and the price of gas is 2.35 and the car gets 40 miles per gallon.  However, the code has errors.  Fix the code so that it compiles and runs correctly.
              ~~~~          
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      gallonPrice = 2.35;
                      40 = double milesPerGallon;
                      double totalFunds = 8.0;
                      double numGallons = totalFunds gallonPrice; 
                      double numMiles = numGallons * milesPerGallon;
                      System.out.println(numMiles;
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
                        String expect = "136.17021276595744\n";
                        boolean passed = getResults(expect, output, "Expected output from main");
                        assertTrue(passed);
                    }
                    @Test
                    public void testPrintStringsB() throws IOException
                    {
                     String target = "numGallons = totalFunds / gallonPrice";
                     boolean passed = checkCodeContains("formula for numGallons", target);
                     assertTrue(passed);
                    }
                    
                }



..        .. tab:: Answer
        
           Line 5 is missing the type ``double``.  Line 6 is backwards.  It should be ``double milesPerGallon = 40;``.  Line 8 is missing a ``/``.  Line 10 is missing a ``)``.
        
           .. activecode::  ch3Ex3a
              :language: java
              :optional:
              
              This is the answer to the previous question.
              ~~~~
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      double gallonPrice = 2.35;
                      double milesPerGallon = 40;
                      double totalFunds = 8.0;
                      double numGallons = totalFunds / gallonPrice; 
                      double numMiles = numGallons * milesPerGallon;
                      System.out.println(numMiles);
                  }
              }
              
     
.. activecode::  code1_10_9
              :language: java
              :autograde: unittest
              :practice: T
   
              The following code should calculate the cost of an item that is on clearance (70% off) when you also have a coupon for an additional 20% off the clearance price.  However, the code has errors.  Fix the code so that it compiles and runs correctly.
              ~~~~
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      int originalPrice = 68.00;
                      int clearancePrice = originalPrice * 0.3;
                      int finalPrice = clearancePrice * 0.8;
                      System.out.println(finalPrice);
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
                        String expect = "16.32\n";
                        boolean passed = getResults(expect, output, "Expected output from main");
                        assertTrue(passed);
                    }
                }



..        .. tab:: Answer
        
           Lines 5, 6, and 7 should all be ``double`` versus ``int`` so that the decimal portion of the calculation isn't thrown away.
        
           .. activecode::  ch3Ex4a
              :language: java
              :optional:
                 
              This is the answer to the previous question.
              ~~~~
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      double originalPrice = 68.00;
                      double clearancePrice = originalPrice * 0.3;
                      double finalPrice = clearancePrice * 0.8;
                      System.out.println(finalPrice);
                  }
              }
              
          
.. activecode::  code1_10_10
              :language: java
              :autograde: unittest
              :practice: T
   
              The following code should calculate the number of whole days in 320893 seconds. However, the code has errors.  Fix the code so that it compiles and runs correctly. 
              ~~~~
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      int numSecs = 320893;
                      int numHours = numSecs   3600;
                      int numDays = numHours   24;
                      System.out.println numDays);
                      
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
                        String expect = "3\n";
                        boolean passed = getResults(expect, output, "Expected output from main");
                        assertTrue(passed);
                    }
                }



..       .. tab:: Answer
        
           Lines 6 and 7 are both missing a ``/``.  Line 8 is missing a ``(``.  Line 9 is missing a ``}`` to close the ``main`` method.
        
           .. activecode::  ch3Ex5a
              :language: java
              :optional:
                 
              This is the answer to the previous question.
              ~~~~
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      int numSecs = 320893;
                      int numHours = numSecs / 3600;
                      int numDays = numHours / 24;
                      System.out.println(numDays);
                   }   
              }

.. activecode::  code1_10_11
              :language: java
              :autograde: unittest
              :practice: T
   
              Complete the code below to calculate and print how many months it will take to save $200 
              if you earn $20 a week.  First calculate how many weeks it would take to make $200, then
              calculate how many months it will take assuming there are 4 weeks per month. 
              ~~~~
              public class Test1
              {
                  public static void main(String[] args)
                  {
                    double goal = 
                    double weeklyRate = 
                    double numWeeks = 
                    double numMonths = 
                    System.out.println(numMonths);
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
                    String expect = "2.5\n";
                    boolean passed = getResults(expect, output, "Expected output from main");
                    assertTrue(passed);
                  }

                  @Test
                  public void testFormulaNumMonths() throws IOException
                  {
                    String target = "numMonths =  numWeeks / 4;";
                    boolean passed = checkCodeContains("formula for numMonths", target);
                    assertTrue(passed);
                    }
                }



..        .. tab:: Answer
        
           Calculate how many weeks it would take to make $200.  Next divide the number of weeks by 4 (roughly the number of weeks in a month).  
        
           .. activecode::  ch3Ex6a
              :language: java
              :optional:
                 
              This is the answer to the previous question.
              ~~~~
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      double weeklyRate = 20;
                      double goal = 200;
                      double numWeeks = goal / weeklyRate;
                      double numMonths = numWeeks / 4;
                      System.out.println(numMonths);
                  }
              }
              
            
.. activecode::  code1_10_12
              :language: java 
              :autograde: unittest
              :practice: T  
                
              Write the code to calculate the number of miles you can drive if you have a 10 gallon gas tank and are down to a quarter of a tank of gas and your car gets 32 miles per gallon.
              ~~~~
              public class Test1
              {
                  public static void main(String[] args)
                  {
                     // Your code should use the variables 
                     // numGallons, milesPerGallon, and miles
                     // and print out miles
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
                    String expect = "80.0\n";
                    boolean passed = getResults(expect, output, "Expected output from main");
                    assertTrue(passed);
                  }

                @Test
                  public void testFormulaMiles() throws IOException
                  {

                     String code = getCode();
                     int count1 = countOccurences(code, "double miles = numGallons * milesPerGallon") ;
                     int count2 = countOccurences(code, "double miles = milesPerGallon * numGallons") ;
                     
                    boolean passed = count1+count2 >= 1;

                    passed = getResults("1 count", "" + (count1 +count2)  + " count", "calculation for miles using numGallons and milesPerGallon", passed);
                    assertTrue(passed);
                  }  
                }



..        .. tab:: Answer
        
           First calculate the number of gallons you have left and then multiply that by the miles per gallon to get the number of miles you can still drive. 
        
           .. activecode::  ch3Ex7a
              :language: java
              :optional:
   
              This is the answer to the previous question.
              ~~~~
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      double numGallons = 10.0 / 4;
                      double milesPerGallon = 32;
                      double miles = numGallons * milesPerGallon;
                      System.out.println(miles);
                      
                  }
              }


.. activecode::  code1_10_13
              :language: java
              :autograde: unittest
              :practice: T
   
              Write the code to calculate the number of seconds in 3 days.  Remember that there are 60 seconds in a minute and 60 minutes in an hour and 24 hours in a day.
              ~~~~
              public class Test1
              {
                  public static void main(String[] args)
                  {
                     // Your code should use the variables
                     // secondsInDay and secondsInThreeDays
                     // and print out secondsInThreeDays
                      
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
                    String expect = "259200\n";
                    boolean passed = getResults(expect, output, "Expected output from main");
                    assertTrue(passed);
                  }

                @Test
                  public void testFormulaMiles() throws IOException
                  {
                    
                     String code = getCode();
                     int count1 = countOccurences(code, "int secondsInThreeDays = secondsInDay * 3") ;
                     int count2 = countOccurences(code, "int secondsInThreeDays = 3 * secondsInDay") ;
                     
                    boolean passed = count1+count2 >= 1;

                    passed = getResults("1 count", "" + (count1 +count2)  + " count", "formula for secondsInThreeDays using secondsInDay", passed);
                    assertTrue(passed);

                  } 
                } 


..        .. tab:: Answer
        
           First compute the number of seconds in 1 day and then multiple that by 3 days.
           
           .. activecode::  ch3Ex8a
              :language: java
              :optional:
 
              This is the answer to the previous question.
              ~~~~
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      int secondsInMinute = 60;
                      int minutesInHour = 60;
                      int hoursInDay = 24;
                      int secondsInDay = secondsInMinute * minutesInHour * hoursInDay;
                      int secondsInThreeDays = secondsInDay * 3;
                      System.out.println(secondsInThreeDays);
                  }
              }
           




.. activecode::  code1_10_14
              :language: java
              :autograde: unittest
              :practice: T
   
              Write the code to print the number of chicken wings you can buy if you have $4.50 and they cost $0.75 each.  
              Remember that you can't buy part of a wing.  Divide the amount of money you have by the cost of each wing and then use casting to set the 
              result to an int since you can't buy a part of a wing.
              ~~~~
              public class Test1
              {
                  public static void main(String[] args)
                  {
                    // Your code should use the variables
                    // money, pricePerWing, numWings 
                    // and print out numWings
                      
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
                    String expect = "6\n";
                    boolean passed = getResults(expect, output, "Expected output from main");
                    assertTrue(passed);
                  }

                  @Test
                  public void testFormulaWings() throws IOException
                  {
                    String target = "int numWings = (int)(money / pricePerWing);";
                    boolean passed = checkCodeContains("formula for numWings using money and pricePerWing, and type casting", target);
                    assertTrue(passed);
                  }  
                }



..        .. tab:: Answer
        
           Divide the amount of money you have by the cost of each wing and set the 
           result to an integer since you can't buy a part of a wing.
           
           .. activecode::  ch3Ex10a
              :language: java
              :optional:
                 
              This is the answer to the previous question.
              ~~~~
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      double money = 4.5;
                      double pricePerWing = 0.75;
                      int num = (int) (money / pricePerWing);
                      System.out.println(num);
                  }
              }
              