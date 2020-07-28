.. qnum::
   :prefix: 5-2-
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
 
    
Method Parameters
=================

Consider two verses in the "Old MacDonald" song:

.. table:: 
  :align: left
  :widths: auto

  ===================================  ==================================  
             Verse 1                             Verse 2                
  ===================================  ==================================
   Old MacDonald had a farm            Old MacDonald had a farm          
   E-I-E-I-O                           E-I-E-I-O                        
   And on that farm he had a cow       And on that farm he had a duck   
   E-I-E-I-O                           E-I-E-I-O                        
   With a moo-moo here                 With a quack-quack here          
   And a moo-moo there                 And a quack-quack there          
   Here a moo, there a moo             Here a quack, there a quack      
   Everywhere a moo-moo                Everywhere a quack-quack         
   Old MacDonald had a farm            Old MacDonald had a farm         
   E-I-E-I-O                           E-I-E-I-O                        
  ===================================  ==================================

    
Each verse is identical, except for the animal (cow vs duck) and the noise (moo vs quack).
We can create a method named **verse** to abstract the repetitive lines, 
but the method will need two **formal parameters**, which are placeholders that allow 
different values to be substituted for the animal and noise when the method is called. 
The method body will use the formal parameter variables to customize the 
print statements. When you call the method, you provide values between the parentheses, called **actual arguments** or **actual parameters**, that are 
copied into the formal parameter variables. 

Figure 1 shows the new **verse** method with two formal parameters for **animal** and **noise**. The print statements
in the method body use the parameters to customize the output.  The figure
depicts how actual argument values in the method call ``verse("cow","moo");`` are copied 
into the formal parameter variables.

.. figure:: Figures/argumentpassingcow.png
  :width: 500px
  :align: center
  :alt: Actual Argument Values Passed Into Formal Parameters
  :figclass: align-center
  
  Figure 1: Method Call Passes Actual Argument Values Into Formal Parameter Variables

.. activecode:: SongFarm
  :language: java
  :autograde: unittest
  :practice: T
    
  Use the CodeLens button or copy the code into the |visualizer| to watch how the main method
  passes actual argument values into each call to the verse method.
  Update the main method to add a third verse to the song with another animal and noise.
  Rerun the program to confirm the third verse correctly prints.
  ~~~~
  public class Song 
  { 
  
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
    }
  }
  ====
  import static org.junit.Assert.*;
  import org.junit.*;;
  import java.io.*;

  public class RunestoneTests extends CodeTestHelper
  {
    
    public RunestoneTests() {
      super("Song");
    }

    @Test
    public void test1()
    {
      String code = getCode();
      int numVerses = countOccurences(code, "verse(");
      boolean passed = numVerses >= 3;
      passed = getResults("3 verses", numVerses + " verses", "Update the main with a third verse call", passed);
      assertTrue(passed);
    }
  }

A method allows us to write blocks of code that perform a task, 
which can be generalised by having formal parameter variables.  We define a method to give the block of 
code a reusable name.
The parameters allow the code to adapt to a variety of different situations, 
depending on the values passed into the method.


The code below calculates and prints the weekly pay for two employees.
Notice that some lines of code are similar but differ by value, while other lines of code are identical.
  
 .. code-block:: java
 
  public class PayrollCalculator
  { 
  
    public static void main(String[] args) {

      double hourlyRate, hoursWorked, weeklyPay;
      String employee;

      //Calculate weekly pay for Fred
      employee = "Fred";
      hourlyRate = 12.50;
      hoursWorked = 20;
      weeklyPay = hourlyRate * hoursWorked;
      System.out.println(employee  + ":" + weeklyPay);
      
      //Calculate weekly pay for Amir 
      employee = "Amir";
      hourlyRate = 15.0;
      hoursWorked = 35;
      weeklyPay = hourlyRate * hoursWorked;
      System.out.println(employee  + ":" + weeklyPay);

    }

  }


The table below compares the code for each employee side by side.  Notice the first three lines of code 
are the same except for
the value in the right hand side of each assignment, while the last two lines of code
that calculate and print the weekly pay are identical.  
We can eliminate code redundancy by adding a new method named ``calculatePay``. 
The   method needs 3 formal parameters to allow
values to be passed into the method: employee, hourlyRate, and hoursWorked.  
The method body will use the formal
parameters to compute and print the weekly pay.

