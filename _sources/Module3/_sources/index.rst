=====================
Module 3
=====================

.. Here is were you specify the content and order of your new book.

.. Each section heading (e.g. "SECTION 1: A Random Section") will be
   a heading in the table of contents. Source files that should be
   generated and included in that section should be placed on individual
   lines, with one line separating the first source filename and the
   :maxdepth: line.

.. Sources can also be included from subfolders of this directory.
   (e.g. "DataStructures/queues.rst").



Exercise : 3.32. Make a copy of an array
:::::::::::::::::::::::::::::::::::::::::::::::::::

There are two parts of this exercise 

* First you will make a copy of an array.

* Then you will change your code so that as you copy, you create the Pig Latin version of each string from the original array.

* Find and open the ``CopyArraysAndPigLatin`` Java program in the ``exercises3`` package.

* Write code to make a copy of the provided ``names`` array. We do this so that we can make changes to the copy without affecting the original array. If we call the copy array ``copy``, then the steps you take are as follows:

  * Allocate the ``copy`` array with enough space to hold each of the elements of ``name``.

   Do not use constants here: pretend that the names array could be of any length.

   * Iterate over the names array to assign each element of copy from names.

* Check your results by iterating over copy and printing each element.

* Now go back and cause each element of the copy array to have the `Pig Latin <http://en.wikipedia.org/wiki/Pig_Latin>`_ version of each string in the original names array.

Exercise : 3.65. Permuting an array
:::::::::::::::::::::::::::::::::::::::::::::::::::

* Find and open the ``Shuffle`` Java program in the ``exercises3`` package.

* It declares an array of strings called ``original`` that contains the strings ``"A"`` through ``"H"``, in alphabetical order.

* The goal of this exercise is to shuffle this array, or a copy of it as you prefer, so at to obtain a randomized order of the strings.

* This is tricky, so try your best but don’t feel bad if you need to see the solution before you have it working completely.

   You can watch just enough of the solution video to get unstuck and then try moving forward on your own.

Exercise : 3.75. Permuting an array
:::::::::::::::::::::::::::::::::::::::::::::::::::

* Find and open the ``TimesTable`` Java program in the ``exercises3`` package.

* Complete the class so it prints a table of products, as shown on the introductory video.

   Your columns should line up nicely, assuming that all products take at most 2 digits. In other words, it should look nice when given an input value of 9. For greater values, your columns need not line up but the data should be correct.


Studio 3: Sieve of Eratosthenes
::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::

**Studio activities should not be started before class! Come to the session and work on the activity with other students!**

* `Studio Setup and Procedure`_

* `Background`_

* `Sieve of Eratosthenes`_

* `Making a program Sieve for You`_

* `Review and Revise`_

* `Peer Comparisons`_

* `Demo`_

.. _Studio Setup and Procedure:

**Studio Setup and Procedure**

* Form a group of 2-3 students and find a TA or instructor to work with.

* All but one member of your group should have this web page open so you can follow along and see the instructions as you work.

* Plan to work on one computer (using Eclipse).

  * Initially, one of you will be in charge of typing at that computer.

  * Throughout the studio you should trade who is in charge of the keyboard.

**READ THE FOLLOWING FULLY BEFORE PROCEEDING**

1. Have **one person** in your group create a new team by `Logo <https://classroom.github.com/g/n3TfYnGC>`_ here and going to the ``OR Create a new team`` box at the bottom of the page. The team name should include the last names of all your group members. For example, if Xia and Smith are working together, the team name should be something like “XiaSmith”.

2. **After the team is created**, all other members of your team should click on the same link and follow the instructions to join the team.

   1. **Be careful to join the right team!** You won’t be able to change teams yourself and will have to contact instructors if there’s a problem.

   2. **Be sure everyone else joins the team!** If grades don’t get entered correctly we will use the team to help verify credit for a particular studio.

3. Finally, one person should import the studio repository into Eclipse, as described in `Assignment 0’s Add the assignment to Eclipse <https://classes.engineering.wustl.edu/2021/fall/cse131//modules/0/assignment#4-add-the-assignment-to-eclipse>`_

   * All team members will have access to the work pushed to GitHub. Be sure to ``Commit and Push`` at the end of the day so everyone can refer back to the work later as needed.

.. _Problem 1:Gambler's Ruin:

**Problem 1:Gambler's Ruin**

.. _Background:

**Background**

It may have been a few years since you worked with these concepts, so some quick review:

