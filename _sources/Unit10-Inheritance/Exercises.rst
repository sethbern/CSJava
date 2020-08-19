.. qnum::
   :prefix: 10-11-
   :start: 1			
   
Multiple-Choice Exercises
=========================

Easier Multiple Choice Questions
----------------------------------



.. mchoice:: qooe_1
   :practice: T
   :answer_a: Initialize the fields in the object.
   :answer_b: Determines the amount of space needed for an object and creates the object.
   :answer_c: Names the new object.
   :correct: a
   :feedback_a: A constructor is often used to initialize the fields to their default values or in the case of a parameterized constructor, to the values passed in to the constructor.
   :feedback_b: The object is already created before the constructor is called.
   :feedback_c: Constructors do not name the object.

   What best describes the purpose of a class's constructor?

.. mchoice:: qooe_2
   :practice: T
   :answer_a: The methods do different things.
   :answer_b: The methods have different parameter names.
   :answer_c: The methods have different post-conditions.
   :answer_d: Two methods with the same name can never be included in the same class.
   :answer_e: The methods have different numbers of parameters
   :correct: e
   :feedback_a: Methods that do different things should be named differently.
   :feedback_b: There is no reason the parameter names ought to be different if the two methods are performing the same action.
   :feedback_c: If the methods have different post-conditions, they are performing different functions, and should be named differently.
   :feedback_d: If two methods perform the same function, they can be named the same.  However, the number of parameters, type of parameters, or order of parameter types must be different.
   :feedback_e: Overloading occurs when two methods perform the same essential operation, but take a different number and/or type of parameters.

   Under which of these conditions is it appropriate to overload a method (ie: the class will contain two methods with the same name)?

.. .. mchoice:: qooe_3
   :practice: T
   :answer_a: I and II only
   :answer_b: II only
   :answer_c: I, II and III
   :answer_d: I only
   :answer_e: III only
   :correct: b
   :feedback_a: An abstract class can have constructors. A class with an abstract method must also be declared as abstract.
   :feedback_b: A class with an abstract method must also be declared abstract. You can have constructors and fields in an abstract class.
   :feedback_c: A class with an abstract method must also be abstract. You can have constructors and fields in an abstract class.
   :feedback_d: Only II is true. You can have constructors in an abstract class. A class with an abstract method must also be declared abstract.
   :feedback_e: Only II is true. You can have fields in an abstract class. A class with an abstract method must also be declared abstract.

   Which of the following statements about a class that contains an abstract method is (are) true?

   .. code-block:: java

      I. You can't have any constructors in this class.
      II.  This class must be declared as abstract.
      III.  You can't declare any fields in this class.

.. .. mchoice:: qooe_4
   :practice: T
   :answer_a: Abstract classes cannot be instantiated, but they can be sub-classed.
   :answer_b: Abstract classes can be instantiated, but they cannot be sub-classed.
   :answer_c: Abstract classes can only contain abstract methods.  They can be sub-classed.
   :answer_d: Abstract classes can only contain abstract methods.  They cannot be sub-classed.
   :correct: a
   :feedback_a: Sub-classes must implement the abstract methods declared in the abstract class or also be declared abstract.
   :feedback_b: You can not create an object of an abstract class type.  You can only create objects from concrete (not abstract) classes.
   :feedback_c: Abstract classes can contain fields and non-abstract methods.
   :feedback_d: Abstract classes can contain fields and non-abstract methods.  They can also be sub-classed.

   Which of the following is true about abstract classes?