.. table:: 
  :align: left
  :widths: auto

  ================================================   =================================================
  Calculate pay for first employee                   Calculate pay for second employee                 
  ================================================   =================================================
  employee = "Fred";                                 employee = "Amir";
  hourlyRate = 12.50;                                hourlyRate = 15.0;
  hoursWorked = 20;                                  hoursWorked = 35;
  weeklyPay = hourlyRate * hoursWorked;              weeklyPay = hourlyRate * hoursWorked;
  System.out.println(employee  + ":" + weeklyPay);   System.out.println(employee  + ":" + weeklyPay);
  ================================================   =================================================
 
The figure below shows the signature and body for the new method ``calculatePay``.  The method signature
contains  three formal parameters for employee, hourlyRate, and hoursWorked.  When the method is called, actual values
will need to be provided as shown.

.. figure:: Figures/calculatePay.png
  :align: center
  :alt: Parameter passing for the calculatePay method 
  :figclass: align-center

  Figure 3: The calculatePay method

.. activecode:: CalculatePayMethod
  :language: java
  :autograde: unittest
  :practice: T
    
  Update the code below to add the ``calculatePay`` method shown in Figure 3.  Update the ``main`` method to 
  call the ``calculatePay`` method twice to compute the pay for each employee.  
  Use the CodeLens button or copy the code into the |visualizer| to confirm that your main method makes the two calls to calculatePay, with the correct values passed into the method.

  ~~~~
  public class PayrollCalculator
  { 

    //add a new static method calculatePay here
  


    public static void main(String[] args) {
      
        //call calculatePay for employee Fred, hourly rate 12.50 and hours worked 20.0

        //call calculatePay for employee Amir, hourly rate 15.0 and hours worked 35.0

    }
  }
  ====
  import static org.junit.Assert.*;
  import org.junit.*;;
  import java.io.*;

  public class RunestoneTests extends CodeTestHelper
  {
    
    public RunestoneTests() {
      super("PayrollCalculator");
    }

    @Test
        public void test1()
        {
            String output = getMethodOutput("main");
            String expect = "Fred:250.0\nAmir:525.0\n";
            boolean passed = getResults(expect, output, "Expected output from main", true);
            assertTrue(passed);
        }

    @Test
        public void test2()
        {
           String code = getCode();
           int sig = countOccurences(code, "public static void calculatePay(");
           boolean passed = sig == 1;
           passed = getResults("1 method signature", sig + " method signature", "Add a new method calculatePay", passed);
           assertTrue(passed);
        }

    @Test
        public void test3()
        {
           String code = getCode();
           int calls = countOccurences(code, "calculatePay(");
           boolean passed = calls >=2;
           passed = getResults("2 calls", calls + " calls", "Update the main with two calls to calculatePay", passed);
           assertTrue(passed);
        }
  }


When a method is called, the right method definition is found by 
checking the **method signature** or **header** at the top of the method 
definition to match the method name, the number of arguments, the data 
types for the arguments and the return type. 

|Exercise| **Check your understanding**

.. mchoice:: mparam1
   :practice: T
   :answer_a: mystery("9");
   :answer_b: mystery(9);
   :answer_c: mystery(5, 7);
   :correct: b
   :feedback_a: The type of the actual argument "9" is String, but the formal parameter i is an int.
   :feedback_b: The type of the actual argument 9 and the formal parameter i are both int.
   :feedback_c: The method expects one int to be passed as an actual argument, not 2.  
   
   Based on the method header shown below, which method call is correct?  
   
   .. code-block:: java

     public static void mystery(int i)


.. mchoice:: mparam2
   :practice: T
   :answer_a: mystery("abc", 9);
   :answer_b: mystery("xyz", "9");
   :answer_c: mystery(9, 5);
   :correct: a
   :feedback_a: The actual argument and formal parameter types match.
   :feedback_b: The second parameter i has type int, while the second argument "9" is a string.
   :feedback_c: The method expects a string and an int as actual arguments, not two ints. 
   
   Based on the method header shown below, which method call is correct?  
   
   .. code-block:: java

     public static void mystery(String s, int i)

.. mchoice:: mparam3
   :practice: T
   :answer_a: mystery("true", "hello");
   :answer_b: mystery("hello", false);
   :answer_c: mystery(true, "hello");
   :correct: c
   :feedback_a: "true" is a String, not a boolean.
   :feedback_b: The first argument should be a boolean, and the second argument should be a String.
   :feedback_c: The actual argument and formal parameter types match. 
   
   Based on the method header shown below, which method call is correct?  
   
   .. code-block:: java

     public static void mystery(boolean b, String s)


