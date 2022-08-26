.. qnum::
   :prefix: 6-6-
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

..	index::
	single: method 
    single: return
    single: parameter
    single: argument
    single: abstraction
    pair: method; parameter
    pair: method; argument
    pair: method; return 
    
Writing Instance Methods
=========================

In Unit 5 you saw how to write **static methods**.  A static method is also referred to as a **class method**, and it is called
without an object.  Because of this, static methods can't access y attributes (instance variables) or other non-static methods without first
creating an object.

Non-static methods, which we will refer to  as **instance methods** or **object methods**
are called using an object and therefore have access to an object's instance variables.
Note the method header will not include the keyword static.  


There are three steps to creating and calling an instance method:

1. **Object of the Class**: Declare an object of your class in the main method or from outside the class.

    .. code-block:: java

       // Step 1: declare an object in main or from outside the class
       Classname objectName = new Classname(); 


2. **Method Definition**:  write the method's **header** and **body** code like below: 

    .. code-block:: java

        // Step 3: Define the method in the class
        // method header
        public void methodName() 
        { 
              // method body for the code
        }


3. **Method Call**: whenever you want to use the method, call objectName.methodName(); 

    .. code-block:: java

       // Step 2: call the object's method
       objectName.methodName(); //Step 2


How is this different than calling a static method?  Notice the object reference and dot notation before the method name.
Since the method may set and get instance variables, you must call the method on an actual instance of the class.



Practice
-----------

.. mchoice:: q6_6_1
    :practice: T

    Consider the following class, which uses the instance variable dollars to represent the money in a wallet in dollars.
        
    .. code-block:: java

        public class Wallet
        {
            private double dollars;

            public double putMoneyInWallet(int amount)
            {
                /* missing code */
            }
        }

    The putMoneyInWallet method is intended to increase the dollars in the wallet by the parameter amount and then return the updated dollars in the wallet. Which of the following code segments should replace  *missing code* so that the putMoneyInWallet method will work as intended?
    
    - .. code-block:: java

        amount += dollars;
        return dollars;

      - dollars should be incremented by amount.
        
    - .. code-block:: java

        dollars = amount;
        return amount;
        
      - dollars should be incremented by amount.
        
    - .. code-block:: java

        dollars += amount;
        return dollars;
        
      + Correct.

    - .. code-block:: java

        dollars = dollars + amount;
        return amount;
       
      - amount is returned instead of dollars.
        
    - .. code-block:: java

        amount = dollars + amount;
        return dollars;
        
      - dollars should be incremented by amount.
        


.. mchoice:: q6_6_2
    :practice: T

    Consider the Liquid class below.
    
    .. code-block:: java

        public class Liquid
        {
            private int currentTemp;
            private int boilingPoint;

            public Liquid(int ct, int bp)
            {
                currentTemp = ct;
                boilingPoint = bp;
            }

            public boolean isBoiling(int amount)
            {
                /* missing code */
            }
        }

    The isBoiling method is intended to return true if increasing the currentTemp by the parameter amount is greater than or equal to the boilingPoint, or otherwise return false. Which of the following code segments can replace *missing code* to ensure that the isBoiling method works as intended? 
    
    .. code-block:: java

       I.   if (currentTemp + amount < boilingPoint)
            {
                return false;
            }
            else
            {
                return true;
            }
       II.  if (amount > currentTemp)
            {
                return false;
            }
            else
            {
                return currentTemp;
            }
       III. if (amount + currentTemp >= boilingPoint)
            {
                return true;
            }
            else
            {
                return false;
            }

    - I only
          
      - I would work but it is not the only code that would work.

    - II only
    
      - II does not check against the boilingPoint and does not return only boolean values.
  
    - III only
    
      - III would work but it is not the only code that would work.

    - I and III only.
  
      + Correct! 
      
    - I, II, III
    
      - II does not check against the boilingPoint and does not return only boolean values.

Summary
--------

- **Procedural Abstraction** (creating methods) reduces the complexity and repetition of code. We can name a block of code as a method and call it whenever we need it, abstracting away the details of how it works.  

- A programmer breaks down a large problem into smaller subproblems by creating methods to solve each individual subproblem.

- To write methods, write a **method definition** with a **method signature** like "public void chorus()" and a **method body** in {} and method calls using an object.the method name and arguments whenever you need it to do its job.

- To call an object's method, you must use the object name and the dot (.) operator followed by the method name, for example **object.method();** 


- When you call a method, you can give or pass in **arguments** or **actual parameters** to it inside the parentheses **object.method(arguments)**. The arguments are saved in local **formal parameter** variables that are declared in the method header, for example: public void method(type param1, type param2) { ... }.

- Values provided in the arguments in a method call need to correspond to the order and type of the parameters in the method signature.

- When an actual parameter is a primitive value, the formal parameter is initialized with a copy of that value. Changes to the formal parameter have no effect on the corresponding actual parameter.

- When an actual parameter is a reference to an object, the formal parameter is initialized with a copy of that reference, not a copy of the object. The formal parameter and the actual parameter are then aliases, both refering to the same object.

-  When an actual parameter is a reference to an object, the method or constructor could use this reference to alter the state of the original object. However, it is good programming practice to not modify mutable objects that are passed as parameters unless required in the specification.