.. mchoice:: qooe_5
   :practice: T
   :answer_a: Use four unrelated classes: <code>Car</code>, <code>Doors</code>, <code>AirConditioning</code>, and <code>MilesPerGallon</code>.
   :answer_b: Use a class <code>Car</code> with three subclasses: <code>Doors</code>, <code>AirConditioning</code>, and <code>MilesPerGallon</code>.
   :answer_c: Use a class <code>Car</code>, with fields: <code>numDoors</code>, <code>hasAir</code>, and <code>milesPerGallon</code>.
   :answer_d: Use a class <code>Car</code>, with subclasses of <code>Doors</code>, <code>AirConditioning</code>, and <code>MilesPerGallon</code>.
   :answer_e: Use classes: <code>Doors</code>, <code>AirConditioning</code>, and <code>MilesPerGallon</code>, each with a subclass <code>Car</code>.
   :correct: c
   :feedback_a: Only <code>Car</code> should be a class. The number of doors, flag if it has air conditioning, and the average number of miles per gallon are attributes of a car so they belong in a <code>Car</code> class.
   :feedback_b: Doors, air conditioning, and miles per gallon are not a kind of car. Child classes need to be able to be substituted for the parent class.
   :feedback_c: The number of doors, flag if it has air conditioning, and the average number of miles per gallon are attributes of a car. Each of these is a simple value so they can just be fields of a <code>Car</code> class.
   :feedback_d: A door is not a type of car. A flag for air conditioning is not a type of door, and a miles per gallon is not a type of air conditioning flag. Child classes need to be able to be substituted for the parent class.
   :feedback_e: A class <code>Car</code> can't be a subclass of three different classes. Each class can only have one parent class. Also a car is not a type of door, air conditioning flag, or miles per gallon. Child classes need to be able to be substituted for the parent class.

    A car dealership needs a program to store information about the cars for sale. For each car, they want to keep track of the following information: number of doors (2 or 4), whether the car has air conditioning, and its average number of miles per gallon. Which of the following is the best design?

.. mchoice:: qooe_6
   :practice: T
   :answer_a: How the methods are implemented.
   :answer_b: The method names.
   :answer_c: The method return types.
   :answer_d: Constants
   :answer_e: The number and types of the method parameters.
   :correct: a
   :feedback_a: Only the programmer of the <code>Employee</code> class must know how the public methods work. The programmer that is using the <code>Employee</code> class can just use the public methods and not worry about how they are implemented.
   :feedback_b: The programmer who writes the methods will need to know what the names are. The programmer who will use the public methods will also need to know the names of the methods in order to invoke them.
   :feedback_c: In order to use the public methods of the <code>Employee</code> class, a programmer must know the method return types.
   :feedback_d: Constants are public fields and are meant to be used by people using a class.
   :feedback_e: In order to use the public methods of the <code>Employee</code> class, a programmer must know the number of parameters and the type for each parameter.

    A program is being written by a team of programmers. One programmer is implementing a class called ``Employee``; another programmer is writing code that will use the ``Employee`` class. Which of the following aspects of the public methods and fields of the ``Employee`` class does not need to be known by both programmers?

.. mchoice:: qooe_7
   :practice: T
   :answer_a: Create one class <code>PublishedMaterial</code> with the requested fields plus type.
   :answer_b: Create classes <code>Book</code>, <code>Movie</code>, and <code>AudioTape</code> with the requested fields.
   :answer_c: Create one class <code>BookStore</code> with the requested fields plus type.
   :answer_d: Create classes for each.
   :answer_e: Create the class <code>PublishedMaterial</code> with children classes of <code>Book</code>, <code>Movie</code>, and <code>AudioTape</code>.
   :correct: e
   :feedback_a: This will complicate the process of retrieving objects based on their type. Also if we need to add information that is specific to <code>Book</code> or <code>Movie</code> or <code>AudioTape</code> it would be best if these were subclasses of <code>PublishedMaterial</code>.
   :feedback_b: This involves writing more code than is necessary (usually people copy and paste the shared code) and makes it harder to fix errors. It would be better to put common fields and methods in the superclass <code>PublishedMaterial</code> and have <code>Book</code>, <code>Movie</code>, and <code>AudioTape</code> be subclasses.
   :feedback_c: The class name, <code>BookStore</code>, seems to imply the thing that keeps track of the store. This would be an appropriate class name for an object that handles the items in the <code>Bookstore</code>. However, for the published material, it would be better to use a superclass <code>PublishedMaterial</code> and subclasses for <code>Book</code>, <code>Movie</code> and <code>AudioTape</code>.
   :feedback_d: This is more classes than is necessary. Items such as <code>Title</code>, <code>Price</code>, <code>ID</code>, <code>Author</code> and <code>DatePublished</code> are simple variables that do not need a class of their own but should be fields in a <code>PublishedMaterial</code> superclass, with <code>Movie</code>, <code>AudioTape</code> and <code>Book</code> as subclasses.
   :feedback_e: We will need to get objects based on their type so we should create classes for <code>Book</code>, <code>Movie</code>, and <code>AudioTape</code>. They have common fields so we should put these in a common superclass <code>PublishedMaterial</code>.

   A bookstore is working on an on-line ordering system. For each type of published material (books, movies, audio tapes) they need to track the id, title, author(s), date published, and price. Which of the following would be the best design?

