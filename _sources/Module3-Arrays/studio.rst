===============================
Studio 3: Sieve of Eratosthenes
===============================

**Studio activities should not be started before class! Come to the session and work on the activity with other students!**

Studio Setup and Procedure
=============================

1. Form a group of 2-3 students. Make sure you know who your TA is.
2. Choose one group member to open VS Code. They will be in charge of typing code for the first part of the studio. You will rotate this responsibility throughout the studio, but the initial person will have to be comfortable with others typing on their computer.
3. Everyone else, open the studio instructions on your own computer.
4. Choose one group member to complete the following instructions:

	1. Open `this link <https://classroom.github.com/a/BAbBkV8w>`_ in a new tab.
	2. Go to the bottom of the page, where it says `OR Create a new team`.
	3. Enter your group's last names and "Studio3" into the text field. Ex: "XiaSmith-Studio3"
	4. Click the button to create the team.
5. After the team is created, all other members of your team should complete the following instructions:

	1. Open `this link <https://classroom.github.com/a/BAbBkV8w>`_ in a new tab.
	2. Find the team your groupmate created.
	3. Join the team. 
	
	* If you join the wrong team, you will need to contact one of the instructors or Head TAs to fix it.
6. VS Code person: import the studio repository as described in `the software setup <setup.html>`_

Sieve of Eratosthenes
=====================

In this studio you will make a program that performs the `sieve of Eratosthenes <https://en.wikipedia.org/wiki/Sieve_of_Eratosthenes>`__.

* Much like a `sieve <https://en.wikipedia.org/wiki/Sieve>`__ that’s used to separate or sift out unwanted materials, the sieve of Eratosthenes starts with all the positive integers and then separates the composite numbers out, leaving only the prime numbers.

* You should understand the process being done before trying to represent it with a computer program. Start by:

1. Review the description of the `sieve of Eratosthenes <https://en.wikipedia.org/wiki/Sieve_of_Eratosthenes>`__.

2. Work through the `process <https://en.wikipedia.org/wiki/Sieve_of_Eratosthenes#Overview>`_ of the sieve to find all the primes up to 40. **Work through it on paper. It’s really important that you have a reasonable understanding of tasks before you try to make a computer do them. Do not skip this step!**

3. When done, review your work. Confirm that all the values you found are primes and that all the composites have been removed.

4. Conceptual checkpoint 1: Talk through your approach with a TA and how each step relates to concepts you've seen in class.

Making a Program Sieve for You
==============================

1. Add a new ``Sieve`` class to the ``studio-03/src`` folder.

2. Prompt the user for the ``n``. You’ll need to find all prime numbers up to ``n``.

   * **You can decide if you want to include n itself or not, but decide now!**

3. Create code that will represent the items being sieved (i.e., an array). There are many valid approaches. Some things to consider:

   * What will be in the array? How do the stored values relate to the sieve process?

   * How big should the array be?

   * How will indices be used? How do they relate to the sieve process?

   * How can you incrementally test your work to ensure that what you’re doing is correct/working? (Hint, printing details as your code executes is really helpful)

4. Conceptual checkpoint 2: What is the structure of a for loop? What values should you use for iterating through all even numbers up to 100? What about multiples of 5 up to 100?

5. Choose a new person to type.

6. Write code that updates the array when you find out a number is not prime. Note: You should not use mod (%) in this studio. If it seems like you need it, go back to the description of the sieve.

7. Develop and refine your code until it works.

   * Think carefully about whether you are including the ``n``-th value or not. Test that your program works as expected. If it doesn’t, figure out why.

8. Have your program print all the prime values it finds and nothing else.

9. Once you can successfully print primes, try it with large values of ``n``, like 10,000,000. If you’ve implemented everything correctly it should only take a few seconds to final all the primes less than 10,000,000! (One takeaway from today’s studio: You can use a little code to quickly automate tasks! This is much quicker and more accurate than attempting to do this by hand!)


Review and Revise
=====================

`Pseudocode <https://en.wikipedia.org/wiki/Pseudocode>`__ is a way to describe things with a precise format that is similar to computer programs. Review the `Pseudo Code for the sieve of Eratosthenes <https://en.wikipedia.org/wiki/Sieve_of_Eratosthenes#Pseudocode>`__ and compare it to your version. Not everything done in the pseudocode is straightforward in Java. None the less, if your approach is substantially different, revise it to include some of the approaches described in the pseudocode that seem sensible. Compare/contrast the approaches with your TA.


Peer Comparisons
=====================

Compare your work to that of other groups. Are there things that make one approach easier/harder to understand?

Demo
=====================

**Commit and Push your work.** Be sure that any file you worked on is updated on `GitHub <https://github.com/>`_. This way the other members of your team will be able to access the code that you worked on.

To get participation credit for your work talk to the TA you’ve been working with and complete the demo/review process. Be prepared to show them the work that you have done and answer their questions about it!