|Exercise| **Check your understanding**
   
.. figure:: Figures/mysteryoutput.png
  :align: center
  :figclass: align-center
  
  Figure 2: Method Overloading

Figure 2 above shows a class with 3 methods named ``mystery``. While the 3 methods have the same name,
notice that either the type of the formal parameter or the number of formal parameters is different.
You may recall from the constructor lesson that this is called **overloading**. 

.. parsonsprob:: methodargsparson
   :adaptive:
   :noindent:

   The print output shown in the upper right section of 
   Figure 2 was produced by adding 3 method calls in the main method, which have been erased.
   Drag the needed blocks from the left area below into the correct order  in the right area
   to produce the print output shown in Figure 2: 
   -----
   mystery( 5 );
   =====
   mystery( "5" ); #paired
   =====
   mystery( "hello");
   =====
   mystery( hello);  #paired
   =====
   mystery( 9, "bye");
   =====
   mystery( "bye", 9); #paired



Variable Scope
---------------

A variable may be available for use in some lines of code, but not others. 
The **scope** of a variable is the region of the program that is it visible, which means it is accessible by name
and can be used in the code.

A variable declared inside a method is called a **local variable**.  
The scope of a local variable is the method body
in which it is declared, which means it is visible and can be used within the method but not outside of the method. 
You can't use a variable before it is declared, so in fact the scope begins when you declare the variable
and continues until the last line of code in the method.    The local variable's memory location is also only available while 
the method is executing.  When the method completes, the memory location is released. If you called 
the method again, the old value would not be available.  

Consider the following methods:
    
    .. code-block:: java

        public static void inchesToCentimeters(double inches)
        {
            double centimeters = inches * 2.54;
            System.out.print(inches + "-->" + centimeters);
        }

        public static void main(String[] args)  
        {
            inchesToCentimeters(10);
            inchesToCentimeters(15.7);
        }


The ``inchestToCentimeters`` method defines a local 
variable ``centimeters``.  The variable is only available for use in the ``inchesToCentimeters`` method, 
the ``main`` method can't see or use the variable.  Each time the method is called, a new memory location is
created for the variable.

A formal parameter is like a local variable in that its scope is the body of the corresponding method.   
The ``inches`` formal parameter variable is only visible in the ``inchesToCentimeters`` method body. 

While a local variable has its value initialized within the method body, the formal parameter variable has its value
initialized by the method call.  You must explicitly assign a local variable a value before you can use it 
in a calculation.  The compiler will warn you if you try to use a local variable in a calculation or print statement before it has been assigned a value.

|Exercise| **Check your understanding**

.. mchoice:: mscope1
   :practice: T
   :answer_a: print1;
   :answer_b: main;
   :answer_c: print1 and main;
   :correct: b
   :feedback_a: Method print1 accesses num, which is a formal parameter with method level scope.
   :feedback_b: Method main can accesses the local variable age, since it is declared in the main method.
   :feedback_c: Variable age is declared in the main method, so it can't be accessed in the print1 method.
   
   Based on the class shown below, variable age can be used in which method?  
   
   .. code-block:: java

      public class Visibility {

        public static void print1(int num) {
          System.out.println("num is " + num);   
        }

        public static void main(String[] args) {
            int age = 20;
            print1(age);
        }
      }



.. mchoice:: mscope2
   :practice: T
   :answer_a: print1;
   :answer_b: print2;
   :answer_c: main;
   :correct: b
   :feedback_a: Method print1 accesses num, which is a formal parameter with method level scope.
   :feedback_b: Method print2 accesses age, which is not accessible since it is declared in the main method.
   :feedback_c: Method main accesses age, which is a local variable with method level scope..
   
   Based on the class shown below, which method has a scope error (uses a variable that is not visible in that method)?  
   
   .. code-block:: java

      public class Visibility {

        public static void print1(int num) {
          System.out.println("num is " + num);   
        }

        public static void print2() {
          System.out.println("age is " + age);   
        }

        public static void main(String[] args) {
            int age = 20;
            print1(age);
            print2();
        }
      }




Method Tracing
------------------

Any method can call another method.  See if you can trace through the code in the following examples to predict the output.  If you have trouble, copy
the code into the |visualizer|.


|Exercise| **Check your understanding**

