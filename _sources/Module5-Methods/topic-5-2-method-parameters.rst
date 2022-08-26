.. qnum::
   :prefix: 5-2-
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

   
Method Parameters
=================

Consider two verses in the "Old MacDonald" song:

.. table:: 
  :align: left
  :widths: auto

  ===================================  ===================================  
             Verse 1                             Verse 2                
  ===================================  ===================================
   Old MacDonald had a farm            Old MacDonald had a farm          
   E-I-E-I-O                           E-I-E-I-O                        
   And on that farm he had a **cow**   And on that farm he had a **duck**   
   E-I-E-I-O                           E-I-E-I-O                        
   With a **moo-moo** here             With a **quack-quack** here          
   And a **moo-moo** there             And a **quack-quack** there          
   Here a **moo**, there a **moo**     Here a **quack**, there a **quack**      
   Everywhere a **moo-moo**            Everywhere a **quack-quack**         
   Old MacDonald had a farm            Old MacDonald had a farm         
   E-I-E-I-O                           E-I-E-I-O                        
  ===================================  ===================================

    
Each verse is identical, except for the animal (cow vs duck) and the noise (moo vs quack).
We can create a method named **verse** to abstract the repetitive lines, 
but the method will need two **formal parameters**, which are placeholders that allow 
different values to be substituted for the animal and noise when the method is called. 
The method body will use the formal parameter variables to customize the 
print statements. 

.. code-block:: java

     public static void verse( String animal, String noise ) 
     {
       System.out.println( "Old MacDonald had a farm" );
       System.out.println( "E-I-E-I-O" );
       System.out.println( "And on that farm he had a " + animal );
       System.out.println( "E-I-E-I-O" );
       System.out.println( "With a " + noise + "-" + noise + " here") ;
       System.out.println( "And a " + noise + "-" + noise + " there" );
       System.out.println( "Here a " + noise + ", there a " + noise );
       System.out.println( "Everywhere a " + noise + "-" + noise );
       System.out.println( "Old MacDonald had a farm" );
       System.out.println( "E-I-E-I-O" );
     }


When you call the method, you provide values between the parentheses, called **actual arguments** or **actual parameters**, that are 
copied into the formal parameter variables. 

.. code-block:: java

      verse( "cow", "moo" );
      verse( "duck", "quack" );

The main method will call the verse method twice, once for the cow and once for the duck.  
The call stack diagram shown below corresponding to the ``verse( "cow" , "moo" );``  method call.  
If you look at the frame on the call stack for the ``verse`` method, it
contains not only the current line but also the formal parameter variables and values.  The print statements will use the formal parameter variables to customize the output.


.. figure:: Figures/stackframesong.png


.. activecode:: code5_2_1
  :language: java
  :autograde: unittest
  :practice: T
  
  Update the main method to add a third verse to the song with another animal and noise. Use the CodeLens button to step through the code.
  ~~~~
  public class Song 
  { 
  
    public static void verse(String animal, String noise) 
    {
      System.out.println( "Old MacDonald had a farm" );
      System.out.println( "E-I-E-I-O" );
      System.out.println( "And on that farm he had a " + animal );
      System.out.println( "E-I-E-I-O" );
      System.out.println( "With a " + noise + "-" + noise + " here") ;
      System.out.println( "And a " + noise + "-" + noise + " there" );
      System.out.println( "Here a " + noise + ", there a " + noise );
      System.out.println( "Everywhere a " + noise + "-" + noise );
      System.out.println( "Old MacDonald had a farm" );
      System.out.println( "E-I-E-I-O" );
    }

    public static void main(String[] args) 
    {
      verse( "cow" , "moo" );
      verse( "duck" , "quack" );
    }
  }
  ====
  import static org.junit.Assert.*;
  import org.junit.*;;
  import java.io.*;

  public class RunestoneTests extends CodeTestHelper
  {
    
    public RunestoneTests() {
      super("Song");
    }

    @Test
    public void test1()
    {
      String code = getCode();
      int numVerses = countOccurences(code, "verse(");
      numVerses--; //exclude definition
      boolean passed = numVerses >= 3;
      
      passed = getResults("3 verses", numVerses + " verses", "Update the main with a third verse call", passed);
      assertTrue(passed);
    }
  }


 


Refactoring - Removing Duplicate Code
---------------------------------------

