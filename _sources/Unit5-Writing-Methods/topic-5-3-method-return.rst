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

Formal parameters allow you to pass values into a method. You can also  pass a value out of a method.  
You saw some examples of  methods that return values in unit 2 with the ``Turtle`` methods (getWidth, getXpos, etc).
If you recall the methods were usually on the right hand side of an assignment, or were contained in a print statement.
The methods returned a value, so your code needed to store or use the value in some way.

In this lesson, you will create new methods that return a value.  

Method Return Type
------------------

A method can return at most one value.
The method signature specifies the return type, which can be a primitive (int, double, boolean), 
a class (String, Turtle, etc), or void.
A return type of void means the method does not return a value.
If a method has a non-void return type, then it must contain a **return statement** that specifies the value to return.
The method return type must match the type of the value.

.. activecode:: squarereturn
  :language: java
  :autograde: unittest
  :practice: T
    
  The method square takes a value passed into parameter x and returns the value x*x.
  Use the CodeLens to watch the value being passed in and out of the square method.
  Experiment with passing different values to the method.

  ~~~~
  public class SquaredExample 
  {
    public static double square(double x)
    {
      return x * x;
    }

    public static void main(String[] args) 
    {
      double result = square(5.0);
      System.out.println(result);   
    }
  }

  ====
  import static org.junit.Assert.*;
  import org.junit.*;;
  import java.io.*;

  public class RunestoneTests extends CodeTestHelper
  {
    
    public RunestoneTests() {
      super("SquaredExample");
    }

    @Test
      public void test1()
      {
        boolean passed = getResults("true", "true", "main()");
        assertTrue(passed);
      }
  }



.. activecode:: inchestocentimeters
  :language: java
  :autograde: unittest
  :practice: T
    
  The code below contains a method inchesToCentimeters that computes and prints the centimeter equivalent of the value passed into the inches parameter.
  Instead of printing the centimeter value inside the method, you should update the inchesToCentimeters 
  method to return the value.  You will have to change 
  the return type of the method.  Update the main method to print the value returned by the 
  inchesToCentiments method. 

  ~~~~
  public class InchesToCentimeters 
  {
    public static void inchesToCentimeters(double inches)
        {
            double centimeters = inches * 2.54;
            System.out.println(centimeters);
        }

        public static void main(String[] args)  
        {
            inchesToCentimeters(10);
            inchesToCentimeters(12.5);
        }
  }

  ====
  import static org.junit.Assert.*;
  import org.junit.*;;
  import java.io.*;

  public class RunestoneTests extends CodeTestHelper
  {
    
    public RunestoneTests() {
      super("InchesToCentimeters");
    }

      @Test
      public void checkCodeContainsSig(){
        String code = getCode();
        int num = countOccurences(code, "public static double inchesToCentimeters(double inches)");
        boolean passed = num ==1;
        passed = getResults("1", num , "Change the return type of inchesToCentimeters", passed);
        assertTrue(passed);
      }

     @Test
      public void checkCodeContainsReturn(){
        String code = getCode();
        int num = countOccurences(code, "return");
        boolean passed = num ==1;
        passed = getResults("1", num , "The method inchesToCentiments is missing a return statement", passed);
        assertTrue(passed);
      }

      @Test
      public void testMain() throws IOException
      {
            String output = getMethodOutput("main");
            String expect = "25.4\n9.95\n31.74";
            boolean passed = output.contains(expect);
            getResults(expect, output, "Expected output from main");
            assertTrue(passed);
      }
    }
  }





|Exercise| **Check your understanding**


asdfasdf

.. mchoice:: m_5_3_1
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


.. mchoice:: m_5_3_2
   :practice: T
   :answer_a: return "hello";
   :answer_b: return true;
   :answer_c: return "7";
   :answer_d: return 10;
   :correct: b
   :feedback_a: The method return type boolean does not match the return statement type String. 
   :feedback_b: The method return type boolean matches the return statement type boolean.
   :feedback_c: The method return type boolean does not match the return statement type String.
   :feedback_d: The method return type boolean does not match the return statement type int.
   
   Based on the method header below, which return statement has the correct type?  
    
   .. code-block:: java

     public static boolean mystery2()


.. mchoice:: m_5_3_3
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


.. mchoice:: m_5_3_4
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
   
   Based on the method header below, which statement is correct for the method?  
    
   .. code-block:: java

     public static void mystery4()


.. mchoice:: m_5_3_1
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


