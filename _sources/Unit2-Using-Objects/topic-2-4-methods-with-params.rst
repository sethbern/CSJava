.. qnum::
   :prefix: 2-4-
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
    single: parameter
    single: argument

.. |repl link| raw:: html

   <a href="https://repl.it/@LindaMM/Java-Swing-Turtle" target="_blank" style="text-decoration:underline">repl.it link</a>



.. |github| raw:: html

   <a href="https://github.com/bhoffman0/APCSA-2019/tree/master/_sources/Unit2-Using-Objects/TurtleJavaSwingCode.zip" target="_blank" style="text-decoration:underline">here</a>

    
.. |runbutton| image:: Figures/run-button.png
    :height: 30px
    :align: top
    :alt: run button
   



Calling Methods With Parameters
===========================================

In the last lesson, we used methods like forward() and turnRight() to make the turtle draw lines. You may have noticed that forward() and backward() always move the same number of pixels (100 pixels), and turnRight() and turnLeft() always turn at right angles (90 degrees). This is a little limiting. What if we wanted to draw a triangle or the letter A? These require smaller angles to draw diagonal lines and different length lines. Luckily, there are more complex methods in the Turtle class that let you specify the number of pixels to move forward or the number of degrees to turn. These values that you can give to methods to help them do their job are called **arguments** or **parameters**. 

The parentheses () after method names are there in case you need to give the 
method **actual parameters** or **arguments** (some data) to do its job. 
For example, we can give the argument 25 in forward(25) to make the turtle go 
forward 25 pixels or the argument 30 in turn(30) to make the turtle turn 30 degrees. 


.. note::

    object.method(arguments); is used to call an object's method and give it some arguments (actual parameters) to do its job. 


Although some people use the words parameters and arguments interchangeably, there is a subtle difference. 
When you create your own method, the variables you define for it are 
called **formal parameters**. When you call the method to do its job, you give or 
pass in **arguments** or **actual parameters** to it that are then saved in the 
parameter variables. So, in the definition of the forward method, it has a 
parameter variable called pixels, and in the call to forward(25), the argument is the 
value 25 which will get saved in the parameter variable pixels. 
You will learn to write your own methods in Unit 5. 
In this unit, you will learn to call methods that are already written for you.

.. code-block:: java 

    // Method call
    yertle.forward(25); // argument is 25
    
    // Method definition written for you
    public void forward(int pixels) // parameter pixels
    ...

|Exercise| **Check your understanding**

.. dragndrop:: Params
    :feedback: Review the vocabulary above.
    :match_1: an object's behaviors or functions that can be used or called to do its job|||methods
    :match_2: the values or data passed to an object's method|||arguments or actual parameters
    :match_3: the variables in a method's definition that hold the arguments|||formal parameters
    :match_4: asking to run the method|||method call    
    
    Drag the definition from the left and drop it on the correct word on the right.  Click the "Check Me" button to see if you are correct.

	
Here is the Turtle class diagram again that shows some of the variables and methods inherited from the SimpleTurtle class in the class Turtle that are written for you. 

.. figure:: Figures/turtleUMLClassDiagram.png
    :width: 300px
    :align: center
    :alt: Turtle class diagram
    :figclass: align-center

    Figure 1: Turtle Class Diagram
    
.. |Color| raw:: html

   <a href= "https://docs.oracle.com/javase/7/docs/api/java/awt/Color.html" target="_blank">Color</a>
   
.. |javadoc (documentation) file| raw:: html

   <a href="https://www2.cs.uic.edu/~i101/doc/SimpleTurtle.html" target="_blank">javadoc (documentation) file</a>   

Try some of the methods above in the turtle code below. 
You can see all the methods that are inherited in Turtle in this |javadoc (documentation) file|. 

Methods are said to be **overloaded** when there
are multiple methods with the same name but a
different **method signature**, where it requires a different number or type of parameters. 
For example, we have two different forward methods, forward() with no parameters 
and forward(25) which has an int parameter that tells it how much to move forward. 
If there is more than one parameter, then the values given to the method need to correspond to the order and types in the method signature. 


|CodingEx| **Coding Exercise**

(If the code below does not work in your browser, you can also use the Turtle code at this |repl link| (refresh page after forking and if it gets stuck) or download the files |github| to use in your own IDE.)


