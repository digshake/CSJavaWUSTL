.. qnum::
   :prefix: 7-3-
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
    
.. arrays of objects?

Enhanced For-Loop (For-Each) for Arrays
=======================================

..	index::
	single: for-each
	pair: loop; for-each
   
There is a special kind of loop that can be used with arrays  called an **enhanced for loop** or a **for each loop**. This loop is much easier to write because it does not involve an index variable or the use of the []. It just sets up a variable that is set to each value in the array successively. 

To set up a for-each loop, use **for (type variable : arrayname)** where the type is the type for elements 
in the array, and read it as "for each variable value in arrayname". 

 .. code-block:: java

    for (type item: array)
    {
         //statements using item;
    }


See the examples below in Java that loop through an int and a String array. Notice the type of the loop variable is the type of the array.

.. code-block:: java 
 
  int[] highScores = { 10, 9, 8, 8};
  String[] names = {"Jamal", "Emily", "Destiny", "Mateo"};
  // for each loop: for each value in highScores
  // for (type variable : arrayname)
  for (int value : highScores)
  {
      // Notice no index or [ ], just the variable value!
      System.out.println( value );
  }
  // for each loop with a String array to print each name
  // the type for variable name is String!
  for (String name : names)
  {
      System.out.println(name); 
  }

Use the enhanced for each loop with arrays whenever you can, because it cuts down on errors. You can use it whenever you need to loop through all the elements of an array and don't need to know their index and don't need to change their values.  It starts with the first item in the array (the one at index 0) and continues through in order to the last item in the array. This type of loop can only be used with arrays and some other collections of items like ArrayLists which we will see in the next unit.  

|CodingEx| **Coding Exercise**



.. activecode:: code7_3_1
   :language: java
   :autograde: unittest
   
   Try the following code. Notice the for each loop with an int array and a String array. Add another high score and another name to the arrays and run again.
   ~~~~
   public class ForEachDemo
   {      
      public static void main(String[] args)
      {
        int[] highScores = { 10, 9, 8, 8};
        String[] names = {"Jamal", "Emily", "Destiny", "Mateo"};
        // for each loop with an int array
        for (int value : highScores)
        {
            System.out.println( value );
        }
        // for each loop with a String array
        for (String value : names)
        {
            System.out.println(value); // this time it's a name!
        }
      }
    }
    ====
    import static org.junit.Assert.*;
    import org.junit.*;;
    import java.io.*;

    public class RunestoneTests extends CodeTestHelper
    {
        public RunestoneTests() {
            super("ForEachDemo");
        }

        @Test
        public void test1()
        {
            String output = getMethodOutput("main");
            String expect1 = "10\n9\n8\n8";
            String expect2 = "Jamal\nEmily\nDestiny\nMateo";

            boolean passed = output.contains(expect1) && output.contains(expect2);

            passed = getResults(expect1 + " " + expect2, output, "Original main()", passed);
            assertTrue(passed);
        }

        @Test
        public void test2()
        {
            String output = getMethodOutput("main");
            String expect = "10 9 8 8 Jamal Emily Destiny Mateo".replaceAll(" ", "\n");

            boolean passed = !output.equals(expect) && output.length() > expect.length();

            passed = getResults(expect, output, "Added another high score and name", passed);
            assertTrue(passed);
        }
    }
  
|CodingEx| **Coding Exercise**



.. activecode:: code7_3_2
   :language: java
   :autograde: unittest
   :practice: T
   
   Rewrite the following for loop which prints out the even numbers in the array as an enhanced for-each loop. Make sure it works!
   ~~~~
   public class EvenLoop
   {      
      public static void main(String[] args)
      {
        int[ ] values = {6, 2, 1, 7, 12, 5};
        // Rewrite this loop as a for each loop and run
        for (int i=0; i < values.length; i++)
        {
          if (values[i] % 2 == 0)
              System.out.println(values[i] + " is even!");
        }
      }
   }
   ====
   // Test for Lesson 6.3.2 - EvenLoop

    import static org.junit.Assert.*;
    import org.junit.*;;
    import java.io.*;

    public class RunestoneTests extends CodeTestHelper
    {
        public RunestoneTests() {
            super("EvenLoop");
        }

        @Test
        public void test1()
        {
            String output = getMethodOutput("main");
            String expect = "6 is even!\n2 is even!\n12 is even!";

            boolean passed = getResults(expect, output, "main()");
            assertTrue(passed);
        }

        @Test
        public void test2() 
        {
            boolean passed = checkCodeContains("for each loop", "for(int * : values)");
            assertTrue(passed);
        }
    }

