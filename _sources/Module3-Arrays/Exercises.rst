.. qnum::
   :prefix: 7-7-
   :start: 1


Multiple-Choice Exercises
=========================
   
Easier Multiple Choice Questions
----------------------------------


.. mchoice:: q7_7_1
   :practice: T
   :answer_a: <code>nums.length</code>
   :answer_b: <code>nums.length - 1</code>
   :correct: b
   :feedback_a: Since the first element in an array is at index 0 the last element is the length minus 1.
   :feedback_b: Since the first element in an array is at index 0 the last element is the length minus 1.

   Which index is the last element in an array called ``nums`` at?
   
.. mchoice:: q7_7_2
   :practice: T
   :answer_a: <code>int[] scores = null;</code>
   :answer_b: <code>int[] scoreArray = {50,90,85};</code>
   :answer_c: <code>String[] nameArray = new String[10];</code>
   :answer_d: <code>String[] nameArray = {5, 3, 2};</code>
   :answer_e: <code>int[] scores = new int[5];</code>
   :correct: d
   :feedback_a: You can initialize an array reference to null to show that it doesn't refer to any array yet.
   :feedback_b: You can provide the values for an array when you declare it.
   :feedback_c: You can declare and array and create the array using the <code>new</code> operator in the same statement.
   :feedback_d: You can not put integers into an array of String objects.
   :feedback_e: You can declare and array and create it in the same statement.  Use the <code>new</code> operator to create the array and specify the size in square brackets.  

   Which of the following declarations will cause a compile time error?
   
.. mchoice:: q7_7_3
   :practice: T
   :answer_a: 1
   :answer_b: 2
   :answer_c: 3
   :answer_d: 6
   :answer_e: 4
   :correct: b
   :feedback_a: This would be returned from <code>arr[2]</code>.
   :feedback_b: This returns the value in <code>arr</code> at index 3.  Remember that the first item in an array is at index 0. 
   :feedback_c: This would be returned from <code>arr[1]</code>.
   :feedback_d: This would be returned from <code>arr[0]</code>.
   :feedback_e: This would be returned from <code>arr.length</code>

   What is returned from ``arr[3]`` if ``arr={6, 3, 1, 2}``?  
   
.. mchoice:: q7_7_4
   :practice: T
   :answer_a: 17.5
   :answer_b: 30.0
   :answer_c: 130
   :answer_d: 32
   :answer_e: 32.5
   :correct: e
   :feedback_a: This would be true if the loop stopped at <code>arr.length - 1</code>.  
   :feedback_b: This would be true if the loop started at 1 instead of 0.  
   :feedback_c: This would be true if it returned <code>output</code> rather than <code>output / arr.length</code> 
   :feedback_d: This would be true if <code>output</code> was declared to be an int rather than a double. 
   :feedback_e: This sums all the values in the array and then returns the sum divided by the number of items in the array.  This is the average.  

   What is the value of from ``output`` when it is passed ``{10, 30, 30, 60}``?
   
   .. code-block:: java
   
      public static void main(String[] args) {
         int[] arr = {10, 30, 30, 60};
      	double output = 0;
         for (int i = 0; i < arr.length; i++) {
            output = output + arr[i];
         }
         output = output / arr.length;
      }
      
.. mchoice:: q7_7_5
   :practice: T
   :answer_a: {-20, -10, 2, 8, 16, 60}
   :answer_b: {-20, -10, 2, 4, 8, 30}
   :answer_c: {-10, -5, 1, 8, 16, 60}
   :answer_d: {-10, -5, 1, 4, 8, 30} 
   :correct: c
   :feedback_a: This would true if it looped through the whole array.  Does it?
   :feedback_b: This would be true if it looped from the beginning to the middle.  Does it?
   :feedback_c: It loops from the middle to the end doubling each value. Since there are 6 elements it will start at index 3.  
   :feedback_d: This would be true if array elements didn't change, but they do.  

   Given the following values of ``a`` and the method ``doubleLast`` what will the values of ``a`` be after the following code is executed?
   
   .. code-block:: java 
   
      public static void main(String[] args) {
         int[] a = {-10, -5, 1, 4, 8, 30};
         for (int i = a.length / 2; i < a.length; i++) {
            a[i] = a[i] * 2;
         }
      }

