.. qnum::
   :prefix: 7-6-
   :start: 1

Code Practice with Arrays
============================

.. tabbed:: ch7Ex1

        .. tab:: Question

           .. activecode::  ch7Ex1q
              :language: java

              Fix the following code so that it prints every other value in the array ``arr1`` starting with the value at index 0.
              ~~~~
              public class Test
              {
                  public static void main(String[] args)
                  {
                      int arr1 = {1, 3, 7, 9, 15, 17};
                      for (int index = 0; index <= arr1.length; index+=2)
                      {
                          System.out.print(index + ", ");
                      }
                  }
              }


        .. tab:: Answer

           Change line 5 to add the ``[]`` on the declaration of ``arr1`` to show that it is an array of integer values.  Change line 6 to ``index < arr1.length`` so that you don't go out of bounds (the last valid index is the length minus one).  Change line 8 to print ``arr1[index]``.

           .. activecode::  ch7Ex1a
              :language: java

              Solution to question above.    
              ~~~~
              public class Test
              {
                  public static void main(String[] args)
                  {
                      int[] arr1 = {1, 3, 7, 9, 15};
                      for (int index = 0; index < arr1.length; index+=2)
                      {
                          System.out.print(arr1[index] + ", ");
                      }
                  }
              }


.. activecode::  ch7Ex2q
              :language: java
              
              Fix the following to print the values in the array ``a1`` starting with the value at the last index and then backwards to the value at the first index.
              ~~~~
              public class Test
              {
                  public static void main(String[] args)
                  {
                      int[] a1 = {1, 3, 7, 9, 15};
                      for (int i = a1.length; i > 0; i--)
                          System.out.print(arr[i] + ", ");
                  }
              }


..        .. tab:: Answer

           Change line 6 to ``a1.length - 1`` since the last valid index is one less than the length of the array and ``i >= 0`` since the first valid index is 0. Change line 7 to ``a1``.

           .. activecode::  ch7Ex2a
              :language: java

              Solution to question above.    
              ~~~~
              public class Test
              {
                  public static void main(String[] args)
                  {
                      int[] a1 = {1, 3, 7, 9, 15};
                      for (int i = a1.length - 1; i >= 0; i--)
                          System.out.print(a1[i] + ", ");
                  }
              }



.. activecode::  ch7Ex3q
              :language: java

              Rewrite the following code so that it prints all the values in an array ``arr1`` using a for-each loop instead of a ``for`` loop.
              ~~~~
              public class Test
              {
                  public static void main(String[] args)
                  {
                      int[] arr1 = {1, 3, 7, 9};
                      for (int index = 0; index < arr1.length; index++)
                      {
                          System.out.print(arr1[index] + ", ");
                      }
                  }
              }



..        .. tab:: Answer

           In a for-each loop you specify the type of the values in the array, a name for the current value, and then a ``:`` and then the name of the array.  The first time through the loop the value will be the one at index 0.  The next time the one at index 1 and so on until you reach the last value in the array.

           .. activecode::  ch7Ex3a
              :language: java

              Solution to question above.    
              ~~~~
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      int[] arr1 = {1, 3, 7, 9};
                      for (int value: arr1)
                      {
                          System.out.print(value + ", ");
                      }
                  }
              }


.. activecode::  ch7Ex4q
              :language: java

              Finish the following code so that it prints out all of the odd values in the array ``a1``.
              ~~~~
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      int[] a1 = {0, 3, 6, 7, 9, 10};
                      for (int value : a1)
                      {
                      }
                  }
              }


..        .. tab:: Answer

           If the remainder of the value divided by 2 is 1 then it is odd so print it out followed by a space (to keep the values separated).

           .. activecode::  ch7Ex4a
              :language: java

              Solution to question above.    
              ~~~~
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      int[] a1 = {0, 3, 6, 7, 9, 10};
                      for (int value : a1)
                      {
                          if (value % 2 == 1)
                          {
                              System.out.print(value + " ");
                          }
                      }
                  }
              }



.. activecode::  ch7Ex5q
              :language: java

              Finish the following method ``getSum`` to return the sum of all values in the passed array.
              ~~~~
              public class Test
              {

                  public static int getSum(int[] arr)
                  {

                  }

                  public static void main(String[] args)
                  {
                      int[] a1 = {1, 2, 5, 3};
                      System.out.println("It should print 11 " +
                                         " and your answer is: " + getSum(a1));
                  }
              }



