.. qnum::
   :prefix: 9-2-
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
    
Nested Loops for 2D Arrays
==========================

In this lesson, you will learn how to use nested loops to traverse a 2D Array.

Getting the Number of Rows and Columns
---------------------------------------
..	index::
	pair: 2D Array; number of rows
	pair: 2D Array; number of columns

Arrays know their length (how many elements they can store).  The length is a public read-only field so you can use *dot-notation* to access the field (``arrayName.length``). The length of the outer array is the number of rows and the length of one of the inner arrays is the number of columns. 



.. code-block:: java 

  ticketInfo.length // returns the number of rows
  ticketInfo[0].length // returns the number of columns
  
.. note::

     Note that length is a field and not a method, so you don't add parentheses after length.

|Exercise| **Check your understanding**

.. mchoice:: q9_2_1
   :practice: T
   :answer_a: 2
   :answer_b: 4
   :answer_c: 8
   :correct: a
   :feedback_a: The size of outer list is the number of rows.
   :feedback_b: The size of the inner list is the number of columns.
   :feedback_c: This is the total number of items in the array.

   How many rows does ``a`` have if it is created as follows ``int[][] a = { {2, 4, 6, 8}, {1, 2, 3, 4}};``?	
   
.. mchoice:: q9_2_2
   :practice: T
   :answer_a: nums[3][2]
   :answer_b: nums[2][3]
   :answer_c: nums[2][1]
   :answer_d: nums[1][2]
   :correct: c
   :feedback_a: This would be true if array indices started with 1 but they start with 0. 
   :feedback_b: This would be true if array indicies started with 1 and the column was specified first.  However, array indices start at 0 and the row is given first in row-major order.
   :feedback_c: Array indices start with 0 so the third row has an index of 2 and the second column has an index of 1.  
   :feedback_d: This would be true if the column index was first, but in row-major order the row index is first.

   Which of the following would I use to get the value in the third row and second column from a 2D array called ``nums``?
   
 
Looping Through a 2D Array
--------------------------

..	index::
	pair: 2D Array; looping through
	pair: loop; nested

Since you can find out the number of rows and columns in a 2D array you can use a **nested for loop** (one loop inside of another loop) to loop/traverse through all of the elements of a 2D array. 

.. code-block:: java 

  int[][] array = { {1,2,3},{4,5,6}};
  for (int row = 0; row < array.length; row++)
  {
      for (int col = 0; col < array[0].length; col++)
      {
           System.out.println( array[row][col] );
      }
   }
   
|CodingEx| **Coding Exercise**


   
   What does the ``E012DArrayTraversal`` program do? Add another row of numbers to the matrix. Will the loops traverse this row too?
   
   
Some key things to notice about this code are:

- ``total`` is declared to be a double so that the result will be a double.  If ``total`` was declared to be an ``int`` then the result would be an integer and the values after the decimal point would be thrown away.  
- The number of rows is ``a.length``
- The number of columns is ``a[0].length``
- The number of times this loop executes is the number of rows times the number of columns.  



|Exercise| **Mixed up programs**

.. parsonsprob:: q9_2_3
   :numbered: left
   :practice: T
   :adaptive:

   The following has the correct code to find the largest value in a 2D array. Drag the blocks from the left into the correct order on the right and indent them as well. Check your solution by clicking on the <i>Check Me</i> button.  You will be told if any of the blocks are in the wrong order or have the wrong indention.
   -----
   public static int getLargest(int[][] arr)  {
   =====
    int largest = arr[0][0];
    int current = 0;
    for (int r = 0; r < arr.length; r++)  {
    =====
      for (int c = 0; c < arr[0].length; c++)  {
    =====
        current = arr[r][c];
        if (current > largest)  {
    =====
          largest = current;
    =====
        } // end if
    =====
      } // end column loop
    =====
    } // end row loop
    return largest;
   =====
   } // end method
   
Most nested loops with 2D Arrays use "row-major order" where the outer loop goes through each row. However, you can write nested loops that traverse in "column-major order" like below.

   
|CodingEx| **Coding Exercise**

   
   What will the ``E02ColumnMajorTraversal`` program print out? Try to guess before you run it. Then, step through it with the debugger.
  
         

Enhanced For-Each Loop for 2D Arrays
----------------------------------------------------
   
   The ``E03Average`` program is a nested enhanced for loops demo. Use the debugger to step through the code.

  
In this case the ``for (int[] colArray : a)`` means to loop through each element of the outer array which will set colArray to the current column array.  Then you can loop through the value in the column array.

Summary
----------

- We can loop through 2D arrays using nested for loops or nested enhanced for each loops.

- The outer loop for a 2D array usually traverses the rows, while the inner loop traverses the columns in a single row. 

- The 2D array's length gives the number of rows. A row's length array[0].length gives the number of columns. 

- Nested iteration statements can be written to traverse the 2D array in "row-major order" or "column-major order."

- In a enhanced for each loop, the variable of the outer loop must be the type of each row, which is a 1D array. The inner enhanced for loop variable must be the same type as the elements stored in the array.

- When applying sequential/linear search algorithms to 2D arrays, each row must be accessed then sequential/linear search applied to each row of a 2D array.





