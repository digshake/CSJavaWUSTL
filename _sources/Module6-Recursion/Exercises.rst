.. qnum::
   :prefix:  11-7-
   :start: 1
   
Exercises
====================

A recursive method contains a call to itself.  The recursion stops when a base case test is true and a value is returned.


.. clickablearea:: rec_base2
   :question: Click on the line or lines that contain the test for the base case
   :iscode:
   :feedback: When a base case test is true a value is returned and the recursion stops

   :click-incorrect:public static int mystery(int n):endclick:
   :click-incorrect:{:endclick:
       :click-correct:if (n == 0):endclick:
           :click-incorrect:return 1;:endclick:
       :click-incorrect:else:endclick:
           :click-incorrect:return 2 * mystery (n - 1);:endclick:
   :click-incorrect:}:endclick:

.. clickablearea:: rec_base3
   :question: Click on the line or lines that contain the test for the base case
   :iscode:
   :feedback: When a base case test is true a value is returned and the recursion stops

   :click-incorrect:public static int bunnyEars(int bunnies):endclick:
   :click-incorrect:{:endclick:
       :click-correct:if (bunnies == 0) return 0;:endclick:
       :click-correct:else if (bunnies == 1) return 2;:endclick:
       :click-incorrect:else return 2 + bunnyEars(bunnies - 1);:endclick:
   :click-incorrect:}:endclick:

.. clickablearea:: rec_base4
      :question: Click on the line or lines that contain the test for the base case
      :iscode:
      :feedback: When a base case test is true a value is returned and the recursion stops

      :click-incorrect:public static void mystery (int x) {:endclick:
          :click-incorrect:System.out.print(x % 10);:endclick:
          :click-correct:if ((x / 10) != 0) {:endclick:
              :click-incorrect:mystery(x / 10);:endclick:
          :click-incorrect:}:endclick:
          :click-incorrect:System.out.print(x % 10);:endclick:
      :click-incorrect:}:endclick:

.. clickablearea:: rec_base5
   :question: Click on the line or lines that contain the test for the base case
   :iscode:
   :feedback: When a base case test is true a value is returned and the recursion stops

   :click-incorrect:public static int mystery(String str):endclick:
   :click-incorrect:{:endclick:
       :click-correct:if (str.length() == 1) return 0;:endclick:
       :click-incorrect:else:endclick:
       :click-incorrect:{:endclick:
           :click-incorrect:if (str.substring(0,1).equals("y")) return 1 +:endclick:
                              :click-incorrect:mystery(str.substring(1));:endclick:
            :click-incorrect:else return mystery(str.substring(1));:endclick:
         :click-incorrect:}:endclick:
      :click-incorrect:}:endclick:



Easier Multiple Choice Questions
----------------------------------


.. mchoice:: qre_1
   :practice: T
   :answer_a: 1
   :answer_b: 3
   :answer_c: 4
   :answer_d: 5
   :correct: d
   :feedback_a: This is the method declaration.  Look for a call to the same method in the body of the method.
   :feedback_b: This is a conditional, not a method call.
   :feedback_c: This is a return statement, not a method call.
   :feedback_d: This line contains a call to the same method which makes this method recursive.

   Which line has the recursive call?

   .. code-block:: java
      :linenos:

      public static int factorial(int n)
      {
         if (n == 0)
            return 1;
         else return n * factorial(n-1);
      }

.. mchoice:: qre_2
   :practice: T
   :answer_a: 1
   :answer_b: 3
   :answer_c: 4
   :answer_d: 5
   :answer_e: 6
   :correct: e
   :feedback_a: This is the method declaration.  Look for a call to the same method in the body of the method.
   :feedback_b: This is a conditional, not a method call.
   :feedback_c: This is a return statement, not a method call.
   :feedback_d: This is an else which is part of a conditional, not a method call.
   :feedback_e: This line contains a call to the same method which makes this method recursive.

   Which line has the recursive call?

   .. code-block:: java
      :linenos:

      public String starString(int n)
      {
         if (n == 0) {
            return "*";
         } else {
            return starString(n - 1) + starString(n - 1);
         }
      }

.. mchoice:: qre_3
   :practice: T
   :answer_a: 0
   :answer_b: 1
   :answer_c: 2
   :answer_d: 3
   :correct: c
   :feedback_a: Look at line 7 more closely.
   :feedback_b: Many recursive methods only have one recursive call.  But, this one has two.
   :feedback_c: Line 7 has two calls to <code>fibonacci</code>.
   :feedback_d: There are not 3 calls to <code>fibonacci</code>.

   How many recursive calls does the following method contain?

   .. code-block:: java
      :linenos:

      public static int fibonacci(int n)
      {
         if (n == 0)
            return 0;
         else if (n == 1)
            return 1;
         else return fibonacci(n-1) + fibonacci(n-2);
  	  }