Sometimes a program has blocks of code that are similar, but not exactly the same.
The code might perform a similar function but with different values. 

We can introduce a method to perform a task that can be generalised by having formal parameter variables.  
The method can adapt to a variety of  situations
depending on the values passed into the method.  

The ``PayrollCalculator`` class listed below calculates and prints the weekly pay for two employees.  
Do you notice any redundancy?
  
 .. code-block:: java
 
  public class PayrollCalculator
  { 
  
    public static void main(String[] args) {

      double hourlyRate, hoursWorked, weeklyPay;
      String employee;

      //Calculate weekly pay for Fred
      employee = "Fred";
      hourlyRate = 12.50;
      hoursWorked = 20;
      weeklyPay = hourlyRate * hoursWorked;
      System.out.println(employee  + ":" + weeklyPay);
      
      //Calculate weekly pay for Amir 
      employee = "Amir";
      hourlyRate = 15.0;
      hoursWorked = 35;
      weeklyPay = hourlyRate * hoursWorked;
      System.out.println(employee  + ":" + weeklyPay);

    }

  }


The table below displays the code for each employee side by side.  The first three lines of code 
are the same except for
the value in the right hand side of each assignment, while the last two lines of code are identical.  


.. table:: 
  :align: left
  :widths: auto

  ================================================   =================================================
  Calculate pay for first employee                   Calculate pay for second employee                 
  ================================================   =================================================
  employee = "Fred";                                 employee = "Amir";
  hourlyRate = 12.50;                                hourlyRate = 15.0;
  hoursWorked = 20;                                  hoursWorked = 35;
  weeklyPay = hourlyRate * hoursWorked;              weeklyPay = hourlyRate * hoursWorked;
  System.out.println(employee  + ":" + weeklyPay);   System.out.println(employee  + ":" + weeklyPay);
  ================================================   =================================================
 
The redundant calculation and printing can be eliminated by adding a new method named ``calculatePay``.  
Three formal parameters are needed to allow different
values to be passed into the method: ``employee``, ``hourlyRate``, and ``hoursWorked``.  
The ``weeklyPay`` variable is declared in the method body, since its value is computed using the formal parameter variables.
A variable declared in a method is called a **local variable**. 

.. code-block:: java
 
  public static void calculatePay ( String employee, double hourlyRate, double hoursWorked)
  {
     double weeklyPay = hourlyRate * hoursWorked;
     System.out.println(employee  + ":" + weeklyPay);
  }
 
When the **calculatePay** method is called, actual values must be provided for each parameter:

.. code-block:: java

  calculatePay ( "Fred", 12.50, 20.0 );
  calculatePay ( "Amir", 15.00, 35.0 );

.. activecode:: code5_2_2
  :language: java
  :autograde: unittest
  :practice: T
    
  Update the code below to add the ``calculatePay`` method.  Update the ``main`` method to 
  call the ``calculatePay`` method twice to compute the pay for each employee.  
  Use the CodeLens button to confirm that your main method makes the two calls to calculatePay, with the correct values passed into the method.

  ~~~~
  public class PayrollCalculator
  { 

    //add a new static method calculatePay here
  


    public static void main(String[] args) 
    {
      
        //call calculatePay for employee Fred, hourly rate 12.50 and hours worked 20.0

        //call calculatePay for employee Amir, hourly rate 15.0 and hours worked 35.0

    }
  }
  ====
  import static org.junit.Assert.*;
  import org.junit.*;;
  import java.io.*;

  public class RunestoneTests extends CodeTestHelper
  {
    
    public RunestoneTests() {
      super("PayrollCalculator");
    }

    @Test
        public void test1()
        {
            String output = getMethodOutput("main");
            String expect = "Fred:250.0\nAmir:525.0\n";
            boolean passed = getResults(expect, output, "Expected output from main");
            assertTrue(passed);
        }

    @Test
        public void test2()
        {
           String code = getCode();
           int sig = countOccurences(code, "public static void calculatePay(");
           boolean passed = sig == 1;
           passed = getResults("1 method signature", sig + " method signature", "Add a new method calculatePay", passed);
           assertTrue(passed);
        }

    @Test
        public void test3()
        {
           String code = getCode();
           int calls = countOccurences(code, "calculatePay(\"");
           boolean passed = (calls==2);
           passed = getResults("2 calls", calls + " calls", "Update the main with two calls to calculatePay", passed);
           assertTrue(passed);
        }

  }