.. mchoice:: q7_7_6
   :practice: T
   :answer_a: {1, 3, -5, -2}
   :answer_b: {3, 9, -15, -6}
   :answer_c: {2, 6, -10, -4}
   :answer_d: The code will never stop executing due to an infinite loop
   :correct: b
   :feedback_a: This would be true if the contents of arrays could not be changed but they can. 
   :feedback_b: This code multiplies each value in a by the passed amt which is 3 in this case.
   :feedback_c: This would be correct if we called multAll(2) instead of multAll(3).
   :feedback_d: The variable i starts at 0 and increments each time through the loop and stops when it equals the number of items in a.  

   What are the values in a after the following code executes?
   
   .. code-block:: java 
     
     public static void main(String[] args) {
        int[ ] a = {1, 3, -5, -2};
        int i = 0;
        int amt = 3;
        while (i < a.length) {
           a[i] = a[i] * amt;
           i++;
        } // end while
     } // end method  
     
.. mchoice:: q7_7_7
   :practice: T
   :answer_a: {1, 3, -5, -2}
   :answer_b: {3, 9, -15, -6}
   :answer_c: {2, 6, -10, -4}
   :answer_d: The code will never stop executing due to an infinite loop
   :correct: d
   :feedback_a: Does the value of i ever change inside the loop?
   :feedback_b: Does the value of i ever change inside the loop?
   :feedback_c: Does the value of i ever change inside the loop?
   :feedback_d: The value of i is initialized to 0 and then never changes inside the body of the loop, so this loop will never stop.  It is an infinite loop.   

   What are the values in a after mult(2) executes?
   
   .. code-block:: java 
     
     public static void main(String[] args) {
        int[ ] a = {1, 3, -5, -2};
        int i = 0;
        int amt = 2;
        while (i < a.length) {
           a[i] = a[i] * amt;
        } // end while
     } // end method  
     

.. mchoice:: q9_6_1
   :practice: T
   :answer_a: 2
   :answer_b: 4
   :answer_c: 8
   :correct: b
   :feedback_a: The size of outer array is the number of rows.  Remember that two-dimensional arrays are actually an array of arrays in Java.
   :feedback_b: The size of the inner array is the number of columns.
   :feedback_c: This is the total number of items in the array.

   How many columns does ``a`` have if it is created as follows ``int[][] a = { {2, 4, 6, 8}, {1, 2, 3, 4}};``?	
   
.. mchoice:: q9_6_2
   :practice: T
   :answer_a: <code>strGrid[0][2] = "S";</code>
   :answer_b: <code>strGrid[1][3] = "S";</code>
   :answer_c: <code>strGrid[3][1] = "S";</code>
   :answer_d: <code>strGrid[2][0] = "S";</code> 
   :answer_e: <code>strGrid[0][0] = "S";</code>
   :correct: d  
   :feedback_a: The code <code>letterGrid[0][2] = "S";</code> actually sets the 1st row and 3rd column to hold a reference to the <code>String</code> object "S".
   :feedback_b: This would be true if row and column indicies started at 1 instead of 0 and if this was in column major order. 
   :feedback_c: This would be true if row and column indicies started at 1 instead of 0.  
   :feedback_d: In row-major order the row is specified first followed by the column.  Row and column indicies start with 0.  So <code>letterGrid[2][0]</code> is the 3rd row and 1st column. 
   :feedback_e: This would set the element at the first row and column.   

   Which of the following statements assigns the letter S to the third row and first column of a two-dimensional array named ``strGrid`` (assuming row-major order).
   
