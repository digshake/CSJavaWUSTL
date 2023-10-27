.. qnum::
   :prefix: 10-6-
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
    
Polymorphism
=============

..	index::
    single: polymorphism
    
**Polymorphism** is a big word that you can break down into "poly" which means many and "morphism" which means form.  So, it just means many forms.  In Java it means that the method that gets called at **run-time** (when the code is run) depends on the *type* of the object at run-time.  

This is simliar to a toddler toy that has pictures of animals and when a handle is pulled an arrow spins.  When the arrow stops the toy plays the sound associated with that animal. 

.. figure:: Figures/SeeNSay.jpg
    :width: 250px
    :align: center
    :figclass: align-center

    Figure 1: A see n say toy

   
If you were simulating this toy in software you could create an Animal class that had a makeNoise method. Each subclass of Animal would override the makeNoise method to make the correct noise for that type.  This type of polymorphism is called **inheritance-based polymorphism**.  You have a common parent class, but the behavior is specified in the child class.

..	index::
    single: declared type
    single: actual type
    single: run-time type
    pair: type; declared
    pair: type; actual
    pair: type; run-time


.. note::

   In Java an object variable has both a **declared (compile-time) type** and an **actual (run-time) type**.  The *declared (compile-time) type*  of a variable is the type that is used in the declaration.  The *actual (run-time) type* is the class that actually creates the object using new.  
   
The variable ``nameList`` declared below has a **declared type** of ``List`` and an **actual** or **run-time type** of ``ArrayList``.  The complier will check if the declared type has the methods or inherits the methods being used in the code and give an error if it doesn't find the method(s).  The List interface does have an ``add`` method so this code will compile.  At run-time the execution environment will first look for the ``add`` method in the ``ArrayList`` class since that is the actual or run-time type. If it doesn't find it there it will look in the parent class and keep looking up the inheritance tree until it finds the method. It may go up all the way to the Object class.  The method will be found, since otherwise the code would not have compiled.

.. code-block:: java 

  List<String> nameList = new ArrayList<String>(); 
  nameList.add("Hi");
  
The variable ``message`` declared below has a **declared type** of ``Object`` and an **actual** or **run-time type** of ``String``.  Since the declared type of ``message`` is ``Object`` the code ``message.indexOf("h");`` will cause a compiler error since the ``Object`` class does not have an ``indexOf`` method.
  
.. code-block:: java 

  Object message = new String("hi");
  message.indexOf("h"); // ERROR!! Objects don't have indexOf!
  
.. .. note::

   Any object variable can refer to an object of the declared type or *any descendant (subclass) of the declared type* at run-time. The class ``String`` inherits from the class ``Object`` so an ``Object`` variable can hold a reference to a ``String`` object.  But, you can only call methods that are available in the ``Object`` class unless you cast it back to the ``String`` class.

At compile time, the compiler uses the declared type to check that the methods you are trying to use are available to an object of that type.  The code won't compile if the methods don't exist in that class or some parent class of that class.  At run-time, the actual method that is called depends on the actual type of the object.  Remember that an object keeps a reference to the class that created it (an object of the class called ``Class``).  When a method is called at run-time the first place that is checked for that method is the class that created the object.  If the method is found there it will be executed.  If not, the parent of that class will be checked and so on until the method is found.  

In the last lesson on inheritance hierarchies, we were actually seeing polymorphic behavior at run-time in the following ways. 

1. Polymorphic assignment statements such as ``Shape s = new Rectangle();``
2. Polymorphic parameters such as ``print(Shape)`` being called with different subclass types.
3. Polymorphic array and ArrayList types such as ``Shape[] shapeArray = { new Rectangle(), new Square() };``

In all of these cases, there are no errors at compile-time because the compiler checks that the "subclass is-a superclass" relationship is true. But at run-time, the Java interpreter will use the object's actual subclass type and call the subclass methods for any overriden methods. This is why they are polymorphic -- the same code can have different results depending on the object's actual type at run-time.

|Exercise| **Check your understanding**

.. mchoice:: qoo_10
   :practice: T
   :answer_a: Shape Shape Shape Shape
   :answer_b: Shape Rectangle Square Circle
   :answer_c: There will be a compile time error
   :answer_d: Shape Rectangle Rectangle Circle
   :answer_e: Shape Rectangle Rectangle Oval
   :correct: d
   :feedback_a: The Rectangle subclass of Shape overrides the what method so this can't be right.
   :feedback_b: The Square subclass doesn't not override the what method so it will use the one in Rectangle.  
   :feedback_c: This code will compile.  The declared type can hold objects of that type or any subclass of the type.
   :feedback_d: The Shape object will print Shape.  The Rectangle object will print Rectangle.  The Square object will also print Rectangle since it doesn't overrride the what method.  The Circle object will print Circle.  
   :feedback_e: The Circle class does override the what method so this can't be right.  

   What is the output from running the main method in the Shape class?
   
   .. code-block:: java 
   
      public class Shape {
         public void what() { System.out.print("Shape ");}
         
         public static void main(String[] args) {
         
            Shape[] shapes = {new Shape(), new Rectangle(), new Square(), 
                              new Circle()};
            for (Shape s : shapes)
            {
               s.what();
               System.out.print(" ");
            }
         }

      } 

      class Rectangle extends Shape {
         public void what() { System.out.print("Rectangle "); }
      }

      class Square extends Rectangle {
      }
      
      class Oval extends Shape {
         public void what() { System.out.print("Oval "); }
      }

      class Circle extends Oval {
         public void what() { System.out.print("Circle ");}
      }
      
