=====================
Studio PR: Peer Review
=====================

**Studio activities should not be started before class! Come to the session and work on the activity with other students!**

Studio Setup and Procedure
==========================

You know the drill by now! 2–3 students per group. Here's `the Github link <https://classroom.github.com/a/LYiCCXDn>`_.

Peer Review
===========

For this studio we will go through an exercise called Peer Review. Like many disciplines, computing often requires many people to work together to solve large, complex problems. Humans are prone to mistakes and biases, however, so by performing regular peer reviews we gain the perspective of others on our code which may catch problems that were otherwise missed. The act of peer review is very common in industry and professional programmers are regularly expected to have their code reviewed by their peers as well as to review their peers' code submissions.

For this peer review we want you to focus specifically on the style of the code. While there is some flexibility in how you can write your code, keeping your code files clean and consistent will make it easier for others to understand what your code is doing.

1. Once you have formed a group, review the `Google Java Style Guide <https://google.github.io/styleguide/javaguide.html>`_ with your group. You do not have to become familiar with the entire style guide, rather for today you should focus on three areas: **brackets**, **whitespace** (tabs, spacing, new lines, etc.), and **variable names**. Make sure you understand what the style guide says about these areas before proceeding.

2. Start with the file called ``Nim.java``. This is a functional version of the Game of Nim from `Assignment 2 <https://131text.com/ns/books/published/csjava/Module2-Choice-and-Iteration/assignment.html>`_. It is quite messy however! Clean it up, focusing on the following:
    
    * Naming - Variable names should be descriptive. Single letter variable names are bad!
    * Whitespace - Indentation should be proper, and there should not be any excessive blank lines.
    * Brackets - Opening brackets should immediately follow the code they belong to: `if (true) {`. They should not go on the next line! Closing brackets should be on their own line and line up vertically with the block they are closing.

3. VSCode provides tools to help with this process! Do some googling ("how to rename variables in VSCode") or talk to a TA about this.

4. Once you have cleaned up the game of Nim, **get your work cleared by a TA before proceeding**.

5. The next file to examine is ``Dice.java``. This code simulates rolling a number of dice a certain number of times (for example, roll 4 dice 7 times). It creates two tables (also known as **arrays**) to track information about the dice that are rolled. The 2D array tracks each individual value that gets rolled, while the 1D array is intended to keep track of the sums of each throw. The program displays each die that is rolled for a throw, the sum of each throw, and the number of times that each sum itself was rolled. It also counts and reports something called "yahtzees", which is when all of the dice for a given throw have the same value.

6. Repeat the process of cleaning up this code. You will have to use context about the code itself to decide upon appropriate names for the variables. Ask a TA if you need help!

7. Unlike the last example, this example has some bugs in it that prevent it from working properly. **After** cleaning up the code, search out these bugs and fix them. In particular pay attention to the following areas:
    
    * Are the arrays sized appropriately for what they are used for?
    * Is the sum computed properly?
    * Are the proper die values being generated?
    * This example uses nested loops - what does each loop represent? Does it make sense?
    * The process for detecting yahtzees is very broken. How can this be properly determined?

8. **Show your work to a TA**. It must pass TA approval (clean and functional!) before the studio is considered complete!

**To complete this studio:** Be sure to fill out the reflection questions on Canvas!