.. mchoice:: q9_6_3
   :practice: T
   :answer_a: a[0][3]
   :answer_b: a[1][3]
   :answer_c: a[0][2]
   :answer_d: a[2][0]
   :answer_e: a[3][1]
   :correct: c
   :feedback_a: This would be true if the row index started at 0, but the column index started at 1.
   :feedback_b: Both the row and column indicies start with 0.  
   :feedback_c: The value 6 is at row 0 and column 2.  
   :feedback_d: The row index is specified first, then the column index.
   :feedback_e: The row index is specified first and the indicies start at 0.  

   How would you get the value 6 out of the following array ``int[][] a = { {2, 4, 6, 8}, {1, 2, 3, 4}};``?
   
    




Medium Multiple Choice Questions
----------------------------------


.. mchoice:: q7_7_8
   :practice: T
   :answer_a: The value in <code>b[0]</code> does not occur anywhere else in the array
   :answer_b: Array <code>b</code> is sorted
   :answer_c: Array <code>b</code> is not sorted
   :answer_d: Array <code>b</code> contains no duplicates
   :answer_e: The value in <code>b[0]</code> is the smallest value in the array
   :correct: a
   :feedback_a: The assertion denotes that <code>b[0]</code> occurs only once, regardless of the order or value of the other array values.
   :feedback_b: The array does not necessarily need to be in order for the assertion to be true.
   :feedback_c: We can't tell if it is sorted or not from this assertion.
   :feedback_d: The only value that must not have a duplicate is <code>b[0]</code>
   :feedback_e: <code>b[0]</code> can be any value, so long as no other array element is equal to it.

   Which of the following statements is a valid conclusion. Assume that variable ``b`` is an array of ``k`` integers and that the following is true: 
   
   .. code-block:: java

     b[0] != b[i] for all i from 1 to k-1

.. mchoice:: q7_7_9
   :practice: T
   :answer_a: whenever the first element in <code>a</code> is equal to <code>val</code>
   :answer_b: Whenever <code>a</code> contains any element which equals <code>val</code>
   :answer_c: Whenever the last element in <code>a</code> is equal to <code>val</code>
   :answer_d: Whenever more than 1 element in <code>a</code> is equal to <code>val</code>
   :answer_e: Whenever exactly 1 element in <code>a</code> is equal to <code>val</code>
   :correct: c
   :feedback_a: It is the last value in <code>a</code> that controls the final state of <code>temp</code>, as the loop is progressing through the array from 0 to the end.
   :feedback_b: Because <code>temp</code> is reset every time through the loop, only the last element controls whether the final value is true or false.
   :feedback_c: Because each time through the loop <code>temp</code> is reset, it will only be returned as true if the last value in <code>a</code> is equal to <code>val</code>.  
   :feedback_d: Because <code>temp</code> is reset every time through the loop, only the last element controls whether the final value is true or false, so it is possible for just the last value to be equal to <code>val</code>.
   :feedback_e: Because <code>temp</code> is reset every time through the loop, only the last element controls whether the final value is true or false, so it is possible for several elements to be equal to <code>val</code>.

   Consider the following code segment. Which of the following statements best describes the condition when it prints true?
   
   .. code-block:: java

     boolean temp = false;
     for (int i = 0; i < a.length; i++) {
        temp = (a[i] == val);
     }
     System.out.println(temp);
     
