.. qnum::
   :prefix: 5-4-
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
  
Method Comments
=================

Recall that there are 3 types of comments in Java:

1. ``//`` Single line comment
2. ``/*`` Multiline comment ``*/``
3. ``/**`` Documentation comment ``*/``

.. |Java JDK| raw:: html

   <a href="https://www.oracle.com/technetwork/java/javase/downloads/index.html" target="_blank">Java JDK</a>

.. |javadoc| raw:: html

   <a href="https://www.tutorialspoint.com/java/java_documentation.htm" target="_blank">javadoc</a>

.. |String class| raw:: html

   <a href="http://docs.oracle.com/javase/7/docs/api/java/lang/String.html" target="_blank">String class</a>
   
The special characters ``//`` are used to mark the rest of the line as a comment in many programming languages.  If the comment is going to be multiple lines, we use ``/*`` to start the comment and ``*/`` to end the comment. 

The multi-line comment, ``/**``  ``*/`` is called the documentation comment. 
Java has a cool tool called |javadoc| that comes with the |Java JDK| that will pull out all of these 
comments to make documentation of a class as a web page.  This tool generates the official Java 
documentation too, for example for the |String class|. 
It's a good idea to use the documentation comment in front of classes, methods, and 
instance variables in case you want to use this tool. 

The are some special tags that you can use in Java documentation. These are not required but many programmers use them. Here are some common tags:

- @author  Author of the program
- @since   Date released
- @version Version of program 
- @param   Parameter of a method
- @return  Return value for a method

The code below shows example commenting for a trivial class as well as an example method

.. code-block:: java

    /**
    * The Add2Number program implements an application that
    * adds two given integer numbers and prints
    * the output on the screen.
    *
    * @author  Fred Smith
    * @version 1.0
    * @since   2019-01-31
    */
    public class Add2Number {

        /**
        * This method is used to add two integers.
        * @param numA The first number to use in the sum
        * @param numB  The second number to use in the sum
        * @return int This returns sum of numA and numB.
        */
        public static int addNum(int numA, int numB) {
            return numA + numB;
        }

        /**
        * This is the main method which makes use of addNum method.
        * @param args Unused.
        * @return Nothing.
        */

        public static void main(String args[])  {
            int sum = addNum(10, 20);
            System.out.println("Sum of 10 and 20 is :" + sum);
        }

    }

 
Preconditions and  Postconditions
---------------------------------

As you write methods in a class, it is a good idea to keep in mind the **preconditions** and the **postconditions** for the method and write them in the comments. A precondition is a condition that must be true for your method code to work, for example the assumption that the parameters have values and are not null. The methods could check for these preconditions, but they do not have to. The precondition is what the method expects in order to do its job properly.

A postcondition is a condition that is true after running the method. It is what the method promises to do. Postconditions describe the outcome of running the method, for example what is being returned or the changes to the instance variables. These assumptions are very useful to other programmers who want to use your class and get the correct results. 


Here is an example of preconditions, postconditions, and @param in the Turtle code that we have used in the past for our drawing turtles.

.. code-block:: java 

       /**
         * Constructor that takes the x and y position for the
         * turtle
         * Preconditions: parameters x and y are coordinates from 0 to 
         *    the width and height of the world.
         * Postconditions: the turtle is placed in (x,y) coordinates 
         * @param x the x position to place the turtle
         * @param y the y position to place the turtle
         */
        public Turtle(int x, int y)
        {
          xPos = x;
          yPos = y;
        }
        
|CodingEx| **Coding Exercise**

Try to break the preconditions of the Turtle constructor below. Does the Turtle constructor behave properly if you break the preconditions that x and y are between 0 and 300. Try giving the Turtle constructor  x and y values out of these ranges. What happens? Does the method give good results? Does it give any warnings? What about the t.forward() method? Does it have any preconditions that you can break?

.. |github| raw:: html

   <a href="https://github.com/bhoffman0/APCSA-2019/tree/master/_sources/Unit2-Using-Objects/TurtleJavaSwingCode.zip" target="_blank" style="text-decoration:underline">here</a>
   
.. |repl link| raw:: html

   <a href="https://repl.it/@BerylHoffman/Java-Swing-Turtle" target="_blank" style="text-decoration:underline">repl.it link</a>
   