.. activecode:: TurtleTestMethods1
    :language: java
    :autograde: unittest
    :datafile: turtleClasses.jar

    1. Can you make yertle draw a square and change the pen color for each side of the square? Try something like: yertle.setColor(Color.red); This uses the |Color| class in Java which has some colors predefined like red, yellow, blue, magenta, cyan. You can also use more specific methods like setPenColor, setBodyColor, and setShellColor.
    2. Can you draw a triangle? The turnRight() method always does 90 degree turns, but you'll need 60 degree angles for a equilateral triangle. Use the turn method which has a parameter for the angle of the turn in degrees. For example, turn(90) is the same as turnRight(). Try drawing a triangle with different colors. 
    ~~~~
    import java.util.*;
    import java.awt.*;

    public class TurtleTestMethods1
    {
      public static void main(String[] args)
      {
          World world = new World(300,300);
          Turtle yertle = new Turtle(world);
          
          yertle.forward(100);
          yertle.turnLeft();
          yertle.forward(75);
          
          world.show(true); 
      }
    }
    ====
    import static org.junit.Assert.*;
    import org.junit.*;;
    import java.io.*;

    public class RunestoneTests extends CodeTestHelper
    {
        public RunestoneTests() {
            super("TurtleTestMethods1");
        }

        @Test
        public void test1()
        {
            String orig = "import java.util.*;\nimport java.awt.*;\n\npublic class TurtleTestMethods1\n{\n  public static void main(String[] args)\n  {\n      World world = new World(300,300);\n      Turtle yertle = new Turtle(world);\n\n      yertle.forward(100);\n      yertle.turnLeft();\n      yertle.forward(75);\n\n      world.show(true);\n  }\n}\n";
            boolean passed = codeChanged(orig);
            assertTrue(passed);
        }

        @Test
        public void test2()
        {
            String code = getCode();
            int numColors = countOccurences(code, "Color(");

            boolean passed = numColors >= 4;
            passed = getResults("4 or more", ""+numColors, "Changing color at least 4 times", passed);
            assertTrue(passed);
        }

        @Test
        public void test3()
        {
            String code = getCode();
            int numTurns = countOccurences(code, ".turn");

            boolean passed = numTurns >= 4;
            passed = getResults("4 or more", ""+numTurns, "Number of turns", passed);
            assertTrue(passed);
        }

        @Test
        public void test4()
        {
            String code = getCode();
            int numTurns = countOccurences(code, ".turn(");

            boolean passed = numTurns >= 1;
            passed = getResults("1 or more", ""+numTurns, "Calls to turn(...)", passed);
            assertTrue(passed);
        }

        @Test
        public void test5()
        {
            String code = getCode();
            int numForward = countOccurences(code, ".forward(");

            boolean passed = numForward >= 4;
            passed = getResults("4 or more", ""+numForward, "Calls to forward()", passed);
            assertTrue(passed);
        }
    }



|CodingEx| **Coding Exercise**

Try the following mixed up code to draw a simple house made of a square and a triangle roof.

.. image:: Figures/house.png
    :width: 200px
    :align: left
    :alt: simple house
    
    
.. parsonsprob:: DrawAHouse
   :numbered: left
   :practice: T
   :adaptive:
   :noindent:
   
   The following code uses a turtle to draw a simple house, but the lines are mixed up.  Drag the code blocks to the right and put them in the correct order to first draw a square for the house and then a red triangle for the roof.  Click on the "Check Me" button to check your solution.  You can copy and paste this code in the Active Code window above to see it in action.
   -----
   public class TurtleDrawHouse
   {
   =====
      public static void main(String[] args)
      {
      =====
         World world = new World(300,300);
         =====
         Turtle builder = new Turtle(world);
         =====
         // Draw a square
         builder.turnRight();
         builder.forward(100);
         builder.turnRight();
         builder.forward(100);
         builder.turnRight();
         builder.forward(100);
         builder.turnRight();
         builder.forward(100);
         =====
         builder.setColor(Color.red);
         =====
         // Draw a triangle
         builder.turn(30);
         builder.forward(100);
         builder.turn(120);
         builder.forward(100);
         builder.turn(120);
         builder.forward(100);
         =====
         world.show(true);
         =====
      }
      =====
   }
   