.. mchoice:: q7_7_14
   :practice: T
   :answer_a: k - 1
   :answer_b: k + 1
   :answer_c: k 
   :answer_d: 1
   :answer_e: 0
   :correct: a
   :feedback_a: This loop will start at 1 and continue until <code>k</code> is reached as long as <code>arr[i] < someValue</code> is true.  The last time the loop executes, <code>i</code> will equal <code>k-1</code>, if the condition is always true.  The number of times a loop executes is equal to the largest value when the loop executes minus the smallest value plus one.  In this case that is <code>(k - 1) - 1 + 1</code> which equals <code>k - 1</code>.  
   :feedback_b: This would be true if <code>arr[i] < someValue</code> was always true and the loop started at 0 instead of 1 and continued while it was less than or equal to <code>k</code>.
   :feedback_c: This would be true if <code>arr[i] < someValue</code> was always true and the loop started at 0 instead of 1.  
   :feedback_d: This would be the case if only one element in the array would fulfill the condition that <code>arr[i] < someValue</code>.
   :feedback_e: This is the minimum number of times that <code>HELLO</code> could be executed.  This would be true if <code>k</code> was less than <code>i</code> initially.  

   Consider the following code. What is the *maximum* amount of times that ``HELLO`` could possibly be printed?

   .. code-block:: java
     
      for (int i = 1; i < k; i++) {
         if (arr[i] < someValue) {
           System.out.print("HELLO")
         }
      }
   
.. mchoice:: q7_7_17
   :practice: T
   :answer_a: The values don't matter this will always cause an infinite loop.
   :answer_b: Whenever <code>a</code> includes a value that is less than or equal to zero.
   :answer_c: Whenever <code>a</code> has values larger then <code>temp</code>.
   :answer_d: When all values in <code>a</code> are larger than <code>temp</code>.
   :answer_e: Whenever <code>a</code> includes a value equal to <code>temp</code>.
   :correct: b
   :feedback_a: An infinite loop will not always occur in this code segment.
   :feedback_b: When <code>a</code> contains a value that is less than or equal to zero then multiplying that value by 2 will never make the result larger than <code>temp</code> (which was set to some value > 0), so an infinite loop will occur.
   :feedback_c: Values larger then <code>temp</code> will not cause an infinite loop.
   :feedback_d: Values larger then <code>temp</code> will not cause an infinite loop.
   :feedback_e: Values equal to <code>temp</code> will not cause the infinite loop.

   Given the following code segment, which of the following will cause an infinite loop?  Assume that ``temp`` is an ``int`` variable initialized to be greater than zero and that ``a`` is an array of ints.
   
   .. code-block:: java 

      for ( int k = 0; k < a.length; k++ ) {
         while ( a[ k ] < temp ) {
            a[ k ] *= 2;
         }
      }
      

.. mchoice:: q9_6_4
   :practice: T
   :answer_a: 4
   :answer_b: 8
   :answer_c: 9
   :answer_d: 12
   :answer_e: 10
   :correct: b
   :feedback_a: This would be correct if the variable col was 0 because then it would add 1 + 1 + 1 + 1 which is 4.   
   :feedback_b: Since col is matrix[0].length - 2 it is 4 - 2 which is 2.  This code will loop through all the rows and add all the numbers in the third column (index is 2) which is 2  + 2 + 3 + 1 which is 8.
   :feedback_c: This would be correct if the variable col was 1 because then it would add 1 + 2 + 2 + 4 which is 9.  
   :feedback_d: This would be correct if the variable col was 3 becuase then it would add 2 + 4 + 4+ 2 which is 12. 
   :feedback_e: This would be true if we were adding the values in the 3rd row (row = 2) instead of the 3rd column.  This would be 1 + 2 + 3 + 4 which is 10.   

   Given the following code segment, what is the value of sum after this code executes?
   
   .. code-block:: java 

      int[][] matrix = { {1,1,2,2},{1,2,2,4},{1,2,3,4},{1,4,1,2}};

      int sum = 0;
      int col = matrix[0].length - 2;
      for (int row = 0; row < 4; row++) {
         sum = sum + matrix[row][col];
      }
            
