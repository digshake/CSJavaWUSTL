=====================
Module 3 Exercises
=====================

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