|Exercise| **Check your understanding**


.. mchoice:: q5_2_1
   :practice: T
   :answer_a: Chen 20.00 15.00
   :answer_b: Chen:300.0
   :answer_c: employee:weeklyPay
   :correct: b
   :feedback_a: Incorrect. The weeklyPay is computed as 20.00 * 15.00.  This result is used in the print statement.
   :feedback_b: Correct.
   :feedback_c: Incorrect. The actual values of the employee and weeklyPay variables will be printed.  
   
   What is printed by the method call:  calculatePay ( "Chen", 20.00, 15.00 ) ;


.. note:: 

  A call stack method frame stores formal parameter variables as well as local variables.

.. mchoice:: q5_2_2
   :practice: T
   :answer_a: Chris:125.0
   :answer_b: employee:weeklyPay
   :answer_c: "Chris":125.0
   :correct: a
   :feedback_a: Correct.
   :feedback_b: Incorrect. The actual values of the employee and weeklyPay variables will be printed.
   :feedback_c: Incorrect. The CodeLens tool just shows quotes to let you know the value is a String.  
   
   The figure shows the call stack after line 8 executed.  Notice the weeklyPay local variable is stored in the
   calculatePay method frame on the call stack.    What is printed when line 9 executes?

   .. figure:: Figures/stackframecalculatepay.png
  

When a method is called, the right method definition is found by 
checking the **method header** at the top of the method 
definition to match the name, number and type of arguments, and return type. 


.. mchoice:: q5_2_3
   :practice: T
   :answer_a: mystery("9");
   :answer_b: mystery(9);
   :answer_c: mystery(5, 7);
   :correct: b
   :feedback_a: The type of the actual argument "9" is String, but the formal parameter i is an int.
   :feedback_b: The type of the actual argument 9 and the formal parameter i are both int.
   :feedback_c: The method expects one int to be passed as an actual argument, not 2.  
   
   Based on the method header shown below, which method call is correct?  
   
   .. code-block:: java

     public static void mystery(int i)


.. mchoice:: q5_2_4
   :practice: T
   :answer_a: mystery("abc", 9);
   :answer_b: mystery("xyz", "9");
   :answer_c: mystery(9, 5);
   :correct: a
   :feedback_a: The actual argument and formal parameter types match.
   :feedback_b: The second parameter i has type int, while the second argument "9" is a string.
   :feedback_c: The method expects a string and an int as actual arguments, not two ints. 
   
   Based on the method header shown below, which method call is correct?  
   
   .. code-block:: java

     public static void mystery(String s, int i)

.. mchoice:: q5_2_5
   :practice: T
   :answer_a: mystery("true", "hello");
   :answer_b: mystery("hello", false);
   :answer_c: mystery(true, "hello");
   :correct: c
   :feedback_a: "true" is a String, not a boolean.
   :feedback_b: The first argument should be a boolean, and the second argument should be a String.
   :feedback_c: The actual argument and formal parameter types match. 
   
   Based on the method header shown below, which method call is correct?  
   
   .. code-block:: java

     public static void mystery(boolean b, String s)


.. mchoice:: q5_2_6
   :practice: T
   :answer_a: mystery("5");
   :answer_b: mystery(5);
   :answer_c: mystery(5, "5");
   :correct: b
   :feedback_a: Incorrect.  This will call the first method, which expects a String value.
   :feedback_b: Correct.  The second method expects an integer value.
   :feedback_c: Incorrect.  This will call the third method, which expects two values to be passed as arguments.
   
   A class can have several methods with the same name as long as the type or number of formal parameters is different. 
   You may recall from the constructor lesson that this is called "overloading".  
   Select the method call that causes the program to print ``second method 5``.

   .. code-block:: java

    public class TestArgumentPassing {
      public static void mystery ( String str )
      {
        System.out.println("first method " + str);
      }
      
      public static void mystery ( int num )
      {
        System.out.println("second method " + num);
      }
      
      public static void mystery ( int num , String str)
      {
        System.out.println("third method " + num + "," + str);
      }
      
      public static void main (String[] args)
      {
          
      }
	
    }



Variable Scope
---------------

A variable may be available for use in some lines of code, but not others. 
The **scope** of a variable is the region of the program that is it visible, which means it is accessible by name
and can be used in the code.