Foreach Loop Limitations
--------------------------

.. |visualizer| raw:: html

   <a href="http://www.pythontutor.com/visualize.html#code=%20%20%20public%20class%20IncrementLoop%0A%20%20%20%7B%20%20%20%20%20%20%0A%20%20%20%20%20%20public%20static%20void%20main%28String%5B%5D%20args%29%0A%20%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20int%5B%20%5D%20values%20%3D%20%7B6,%202,%201,%207,%2012,%205%7D%3B%0A%20%20%20%20%20%20%20%20//%20Can%20this%20loop%20increment%20the%20values%3F%0A%20%20%20%20%20%20%20%20for%20%28int%20val%20%3A%20values%29%0A%20%20%20%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20%20%20val%2B%2B%3B%0A%20%20%20%20%20%20%20%20%20%20System.out.println%28%22New%20val%3A%20%22%20%2B%20val%29%3B%0A%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%20%20//%20Print%20out%20array%20to%20see%20if%20they%20really%20changed%0A%20%20%20%20%20%20%20%20for%20%28int%20v%20%3A%20values%29%0A%20%20%20%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20%20%20System.out.print%28v%20%2B%20%22%20%22%29%3B%0A%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%7D%0A%20%20%20%7D%0A%20%20%20&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=java&rawInputLstJSON=%5B%5D&textReferences=false&curInstr=0" target="_blank"  style="text-decoration:underline">Java visualizer</a>	
   
What if we had a loop that incremented all the elements in the array. Would that work with an enhanced for-each loop? Unfortunately not! Because only the variable in the loop changes, not the real array values. We would need an indexed loop to modify array elements. Try it in the Active Code below or in the |visualizer| by clicking the CodeLens button and step through the code to see why it doesn't work. 

|CodingEx| **Coding Exercise**


.. activecode:: code7_3_3
   :language: java
   :autograde: unittest
   :practice: T

   The for-each loop below cannot change the values in the array because only the loop variable value will change. Run it with the CodeLens button to see why this is. Then, change the loop to an indexed for loop to make it change the array values.
   ~~~~
   public class IncrementLoop
   {      
      public static void main(String[] args)
      {
        int[ ] values = {6, 2, 1, 7, 12, 5};
        // Can this loop increment the values?
        for (int val : values)
        {
          val++;
          System.out.println("New val: " + val);
        }
        // Print out array to see if they really changed
        System.out.println("Array after the loop: ");
        for (int v : values)
        {
          System.out.print(v + " ");
        }
      }
   }
   ====
   // Test for Lesson 6.3.3 - IncrementLoop

    import static org.junit.Assert.*;
    import org.junit.*;;
    import java.io.*;

    public class RunestoneTests extends CodeTestHelper
    {
        public RunestoneTests() {
            super("IncrementLoop");
        }

        @Test
        public void test1()
        {
            String output = getMethodOutput("main");
            String expect = "New val: 7\nNew val: 3\nNew val: 2\nNew val: 8\nNew val: 13\nNew val: 6\nArray after the loop:\n7 3 2 8 13 6";

            boolean passed = getResults(expect, output, "main()");
            assertTrue(passed);
        }

        @Test
        public void test2() 
        {
            String target = "for (int * = #; * ? *.length; *~)";
            boolean passed = checkCodeContains("for loop", target);
            assertTrue(passed);

        }
    }
   
.. note::

   Enhanced for each loops cannot be used in all situations. Only use for-each loops when you want to loop through **all** the values in an array without changing their values. 
   
   - Do not use for each loops if you need the index.
   - Do not use for each loops if  you need to change the values in the array.
   - Do not use for each loops if you want to loop through only part of an array or in a different order.
  



