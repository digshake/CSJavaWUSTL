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

In Unit 2, we explored the Math class and its many static methods like Math.random(), and we've always used a main method which is static. In this lesson, you will learn to write your own static variables and methods.

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

.. |Java visualizer| raw:: html

   <a href="http://www.pythontutor.com/visualize.html#code=%20public%20class%20Person%20%0A%20%20%7B%0A%20%20%20%20%20//%20instance%20variables%20%0A%20%20%20%20%20private%20String%20name%3B%0A%20%20%20%20%20private%20String%20email%3B%0A%20%20%20%20%20private%20String%20phoneNumber%3B%0A%20%20%20%20%20%0A%20%20%20%20%20//%20Static%20counter%20variable%0A%20%20%20%20%20public%20static%20int%20personCounter%20%3D%200%3B%0A%20%20%20%20%20%0A%20%20%20%20%20//%20static%20method%20to%20print%20out%20counter%0A%20%20%20%20%20public%20static%20void%20printPersonCounter%28%29%20%7B%0A%20%20%20%20%20%20%20%20%20%20System.out.println%28%22Person%20counter%3A%20%22%20%2B%20personCounter%29%3B%0A%20%20%20%20%20%7D%0A%20%20%20%20%20%0A%20%20%20%20%20//%20constructor%3A%20construct%20a%20Person%20copying%20in%20the%20data%20into%20the%20instance%20variables%0A%20%20%20%20%20public%20Person%28String%20initName,%20String%20initEmail,%20String%20initPhone%29%0A%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20name%20%3D%20initName%3B%0A%20%20%20%20%20%20%20%20email%20%3D%20initEmail%3B%0A%20%20%20%20%20%20%20%20phoneNumber%20%3D%20initPhone%3B%0A%20%20%20%20%20%20%20%20personCounter%2B%2B%3B%0A%20%20%20%20%20%7D%0A%20%20%20%20%20%0A%20%20%20%20%20//%20toString%28%29%20method%0A%20%20%20%20%20public%20String%20toString%28%29%20%0A%20%20%20%20%20%7B%20%0A%20%20%20%20%20%20%20return%20%20name%20%2B%20%22%3A%20%22%20%2B%20email%20%2B%20%22%20%22%20%2B%20phoneNumber%3B%0A%20%20%20%20%20%7D%0A%20%20%20%20%20%0A%20%20%20%20%20//%20main%20method%20for%20testing%0A%20%20%20%20%20public%20static%20void%20main%28String%5B%5D%20args%29%0A%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20//%20call%20the%20constructor%20to%20create%20a%20new%20person%0A%20%20%20%20%20%20%20%20Person%20p1%20%3D%20new%20Person%28%22Sana%22,%20%22sana%40gmail.com%22,%20%22123-456-7890%22%29%3B%0A%20%20%20%20%20%20%20%20Person%20p2%20%3D%20new%20Person%28%22Jean%22,%20%22jean%40gmail.com%22,%20%22404%20899-9955%22%29%3B%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%20%20%20%20Person.printPersonCounter%28%29%3B%0A%20%20%20%20%20%7D%0A%20%20%7D%0A%20%20&cumulative=false&curInstr=1&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=java&rawInputLstJSON=%5B%5D&textReferences=false" target="_blank" style="text-decoration:underline">Java visualizer</a>

Static methods only have access to other static variables and static methods (unless the static method creates an object through which to access instance variables and methods). 
Static methods cannot access or change the values of instance variables or use the "this" reference (since there is no calling object for them), and static methods cannot call non-static methods. However, non-static methods have access to all variables (instance or static) and methods (static or non-static) in the class.

Since there is only 1 copy of a static variable or method, static variables are often used to count how many objects are generated. In the following class Person, there is a static variable called personCounter that is incremented each time the Person constructor is called to initialize a new Person object. The static method printCounter() prints out its value.  You can also watch how it works in the |Java visualizer| by clicking the CodeLens button below.

.. activecode:: code6_7_1
  :language: java
  :autograde: unittest

  What will the following code print out? Try adding another Person object and see what happens. Try the CodeLens button to run the code step by step.
  ~~~~
  public class Person 
  {
     // instance variables 
     private String name;
     private String email;
     private String phoneNumber;
     
     // Static counter variable
     public static int personCounter = 0;
     
     // static method to print out counter
     public static void printPersonCounter() {
          System.out.println("Person counter: " + personCounter);
     }
     
     // constructor: construct a Person copying in the data into the instance variables
     public Person(String initName, String initEmail, String initPhone)
     {
        name = initName;
        email = initEmail;
        phoneNumber = initPhone;
        personCounter++;
     }
     
     // toString() method
     public String toString() 
     { 
       return  name + ": " + email + " " + phoneNumber;
     }
     
     // main method for testing
     public static void main(String[] args)
     {
        // call the constructor to create a new person
        Person p1 = new Person("Sana", "sana@gmail.com", "123-456-7890");
        Person p2 = new Person("Jean", "jean@gmail.com", "404 899-9955");
        
        Person.printPersonCounter();
     }
  }
  ====
  import static org.junit.Assert.*;
    import org.junit.*;;
    import java.io.*;

    public class RunestoneTests extends CodeTestHelper
    {
      @Test
        public void testMain() throws IOException
        {
            String output = getMethodOutput("main");
            String expect = "Person counter: 2";
            boolean passed = getResults(expect, output, "Expected output from main", true);
            assertTrue(passed);
        }
    }

  
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
      

