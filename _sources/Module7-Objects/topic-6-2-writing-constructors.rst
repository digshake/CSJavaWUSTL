.. qnum::
   :prefix: 6-2-
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

Writing Constructors
====================

..	index::
	pair: class; constructor
	
Objects are created in programs by declaring a variable of the class and using the keyword new followed by a call to a constructor. **Constructors**  set the initial values for the object's instance variables.    For example, here is how we create a Person object.  

.. code-block:: java 

    // To create a new object, write:
    // ClassName variableName = new ConstructorName(arguments);
    Person p = new Person("Pat","pat@gmail.com","123-456-7890");
    

In a new class, constructors are usually written after the instance variables and before any methods.    They typically start with ``public`` and then the *name* of the class: ``public ClassName()``. Unlike other methods, they do not have a return type, not even void, after the access modifier public.  They can take **parameters** (specified in parentheses) for the data which is used to initialize the instance variables. 

.. code-block:: java 

   public class ClassName {

      /* Instance Variable Declarations -- not shown */

      /* Constructor - same name as Class, no return type */
      public ClassName() {
        /* Implementation not shown */
      }
   }
    
.. note::

   Constructors must have the same name as the class! Constructors have no return type!
   
Classes usually have more than one constructor. There are usually at least 2 constructors:

- a constructor that takes no parameters  
- a constructor that takes all the parameters necessary for initializing all the instance variables 

The attributes of an object and their values at a given time define that object's state. The constructors initialize the object's state by assigning initial values to the instance variables that the object has as its attributes. 

Here are two constructors that could be written for the Person class. Notice that the first one initializes name, email, and phoneNumber to empty string "" as the default values. Most programmers use "" as the default value for String variables and 0 as the default value for int and double variables.

.. code-block:: java 

     // default constructor: initialize instance vars to default empty strings
     public Person() {
        name = "";
        email = "";
        phoneNumber = "";
     }

     // constructor: initialize all 3 instance variables to parameters
     public Person(String initName, String initEmail, String initPhone) {
        name = initName;
        email = initEmail;
        phoneNumber = initPhone;
     }

If there are no constructors written for a class, Java provides a no-argument **default constructor** where the instance variables are set to their default values. For int and double variables, the default value used is **0**, and for String and other object variables, the default is **null**. However, if you do write at least one constructor, Java will not generate the default constructor for you, so you should write at least a constructor with no parameters and one with many parameters.
 
   
|Exercise| **Check Your Understanding** 

     
.. clickablearea:: q6_2_1
    :question: Click on all the lines of code that are part of constructors in the following class.
    :iscode:
    :feedback: Constructors are public and have the same name as the class.  

    :click-incorrect:public class Name {:endclick:
    
        :click-incorrect:private String first;:endclick:
        :click-incorrect:private String last;:endclick:
        
        :click-correct:public Name(String theFirst, String theLast) {:endclick:
            :click-correct:first = theFirst;:endclick:
            :click-correct:last = theLast;:endclick:
         :click-correct:}:endclick:
         
         :click-incorrect:public void setFirst(String theFirst) {:endclick:
            :click-incorrect:first = theFirst;:endclick:
         :click-incorrect:}:endclick:
         
         :click-incorrect:public void setLast(String theLast) {:endclick:
            :click-incorrect:last = theLast;:endclick:
         :click-incorrect:}:endclick:
         
    :click-incorrect:}:endclick:  
    
.. mchoice:: q6_2_2
   :practice: T
   :answer_a: Determines the amount of space needed for an object and creates the object
   :answer_b: Names the new object
   :answer_c: Return to free storage all the memory used by this instance of the class.
   :answer_d: Initialize the instance variables in the object
   :correct: d
   :feedback_a: The object is already created before the constructor is called but the constructor initializes the instance variables.
   :feedback_b: Constructors do not name the object.  
   :feedback_c: Constructors do not free any memory. In Java the freeing of memory is done when the object is no longer referenced.
   :feedback_d: A constructor  initializes the instance variables to their default values or in the case of a parameterized constructor, to the values passed in to the constructor.
   
   What best describes the purpose of a class's constructor?
   


