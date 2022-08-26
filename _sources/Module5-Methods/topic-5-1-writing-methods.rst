.. qnum::
   :prefix: 5-1-
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

..	index::    
	single: method 
    single: return
    single: parameter
    single: argument
    single: abstraction
    pair: method; parameter
    pair: method; argument
    pair: method; return 
    
Writing Methods
=================

Up until this unit, you wrote all  code in the main method, 
but now you will be creating new methods that can be called by the main method. 
Why have multiple methods instead of just one? 
**Procedural Abstraction** allows us to name a block of code as a method and 
call it whenever we need it, abstracting away the details of how it works.  
This serves to organize our code by function and reduce 
the repetition of code. In addition, it helps with debugging and maintenance since 
changes to that block of code only need to happen in one place. 
Here are some of the main reasons to use multiple methods in your programs:

- Reducing Complexity: Divide a problem into subproblems to solve it a piece at a time.
- Reusing Code: Avoid repetition of code. 
- Maintainability and Debugging: Smaller methods are easier to debug and understand.

Let's look at an example with repetition and then we will 
create a method to reduce the redundant code. 


.. clickablearea:: q5_1_1
    :question: Click on each line that occurs more than once in the song.
    :iscode:
    :feedback: Look for lines that are completely identical.  

    :click-incorrect:public static void main(String args[]) {:endclick:
        :click-correct:System.out.println("I'm looking over a four-leaf clover");:endclick:
        :click-correct:System.out.println("That I overlooked before");:endclick:
        :click-incorrect:System.out.println("One leaf is sunshine, the second is rain");:endclick:
        :click-incorrect:System.out.println("Third is the roses that grow in the lane");:endclick:
        :click-incorrect:System.out.println();:endclick:
        :click-incorrect:System.out.println("No need explaining, the one remaining");:endclick:
        :click-incorrect:System.out.println("Is somebody I adore");:endclick:
        :click-correct:System.out.println("I'm looking over a four-leaf clover");:endclick:
        :click-correct:System.out.println("That I overlooked before");:endclick:
    :click-incorrect:}:endclick:
            
The two-line chorus is 
repeated at the beginning and ending of the song. 

When you see duplicate lines of code, that is a signal for you to make a new method!
A method is a **named** set of statements.  When we want to execute the statements, 
we call the method using its name.
In a subsequent lesson you will create methods that are called using an object, 
referred to as **instance methods** or **object methods**.
The methods in this unit are called without an object, so they are  **static methods**.  
Static methods are also referred to as **class methods**.

.. note::
  static methods - can call without an object ``m()``

  instance methods - must call using an object  ``obj.m()``

Writing Static Methods
----------------------

There are two steps to writing and using a static method:

- Step 1. Method Definition
- Step 2. Method Call

You define a method by writing the method's **header** and **body**.  
The header is also called 
a method **signature**.  The parts of the main method header are shown in the figure below, 
which include an access modifier,
static modifier, return type, name, and formal parameters.   The method body 
consists of a set of statements enclosed in curly braces { }.  

.. mchoice:: q5_1_2
   :answer_a: public
   :answer_b: static
   :answer_c: void
   :answer_d: main
   :correct: d
   :feedback_a: This is the access modifier.
   :feedback_b: This is the non-access modifier.
   :feedback_c: This is the return type.
   :feedback_d: Correct.
  
   Given the method signature, what is the method name?

    .. figure:: Figures/methodsig.png


The code below contains a chorus() method definition 
that we could write to encapsulate the two lines that get repeated in the song.  

.. code-block:: java

    // Step 1: define a new method named chorus
    public static void chorus() 
    { 
        System.out.println("I'm looking over a four-leaf clover");
        System.out.println("That I overlooked before");
    }


Whenever you want to use a method, you call it using the method name followed by parentheses.
The method header ``public static void chorus()`` indicates the return type is void and there are no formal parameters
between the parentheses, which means you can call the method as shown:

.. code-block:: java

    // Step 2: call the chorus method
    chorus(); 

Notice that we can just call the static method, we don't need to create an object to use for calling the method.
The main method can call the chorus method multiple times to repeat the two lines of the song.
   
|CodingEx| **Coding Exercise**