..       .. tab:: Answer

           Declare a variable to hold the ``sum`` and initialize it to zero.  Loop through all the values in the array using a for-each loop and add each value to the ``sum``.  Return the ``sum``.

           .. activecode::  ch7Ex5a
              :language: java

              Solution to question above.    
              ~~~~
              public class Test
              {

                  public static int getSum(int[] arr)
                  {
                     int sum = 0;
                     for (int value : arr)
                     {
                         sum = sum + value;
                     }
                     return sum;
                  }

                  public static void main(String[] args)
                  {
                      int[] a1 = {1, 2, 5, 3};
                      System.out.println("It should print 11 " +
                                         " and your answer is: " + getSum(a1));
                  }
              }


.. activecode::  ch7Ex6q
              :language: java

              Finish the following method to return the sum of all of the non-negative values in the passed array.
              ~~~~
              public class Test
              {

                  public static int getSumNonNeg(int[] arr)
                  {
                  }

                  public static void main(String[] args)
                  {
                      int[] a1 = {1, 2, 5, 3, -1, -20};
                      System.out.println("The code should print 11 " +
                                         "and your answer is: " + getSumNonNeg(a1));
                  }
              }


..        .. tab:: Answer

          Declare a variable to hold the ``sum`` and initialize it to zero.  Loop through all the values in the array.  If the current value is non negative (greater than or equal to 0) then add it to the ``sum``.  Return the ``sum``.

           .. activecode::  ch7Ex6a
              :language: java

              Solution to question above.    
              ~~~~
              public class Test
              {

                  public static int getSumNonNeg(int[] arr)
                  {
                      int sum = 0;
                      for (int value : arr)
                      {
                          if (value >= 0)
                              sum = sum + value;
                      }
                      return sum;
                  }


                  public static void main(String[] args)
                  {
                      int[] a1 = {1, 2, 5, 3, -1, -20,};
                      System.out.println("The code should print 11 " +
                                         "and your answer is: " + getSumNonNeg(a1));
                  }
              }


        
.. activecode::  ch7Ex7nq
              :language: java

              
              Finish the following code to print the strings at the odd indices in the array.
              ~~~~
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      String[] stArr1 = {"Destini", "Landon", "Anaya", "Gabby", "Evert"};

                  }
              }


..        .. tab:: Answer

           Use a for loop and start the index at 1 and increment it by 2 each time through the loop.  Print the value at the index.

           .. activecode::  ch7Ex7na
              :language: java

              Solution to question above.    
              ~~~~
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      String[] stArr1 = {"Destini", "Landon", "Anaya", "Gabby", "Evert"};
                      for (int i = 1; i < stArr1.length; i+=2)
                      {
                          System.out.println(stArr1[i]);
                      }
                  }
              }


.. activecode::  ch7Ex8nq
              :language: java

              Finish the method ``getSumChars`` below to return the total number of characters in the array of strings ``strArr``.
              ~~~~ 
              public class Test
              {

                  public static int getSumChars(String[] strArr)
                  {
                  }

                  public static void main(String[] args)
                  {
                      String[] strArr = {"hi", "bye", "hola"};
                      System.out.println(getSumChars(strArr));
                  }
              }




..        .. tab:: Answer

           Declare the ``sum`` and initialize it to 0.  Use a for-each loop to loop through each string in the array.  Add the length of the current string to the ``sum``.  Return the ``sum``.

           .. activecode::  ch7Ex8na
              :language: java

              Solution to question above.    
              ~~~~
              public class Test
              {
                  public static int getSumChars(String[] strArr)
                  {
                      int sum = 0;
                      for (String str : strArr)
                      {
                          sum = sum + str.length();
                      }
                      return sum;
                  }

                  public static void main(String[] args)
                  {
                      String[] strArr = {"hi", "bye", "hola"};
                      System.out.println(getSumChars(strArr));
                  }
              }


.. activecode::  ch7Ex9nq
              :language: java

              Finish the method ``findMin`` so that it finds and returns the minimum value in the array.
              ~~~~
              public class Test
              {

                  public static int findMin(int[] arr)
                  {
                  }

                  public static void main(String[] args)
                  {
                      int[] arr = {20, -3, 18, 55, 4};
                      System.out.println(findMin(arr));
                  }
              }




