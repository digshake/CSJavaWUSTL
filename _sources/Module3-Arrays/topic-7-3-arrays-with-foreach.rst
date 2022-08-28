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

   
   Try the ``ForEachDemo`` program. Notice the for each loop with an int array and a String array. Add another high score and another name to the arrays and run again.
  
  
|CodingEx| **Coding Exercise**


   
   Rewrite the for loop in the ``EvenLoop`` program which prints out the even numbers in the array as an enhanced for-each loop. Make sure it works!
 

Foreach Loop Limitations
--------------------------

.. |visualizer| raw:: html

   <a href="http://www.pythontutor.com/visualize.html#code=%20%20%20public%20class%20IncrementLoop%0A%20%20%20%7B%20%20%20%20%20%20%0A%20%20%20%20%20%20public%20static%20void%20main%28String%5B%5D%20args%29%0A%20%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20int%5B%20%5D%20values%20%3D%20%7B6,%202,%201,%207,%2012,%205%7D%3B%0A%20%20%20%20%20%20%20%20//%20Can%20this%20loop%20increment%20the%20values%3F%0A%20%20%20%20%20%20%20%20for%20%28int%20val%20%3A%20values%29%0A%20%20%20%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20%20%20val%2B%2B%3B%0A%20%20%20%20%20%20%20%20%20%20System.out.println%28%22New%20val%3A%20%22%20%2B%20val%29%3B%0A%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%20%20//%20Print%20out%20array%20to%20see%20if%20they%20really%20changed%0A%20%20%20%20%20%20%20%20for%20%28int%20v%20%3A%20values%29%0A%20%20%20%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20%20%20System.out.print%28v%20%2B%20%22%20%22%29%3B%0A%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%7D%0A%20%20%20%7D%0A%20%20%20&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=java&rawInputLstJSON=%5B%5D&textReferences=false&curInstr=0" target="_blank"  style="text-decoration:underline">Java visualizer</a>	
   
What if we had a loop that incremented all the elements in the array. Would that work with an enhanced for-each loop? Unfortunately not! Because only the variable in the loop changes, not the real array values. We would need an indexed loop to modify array elements.  

|CodingEx| **Coding Exercise**


   The for-each loop in the ``IncrementLoop`` program cannot change the values in the array because only the loop variable value will change. Run it with the debugger to see why this is. Then, change the loop to an indexed for loop to make it change the array values.
  
   
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
    


Summary
-------

- An **enhanced for loop**, also called a **for each loop**, can be used to loop through an array without using an index variable.

- An enhanced for loop header includes a variable, referred to as the enhanced for loop variable, that holds each value in the array.

- For each iteration of the enhanced for loop, the enhanced for loop variable is assigned a copy of an element without using its index.

- Assigning a new value to the enhanced for loop variable does not change the value stored in the array.

- Program code written using an enhanced for loop to traverse and access elements in an array can be rewritten using an indexed for loop or a while loop.
 