.. |visualization| raw:: html

   <a href="http://www.pythontutor.com/visualize.html#code=%20%20public%20class%20MethodTrace%20%0A%20%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20public%20void%20square%28int%20x%29%0A%20%20%20%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20System.out.print%28x*x%29%3B%0A%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%20%20public%20void%20divide%28int%20x,%20int%20y%29%0A%20%20%20%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20System.out.println%28x/y%29%3B%0A%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%20%20public%20static%20void%20main%28String%5B%5D%20args%29%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20MethodTrace%20traceObj%20%3D%20new%20MethodTrace%28%29%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20traceObj.square%285%29%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20System.out.print%28%22%20and%20%22%29%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20traceObj.divide%284,2%29%3B%0A%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%20%7D&cumulative=false&curInstr=18&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=java&rawInputLstJSON=%5B%5D&textReferences=false" target="_blank" style="text-decoration:underline">visualization</a>

Try this |visualization| to see this code in action.

|Groupwork| Programming Challenge : Turtle House
------------------------------------------------

.. image:: Figures/houseWithWindows.png
    :width: 200px
    :align: left
    :alt: simple house
    
Design a house and have the turtle draw it with different colors 
below (or with this |repl link|). Can you add windows and a door? 

To draw a window, you will need to do penUp() to walk the turtle into position, for example:

.. code-block:: java 

   builder.penUp();
   builder.moveTo(120,200);
   builder.penDown();
   
It may help to act out the code pretending you are the turtle. 
Remember that the angles you turn depend on which direction you are facing, 
and the turtle begins facing up.


.. activecode:: challenge2-4-TurtleHouse
    :language: java
    :autograde: unittest
    :datafile: turtleClasses.jar

    import java.util.*;
    import java.awt.*;

    public class TurtleHouse
    {
      public static void main(String[] args)
      {
          World world = new World(300,300);
          
          
          
          world.show(true); 
      }
    }
    ====
    import static org.junit.Assert.*;
    import org.junit.*;;
    import java.io.*;

    public class RunestoneTests extends CodeTestHelper
    {
        public RunestoneTests() {
            super("TurtleHouse");
        }

        @Test
        public void test1()
        {
            String orig = "import java.util.*;\nimport java.awt.*;\n\npublic class TurtleHouse\n{\n  public static void main(String[] args)\n  {\n      World world = new World(300,300);\n\n\n\n      world.show(true);\n  }\n}\n";
            boolean passed = codeChanged(orig);
            assertTrue(passed);
        }

        @Test
        public void test2()
        {
            String code = getCode();
            int num = countOccurences(code, "moveTo(");

            boolean passed = num >= 1;
            passed = getResults("1 or more", ""+num, "Calls moveTo(...)", passed);
            assertTrue(passed);
        }

        @Test
        public void test3()
        {
            String code = getCode();
            int num = countOccurences(code, ".penUp()");

            boolean passed = num >= 1;
            passed = getResults("4 or more", ""+num, "Calls penUp()", passed);
            assertTrue(passed);
        }

        @Test
        public void test4()
        {
            String code = getCode();
            int num = countOccurences(code, ".penDown(");

            boolean passed = num >= 1;
            passed = getResults("1 or more", ""+num, "Calls penDown()", passed);
            assertTrue(passed);
        }
        @Test
        public void test5()
        {
            String code = getCode();
            int numTurns = countOccurences(code, ".turn");

            boolean passed = numTurns >= 6;
            passed = getResults("6 or more", ""+numTurns, "turns", passed);
            assertTrue(passed);
        }

        @Test
        public void test6()
        {
            String code = getCode();
            int numForward = countOccurences(code, ".forward(");

            boolean passed = numForward >= 6;
            passed = getResults("6 or more", ""+numForward, "Calls to forward()", passed);
            assertTrue(passed);
        }
    }


Summary
-------------------

- **Methods** define the behaviors or functions for objects. 

- To use an object's method, you must use the object name and the dot (.) operator followed by the method name, for example **object.method();** 

- Some methods take parameters/arguments that are placed inside the parentheses **object.method(arguments)**.

- Values provided in the parameter list need to correspond to the order and type in the method signature.
