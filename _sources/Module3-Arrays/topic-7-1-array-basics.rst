.. qnum::
   :prefix: 7-1-
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
    

Array Creation and Access
--------------------------

..	index::
	single: array
	single: index
	pair: array; index

To keep track of 10 exam scores, we could declare 10 separate variables:  int score1, score2, score3, … , score10; 
But what if we had 100 exam scores? That would be a lot of variables! Most programming languages have a simple **data structure** for a collection of related data that makes this easier. In App Inventor, this is called a list. In Java and many programming languages, this is called an **array**.

An **array** is a block of memory that stores a collection of data items (**elements**) of the same type under one name. Arrays are useful whenever you have many elements of data of the same type that you want to keep track of, but you don't need to name each one. Instead you use the array name and a number (called an **index**) for the position of an item in the array. You can make arrays of ints, doubles, Strings, and even classes that you have written like Students. 

.. |video| raw:: html

   <a href="https://youtu.be/G7aF-OuLfl4" target="_blank">video</a>
   
Here's a fun |video| that introduces the concept of an array and gives an example.

.. youtube:: G7aF-OuLfl4
    :width: 640
    :align: center

An array is like a row of small lockers, except that you can't cram lots of stuff into it. You can only store one value at each locker.  


.. figure:: Figures/rowLockers.jpg
    :width: 400px
    :align: center
    :figclass: align-center

    Figure 1: A row of lockers

You can store a value in an array using an **index** (location in the array). An array index is like a locker number.  It helps you find a particular place to store your stuff and retrieve stuff.    You can get or store a value from or to an array using an index. 

Arrays and lists in most programming languages start counting elements from the number 0, 
so the first element in an array is at index 0. 
This is similar to how Strings are indexed in Java -- the first character is at index 0.  


Declaring and Creating an Array
===============================

When we declare a variable, we specify its type and then the variable name.  To make a variable into an array, we put square brackets after the data type. This data type will be for all the elements in the array.

.. code-block:: java 
   
   // Declaration for a single int variable 
   int score;
   // Declaration for an array of ints
   int[] scores;

The declarations do not create the array.  Arrays are **objects** in Java, so any variable that declares an array holds a reference to an object.  If the array hasn't been created yet and you try to print the value of the variable, it will print **null** (meaning it doesn't reference any object yet).  



To actually create an array after declaring the variable, use the **new** keyword with the type and the size of the array (the number of elements it can hold). This will actually create the array in memory.  You can do the declaration and the creation all in one step, see the String array names below. The size of an array is set at the time of creation and cannot be changed after that.

.. code-block:: java 
   
  //declare an array variable
  int[] highScores;
  // create the array
  highScores = new int[5];
  // declare and create array in 1 step!
  String[] names = new String[5];
  


|Exercise| **Check Your Understanding**

.. mchoice:: q7_1_1
   :practice: T
   :answer_a: int[] prices = new int[10];
   :answer_b: double[] prices = new double[10];
   :answer_c: double[] prices;
   :answer_d: double[10] prices = new double[];
   :correct: b
   :feedback_a: We need double for money amounts in prices.
   :feedback_b: Yes correct!
   :feedback_c: This declares the array but does not create it with new.
   :feedback_d: This is not the correct syntax.
   
   Which of the following creates an array of 10 doubles called prices?

|CodingEx| **Coding Exercise**

   
   In the ``E01EmptyArrayDeclaration`` program, add another array declaration that creates an array of 5 doubles called prices and another array of 5 Strings called names. Update the corresponding System.out.println commands.
   

..	index::
	pair: array; initialization
    
.. note::
  
   Array elements are initialized to default values like the following. 
   
   - 0 for elements of type ``int`` 
   - 0.0 for elements of type ``double`` 
   - false for elements of type ``boolean``
   - null for elements of type ``String`` 

.. figure:: Figures/arrayIndicies.png
    :width: 200px
    :align: center
    :figclass: align-center

    Figure 3: Two 5 element arrays with their values set to the default values for integer and object arrays.

Initializer Lists
============================

Another way to create an array is to use an **initializer list**. You can initialize (set) the values in the array to a list of values in curly brackets { } when you create it, like below.  In this case you don't specify the size of the array, it will be determined from the number of values that you specify.  

.. code-block:: java 

  int[ ] highScores = {99,98,98,88,68};
  String[ ] names = {"Jamal", "Emily", "Destiny", "Mateo", "Sofia"};
  
  

  
When you create an array of a **primitive type** (like ``int``) with initial values specified, space is allocated for the specified number of items of that type and the values in the array are set to the specified values.  When you create an array of an **object type** (like ``String``) with initial values, space is set aside for that number of object references.  The objects are created and the object references set so that the objects can be found. 

.. figure:: Figures/intAndStringArrays.png
    :width: 500
    :align: center
    :figclass: align-center

    Figure 4: A primitive array and an object array

..	index::
    single: dot-notation
	pair: array; length



Arrays know their length (how many elements they can store).  It is a public read-only instance variable so you can use **dot-notation** to access the instance variable (``arrayName.length``).  **Dot-notation** is using variable name followed by a ``.`` and then the instance variable (property) name or a method name. Try the following.

|CodingEx| **Coding Exercise**


   
   Try running the ``E02InitializerList`` program to see the length. Try adding another value to the highScores initializer list and run again to see the length value change.
   