Medium Multiple Choice Questions
----------------------------------

           
.. mchoice:: qoom_1
   :practice: T
   :answer_a: Won't compile since <code>GradStudent</code> doesn't have a <code>getInfo</code> method
   :answer_b: Taco
   :answer_c: Pizza
   :answer_d: Won't compile since you are creating a <code>GradStudent</code>, not a <code>Student</code>
   :answer_e: Won't compile since you use <code>this.getFood()</code>
   :correct: b
   :feedback_a: <code>GradStudent</code> will inherit the <code>getInfo</code> method from <code>Student</code>. This would be true if <code>getInfo</code> was a private method.
   :feedback_b: Objects know what class they are created as and all methods are resolved starting with that class at run time. If the method isn't found in that class the parent class is checked (and so on until it is found). So it will first look for <code>getInfo</code> in <code>GradStudent</code> and when it doesn't find it it will look in <code>Student</code>. In <code>getInfo</code> it calls <code>this.getFood</code>. Again, it will first look for this method in <code>GradStudent</code>. It will find the <code>getFood</code> method there and return "Taco".
   :feedback_c: This would be true if it was <code>Student s1 = new Student();</code>
   :feedback_d: An object of a subclass can be substituted for a parent class object. A <code>GradStudent</code> is a <code>Student</code>.
   :feedback_e: In object methods if you leave off the <code>this.</code> when invoking an object method it will be added for you by the compiler. The keyword <code>this</code> refers to the current object which is implicitly passed to all object methods.  

   Given the following class declarations, what is the output from ``Student s1 = new GradStudent();`` followed by ``s1.getInfo();``?
   
   .. code-block:: java 

      public class Student {
         public String getFood() {
            return "Pizza";
         }
         public String getInfo()  { 
            return this.getFood(); 
         }
      }

      public class GradStudent extends Student {
         public String getFood() {
            return "Taco";
         }
      }
      
.. mchoice:: qoom_2
   :practice: T
   :answer_a: I only
   :answer_b: II only
   :answer_c: I and II only
   :answer_d: II and III only
   :answer_e: I, II, and III
   :correct: d
   :feedback_a: I is wrong because <code>y</code> is a private field and thus can not be directly accessed from code in a client class.
   :feedback_b: I is wrong because <code>y</code>  is a private field and thus can not be directly accessed from code in a client class. II is correct because <code>EnhancedItem</code> has <code>setY</code> as a public method. III is correct because <code>EnhancedItem</code> inherits the public method <code>setX</code> from <code>Item</code>.
   :feedback_c: I is wrong because <code>y</code>  is a private field and thus can not be directly accessed from code in a client class.
   :feedback_d: I is wrong because <code>y</code>  is a private field and thus can not be directly accessed from code in a client class.  II is correct because <code>EnhancedItem</code> has <code>setY</code> as a public method.  III is correct because <code>EnhancedItem</code> inherits the public method <code>setX</code> from <code>Item</code>.
   :feedback_e: I is wrong because <code>y</code>  is a private field and thus can not be directly accessed from code in a client class.

   Given the following class declarations, and ``EnhancedItem enItemObj = new EnhancedItem();`` in a client class, which of the following statements would compile?
   
   .. code-block:: java 

      public class Item
      {
         private int x;

         public void setX(int theX)
         {
            x = theX;
         }
         // ... other methods not shown
      }

      public class EnhancedItem extends Item
      {
         private int y;

         public void setY(int theY)
         {
            y = theY;
         }

        // ... other methods not shown
      }

      I. enItemObj.y = 32;
      II. enItemObj.setY(32);
      III. enItemObj.setX(52);
      