.. mchoice:: qre_4
   :practice: T
   :answer_a: 0
   :answer_b: 1
   :answer_c: 2
   :answer_d: 3
   :correct: b
   :feedback_a: Look for a call to the same method in the body of the method.
   :feedback_b: Line 6 has one call to <code>multiplyEvens</code>.
   :feedback_c: Where do you see 2 calls to <code>multiplyEvens</code>?
   :feedback_d: Where do you see 3 calls to <code>multiplyEvens</code>?

   How many recursive calls does the following method contain?

   .. code-block:: java
      :linenos:

      public static int multiplyEvens(int n)
      {
         if (n == 1) {
            return 2;
         } else {
            return 2 * n * multiplyEvens(n - 1);
         }
      }


Medium Multiple Choice Questions
----------------------------------


.. mchoice:: qrm_1
   :practice: T
   :answer_a: 1441
   :answer_b: 43211234
   :answer_c: 3443
   :answer_d: 12344321
   :answer_e: Many digits are printed due to infinite recursion.
   :correct: b
   :feedback_a: The first call to <code>mystery</code> with the integer 1234 will print 1234 % 10. The '%' means modulo or remainder. The remainder of 1234 divided by 10 is 4 so the first thing printed must be 4.
   :feedback_b: This has a recursive call which means that the method calls itself when (x / 10) is greater than or equal to zero. Each time the method is called it prints the remainder of the passed value divided by 10 and then calls the method again with the result of the integer division of the passed number by 10 (which throws away the decimal part). After the recursion stops by <code>(x / 10) == 0</code> the method will print the remainder of the passed value divided by 10 again.
   :feedback_c: The first call to <code>mystery</code> with the integer 1234 will print 1234 % 10. The '%' means modulo or remainder. The remainder of 1234 divided by 10 is 4 so the first thing printed must be 4.
   :feedback_d: The first call to <code>mystery</code> with the integer 1234 will print 1234 % 10. The '%' means modulo or remainder. The remainder of 1234 divided by 10 is 4 so the first thing printed must be 4.
   :feedback_e: When the recursive call to <code>mystery(1)</code> occurs (the 4th call to mystery), the division of x /10 equals .01--this becomes 0 because this is integer division and the remainder is thrown away. Therefore the current call will be completed and all of the previous calls to <code>mystery</code> will be completed.

   Given the following method declaration, which of the following is printed as the result of the call ``mystery(1234)``?

   .. code-block:: java
      :linenos:

      //precondition:  x >=0
      public static void mystery (int x)
      {
         System.out.print(x % 10);

         if ((x / 10) != 0)
         {
            mystery(x / 10);
         }
         System.out.print(x % 10);
      }

You can step through the code using the Java Visualizer by clicking on the following link: `Q-11-7-1 <http://cscircles.cemc.uwaterloo.ca/java_visualize/#code=public+class+ClassNameHere+%7B%0A+++%0A+++public+static+void+mystery+(int+x)%0A+++%7B%0A+++++++++System.out.print(x+%25+10)%3B%0A%0A+++++++++if+((x+/+10)+!%3D+0)%0A+++++++++%7B%0A++++++++++++mystery(x+/+10)%3B%0A+++++++++%7D%0A+++++++++System.out.print(x+%25+10)%3B%0A+++%7D%0A+++%0A+++public+static+void+main(String%5B%5D+args)+%7B%0A++++++mystery(1234)%3B%0A++++++%0A+++%7D%0A%7D&mode=display&curInstr=0>`_.

.. mchoice:: qrm_2
   :practice: T
   :answer_a: 243
   :answer_b: 0
   :answer_c: 3
   :answer_d: 81
   :answer_e: 27
   :correct: a
   :feedback_a: For the call <code>mystery(5)</code>, <code>n != 0</code> so the <code>else</code> statement is executed. This results in the next recursive call of <code>mystery(4)</code>. This will continue until the call <code>mystery(0)</code> is executed. At this point, the value 1 will be returned. Then each call of <code>mystery</code> can return with the 3 * the result of the recursive call. So this method will compute 3 to the given power.
   :feedback_b: This can never be 0 because the stopping condition returns 1 when you call <code>mystery(0)</code>
   :feedback_c: This would only be true if you called <code>mystery(1)</code>
   :feedback_d: This would be true if you called <code>mystery(4)</code>
   :feedback_e: This would be true if you called <code>mystery(3)</code>

   Given the following method declaration, what value is returned as the result of the call ``mystery(5)``?

   .. code-block:: java
      :linenos:

      public static int mystery(int n)
      {
         if (n == 0)
            return 1;
         else
            return 3 * mystery (n - 1);
      }

