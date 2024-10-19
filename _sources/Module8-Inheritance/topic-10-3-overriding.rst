.. qnum::
   :prefix: 10-3-
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
    
   
Overriding Methods
======================

A subclass inherits all public methods from its superclass, and these methods remain public in the subclass. But, we also usually add more methods or instance variables to the subclass. Sometimes, we want to modify existing inherited methods. This is called **overriding**  methods. 


**Overriding** an inherited method means providing a public method in a subclass with the same **method signature** (method name, parameter type list and return type) as a public method in the superclass.  The method in the subclass will be called *instead of* the method in the superclass. One common method that is overriden is the toString() method. The example below shows a similar method called greet().  

|CodingEx| **Coding Exercise**

In this example the ``MeanGreeter`` inherits the ``greet()`` method from ``Greeter``, but then overrides it. Run the program to see. 

Add another subclass called SpanishGreeter (or another language that you know) that extends Greeter and override the greet() method to return "Hola!" (or hi in another language) instead of "Hi!". Create an object to test it out.
   
   
.. note::

    To override an inherited method, the method in the child class must have the same name, parameter list, and return type (or a subclass of the return type) as the parent method. Any method that is called must be defined within its own class or its superclass.

You may see the @Override annotation above a method. This is optional but it provides an extra compiler check that you have matched the method signature exactly.

.. code-block:: java

    @Override
    public String greet() {
         return "Go Away";
    }


Overloading Methods
-------------------
Don't get **overriding** a method confused with **overloading** a method!
**Overloading** a method is when several methods have the same name but the parameter types, order, or number are different. So with overriding, the method signatures look identical but they are in different classes, but in overloading, only the method names are identical and they have different parameters.

.. code-block:: java

    // overriding methods
    g2.greet(); // This could be calling an overriden greet method in g2's class
    g1.greet("Sam"); // This calls an overloaded greet method 
    
|CodingEx| **Coding Exercise**

Notice that in the ``Greeter`` class, the ``greet(String who)`` method overloads the ``greet()`` method of ``Greeter``.  Notice that ``MeanGreeter`` inherits this method and it isn't overriden. 
   

.. note::
   
   To overload a method the method must have the same name, but the parameter list must be different in some way.  It can have a different number of parameters, different types of parameters, and/or a different order for the parameter types.  The return type can also be different.
  
|Exercise| **Check your understanding**

.. mchoice:: qoo_5
   :practice: T
   :answer_a: public void getFood()
   :answer_b: public String getFood(int quantity)
   :answer_c: public String getFood()
   :correct: c
   :feedback_a: The return type must match the parent method return type.
   :feedback_b: The parameter lists must match (must have the same types in the same order).  
   :feedback_c: The return type and parameter lists must match.   
    
    Which of the following declarations in ``Student`` would correctly *override* the ``getFood`` method in ``Person``?
    
    .. code-block:: java 
   
      public class Person {
         private String name = null;
         
         public Person(String theName) {
            name = theName;
         }
         
         public String getFood() {
            return "Hamburger";
         }
      }
        
      public class Student extends Person {
         private int id;
         private static int nextId = 0;
         
         public Student(String theName) {
           super(theName);
           id = nextId;
           nextId++;
         }
         
         public int getId() {return id;}
         
         public void setId (int theId) {
            this.id = theId;
         }
      }
      

|Exercise| **Check your understanding**

.. mchoice:: qoo_6
   :practice: T
   :answer_a: public void getFood()
   :answer_b: public String getFood(int quantity)
   :answer_c: public String getFood()
   :correct: b
   :feedback_a: You can not just change the return type to overload a method.  
   :feedback_b: For overloading you must change the parameter list (number, type, or order of parameters).  
   :feedback_c: How is this different from the current declaration for <code>getFood</code>?
    
    Which of the following declarations in ``Person`` would correctly *overload* the ``getFood`` method in ``Person``?
    
    .. code-block:: java 
   
      public class Person {
         private String name = null;
         
         public Person(String theName) {
            name = theName;
         }
         
         public String getFood() {
            return "Hamburger";
         }
      }
        
      public class Student extends Person {
         private int id;
         private static int nextId = 0;
         
         public Student(String theName) {
           super(theName);
           id = nextId;
           nextId++;
         }
         
         public int getId() {return id;}
         public void setId (int theId) {
            this.id = theId;
         }
      }  
      


Inherited Get/Set Methods
---------------------------

..	index::
    pair: inheritance; access to private fields

Inheritance means that an object of the child class automatically includes the object instance variables and methods defined in the parent class.  But, if the inherited instance variables are private, which they should be, the child class can not directly access the them using dot notation.  The child class can use public **accessors** (also called getters or get methods) which are methods that get instance variable values and public **mutators**  (also called modifier methods or setters or set methods) which set their values.  

For example, if a parent has a private instance variables, ``name``, then the parent typically provides a public ``getName`` method and a public ``setName`` method as shown below.  In the ``setName`` method below, the code checks if the passed string is null before it sets it and returns true if the set was successful or false otherwise.  The ``Employee`` class inherits the ``name`` field but must use the public method ``getName`` and ``setName`` to access it.

  
|Exercise| **Check your understanding**
  
.. mchoice:: qoo_7
   :practice: T
   :answer_a: currItem.setX(3);
   :answer_b: currItem.setY(2);
   :answer_c: currItem.x = 3;
   :answer_d: currItem.y = 2;
   :correct: c
   :feedback_a: The object currItem is an EnhancedItem object and it will inherit the public setX method from Item.
   :feedback_b: The object currItem is an EnhancedItem object and that class has a public setY method.
   :feedback_c: Even though an EnhancedItem object will have a x field the subclass does not have direct access to a private field.  Use the public setX method instead.
   :feedback_d: All code in the same class has direct access to all object fields.  
    
   Given the following class definitions which of the following would not compile if it was used in place of the missing code in the main method?
      
   .. code-block:: java 
   
      class Item {
         private int x;

         public void setX(int theX) {
            x = theX;
         }
         // ... other methods not shown
      }
      
      public class EnhancedItem extends Item {
         private int y;

         public void setY(int theY) {
            y = theY;
         }

         // ... other methods not shown
   
         public static void main(String[] args) {
            EnhancedItem currItem = new EnhancedItem();
            // missing code
         }
      }

Summary
---------

- Method **overriding** occurs when a public method in a subclass has the same method signature as a public method in the superclass.

- Any method that is called must be defined within its own class or its superclass.

- A subclass is usually designed to have modified (overridden) or additional methods or instance variables.

- A subclass will inherit all public methods from the superclass (for example all the set and get methods); these methods remain public in the subclass. 

- **Overloading** a method is when several methods have the same name but the parameter types, order, or number are different.