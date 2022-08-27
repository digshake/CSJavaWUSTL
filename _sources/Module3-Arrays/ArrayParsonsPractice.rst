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


.. parsonsprob:: q7_5_4
   :numbered: left
   :practice: T
   :adaptive:

   The following program segment is a method that should return the smallest integer given an array of integers (the parameter).  But, the blocks have been mixed up and include <b>one extra block</b> that is not needed in a correct solution.  Drag the blocks from the left and put them in the correct order with the correct indentation on the right.  Click the <i>Check Me</i> button to check your solution. </p>
   -----
   public static int findSmallest(int[] arr) {
   =====
       int smallest = arr[0];
   =====
       for (int i = 0 ; i < arr.length; i++) {
   =====
           if (arr[i] < smallest) {
   =====
           if (arr[i] > smallest) { #distractor
   =====
               smallest = arr[i];
   =====
           }
   =====
       } //end for loop
   =====
       return smallest;
   =====
   } //end findSmallest method


.. parsonsprob:: q7_5_5
   :numbered: left
   :practice: T
   :adaptive:

   The following program segment is a method that should return the average given an array of integers (the parameter).  But, the blocks have been mixed up and include <b>one extra block</b> that is not needed in a correct solution.  Drag the blocks from the left and put them in the correct order with the correct indentation on the right.  Click the <i>Check Me</i> button to check your solution. </p>
   -----
   public static double findAverage(int[] arr) {
   =====
       double sum = 0;
   =====
       int sum = 0; #distractor
   =====
       for (int i = 0; i < arr.length; i++) {
   =====
           sum += arr[i];
   =====
       } //end for loop
   =====
       return (sum / arr.length);
   =====
   } //end findAverage method


.. parsonsprob:: q7_5_6
   :numbered: left
   :practice: T
   :adaptive:

   The following program segment is a method that should return the largest integer given an array of integers (the parameter).  But, the blocks have been mixed up and include <b>two extra blocks</b> that are not needed in a correct solution.  Drag the needed code from the left to the right and put them in order with the correct indention so that the code would work correctly.  Click the <i>Check Me</i> button to check your solution. </p>
   -----
   public static int findLargest(int[] arr) {
   =====
      int largest = arr[0];
   =====
      int largest = arr.get(0); #distractor
   =====
      for (int i = 0; i < arr.length; i++) {
   =====
          if (largest < arr[i]) {
   =====
          if (largest > arr[i]) { #distractor
   =====
              largest = arr[i];
   =====
          } //end conditional
   =====
      } //end for loop
   =====
      return largest;
   =====
   } //end findLargest method


.. parsonsprob:: q7_5_7
   :numbered: left
   :practice: T
   :adaptive:

   The following program segment is a method that should return an integer array that is "right shifted" by one -- so {6, 2, 5, 3} returns {3, 6, 2, 5} (the parameter). Note that the method return type is int[] which means it will return an int array. But, the blocks have been mixed up and include <b>one extra block</b> that is not needed in a correct solution.  Drag the blocks from the left and put them in the correct order on the right.  Click the <i>Check Me</i> button to check your solution. </p>
   -----
   public static int[] shiftRight(int[] arr) {
   =====
       int[] result = new int[arr.length];
   =====
       result[0] = arr[arr.length-1];
   =====
       for (int i = 0; i < arr.length - 1; i++) {
   =====
       for (int i = 0; i < arr.length; i++) { #distractor
   =====
           result[i + 1] = arr[i];
   =====
       } //end for loop
   =====
       return result;
   =====
   } //end shiftRight method


.. parsonsprob:: q7_5_8
   :numbered: left
   :practice: T
   :adaptive:

   The following program segment is a method that should return a new array of length 2 containing the middle two elements of a given array of integers of even length (the parameter) -- so {1,2,3,4} should return {2,3}.  But, the blocks have been mixed up and include <b>one extra block</b> that is not needed in a correct solution.  Drag the blocks from the left and put them in the correct order on the right.  Click the <i>Check Me</i> button to check your solution. </p>
   -----
   public static int[] makeMiddle(int[] arr) {
   =====
       int[] result = new int[2];
   =====
       int middleIndex = (arr.length / 2) - 1;
   =====
       int middleIndex = (arr.length / 2); #distractor
   =====
       result[0] = arr[middleIndex];
       result[1] = arr[middleIndex + 1];
   =====
       return result;
   =====
   } //end makeMiddle method


.. parsonsprob:: q7_5_9
   :numbered: left
   :practice: T
   :adaptive:

   The following program segment is a method that should return string array that is in reverse order -- so {"b", "a", "z"} should return {"z", "a", "b"}.  But, the blocks have been mixed up and include <b>two extra blocks</b> that are not needed in a correct solution.  Drag the blocks from the left and put them in the correct order on the right.  Click the <i>Check Me</i> button to check your solution. </p>
   -----
   public static String[] reverse(String[] arr) {
   =====
       String[] result = new String[arr.length];
   =====
       int i = arr.length - 1;
   =====
       int i = arr.length; #distractor
   =====
       for (String element: arr) {
   =====
       for (element: arr) { #distractor
   =====
         result[i] = element;
   =====
         i--;
   =====
       } //end for loop
   =====
       return result;
   =====
   } //end reverse method


.. parsonsprob:: q7_5_10
   :numbered: left
   :practice: T
   :adaptive:

   The following program copies the first half of an array given as an argument to the method into a result array which is returned. But, the blocks have been mixed up and include <b>one extra block</b> that is not needed in a correct solution.  Drag the blocks from the left and put them in the correct order on the right.  Click the <i>Check Me</i> button to check your solution. </p>
   -----
   public static int[] firstHalf(int[] arr) {
   =====
       int[] result = new int[arr.length / 2];
   =====
       for (int i = 0; i < result.length; i++) {
   =====
       for (int i = 0; i < arr.length; i++) { #distractor
   =====
         result[i] = arr[i];
   =====
       } //end for loop
   =====
       return result;
   =====
   } //end firstHalf method





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


.. parsonsprob:: q9_4_3
   :numbered: left
   :practice: T
   :adaptive:
   :noindent:

   The following program segment is a method that should accept a two-dimensional int array and return the sum of all of its values.  But, the blocks have been mixed up and include <b>three extra blocks</b> that are not needed in a correct solution.  Drag the needed blocks from the left and put them in the correct order on the right.  Click the <i>Check Me</i> button to check your solution.</p>
   -----
   public static int sumVals(int[][] nums) {
   =====
      int sum = 0;
   =====
      int sum; #distractor
   =====
      for (int row = 0; row < nums.length; row++) {
   =====
      for (int row = 0; row < nums.length(); row++) { #paired
   =====
            for (int col = 0; col < nums[row].length; col++) {
   =====
                sum += nums[row][col];
   =====
                sum = nums[row][col]; #paired
   =====
            } //end inner for loop
   =====
      } //end outer for loop
      return sum;
   =====
   } //end method


.. parsonsprob:: q9_4_4
   :numbered: left
   :practice: T
   :adaptive:
   :noindent:

   The following program segment is a method that should accept a two-dimensional String array "image" and flip the "image" 180 degrees vertically. For example:  </br>

   1 2 3 4&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;4 3 2 1 </br>
   1 2 3 4&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;4 3 2 1 </br>
   1 2 3 4&nbsp;&nbsp;->&nbsp;&nbsp;4 3 2 1 </br>
   1 2 3 4&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;4 3 2 1 </br>

   But, the blocks have been mixed up and include <b>one extra block</b> that is not needed in a correct solution.  Drag the needed blocks from the left and put them in the correct order on the right.  Click the <i>Check Me</i> button to check your solution.</p>
   -----
   public static void flipImage(String[][] image) {
   =====
       for (int row = 0; row < image.length; row++) {
   =====
           for (int col = 0; col < image[0].length / 2; col++) {
   =====
               String temp = image[row][col];
               image[row][col] = image[row][image.length - 1 - col];
               image[row][image.length - 1 - col] = temp;
   =====
               image[row][col] = image[row][image.length - 1 - col]; #paired
               image[row][image.length - 1 - col] = image[row][col];
   =====
           } //end inner for loop
       } //end outer for loop
   } //end method


.. parsonsprob:: q9_4_5
   :numbered: left
   :practice: T
   :adaptive:
   :noindent:

   The following program segment is a method that should accept a two-dimensional array of ints and edit it such that all even numbers are replaced by zero.  But, the blocks have been mixed up and include <b>two extra blocks</b> that are not needed in a correct solution.  Drag the needed blocks from the left and put them in the correct order on the right.  Click the <i>Check Me</i> button to check your solution.</p>
   -----
   public static void makeEvenNumsZero(int[][] nums) {
   =====
       for (int row = 0; row < nums.length; row++) {
   =====
           for (int col = 0; col < nums[row].length; col++) {
   =====
           for (int col = 0; col < nums[row].length(); col++) { #distractor
   =====
               if (nums[row][col] % 2 == 0) {
                   nums[row][col] = 0;
               } //end if
   =====
               if (nums[row][col] % 2 == 1) { #distractor
                   nums[row][col] = 0;
               } //end if
   =====
           } //end inner for loop
   =====
       } //end outer for loop
   } //end method


.. parsonsprob:: q9_4_6
   :numbered: left
   :practice: T
   :adaptive:

   The following program segment is a method that should accept a two-dimensional array of ints and a desired int and return the number of occurrences of the desired int in the two-dimensional array.  But, the blocks have been mixed up and include <b>two extra blocks</b> that are not needed in a correct solution.  Drag the needed blocks from the left and put them in the correct order on the right.  Click the <i>Check Me</i> button to check your solution.</p>
   -----
   public static int numOccurrences(int[][] nums, 
                                    int desired) {
   =====
       int occurrences = 0;
   =====
       int occurrences; #distractor
   =====
       for (int i = 0; i < nums.length; i++) {
           for (int j = 0; j < nums[i].length; j++) {
   =====
               if (nums[i][j] == desired) {
                   occurrences++;
               }
   =====
               if (nums[i][j] != desired) { #distractor
                   occurrences++;
               }
   =====
           } //end inner for loop
       } //end outer for loop
   =====
       return occurrences;
   } //end method


.. parsonsprob:: q9_4_7
   :numbered: left
   :practice: T
   :adaptive:

   The following program segment is a method that should accept a two-dimensional int array and return a single dimensional (normal) int array containing the average of each of the columns.  But, the blocks have been mixed up and include <b>three extra blocks</b> that are not needed in a correct solution.  Drag the needed blocks from the left and put them in the correct order on the right.  Click the <i>Check Me</i> button to check your solution.</p>
   -----
   public static int[] averageCols(int[][] nums) {
   =====
       int[] averages = new int[nums.length]; #distractor
   =====
       int[] averages = new int[nums[0].length];
   =====
       for (int col = 0; col < nums[0].length; col++) {
   =====
           int colSum = 0;
   =====
           for (int row = 0; row < nums.length; row++) {
               colSum += nums[row][col];
           } //end inner for loop
   =====
           for (int row = 0; row < nums.length; row++) { #distractor
               colSum += nums[col][row];
           } //end inner for loop
   =====
           averages[col] = colSum / nums.length;
   =====
           averages[col] = colSum / nums.length(); #distractor
   =====
       } //end outer for loop
       return averages;
   } //end method


.. parsonsprob:: q9_4_8
   :numbered: left
   :practice: T
   :adaptive:

   The following program segment is a method that should accept a two-dimensional int array and return a new two-dimensional int array containing only the odd index rows.  But, the blocks have been mixed up and include <b>three extra blocks</b> that are not needed in a correct solution.  Drag the needed blocks from the left and put them in the correct order on the right.  Click the <i>Check Me</i> button to check your solution.</p>
   -----
   public static int[][] oddRows(int[][] nums) {
   =====
   public static int[] oddRows(int[][] nums) { #distractor
   =====
       int[][] odds = new int[nums.length / 2][nums[0].length];
   =====
       int[][] odds = new int[nums.length][nums[0].length]; #distractor
   =====
       int index = 0;
       for (int i = 0; i < nums.length; i++) {
   =====
           if (i % 2 == 1) {
   =====
               for (int j = 0; j < nums[i].length; j++) {
                   odds[index][j] = nums[i][j];
               }
   =====
               for (int j = 0; j < nums[i].length; j++) { #distractor
                   odds[index][j] = nums[j][i];
               }
   =====
               index++;
   =====
           } //end if
   =====
       } //end outer for loop
       return odds;
   } //end method


.. parsonsprob:: q9_4_9
   :numbered: left
   :practice: T
   :adaptive:

   The following program segment is a method that should accept a two-dimensional String array, in which each row contains the characters of a word.  The method should return a single-dimensional (normal) String array containing the words in each row of the two-dimensional array.

   Take for example, the input 2d array: { {"b", "a", "t", "h"},
                                          {"t", "e", "n", "s"},
                                          {"j", "a", "c", "k"},
                                          {"l", "a", "z", "y"}}

   Resulting array: {"bath", "tens", "jack", "lazy"}

   But, the blocks have been mixed up.  Drag the needed code from the left to the right and put them in order with the correct indention so that the code would work correctly.  Click the <i>Check Me</i> button to check your solution.</p>
   -----
   public static String[] breakIntoLetters(String[][] words) {
   =====
      String[] result = new String[words.length];
   =====
      for (int i = 0; i < words.length; i++) {
   =====
          String word = "";
   =====
          for (int j = 0; j < words[i].length; j++) {
              word += words[i][j];
          }
   =====
          result[i] = word;
   =====
      } //end for loop
      return result;
   =====
   } //end method


.. parsonsprob:: q9_4_10
   :numbered: left
   :practice: T
   :adaptive:

   The following program segment is a method that should accept a two-dimensional int array, and return a single-dimensional (normal) int array containing the max of each row.  But, the blocks have been mixed up and include <b>one extra block</b> that is not needed in a correct solution.  Drag the needed code from the left to the right and put them in order with the correct indention so that the code would work correctly.  Click the <i>Check Me</i> button to check your solution.</p>
   -----
   public static int[] maxEachRow(int[][] nums) {
   =====
      int[] max = new int[nums.length];
   =====
      for (int i = 0; i < nums.length; i++) {
   =====
          int maxVal = nums[i][0];
          for (int j = 1; j < nums[i].length; j++) {
   =====
              if (maxVal < nums[i][j]) {
                  maxVal = nums[i][j];
              }
   =====
              if (maxVal > nums[i][j]) { #distractor
                  maxVal = nums[i][j];
              }
   =====
          } //end inner for loop
          max[i] = maxVal;
   =====
      } //end outer for loop
      return max;
   } //end method