You can step through this code using the Java Visualizer by clicking on the following link `Shape Example <http://cscircles.cemc.uwaterloo.ca/java_visualize/#code=public+class+Shape+%7B%0A+++public+void+what()+%7B+System.out.print(%22Shape+%22)%3B%7D%0A+++++++++%0A+++public+static+void+main(String%5B%5D+args)+%7B%0A+++++++++%0A++++++Shape%5B%5D+shapes+%3D+%7Bnew+Shape(),+new+Rectangle(),+new+Square(),+%0A++++++++++++++++++++++++++++++new+Circle()%7D%3B%0A++++++for+(Shape+s+%3A+shapes)%0A++++++%7B%0A+++++++++s.what()%3B%0A+++++++++System.out.print(%22+%22)%3B%0A++++++%7D%0A+++%7D%0A%0A%7D+%0A%0Aclass+Rectangle+extends+Shape+%7B%0A+++public+void+what()+%7B+System.out.print(%22Rectangle+%22)%3B+%7D%0A%7D%0A%0Aclass+Square+extends+Rectangle+%7B%0A%7D%0A++++++%0Aclass+Oval+extends+Shape+%7B%0A+++public+void+what()+%7B+System.out.print(%22Oval+%22)%3B+%7D%0A%7D%0A%0Aclass+Circle+extends+Oval+%7B%0A+++public+void+what()+%7B+System.out.print(%22Circle+%22)%3B%7D%0A%7D%0A%0A&mode=display&curInstr=38>`_.
      

.. mchoice:: qoo_11
   :practice: T
   :answer_a: Pizza
   :answer_b: Taco
   :answer_c: You will get a compile time error
   :answer_d: You will get a run-time error
   :correct: b
   :feedback_a: This would be true if s1 was actually a Student, but it is a GradStudent.  Remember that the run-time will look for the method first in the class that created the object.
   :feedback_b: Even though the getInfo method is in Student when getFood is called the run-time will look for that method first in the class that created this object which in this case is the GradStudent class.
   :feedback_c: This code will compile.  The student class does have a getInfo method.  
   :feedback_d: There is no problem at run-time. 

   What is the output from running the main method in the Student class?
   
   .. code-block:: java 
   
      public class Student {
      
         public String getFood() {
            return "Pizza";
         }
         
         public String getInfo()  { 
           return this.getFood(); 
         }
         
         public static void main(String[] args)
         {
           Student s1 = new GradStudent();
           s1.getInfo();
         }
      }

      class GradStudent extends Student {
      
        public String getFood() {
           return "Taco";
        }
        
      }
       
 
.. mchoice:: qoo_12
   :practice: T
   :answer_a: 5 6 10 11
   :answer_b: 5 6 5 6
   :answer_c: 10 11 10 11
   :answer_d: The code won't compile.  
   :correct: a
   :feedback_a: The code compiles correctly, and because RaceCar extends the Car class, all the public object methods of Car can be used by RaceCar objects.
   :feedback_b: RaceCar, while it inherits object methods from Car via inheritance, has a separate and different constructor that sets the initial fuel amount to 2 * g, thus in this case, fuel for fastCar is set to 10 initially.
   :feedback_c: The variable car is a Car object, so the constructor used is not the same as the fastCar object which is a RaceCar. The car constructor does not change the passed in parameter, so it is set to 5 initially. 
   :feedback_d: RaceCar inherits from the Car class so all the public object methods in Car can be accessed by any object of the RaceCar class.

   What is the output from running the main method in the RaceCar class?
   
   .. code-block:: java
   
      public class Car
      {
        private int fuel;

        public Car() { fuel = 0; } 
        public Car(int g) { fuel = g; }

        public void addFuel() { fuel++; }
        public void display() { System.out.print(fuel + " "); }
        
        public static void main(String[] args)
        {
           Car car = new Car(5);
           Car fastCar = new RaceCar(5);
           car.display();
           car.addFuel();
           car.display();
           fastCar.display();
           fastCar.addFuel();
           fastCar.display();
        }
        
      }

      class RaceCar extends Car
      {
        public RaceCar(int g) { super(2*g); }
      } 
      
      
.. mchoice:: qoo_13
   :practice: T
   :answer_a: b.getISBN();
   :answer_b: b.getDefintion();
   :answer_c: ((Dictionary) b).getDefinition();
   :correct: b
   :feedback_a: The b object is actually a Dictionary object which inherits the getISBN method from Book.
   :feedback_b: At compile time the declared type is Book and the Book class does not have or inherit a getDefintion method.
   :feedback_c: Casting to Dictionary means that the compiler will check the Dictionary class for the getDefinition method.

   Given the following class definitions and a declaration of Book b = new Dictionary which of the following will cause a compile-time error?
   
   .. code-block:: java 
   
      public class Book
      {
         public String getISBN() 
         {
            // implementation not shown
         }
   
         // constructors, fields, and other methods not shown
      }

      public class Dictionary extends Book
      {
         public String getDefinition()
         {
            // implementation not shown
         }
      } 
    
Summary
----------

- At compile time, methods in or inherited by the **declared type** determine the correctness of a non-static method call.

- At run-time, the method in the **actual object type** is executed for a non-static method call. This is called **polymorphism**.