.. note::

   Note that length is an instance variable and not a method, unlike the String ``length()`` method, so you don't add parentheses after length. The length instance variable is declared as a ``public final int``.  ``public`` means you can access it and ``final`` means the value can't change.
   


|Exercise| **Check your understanding**
   
.. mchoice:: q7_1_2
   :practice: T
   :answer_a: <code>highScores.length</code>
   :answer_b: <code>highScores.length - 1</code>
   :correct: b
   :feedback_a: Remember that the first element in an array starts at index 0. If the length (the number of elements) of the array is 5, at what index would you find the last element?  
   :feedback_b: Since the first element in an array is at index 0 the last element is the length minus 1.

   Which index is for the last element of an array called ``highScores``?
 

Access and Modify Array Values 
=====================================

To access the items in an array, we use an **indexed array variable** which is the array name and the 
index inside of square bracket [ ]. Remember that an **index** is a number that indicates 
the position of an item in a list, starting at 0. 

An indexed variable like **arrayname[index]** can be used anywhere a regular variable can be used, for example to assign a new value or to get a value from the array like below.


.. code-block:: java 
 
  // assign a new value 99 to the first element in the array
  highScores[0] = 99;
  // print the first element of the array
  System.out.println( highScores[0] );
  
.. note::

    The first value in an array is stored at index 0 and the index of the last value is the length of the array minus one (since the first index is 0). Use arrayname[index] to access or modify array items.
    



|Exercise| **Check your understanding**

.. mchoice:: q7_1_3
   :practice: T
   :answer_a: 0
   :answer_b: 1
   :correct: a
   :feedback_a: The index is really telling the computer how far the item is from the front of the array.  So the first element in an array is at index 0. 
   :feedback_b: While this matches with how we number some things, the first item in an array is at index 0.

   At what index do you find the first element of an array?
 

.. fillintheblank:: q7_1_4
    
    Fill in the blank with code to access the cars array.

    
   String[] cars = {"Honda", "Volvo", "BMW"};
   
   // Access cars array to get Volvo
   
   String v = |blank|;

   -   :cars\[1\]: Correct.
       :x: Use the array name cars with [ ] with a number in it. Don't use spaces in your answer! Remember that the first element in an array starts at index 0. 
       
.. fillintheblank:: q7_1_5

    Fill in the blank with code to access the cars array.  NOTE: The semicolon is provided for you after the box.
    
   String[] cars = {"Honda", "Volvo", "BMW"};
   
   // Set the first item of the cars array to be Toyota
   
   |blank|  = "Toyota";  

   -   :cars\[0\]: Correct.
       :x: Use the array name cars with [ ] with a number in it. Remember which index is for the first item in the array. Don't use spaces in your answer!

  
.. clickablearea:: q7_1_6
        :question: Click on the value at index 2 in the following array.
        :feedback: Remember that the first value is at index 0.  Click on an area again to unselect it and try again.
        :table:
        :correct: 1,3;
        :incorrect: 1,1;1,2;1,4;
        
        +----+----+----+----+
        | 4  | -2 |  8 | 7  |
        +----+----+----+----+


..  **Coding Exercise**

Try out the ``E03ArrayAccess`` program which has an int array of highScores and names. Can you print out 3rd score in the array (remember that the first score is at index 0)? Can you change last score to 97 using an assignment statement in the code? Can you change the array so that it has 6 elements and add another score and print it out? What happens if you try to access an element that is not there, for example at index 7?


If you want to keep track of the top 5 highest scores in a game and the names of the people with those scores, you could use two **parallel arrays**.  One array could keep track of the scores and the other the names. You have to make sure you keep them in the same order so that the same index can be used to get correponding names and scores. 

|CodingEx| **Coding Exercise**
   
Try out the ``E04ParallelArrays`` program which has two parallel arrays, highScores and names. Can you print out Mateo's score? Can you change Sofia's score to 97 using an assignment statement in the code? Can you change the arrays so that they have 6 elements and add your name and score and print them out? 
   
.. note::

    Using an index value outside of 0 - (length-1) will result in an ArrayIndexOutOfBoundsException being thrown.  
 

One powerful feature in the array **data abstraction** is that we can use variables for the index! As long as the variable holds an integer, we can use it as an index. 

.. code-block:: java 
 
  // use a variable for the index
  int index = 3;
  System.out.println(  highScores[index] );

    
Summary
=========

- Arrays represent collections of related data all of the same data type. 

- The size of an array is established at the time of creation and cannot be changed.

- Arrays can store either primitive data or object reference data.

- When an array is created using the keyword new, all of its elements are initialized with a specific value based on the type of elements:

  - Elements of type int are initialized to 0
  - Elements of type double are initialized to 0.0
  - Elements of type boolean are initialized to false
  - Elements of a reference type are initialized to the reference value null. No objects are automatically created.
  
- Initializer lists can be used to create and initialize arrays.

- Square brackets ([ ]) are used to access and modify an element in an array using an index. The indexed array variable, for example array[index], can be used anywhere a regular variable can be used, for example to get or assign values.

- The valid index values for an array are 0 through one less than the number of elements in the array, inclusive. Using an index value outside of this range will result in an ArrayIndexOutOfBoundsException being thrown.