.. mchoice:: q9_6_5
   :practice: T
   :answer_a: { {2 3 3}, {1 2 3}, {1 1 2}, {1 1 1}} 
   :answer_b: { {2 1 1}, {3 2 1}, {3 3 2}, {3 3 3}} 
   :answer_c: { {2 1 1 1}, {3 2 1 1}, {3 3 2 1}} 
   :answer_d: { {2 3 3 3}, {1 2 3 3}, {1 1 2 3}} 
   :answer_e: { {1 1 1 1}, {2 2 2 2}, {3 3 3 3}} 
   :correct: b
   :feedback_a: This woud be true if the code put a 3 in the array when the row index is less than the column index and a 2 in the array when the row and column index are the same, and a 1 in the array when the row index is greater than the column index. 
   :feedback_b: This code will put a 1 in the array when the row index is less than the column index and a 2 in the array when the row and column index are the same, and a 3 in the array when the row index is greater than the column index. 
   :feedback_c: This code creates a 2D array with 4 rows and 3 columns so this can't be right.  
   :feedback_d: This code creates a 2D array with 4 rows and 3 columns so this can't be right.  
   :feedback_e: This code creates a 2D array with 4 rows and 3 columns so this can't be right.    

   What are the contents of ``mat`` after the following code segment has been executed? 
   
   .. code-block:: java 

      int [][] mat = new int [4][3];
      for (int row = 0; row < mat.length; row++) { 
         for (int col = 0; col < mat[0].length; col++) { 
            if (row < col) {
               mat[row][col] = 1;
            } else if (row == col) {    
               mat[row][col] = 2; 
            } else { 
               mat[row][col] = 3; 
		    } 
		 }
      }		 
               
.. mchoice:: q9_6_6
   :practice: T
   :answer_a: 4
   :answer_b: 6
   :answer_c: 9
   :answer_d: 10
   :answer_e: 20
   :correct: c
   :feedback_a: This would be correct if it was adding up all the values in the first row.  Does it?
   :feedback_b: This would be correct if it was adding up all the values in column 0.  
   :feedback_c: This adds all the values in column 1 starting with the one in the last row (row 3).    
   :feedback_d: This would be correct if it was adding up all the values in the second row.  
   :feedback_e: This would be correct if it was adding up all the values in the last row.    

   Given the following code segment, what is the value of sum after this code executes?
   
   .. code-block:: java 

      int[][] m = { {1,1,1,1},{1,2,3,4},{2,2,2,2},{2,4,6,8}};

      int sum = 0;
      for (int k = 0; k < m.length; k++) {
          sum = sum + m[m.length-1-k][1];
      }
         

Hard Multiple Choice Questions
----------------------------------

.. mchoice:: q9_6_7
   :practice: T
   :answer_a: { {6, 4, 2}, {2, 4, 6}}
   :answer_b: { {3, 2, 1}, {1, 4, 6}}
   :answer_c: { {3, 2, 1}, {1, 4, 8}}
   :answer_d: { {4, 4, 2}, {2, 4, 4}}
   :answer_e: { {3, 2, 1}, {2, 4, 4}}
   :correct: c
   :feedback_a: Check the starting values on the nested loops.
   :feedback_b: Notice that there are two if's, not an if and else.
   :feedback_c: The first if will change an odd number to an even.  The second if will also execute after an odd number has been made even.  Both loops start at index 1 so this only changes the items in the second row and second and third column.   
   :feedback_d: Both if's will execute.  Also, check the bounds on the nested loop. 
   :feedback_e: Both if's will execute.  Check the bounds on the inner loop.  When does it stop?    

   What are the contents of ``arr`` after the following code has been executed? 
   
   .. code-block:: java 

      int[][] arr = { {3,2,1},{1,2,3}};
      int value = 0;
      for (int row = 1; row < arr.length; row++) {
         for (int col = 1; col < arr[0].length; col++) {
            if (arr[row][col] % 2 == 1) {
                arr[row][col] = arr[row][col] + 1;
            }
            if (arr[row][col] % 2 == 0) {
                arr[row][col] = arr[row][col] * 2;
            }
         }
      }
      

      