|Exercise| **Check Your Understanding**

.. mchoice:: q7_3_1
   :practice: T
   :answer_a: Only I.
   :answer_b: I and III only.
   :answer_c: II and III only.
   :answer_d: All of the Above.
   :correct: b
   :feedback_a: This style of loop does access every element of the array, but using a for-each loop also means the user can access elements through the variable name.
   :feedback_b: Correct! For-each loops access all elements and enable users to use a variable name to refer to array elements, but do not allow users to modify elements directly.
   :feedback_c: For-each loops, as well as allowing users to refer to array elements, run through every element. For-each loops also do not allow users to modify elements directly.
   :feedback_d: For-each loops access all of an array's elements and allow users to refer to elements through a variable, but do not allow users to modify elements directly.  


   What are some of the reasons you would use an enhanced for-each loop instead of a for loop?
   
   .. code-block:: java

      I: If you wish to access every element of an array.
      II: If you wish to modify elements of the array.
      III: If you wish to refer to elements through a variable name instead of an array index. 


.. mchoice:: q7_3_2
   :practice: T
   
   What is the output of the following code segment?
   
   .. code-block:: java
   
      int[ ] numbers = {44, 33, 22, 11};
      for (int num : numbers)
      {
          num *= 2;
      }
      for (int num : numbers)
      {
          System.out.print(num + " ");
      }
      
   - 44 33 22 11
    
     + The array is unchanged because the foreach loop cannot modify the array elements.
      
   - 46 35 24 13
    
     - Remember that the foreach loop cannot modify the array elements, but it also uses multiplication, not addition.
    
   - 88 66 44 22
    
     - Remember that the foreach loop cannot modify the array elements. Only the variable num will be doubled, not the original array values.
         
   - The code will not compile. 
    
     - This code will compile.
    

Foreach Loop Algorithms
--------------------------



.. |Java visualizer| raw:: html

   <a href="http://www.pythontutor.com/java.html#code=public+class+ArrayWorker%0A%7B%0A+++private+int%5B+%5D+values%3B%0A%0A+++public+ArrayWorker(int%5B%5D+theValues)%0A+++%7B%0A++++++values+%3D+theValues%3B%0A+++%7D%0A%0A+++public+double+getAverage()%0A+++%7B%0A+++++double+total+%3D+0%3B%0A+++++for+(int+val+%3A+values)%0A+++++%7B%0A+++++++total++%3D+total+%2B+val%3B%0A+++++%7D%0A+++++return+total+/+values.length%3B%0A+++%7D%0A%0A+++public+static+void+main(String%5B%5D+args)%0A+++%7B%0A+++++int%5B%5D+numArray+%3D++%7B2,+6,+7,+12,+5%7D%3B%0A+++++ArrayWorker+aWorker+%3D+new+ArrayWorker(numArray)%3B%0A+++++System.out.println(aWorker.getAverage())%3B%0A+++%7D%0A%7D%0A%0A&mode=display&curInstr=0" target="_blank"  style="text-decoration:underline">Java visualizer</a>	
   

Here is an object-oriented example that has the array as a private instance variable in the class and provides a public method average that uses a for-each loop.  You can use the |Java Visualizer| or the Code Lens button to step through this code. 
     

.. activecode:: code7_3_4
   :language: java
   :autograde: unittest
   
   Try the code below. 
   ~~~~
   public class ArrayWorker
   {
      
      public static double getAverage(int[] values)
      {
        double total = 0;
        for (int val : values)
        {
          total  = total + val;
        }
        return total / values.length;
      }
      
      public static void main(String[] args)
      {
        int[] numArray =  {2, 6, 7, 12, 5};
        System.out.println(getAverage(numArray));
      }
   }
   ====
   // Test for Lesson 6.3.3 - IncrementLoop

    import static org.junit.Assert.*;
    import org.junit.*;;
    import java.io.*;

    public class RunestoneTests extends CodeTestHelper
    {
        public RunestoneTests() {
            super("ArrayWorker");
        }

        @Test
        public void test1()
        {
            String output = getMethodOutput("main");
            String expect = "6.4";

            boolean passed = getResults(expect, output, "main()", true);
            assertTrue(passed);
        }
    }