(If the code below does not work for you, you can copy the code into  this |repl link| (refresh page after forking and if it gets stuck) or download the files |github| to use in your own IDE.)

.. activecode:: turtle-preconditions
    :language: java
    :datafile: turtleClasses.jar

    import java.util.*;
    import java.awt.*;

    public class TurtlePreconditions
    {
      public static void main(String[] args)
      {
          World world = new World(300,300);
          // Change 0,0 to other values outside of 0-300 to break the preconditions and see what happens
          Turtle t = new Turtle(0,0,world);
          t.turnRight();
          world.show(true); 
      }
    }
    
The Turtle constructor's precondition is that x and y should be between 0 and the width and height of the world. If it receives values out of this range, it sets x and y to the closest legal values that it can so that the turtle appears just at the edge of the world. Similarly, the forward() method will not allow the turtle to leave the world.  

|Exercise| **Check your understanding**

.. mchoice:: AP5-3-1
    :practice: T
    :answer_a: /* Precondition: s <= 0 */
    :answer_b: /* Precondition: score >= 0 */
    :answer_c: /* Precondition: s and ec >= 0 */
    :answer_d: /* Precondition: n is not the empty String */
    :answer_e: /* Precondition: studentName is not the empty String */
    :correct: c, d
    :feedback_a: It is not reasonable the s which sets the score should be negative.
    :feedback_b: The precondition should be about the parameters of the constructor. score is not the parameter variable.
    :feedback_c: Correct. It is reasonable that the score and extraCredit should be set to positive values using the parameters s and ec.
    :feedback_d: Correct. It is reasonable that the parameter n which sets the name should be not empty. 
    :feedback_e: The precondition should be about the parameters of the constructor. score is not the parameter variable.
   
    Consider the following class definition.

    .. code-block:: java

        public class TestScore
        {
            private String studentName;
            private double score;
            private double extraCredit;

            public TestScore (String n, double s, double ec)
            {
                studentName = n;
                score = s;
                extraCredit = ec;
            }
            /* Other methods not shown */
        }

     Which of the following preconditions are reasonable for the TestScore constructor?
            

Let's consider the substring method in Java. This method has a strong precondition that its arguments refer to indices within the given string. 

|CodingEx| **Coding Exercise**

.. activecode:: substring-preconditions
    :language: java
    :autograde: unittest

    The following code breaks the preconditions of the substring method and throws an IndexOutOfBoundsException. Can you fix the code by changing the arguments for the substring method to print out the substring "lo"? What are the preconditions for the substring method?
    ~~~~
    public class SubstringPreconditions
    {
      public static void main(String[] args)
      {
          String str = "hello";
          System.out.println( str.substring(-1,10) );
      }
    }
    ====
    // Test for Lesson 5.3.2 Substring-preconditions
    import static org.junit.Assert.*;
    import org.junit.*;
    import java.io.*;

    public class RunestoneTests extends CodeTestHelper
    {
        public RunestoneTests() {
            super("SubstringPreconditions");
        }

        @Test
        public void testMain() throws IOException
        {
            String output = getMethodOutput("main");
            String expect = "lo";
            boolean passed = getResults(expect, output, "Expected output from main");
            assertTrue(passed);
        }
    }

.. note::
 
    The method str.substring(beginIndex, endIndex) has the precondition that 0 <= beginIndex <= endIndex <= str.length.
    
|Exercise| **Check your understanding**

.. mchoice:: AP5-3-2
   :practice: T
   :answer_a: /* Precondition: i >= 0 */
   :answer_b: /* Precondition: i <= str.length() */
   :answer_c: /* Precondition: 0 < i < str.length() */
   :answer_d: /* Precondition: 0 <= i < str.length() */
   :correct: d
   :feedback_a: This is true but it could still throw an exception if i is a large value.
   :feedback_b: This is true but it could still throw an exception if i is a negative value.   
   :feedback_c: This is true but a little too restrictive.
   :feedback_d: Correct. i can refer to character 0 up to str.length().
      
   The following method is intended to return the substring starting at index i until the end of the string. For example, getiToEnd("012",1) should return "12". Which of the following is the most appropriate precondition for the method so that it does not throw an exception?

   .. code-block:: java

        /* missing precondition */
        public String getiToEnd(String str, int i)
        {
            return str.substring(i, str.length());
        }
    