Practice
------------

.. mchoice:: q6_2_3
   :practice: T
   :answer_a: I only
   :answer_b: I and II
   :answer_c: I and III
   :answer_d: I, II, and III
   :answer_e: II and III
   :correct: c
   :feedback_a: I is one of the correct constructors but the second constructor can also be used.
   :feedback_b: II is not correct because there is no Cat constructor that takes 2 parameters.
   :feedback_c: I and III call the correct constructors.
   :feedback_d: II is not correct because there is no Cat constructor that takes 2 parameters.
   :feedback_e: II is not correct because there is no Cat constructor that takes 2 parameters.

    Consider the following class. Which of the following successfully creates a new Cat object?

    .. code-block:: java

        public class Cat {
            private String color;
            private String breed;
            private boolean isHungry;

            public Cat() {
                color = "unknown";
                breed = "unknown";
                isHungry = false;
            }

            public Cat(String c, String b, boolean h) {
                color = c;
                breed = b;
                isHungry = h;
            }
        }

        I.   Cat a = new Cat();
        II.  Cat b = new Cat("Shorthair", true);
        III. String color = "orange";
             boolean hungry = false;
             Cat c = new Cat(color, "Tabby", hungry);

.. mchoice:: q6_2_4
   :practice: T
   :answer_a: Movie m = new Movie(8.0, "Lion King");
   :answer_b: Movie m = Movie("Lion King", 8.0);
   :answer_c: Movie m = new Movie();
   :answer_d: Movie m = new Movie("Lion King", "Disney", 8.0);
   :answer_e: Movie m = new Movie("Lion King");
   :correct: d
   :feedback_a: There is no Movie constructor with 2 parameters.
   :feedback_b: There is no Movie constructor with 2 parameters.
   :feedback_c: This creates a Movie object but it does not have the correct title and rating.
   :feedback_d: This creates a Movie object with the correct title and rating.
   :feedback_e: This creates a Movie object but it does not have a rating of 8.0.

   Consider the following class.  Which of the following code segments will construct a Movie object m with a title of "Lion King" and rating of 8.0?

   .. code-block:: java

        public class Movie {
            private String title;
            private String director;
            private double rating;
            private boolean inTheaters;

            public Movie(String t, String d, double r) {
                title = t;
                director = d;
                rating = r;
                inTheaters = false;
            }

            public Movie(String t) {
                title = t;
                director = "unknown";
                rating = 0.0;
                inTheaters = false;
            }
        }






|CodingEx| **Coding Exercise**

  
The given ``Car`` class is already defined with the instance variables model and year, for example a Honda 2010 car. However, some of the code is missing. Fill in the code for the 2 constructors that are numbered 1 and 2. And fill in the code to call the constructors in the main method numbered 3. The car1 object should test the first constructor with default values and the car2 object should test the second constructor to create a Honda 2010 car. Run your program and make sure it works and prints out the information for both cars.
  


Constructors are used to set the initial state of an object by initializing its instance variables. The examples above have instance variables that are primitive types, but you can have other objects, reference types, as instance variables. For example, a Person class could have an Address object as an instance variable, and the Address class could have String instance variables for the street, city, and state. 

When you pass object references as parameters to constructors or methods, they become aliases for the original object and can change it. If a constructor has an object instance variable, it can copy   the referenced object in the parameter using new and the constructor of the referenced object like below so that it does not change the state of the original object. You will see more examples like this in later lessons.

.. code-block:: java 

     public class Person {
       private String name;
       private Address addr; //Assumes an Address class is already defined
       
       // constructor: initialize instance variable and call Address constructor to make a copy
       public Person(String initName, Address initAddr) {
          name = initName;
          addr = new Address(initAddr.getStreet(), 
                     initAddr.getCity(), initAddr.getState());
       }
      }
     


Practice
------------



