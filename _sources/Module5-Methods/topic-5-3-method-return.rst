  .. qnum::
   :prefix: 5-3-
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


.. |visualizer| raw:: html

   <a href="https://cscircles.cemc.uwaterloo.ca/java_visualize/">Java Visualizer</a>    

Method Returns
=================

A method bundles together lines of code that perform a specific task.

- You can pass values into a method using formal parameters. 
- You can pass a value out of a method using a **return statement**.  

You saw examples of  methods that return values in Unit 2 with the ``Turtle`` methods (getWidth, getXpos, etc).
The method calls were usually on the right hand side of an assignment, or they were contained in a print statement.
When a method returns a value, the code should do something with the value such as store it in a 
variable or print it.

You will learn how to  create methods that access object attributes in a later lesson. 
This lesson shows 
you how to create static methods that are functions. 
A function takes one or more values passed as formal parameters and computes a new value to return.


A method can return at most one value.  The method signature specifies the **return type**, which can be a primitive (int, double, boolean), 
a class (String, Turtle, etc), or void.

.. mchoice:: q5_3_1
   :answer_a: public
   :answer_b: static
   :answer_c: double
   :answer_d: volumeCylinder
   :correct: c
   :feedback_a: This is the access modifier.
   :feedback_b: This is the non-access modifier.
   :feedback_c: Correct. This is the return type.
   :feedback_d: This is the method name.
  
   This method computes the volume of a cylinder.  The method has formal parameters for radius and height, and returns a value representing the corresponding volume. 
   Given the method signature, what is the return type?

    .. figure:: Figures/volumeCylinder.png


Method Return Type
------------------

A **void** return type means the method does not return a value.
If a method has a **non-void** return type, then it must contain a **return statement** that specifies the value to return.
The return type must match with the value in the return statement.


Click on each tab to observe the data flowing into the method through the formal parameters and out of the method through the return statement.

.. tabbed:: q5_3_2

    .. tab:: Tab 1

      The program starts at the first line of the main method.
      The red arrow shows that line 12 is next to execute, which will call the volumeCylinder function.
      
      .. figure:: Figures/frame1.png
 
    .. tab:: Tab 2

      The stack diagram shows a new frame was created for the volumeCylinder(4,10) method call. The new
      stack frame contains the formal parameter variables initialized to the actual argument values.   

      .. figure:: Figures/frame2.png

    .. tab:: Tab 3

      After line 6 is executed, the stack frame shows the computed value 502.6 will be returned 
      out of the method.  Where does the returned value go?  The call stack diagram indicates the value 
      is returned to line 12 of the main method, since that is the line of code that called the volumeCylinder method.

      .. figure:: Figures/frame3.png

    .. tab:: Tab 4

      The value was returned to the main method and line 12 assigns the value to the "vol" local variable.
      Line 13 is the next line to execute.

      .. figure:: Figures/frame4.png

    .. tab:: Tab 5

      Line 13 prints the value stored in the vol local variable.  The output window shows what was printed.

      .. figure:: Figures/frame5.png



.. activecode:: code5_3_1
  :language: java
    
  Use the CodeLens to step through the code.  Experiment with passing different values to the volumeCylinder method.

  ~~~~
  public class VolumeExample 
  {
    public static double volumeCylinder(double radius, double height) 
    {
      return Math.PI * radius * radius * height;
    }   

    public static void main(String args[])
    {
      // Calculate the volume of a cylinder  radius=4 and height=10
      double vol = volumeCylinder(4, 10);
      System.out.println(vol);
    }
  }

|CodingEx| **Coding Exercise**

