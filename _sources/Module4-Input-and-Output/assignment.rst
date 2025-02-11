=====================================
Assignment 4: Cookie Clicker
=====================================

Authors
=======

Dorian Marr, '26 Vicky Prisco, '25

Assignment Setup
=====================

To create your repository go `here <https://classroom.github.com/a/6x_eCcGi>`_. Then follow the same accept/import process described in `the setup instructions <../Module0-Introduction/software.html>`_.

Background
=====================

Idle games are games that can be played both actively and inactively: when playing actively, you can progress quickly usually by clicking on an object rack up some kind of currency. When not playing, the game continues to gain currency idly in the background at a different rate than if you were actively clicking.

Cookie clicker is a game where you... click on a picture of a cookie! When clicking, you get some currency (in this game the currency is called cookies) for each click. Once you reach a certain amount of clicks, you can buy bots that will click for you when you aren't playing, or powerups that make each one of your clicks more valuable. You can try the game out `here <https://cookieclicker.ee>`_ if you haven't played before, but beware of forgetting that you have this assignment to complete...

Prompt Engineering in This Assignment
=====================================

As we saw in lecture, generative AI tools, like chatGPT, can generate code quickly. The code it generates might not be what we were looking for or fit for our needs -- this is where prompt engineering comes in. How we interact with these tools can change the results we get; knowing what to ask is an important skill in getting help!

Recommended Workflow
====================

For each step in the procedure below, we will ask you to complete one step towards a functioning game. Some of these steps have complex math (like finding where the user clicked) or other tricky elements. Use your AI tool of choice to work through these - a great perk of using these tools is to make them teach you about things you don't know yet. Don't use AI to do everything at once, you'll have much better results if you complete the assignment one item at a time. If you get some code you don't fully understand or haven't seen before, ask how it works! If the explanation you get doesn't quite click for you, feel free to get help from TAs or instructors (post on Piazza or stop by office hours)! Remember that at demo time you will be expected to explain how your code works - even if it is code that you did not write yourself.

Steps to a Complete Cookie Clicker
=====================================
	
1. Draw the cookie and some text that says "Cookie Clicker!"

   * Run your program and verify that your cookie looks correct.
2. Draw 5 chocolate chips, randomly placed on the cookie.
   * These chips should be randomly placed at the beginning of the game and stay in the same place for the duration of the game
3. Detect when the user clicks on the cookie. (Hint: Use `StdDraw <https://introcs.cs.princeton.edu/java/stdlib/javadoc/StdDraw.html>`_ mouse methods such as: ``isMousePressed()`` and ``mouseX()`` and ``mouseY()``)

   * To check your work, try printing something to the console (i.e., use ``System.out.println``) when the screen is clicked.
4. Display a cookie counter on the screen and add one to it every time the cookie is clicked
5. Implement idle point earning: every second, the user should earn 1 cookie without having to click 

   * Use the timing methods provided in the ``TimingPractice`` examples to get the current time in milliseconds.
6. Starting at a cost of 20 cookies, a power up will begin that increases the amount of cookies they get with each click. This power up should be able to be bought multiple times, increasing the click power each time, and increasing in cost after each purchase.
7. Starting at a cost of 60 cookies, a power up will begin that earns one more idle cookie per second. This power up should be able to be bought multiple times, increasing the idle cookies earned each time, and increasing in cost after each purchase.

Requirements
============

Your cookie clicker should:

* Increment total amount of cookies clicked with each click
* Increment total amount of cookies clicked idly every second
* Implement the click power up as explained above.
* Implement the idle power up as explained above.
* Power ups should be begin automatically once enough cookies have been earned. No buttons should be used for the powerups.
* After each powerup begins, the amount of cookies to start the powerup should increase by some factor (up to you!)
* The game should continue endlessly
* For each step, record the prompts you used to interact with the generative AI you chose in a comment in your code. We will ask you how you worked with your chosen tool to develop your code!

Tips for if you get stuck
=========================

* Try printing (or drawing) some of your variables. This shows you their values and how they're changing, which may help you figure out what's going on.
* If you get an error message you can't understand, try asking your generative AI tool what it means. You can then use this to help figure out why the error is occurring and how to solve it.
* Pay attention to the scope of your variables!


Submitting your work
=====================


Get your assignment graded by bringing it to lab on Wednesday or going to office hours and signing up for a demo via `wustl-cse.help <https://wustl-cse.help/>`_.

Confirm that your score is recorded in `Canvas <https://wustl.instructure.com/courses/143742>`_.  Mistakes can happen and you should always confirm credit is recorded before leaving class!