A variable declared inside a method is called a **local variable**.  
The scope of a local variable is the method body
in which it is declared. 
You can't use a variable before it is declared, so in fact the scope begins on the line that declares the variable
and continues until the last line of code in the method or block.    The local variable's memory location is  only available while 
the method is executing.  When the method completes, the memory location is released. If you called 
the method again, the old value is not available.  

.. activecode:: code5_2_3
  :language: java
    
  Use the CodeLens button to step through the two method calls in the main.  Notice the ``inches`` and ``centimeters`` variables are
  visible in the ``inchesToCentimeters`` method but not the ``main`` method.  
  ~~~~
  public class ScopeExample 
  {
    public static void inchesToCentimeters(double inches)
    {
        double centimeters = inches * 2.54;
        System.out.println(inches + "-->" + centimeters);
    }

    public static void main(String[] args)  
    {
        inchesToCentimeters(10);
        inchesToCentimeters(15.7);
    }

  }

The ``inchestToCentimeters`` method defines a local 
variable ``centimeters``, which is only visible inside that method. 
The main method can't see or use the variable.  Each time the inchestToCentimeters method is called, a new memory location is
created for the local variable.

A formal parameter is like a local variable in that its scope is the body of the corresponding method.   
The ``inches`` variable is only visible in the ``inchesToCentimeters`` method body. 


.. note::

   A local variable has its value initialized within the method body.

   A formal parameter has its value initialized by the method call.


You must explicitly assign a local variable a value before you can use it 
in a calculation.  The compiler will warn you if you try to use a local variable in a calculation or print statement before it has been assigned a value.

|Exercise| **Check your understanding**

.. mchoice:: q5_2_7
   :practice: T
   :answer_a: print1
   :answer_b: main
   :answer_c: print1 and main
   :correct: b
   :feedback_a: Method print1 accesses num, which is a formal parameter with method level scope.
   :feedback_b: Method main can accesses the local variable age, since it is declared in the main method.
   :feedback_c: Variable age is declared in the main method, so it can't be accessed in the print1 method.
   
   The variable ``age`` is visible in which method(s)?  
   
   .. code-block:: java

      public class Visibility {

        public static void print1(int num) {
          System.out.println("num is " + num);   
        }

        public static void main(String[] args) {
            int age = 20;
            print1(age);
        }
      }



.. mchoice:: q5_2_8
   :practice: T
   :answer_a: print1
   :answer_b: print2
   :answer_c: main
   :correct: b
   :feedback_a: Method print1 accesses num, which is a formal parameter with method level scope.
   :feedback_b: Method print2 accesses age, which is not accessible since it is declared in the main method.
   :feedback_c: Method main accesses age, which is a local variable with method level scope..
   
   Which method has a scope error (i.e. uses a variable that is not visible in that method)?  
   
   .. code-block:: java

      public class Visibility {

        public static void print1(int num) {
          System.out.println("num is " + num);   
        }

        public static void print2() {
          System.out.println("age is " + age);   
        }

        public static void main(String[] args) {
            int age = 20;
            print1(age);
            print2();
        }
      }


Method Tracing
------------------

.. |visualizeTrace| raw:: html

   <a href="http://pythontutor.com/visualize.html#code=public%20class%20TraceMethods%20%7B%0A%20%20public%20static%20void%20inchesToCentimeters%28double%20i%29%0A%20%20%7B%0A%20%20%20%20%20%20double%20c%20%3D%20i%20*%202.54%3B%0A%20%20%20%20%20%20printInCentimeters%28i,%20c%29%3B%0A%20%20%7D%0A%20%20%0A%20%20public%20static%20void%20printInCentimeters%28double%20inches,%20double%20centimeters%29%0A%20%20%7B%0A%20%20%20%20%20%20System.out.println%28inches%20%2B%20%22--%3E%22%20%2B%20centimeters%29%3B%0A%20%20%7D%0A%20%20%0A%20%20public%20static%20void%20main%28String%5B%5D%20args%29%0A%20%20%7B%0A%20%20%20%20%20%20inchesToCentimeters%2810%29%3B%0A%20%20%7D%0A%7D&cumulative=true&curInstr=6&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=java&rawInputLstJSON=%5B%5D&textReferences=false" target="_blank">visualizer</a>    
 
A method can call other methods to help it do its job.  


|Exercise| **Check your understanding**