You can step through the code using the Java Visualizer by clicking on the following link: `Q-11-7-2 <http://cscircles.cemc.uwaterloo.ca/java_visualize/#code=public+class+ClassNameHere+%7B%0A+++%0A+++public+static+int+mystery(int+n)%0A+++%7B%0A+++++++++if+(n+%3D%3D+0)%0A++++++++++++return+1%3B%0A+++++++++else%0A++++++++++++return+3+*+mystery+(n+-+1)%3B%0A+++%7D%0A+++%0A+++public+static+void+main(String%5B%5D+args)+%7B%0A++++++System.out.println(mystery(5))%3B%0A++++++%0A+++%7D%0A%7D&mode=display&curInstr=0>`_.

.. mchoice:: qrm_3
   :practice: T
   :answer_a: 1
   :answer_b: 10
   :answer_c: 25
   :answer_d: 3125
   :answer_e: 15
   :correct: e
   :feedback_a: The value 1 will only be returned when the initial call to product is less than or equal to 1.
   :feedback_b: If you assume the purpose of the method is to compute <code>n * 2</code>, this is correct, but the product method does not do this. Be sure to trace the code to see what happens.
   :feedback_c: If you assume the purpose of the method is to compute <code>n * n</code> this is correct, but the product method does not do this. Be sure to trace the code to see what happens.
   :feedback_d: If you assume the purpose of the method is to compute <code>n ^ n</code>, this would be correct. But product does not do this. Be sure to trace the code to see what happens.
   :feedback_e: The result from <code>product(5)</code> is <code>5 * product(3)</code> which is 3 * product(1) which is <code>1</code> so the answer is <code>1 * 3 * 5 = 15</code>.

   Given the following method declaration, what value is returned as the result of the call ``product(5)``?

   .. code-block:: java
      :linenos:

      public static int product(int n)
      {
         if (n <= 1)
            return 1;
         else
            return n * product(n - 2);
      }

You can step through the code using the Java Visualizer by clicking on the following link: `Q11-7-3 <http://cscircles.cemc.uwaterloo.ca/java_visualize/#code=public+class+ClassNameHere+%7B%0A+++%0A+++public+static+int+product(int+n)+%0A+++%7B%0A+++++++++if+(n+%3C%3D+1)%0A++++++++++++return+1%3B%0A+++++++++else%0A++++++++++++return+n+*+product(n+-+2)%3B%0A+++%7D%0A+++%0A+++public+static+void+main(String%5B%5D+args)+%7B%0A++++++System.out.println(product(5))%3B%0A++++++%0A+++%7D%0A%7D&mode=display&curInstr=0>`_.

.. mchoice:: qrm_4
   :practice: T
   :answer_a: 8
   :answer_b: 3
   :answer_c: There is no result because of infinite recursion.
   :answer_d: 5
   :answer_e: 0
   :correct: d
   :feedback_a: This would be true if it was <code>f(6)</code> not <code>f(5)</code>.
   :feedback_b: This would be true if it was <code>f(4)</code> not <code>f(5)</code>.
   :feedback_c: This method will stop when <code>n</code> equals <code>0</code> or <code>1</code>.
   :feedback_d: This is the Fibonacci method which returns <code>0</code> for <code>0</code> and <code>1</code> for <code>1</code> and <code>Fibonacci(n-1) + Fibonacci(n-2)</code> for the rest of the numbers.
   :feedback_e: This would be true if it was <code>f(0)</code> not <code>f(5)</code>.

   Given the following method declaration, what value is returned as the result of the call ``f(5)``?

   .. code-block:: java
      :linenos:

      public static int f(int n)
      {
         if (n == 0)
            return 0;
         else if (n == 1)
            return 1;
         else return f(n-1) + f(n-2);
      }

You can step through the code using the Java Visualizer by clicking on the following link: `Q11-7-4 <http://cscircles.cemc.uwaterloo.ca/java_visualize/#code=public+class+ClassNameHere+%7B%0A+++%0A+++public+static+int+f(int+n)%0A+++%7B%0A+++++++++if+(n+%3D%3D+0)%0A++++++++++++return+0%3B%0A+++++++++else+if+(n+%3D%3D+1)%0A++++++++++++return+1%3B%0A+++++++++else+return+f(n-1)+%2B+f(n-2)%3B%0A+++%7D%0A+++%0A+++public+static+void+main(String%5B%5D+args)+%7B%0A++++++System.out.println(f(5))%3B%0A++++++%0A+++%7D%0A%7D&mode=display&curInstr=0>`_.

