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

.. activecode:: code1_6_1
   :language: java
   
   What happens when you divide an int by an int or with a double operand or with the type cast (double) on one of the operands?
   ~~~~
   public class OperatorTest
   {
      public static void main(String[] args)
      {
        System.out.println(1 / 3);
        System.out.println(1.0 / 3);
        System.out.println(1 / 3.0);
        System.out.println((double) 1 / 3);
        System.out.println((double) (1 / 3));
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
            String expect = "0\n0.3333333333333333\n0.3333333333333333\n0.3333333333333333\n";
            boolean passed = getResults(expect, output, "Expected output from main");
            assertTrue(passed);
        }
    }
	
Java assumes that if you are doing division with integers that you want an integer result and it will truncate and throw away the part after the decimal point.  But, if you use a mixture of integers (int) and decimal (double) numbers Java will assume that you want a double result. If there is at least one double in the operation, Java will widen the type of the other operand to double too and return the result in a double. If you have integers and you want a double result from some mathematical operation **cast** one of the integers to a double using (double) as shown above.  

Values of type double can be rounded to the nearest integer by adding or subtracting .5 and 
casting with (int) using formulas like the following. 

.. note::  

   int nearestInt = (int)(number + 0.5); 
   
   int nearestNegInt = (int)(negNumber – 0.5);


For example, if you divide 5/3 using integer division, Java will truncate 1.67 to 1 to give an int result. However, we usually round up any answer .5 and above. Using the formula above, if we add 1.67 + 0.50, we get 2.17 and then casting it to an int throws away what's after the decimal point, just leaving 2.  

.. activecode:: code1_6_2
   :language: java
   :autograde: unittest
   
   Run the code below to see how the formula of adding or subtracting .5 and then casting with (int) rounds a positive or negative double number to the closest int.
   ~~~~
   public class NearestInt
   {
      public static void main(String[] args)
      {
        double number = 5.0 / 3;
        int nearestInt = (int)(number + 0.5);
        System.out.println("5.0/3 = " + number);
        System.out.println("5/3 truncated: " + (int)number );
        System.out.println("5.0/3 rounded to nearest int: " + nearestInt);
        double negNumber = -number;
        int nearestNegInt = (int)(negNumber - 0.5);
        System.out.println("-5.0/3 rounded to nearest negative int: " + nearestNegInt);
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
            String expect = "5.0/3 = 1.6666666666666667\n5/3 truncated: 1\n5.0/3 rounded to nearest int: 2\n-5.0/3 rounded to nearest negative int: -2\n";

            boolean passed = getResults(expect, output, "Expected output from main", true);
            assertTrue(passed);
        }
     }


..	index::
	pair: double; number of digits


What happens to repeating decimal numbers like 3.333333...?  Java limits the number of digits you can save for any ``double`` number to about 14-15 digits. You should be aware that the accuracy of any calculation on a computer is limited by the fact that computers can only hold a limited number of digits. 

For example, int values are stored in 4 bytes of memory. There is an Integer.MAX_VALUE defined as 2147483647 and an Integer.MIN_VALUE defined as -2147483648. If you try to store any number larger or smaller than these numbers in an int variable, it will result in an error called **integer overflow**. Try it below.

.. activecode:: code1_6_3
   :language: java
   :autograde: unittest
   
   Try the code below to see two integer overflow errors for a positive and negative number. An int cannot hold that many digits! Fix the integer overflow error by deleting the last 0 in the numbers.
   ~~~~
   public class TestOverflow
   {
      public static void main(String[] args)
      {
        int id = 2147483650; // overflow error!
        int negative = -2147483650; // overflow 
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
            String expect = "214748365\n-214748365\n";

            boolean passed = getResults(expect, output, "Fixed Integer Overflow Error", true);
            assertTrue(passed);
        }
    }

..	index::
	pair: double; precision format
    
You can format long decimal numbers to just show 2 digits after the decimal point with the following code:

.. activecode:: code1_6_4
   :language: java
   :autograde: unittest
   
   Run the code below to see how a decimal number can be formatted to show 2 digits after the decimal point.
   ~~~~
   public class TestFormat
   {
      public static void main(String[] args)
      {
        double number = 10 / 3.0;
        System.out.println(number);
        System.out.println( String.format("%.02f", number) );
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
            String expect = "3.0\n3.00\n";

            boolean passed = getResults(expect, output, "Expected output from main", true);
            assertTrue(passed);
        }
    }


   

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
   
|Groupwork| Programming Challenge : Average 3 Numbers
------------------------------------------------------

In the code below, declare and initialize 3 int variables that represent grades, and then sum and average them. 
Use casting to report the result as a double. 
For example, if the grades are 90, 100, and 94, the sum of the three 
numbers is 90 + 100 + 94 = 284, and the average is the sum 284 divided by 3 which 
casted to a double is 94.666667. You should use variables instead of the numeric literals 
in your formulas. Follow the pseudocode below. 

 
.. |repl| raw:: html

   <a href="https://repl.it" target="_blank">repl.it</a>
   

.. |Scanner| raw:: html

   <a href="https://www.w3schools.com/java/java_user_input.asp" target="_blank">Scanner class</a>
   
   

.. activecode:: code1_6_5
   :language: java
   :autograde: unittest
   :stdin: 90 100 94
   :practice: T

   Sum and average 3 grades.   Your grade variables must have type int, not double. 
   Use type casting to compute the average as a double. 
   For an extra challenge, use a Scanner to read the grades from standard input.

   ~~~~
   public class Challenge1_6
   {
      public static void main(String[] args)
      {
         // 1. Declare 3 int variables called grade1, grade2, grade3
         // and initialize them to 3 values
  
         
         // 2. Declare an int variable called sum for the sum of the grades
         
         // 3. Declare a double variable called average for the average of the grades
         
         // 4. Write a formula to calculate the sum of the 3 grades (add them up). 
         
         // 5. Write a formula to calculate the average of the 3 grades from the sum using division and type casting.
         
         // 6. Print out the average
         
      
      }
   }
   ====
   import static org.junit.Assert.*;
    import org.junit.*;
    import java.io.*;

    public class RunestoneTests extends CodeTestHelper
    {

       @Test
       public void testAsgn1() throws IOException
       {
           String target = "sum = grade1 + grade2 + grade3;";
           boolean passed = checkCodeContains("formula for summing grades", target);
           assertTrue(passed);
       }
        @Test
       public void testAsgn2() throws IOException
       {
           String target = "average = (double) sum/3;";
           boolean passed = checkCodeContains("formula for average of 3 grades using sum and type casting to double", target);
           assertTrue(passed);
       }
    }


.. |Unicode| raw:: html

   <a href="https://en.wikipedia.org/wiki/List_of_Unicode_characters" target="_blank">Unicode</a>
   
.. |Chinese| raw:: html

   <a href="https://unicodelookup.com/#cjk/1" target="_blank">Chinese characters</a> 
   
.. |Unicode Lookup| raw:: html

   <a href="https://unicodelookup.com/" target="_blank">Unicode Lookup</a>
   
   
Summary
-------------------

- **Type casting** is used to convert variables from one type to another.
- The casting operators (int) and (double) can be used to create a temporary value converted to a different data type.
- Casting a double value to an int causes the digits to the right of the decimal point to be truncated (cut off and thrown away).

- Some programming code causes int values to be automatically cast (widened) to double values.
- Values of type double can be rounded to the nearest integer by (int)(x + 0.5) or (int)(x – 0.5) for negative numbers.

- Integer values in Java are represented by values of type int, which are stored using a finite amount (4 bytes) of memory. Therefore, an int value must be in the range from Integer.MIN_VALUE to Integer.MAX_VALUE inclusive.

- If an expression would evaluate to an int value outside of the allowed range, an integer overflow occurs. This could result in an incorrect value within the allowed range.