.. activecode:: code5_1_1
  :language: java   
  :autograde: unittest    
  :practice: T

  Run the following code to see the song print out.  
  Notice the first line of code in the main method
  is a call to the new method ``chorus()``.
  Can you replace the last two print statements in the main 
  method with another call to the ``chorus()`` method? 
  Use the CodeLens to step through the program and notice what happens when the main method calls the chorus method.
  ~~~~
  public class Song 
  { 
    // The chorus method
    public static void chorus() 
    {
       System.out.println("I'm looking over a four-leaf clover");
       System.out.println("That I overlooked before");
    }

    public static void main(String args[]) 
    {
      chorus();
      System.out.println("One leaf is sunshine, the second is rain");
      System.out.println("Third is the roses that grow in the lane");
      System.out.println();
      System.out.println("No need explaining, the one remaining");
      System.out.println("Is somebody I adore");
      // Can you replace these 2 lines with a method call to chorus()?
      System.out.println("I'm looking over a four-leaf clover");
      System.out.println("That I overlooked before");
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
            String expect = "I'm looking over a four-leaf clover\nThat I overlooked before\nOne leaf is sunshine, the second is rain\nThird is the roses that grow in the lane\n\nNo need explaining, the one remaining\nIs somebody I adore\nI'm looking over a four-leaf clover\nThat I overlooked before";
            boolean passed = getResults(expect, output, "Expected output from main");
            assertTrue(passed);
        }

        @Test
        public void testcodeContains(){
          int count = countOccurences(getCode(),"chorus();");
          boolean passed = count > 1;
          passed = getResults("> 1 chorus call",  count  + " chorus call(s)", "Added second call to chorus?", passed);
          assertTrue(passed);
        }

    }
  
|Exercise| **Check Your Understanding**
   
.. clickablearea:: q5_1_3
    :question: A method definition consists of a method header and a method body. Click on the method header for the method named "greet" in the following code.
    :iscode:
    :feedback: There is one header for the greet method: public static void greet()
    
    :click-incorrect:public class GreetingExample:endclick:
    :click-incorrect:{:endclick:
        :click-correct:public static void greet():endclick:
        :click-incorrect:{:endclick:
            :click-incorrect:System.out.println("Hello!");:endclick:
            :click-incorrect:System.out.println("How are you?");:endclick:
        :click-incorrect:}:endclick:
        :click-incorrect: :endclick:
        :click-incorrect:public static void main(String[] args):endclick:
        :click-incorrect:{:endclick:
            :click-incorrect:System.out.println("Before greeting");:endclick:
            :click-incorrect:greet();:endclick:
            :click-incorrect:System.out.println("After greeting");:endclick:
        :click-incorrect:}:endclick:
    :click-incorrect:}:endclick:


   
.. clickablearea:: q5_1_4
    :question: Click on all statements contained within the greet method body.
    :iscode:
    :feedback: The greet method body consists of the 2 print statements nested between the curly braces that follow the method header.  
    
    :click-incorrect:public class GreetingExample:endclick:
    :click-incorrect:{:endclick:
        :click-incorrect:public static void greet():endclick:
        :click-incorrect:{:endclick:
            :click-correct:System.out.println("Hello!");:endclick:
            :click-correct:System.out.println("How are you?");:endclick:
        :click-incorrect:}:endclick:
        :click-incorrect: :endclick:
        :click-incorrect:public static void main(String[] args):endclick:
        :click-incorrect:{:endclick:
            :click-incorrect:System.out.println("Before greeting");:endclick:
            :click-incorrect:greet();:endclick:
            :click-incorrect:System.out.println("After greeting");:endclick:
        :click-incorrect:}:endclick:
    :click-incorrect:}:endclick:


   
.. clickablearea:: q5_1_5
    :question: Click on the greet method call.
    :iscode:
    :feedback: The greet method call occurs in the main method.  
    
    :click-incorrect:public class GreetingExample:endclick:
    :click-incorrect:{:endclick:
        :click-incorrect:public static void greet():endclick:
        :click-incorrect:{:endclick:
            :click-incorrect:System.out.println("Hello!");:endclick:
            :click-incorrect:System.out.println("How are you?");:endclick:
        :click-incorrect:}:endclick:
        :click-incorrect: :endclick:
        :click-incorrect:public static void main(String[] args):endclick:
        :click-incorrect:{:endclick:
            :click-incorrect:System.out.println("Before greeting");:endclick:
            :click-correct:greet();:endclick:
            :click-incorrect:System.out.println("After greeting");:endclick:
        :click-incorrect:}:endclick:
    :click-incorrect:}:endclick:


.. fillintheblank:: q5_1_6

   Given the GreetingExample class in the previous problem, how many times is  **System.out.println** called in total when the program runs?

   -    :4: Correct.  
        :.*: Incorrect. The main method calls System.out.println directly 2 times, and the call to greet() results in 2 additional calls to System.out.println.

Flow of Execution - Stack Diagrams
------------------------------------

A class can contain several methods.  It can be tempting to think the methods are executed in the order they
appear in the class, but this is not the case.