.. |visualizer2| raw:: html

   <a href="http://www.pythontutor.com/visualize.html#code=public%20class%20Temperature%20%0A%7B%0A%20%20%20private%20double%20temperature%3B%0A%20%20%20public%20static%20double%20maxTemp%20%3D%200%3B%0A%20%20%20%0A%20%20%20public%20Temperature%28double%20t%29%0A%20%20%20%7B%0A%20%20%20%20%20%20%20temperature%20%3D%20t%3B%0A%20%20%20%20%20%20%20if%20%28t%20%3E%20maxTemp%29%0A%20%20%20%20%20%20%20%20%20%20%20maxTemp%20%3D%20t%3B%0A%20%20%20%7D%0A%20%20%20public%20static%20void%20main%28String%5B%5D%20args%29%0A%20%20%20%7B%0A%20%20%20%20%20%20%20Temperature%20t1%20%3D%20new%20Temperature%2875%29%3B%0A%20%20%20%20%20%20%20Temperature%20t2%20%3D%20new%20Temperature%28100%29%3B%0A%20%20%20%20%20%20%20Temperature%20t3%20%3D%20new%20Temperature%2865%29%3B%0A%20%20%20%20%20%20%20System.out.println%28%22Max%20Temp%3A%20%22%20%2B%20Temperature.maxTemp%29%3B%0A%20%20%20%7D%0A%7D&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=java&rawInputLstJSON=%5B%5D&textReferences=false" target="_blank" style="text-decoration:underline">Java visualizer</a>
   
You can see this code in action in the |visualizer2|.

|CodingEx| **Coding Exercise**

.. activecode:: code6_7_2
  :language: java
  :autograde: unittest
  :practice: T

  Fix the bugs in the following code. 
  ~~~~
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

    public static printMax()
    {
       System.out.println(temperature);
    }
    
    public static void main(String[] args)
    {
       Temperature t1 = new Temperature(75);
       Temperature t2 = new Temperature(100);
       Temperature.printMax();   
    }
   }
   ====
   import static org.junit.Assert.*;
    import org.junit.*;;
    import java.io.*;
    
    public class RunestoneTests extends CodeTestHelper
    {
        @Test
        public void testCodeContains1()
        {

            boolean passed = checkCodeContains("return type of printMax()", "public static void printMax()");
            assertTrue(passed);
        }

         @Test
        public void testCodeContains2()
        {

            boolean passed = checkCodeContains("static variable maxTemp in static function", "System.out.println(maxTemp);");
            assertTrue(passed);
        }

        @Test
        public void testMain() throws IOException
        {
            String output = getMethodOutput("main");
            String expect = "100.0";
            boolean passed = getResults(expect, output, "Expected output from main", true);
            assertTrue(passed);
        }
    }


|Groupwork| Programming Challenge : Static Song and counter
------------------------------------------------------------

In Unit 5-2, we wrote a class with a static method to print out the verses in the Old MacDonald song. 
Notice that this is a class where 
there are no instance variables and we don't really need to generate multiple objects. 
With students or pets, it makes sense to have multiple objects. 
With the Song, we were able to make the verse method static and have just 1 copy. 


.. activecode:: code6_7_3
  :language: java

  Add a static variable to the Song class that keeps track of the number of verses. 
  Increment this variable each time the method to print a verse is called and print it out. 
  Update the main method to add a few more verses (pig says oink, chicken says cluck) and rerun the program.

  ~~~~

  public class Song 
  { 

    //add a static variable to count how many times the verse method is called
  

    //update the method to increment the counter
    public static void verse(String animal, String noise) 
    {
      System.out.println( "Old MacDonald had a farm" );
      System.out.println( "E-I-E-I-O" );
      System.out.println( "And on that farm he had a " + animal );
      System.out.println( "E-I-E-I-O" );
      System.out.println( "With a " + noise + "-" + noise + " here") ;
      System.out.println( "And a " + noise + "-" + noise + " there" );
      System.out.println( "Here a " + noise + ", there a " + noise );
      System.out.println( "Everywhere a " + noise + "-" + noise );
      System.out.println( "Old MacDonald had a farm" );
      System.out.println( "E-I-E-I-O" );
    }

    public static void main(String[] args) 
    {
      verse( "cow" , "moo" );
      verse( "duck" , "quack" );
      //add a few more verses
      

      //print the counter value


    }
  }


Summary
-------

- Static methods and variables include the keyword static  before their name in the header or declaration. They can be public or private.

- Static variables belong to the class, with all objects of a class sharing a single static variable.

- Static methods are associated with the class, not objects of the class.

- Static variables are used with the class name and the dot operator, since they are associated with a class, not objects of a class.

- Static methods cannot access or change the values of instance variables, but they can access or change the values of static variables.

- Static methods cannot call non-static methods.