.. mchoice:: qoom_3
   :practice: T
   :answer_a: t1.method1(t1,t1);
   :answer_b: t2.method1(t2,t2);
   :answer_c: t3.method1(t1,t1);
   :answer_d: t2.method1(t3,t2);
   :answer_e: t3.method1(t3,t3);
   :correct: e
   :feedback_a: You can't pass an object of class <code>Test1</code> since it is not either an object of type <code>Test2</code> or an object of type <code>Test3</code>. You can pass the specified type or an object that is a subclass of the specified type but <code>Test1</code> is not a subclass of <code>Test2</code> or <code>Test3</code>.
   :feedback_b: You can't pass an object of class <code>Test2</code> as a parameter of type <code>Test3</code>. <code>Test2</code> is the parent class of <code>Test3</code> not a subclass. You can pass an object of the specified type or an object of any subclass.
   :feedback_c: You can't pass an object of class <code>Test1</code> since it is not either an object of type <code>Test2</code> or an object of type <code>Test3</code>. You can pass the specified type or an object that is a subclass of the specified type but <code>Test1</code> is not a subclass of <code>Test2</code> or <code>Test3</code>.
   :feedback_d: You can't pass <code>t2</code> as an object of type <code>Test3</code> since it is an object of class <code>Test2</code> and class <code>Test2</code> is not either class <code>Test3</code> or a subclass of class <code>Test3</code>. Class <code>Test2</code> is the parent of class <code>Test3</code>.
   :feedback_e: Since <code>method1</code> is a public method of class <code>Test1</code> objects of any subclasses of <code>Test1</code> can invoke the method. So, it can be invoked on <code>t3</code> since it is an object of <code>Test3</code> and this is a subclass of <code>Test1</code>.  And, since <code>method1</code> takes an object of class <code>Test2</code> and <code>Test3</code> as parameters. This actually means it can take an object of <code>Test2</code> or any subclass of <code>Test2</code> and an object of <code>Test3</code> or any subclass of <code>Test3</code>. So it can take <code>t3</code> which is an object of class <code>Test3</code> as an object of <code>Test2</code> since <code>Test3</code> is a subclass of <code>Test2</code>.

   Given the following class declarations and initializations in a client program, which of the following is a correct call to ``method1``?
   
   .. code-block:: java 

      public class Test1
      {
         public void method1(Test2 v1, Test3 v2)
         {
            // rest of method not shown
         }
      }

      public class Test2 extends Test1
      {
      }

      public class Test3 extends Test2
      {
      }
      
      The following initializations appear in a different class.
      Test1 t1 = new Test1();
      Test2 t2 = new Test2();
      Test3 t3 = new Test3();
      
.. mchoice:: qoom_4
   :practice: T
   :answer_a: Meow Moo Woof Awk Awk
   :answer_b: Awk Awk Awk Awk Awk
   :answer_c: This will not compile
   :answer_d: This will have runtime errors
   :answer_e: Meow Moo Woof Oink Awk
   :correct: a
   :feedback_a: Objects keep a reference to the class that created them. So, even if you put them in an array of <code>Animal</code> objects, they know what they are and all methods are resolved starting with the class of the object. <code>Bird</code> and <code>Pig</code> do not override speak so the <code>speak</code> method in <code>Animal</code> will execute.
   :feedback_b: Methods are always resolved starting with the class of the object, so <code>Cat</code>, <code>Cow</code>, and <code>Dog</code> will all execute their overridden <code>speak</code> methods, so the output will be: Meow Moo Woof Awk Awk.
   :feedback_c: Because <code>Bird</code>, <code>Cow</code>, <code>Cat</code>, <code>Dog</code>, and <code>Pig</code> are subclasses of <code>Animal</code>, they can be stored in an array declared as <code>Animal</code> without any compile time errors.
   :feedback_d: Because <code>Bird</code>, <code>Cow</code>, <code>Cat</code>, <code>Dog</code>, and <code>Pig</code> are subclasses of <code>Animal</code>, they can be stored in an array declared as <code>Animal</code> without any runtime errors.
   :feedback_e: The <code>Pig</code> class did not override the <code>speak</code> method, so it will use the method from <code>Animal</code>, thus the output should be: Meow Moo Woof Awk Awk

    If you have a parent class ``Animal`` that has a method ``speak()`` which returns: Awk. ``Cat`` has a ``speak`` method that returns: Meow.  ``Bird`` does not have a ``speak`` method.  ``Dog`` has a ``speak`` method that returns: Woof.  ``Pig`` does not have a ``speak`` method.  ``Cow`` has a ``speak`` method that returns: Moo.   What is the output from looping through the array ``a`` created below and asking each element to ``speak()``? 
	
    .. code-block:: java 
	  
	  Animal[] a = { new Cat(), new Cow(), new Dog(), new Pig(), new Bird() }
	  
