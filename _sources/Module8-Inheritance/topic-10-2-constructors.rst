.. qnum::
   :prefix: 10-2-
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
    

Inheritance and Constructors
============================

..	index::
    pair: constructor; super

Subclasses inherit all the private instance variables in a superclass that they extend, but they cannot directly access them since they are private. And constructors are not inherited. 

How do you initialize inherited private variables if you don't have direct access to them in the subclass?  In Java you can put a call to the parent constructor using  as the first line in a subclass constructor.   In Java, the superclass constructor can be called from the first line of a subclass constructor by using the keyword super and passing appropriate parameters, for example ``super();`` or ``super(theName);`` as in the code below.
The actual parameters given to super() are used to initialize the inherited instance variables, for example the name instance variable in the Person superclass.

.. code-block:: java

    public class Employee extends Person {
        public Employee() {
            super(); // calls the Person() constructor
        }
        public Employee(String theName) {
            super(theName); // calls Person(theName) constructor
        }
    }
    
|CodingEx| **Coding Exercise**

The ``super(theName)`` in the ``Employee`` constructor will call the constructor that takes a ``String`` object in the ``Person`` class to set the name. 


  Try creating another Employee object in the main method that passes in your name and then use the get methods to print it out. Which class constructor sets the name? Which class constructor sets the id?

  
If a class has no constructor in Java, the compiler will add a no-argument constructor.  A no-argument constructor is one that doesn't have any parameters, for example ``public Person()``.   

If a subclass has no call to a superclass constructor using ``super`` as the first line in a subclass constructor then the compiler will automatically add a ``super()`` call as the first line in a constructor.  So, be sure to provide no-argument constructors in parent classes or be sure to use an explicit call to ``super()`` as the first line in the constructors of subclasses.

Regardless of whether the superclass constructor is called implicitly or explicitly, the process of calling superclass constructors continues until the Object constructor is called since every class inherits from the Object class.

|Exercise| **Check your understanding**

.. .. mchoice:: qoo_8
   :practice: T
   :answer_a: II only
   :answer_b: III only 
   :answer_c: I and II only
   :answer_d: I, II, and III
   :correct: d
   :feedback_a: I is true because Point2D does have a no-arg constructor. II is true because Point2D does have a constructor that takes x and y. III is true because Point2D does have a no-arg constructor which will be called before the first line of code is executed in this constructor. The fields x and y are public in Point2D and thus can be directly accessed by all classes.
   :feedback_b: Point2D does have a constructor that takes an x and y value so this is okay. Also the call to super is the first line of code in the child constructor as required. However, both I and III are okay as well. 
   :feedback_c: The x and y values in Point2D are public and so can be directly accessed by all classes including subclasses. Also there is a no-arg constructor in Point2D so the super no-arg constructor will be called before the first line of code in this constructor.
   :feedback_d: I is true because Point2D does have a no-arg constructor. II is true because Point2D does have a constructor that takes x and y. III is true because Point2D does have a no-arg constructor which will be called before the first line of code is executed in this constructor. The fields x and y are public in Point2D and thus can be directly accessed by all classes.
    
   Given the class definitions of Point2D and Point3D below, which of the constructors that follow (labeled I, II, and III) would be valid in the Point3D class?

   .. code-block:: java 
   
      class Point2D {
         public int x;
         public int y;

         public Point2D() {}

         public Point2D(int x,int y) {
           this.x = x;
           this.y = y;
         }
         // other methods
      }

      public class Point3D extends Point2D {
         public int z;
   
         // other code
      }
      
      // possible constructors for Point3D
      I.  public Point3D() {}
      II. public Point3D(int x, int y, int z) 
          {
             super(x,y);
             this.z = z;
          }
      III. public Point3D(int x, int y)
           {
              this.x = x;
              this.y = y;
              this.z = 0;
           }
           


.. mchoice:: qoo_9
   :practice: T
   :answer_a: I only
   :answer_b: I and III
   :answer_c: II only 
   :answer_d: III only
   :correct: b
   :feedback_a: I is okay but III is also okay.
   :feedback_b: NamedPoint will inherit from MPoint all fields but the fields are private and they can not be directly accessed in NamedPoint. You can use super as the first line in a constructor to initialize inherited fields. You can also set your own fields in a constructor. If you don't use super as the first line in a constructor one will be put there by the compiler that will call the parent's no argument constructor.
   :feedback_c: II is invalid. Children inherit all of the fields from a parent but do not have direct access to private fields. You can use super in a constructor to initialize inherited fields by calling the parent's constructor with the same parameter list.
   :feedback_d: I is also okay
    
   Given the class definitions of MPoint and NamedPoint below, which of the constructors that follow (labeled I, II, and III) would be valid in the NamedPoint class?

   .. code-block:: java 
   
      
      class MPoint {
         private int myX; // coordinates
         private int myY;

         public MPoint( ) {
            myX = 0;
            myY = 0;
         }

         public MPoint(int a, int b) {
            myX = a;
            myY = b;
         }

         // ... other methods not shown

      }
      
      public class NamedPoint extends MPoint {
         private String myName;
         // constructors go here
         // ... other methods not shown
      }
      
      //  Proposed constructors for this class:
      I.   public NamedPoint()
           {
              myName = "";
           }
      II.  public NamedPoint(int d1, int d2, String name)
           {
              myX = d1;
              myY = d2;
              myName = name;
           }
      III. public NamedPoint(int d1, int d2, String name)
           {
              super(d1, d2);
              myName = name;
           }
       

|Groupwork| Programming Challenge : Square is-a Rectangle 
----------------------------------------------------------

In this challenge, you are giving a class called Rectangle that has two instance variables, length and width, and two constructors that initialize them, and a method called draw() that uses nested loops to draw a length x width rectangle of stars. Try it out below.

You will write a new class called Square that inherits from Rectangle. Is a square a rectangle? Yes! A square is a rectangle where the length and width are equal. Square will inherit length, width, and the draw method. You will write square constructors that will call the Rectangle constructors. 

1. Make the class Square inherit from Rectangle
2. Add a Square no-argument constructor that calls Rectangle's constructor using super().
3. Add a Square constructor with 1 argument for a side that calls Rectangle's constructor with 2 arguments using super.
4. Uncomment the objects in the main method to test drawing the squares.
5. Add an area() method to Rectangle that computes the area of the rectangle. Does it work for squares too? Test it.
6. Add another subclass called LongRectangle which inherits from Rectangle but has the additional condition that the length is always 2 x the width. Write constructors for it and test it out. 

Summary
---------

- Subclasses inherit all the private instance variables in a superclass that they extend, but they cannot directly access them since they are private.

- Constructors are not inherited.

- The superclass constructor can be called from the first line of a subclass constructor by using the keyword super and passing appropriate parameters to set the private instance variables of the superclass.

- The actual parameters passed in the call to the superclass constructor provide values that the constructor can use to initialize the object’s instance variables.

- When a subclass’s constructor does not explicitly call a superclass’s constructor using super, Java inserts a call to the superclass’s no-argument constructor.

- Regardless of whether the superclass constructor is called implicitly or explicitly, the process of calling superclass constructors continues until the Object constructor is called. At this point, all of the constructors within the hierarchy execute beginning with the Object constructor.