|Exercise| **Check Your Understanding**

.. parsonsprob:: q7_3_3
   :numbered: left
   :practice: T
   :adaptive:

   The following method has the correct code to return the largest value in an integer array called <i>vals</i> (an instance variable of the current object), but the code is mixed up.  Drag the blocks from the left into the correct order on the right and indent them correctly as well. You will be told if any of the blocks are in the wrong order or not indented correctly.</p>
   -----
   public int getLargest()
   {
   =====
     int largest = vals[0];
   =====
     for (int item : vals)
     {
   =====
       if (item > largest)
       {
   =====
         largest = item;
   =====
       }  // end if 
   =====
     } // end for
     return largest;
   =====
   } // end method
   

.. |Java visualizer link| raw:: html

   <a href="http://www.pythontutor.com/java.html#code=public+class+ArrayWorker%0A%7B%0A+++private+int%5B+%5D+values%3B%0A%0A+++public+ArrayWorker(int%5B%5D+theValues)%0A+++%7B%0A++++++values+%3D+theValues%3B%0A+++%7D%0A%0A+++public+double+getAverage()%0A+++%7B%0A+++++double+total+%3D+0%3B%0A+++++for+(int+val+%3A+values)%0A+++++%7B%0A+++++++total++%3D+total+%2B+val%3B%0A+++++%7D%0A+++++return+total+/+values.length%3B%0A+++%7D%0A+++%0A+++public+int+getLargest()%0A+++%7B%0A++%0A+++++int+largest+%3D+values%5B0%5D%3B%0A%0A+++++for+(int+item+%3A+values)%0A+++++%7B%0A%0A+++++++if+(item+%3E+largest)%0A+++++++%7B%0A%0A+++++++++largest+%3D+item%3B%0A%0A+++++++%7D++//+end+if+%0A%0A+++++%7D+//+end+for%0A+++++return+largest%3B%0A%0A+++%7D+//+end+method%0A%0A+++public+static+void+main(String%5B%5D+args)%0A+++%7B%0A+++++int%5B%5D+numArray+%3D++%7B2,+6,+7,+12,+5%7D%3B%0A+++++ArrayWorker+aWorker+%3D+new+ArrayWorker(numArray)%3B%0A+++++System.out.println(aWorker.getLargest())%3B%0A+++%7D%0A%7D%0A%0A&mode=display&curInstr=0" target="_blank">Java visualizer link</a>
   
If you want to step through the correct code to see what it does in the Java Visualizer click on the following |Java visualizer link|.


.. Some examples of finding the largest value in an array start by setting the largest variable to 0.  But, what happens if the array only contains negative numbers?  What value could you set largest to and still have it work correctly even if the field ``vals`` contained only negative numbers?

|Exercise| **Check Your Understanding**

.. mchoice:: q7_3_4
   :practice: T
   :answer_a: Whenever the first element in <i>array</i> is equal to <i>target</i>.
   :answer_b: Whenever <i>array</i> contains any element which equals <i>target</i>.
   :answer_c: Whenever the last element in <i>array</i> is equal to <i>target</i>.
   :answer_d: Whenever only 1 element in <i>array</i> is equal to <i>target</i>.
   :correct: c
   :feedback_a: This would be true if the loop started at the end of the array and moved toward the beginning.  But, it will loop from the first element to the last.  
   :feedback_b: This would be true if temp was only set to the result of checking if the current element in the array is equal to <i>target</i> when it is <i>false</i>.  But, it is reset each time through the loop.
   :feedback_c: The variable <i>temp</i> is assigned to the result of checking if the current element in the array is equal to <i>target</i>.  The last time through the loop it will check if the last element is equal to <i>val</i>.
   :feedback_d: There is no count of the number of times the array element is equal to <i>target</i>.  


   Given that ``array`` is an array of integers and ``target`` is an integer value, which of the following best describes the conditions under which the following code segment will return true?
   
   .. code-block:: java 

     boolean temp = false;
     for (int val : array)
     { 
       temp = ( target == val ); 
     }
     return temp;
     