.. mchoice:: q5_2_9
    :practice: T

    Consider the following methods:
    
    .. code-block:: java

        public static void inchesToCentimeters(double i)
        {
            double c = i * 2.54;
            printInCentimeters(i, c);
        }

        public static void printInCentimeters(double inches, double centimeters)
        {
            System.out.println(inches + "-->" + centimeters);
        }

        public static void main(String[] args)  
        {
            inchesToCentimeters(10);
        }

    What is printed when the main method is run?    It might help to draw out a stack diagram on paper, or use the CodeLens visualizer to step through the code.
    
    - inches --> centimeters
    
      - The values of the variables inches and centimeters should be printed out, not the words.
      
    - 10 -->  25
      
      - Two doubles should be printed, not two ints, and the centimeters should be 25.4
    
    - 25.4 --> 10
    
      - Inches should be printed before centimeters.
    
    - 10 --> 12.54
    
      - c = 10 * 2.54 = 25.4, not 12.54.
    
    - 10.0 --> 25.4
    
      + Correct! centimeters = 10 * 2.54 = 25.4. 




.. mchoice:: q5_2_10
    :practice: T
    
    Consider the following methods.

    .. code-block:: java
    
        public static void splitPizza(int numOfPeople)
        {
            int slicesPerPerson = 8/numOfPeople;
            /* INSERT CODE HERE */
        }

        public static void printSlices(int slices)
        {
            System.out.println("Each person gets " + slices + " slices each");
        }


    Which of the following lines would go into ``/* INSERT CODE HERE */`` in the method splitPizza in 
    order to call the ``printSlices`` method to print the number of slices per person correctly? 
    
    - printSlices(slicesPerPerson);
    
      + Correct! If you had 4 people, slicesPerPerson would be 8/4=2 and printSlices would print out "Each person gets 2 slices each".
      
    - printSlices(numOfPeople);
    
      - If you had 4 people, this would print out that they get 4 slices each of an 8 slice pizza.
      
    - printSlices(8);
    
      - This would always print out 8 slices each.
      
    - splitPizza(8);
    
      - This would not call the printSlices method.
      
    - splitPizza(slicesPerPerson);
    
      - This would not call the printSlices method.


|Exercise| **Check your understanding**

.. mchoice:: q5_2_11
   :practice: T
   :answer_a: 25 and 2
   :answer_b: 25 and .5
   :answer_c: 2 25
   :answer_d: 25 2
   :answer_e: Nothing, it does not compile.
   :correct: a
   :feedback_a: Correct.
   :feedback_b: The order of the arguments to the divide(x,y) method will divide x by y and return an int result.
   :feedback_c: The square(x) method is called before the divide(x,y) method.
   :feedback_d: The main method prints out " and " in between the method calls.
   :feedback_e: Try the code in the CodeLens visualizer.
   
   What does the following code print?
   
   .. code-block:: java
   
      public class MethodTrace 
      {
        public static void square(int x)
        {
            System.out.print(x*x);
        }
        public static void divide(int x, int y)
        {
            System.out.println(x/y);
        }
        public static void main(String[] args) {
            square(5);
            System.out.print(" and ");
            divide(4,2);
        }
       }




Pass by value
---------------

Java uses **pass by Value** when it passes arguments into a method. 
This means that a copy of the actual parameter value is stored in the formal parameter variable. 
The original value outside the method is not changed if a new value is assigned to the formal parameter within the method body.  **It is generally not a good idea to change the 
value of a formal parameter inside a method, however it is possible as the example below shows.**

|CodingEx| **Check your understanding**

.. activecode:: code5_2_4
  :language: java
    
  Use the CodeLens button to watch how the square method
  alters the value of x, while the value of y in the main method is not affected.

  Try changing the name of the variable in the main method to "x" and rerun the program.  You should see
  that the variable in the main method remains unaffected by changes made in the square method, even when 
  the variables have the same name.
  ~~~~
  public class CallByValue 
  {
    public static void square(int x)
    {
      x = x * x;  
      System.out.println(x);
    }

    public static void main(String[] args) 
    {
      int y = 5;
      square(y);  
      System.out.println(y); 
    }
  }



If you pass in an argument that holds a reference to an object, 
like a String or Person or Turtle object, a copy of this reference 
is passed in and saved in the parameter variable. You will explore 
this more in the following unit.