..        .. tab:: Answer

           Declare a variable to hold the minimum value found and initialize it to the first value in the array.  Loop from 1 to the length of the array minus one and get the value at that index.  If the value is less than the minimum found so far reset the minimum found so far to the value.  Return the minimum.

           .. activecode::  ch7Ex9na
              :language: java

              Solution to question above.    
              ~~~~
              public class Test
              {

                  public static int findMin(int[] arr)
                  {
                       int min = arr[0];
                       int value = 0;
                       for (int i = 1; i < arr.length; i++)
                       {
                           value = arr[i];
                           if (value < min)
                           {
                               min = value;
                           }
                        }
                        return min;
                  }

                  public static void main(String[] args)
                  {
                      int[] arr = {20, -3, 18, 55, 4};
                      System.out.println(findMin(arr));
                  }
              }




.. activecode::  ch7Ex10nq
              :language: java
              
              Finish the method ``getAverage`` to calculate and return the average of all of the values in the array.
              ~~~~
              public class Test
              {

                  public static double getAverage(int[] arr)
                  {
                  }

                  public static void main(String[] args)
                  {
                      int[] arr = {20, 3, 18, 55, 4};
                      System.out.println(getAverage(arr));;
                  }
              }


..        .. tab:: Answer

           Declare a variable to hold the ``total`` and it should be of type ``double`` so that the average is a ``double``.  Initialize it to 0.  Loop through all the values in the array and add each to the ``total``.  Return the ``total`` divided by the length of the array.

           .. activecode::  ch7Ex10na
              :language: java
              
              Solution to question above.    
              ~~~~
              public class Test
              {

                  public static double getAverage(int[] arr)
                  {
                      double total = 0;
                      for (int value : arr)
                      {
                          total = total + value;
                      }
                      return total / arr.length;
                  }

                  public static void main(String[] args)
                  {
                      int[] arr = {20, 3, 18, 55, 4};
                      System.out.println(getAverage(arr));;
                  }
              }


More Practice
---------------
   
For practice with simple array manipulation and conditionals, but no loops see http://codingbat.com/java/Array-1. 
For more practice with loops and arrays go to http://codingbat.com/java/Array-2.

Here are problems without loops

* http://codingbat.com/prob/p167011
* http://codingbat.com/prob/p191991
* http://codingbat.com/prob/p146256
* http://codingbat.com/prob/p199519
* http://codingbat.com/prob/p109537

Here are problems with loops

* http://codingbat.com/prob/p180920
* http://codingbat.com/prob/p104627
* http://codingbat.com/prob/p199612
* http://codingbat.com/prob/p105031
* http://codingbat.com/prob/p100246

.. tabbed:: arr2DEx1

        .. tab:: Question

           Replace the "ADD CODE HERE" below with the code to declare and create a 3 by 3 two-dimensional int array named ``table``. The finished code will print the values 0 to 8.
           
           .. activecode::  arr2DEx1q
              :language: java
   
              public class Test1
              {
              	
                  public static void main(String[] args)
                  {
                      // ADD CODE HERE //
                      
                      // Should print the values in table
                      int count = 0;
                      for (int row = 0; row < table.length; row++) 
                      {
                          for (int col = 0; col < table.length; col++) 
                          {
                     	      table[row][col] = count;
                     	      count++;
                     	      System.out.print(table[row][col] + " ");
                      	  }
                      }
                  }
              }


        .. tab:: Answer
        
           Declaring and creating a 3 by 3 two-dimensional int array only takes one line.  To declare the array specify the type of values in the array followed by ``[][]`` to indicate a 2D array and then provide a name for the array. To create the array add an ``= new``, followed by the same type as before and ``[num rows][num cols]``.
        
           .. activecode::  arr2DEx1a
              :language: java
   
              public class Test1
              {
              
                  public static void main(String[] args)
                  {
                      int[][] table = new int[3][3];
                      
                      int count = 0;
                      for (int row = 0; row < table.length; row++) 
                      {
                          for (int col = 0; col < table[0].length; col++) 
                          {
                     	      table[row][col] = count;
                     	      count++;
                     	      System.out.print(table[row][col] + " ");
                      	  }
                      }
                  }
              }

              
 
           
Replace the "ADD CODE HERE" below with the code to declare and initialize a two-dimensional String array called ``students`` with the names "Brice, Marvin, Anna" in the first row and "Kamal, Maria, Elissa" in the second. The finished code will print all the names in the array starting with all in the first row followed by all in the second row. 
           
