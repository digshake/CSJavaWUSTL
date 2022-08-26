.. qnum::
   :prefix: 2-14-
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

.. |repl| raw:: html

   <a href="https://repl.it" target="_blank" style="text-decoration:underline">repl.it</a>
   
.. |Java Swing Example| raw:: html

   <a href="https://repl.it/@BerylHoffman/JavaSwingHello" target="_blank" style="text-decoration:underline">Java Swing Example</a>
   
.. |JButton Class| raw:: html

   <a href="https://www.javatpoint.com/java-jbutton" target="_blank" style="text-decoration:underline">JButton Class</a>
      

Java Swing GUIs (optional)
==============================

Java has a library called **Swing** which is a 
graphical user interface (GUI) toolkit that includes buttons and other 
standard graphical components. 
This lesson is an optional introduction to Java Swing and using its classes.

The graphical components in Java Swing are all classes, and to use them, you must declare objects of those classes. In this lesson, we will show the following Swing classes:

    - JFrame : a window or container for the GUI.
    - JButton : a button that can be clicked.
    - JLabel : a label that can be used to print output to the GUI.

To use Java Swing, you usually need to import the following libraries:

.. code-block:: java 

    import java.swing.*;
    import java.awt.*;
    import java.awt.event.*;
    
To set up a JFrame window for your UI, declare an object of type JFrame, set its size in pixels, its layout, and make it visible:

.. code-block:: java 

    JFrame frame = new JFrame("My app"); 
    frame.setSize(500, 500);
    frame.setLayout(null);
    frame.setVisible(true); // usually at the end of the main method

Once you have a JFrame, you can create graphical objects like buttons and labels and add them to the JFrame. You can look up more information about these Java Swing Components and what methods they have. For example, here's more information on the |JButton Class|.

.. code-block:: java 

    JButton button1 = new JButton("Click Me!");
    // if using null layout, set position and size for components
    // setBounds(x position, y position, width, height)
    button1.setBounds(10, 10, 100, 50);
    frame.add(button1);

If you set the layout of the frame to null, you must use setBounds(x position, y position, width, height) for each component to set their position and size on the frame. Remember that the top left corner has the (x,y) coordinates (0,0). The bottom right corner coordinates are the size of your frame, for example (500,500). The width 100 and the height 50 are good sizes for most components. Some Java IDEs have GUI Visual Designers where you can drag and drop in and resize components.  

In |repl|, there is no GUI designer available, but it can display Java Swing GUIs. When creating a new repl, you can choose Java Swing as the file type, instead of just Java, to use a Java Swing UI.

|CodingEx| **Coding Exercise**

Here's a |Java Swing Example| on repl that sets up a JFrame with a JButton and a JLabel. It calls a special method called addActionListener where you can put the code to be executed when you click on a button. Can you add another button to it? Remember that you will need to create a JButton object, setBounds for it, and add it to the frame. Copy the addActionListener code and change it to work for your new button to say Good Bye instead of hello. 

.. raw:: html

    <iframe height="800px" width="100%" style="max-width:90%; margin-left:5%" src="https://repl.it/@BerylHoffman/JavaSwingHello?lite=true" scrolling="no" frameborder="no" allowtransparency="true" allowfullscreen="true" sandbox="allow-forms allow-pointer-lock allow-popups allow-same-origin allow-scripts allow-modals"></iframe><br>

To learn more about Java Swing, click on the different Swing components in the left navigation column of https://www.javatpoint.com/java-swing and try them out!