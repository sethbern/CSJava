.. qnum::
   :prefix: 2-3-
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


.. |github| raw:: html

   <a href="https://github.com/bhoffman0/APCSA-2019/tree/master/_sources/Unit2-Using-Objects/TurtleJavaSwingCode.zip" target="_blank" style="text-decoration:underline">here</a>

.. |repl link| raw:: html

   <a href="https://repl.it/@LindaMM/Java-Swing-Turtle" target="_blank" style="text-decoration:underline">repl.it link</a>


Calling Object Methods Without Parameters
===========================================

Methods define common behavior for all objects of the class.
In the ``Turtle`` class, methods 
like ``forward()`` and ``turnRight()`` give turtle objects the ability to 
move forward 100 pixels and turn 90 degrees right.

The methods written for the Turtle class are called **object methods** or **non-static methods**. 
An object method *must* be called on an object of the class that the method is defined in.  
Object methods work with the **attributes** of the object, such as the 
direction the turtle is heading or its position. 

To call an object method, you must use a variable that references an object, along with the dot (.) operator followed 
by the method name.  For example, ``yertle.forward();`` calls the "forward" method on the turtle referenced
by the variable "yertle", which results in a change to yertle's location.  
On the other hand, ``myrtle.turnRight()`` calls the "turnRight" method on a different turtle object
referenced by the "myrtle" variable, resulting in a change to myrtle's heading. 

Every method call is followed by parentheses. 
The parentheses ``()`` after method names are there in case you need to give the 
method parameters (data) to do its job, which we will see in the next lesson. 
You must always include the parentheses after the method name.


|Exercise| **Check Your Understanding: Mixed-up Code**

.. parsonsprob:: 2_3_Draw7
   :practice: T
   :numbered: left
   :adaptive:
   :noindent:

   The following code uses a turtle to draw the digital number 7, but the lines are mixed up.  
   Drag the code blocks to the right and put them in the correct order to first 
   draw the line going up (towards the top of the page) and then turn and draw a 
   line to the left to make a 7. Remember that the turtle is facing the top of the 
   page when it is first created. 
   -----
   public class DrawL
   {
   =====
       public static void main(String[] args)
       {
   =====
           World world = new World(300,300);
   =====
           Turtle yertle = new Turtle(world);
   =====
           yertle.forward();
   =====
           yertle.turnLeft();
           yertle.forward();
   =====
           world.show(true);
   =====
       } // end main
   =====
   } // end class

|CodingEx| **Coding Exercise:**


After you put the mixed up code in order above, 
type in the same code below to make the turtle draw a 7.

.. activecode:: TurtleDraw7
    :language: java
    :autograde: unittest
    :datafile: turtleClasses.jar

    import java.util.*;
    import java.awt.*;

    public class TurtleDraw7
    {
      public static void main(String[] args)
      {
          World world = new World(300,300);
          Turtle yertle = new Turtle(world);
          // Make yertle draw a 7 using the code above



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
            super("TurtleDraw7");
        }

        @Test
        public void test1()
        {
            String orig = "yertle.forward();\nyertle.turnLeft();\nyertle.forward();";
            boolean passed = checkCodeContains(orig);
            assertTrue(passed);
        }
    }

|CodingEx| **Coding Exercise:**


.. activecode:: TurtleDraw8
    :language: java
    :autograde: unittest
    :datafile: turtleClasses.jar

    Can you make yertle draw the digital number 8, as 2 squares on top of each other?
    ~~~~
    import java.util.*;
    import java.awt.*;

    public class TurtleDraw8
    {
      public static void main(String[] args)
      {
          World world = new World(300,300);
          Turtle yertle = new Turtle(world);
          // Make yertle draw an 8 with 2 squares
          yertle.forward();


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
            super("TurtleDraw8");
        }

        @Test
        public void test1()
        {
            String orig = "import java.util.*;\nimport java.awt.*;\n\npublic class TurtleDraw8\n{\n  public static void main(String[] args)\n  {\n      World world = new World(300,300);\n      Turtle yertle = new Turtle(world);\n      // Make yertle draw an 8 with 2 squares\n      yertle.forward();\n\n\n      world.show(true);\n  }\n}\n";
            boolean passed = codeChanged(orig);
            assertTrue(passed);
        }

        @Test
        public void test2() {
            String code = getCode();
            int numForward = countOccurences(code, "forward()");

            boolean passed = numForward >= 7;

            passed = getResults("7 or more", ""+numForward, "Calls to forward()", passed);
            assertTrue(passed);
        }

        @Test
        public void test3() {
            String code = getCode();
            int numTurn = countOccurences(code, ".turn");

            boolean passed = numTurn >= 5;

            passed = getResults("5 or more", ""+numTurn, "Calls to turnRight() or turnLeft()", passed);
            assertTrue(passed);
        }
    }