* A `composite <https://en.wikipedia.org/wiki/Composite_number>`_ is a positive integer that can be expressed as the product of two other integers. For example, 36 is the product of 6 and 6 so 36 is a composite number.

* A `prime number <https://en.wikipedia.org/wiki/Prime_number>`_ is a whole number that can’t be formed by the product of other whole numbers. 29 is an example. It can only be expressed as the product of 1 and 29.

  * Prime numbers may not be that important to you, but they are a significant concept in many branches of mathematics and critical to many modern technologies, like encryption.

  * Today’s main goal is practice using arrays in an interesting way.


.. _Sieve of Eratosthenes:

**Sieve of Eratosthenes**

In this studio you will make a program that performs the `sieve of Eratosthenes <https://en.wikipedia.org/wiki/Sieve_of_Eratosthenes>`__.

* Much like a `sieve <https://en.wikipedia.org/wiki/Sieve>`__ that’s used to separate or sift out unwanted materials, the sieve of Eratosthenes starts with all the positive integers and then separates the composite numbers out, leaving only the prime numbers.

* You should understand the process being done before trying to represent it with a computer program. Start by:

1. Review the description of the `sieve of Eratosthenes <https://en.wikipedia.org/wiki/Sieve_of_Eratosthenes>`__.

2. Work through the `process <https://en.wikipedia.org/wiki/Sieve_of_Eratosthenes#Overview>`_ of the sieve to find all the primes up to 40. **Work through it on paper. It’s really important that you have a reasonable understanding of tasks before you try to make a computer do them. Do not skip this step!**

3. When done, review your work. Confirm that all the values you found are primes and that all the composites have been removed.

4. Reflect on the process — discuss each step and how it relates to concepts you’ve seen in class. *Check your work with both a TA and other groups*.

.. _Making a program Sieve for You:

**Making a program Sieve for You**

1. Add a new ``Sieve`` class to the ``studio-03/src`` folder.

2. Prompt the user for the ``n``. You’ll need to find all prime numbers up to ``n``.

   * **You can decide if you want to include n itself or not, but decide now!**

3. Create code that will represent the items being sieved (i.e., an array). There are many valid approaches. Some things to consider:

   * What will be in the array? How do the stored values relate to the sieve process?

   * How big should the array be?

   * How will indices be used? How do they relate to the sieve process?

   * How can you incrementally test your work to ensure that what you’re doing is correct/working? (Hint, printing details as your code executes is really helpful)

4. Develop and refine your code until it works.

   * Think carefully about whether you are including the ``n``-th value or not. Test that your program works as expected. If it doesn’t, figure out why.

5. Have your program print all the prime values it finds and nothing else.

6. Once you can successfully print primes, try it with large values of ``n``, like 10,000,000. If you’ve implemented everything correctly it should only take a few seconds to final all the primes less than 10,000,000! (One takeaway from today’s studio: You can use a little code to quickly automate tasks! This is much quicker and more accurate than attempting to do this by hand!)




.. _Review and Revise:

**Review and Revise**

`Pseudocode <https://en.wikipedia.org/wiki/Pseudocode>`__ is a way to describe things with a precise format that is similar to computer programs. Review the `Pseudo Code for the sieve of Eratosthenes <https://en.wikipedia.org/wiki/Sieve_of_Eratosthenes#Pseudocode>`__ and compare it to your version. Not everything done in the pseudocode is straightforward in Java. None the less, if your approach is substantially different, revise it to include some of the approaches described in the pseudocode that seem sensible. Compare/contrast the approaches with your TA.



.. _Peer Comparisons:

**Peer Comparisons**

Compare your work to that of other groups. Are there things that make one approach easier/harder to understand?

.. _Demo:

**Commit and Push** your work. Be sure that any file you worked on is updated on `GitHub <https://github.com/>`_.

To get participation credit for your work talk to the TA you’ve been working with and complete the demo/review process. Be prepared to show them the work that you have done and answer their questions about it!

*Before leaving check that everyone in your group has a grade recorded in Canvas!*


Assignment 3: Array Puzzles 
::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::

* `Arrays Bonus Video`_

* `Assignment Setup`_

* `Array Puzzles`_

  * `Bubble Sort`_

  * `Frequency Table`_

  * `Symmetrical Image`_

* `Submitting your work`_


.. _Arrays Bonus Video:

**Arrays Bonus Vieo**