.. mchoice:: qoom_5
   :practice: T
   :answer_a: The code compiles and runs with no errors, the output is 5 6 5 6
   :answer_b: The code compiles and runs with no errors, the output is: 5 6 10 11
   :answer_c: The code compiles and runs with no errors, the output is 10 11 10 11
   :answer_d: The code won't compile.
   :answer_e: You get a runtime error <code>ClassCastException</code>, when <code>fastCar.addFuel()</code> is executed.
   :correct: b
   :feedback_a: <code>RaceCar</code>, while it inherits methods from <code>Car</code> via inheritance, has a separate and different constructor that sets the initial fuel amount to <code>2 * g</code>, thus in this case, <code>fuel</code> for <code>fastCar</code> is set to <code>10</code> initially.
   :feedback_b: The code compiles correctly, and because <code>RaceCar</code> extends the <code>Car</code> class, all the public methods of <code>Car</code> can be used by <code>RaceCar</code> objects. Also, a variable <code>Car</code> can refer to a <code>Car</code> object or an object of any subclass of <code>Car</code>. An object always knows the class that created it, so even though <code>fastCar</code> is declared to be a <code>Car</code> the constructor that is executed is the one for <code>RaceCar</code>.
   :feedback_c: The variable <code>car</code> is a <code>Car</code> object, so the constructor used is not the same as the <code>fastCar</code> object which is a <code>RaceCar</code>. The <code>car</code> constructor does not change the passed in parameter, so it is set to <code>5</code> initially.
   :feedback_d: <code>RaceCar</code> inherits from the <code>Car</code> class so all the public methods in <code>Car</code> can be accessed by any object of the <code>RaceCar</code> class.
   :feedback_e: <code>RaceCar</code> inherits from the <code>Car</code> class so all the public methods in <code>Car</code> can be accessed by any object of the <code>RaceCar</code> class.

   Given the following class declarations and code, what is the result when the code is run?
   
   .. code-block:: java 

      public class Car
      {
         private int fuel;

         public Car() { fuel = 0; } 
         public Car(int g) { fuel = g; }

         public void addFuel() { fuel++; }
         public void display() { System.out.print(fuel + " "); }
      }

      public class RaceCar extends Car
      {
         public RaceCar(int g) { super(2*g); }
      }
      
      What is the result when the following code is compiled and run?

      Car car = new Car(5);
      Car fastCar = new RaceCar(5);
      car.display()
      car.addFuel();
      car.display();
      fastCar.display();
      fastCar.addFuel();
      fastCar.display();
      