.. activecode::  arr2DEx2q
              :language: java
   
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      // ADD CODE HERE // 
                      
                      
                      // Should print the values in students in order
                      for (int row = 0; row < students.length; row++) 
                      {
                          for (int col = 0; col < students[0].length; col++) 
                          {
                     	      System.out.print(students[row][col] + " ");
                     	  }
                      }
                  }
              }



..        .. tab:: Answer
        
           You can declare, create, and initialize a 3 by 3 two-dimensional String array on one line as shown below.  Declare the array with ``type[][] name``.  Create and initialize an array with two rows and three columns
           using ``={ {item1, item2, item3}, {item4, item5, item6} };``.  Be sure to separate the items with commas.  Also separate the rows with a comma.
           
           .. activecode::  arr2DEx2a
              :language: java
   
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      // Can declare and initialize in one line
                      String[][] students = { {"Brice", "Marvin", "Anna"}, 
                                             {"Kamal", "Maria", "Elissa"} };
           
                      for (int row = 0; row < students.length; row++) 
                      {
                          for (int col = 0; col < students[0].length; col++) 
                          {
                     	      System.out.print(students[row][col] + " ");
                     	  }
                      }
                  }
              }

              

Print the values 47, 51, and 20 by accessing them in the  the given two-dimensional array.
           
.. activecode::  arr2DEx3q
              :language: java
   
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      int[][] arr = { {47,3,12},{51,74,20} };
                      
                      // ADD CODE HERE //
                      
                  }
              }



..        .. tab:: Answer
           
           Use ``arr[row][col]`` to get the value at a particular row and column.
           Remember that the index for the first row is 0 and the index for the first column is also 0. 
 
           .. activecode::  arr2DEx3a
              :language: java
   
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      int[][] arr = { {47,3,12},{51,74,20} };
                     
                      // Prints 47, 51, 20 in that order
                      System.out.println(arr[0][0]);
                      System.out.println(arr[1][0]);
                      System.out.println(arr[1][2]);   
                  }
              }
              


Print the values 8, 3, 87, and 34 by accessing them from the given two-dimensional array.
           
.. activecode::  arr2DEx4q
              :language: java
   
              public class Test1
              {
                  public static void main(String[] args)
                  {
               	      int[][] arr = { {10,39,8},{3},{35,87},{22},{34} };
               	      
               	      // ADD CODE HERE //
                     
                  }
              }



..        .. tab:: Answer
           
           Use ``arr[row][col]`` to get the value at a particular row and column.
           Remember that the index for the first row is 0 and the index for the first column is also 0.
 
           .. activecode::  arr2DEx4a
              :language: java
   
              public class Test1
              {
                  public static void main(String[] args)
                  {
               	      int[][] arr = { {10,39,8},{3},{35,87},{22},{34} };
               		
               	      // Prints 8, 3, 87, and 34 in order
               	      System.out.println(arr[0][2]);  
               	      System.out.println(arr[1][0]);  
               	      System.out.println(arr[2][1]);  
               	      System.out.println(arr[4][0]);  
                     
                  }
              }
              
Print the number of rows in the given two-dimensional array, or the length of the outer array. Then print the number of columns, or the length of each inner array. 
           
**Ex.** The array { {"hello","there","world"},{"how","are","you"} } should print:
           
Rows: 2
           
Columns: 3
           
.. activecode::  arr2DEx5q
              :language: java
   
              public class Test1 {
              
                  public static void main(String[] args)
                  {
                      String[][] arr = { {"hello","there","world"},
                                        {"how","are","you"} };
                                        
                      System.out.println("Rows:");
                      // ADD CODE TO PRINT NUMBER OF ROWS HERE // 
                      
                      System.out.println("Columns:");
                      // ADD CODE TO PRINT NUMBER OF COLUMNS HERE // 
                  	
                  }
              }

..        .. tab:: Answer
           
          To get the number of rows, or the length of the outer array, use ``arrayName.length`` . 
          To get the number of columns, or the length of an inner array, use ``arrayName[0].length``. 
 
          .. activecode::  arr2DEx5a
              :language: java
   
              public class Test1 {
                  public static void main(String[] args)
                  {
                      String[][] arr = { {"hello","there","world"},
                                        {"how","are","you"} };
                                        
                      System.out.println("Rows:" + arr.length);
                      System.out.println();
                      System.out.println("Columns:" + arr[0].length);
                  }
              }
              
