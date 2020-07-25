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
------------------

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
but the method will need two **formal parameters**, which are placeholders that allow different values to be substituted for the animal and noise each time the method is called. 
The method body will use the formal parameter variables to customize the 
print statements.
When the method is called, 
you must provide values for the animal and noise, called **actual arguments** or **actual parameters**, that are 
copied into the formal parameter variables. 

Figure 1 shows how the actual argument values in the method call ``verse("cow","moo");`` are copied 
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
  Rerun the program to confirm the program works.
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

The class listed in Figure 2 above has 3 methods named **mystery**.  While the 3 methods all have the same method name,
notice that either the type of the formal parameter is different, or the number of formal parameters is different.
This is called **overloading**, since the name **mystery** is associated with more
than one method body.    The print output shown in the upper right section of Figure 2 is produced by 3 calls to mystery in the main method, which have been erased.

.. parsonsprob:: methodargsparson
   :numbered: left
   :adaptive:
   :noindent:

   The main method needs 3 method calls to produce the output shown in Figure 2.
   Drag the needed blocks from the left area into the correct order  in the right area
   to produce the expected output:  
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


Java uses **Call by Value** when it passes arguments to methods. 
This means that a copy of the value in the argument is saved in the parameter variable. 
If the parameter variable changes its value inside the method, 
the original value outside the method is not changed.

If you pass in an argument that holds a reference to an object, 
like a String or Person or Turtle object, a copy of this reference 
is passed in and saved in the parameter variable. You will explore 
this more in the following unit.
    
Methods can also return values of any type back to the calling method. 
The calling method should do something with this return value, 
like printing it out or saving it in a variable. 
Try the problems below to practice with a String method that takes a parameter and returns a boolean value.


Practice
-------------

.. mchoice:: AP2-4-1
    :practice: T

    Consider the following methods:
    
    .. code-block:: java

        public void inchesToCentimeters(double i)
        {
            double c = i * 2.54;
            printInCentimeters(i, c);
        }

        public void printInCentimeters(double inches, double centimeters)
        {
            System.out.print(inches + "-->" + centimeters);
        }

    Assume that the method call ``inchesToCentimeters(10)`` appears in a method in the same class. What is printed as a result of the method call?
    
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
    
    Consider the following methods, which appear in the same class.

    .. code-block:: java
    
        public void splitPizza(int numOfPeople)
        {
            int slicesPerPerson = 8/numOfPeople;
            /* INSERT CODE HERE */
        }

        public void printSlices(int slices)
        {
            System.out.println("Each person gets " + slices + " slices each");
        }

    Which of the following lines would go into ``/* INSERT CODE HERE */`` in the method splitPizza in order to call the ``printSlices`` method to print the number of slices per person correctly? 
    
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





Tracing Methods
-----------------

You will not write your own methods until Unit 5, but you should be able to trace and interpret method calls like below. 


|Exercise| **Check your understanding**

.. mchoice:: traceMethods
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
   :feedback_e: Try the code in the visualizer link below.
   
   What does the following code print out?
   
   .. code-block:: java
   
      public class MethodTrace 
      {
        public void square(int x)
        {
            System.out.print(x*x);
        }
        public void divide(int x, int y)
        {
            System.out.println(x/y);
        }
        public static void main(String[] args) {
            MethodTrace traceObj = new MethodTrace();
            traceObj.square(5);
            System.out.print(" and ");
            traceObj.divide(4,2);
        }
       }











|CodingEx| **Coding Exercise**



.. activecode:: StringFind_method
  :language: java
  :autograde: unittest    
  :practice: T

  Run the following program which contains a method called findLetter that takes a letter and a text as parameters and uses a loop to see if that letter is in the text and returns true if it is, false otherwise. Give the variables ``letter`` and ``text`` new values in the main method and run it again to try finding a different letter. Then, change the code of the findLetter method to return how many times it finds letter in text, using a new variable called ``count``. How would the return type change?
  ~~~~
  public class StringFind 
  { 
    /** findLetter looks for a letter in a String
     * @param String letter to look for
     * @param String text to look in
     * @return boolean true if letter is in text
     * After running the code, change this method to return 
     * an int count of how many times letter is in the text. 
     */
     public boolean findLetter(String letter, String text)
     {
        boolean flag = false;
        for(int i=0; i < text.length(); i++) {
            if (text.substring(i, i+1).equalsIgnoreCase(letter))
	        {
                flag = true;
	        }
        }
        return flag;
     }
    public static void main(String args[]) 
    {
      StringFind test = new StringFind();
      String message = "Apples and Oranges";
      String letter = "p";
      System.out.println("Does " + message +  " contain a " + letter + "?");
      System.out.println( test.findLetter(letter, message) ); 
    }
  }
  ====
  import static org.junit.Assert.*;
    import org.junit.*;;
    import java.io.*;

    public class RunestoneTests extends CodeTestHelper
    {
        @Test
        public void tryfindLetter() throws IOException
        { 
           String message = "Apples and Oranges";
           String letter = "p";
           Object[] args = {letter,message};
           String output = getMethodOutput("findLetter", args);
           String expect = "2";

           boolean passed = getResults(expect, output, 
                    "findLetter(\"p\",\"Apples and Oranges\")");
           assertTrue(passed);
        }

         @Test
        public void tryfindLetter2() throws IOException
        { 
           String message = "Test strings";
           String letter = "s";
           Object[] args = {letter,message};
           String output = getMethodOutput("findLetter", args);
           String expect = "3";

           boolean passed = getResults(expect, output, 
                    "findLetter(\"s\",\"Test strings\")");
           assertTrue(passed);
        }
        @Test
        public void test2() 
        {
            boolean passed = checkCodeContains("changed return type of findLetter", "public int findLetter(String letter, String text)");
            assertTrue(passed);
        }

         @Test
        public void test1() 
        {
            boolean passed = checkCodeContains("variable count set to 0", "int count = 0;");
            assertTrue(passed);
        }

         @Test
        public void test3() 
        {   String code = getCode();
            boolean passed = code.contains("count++;") || 
            code.contains("count = count + 1;") || code.contains("count = 1 + count;") || code.contains("count += 1;") || code.contains("++count;");
            passed = getResults("count incremented",Boolean.toString(passed),"Count incremented?", passed);
            assertTrue(passed);
        }
    }
  
