.. qnum::
   :prefix: 5-4-
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
  
Method Comments and Conditions
===============================

In industry you often produce code that other people will use and you will use code other people produced.  It is important
to document your code to facilitate understanding and reuse.


Method Comments
----------------

Recall that there are 3 types of comments in Java:

1. ``//`` Single line comment
2. ``/*`` Multiline comment ``*/``
3. ``/**`` Documentation comment ``*/``

.. |Java JDK| raw:: html

   <a href="https://www.oracle.com/technetwork/java/javase/downloads/index.html" target="_blank">Java JDK</a>

.. |javadoc| raw:: html

   <a href="https://www.tutorialspoint.com/java/java_documentation.htm" target="_blank">javadoc</a>

.. |String class| raw:: html

   <a href="http://docs.oracle.com/javase/7/docs/api/java/lang/String.html" target="_blank">String class</a>
   
The special characters ``//`` are used to mark the rest of the line as a comment in many programming languages.  If the comment is going to be multiple lines, we use ``/*`` to start the comment and ``*/`` to end the comment. 

The multi-line comment, ``/**``  ``*/`` is called the documentation comment. 
Java has a cool tool called |javadoc| that comes with the |Java JDK| that will pull out all of these 
comments to make documentation of a class as a web page.  This tool generates the official Java 
documentation too, for example for the |String class|. 
It's a good idea to use the documentation comment in front of classes, methods, and 
instance variables in case you want to use this tool. 

The are some special tags that you can use in Java documentation. These are not required but many programmers use them. Here are some common tags:

- @author  Author of the program
- @since   Date released
- @version Version of program 
- @param   Parameter of a method
- @return  Return value for a method

The code below shows example commenting for a class and two enclosed methods.

.. code-block:: java

    /**
    * The Converter program implements an application that
    * converts inches to centimeters and prints
    * the equivalent quantities.
    *
    * @author  Fred Smith
    * @version 1.0
    * @since   2020-01-31
    */
    public class Converter {

        /**
        * This method is used to convert inches to centimeters.
        * @param inches A double representing a quantity of inches.
        * @return double The equivalent quantity of centimeters.
        */
        public static double inchesToCentimeters(double inches)
        {
            return inches * 2.54;
        }

        /**
        * The main method demonstrates use of the inchesToCentimeters method.
        * @param args Unused.
        * @return Nothing.
        */
        public static void main(String[] args)  
        {
            System.out.println("10 inches = " + inchesToCentimeters(10) + " centimeters");
            System.out.println("15.7 inches = " + inchesToCentimeters(15.7) + " centimeters");
        }


    }

 
Preconditions and  Postconditions
---------------------------------

As you write methods in a class, it is a good idea to keep in mind the **preconditions** and the **postconditions** for the method and write them in the comments. A precondition is a condition that must be true for your method code to work, for example the assumption that the parameters have values and are not null. The methods could check for these preconditions, but they do not have to. The precondition is what the method expects in order to do its job properly.

A postcondition is a condition that is true after running the method. It is what the method promises to do. Postconditions describe the outcome of running the method, for example what is being returned or the changes to the instance variables. These assumptions are very useful to other programmers who want to use your class and get the correct results.   

Let's consider the substring method in Java. This method has a strong precondition that its arguments refer to indices within the given string. 

|CodingEx| **Coding Exercise**

.. activecode:: code5_4_1
    :language: java
    :autograde: unittest

    The following code breaks the preconditions of the substring method and throws an IndexOutOfBoundsException. Can you fix the code by changing the arguments for the substring method to print out the substring "lo"? What are the preconditions for the substring method?
    ~~~~
    public class SubstringPreconditions
    {
      public static void main(String[] args)
      {
          String str = "hello";
          System.out.println( str.substring(-1,10) );
      }
    }
    ====
    // Test for Lesson 5.3.2 Substring-preconditions
    import static org.junit.Assert.*;
    import org.junit.*;
    import java.io.*;

    public class RunestoneTests extends CodeTestHelper
    {
        public RunestoneTests() {
            super("SubstringPreconditions");
        }

        @Test
        public void testMain() throws IOException
        {
            String output = getMethodOutput("main");
            String expect = "lo";
            boolean passed = getResults(expect, output, "Expected output from main");
            assertTrue(passed);
        }
    }

.. note::
 
    The method str.substring(beginIndex, endIndex) has the precondition that 0 <= beginIndex <= endIndex <= str.length.
    
|Exercise| **Check your understanding**

.. mchoice:: q5_4_1
   :practice: T
   :answer_a: /* Precondition: i >= 0 */
   :answer_b: /* Precondition: i <= str.length() */
   :answer_c: /* Precondition: 0 < i < str.length() */
   :answer_d: /* Precondition: 0 <= i < str.length() */
   :correct: d
   :feedback_a: This is true but it could still throw an exception if i is a large value.
   :feedback_b: This is true but it could still throw an exception if i is a negative value.   
   :feedback_c: This is true but a little too restrictive.
   :feedback_d: Correct. i can refer to character 0 up to str.length().
      
   The following method is intended to return the substring starting at index i until the end of the string. For example, getiToEnd("012",1) should return "12". Which of the following is the most appropriate precondition for the method so that it does not throw an exception?

   .. code-block:: java

        /* missing precondition */
        public String getiToEnd(String str, int i)
        {
            return str.substring(i, str.length());
        }
    


