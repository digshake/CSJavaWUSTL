=====================
Module 5 Exercises
=====================



Exercise : 5.25. Cooking abstractions 
:::::::::::::::::::::::::::::::::::::::::::::::::::

* Find and open the ``Recipe Java`` program in the ``exercises5`` package.

* For the work below, enter your work into that file.

In the introductory video for this exercise, you heard the following recipe excerpt:

* Heat 200 cc water to 100 degrees

* Stir in 5 grams of yeast

* Melt butter and stur in the vanilla with the butter

* After 5 minutes, combine yeast with butter, sugar, and flour

* Place the mixture in a 110 degree oven to rise for 45 minutes

* Divide the mixture into 10 equally sized portions and cook for 45 minutes at 350 degrees


Define abstractions present in the above recipe. Rephrase the recipe in terms of your abstractions.


Exercise : 5.45. Exercises
:::::::::::::::::::::::::::::::::::::::::::::::::::

* Find and open the ``StringMethods`` Java program in the ``exercises5`` package.

* Write the methods described below into the program.

* Call those methods from the ``main`` method and print out the results to check that your work is correct.

* The first method is completed for you already.

The methods you should write:

* A method that takes in a ``String`` and returns that string concatenated with itself. This one is completed for you.

* A method that takes in a ``String`` and an ``int`` *n*, and returns *n* copies of the string concatenated together

* Now go back and rewrite your first method by having it call the second one.

* Take a look at Java’s `split <https://docs.oracle.com/en/java/javase/13/docs/api/java.base/java/lang/String.html#split(java.lang.String)>`__ method, that splits a ``String`` into an array containing the parts split by the specified regular expression.

   Here, assume the regular expression is simply " ", so that the input ``String`` is split into words.

* Write a method ``join(String[] array, String joiner)`` that is the inverse of split: it returns a single ``String`` with a copy of the ``joiner`` string between each part.

* Rewrite your second method in terms of this last one. To do this, create an array that has *n* copies of a given ``String``, and then use your ``join`` method to concatenate them.

   Think about the string you want to appear between the copies, so that it appears the strings were concatenated together as before.

