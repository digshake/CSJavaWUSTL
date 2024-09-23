  .. qnum::
   :prefix: 5-3-
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

Method Returns
=================

A method bundles together lines of code that perform a specific task.

- You can pass values into a method using formal parameters. 
- You can pass a value out of a method using a **return statement**.  

When a method returns a value, the code should do something with the value such as store it in a 
variable or print it.

You will learn how to  create methods that access object attributes in a later lesson. 
This lesson shows 
you how to create static methods that are functions. 
A function takes one or more values passed as formal parameters and computes a new value to return.


Method Return Type
------------------

A **void** return type means the method does not return a value.
If a method has a **non-void** return type, then it must contain a **return statement** that specifies the value to return.
The return type must match with the value in the return statement.


Click on each tab to observe the data flowing into the method through the formal parameters and out of the method through the return statement.

.. tabbed:: q5_3_2

    .. tab:: Tab 1

      The program starts at the first line of the main method.
      The red arrow shows that line 12 is next to execute, which will call the volumeCylinder function.
      
      .. figure:: Figures/frame1.png
 
    .. tab:: Tab 2

      The stack diagram shows a new frame was created for the volumeCylinder(4,10) method call. The new
      stack frame contains the formal parameter variables initialized to the actual argument values.   

      .. figure:: Figures/frame2.png

    .. tab:: Tab 3

      After line 6 is executed, the stack frame shows the computed value 502.6 will be returned 
      out of the method.  Where does the returned value go?  The call stack diagram indicates the value 
      is returned to line 12 of the main method, since that is the line of code that called the volumeCylinder method.

      .. figure:: Figures/frame3.png

    .. tab:: Tab 4

      The value was returned to the main method and line 12 assigns the value to the "vol" local variable.
      Line 13 is the next line to execute.

      .. figure:: Figures/frame4.png

    .. tab:: Tab 5

      Line 13 prints the value stored in the vol local variable.  The output window shows what was printed.

      .. figure:: Figures/frame5.png

    
Use the debugger to step through the ``E01VolumeExample`` program.  Experiment with passing different values to the volumeCylinder method.

|CodingEx| **Coding Exercise**
    
The ``E02InchesToCentimeters`` program contains a method ``inchesToCentimeters`` that computes and prints the centimeter equivalent of the value passed into the inches parameter.
Instead of printing the centimeter value inside the inchesToCentimeters method, you should update the  
method to return the value and then move the printing to the main method.  You will have to change 
the return type of the inchesToCentimeters method to match the type of the value being returned. 
Update the ``main`` method to print the value returned by the ``inchesToCentiments`` method. 


|Exercise| **Check your understanding**

.. mchoice:: q5_3_3
   :practice: T
   :answer_a: return "hello";
   :answer_b: return true;
   :answer_c: return 7.5;
   :answer_d: return 10;
   :correct: d
   :feedback_a: The method return type int does not match the return statement type String. 
   :feedback_b: The method return type int does not match the return statement type boolean.
   :feedback_c: The method return type int does not match the return statement type double.
   :feedback_d: The method return type int matches the return statement type int.
   
   Based on the method header below, which return statement has the correct type?  
    
   .. code-block:: java

     public static int mystery()


.. mchoice:: q5_3_4
   :practice: T
   :answer_a: return "hello";
   :answer_b: return true;
   :answer_c: return "true";
   :answer_d: return 10;
   :correct: b
   :feedback_a: The method return type boolean does not match the return statement type String. 
   :feedback_b: The method return type boolean matches the return statement type boolean.
   :feedback_c: The method return type boolean does not match the return statement type String.
   :feedback_d: The method return type boolean does not match the return statement type int.
   
   Based on the method header below, which return statement has the correct type?  
    
   .. code-block:: java

     public static boolean mystery2()


.. mchoice:: q5_3_5
   :practice: T
   :answer_a: String result = mystery3();
   :answer_b: int result = mystery3();
   :answer_c: boolean result = mystery3();
   :correct: b
   :feedback_a: The method return type int does not match the variable type String. 
   :feedback_b: The method return type int matches the variable type int.
   :feedback_c: The method return type int does not match the variable type boolean.
   
   Based on the method header below, which assignment statement is correct?  
    
   .. code-block:: java

     public static int mystery3()


.. mchoice:: q5_3_6
   :practice: T
   :answer_a: String result = mystery4();
   :answer_b: int result = mystery4();
   :answer_c: boolean result = mystery4();
   :answer_d: mystery4();
   :correct: d
   :feedback_a: A void return type means no value is returned.  There is no value to assign. 
   :feedback_b: A void return type means no value is returned.  There is no value to assign. 
   :feedback_c: A void return type means no value is returned.  There is no value to assign. 
   :feedback_d: A void return type means no value is returned.  You call the method as a statement.
   
   Based on the method header below, which statement is correct for calling the method?  
    
   .. code-block:: java

     public static void mystery4()


.. mchoice:: q5_3_7
   :practice: T
   :answer_a: return 10;
   :answer_b: return 12 * 4;
   :answer_c: return 15 / 2;
   :answer_d: return 3.7 ;
   :correct: d
   :feedback_a: The method return type int matches the return statement type int.
   :feedback_b: The method return type int matches the return statement type int.
   :feedback_c: The method return type int matches the return statement type int.
   :feedback_d: The method return type int does not match the return statement type double.
   
   Based on the method header below, which return statement DOES NOT have the correct type?  
    
   .. code-block:: java

     public static int mystery()


|CodingEx| **Coding Exercise**

A pedometer estimates that taking 2,000 steps is the same as walking 1 mile. 
In the ``E03StepCounter`` program, write a method ``convertToMiles`` that takes a parameter for the number of steps and returns the equivalent miles walked.
Update the main method to call ``convertToMiles`` 3 times with values 500, 2000, 3000. 
Carefully consider the method return type.  Watch out for integer division in the method body!
You can assume the number of steps is an integer.

  

|CodingEx| **Coding Exercise**
  
In the ``E04RandomNumberInRange`` program, write a function ``randomInteger`` that takes two integer 
parameters ``min`` and ``max`` and returns a random integer value between min and max (inclusive).
Have the main method call the function with different values.

Summary
-------

- A method can return at most one value

- The method signature must specify the return type

- A void return type indicates the method does not return a value

- The return statement is used to return a value

- The return statement causes control to immediately transfer out of the method.