Loop through the given two-dimensional array, printing out the values in the first row followed by those in the second row and so on.
           
.. activecode::  arr2DEx6q
              :language: java
   
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      String[][] arr = { {"Hey ", "there! "},{"I ", "hope "}, 
                                        {"you ", "are "}, {"doing ", "well"} };
                                        
                      // ADD CODE HERE // 
                  	
                  }
              }

..        .. tab:: Answer
           
           Create a loop that iterates through all of the outer arrays, or the rows using ``arrayName.length``.
           Then iterate through the inner arrays, or columns, using ``arrayName[0].length``.
 
           .. activecode::  arr2DEx6a
              :language: java
   
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      String[][] arr = { {"Hey ", "there! "},{"I ", "hope "}, 
                                        {"you ", "are "}, {"doing ", "well"} };
                                        
                      for (int row = 0; row < arr.length; row++) 
                      {
                          for (int col = 0; col < arr[0].length; col++) 
                          {
                              System.out.println(arr[row][col]);
                          }
                      }
                  }
              }
              

Declare and create a two-dimensional array of strings named ``colors``.  Put the colors ("red", "yellow", "blue") in the first row, and the colors ("orange", "green", "purple") in the second row. Then print every value in the array.
           
.. activecode::  arr2DEx7q
              :language: java
   
              public class Test1
              {
                  public static void main(String[] args)
                  {
                      // ADD CODE HERE //
                  }
              }

..        .. tab:: Answer
           
           Declare and initialize the array in one statement as shown below.  Loop through the rows and columns and print each value.
 
           .. activecode::  arr2DEx7a
              :language: java
   
              public class Test1
              {
                  public static void main(String[] args)
                  {         
                      String[][] colors = { {"red","yellow","blue"},
                                           {"orange","green","purple"} };
                    
                      for (int row = 0; row < colors.length; row++) 
                      {
                          for (int col = 0; col < colors[0].length; col++) 
                          {
                    	      System.out.println(colors[row][col]);
                    	  }
                      }
                  }
              }
              

Replace the "ADD CODE HERE" below with the code to count and print the number of 7's that are in the 2d array. It should print 2.
           
.. activecode::  arr2DEx8q
              :language: java
   
              public class Test1
              {
              	
                  public static void main(String[] args)
                  {
                      int[][] array = { {4,7,8},{8,8,7} };
                      
                      //ADD CODE HERE
					  
                  }
              }


..        .. tab:: Answer
        
           Use a nested for loop to loop through all the elements in a 2d array.  Initialize a count variable to zero before the loop, and every time there is a 7 at the current row and column, increment the count variable by 1.
        
           .. activecode::  arr2DEx8a
              :language: java
   
              public class Test1
              {
              	
                  public static void main(String[] args)
                  {
                      int[][] array = { {4,7,8},{8,8,7} };
                      
                      int count = 0;
					  
                      for (int row = 0; row < array.length; row++) 
                      {
                          for (int col = 0; col < array[0].length; col++) 
                          {
                              if (array[row][col]==7)
                                  count++;
                          }
                          
                      }
                      
                      System.out.println(count);
                  }
              }

              
Replace the "ADD CODE HERE" below with the code to print out the sum of the numbers in the second row of the "table" array.  It should print 18.
           
.. activecode::  arr2DEx9q
              :language: java
   
              public class Test1
              {
              	
                  public static void main(String[] args)
                  {
                      int[][] table = { {1,4,9},{11,4,3},{2,2,3} };
                      
                      //ADD CODE HERE
 
                  }
              }


..        .. tab:: Answer
        
           Use a loop to find the sum of all of the values in the second row. Since we are only looping through one row, we do not need a nested for loop. Initialize the sum to 0 and then loop through each element in the second row and add it to the sum.
        
           .. activecode::  arr2DEx9a
              :language: java
   
              public class Test1
              {
              	
                  public static void main(String[] args)
                  {
                       int[][] table = { {1,4,9},{11,4,3},{2,2,3} };
                       int sum = 0;
					  
                       for (int col = 0; col < table[0].length; col++) 
                       {
                           sum += table[1][col];
                       }
                       
                       System.out.println("The sum is: "+sum);
                  }
              }

              