A program always begins at the first statement in the main method. 
Each statement in the main is executed one at a time until you reach a method call. 
A method call causes the program execution to jump to the first line of the called method. 
Each statement in the called method is then executed in order.
When the called method is done, the program returns back to the main method.

How does the program keep track of all of this?  
The Java runtime environment keeps track of the method calls using a **call stack**.
The call stack is made up of stack **frames**.  Each time a method is called, a new frame is created
and added to the stack. A frame contains the method’s parameters and local variables, along with the number of the current line that is about to be executed. 

The CodeLens Visualizer represents the call stack using a **stack diagram**, with each 
method frame drawn as a box.  When a method is called, a new frame is added to the bottom of the stack diagram.
You can tell which method is currently executing by looking at the bottom of the stack. 

|Exercise| **Check your understanding**

.. |visualizeTrace| raw:: html

   <a href="http://pythontutor.com/visualize.html#code=public%20class%20GreetingExample%0A%7B%0A%20%20%20%20public%20static%20void%20greet%28%29%0A%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20System.out.println%28%22Hello!%22%29%3B%0A%20%20%20%20%20%20%20%20System.out.println%28%22How%20are%20you%3F%22%29%3B%0A%20%20%20%20%7D%0A%20%20%20%20%20%0A%20%20%20%20public%20static%20void%20main%28String%5B%5D%20args%29%0A%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20System.out.println%28%22Before%20greeting%22%29%3B%0A%20%20%20%20%20%20%20%20greet%28%29%3B%0A%20%20%20%20%20%20%20%20System.out.println%28%22After%20greeting%22%29%3B%0A%20%20%20%20%7D%0A%7D&cumulative=true&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=java&rawInputLstJSON=%5B%5D&textReferences=false" target="_blank">GreetingExample Visualizer</a>    
 


Click on each tab to observe the flow of control for the ``GreetingExample`` class. 

.. tabbed:: q5_1_7

    .. tab:: Tab 1

      The program starts at the first line of the main method.
      The red arrow shows that line 11 is next to execute.
      
      The stack diagram is in the right portion of the screen print, below the print output section 
      where it says "Frames".  There is a single frame for the main method  ``main:11``, 
      indicating line 11 is the current line in the method.

      Click on the next tab to see what happens after line 11 executes.

      .. figure:: Figures/greet0.png
 
    .. tab:: Tab 2

      The red arrow shows that line 12 is next to execute.  
      The main method frame ``main:12`` is updated to indicate the current line.
     
      Click on the next tab to see what happens when line 12 executes and the greet() method is called.

      .. figure:: Figures/greet1.png
         


    .. tab:: Tab 3

      Control is transferred into the greet() method.
      
      The stack diagram shows a new frame was created for the greet() method ``greet:5``, indicating 
      line 5 is the current line in the method.   

      Note that the CodeLens tool adds the new method frame to the bottom of the stack diagram.


      .. figure:: Figures/greet2.png

    .. tab:: Tab 4

      The output is updated after line 5 is executed.  The ``greet:6`` frame indicates line 6 is next to execute.

      .. figure:: Figures/greet2b.png

    .. tab:: Tab 5

      The output is updated after line 6 is executed.  The ``greet:7`` frame indicates line 7 is next to execute, which is the last line of code in the method.

      When line 7 executes, the greet() method will return to the previous frame in the stack, which is the main method. 
      But how does the program know which line in the main to return to?
      The method frame ``main:12`` indicates that control should return to line 12.

      .. figure:: Figures/greet3.png

    .. tab:: Tab 6

      The greet() method completed and its frame was removed from the stack.  
      Control returned to the main method and since there was nothing else to do on line 12, the
      program moves forward to line 13 as depicted in the method frame ``main:13``.  The program
      will execute the remaining lines of code in the main method and then terminate.

      .. figure:: Figures/greet4.png

    .. tab:: Tab 7

      You can step through the program using the |visualizeTrace|.


|Exercise| **Check your understanding**

.. mchoice:: q5_1_8
   :practice: T
   :answer_a: apples and bananas! eat I like to.
   :answer_b: I like to consume consume consume fruit.
   :answer_c: I like to apples and bananas! eat.
   :answer_d: I like to eat eat eat apples and bananas!
   :correct: d
   :feedback_a: Try tracing through the main method and see what happens when it calls the other methods.
   :feedback_b: The consume() method does not print the word consume, and the fruit() method but it does not print the word fruit.
   :feedback_c: Try tracing through the main method and see what happens when it calls the other methods.
   :feedback_d: Yes, the print method calls the consume method 3 times and then the fruit method to print this.
  
   What does the following code print? 

   .. code-block:: java

      public class LikeFood 
      {
        
        public static void fruit()
        {
            System.out.println("apples and bananas!");
        }

        public static void consume() 
        {
           System.out.print("eat ");
        }
        
        public static void main(String[] args) 
        {
            System.out.print("I like to ");
            consume();
            consume();
            consume();
            fruit();
        }
    }

