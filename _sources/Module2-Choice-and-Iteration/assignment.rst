=====================
Assignment 2: Game of Nim
=====================

Assignment Setup
=====================

To create your repository go `here <https://classroom.github.com/a/slDXZGJE>`_. Then follow the same accept/import process described in `the setup instructions <../Module0-Introduction/software.html>`_.

Game of Nim
=====================

`Nim <https://en.wikipedia.org/wiki/Nim>`_ is a `game of strategy <https://en.wikipedia.org/wiki/Strategy_game>`_ in which two players take turns removing sticks from a common pile. There are many variations of Nim but we will stick with a simple version. On each turn a player must remove either 1 or 2 sticks from the pile. The goal of the game is to be the player who removes the last stick.

You will design a game in which one human player is competing against a computer. To simplify your work the person will always take the first turn.

While there is a winning strategy for this game, you are only required to create a computer player that makes random, but valid, moves.

Example
=====================

``Round 0: 7 at start human takes 2, so 5 remain``

``Round 1: 5 at start computer takes 2, so 3 remain``

``Round 2: 3 at start human takes 2, so 1 remain``

``Round 3: 1 at start computer takes 1, so 0 remain``

``The computer wins / you lose!``

Questions to ask if you get stuck
=================================

Like all problems, this one can be tricky. Here are some common questions that we get from students regarding this assignment. Use these questions to gauge your own understanding of what we are asking you to do. Please ask these questions to a TA or an instructor if you are feeling stuck on a certain part of the assignment.

* How can the code know whose turn it is?

* How can numbers be randomly generated within a given range using the `Math` class in Java?

* How can user input be validated to ensure that a proper number is given?

* How do if-statements and while loops with multiple conditions work in Java?

* How do the `&&`, `||`, and `!` operators work in Java?

Notes
=====================

* Begin by prompting the user for the initial number of sticks. In the example above, it appears that 7 sticks were used in the game.

* The human (as always in this assignment) made the first move.

* Clearly, the human could have played better in the above game.

* The computer randomly removes 1 or 2 sticks, but cannot remove more sticks than are left.

* The human is prompted at each turn for how many sticks to remove.

Be careful! A human might enter 5 if 5 sticks are left, and if you are not careful, the human could win by “ `playing <https://en.wikipedia.org/wiki/Cheating>`_ ” in that way. Don’t accept the user’s input if it is illegal. You may assume that they will only enter integers, but you should continue prompting until you get a valid value.

* Start your work by creating a ``Nim`` class in the ``assignment2`` package.

* Use ``Scanner`` to prompt for inputs.

* Your program must continue play until somebody (computer or human) wins.

* Your output should resemble the sample output shown above. It should clearly show if the computer or the human wins.

* When it’s time to demo be prepared to discuss how you would implement a “smarter” strategy for the computer player.

Submitting your work
=====================

Assignments are not graded, however a rubric is presented on Canvas which shows the skills that we hope students to learn by completing this assignment. Please consider discussing your work with an instructor or TA, the exams and quizzes are written based on the concepts presented in the homework assignments and assume that students are practicing these skills by completing the homework.