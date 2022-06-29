=====================
Module 2 Assignment
=====================

.. Here is were you specify the content and order of your new book.

.. Each section heading (e.g. "SECTION 1: A Random Section") will be
   a heading in the table of contents. Source files that should be
   generated and included in that section should be placed on individual
   lines, with one line separating the first source filename and the
   :maxdepth: line.

.. Sources can also be included from subfolders of this directory.
   (e.g. "DataStructures/queues.rst").





Assignment 2: Game of Nim
::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::

* `Assignment Setup`_

* `Game of Nim`_

  * `Example`_

  * Notes_

* `Submitting your work`_

.. _Assignment Setup:

**Assignment Setup**

To create your repository go `here <https://classroom.github.com/a/vDG5z2OJ>`_. Then follow the same accept/import process described in `Assignment 0 <https://classes.engineering.wustl.edu/2021/fall/cse131//modules/0/assignment>`_.

.. _Game of Nim:

**Game of Nim**

`Nim <https://en.wikipedia.org/wiki/Nim>`_ is a `game of strategy <https://en.wikipedia.org/wiki/Strategy_game>`_ in which two players take turns removing sticks from a common pile. There are many variations of Nim but we will stick with a simple version. On each turn a player must remove either 1 or 2 sticks from the pile. The goal of the game is to be the player who removes the last stick.

You will design a game in which one human player is competing against a computer. To simplify your work the person will always take the first turn.

While there is a winning strategy for this game, you are only required to create a computer player that makes random, but valid, moves.

.. _Example:

**Example**

``Round 0: 7 at start human takes 2, so 5 remain``

``Round 1: 5 at start computer takes 2, so 3 remain``

``Round 2: 3 at start human takes 2, so 1 remain``

``Round 3: 1 at start computer takes 1, so 0 remain``

``The computer wins / you lose!``

.. _Notes:

**Notes**

* Begin by prompting the user for the initial number of sticks. In the example above, it appears that 7 sticks were used in the game.

* The human (as always in this assignment) made the first move.

* Clearly, the human could have played better in the above game.

* The computer randomly removes 1 or 2 sticks, but cannot remove more sticks than are left.

* The human is prompted at each turn for how many sticks to remove.

Be careful! A human might enter 5 if 5 sticks are left, and if you are not careful, the human could win by “ `playing <https://en.wikipedia.org/wiki/Cheating>`_ ” in that way. Don’t accept the user’s input if it is illegal. You may assume that they will only enter integers, but you should continue prompting until you get a valid value.

* Start your work by creating a ``Nim`` class in the ``assignment2`` package.

* Use ``ArgsProcessor`` to prompt for inputs.

* Your program must continue play until somebody (computer or human) wins.

* Your output should resemble the sample output shown above. It should clearly show if the computer or the human wins.

* When it’s time to demo be prepared to discuss how you would implement a “smarter” strategy for the computer player.

.. _Submitting your work:

**Submitting your work**

To submit your work come to office hours or class on an “Assignment day” and sign up for a demo via wustl-cse.help.