|Groupwork| Programming Challenge : Calculating Shipping Costs
---------------------------------------------------------------

The ShippingCostCalculator class listed below computes and prints the shipping cost for 3 different items based on their weight. 
The cost is 9.95 if the item weighs less than 15.0, otherwise the cost is 12.95.
While the if-else statements are not identical 
due to the different variables names (weight1 vs weight2 vs weight3, cost1 vs cost2 vs cost3),
each tests the weight and assigns the cost in the same way.  

.. code-block:: java

  public class ShippingCostCalculator {
    
    public static void main(String[] args) {
      
      double weight1, weight2, weight3;
      double cost1, cost2, cost3;

      weight1 = 22.0;  
      weight2 = 10.0;
      weight3 = 12.0;

      //calculate cost for item#1
      if (weight1 < 15.0)
      {
        cost1 = 9.95;
      }
      else 
      {
        cost1 = 12.95;
      }
      System.out.println(cost1);

      //calculate cost for item#2
      if (weight2 < 15.0)
      {
        cost2 = 9.95;
      }
      else 
      {
        cost2 = 12.95;
      }
      System.out.println(cost2);

      //calculate cost for item#3
      if (weight3 < 15.0)
      {
        cost3 = 9.95;
      }
      else 
      {
        cost3 = 12.95;
      }
      System.out.println(cost3);

      }
    }
    

The redundant code will be eliminated by adding a new method to 
compute and print the cost based on item weight.  

.. activecode:: code5_2_5
  :language: java
  :autograde: unittest  

  - Update the program below to add a new method  ``calculateShipping`` that has one formal parameter for ``weight``.  The method will need a local variable for ``cost``.  The method should test the weight and print the corresponding cost.
  - Update the main method to replace the existing code with 3 calls to ``calculateShipping``, each passing an actual value for weight.  The main method will no longer need local variables.
  - Confirm that the new version of the program produces the same output as the original version.

  ~~~~
  public class ShippingCostCalculator {
  
  public static void main(String[] args) {
    
     double weight1, weight2, weight3;
     double cost1, cost2, cost3;

     weight1 = 22.0;  
     weight2 = 10.0;
     weight3 = 12.0;

     //calculate cost for item#1
     if (weight1 < 15.0)
     {
        cost1 = 9.95;
     }
     else 
     {
        cost1 = 12.95;
     }
     System.out.println(cost1);

     //calculate cost for item#2
     if (weight2 < 15.0)
     {
        cost2 = 9.95;
     }
     else 
     {
        cost2 = 12.95;
     }
     System.out.println(cost2);

     //calculate cost for item#3
     if (weight3 < 15.0)
     {
        cost3 = 9.95;
     }
     else 
     {
        cost3 = 12.95;
     }
     System.out.println(cost3);

    }
  }
  ====
  import static org.junit.Assert.*;
    import org.junit.*;;
    import java.io.*;
    
    public class RunestoneTests extends CodeTestHelper
    {

    public RunestoneTests() {
      super("ShippingCostCalculator");
    }
      @Test
      public void checkSig(){
        String code = getCode();
        int num = countOccurences(code, "public static void calculateShipping(");
        boolean passed = num == 1;
        passed = getResults("1 method declaration", num + " method declaration", "Declare the static calculateShipping method", passed);
        assertTrue(passed);
      }

      @Test
      public void checkCodeContains3(){
        String code = getCode();
        int num = countOccurences(code, "calculateShipping(");
        num--;  //exclude method signature
        boolean passed = num ==3;
        passed = getResults("3 method calls", num + " method calls", "Call the calculateShipping method 3 times", passed);
        assertTrue(passed);
      }

      @Test
      public void testMain() throws IOException
      {
            String output = getMethodOutput("main");
            String expect = "12.95\n9.95\n9.95";
            boolean passed = output.contains(expect);
            getResults(expect, output, "Expected output from main");
            assertTrue(passed);
      }
    }


Summary
-------

- When you call a method, you can give or pass in values called **arguments** or **actual parameters** inside the parentheses. The arguments are saved in local **formal parameter** variables  that are declared in the method header.

- Values provided in the arguments in a method call need to correspond to the order and type of the parameters in the method signature.

- When an actual parameter is a primitive value, the formal parameter is initialized with a copy of that value. 

- New values assigned to the formal parameter within the method have no effect on the corresponding actual parameter.