|Groupwork| Programming Challenge : SpellChecker 2
---------------------------------------------------

.. image:: Figures/spellcheck.png
    :width: 100
    :align: left
    :alt: Spell Checker


.. |startsWith()| raw:: html

   <a href= "https://www.w3schools.com/java/ref_string_startswith.asp" target="_blank">startsWith()</a>
   
.. |repl.it| raw:: html

   <a href= "https://repl.it/@BerylHoffman/SpellChecker1" target="_blank">repl.it</a>
   
Copy the spellcheck method that you used in the Spell Checker Challenge in the last lesson. 
Re-write the method  to use an enhanced for-each loop instead of an indexed for-loop. 
If you did the optional printStartsWith(firstLetters) method, re-write that one too. 

.. activecode:: code7_3_5
   :language: java
   :autograde: unittest
   
   Write a spellcheck() method using an enhanced for-each loop that takes a word as a parameter and returns true if it is in the dictionary array. Return false if it is not found.
   ~~~~
   public class SpellChecker
   {
      // Re-write the spellcheck(word, dictionary) (and optionally the printStartsWith(firstLetters, dictionary)) methods to use enhanced for-each loops.
       
       
      
      public static void main(String[] args)
      {
        String[] dictionary = {"the","of","and","a","to","in","is","you","that","it","he","was","for","on","are","as","with","his","they","I","at","be","this","have","from","or","one","had","by","word","but","not","what","all","were","we","when","your","can","said","there","use","an","each","which","she","do","how","their","if","will","up","other","about","out","many","then","them","these","so","some","her","would","make","like","him","into","time","has","look","two","more","write","go","see","number","no","way","could","people","my","than","first","water","been","call","who","oil","its","now","find","long","down","day","did","get","come","made","may","cat","dog","cats","dogs"};

        /* Uncomment to test your method
        String word = "catz";
        if (checker.spellcheck(word, dictionary) == true)
            System.out.println(word + " is spelled correctly!");
        else
            System.out.println(word + " is misspelled!");
        */

       // Optional (not autograded)
       // checker.printStartsWith("a", dictionary);
      }
   }
   ====
   // Test for Lesson 6.2.5 - challenge-6-2-spell-checker

    import static org.junit.Assert.*;
    import org.junit.*;;
    import java.io.*;

    public class RunestoneTests extends CodeTestHelper
    {
        public RunestoneTests() {
            super("SpellChecker");
        }

        @Test
        public void testMain()
        {
            String output = getMethodOutput("main");
            String expect = "catz is misspelled!";

            boolean passed = output.contains(expect);

            passed = getResults(expect, output, "Did you uncomment the main method?", passed);
            assertTrue(passed);
        }



        @Test
        public void test3()
        {
            Object[] args = {"dogz"};
            String output = getMethodOutput("spellcheck", args);
            String expect = "false";

            boolean passed = getResults(expect, output, "spellcheck(\"dogz\")");
            assertTrue(passed);
        }

        @Test
        public void test4()
        {
            Object[] args = {"dog"};
            String output = getMethodOutput("spellcheck", args);
            String expect = "true";

            boolean passed = getResults(expect, output, "spellcheck(\"dog\")");
            assertTrue(passed);
        }

        @Test
        public void testFor() throws IOException
        {
            String target = "for (int * = #; * ? #; *~)";
            boolean passed = checkCodeNotContains("for loop", target);
            assertTrue(passed);
        }

        @Test
        public void testForEach() 
        {
            boolean passed = checkCodeContains("for each loop", "for(String * : dictionary)");
            assertTrue(passed);
        }
    }

Summary
-------

- An **enhanced for loop**, also called a **for each loop**, can be used to loop through an array without using an index variable.

- An enhanced for loop header includes a variable, referred to as the enhanced for loop variable, that holds each value in the array.

- For each iteration of the enhanced for loop, the enhanced for loop variable is assigned a copy of an element without using its index.

- Assigning a new value to the enhanced for loop variable does not change the value stored in the array.

- Program code written using an enhanced for loop to traverse and access elements in an array can be rewritten using an indexed for loop or a while loop.
 