.. mchoice:: qoom_6
   :practice: T
   :answer_a: I only
   :answer_b: II only
   :answer_c: I and III only
   :answer_d: III only
   :answer_e: I, II, and III
   :correct: c
   :feedback_a: Both I and III are correct. I is correct because variable <code>b</code> has been declared to be an object of the class <code>Book</code> so you can invoke any public methods that are defined in the <code>Book</code> class or in parents of <code>Book</code>. II is not correct because you can't invoke methods in the <code>Dictionary</code> class directly on <code>b</code> since <code>b</code> is declared to be of type <code>Book</code> not type <code>Dictionary</code> and <code>Dictionary</code> is a subclass of <code>Book</code> not a parent class of <code>Book</code>. III is correct because you can cast <code>b</code> to type <code>Dictionary</code> and then invoke public methods in <code>Dictionary</code>.
   :feedback_b: You can't invoke methods in the <code>Dictionary</code> class directly on <code>b</code> since <code>b</code> is declared to be of type <code>Book</code> not type <code>Dictionary</code> and <code>Dictionary</code> is a subclass of <code>Book</code> not a parent class of <code>Book</code>. The compiler checks that the method exists on the declared class type, not the run-time type of the object.
   :feedback_c: I is correct because variable <code>b</code> has been declared to be an object of the class <code>Book</code> so you can invoke any public methods that are defined in the <code>Book</code> class or in parents of <code>Book</code>. II is not correct because you can't invoke methods in the <code>Dictionary</code> class directly on <code>b</code> since <code>b</code> is declared to be of type <code>Book</code> not type <code>Dictionary</code> and <code>Dictionary</code> is a subclass of <code>Book</code> not a parent class of <code>Book</code>. III is correct because you can cast <code>b</code> to type <code>Dictionary</code> and then invoke public methods in <code>Dictionary</code>.
   :feedback_d: I is also correct.
   :feedback_e: You can't invoke methods in the <code>Dictionary</code> class directly on <code>b</code> since <code>b</code> is declared to be of type <code>Book</code> not type <code>Dictionary</code> and <code>Dictionary</code> is a subclass of <code>Book</code> not a parent class of <code>Book</code>. The compiler checks that the method exists on the declared class, not the run-time class.

   Given the following class declarations and code, what is the result when the code is run?
   
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
         public String getDefinition(String word)
         {
            // implementation not shown
         }
 
         // constructors, fields, and methods not shown
      }
      
      Assume that the following declaration appears in a client class.
      
      Book b = new Dictionary();
      
      Which of the following statements would compile without error?
      I.  b.getISBN();
      II. b.getDefinition("wonderful");
      III. ((Dictionary) b).getDefinition("wonderful");
      

.. mchoice:: qsh_3
   :practice: T
   :random:
   :answer_a: Lasagna Meow Screeech
   :answer_b: Meow Screeech Lasagna
   :answer_c: Screeech Meow Lasagna
   :answer_d: Lasagna Screeech Meow
   :correct: b
   :feedback_a: The baseclass constructor runs first so Animal doesn't have one so then it goes to Cat's constructor and then Garfield's constructor
   :feedback_b: The baseclass constructor runs first so Animal doesn't have one so then it goes to Cat's constructor and then Garfield's constructor
   :feedback_c: The baseclass constructor runs first so Animal doesn't have one so then it goes to Cat's constructor and then Garfield's constructor
   :feedback_d: The baseclass constructor runs first so Animal doesn't have one so then it goes to Cat's constructor and then Garfield's constructor

   What is the output of the following code?

   .. code-block:: java

    class Animal
    {
        void someSound()
        {
            System.out.print("Screeech ");
        }
    }

    class Cat extends Animal
    {
        public Cat()
        {
            System.out.print("Meow ");
            super.someSound();
        }
    }

    class Garfield extends Cat
    {
        public Garfield()
        {
            System.out.print("Lasagna ");
        }
    }
    public class MainClass
    {
        public static void main(String[] args)
        {
            Garfield garfield = new Garfield();
        }
    }
   
Hard Multiple Choice Questions
----------------------------------