.. youtube:: jKZ0rF1KHM4

Still a confused about arrays? Watch this bonus demonstration by former 131 TA Amanda Hua on how to create, write to, read from, and get the length of arrays.



.. _Assignment Setup:

**Assignment Setup**

To create your repository go `here <https://classroom.github.com/a/BjAINj1I>`_. Then follow the same accept/import process described in `Assignment 0 <https://classes.engineering.wustl.edu/2021/fall/cse131//modules/0/assignment>`__.

.. _Array Puzzels:

**Array Puzzles**

You are given three problems to complete below. For each problem we supply you examples of what the output could look like.

.. _Bubble Sort:

**Bubble Sort**

`Bubble Sort <https://en.wikipedia.org/wiki/Bubble_sort>`__ is a simple, well known, algorithm that can be used to sort an array. Implementing a simple sorting algorithm such as bubble sort is often seen as a rite of passage for the novice computer scientist.

The way that bubble sort works is by “bubbling” the larger values up. If a value is larger than its neighbor it will be swapped until all of the larger values make their way to the end of the array and the smaller values end up at the beginning of the array.

Your task is to create a program called ``BubbleSort.java`` in the ``assignment3`` package. This program should first use ``ArgsProcessor`` to ask the user how big they would like the array to be. It will then prompt the user to enter that many integer values, which get stored into the array.

You should then sort this array in ascending order using the bubble sort algorithm. To assist you, take a look at this `pseudocode <https://en.wikipedia.org/wiki/Pseudocode>`_ implementation of the sorting algorithm:


.. image:: pseudocode.png
  :alt: Example pseudocode


Notice that the above code does not look like Java code that we have seen before. If you were to put this into Eclipse, it would not work. This “pseudocode” captures the essence of the task at hand, which a programmer (in this case, you!) can translate into a more specific computer language like Java or python (or even a human language like Spanish or Chinese….what’s the difference between human language and computer language, anyway?).

For a visualization of how this algorithm works, take a look at `this <https://clementmihailescu.github.io/Sorting-Visualizer/>`_.

You should print out the original array as well as the sorted array so that the results can be easily verified.

Note that the rubric requests that you step through bubble sort in the debugger as part of the demo process. You are highly encouraged to practice this before you demo!


Example Output:

``Given values:  8 6 7 5 3 0 9``

``Sorted values: 0 3 5 6 7 8 9``

.. _Frequency Table:

**Frequency Table**

Make a program called ``FrequencyTable.java`` in the ``assignment3`` package. This program will generate ``x`` integers between 1 and ``n`` where ``x`` and ``n`` are values supplied by the user through ``ArgsProcessor``.

Your program should create a frequency table, counting the number of times that each number is randomly generated. Think carefully about how you can use an array for this purpose. How big should our array be? Can we define a relationship between the random values that are generated and how we count them in the array?

Example Output:

``Frequencies for 100 randomly generated values between 1 and 10``

``1: 10``

``2: 9``

``3: 10``

``4: 9``

``5: 10``

``6: 6``

``7: 15``

``8: 15``

``9: 8``

``10: 8``

.. _Symmetrical Image:

**Symmetrical Image**

Create a program ``SymmetricalImage.java``. This program should create an ``n`` x ``m`` array where ``n`` and ``m`` are values supplied by the user through ``ArgsProcessor``.

We wish to use this array to create some randomly generated vertically symmetrical images. To do this, first select a random point within the 2D array. You will then need to compute the “mirrored” point on the other side of the array. Both of these array positions should be marked.

For example, if the size of the array is 10x10 and the point that I have randomly selected is at position (2, 3), then the corresponding “mirrored” point would be at position (2, 6) and both of these positions would be marked in the array. Note that if (2, 6) was the randomly generated point that (2, 3) is still its mirrored point - your code should work in both situations. If you’re having trouble understanding how this works then sketch out a simple example on paper and make sure you understand it before moving on!

You should generate ``n * m / 4`` random points. It is OK if you randomly select the same point more than once, this will just add to the random flavor of the resulting images.

Finally, you should print out the image by going through the entire array and printing a ``*`` if the value in the given position is marked and a blank space otherwise.



Example output:

``A randomly generated, symmetrical 10 x 10 image:``

.. image:: Example.png
  :alt: Example pseudocode

.. _Submitting your work:

**Submitting your work**

To submit your work come to office hours or class on an “Assignment day” and sign up for a demo via wustl-cse.help.