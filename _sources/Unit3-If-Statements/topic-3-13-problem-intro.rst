Introduction to Problem Types
===============================

Please read the following, watch the videos, and try to solve the problems.


Solving Mixed-up Code Problems
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

If you see a problem like the one below you will need to put the mixed-up
code in the correct order on the right side. You may need to indent the blocks as well.  There may also be extra blocks that are not
needed in a correct solution that you can leave on the left side. Click the "Check" button
to check your solution.

See the video below for an example.

.. youtube:: 0x4yWQ9ZJAg
    :divid: iwgex1-parsons1-java
    :optional:
    :width: 650
    :height: 415
    :align: center

Try to solve the following mixed-up code problem.  This problem doesn't require any indentation.

.. parsonsprob:: intro-simple-parsons-no-indent-java
   :numbered: left
   :adaptive:
   :practice: T
   :order: 3, 1, 2, 0

   Drag the blocks from the left and put them in the correct order on the right. The text in each block
   defines the order.
   -----
   First block
   =====
   Second block
   =====
   Third block

Try to solve the following mixed-up code problem. This problem requires indentation.

.. parsonsprob:: intro-simple-parsons-indent-java
   :numbered: left
   :adaptive:
   :practice: T
   :order: 3, 1, 2, 0

   Drag the blocks from the left and put them in the correct order on the right with the correct indentation.
   The text in each block defines the order and indentation.
   -----
   First block
   =====
   Second block
   =====
       Third block that needs to be indented

Try to solve the following mixed-up code problem. This problem requires indentation and has extra blocks that are not needed in a correct solution.

.. parsonsprob:: intro-simple-parsons-indent-with-dist-java
   :numbered: left
   :adaptive:
   :practice: T
   :order: 3, 1, 2, 0

   Drag the blocks from the left and put them in the correct order on the right with the correct indentation.
   There is an extra block that is not needed in the correct solution.
   -----
   First block
   =====
   Second block
   =====
   Extra block that is not needed #paired: This block is not needed
   =====
       Third block that needs to be indented

The mixed-up code problems have a "Help me" button at the bottom of the
problem. Once you have checked at least three incorrect solutions you can
click the button for help.  It will remove an incorrect code block, if you used
one in your solution, or combine two blocks into one if there are more
than three blocks left.

See the video below for an example.

.. youtube:: jkKp9V_Z22E
    :divid: iwgex1-parsons2-java
    :optional:
    :width: 650
    :height: 415
    :align: center

Solving Write Code Problems
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

If you see a problem like the one below, you will need to write code.  The problem
will have unit tests that you can run to check that your code is working
correctly.  Click on the "Run" button to compile and run your code.  Look after
the code area for compiler errors and/or unit test results.

See the video below for an example.

.. youtube:: tQZrw8yUiSs
    :divid: java-write-code-video-ex
    :optional:
    :width: 650
    :height: 415
    :align: center

.. chapter:: Unit3-If-Statements
.. subchapter:: topic-3-13-problem-intro

Finish writing the code for the following problem.

.. activecode:: intro-sample-write-code-double-csjava-intro
    :practice: T
    :autograde: unittest
    :language:java

    Write a function that takes a number ``num`` and returns the number times 2. For example, ``double(2)`` should return 4 and
    ``double(-1)`` should return -2.  Look below the code to check for any compiler errors or the results from the test cases.  Be sure to ``return`` the result.
    ~~~~
    public class Main {

        // Function to double a number
        public static int doubleNum(int num) {
            // ADD CODE HERE //

        }

        public static void main(String[] args)
        {
            System.out.println(tripleNum(3));
            System.out.println(tripleNum(-4));
            System.out.println(tripleNum(0));
        }
    }
    ====
    import static org.junit.Assert.*;
    import org.junit.Test;
    import java.io.IOException;
    import java.util.Arrays;

    public class RunestoneTests extends CodeTestHelper {
        public RunestoneTests() {
            super();
        }

        @Test
        public void testBoundarySum() throws IOException {
                String output = getMethodOutput("main");
                String expect = "6, -8, 0";
            boolean passed = getResults(expect, output, "Expected output from main");
            assertTrue(passed);

        }
    }



Solving Write Code Problems with Pop-Up Mixed-up Code Puzzles to Help
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
If you see a problem like the one below, you will need to write code. You can go to the **toggle bar** above the problem description to open a mixed-up puzzle that will help you write the code. 
The mixed-up puzzle will have blocks of code that you can drag and drop to create a solution. You can also use the "Help me" button to get additional assistance within the puzzle if needed.


.. youtube:: MsGDozb0jsk
    :optional:
    :divid: write-code-toggle-java
    :width: 780
    :height: 498
    :align: center


.. selectquestion:: intro-sample-toggle-java
    :fromid: intro-sample-write-code-triple-csjava, intro-sample-puzzle-triple-csjava
    :toggle: lock



What to do next
===============

.. raw:: html

    <p>
      Click on the following link to take the pre test before the practice:
      <b>
        <a href="topic-3-13-experiment-pretest.html">
          <font size="+1">Pre Test</font>
        </a>
      </b>
    </p>