.. mchoice:: qooh_1
   :practice: T
   :answer_a: ABDC
   :answer_b: AB
   :answer_c: ABCD
   :answer_d: ABC
   :correct: a
   :feedback_a: Even though b is declared as type <code>Base</code> it is created as an object of the <code>Derived</code> class, so all methods to it will be resolved starting with the <code>Derived</code> class. So the <code>methodOne()</code> in <code>Derived</code> will be called. This method first calls <code>super.methodOne</code> so this will invoke the method in the superclass (which is <code>Base</code>). So next the <code>methodOne</code> in <code>Base</code> will execute. This prints the letter "A" and invokes <code>this.methodTwo()</code>. Since <code>b</code> is really a <code>Derived</code> object, we check there first to see if it has a <code>methodTwo</code>. It does, so execution continues in the <code>Derived</code> class <code>methodTwo</code>. This method invokes <code>super.methodTwo</code>. So this will invoke the method in the super class (<code>Base</code>) named <code>methodTwo</code>. This method prints the letter "B" and then returns. Next the execution returns from the call to the <code>super.methodTwo</code> and prints the letter "D". We return to the <code>Base</code> class <code>methodOne</code> and return from that to the <code>Derived</code> class <code>methodOne</code> and print the letter "C". 
   :feedback_b: This would be true if the object was created of type <code>Base</code>. But the object is really a <code>Derived</code>  object. So all methods are looked for starting with the <code>Derived</code>  class.
   :feedback_c: After the call to <code>methodOne</code> in the super class printing "A", the code continues with the implicit <code>this.methodTwo</code> which resolves from the current object's class which is <code>Derived</code>. Next, <code>methodTwo</code> in the <code>Derived</code> class is executed which then calls <code>super.methodTwo</code> which invokes <code>println</code> "B" from <code>methodTwo</code> in the <code>Base</code> class. Then the "D" in the <code>Derived</code> <code>methodTwo</code> is printed. Finally the program returns to <code>methodOne</code> in the <code>Derived</code> class are prints "C".
   :feedback_d: The call to <code>methodTwo</code> in <code>super.methodOne</code> is to <code>this.methodTwo</code> which is the method from the <code>Derived</code> class. Consequently the "D" is also printed. 

   Assume that ``Base b = new Derived();`` appears in a client program.  What is the result of the call ``b.methodOne();``?
   
   .. code-block:: java 

      public class Base
      {
         public void methodOne()
         {
            System.out.print("A");
            methodTwo();
         }

         public void methodTwo()
         {
            System.out.print("B");
         }
      }

      public class Derived extends Base
      {
         public void methodOne()
         {
            super.methodOne();
            System.out.print("C");
         }

         public void methodTwo()
         {
            super.methodTwo();
            System.out.print("D");
         }
      }
      
.. mchoice:: qooh_2
   :practice: T
   :answer_a: II only
   :answer_b: III only
   :answer_c: I, II, and III
   :answer_d: I and II only
   :answer_e: I only
   :correct: c
   :feedback_a: <code>Point2D</code> does have a constructor that takes an <code>x</code> and <code>y</code> value so this is okay. Also the call to super is the first line of code in the child constructor as required. However, both I and III are okay as well.
   :feedback_b: The <code>x</code> and <code>y</code> values in <code>Point2D</code> are public and so can be directly accessed by all classes including subclasses. Also there is a no-arg constructor in <code>Point2D</code> so the super no-arg constructor will be called before the first line of code in this constructor.
   :feedback_c: I is true because <code>Point2D</code> does have a no-arg constructor. II is true because <code>Point2D</code> does have a constructor that takes <code>x</code> and <code>y</code>. III is true because <code>Point2D</code> does have a no-arg constructor which will be called before the first line of code is executed in this constructor. The fields <code>x</code> and <code>y</code> are public in <code>Point2D</code> and thus can be directly accessed by all classes.
   :feedback_d: This would be true if <code>x</code> and <code>y</code> were private in <code>Point2D</code>, but they are public.
   :feedback_e: <code>Point2D</code> does have a no-arg constructor and since the constructor in <code>Point3D</code> doesn't have an explicit call to super as the first line of code in the constructor one will be added for the no-arg constructor. However, both II and III are okay as well.  

   If you have the following classes.  Which of the following constructors would be valid for ``Point3D``?
   
   .. code-block:: java 
    
      public class Point2D {
         public int x;
         public int y;

         public Point2D() {}

         public Point2D(int x,int y) {
            this.x = x;
            this.y = y;
         }
        // other methods
      }

      public class Point3D extends Point2D
      {
         public int z;
   
         // other code
      }
      
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
           