.. mchoice:: AP2-4-1
    :practice: T

    Consider the following methods:
    
    .. code-block:: java

        public static void inchesToCentimeters(double i)
        {
            double c = i * 2.54;
            printInCentimeters(i, c);
        }

        public static void printInCentimeters(double inches, double centimeters)
        {
            System.out.print(inches + "-->" + centimeters);
        }

        public static void main(String[] args)  
        {
            inchesToCentimeters(10);
        }

    What is printed when the main method is run?
    
    - inches --> centimeters
    
      - The values of the variables inches and centimeters should be printed out, not the words.
      
    - 10 -->  25
      
      - Two doubles should be printed, not two ints, and the centimeters should be 25.4
    
    - 25.4 --> 10
    
      - Inches should be printed before centimeters.
    
    - 10 --> 12.54
    
      - c = 10 * 2.54 = 25.4, not 12.54.
    
    - 10.0 --> 25.4
    
      + Correct! centimeters = 10 * 2.54 = 25.4. 




.. mchoice:: AP2-4-2
    :practice: T
    
    Consider the following methods.

    .. code-block:: java
    
        public static void splitPizza(int numOfPeople)
        {
            int slicesPerPerson = 8/numOfPeople;
            /* INSERT CODE HERE */
        }

        public static void printSlices(int slices)
        {
            System.out.println("Each person gets " + slices + " slices each");
        }


    Which of the following lines would go into ``/* INSERT CODE HERE */`` in the method splitPizza in 
    order to call the ``printSlices`` method to print the number of slices per person correctly? 
    
    - printSlices(slicesPerPerson);
    
      + Correct! If you had 4 people, slicesPerPerson would be 8/4=2 and printSlices would print out "Each person gets 2 slices each".
      
    - printSlices(numOfPeople);
    
      - If you had 4 people, this would print out that they get 4 slices each of an 8 slice pizza.
      
    - printSlices(8);
    
      - This would always print out 8 slices each.
      
    - splitPizza(8);
    
      - This would not call the printSlices method.
      
    - splitPizza(slicesPerPerson);
    
      - This would not call the printSlices method.


|Exercise| **Check your understanding**

.. mchoice:: traceMethods5
   :practice: T
   :answer_a: 25 and 2
   :answer_b: 25 and .5
   :answer_c: 2 25
   :answer_d: 25 2
   :answer_e: Nothing, it does not compile.
   :correct: a
   :feedback_a: Correct.
   :feedback_b: The order of the arguments to the divide(x,y) method will divide x by y and return an int result.
   :feedback_c: The square(x) method is called before the divide(x,y) method.
   :feedback_d: The main method prints out " and " in between the method calls.
   :feedback_e: Try the code in the visualizer.
   
   What does the following code print out?
   
   .. code-block:: java
   
      public class MethodTrace 
      {
        public static void square(int x)
        {
            System.out.print(x*x);
        }
        public static void divide(int x, int y)
        {
            System.out.println(x/y);
        }
        public static void main(String[] args) {
            square(5);
            System.out.print(" and ");
            divide(4,2);
        }
       }




Pass by value
---------------

Java uses **pass by Value** when it passes arguments to methods. 
This means that a copy of the value in the argument is saved in the parameter variable. 
If the parameter variable changes its value inside the method, 
the original value outside the method is not changed.  **It is generally not a good idea to change the 
value of a parameter inside a method, however it is possible as the example below shows.**

|CodingEx| **Check your understanding**

.. activecode:: changeparamvalue
  :language: java
  :autograde: unittest
  :practice: T
    
  Use the CodeLens button or copy the code into the |visualizer| to watch how the square method
  alters the value of x, while the value of y in the main method is not affected.

  Try changing the name of the variable in the main method to "x" and rerun the program.  You should see
  that the variable in the main method remains unaffected by changes made in the square method, even when 
  the variables have the same name.
  ~~~~
  public class CallByValue 
  {
    public static void square(int x)
    {
      x = x * x;
      System.out.print(x);
    }

    public static void main(String[] args) 
    {
      int y = 5;
      square(y);   
    }
  }

  ====
  import static org.junit.Assert.*;
  import org.junit.*;;
  import java.io.*;

  public class RunestoneTests extends CodeTestHelper
  {
    
    public RunestoneTests() {
      super("CallByValue");
    }

    @Test
    public void test1()
    {
      String code = getCode();
      int num = countOccurences(code, "square(");
      boolean passed = numVerses = 1;
      passed = getResults("1 call", 1 + " ca;;", "The main should call the square method", passed);
      assertTrue(passed);
    }
  }

If you pass in an argument that holds a reference to an object, 
like a String or Person or Turtle object, a copy of this reference 
is passed in and saved in the parameter variable. You will explore 
this more in the following unit.


