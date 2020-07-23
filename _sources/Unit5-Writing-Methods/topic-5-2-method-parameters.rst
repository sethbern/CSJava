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
    
Method Parameters
-----------

You may have noticed more repetition in the **This old man** song. What about the lines of each verse? 
Notice that every word is repeated except the last ones that include a number 
and a rhyme such as one/thumb and two/shoe.

.. code-block:: java

    System.out.println("This old man, he played one.");
    System.out.println("He played knick knack on my thumb.");
    ...
    System.out.println("This old man, he played two.");
    System.out.println("He played knick knack on my shoe.");


We can make methods even more powerful and more abstract by giving them 
parameters for data that they need to do their job. 
We can make a method called verse take two values: the number and the rhyme to print!   
The verse method header needs to define two **formal parameter** variables to accept the values. 

.. code-block:: java

    public static void verse(String number, String rhyme)
    {
       System.out.println("This old man, he played " + number);
       System.out.println("He played knick knack on my " + rhyme);
    }


When you call the verse method to do its job, 
you need to pass in **arguments** or **actual parameters** whose values are 
copied into the formal parameter variables. 

Figure 2 shows how the actual arguments in the method call ``verse("one","thumb");`` are copied into the formal parameter variables.
The method body statements use the parameter variables to customize the print statements each time the method is called.

.. figure:: Figures/argumentpassing.png
    :width: 500px
    :align: center
    :alt: Arguments to Parameters
    :figclass: align-center

    Figure 2: Matching Actual Arguments to Formal Parameters 

    
.. |visualizer| raw:: html

   <a href="http://www.pythontutor.com/visualize.html#code=public%20class%20Song%20%0A%20%20%7B%20%0A%20%20%20%20%0A%20%20%20%20/**%20Verse%0A%20%20%20%20%20*%20%40param%20number%20-%20a%20String%20like%20%22one%22,%20%22two%22,%20etc.%0A%20%20%20%20%20*%20%40param%20rhyme%20-%20a%20String%20like%20%22thumb%22,%20%22shoe%22,%20etc.%0A%20%20%20%20%20*/%0A%20%20%20%20%20public%20void%20verse%28String%20number,%20String%20rhyme%29%0A%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20System.out.println%28%22This%20old%20man,%20he%20played%20%22%20%2B%20number%29%3B%0A%20%20%20%20%20%20%20System.out.println%28%22He%20played%20knick%20knack%20on%20my%20%22%20%2B%20rhyme%29%3B%0A%20%20%20%20%20%7D%0A%20%20%20%20%20%0A%20%20%20%20//%20The%20chorus%20method%0A%20%20%20%20public%20void%20chorus%28%29%20%0A%20%20%20%20%7B%0A%20%20%20%20%20%20%20System.out.println%28%22With%20a%20knick%20knack%20paddy%20whack,%20give%20a%20dog%20a%20bone.%22%29%3B%0A%20%20%20%20%20%20%20System.out.println%28%22This%20old%20man%20came%20rolling%20home.%22%29%3B%0A%20%20%20%20%7D%0A%20%20%20%20%0A%20%20%20%20%0A%20%20%20%20public%20static%20void%20main%28String%20args%5B%5D%29%20%0A%20%20%20%20%7B%0A%20%20%20%20%20%20Song%20mySong%20%3D%20new%20Song%28%29%3B%0A%20%20%20%20%20%20mySong.verse%28%22one%22,%20%22thumb%22%29%3B%0A%20%20%20%20%20%20mySong.chorus%28%29%3B%0A%20%20%20%20%20%20mySong.verse%28%22two%22,%20%22shoe%22%29%3B%0A%20%20%20%20%20%20mySong.chorus%28%29%3B%0A%20%20%20%20%7D%0A%20%20%7D&cumulative=false&curInstr=24&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=java&rawInputLstJSON=%5B%5D&textReferences=false&curInstr=0" target="_blank"  style="text-decoration:underline">Java visualizer</a>
   
|CodingEx| **Coding Exercise**


.. activecode:: Song2_methods
  :language: java
  :autograde: unittest    
  :practice: T

  Run the following code to see the song This Old Man print out using the verse and 
  chorus methods.  Use the CodeLens tool to watch how the actual arguments are passed into the 
  formal parameters each time the verse method is called. Can you add verse three with the rhyme "knee"? 
  Can you add verse four with the rhyme "door"? How many verses do you know?
  ~~~~
  public class Song 
  { 
    
    /** Verse - prints out a verse of the song
     * @param number - a String like "one", "two", etc.
     * @param rhyme - a String like "thumb", "shoe", etc.
     */
     public static void verse(String number, String rhyme)
     {
       System.out.println("This old man, he played " + number);
       System.out.println("He played knick knack on my " + rhyme);
     }
     
    // The chorus method
    public static void chorus() 
    {
       System.out.println("With a knick knack paddy whack, give a dog a bone.");
       System.out.println("This old man came rolling home.");
    }
    
    public static void main(String args[]) 
    {
      verse("one", "thumb");
      chorus();
      verse("two", "shoe");
      chorus();
    }
  }
  ====
  import static org.junit.Assert.*;
    import org.junit.*;;
    import java.io.*;
   
    public class RunestoneTests extends CodeTestHelper
    {
        @Test
        public void testThree() 
        {
            boolean passed = checkCodeContains("verse three", "verse(\"three\", \"knee\");");
            assertTrue(passed);
        }

        @Test
        public void testFour() 
        {
            boolean passed = checkCodeContains("verse four", "verse(\"four\", \"door\");");
            assertTrue(passed);
        }
    }
  

When a method is called, the right method definition is found by 
checking the **method signature** or **header** at the top of the method 
definition to match the method name, the number of arguments, the data 
types for the arguments and the return type. 


Java uses **Call by Value** when it passes arguments to methods. This means that a copy of the value in the argument is saved in the parameter variable. If the parameter variable changes its value inside the method, the original value outside the method is not changed.

If you pass in an argument that holds a reference to an object, 
like a String or Person or Turtle object, a copy of this reference 
is passed in and saved in the parameter variable. You will explore 
this more in the following unit.
    
Methods can also return values of any type back to the calling method. 
The calling method should do something with this return value, 
like printing it out or saving it in a variable. Try the problems below to practice with a String method that takes a parameter and returns a boolean value.

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

.. activecode:: challenge-5-6-song
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

.. mchoice:: AP5-6-1
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
        


.. mchoice:: AP5-6-2
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
   