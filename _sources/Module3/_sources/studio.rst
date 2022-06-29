=====================
Module 3 Studio
=====================


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

*Before leaving check that everyone in your group has a grade recorded in Canvas