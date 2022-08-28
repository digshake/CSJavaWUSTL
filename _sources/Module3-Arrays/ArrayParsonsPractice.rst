.. qnum::
   :prefix: 7-5-
   :start: 1

Mixed Up Code Practice
------------------------------

Try to solve each of the following. Click the *Check Me* button to check each solution.  You will be told if your solution is too short, has a block in the wrong order, or you are using the wrong block.  Some of the problems have an extra block or two that aren't needed in the correct solution.  Try to solve these on your phone or other mobile device!

.. parsonsprob:: q7_5_1
   :numbered: left
   :practice: T
   :adaptive:
   :noindent:

   The following program segment should double each element in the array then print out the new value -- so (1,2,3,4,5) should become (2,4,6,8,10).  But, the blocks have been mixed up.  Drag the blocks from the left and put them in the correct order on the right.  Click the <i>Check Me</i> button to check your solution.</p>
   -----
   int[] arr = {1, 2, 3, 4, 5};
   =====
   for (int i = 0; i < arr.length; i++) {
   =====
       arr[i] = arr[i] * 2;
   =====
       System.out.println(arr[i]);
   =====
   }


.. parsonsprob:: q7_5_2
   :numbered: left
   :practice: T
   :adaptive:
   :noindent:

   The following program segment should fill an array with elements that count up from 0 to 50 by 5 (0, 5, 10, 15, 20...).  But the blocks have been mixed up.  Drag the needed blocks from the left and put them in the correct order on the right.  Click the <i>Check Me</i> button to check your solution.</p>
   -----
   int[] arr = new int[11];
   =====
   for (int i = 0; i < 11; i++) {
   =====
       arr[i] = i * 5;
   =====
       System.out.println(arr[i]);
   =====
   }


.. parsonsprob:: q7_5_3
   :numbered: left
   :practice: T
   :adaptive:
   :noindent:

   The following program segment should print each element in the array that is even using an enhanced for each loop.  But, the blocks have been mixed up.  Drag the blocks from the left and put them in the correct order on the right.  Click the <i>Check Me</i> button to check your solution. </p>
   -----
   int[] arr = {14, -5, 2, 17, 29, -8, 36};
   =====
   for (int value : arr) {
   =====
       if (value % 2 == 0) {
   =====
           System.out.println(value);
   =====
       } //end conditional
   =====
   } //end for loop




Try to solve each of the following. Click the *Check Me* button to check each solution.  You will be told if your solution is too short, has a block in the wrong order, or you are using the wrong block.  Some of the problems have an extra block or two that aren't needed in the correct solution.  Try to solve these on your phone or other mobile device!


.. parsonsprob:: q9_4_1
   :numbered: left
   :practice: T
   :adaptive:
   :noindent:

   The following program segment should create a 10 by 10 two-dimensional int array. It should fill this array with numbers 0 to 99 from left to right, top row to bottom row and print the output (in row-column order).  But, the blocks have been mixed up and contain an extra block that is not needed in the solution.  Drag the needed blocks from the left and put them in the correct order on the right.  Click the <i>Check Me</i> button to check your solution.</p>
   -----
   int[][] table = new int[10][10];
   =====
   for (int row = 0; row < table.length; row++) {
       for (int col = 0; col < table[row].length; col++) {
   =====
           table[row][col] = col + 10 * row;
   ===== 
           table[row][col] = row + 10 * col; #paired
   =====
           System.out.print(table[row][col] + "\t");
   =====
       } //end inner for loop
   } //end outer for loop


.. parsonsprob:: q9_4_2
   :numbered: left
   :practice: T
   :adaptive:
   :noindent:

   The following program segment should create a 8 by 8 two-dimensional int array. It should fill this array with a checkered pattern of 0s and 1s -- starting with a 1 in the top left corner and print the output (in row-column order).  But, the blocks have been mixed up and include <b>one extra block</b> that is not needed in a correct solution.  Drag the needed blocks from the left and put them in the correct order on the right.  Click the <i>Check Me</i> button to check your solution.</p>
   -----
   int[][] checkerboard = new int[8][8];
   =====
   for (int row = 0; row < checkerboard.length; row++) {
       for (int col = 0; col < checkerboard[row].length; col++) {
   =====
           if ( (row + col) % 2 == 0) {
   =====
           if ( (row + col) % 2 == 1) { #paired
   =====
               checkerboard[row][col] = 1;
   =====
           } //end if
   =====
           System.out.print(checkerboard[row][col] + " ");
   =====
       } //end inner for loop
   } //end outer for loop

