.. qnum::
   :prefix: 5-4-
   :start: 1

.. |CodingEx| image:: ../../_static/codingExercise.png
    :width: 30px
    :align: middle
    :alt: coding exercise
    
    
.. |Exercise| image:: ../../_static/exercise.png
    :width: 35
    :align: middle
    :alt: exercise
    
    
.. |Groupwork| image:: ../../_static/groupwork.png
    :width: 35
    :align: middle
    :alt: groupwork


.. |visualizer| raw:: html

   <a href="https://cscircles.cemc.uwaterloo.ca/java_visualize/">Java Visualizer</a>   
  
Method Comments and Conditions
===============================

In industry you often produce code that other people will use and you will use code other people produced.  It is important
to document your code to facilitate understanding and reuse.


Method Comments
----------------

Recall that there are 3 types of comments in Java:

1. ``//`` Single line comment
2. ``/*`` Multiline comment ``*/``
3. ``/**`` Documentation comment ``*/``

.. |Java JDK| raw:: html

   <a href="https://www.oracle.com/technetwork/java/javase/downloads/index.html" target="_blank">Java JDK</a>

.. |javadoc| raw:: html

   <a href="https://www.tutorialspoint.com/java/java_documentation.htm" target="_blank">javadoc</a>

.. |String class| raw:: html

   <a href="http://docs.oracle.com/javase/7/docs/api/java/lang/String.html" target="_blank">String class</a>
   
The special characters ``//`` are used to mark the rest of the line as a comment in many programming languages.  If the comment is going to be multiple lines, we use ``/*`` to start the comment and ``*/`` to end the comment. 

The multi-line comment, ``/**``  ``*/`` is called the documentation comment. 
Java has a cool tool called |javadoc| that comes with the |Java JDK| that will pull out all of these 
comments to make documentation of a class as a web page.  This tool generates the official Java 
documentation too, for example for the |String class|. 
It's a good idea to use the documentation comment in front of classes, methods, and 
instance variables in case you want to use this tool. 

The are some special tags that you can use in Java documentation. These are not required but many programmers use them. Here are some common tags:

- @author  Author of the program
- @since   Date released
- @version Version of program 
- @param   Parameter of a method
- @return  Return value for a method

The code below shows example commenting for a class and two enclosed methods.

.. code-block:: java

    /**
    * The Converter program implements an application that
    * converts inches to centimeters and prints
    * the equivalent quantities.
    *
    * @author  Fred Smith
    * @version 1.0
    * @since   2020-01-31
    */
    public class Converter {

        /**
        * This method is used to convert inches to centimeters.
        * @param inches A double representing a quantity of inches.
        * @return double The equivalent quantity of centimeters.
        */
        public static double inchesToCentimeters(double inches) {
            return inches * 2.54;
        }

        /**
        * The main method demonstrates use of the inchesToCentimeters method.
        * @param args Unused.
        * @return Nothing.
        */
        public static void main(String[] args) {
            System.out.println("10 inches = " + inchesToCentimeters(10) + " centimeters");
            System.out.println("15.7 inches = " + inchesToCentimeters(15.7) + " centimeters");
        }


    }