.. mchoice:: q5_1_9
   :practice: T
   :answer_a: 9
   :answer_b: 11
   :answer_c: 19
   :answer_d: 20
   :correct: b
   :feedback_a: Look at the frame on the bottom of the stack diagram to determine the current method.
   :feedback_b: Correct. The bottom stack frame shows the current method is greet() and line 11 is next to execute.
   :feedback_c: Look at the frame on the bottom of the stack diagram to determine the current method.
   :feedback_d: Look at the frame on the bottom of the stack diagram to determine the current method.
  
   Given the stack diagram shown in the figure, which line is next to execute?

    .. figure:: Figures/stackframeq1.png




.. mchoice:: q5_1_10
   :practice: T
   :answer_a: 16
   :answer_b: 17
   :answer_c: 18
   :answer_d: 19
   :correct: d
   :feedback_a: Look at the main method frame in the stack diagram.
   :feedback_b: Look at the main method frame in the stack diagram.
   :feedback_c: Look at the main method frame in the stack diagram.
   :feedback_d: Correct. The main method frame shows the greet method was called at line 19.
  
   After line 12 executes and the greet() method completes, control will return to which line in the main method?

    .. figure:: Figures/stackframeq2.png


.. mchoice:: q5_1_11
   :practice: T
   :answer_a: line 21 in method main.
   :answer_b: line 6 in method o.
   :answer_c: line 16 in method m.
   :correct: c
   :feedback_a: Incorrect. The stack diagram shows method n was called by method m.
   :feedback_b: Incorrect. The stack diagram shows method n was called by method m.
   :feedback_c: Correct. The stack diagram shows method n was called by method m.
   
   Notice the n() method is called both in method o() and method m().  
   The stack diagram shows the current execution
   trace.  After line 12 executes and the n() method completes, 
   control will return to which line in which method?

    .. figure:: Figures/stackframeq3.png


.. mchoice:: q5_1_12
   :practice: T
   :answer_a: Called n
   :answer_b: Called o
   :answer_c: Called m
   :answer_d: After n
   :correct: d
   :feedback_a: Incorrect. The last method call in the main is to method o().  Look at the last line in method o().
   :feedback_b: Incorrect. The last method call in the main is to method o().  Look at the last line in method o().
   :feedback_c: Incorrect. The last method call in the main is to method o().  Look at the last line in method o().
   :feedback_d: Correct. 
   
   What is the last thing printed when the program runs?

     .. figure:: Figures/stackframeq4.png


  
|CodingEx| **Coding Exercise**

.. activecode:: code5_1_2
  :language: java   
  :autograde: unittest    
  :practice: T

  A refrain is similar to a chorus, although usually shorter in length such as a single line that gets repeated.
  In the song below, the refrain is "The farmer in the dell".  
  Add a method named "refrain" and update the main method to call the new method 3 times in place of the duplicate print statements.  
  Run your program to ensure the output is correct.
  ~~~~
  public class FarmerSong 
  { 

    //add your new method here



    public static void main(String args[]) 
    {
       System.out.println("The farmer in the dell");
       System.out.println("The farmer in the dell");
       System.out.println("Heigh ho the derry-o");
       System.out.println("The farmer in the dell");
    }
    
  }
  ====
  import static org.junit.Assert.*;
    import org.junit.*;;
    import java.io.*;
    
    public class RunestoneTests extends CodeTestHelper
    {
        @Test
        public void testSignature(){
          int count = countOccurences(getCode(),"public static void refrain()");
          boolean passed = count == 1;
          passed = getResults("1 refrain signature",  count  + " refrain signature", "Refrain method signature", passed);
          assertTrue(passed);
        }

        @Test
        public void testcodeContains(){
          int count = countOccurences(getCode(),"refrain();");
          boolean passed = count == 3;
          passed = getResults("3 refrain calls",  count  + " refrain calls", "Call refrain() from the main method", passed);
          assertTrue(passed);
        }

    }


Summary
-------

- **Procedural Abstraction** (creating methods) reduces the complexity and repetition of code. We can name a block of code as a method and call it whenever we need it, abstracting away the details of how it works.  

- A programmer breaks down a large problem into smaller subproblems by creating methods to solve each individual subproblem.

- Write a **method definition** with a **method signature** like ``public static void chorus()`` and a **method body** that consists of statements nested within {}.

- Call the method using its name followed by parentheses ``chorus()``.  The method call executes the statements in the method body.