|Groupwork| Programming Challenge : Calculating Shipping Costs
---------------------------------------------------------------

The ShippingCostCalculator class listed below computes and prints the shipping cost for 3 different items based on their weight. 
If the item weighs less than 15.0 lbs the cost is 9.95, otherwise the cost is 12.95.
While the if-else statements are not identical 
due to the different variables names (weight1 vs weight2 vs weight3, cost1 vs cost2 vs cost3),
each tests the weight and assigns the cost in the same way.  

.. code-block:: java

  public class ShippingCostCalculator {
    
    public static void main(String[] args) {
      
      double weight1, weight2, weight3;
      double cost1, cost2, cost3;

      weight1 = 22.0;  
      weight2 = 10.0;
      weight3 = 12.0;

      //calculate cost for item#1
      if (weight1 < 15.0)
      {
        cost1 = 9.95;
      }
      else 
      {
        cost1 = 12.95;
      }
      System.out.println(cost1);

      //calculate cost for item#2
      if (weight2 < 15.0)
      {
        cost2 = 9.95;
      }
      else 
      {
        cost2 = 12.95;
      }
      System.out.println(cost2);

      //calculate cost for item#3
      if (weight3 < 15.0)
      {
        cost3 = 9.95;
      }
      else 
      {
        cost3 = 12.95;
      }
      System.out.println(cost3);

      }
    }
    

The redundant code can be reduced by adding a new method to 
compute and print shipping cost based on item weight.  

.. activecode:: challenge-5-6-costCalculator
  :language: java
  :autograde: unittest  

  - Update the program below to add a new method  ``calculateShipping`` that has one formal parameter for ``weight``.  The method will need a local variable for ``cost``.  The method should test the weight and print the corresponding cost.
  - Update the main method to replace the existing code with 3 calls to ``calculateShipping``, each passing an actual value for weight.  The main method will no longer need local variables.
  - Confirm that the new version of the program produces the same output as the original version.

  ~~~~
  public class ShippingCostCalculator {
  
  public static void main(String[] args) {
    
     double weight1, weight2, weight3;
     double cost1, cost2, cost3;

     weight1 = 22.0;  
     weight2 = 10.0;
     weight3 = 12.0;

     //calculate cost for item#1
     if (weight1 < 15.0)
     {
        cost1 = 9.95;
     }
     else 
     {
        cost1 = 12.95;
     }
     System.out.println(cost1);

     //calculate cost for item#2
     if (weight2 < 15.0)
     {
        cost2 = 9.95;
     }
     else 
     {
        cost2 = 12.95;
     }
     System.out.println(cost2);

     //calculate cost for item#3
     if (weight3 < 15.0)
     {
        cost3 = 9.95;
     }
     else 
     {
        cost3 = 12.95;
     }
     System.out.println(cost3);

    }
  }
  ====
  import static org.junit.Assert.*;
    import org.junit.*;;
    import java.io.*;
    
    public class RunestoneTests extends CodeTestHelper
    {

    public RunestoneTests() {
      super("ShippingCostCalculator");
    }
      @Test
      public void checkCodeContains3(){
        String code = getCode();
        int num = countOccurences(code, "public static void calculateShipping(");
        boolean passed = num = 1;
        passed = getResults("1 method declaration", num + " method declaration", "Declare the static calculateShipping method", passed);
        assertTrue(passed);
      }

      @Test
      public void checkCodeContains3(){
        String code = getCode();
        int num = countOccurences(code, "calculateShipping(");
        boolean passed = num >=3;
        passed = getResults("3 method calls", num + " method calls", "Call the calculateShipping method 3 times", passed);
        assertTrue(passed);
      }

      @Test
      public void testMain() throws IOException
      {
            String output = getMethodOutput("main");
            String expect = "12.95\n9.95\n9.95";
            boolean passed = output.contains(expect);
            getResults(expect, output, "Expected output from main");
            assertTrue(passed);
      }
    }


Summary
-------

- When you call a method, you can give or pass in **arguments** or **actual parameters** inside the parentheses **object.method(arguments)**. The arguments are saved in local **formal parameter** variables that are declared in the method header, for example: public void method(type param1, type param2) { ... }.

- Values provided in the arguments in a method call need to correspond to the order and type of the parameters in the method signature.

- When an actual parameter is a primitive value, the formal parameter is initialized with a copy of that value. 

- New values assigned to the formal parameter within the method have no effect on the corresponding actual parameter.