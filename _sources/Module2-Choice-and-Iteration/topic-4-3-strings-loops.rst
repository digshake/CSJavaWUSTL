.. qnum::
   :prefix: 4-3-
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


.. |AP CS A Reference Sheet| raw:: html

   <a href="https://apcentral.collegeboard.org/pdf/ap-computer-science-a-java-quick-reference-0.pdf?course=ap-computer-science-a" target="_blank">AP CS A Java Quick Reference Sheet</a>

Loops and Strings
=================

..	index::
	single: string processing
	pair: string; loop
	
Loops are often used for **String Traversals** or **String Processing** where the code steps through a string character by character. In previous lessons, we learned to use String objects and built-in string methods to process strings. In this lesson, we will write our own loops to process strings. 

Remember that strings are a sequence of characters where each character is at a position or **index** starting at 0. 

.. figure:: Figures/stringIndicies.png
    :width: 500px
    :align: center
    :alt: a string with the position (index) shown above each character
    :figclass: align-center

    Figure 1: A string with the position (index) shown above each character

.. note::

   The first character in a Java String is at index 0 and the last characters is at **length()** - 1. So loops processing Strings should start at 0!

The String methods (previously covered in unit 2.7) that are most often used to process strings are:

- **int length()** : returns the number of characters in a String object. 
  
- **int indexOf(String str)** : returns the index of the first occurrence of str; returns -1 if not found.

- **String substring(int from, int to)** : returns the substring beginning at index from  and ending at index (to – 1). Note that s.substring(i,i+1) returns the character at index i. 

- **String substring(int from)** : returns substring(from, length()).

While Find and Replace Loop
---------------------------

A while loop can be used with the String indexOf method to find certain characters in a string and process them, usually using the substring method.

.. code-block:: java 

   String s = "example";
   int i = 0;
   // while there is an a in s
   while (s.indexOf("a") >= 0)
   {
     // Find and save the next index for an a
     i = s.indexOf("a");
     // Process the string at that index
     String ithLetter = s.substring(i,i+1);
     ...
   }

The example in the mixed up code below finds and removes all the letter a's in a string.

|Exercise| **Check Your Understanding**
  

.. parsonsprob:: q4_3_1
   :numbered: left
   :practice: T
   :adaptive:
   :noindent:

   The following program removes all the a's from a string, but the code is mixed up.  Drag the blocks from the left area into the correct order in the right area.  Click on the "Check Me" button to check your solution.
   -----
   public static void main(String[] args)
   {
   =====
      String s = "are apples tasty without an a?"; 
      int index = 0;
      System.out.println("Original string: " + s);
   =====
      // while there is an a in s
      while (s.indexOf("a") >= 0)
      {
   =====      
         // Find the next index for an a
         index = s.indexOf("a");
   =====         
         // Remove the a at index by concatenating 
         // substring up to index and then rest of the string.
         s = s.substring(0,index) + 
             s.substring(index+1);
   =====         
      } // end loop 
   =====
      System.out.println("String with a's removed:" + s);
   =====
   } // end method
   
   
Google has been scanning old books and then using software to read the scanned text.  But, the software can get things mixed up like using the number 1 for the letter l. Try the code below to clean up scanning mistakes like this.

|CodingEx| **Coding Exercise**

The ``FindAndReplace`` program  loops through a string replacing all 1's with l's.  Trace through the code below with a partner and explain how it works on the given message. Note that indexOf here can work repeatedly to find the next occurrence of a 1 because they are replaced as soon as they are found. 

   
   Change the ``E01FindAndReplace`` program to add code for a counter variable to count the number of 1's replaced in the message and print it out. Change the message to have more mistakes with 1's to test it.
   
For Loops: Reverse String
--------------------------


For-loops can also be used to process strings, especially in situations where you know you will visit every character. 

.. note::

    While loops are often used with strings when you are looking for a certain character or substring in a string and do not know how many times the loop needs to run. For loops are used when you know you want to visit every character.

For loops with strings usually start at 0 and use the string's length() for the ending condition to step through the string character by character. 

.. code-block:: java 

   String s = "example";
   // loop through the string from 0 to length 
   for(int i=0; i < s.length(); i++) 
   {
      String ithLetter = s.substring(i,i+1);           
      // Process the string at that index
      ...
   }

|Exercise| **Check Your Understanding**
  

.. parsonsprob:: q4_3_2
   :numbered: left
   :practice: T
   :adaptive:
   :noindent:

   The following main method has the correct code to count the number of e's in a string, but the code is mixed up.  Drag the blocks from the left area into the correct order in the right area.  Click on the "Check Me" button to check your solution.
   -----
   public static void main(String[] args)
   {
   =====
      String message = "e is the most frequent English letter.";
      int count = 0;
   =====
      for(int i=0; i < message.length(); i++) 
      {
   =====
         if (message.substring(i,i+1).equalsIgnoreCase("e"))
   =====
            count++;
   =====        
      }
   =====     
        System.out.println(count);  
   =====
   }
    
    
The ``E02ReverseString`` program has a for-loop that creates a new string that reverses the string s.  We start with a blank string sReversed and build up our reversed string in that variable by copying in characters from the string s.

 
|CodingEx| **Coding Exercise**
   
   Open the ``E02ReverseString`` program. What would happen if you started the loop at 1 instead? What would happen if you used <= instead of <? What would happen if you changed the order in which you added the ithLetter in line 12?
   

Summary
---------

- Loops can be used to traverse or process a string.

There are standard algorithms that utilize String traversals to:

* Find if one or more substrings has a particular property
* Determine the number of substrings that meet specific criteria
* Create a new string with the characters reversed