.. mchoice:: q6_2_5
    :practice: T

    Consider the definition of the Cat class below. The class uses the instance variable isSenior to indicate whether a cat is old enough to be considered a senior cat or not.
        
    .. code-block:: java

        public class Cat {
            private String name;
            private int age;
            private boolean isSenior;
            public Cat(String n, int a) {
                name = n;
                age = a;
                if (age >= 10) {
                    isSenior = true;
                } else {
                    isSenior = false;
                }
            }
        }

    Which of the following statements will create a Cat object that represents a cat that is considered a senior cat?
    
    - Cat c = new Cat ("Oliver", 7);

      - The age 7 is less than 10, so this cat would not be considered a senior cat.
      
    - Cat c = new Cat ("Max", "15");

      - An integer should be passed in as the second parameter, not a string.
      
    - Cat c = new Cat ("Spots", true);

      - An integer should be passed in as the second parameter, not a boolean.
      
    - Cat c = new Cat ("Whiskers", 10);

      + Correct!
        
    - Cat c = new Cat ("Bella", isSenior);

      - An integer should be passed in as the second parameter and isSenior would be undefined outside of the class.




.. mchoice:: q6_2_6
   :practice: T
   :answer_a: I only
   :answer_b: II only
   :answer_c: III only
   :answer_d: I and III only
   :answer_e: I, II and III
   :correct: d
   :feedback_a: Option III can also create a correct Cat instance.
   :feedback_b: Option II will create a cat that is 0 years old with 5 kittens.
   :feedback_c: Option I can also create a correct Cat instance.
   :feedback_d: Good job!
   :feedback_e: Option II will create a cat that is 0 years old with 5 kittens.

   Consider the following class definition. Each object of the class Cat will store the cat’s name as name, the cat’s age as age, and the number of kittens the cat has as kittens. Which of the following code segments, found in a class other than Cat, can be used to create a cat that is 5 years old with no kittens?
   
   .. code-block:: java

    public class Cat {
        private String name;
        private int age;
        private int kittens;

        public Cat(String n, int a, int k) {
            name = n;
            age = a;
            kittens = k;
        }
        public Cat(String n, int a) {
            name = n;
            age = a;
            kittens = 0;
        }
        /* Other methods not shown */
    }

    I.   Cat c = new Cat("Sprinkles", 5, 0);
    II.  Cat c = new Cat("Lucy", 0, 5);
    III. Cat c = new Cat("Luna", 5);
    
.. mchoice:: q6_2_7
    :practice: T

    Consider the following class definition.
        
    .. code-block:: java

        public class Cat {
            private String color;
            private boolean isHungry;
            /* missing constructor */
        }

    The following statement appears in a method in a class other than Cat. It is intended to create a new Cat object c with its attributes set to "black" and true. Which of the following can be used to replace  **missing constructor code** in the class definition so that the object c below is correctly created?
    
    .. code-block:: java
  
        Cat c = new Cat("black", true);
        
    - .. code-block:: java
    
        public Cat(String c, boolean h) {
            c = "black";
            h = true;
        }

      - The constructor should be changing the instance variables, not the local variables.

    - .. code-block:: java
    
        public Cat(String c, boolean h) {
            c = "black";
            h = "true";
        }

      - The constructor should be changing the instance variables, not the local variables.

    - .. code-block:: java
    
        public Cat(String c, boolean h) {
            c = color;
            h = isHungry;
        }

      - The constructor should be changing the instance variables, not the local variables.

    - .. code-block:: java
    
        public Cat(String c, boolean h) {
            color = black;
            isHungry = true;
        }

      - The constructor should be using  the local variables to set the instance variables.

    - .. code-block:: java
    
        public Cat(String c, boolean h) {
            color = c;
            isHungry = h;
        }

      + Correct!

Summary
--------


- **Constructors** are used to set the initial state of an object, which includes initial values for all instance variables.

- When no constructor is written, Java provides a no-argument **default constructor**, and the instance variables are set to their default values (0 for int and double, null for objects like String).

- Constructor parameters are local variables to the constructor and provide data to initialize instance variables.