.. activecode:: code5_3_2
  :language: java
  :autograde: unittest
  :practice: T
    
  The code below contains a method ``inchesToCentimeters`` that computes and prints the centimeter equivalent of the value passed into the inches parameter.
  Instead of printing the centimeter value inside the inchesToCentimeters method, you should update the  
  method to return the value and then move the printing to the main method.  You will have to change 
  the return type of the inchesToCentimeters method to match the type of the value being returned. 
  Update the ``main`` method to print the value returned by the ``inchesToCentiments`` method. 

  ~~~~
  public class InchesToCentimeters 
  {
    public static void inchesToCentimeters(double inches)
        {
            double centimeters = inches * 2.54;
            System.out.println(centimeters);
        }

        public static void main(String[] args)  
        {
            inchesToCentimeters(10);
            inchesToCentimeters(12.5);
        }
  }

  ====
  import static org.junit.Assert.*;
  import org.junit.*;;
  import java.io.*;

  public class RunestoneTests extends CodeTestHelper
  {
    
    public RunestoneTests() {
      super("InchesToCentimeters");
    }

    @Test
    public void checkCodeContainsSig(){
      String code = getCode();
      int num = countOccurences(code, "public static double inchesToCentimeters(double inches)");
      boolean passed = num ==1;
      passed = getResults("1 signature", num + " signature", "Return type of inchesToCentimeters method", passed);
      assertTrue(passed);
    }

    @Test
    public void checkCodeContainsReturn(){
      String code = getCode();
      int num = countOccurences(code, "return");
      boolean passed = num ==1;
      passed = getResults("1 return", num + " return" , "Return statement in inchesToCentiments method", passed);
      assertTrue(passed);
    }

    @Test
    public void testMain() throws IOException
    {
          String output = getMethodOutput("main");
          String expect = "25.4\n31.75";
          boolean passed = output.contains(expect);
          getResults(expect, output, "Expected output from main");
          assertTrue(passed);
    }
  }


|Exercise| **Check your understanding**

.. mchoice:: q5_3_3
   :practice: T
   :answer_a: return "hello";
   :answer_b: return true;
   :answer_c: return 7.5;
   :answer_d: return 10;
   :correct: d
   :feedback_a: The method return type int does not match the return statement type String. 
   :feedback_b: The method return type int does not match the return statement type boolean.
   :feedback_c: The method return type int does not match the return statement type double.
   :feedback_d: The method return type int matches the return statement type int.
   
   Based on the method header below, which return statement has the correct type?  
    
   .. code-block:: java

     public static int mystery()


.. mchoice:: q5_3_4
   :practice: T
   :answer_a: return "hello";
   :answer_b: return true;
   :answer_c: return "true";
   :answer_d: return 10;
   :correct: b
   :feedback_a: The method return type boolean does not match the return statement type String. 
   :feedback_b: The method return type boolean matches the return statement type boolean.
   :feedback_c: The method return type boolean does not match the return statement type String.
   :feedback_d: The method return type boolean does not match the return statement type int.
   
   Based on the method header below, which return statement has the correct type?  
    
   .. code-block:: java

     public static boolean mystery2()


.. mchoice:: q5_3_5
   :practice: T
   :answer_a: String result = mystery3();
   :answer_b: int result = mystery3();
   :answer_c: boolean result = mystery3();
   :correct: b
   :feedback_a: The method return type int does not match the variable type String. 
   :feedback_b: The method return type int matches the variable type int.
   :feedback_c: The method return type int does not match the variable type boolean.
   
   Based on the method header below, which assignment statement is correct?  
    
   .. code-block:: java

     public static int mystery3()


.. mchoice:: q5_3_6
   :practice: T
   :answer_a: String result = mystery4();
   :answer_b: int result = mystery4();
   :answer_c: boolean result = mystery4();
   :answer_d: mystery4();
   :correct: d
   :feedback_a: A void return type means no value is returned.  There is no value to assign. 
   :feedback_b: A void return type means no value is returned.  There is no value to assign. 
   :feedback_c: A void return type means no value is returned.  There is no value to assign. 
   :feedback_d: A void return type means no value is returned.  You call the method as a statement.
   
   Based on the method header below, which statement is correct for calling the method?  
    
   .. code-block:: java

     public static void mystery4()


.. mchoice:: q5_3_7
   :practice: T
   :answer_a: return 10;
   :answer_b: return 12 * 4;
   :answer_c: return 15 / 2;
   :answer_d: return 3.7 ;
   :correct: d
   :feedback_a: The method return type int matches the return statement type int.
   :feedback_b: The method return type int matches the return statement type int.
   :feedback_c: The method return type int matches the return statement type int.
   :feedback_d: The method return type int does not match the return statement type double.
   
   Based on the method header below, which return statement DOES NOT have the correct type?  
    
   .. code-block:: java

     public static int mystery()