|Groupwork| Programming Challenge : Song with Parameters
---------------------------------------------------------

.. |The Ants Go Marching| raw:: html

   <a href="https://www.lyrics.com/lyric/5526512/The+Ants+Go+Marching" target="_blank">The Ants Go Marching</a>

Here's another song, |The Ants Go Marching|, that is very similar to the This Old Man song in its repetitive structure. 

.. raw:: html
  
   <pre>
    The ants go marching one by one, hurrah, hurrah
    The ants go marching one by one, hurrah, hurrah
    The ants go marching one by one
    The little one stops to suck his thumb
    And they all go marching down to the ground

    The ants go marching two by two, hurrah, hurrah
    The ants go marching two by two, hurrah, hurrah
    The ants go marching two by two
    The little one stops to tie his shoe
    And they all go marching down to the ground

    The ants go marching three by three, hurrah, hurrah
    The ants go marching three by three, hurrah, hurrah
    The ants go marching three by three
    The little one stops to climb a tree
    And they all go marching down to the ground
    </pre>

1. Print out the |The Ants Go Marching| song and circle the repeated parts of the song.

2. In the active code window below, create a method or methods that takes parameters to print out a verse. The method(s) should be abstract enough to work for all 3 verses.  Use good commenting for your methods that describe the @param. For the autograder, make sure you create a method called verse that takes 2 parameters. 

3. In the main method, create an object of the class and call the method(s) you created in the last step to print out 3 verses of the song. Can you add more verses?

.. activecode:: challenge-5-6-songb
  :language: java
  :autograde: unittest  

  Create method(s) with parameters to print out verses of the song The Ants Go Marching. https://www.lyrics.com/lyric/5526512/The+Ants+Go+Marching
  ~~~~
  public class Song 
  { 
    // Create at least 1 method called verse that takes 2 parameters
    // that can be used to print out the verses of the song The Ants Go Marching
    
    
    public static void main(String args[]) 
    {
      // Create a Song object and call its method(s) to print out 
      // the verses of The Ants Go Marching
      // There should be atleast 1 method called verse that takes 2 arguments.
    
    
    }
  }
  ====
  import static org.junit.Assert.*;
    import org.junit.*;;
    import java.io.*;
    
    public class RunestoneTests extends CodeTestHelper
    {
      @Test
      public void checkCodeContains1(){
        //check verse 1
        boolean passed = checkCodeContains("verse method call with 2 arguments for verse 1", "verse(\"one\", \"suck his thumb\"");
        assertTrue(passed);
      }

      @Test
      public void checkCodeContains2(){
         //check verse 2
          boolean passed = checkCodeContains("verse method call with 2 arguments for verse 2", "verse(\"two\", \"tie his shoe\"");
        assertTrue(passed);
      }

      @Test
      public void checkCodeContains3(){
         //check verse 3
          boolean passed = checkCodeContains("verse method call with 2 arguments for verse 3", "verse(\"three\", \"climb a tree\"");
        assertTrue(passed);  
      }

          @Test
        public void testMain() throws IOException
        {
            String output = getMethodOutput("main");
            String expect = "The ants go marching three by three\nThe little one stops to climb a tree";
            boolean passed = output.contains(expect);
            getResults(expect, output, "Expected output from main contains 3 verses");
            assertTrue(passed);
        }
    }

    



Practice
-----------

.. mchoice:: AP5-6-1a
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
        


.. mchoice:: AP5-6-2b
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
-------

- **Procedural Abstraction** (creating methods) reduces the complexity and repetition of code. We can name a block of code as a method and call it whenever we need it, abstracting away the details of how it works.  

- A programmer breaks down a large problem into smaller subproblems by creating methods to solve each individual subproblem.

- To write methods, write a **method definition** with a **method signature** like "public void chorus()" and a **method body** in {} and method calls using an object.the method name and arguments whenever you need it to do its job.

- To call an object's method, you must use the object name and the dot (.) operator followed by the method name, for example **object.method();** 


- When you call a method, you can give or pass in **arguments** or **actual parameters** to it inside the parentheses **object.method(arguments)**. The arguments are saved in local **formal parameter** variables that are declared in the method header, for example: public void method(type param1, type param2) { ... }.

- Values provided in the arguments in a method call need to correspond to the order and type of the parameters in the method signature.

- When an actual parameter is a primitive value, the formal parameter is initialized with a copy of that value. Changes to the formal parameter have no effect on the corresponding actual parameter.

- When an actual parameter is a reference to an object, the formal parameter is initialized with a copy of that reference, not a copy of the object. The formal parameter and the actual parameter are then aliases, both refering to the same object.

-  When an actual parameter is a reference to an object, the method or constructor could use this reference to alter the state of the original object. However, it is good programming practice to not modify mutable objects that are passed as parameters unless required in the specification.
   