Procedural Abstraction
-----------------------

**Procedural abstraction** allows a programmer to use a method and not worry 
about the details of how it exactly works. 
For example, we know that if we hit the brakes, the car will stop, 
and we can still use the brakes even if we don't really know how they work.

You will learn to write your own methods a later lesson. 
In this unit, you should be able to use methods already 
written for you and figure out what they do.  
For example, look over the methods available in the Turtle class.   You can
probably figure out what each method does just by looking at the method name and parameters. 

.. figure:: Figures/turtleUMLClassDiagram.png
    :width: 300px
    :align: center
    :alt: Turtle class diagram
    :figclass: align-center

    Figure 1: Turtle Class Diagram


|Groupwork| Programming Challenge : Draw two letters
-------------------------------------------------

Write code in the editor window below (or use the |repl link|) to create  2 turtles to draw 
a pair of simple block-style letters that use just straight lines (no curves or diagonals). 
Each turtle should draw a different letter at a different location.  
Go back to the previous lesson and look over the various Turtle constructors if you forget how to create a turtle at a particular x,y location.

Here are some simple turtle methods that you can use:

- ``forward();``
- ``turnLeft();``
- ``turnRight();``
- ``backward();``
- ``penUp();``
- ``penDown();``


.. activecode:: challenge2-3-Turtle_Letter
    :language: java
    :autograde: unittest
    :datafile: turtleClasses.jar

    
    ~~~~
    import java.util.*;
    import java.awt.*;

    public class TurtleLetter
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
            super("TurtleLetter");
        }

        @Test
        public void test1()
        {
            String code = getCode();
            String expect = "new Turtle(";

            int count = countOccurences(code, expect);

            boolean passed = count >= 2;
            passed = getResults("2+ Turtles", "" + count  + " Turtles", "Add two Turtles", passed);
            assertTrue(passed);
        }

        @Test
        public void test2()
        {
            String code = getCode();
            String[] lines = code.split("\n");

            boolean passed = lines.length >= 20;
            passed = getResults("20 or more lines", lines.length + " lines", "Adding a reasonable amount of lines to code", passed);
            assertTrue(passed);
        }
    }


You may notice that it is challenging to have your turtles draw with these simple methods, which do
not have formal parameters (there is nothing between the left and right parenthesis). 
In the next lesson, we will use more complex methods that include formal parameters,
where you can indicate how many pixels the turtle should move or what angle to turn!


Summary
-------------------

- **Methods** are a set of instructions that define the behaviors for all objects of the class.

- Use **dot notation** to execute an object's method.  This is the object's name followed by the dot (.) operator followed by the method name and parentheses: **object.method();**

- A **method signature** is the method name followed by the parameter list which gives the type and name for each parameter. Note that methods do not have to take any parameters, but you still need the parentheses after the method name.

- **Procedural abstraction** allows a programmer to use a method by knowing in general what it does without knowing what lines of code execute. This is how we can drive a car without knowing how the brakes work.

- A **method** or **constructor** call interrupts the sequential execution of statements, causing the program to first execute the statements in the method or constructor before continuing. Once the last statement in the method or constructor has executed or a return statement is executed, the flow of control is returned to the point immediately following the method or constructor call.

- An **object method** or **non-static method** is one that must be called on an object of a class.  It usually works with the object's attributes.

- A **static method** or **class method** method is one that doesn't need to be called on an object of a class.