|CodingEx| **Coding Exercise**

.. activecode:: code5_3_3
  :language: java
  :autograde: unittest
  :practice: T
  
  A pedometer estimates that taking 2,000 steps is the same as walking 1 mile. 
  Write a method ``convertToMiles`` that takes a parameter for the number of steps and returns the equivalent miles walked.
  Update the main method to call ``convertToMiles`` 3 times with values 500, 2000, 3000. 
  Carefully consider the method return type.  Watch out for integer division in the method body!
  You can assume the number of steps is an integer.

  ~~~~
  public class StepCounter 
  {
      //add convertToMiles method here

      public static void main(String[] args)  
      {
         System.out.println("500 steps is equal to " + convertToMiles(500) + " miles");
         //add 2 more method calls here for 2000 and 3000 steps.

      }
  }

  ====
  import static org.junit.Assert.*;
  import org.junit.*;;
  import java.io.*;

  public class RunestoneTests extends CodeTestHelper
  {
    
    
     @Test
    public void checkCodeContainsSig()
    {
      String code = getCode();
      int num = countOccurences(code, "public static double convertToMiles(int");
      boolean passed = num ==1;
      passed = getResults("1 signature", num + "signature", "The convertToMiles signature is not correct. Check your return type and the parameter type", passed);
      assertTrue(passed);
    }

    @Test
    public void checkCodeContainsReturn()
    {
      String code = getCode();
      int num = countOccurences(code, "return");
      boolean passed = num ==1;
      passed = getResults("1 return", num + " return", "The method convertToMiles is missing a return statement", passed);
      assertTrue(passed);
    }


    @Test
    public void testMain() throws IOException
    {
          String output = getMethodOutput("main");
          String expect = "500 steps is equal to 0.25 miles\n2000 steps is equal to 1.0 miles\n3000 steps is equal to 1.5 miles";
          boolean passed = output.equals(expect);
          getResults(expect, output, "Expected output from main");
          assertTrue(passed);
    }
  }


|CodingEx| **Coding Exercise**

.. activecode:: code5_3_4
  :language: java
  :autograde: unittest
  :practice: T
  
  Write a function ``randomInteger`` that takes two integer 
  parameters ``min`` and ``max`` and returns a random integer value between min and max (inclusive).
  Have the main method call the function with different values.  You might want to go back and 
  review random number generation in Unit 2-9.

  ~~~~
  public class RandomNumberInRange 
  {
      //add your method here

      public static void main(String args[])  
      {
         //test your method by calling it

      }
  }

  ====
  import static org.junit.Assert.*;
  import org.junit.*;;
  import java.io.*;

  public class RunestoneTests extends CodeTestHelper
  {
    
    public RunestoneTests() {
      super("RandomNumberInRange");
    }

    @Test
    public void checkCodeContainsSig(){
      String code = getCode();
      int num = countOccurences(code, "public static int randomInteger(int min, int max");
      boolean passed = num ==1;
      passed = getResults("1 signature", num + " signature" , "The randomInteger signature is not correct. Check your return type and the parameters", passed);
      assertTrue(passed);
    }

    @Test
    public void checkCodeContainsReturn(){
      String code = getCode();
      int num = countOccurences(code, "return");
      boolean passed = num ==1;
      passed = getResults("1 return", num + " return", "The method randomInteger is missing a return statement", passed);
      assertTrue(passed);
    }

    @Test
      public void test1()
      {
          String code = getCode();
          int numRandom = countOccurences(code, "Math.random()");

          boolean passed = numRandom >= 1;
          passed = getResults("1+", ""+numRandom, "1 call to Math.random()", passed);
          assertTrue(passed);
      }

  }


Summary
-------

- A method can return at most one value

- The method signature must specify the return type

- A void return type indicates the method does not return a value

- The return statement is used to return a value

- The return statement causes control to immediately transfer out of the method.