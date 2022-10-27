.. qnum::
   :prefix: 6-7-
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
    
    
Static Variables and Methods
============================

We have seen the Math class and its many static methods like Math.random(), and we've always used a main method which is static. In this lesson, you will learn to write your own static variables and methods.

- **Static** variables and methods belong to a class and are called with the Class Name rather than using object variables, like ClassName.methodName();  

- If you are calling a static method from within the same class, you can leave off the Classname and dot notation as we saw in Unit 5.

- There is only one copy of a static variable or method for the whole class. For example, the main method is static because there should only be 1 main method. 

- Static methods can be public or private.

- The static keyword is placed right after the public/private modifier and right before the type of variables and methods in their declarations. 

- A static method does not have a **this** variable, since it is not called with an object.

.. code-block:: java
     
   class ClassName {
     // static variable
     public static type variableName;
     
     // static method
     public static returnType methodName(parameters) {
           // implementation not shown 
     }
   }
   // To call a static method or variable, use the Class Name
   System.out.println(ClassName.staticVariable);
   ClassName.staticMethod();


Static methods only have access to other static variables and static methods (unless the static method creates an object through which to access instance variables and methods). 
Static methods cannot access or change the values of instance variables or use the "this" reference (since there is no calling object for them), and static methods cannot call non-static methods. However, non-static methods have access to all variables (instance or static) and methods (static or non-static) in the class.

Since there is only 1 copy of a static variable or method, static variables are often used to count how many objects are generated. In the following class Person, there is a static variable called personCounter that is incremented each time the Person constructor is called to initialize a new Person object. The static method printCounter() prints out its value.  You can also watch how it works in the |Java visualizer| by clicking the CodeLens button below.


What will the code in the given ``Person`` class print out? Try adding another Person object and see what happens. Try the debugger to run the code step by step.
 
  
Another common use for static variables is the keep track of a minimum or maximum value or an average of the values in a collection of objects.

|Exercise| **Check Your Understanding**

.. mchoice:: q6_7_1
   :practice: T
   
   Consider the class Temperature below which has a static variable. What is the output of the main method below?
   
   .. code-block:: java
   
       public class Temperature 
       {
          private double temperature;
          public static double maxTemp = 0;

          public Temperature(double t)
          {
               temperature = t;
               if (t > maxTemp)
                   maxTemp = t;
          }

          public static void main(String[] args)
          {
               Temperature t1 = new Temperature(75);
               Temperature t2 = new Temperature(100);
               Temperature t3 = new Temperature(65);
               System.out.println("Max Temp: " + Temperature.maxTemp);
          }
        }

   - Max Temp: 0
    
     - maxTemp is changed in each call to the Temperature() constructor.
      
   - There is a compiler error because the static variable maxTemp cannot be used inside a non-static constructor.
    
     - Non-static methods and constructors can use any instance or static variables in the class.
      
   - Max Temp: 100
    
     + Yes, maxTemp is initialized to 0 and then changed to 75 and then 100 by the constructor calls.
      
   - Max Temp: 75
    
     - maxTemp will be changed to 100 by the second constructor call since 100 > 75.
      
   - Max Temp: 65
    
     - maxTemp will not be changed to 65 by the third constructor call because 67 is not > 100.
      
|CodingEx| **Coding Exercise**


Fix the bugs in the ``Temperature`` program.

|Groupwork| Programming Challenge : Static Song and counter
------------------------------------------------------------

In Unit 5, we wrote a class with a static method to print out the verses in the Old MacDonald song. 
Notice that this is a class where 
there are no instance variables and we don't really need to generate multiple objects. 
With students or pets, it makes sense to have multiple objects. 
With the Song, we were able to make the verse method static and have just 1 copy. 


Add a static variable to the ``Song`` class that keeps track of the number of verses. 
Increment this variable each time the method to print a verse is called and print it out. 
Update the main method to add a few more verses (pig says oink, chicken says cluck) and rerun the program.



Summary
-------

- Static methods and variables include the keyword static  before their name in the header or declaration. They can be public or private.

- Static variables belong to the class, with all objects of a class sharing a single static variable.

- Static methods are associated with the class, not objects of the class.

- Static variables are used with the class name and the dot operator, since they are associated with a class, not objects of a class.

- Static methods cannot access or change the values of instance variables, but they can access or change the values of static variables.

- Static methods cannot call non-static methods.
