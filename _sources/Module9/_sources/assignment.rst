=====================
Module 9 Assignment
=====================

.. Here is were you specify the content and order of your new book.

.. Each section heading (e.g. "SECTION 1: A Random Section") will be
   a heading in the table of contents. Source files that should be
   generated and included in that section should be placed on individual
   lines, with one line separating the first source filename and the
   :maxdepth: line.

.. Sources can also be included from subfolders of this directory.
   (e.g. "DataStructures/queues.rst").


Assignment 9: Scene Composer
::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::

* `Assignment Setup`_

  * `Overview`_

  * `Requirements`_

  * `Code base`_

* `Submitting your work`_


.. _Assignment Setup:

**Assignment Setup**

To create your repository go `here <https://classroom.github.com/a/DDL1ilgU>`__. Then follow the same accept/import process described in `Assignment 0 <https://classes.engineering.wustl.edu/2021/fall/cse131//modules/0/assignment>`_.

This assignment is fairly creative in that:

* There is no unit test to guide your work

* The manner in which your solution works is up to you, although there is a video of Prof. Cytron’s solution

* The application you develop here allows creation of artistic images

.. _Overview:

**Overview**

The idea is to develop an application in which a user (presently, just yourself) can compose images.

Some of these images will be available already by names of your choosing. For example, the names ``f0``, ``f1``, …, ``f9`` represent 10 forest images that can be drawn on the screen.

You will allow users to record a sequence of images, and then select a name for that sequence, so that the sequence itself can be called up by its new name.

There is no limit to the fun that can be had here, because new sequences can be created at will and recorded to be known by name.

You can create your solution all in one ``main`` method as you did at the beginning of the semester. Or you can use objects as you have more recently been taught. How you construct your solution is up to you but it must meet the requirements stated below to earn credit.

The code base provided to you draws images using somewhat transparent colors, so that if you draw the same image twice, its intensity increases.

.. _Requirements:

**Requirements**

Before continuing, take a look at `this video <https://wustl.box.com/s/o0cnmrq5enboqsq2t3u8xapcatr511fz>`__.

To receive credit you must:

* Use a ``Map<String,Drawable>`` to allow users to recall existing scenes and create new ones.

* Use a ``List<Drawable>`` as needed to store a list of ``Drawables``.

* Create an initial scene with multiple objects and store it under the name "``init``".

* Prompt the user repeated for input (using ``ArgsProcessor``).

* Properly clear the screen when ``clear`` is typed.

* Cease prompting the user when ``end`` is typed.

* Allow the recording of a sequence of ``Drawables``, and the subsequent recall of that sequence for display.

.. _Code base:

**Code base**

Before continuing, take a look at `this video <https://wustl.box.com/s/s82qapv7gwtz6pw4fryrxjamqxp0nryo>`_.

Familiarize yourself with the code by watching the video and looking at the ``assignment9`` and contained packages.

OK! implement at least the features above and have fun with this!

.. _Submitting your work:

**Submitting your work**

To submit your work come to office hours or class on an “Assignment day” and sign up for a demo via `wustl-cse.help <https://wustl-cse.help/>`_. Be prepared to show them the work that you have done and answer their questions about it!