Replace the "ADD CODE HERE" below with the code to find the sum of the values on the diagonal from [0][0] to [num rows - 1][num rows - 1] Print the sum.  It should print 5.
           
.. activecode::  arr2DEx10q
              :language: java
   
              public class Test1
              {
              	
                  public static void main(String[] args)
                  {
                      int[][] array = { {1,2,3},{-1,-2,-3},{4,5,6} };
                      
                      //ADD CODE HERE

                  }
              }


..        .. tab:: Answer
        
           Create a variable to hold the total and loop through the rows in the array.  Each time through the loop add the value at [row][row] to the total.  Print the total.
		   
           .. activecode::  arr2DEx10a
              :language: java
   
              public class Test1
              {
              	
                  public static void main(String[] args)
                  {
                      int[][] array = { {1,2,3},{-1,-2,-3},{4,5,6} };
                      int total = 0;
                      
                      for (int row = 0; row < array.length; row++)
                      {
                          total += array[row][row];
                                   
                      }
                      
                      System.out.println("The sum of the diagonal is: "+ total);
                      
                  }
              }

              

Replace the “ADD CODE HERE” below with the code to declare and create a two-dimensional array of integers ``numbers`` with the numbers (1,2,3) in the first row, and the numbers (4,5,6) in the second row. Then loop through the two-dimensional array, printing out the values in the first row followed by those in the second row.

.. activecode::  arr2DEx11q
              :language: java

              public class Test1
              {
                  public static void main(String[] args)
                  {
                      // ADD CODE HERE //
                  }
              }

..        .. tab:: Answer

           Declare and initialize the array in one statement as shown below. Loop through the rows and columns and print each value.

           .. activecode::  arr2DEx11a
              :language: java

              public class Test1
              {
                  public static void main(String[] args) 
                  {
                      int[][] arr = { {1,2,3}, {4,5,6} };
                      
                      for (int row = 0; row < arr.length; row++) 
                      {
                          for (int col = 0; col < arr[0].length; col++) 
                          {
                              System.out.println(arr[row][col]);
                          }
                      }
                  }
              }



Replace the “ADD CODE HERE” below with the code to declare and create a two-dimensional array of integers ``numbers`` with the numbers (1,2,3) in the first row, the numbers (4,5,6) in the second row, and the numbers (7,8,9) in the third row. Then loop through the two-dimensional array, printing out the values in the first row followed by those in the second row and so on.

.. activecode::  arr2DEx12q
              :language: java

              public class Test1
              {
                  public static void main(String[] args)
                  {
                      // ADD CODE HERE //
                  }
              }

..        .. tab:: Answer

           Declare and initialize the array in one statement as shown below. Loop through the rows and columns and print each value.

           .. activecode::  arr2DEx12a
              :language: java

              public class Test1
              {
                  public static void main(String[] args)
                  {
                      int[][] arr = { {1,2,3}, {4,5,6}, {7,8,9} };
                      for (int row = 0; row < arr.length; row++) 
                      {
                          for (int col = 0; col < arr[1].length; col++) 
                          {
                              System.out.println(arr[row][col]);
                          }
                      }
                  }
              }



Given the following array, replace the “ADD CODE HERE” below with the code to replace the word "purple" with "yellow".

.. activecode::  arr2DEx13q
              :language: java

              public class Test1
              {
                  public static void main(String[] args)
                  {
                      String[][] arr = { {"red","orange", "purple"}, {"green","blue", "indigo"} };
                      
                      // ADD CODE HERE //
                      
                      for (int row = 0; row < arr.length; row++)
                      {
                          for (int col = 0; col < arr[1].length; col++)
                          {
                              System.out.println(arr[row][col]);
                          }
                      }
                  }
              }

..        .. tab:: Answer
        
           Use arr[row][col] = value; to set the value at a particular row and column.  Remember the index of the first row is 0 and the index of the first column is also 0.


           .. activecode::  arr2DEx13a
              :language: java

              public class Test1
              {
                  public static void main(String[] args)
                  {
                      String[][] arr = { {"red","orange", "purple"}, {"green","blue", "indigo"} };
                      
                      arr[0][2] = "yellow";
                      
                      for (int row = 0; row < arr.length; row++) 
                      {
                          for (int col = 0; col < arr[1].length; col++) 
                          {
                              System.out.println(arr[row][col]);
                          }
                      }
                  }
              }