Hard Multiple Choice Questions
----------------------------------


.. mchoice:: qrh_1
   :practice: T
   :answer_a: The string <code>s</code> contains two or more of the same characters.
   :answer_b: The string <code>s</code> starts with two or more of the same characters.
   :answer_c: The string <code>s</code> contains two or more of the same character that are next to each other.
   :answer_d: The string <code>s</code> ends with two or more of the same characters
   :correct: c
   :feedback_a: It is not enough for <code>s</code> to contain two of the same characters, they must be adjacent to satisfy <code>s.charAt(0) == s.charAt(1)</code>.
   :feedback_b: It is not neccessary for the adjacent characters to be at the start of the string.
   :feedback_c: This method will return true when <code>s</code> has at least 2 characters in it and at least 2 characters are the same and are adjacent.
   :feedback_d: It is not neccessary for the adjacent characters to be at the end of the string.

   Given the following method declaration, this method will return true if and only if:

   .. code-block:: java

      public static boolean check(String s)
      {
         return s.length() >= 2 &&
                (s.charAt(0) == s.charAt(1) ||
                 check(s.substring(1)));
      }

You can step through the code above by clicking on the following link `Ex-11-8-1 <http://cscircles.cemc.uwaterloo.ca/java_visualize/#code=public+class+ClassNameHere+%7B%0A+++%0A+++public+static+boolean+check(String+s)%0A+++%7B%0A++++++return+s.length()+%3E%3D+2+%26%26%0A++++++++++(s.charAt(0)+%3D%3D+s.charAt(1)+%7C%7C%0A+++++++++++check(s.substring(1)))%3B%0A+++%7D%0A+++%0A+++public+static+void+main(String%5B%5D+args)+%7B%0A++++++System.out.println(check(%22xyyz%22))%3B%0A++++++System.out.println(check(%22xyxyz%22))%3B%0A++++++System.out.println(check(%22zyxzyy%22))%3B%0A++++++%0A+++%7D%0A%7D&mode=display&curInstr=0>`_.

.. mchoice:: qrh_2
   :practice: T
   :answer_a: 5
   :answer_b: 4
   :answer_c: 6
   :answer_d: 7
   :answer_e: The method never returns due to infinite recursion.
   :correct: a
   :feedback_a: The first time the method is called, <code>i</code> is not equal to 0, so the method makes a recursive call to itself, with the value of 82/3 which equals 27 due to integer division.  This is still not equal to 0, so the method calls itself with the first parameter equal to 9, then 3, then 1. Finally, the method is called with the first parameter of 1/3 which equals 0 due to integer division which throws away any decimal part. Each method call adds 1 to the result, except for the final call when <code>i</code> is equal to 0.
   :feedback_b: Each time the method is called when <code>i</code> is not equal to 0, the return value is incremented. This happens 5 times, with <code>i</code> equal to 81, 27, 9, 3, and 1.
   :feedback_c: The return value is not incremented the last time the method is called, when <code>i</code> is equal to 0.
   :feedback_d: The method only executes 6 times, with the return value incremented each time <code>i</code> is not equal to zero
   :feedback_e: Infinite recursion would happen if the method never reached its base case where <code>i</code> is equal to 0. This would be true if the division could result in a constantly shrinking fraction, but integer division truncates the fractional portion of the division.

   Given the following method declaration, what will ``redo(82, 3)`` return?

   .. code-block:: java

      public static int redo(int i, int j)
      {
         if (i==0)
            return 0;
         else
            return redo(i/j, j)+1;
      }

You can step through the code above by clicking on the following link `Ex-11-8-2 <http://cscircles.cemc.uwaterloo.ca/java_visualize/#code=public+class+ClassNameHere+%7B%0A+++%0A+++public+static+int+redo(int+i,+int+j)%0A+++%7B%0A++++++if+(i%3D%3D0)%0A+++++++++return+0%3B%0A++++++else+%0A+++++++++return+redo(i/j,+j)%2B1%3B%0A+++%7D%0A+++%0A+++public+static+void+main(String%5B%5D+args)+%7B%0A++++++System.out.println(redo(82,3))%3B%0A+++%7D%0A%7D&mode=display&curInstr=0>`_.
