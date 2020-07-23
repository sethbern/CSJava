.. qnum::
   :prefix: 5-1-
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
    
Writing Methods
=================

Up until this unit, you wrote all  code in the main method, 
but now you will be writing multiple methods. Why have multiple methods instead of just one? 
**Procedural Abstraction** allows us to name a block of code as a method and 
call it whenever we need it, abstracting away the details of how it works.  
This serves to organize our code by function and reduce its complexity and reduce 
the repetition of code. In addition, it helps with debugging and maintenance since 
changes to that block of code only need to happen in one place. 
Here are some of the main reasons to use multiple methods in your programs:

- Organization and Reducing Complexity: organize your program into small sections of code by function to reduce its complexity. Divide a problem into subproblems to solve it a piece at a time.
- Reusing Code: avoid repetition of code. Reuse code by putting it in a method and calling it whenever needed.
- Maintainability and Debugging: smaller methods are easier to debug and understand than searching through a large main method.

Let's look at an example with lots of repetition of code and 
create methods to reduce the repetition of code. 


|Exercise| Check Your Understanding

.. clickablearea:: repeatedcode_methods
    :question: Click on all the lines that are completely identical and repeated.
    :iscode:
    :feedback: Look for lines that are completely identical.  

    :click-incorrect:public static void main(String args[]) {:endclick:
        :click-incorrect:System.out.println("This old man, he played one.");:endclick:
        :click-incorrect:System.out.println("He played knick knack on my thumb. ");:endclick:
        :click-correct:System.out.println("With a knick knack paddy whack, give a dog a bone.");:endclick:
        :click-correct:System.out.println("This old man came rolling home.");:endclick:
        :click-incorrect:System.out.println("This old man, he played two.");:endclick:
        :click-incorrect:System.out.println("He played knick knack on my shoe. ");:endclick:
        :click-correct:System.out.println("With a knick knack paddy whack, give a dog a bone.");:endclick:
        :click-correct:System.out.println("This old man came rolling home.");:endclick:
    :click-incorrect:}:endclick:
            
Did you find some repeated lines of the This Old Man song? 
You may have noticed that the chorus is 
repeated "With a knick knack paddy whack, give a dog a bone. This old man came rolling home." 
When you see repeated code, that is a signal for you to make a new method!

A method is a **named** list of statements.  When we want to execute the list of statements, 
we call the method using its name.
In the next unit you will create methods that are called using an object, 
referred to as **instance methods**.
The methods in this unit are called without an object, so they are  **static methods**.  
Static methods are also referred to as class methods.


.. figure:: Figures/methodsignature.png
    :width: 400px
    :align: center
    :figclass: align-center

    Figure 1: Method Header(Signature) and Method Body
  

There are two steps to creating and calling a static method:

1. **Method Definition**:  write the method's **header** and **body**.  The header is also called 
a method *signature*.  The parts of the *main* method header are shown in Figure 1, which include an access modifier,
static modifier, return type, name, and formal parameters.   The method body 
consists of a set of statements enclosed in curly braces { }.  
Another example method named *methodName* that has no formal parameters is shown below.  

    .. code-block:: java

        // Step 1: Define the method in a class
        // method header
        public static void methodName() 
        { 
              // method body 
        }


2. **Method Call**: whenever you want to use the method, call methodName();  The statements in the method body
will be executed.  

    .. code-block:: java

       // Step 2: call the method
       methodName(); 


For example, here is a chorus() method definition 
that we could write for the "This Old Man Song" to encapsulate the two lines that get repeated.   
The main method can call ``chorus();`` anytime we want
the two print statements in the method body to be executed.

.. code-block:: java
     
        public static void chorus() 
        { 
              System.out.println("With a knick knack paddy whack, give a dog a bone.");
              System.out.println("This old man came rolling home.");
        }
        
   
|CodingEx| **Coding Exercise**


.. activecode:: Song1_methods
  :language: java   
  :autograde: unittest    
  :practice: T

  Run the following code to see the song This Old Man print out.  
  Notice the third line of code in the main method
  is a call to the new method chorus().
  Can you replace the last two lines in the second verse in the main 
  method with another call to the chorus() method? 
  Step through using on the Code Lens button to see how the main method calls the chorus method.
  ~~~~
  public class Song 
  { 
    // The chorus method
    public static void chorus() 
    {
       System.out.println("With a knick knack paddy whack, give a dog a bone.");
       System.out.println("This old man came rolling home.");
    }
    
    public static void main(String args[]) 
    {
      System.out.println("This old man, he played one.");
      System.out.println("He played knick knack on my thumb. ");
      chorus();

      System.out.println("This old man, he played two.");
      System.out.println("He played knick knack on my shoe. ");
      // Can you replace these 2 lines with a method call to chorus()?
      System.out.println("With a knick knack paddy whack, give a dog a bone.");
      System.out.println("This old man came rolling home.");
    }
  }
  ====
  import static org.junit.Assert.*;
    import org.junit.*;;
    import java.io.*;
    
    public class RunestoneTests extends CodeTestHelper
    {
        @Test
        public void testMain() throws IOException
        {
            String output = getMethodOutput("main");
            String expect = "This old man, he played one.\nHe played knick knack on my thumb.  \nWith a knick knack paddy whack, give a dog a bone.\nThis old man came rolling home.\nThis old man, he played two.\nHe played knick knack on my shoe. \nWith a knick knack paddy whack, give a dog a bone.\nThis old man came rolling home.";
            boolean passed = getResults(expect, output, "Expected output from main");
            assertTrue(passed);
        }

        @Test
        public void testChangedCode() {
            String origCode = "public class Song{ // The chorus method public static void chorus() { System.out.println(\"With a knick knack paddy whack, give a dog a bone.\"); System.out.println(\"This old man came rolling home.\"); }  public static void main(String args[])  {  Song mySong = new Song();  System.out.println(\"This old man, he played one.\");  System.out.println(\"He played knick knack on my thumb. \");  chorus();  System.out.println(\"This old man, he played two.\");  System.out.println(\"He played knick knack on my shoe. \");  // Can you replace these 2 lines with a method call to chorus()?  System.out.println(\"With a knick knack paddy whack, give a dog a bone.\");  System.out.println(\"This old man came rolling home.\")  }  }";

            boolean changed = codeChanged(origCode);

            assertTrue(changed);

        }

        @Test
        public void testcodeContains(){
          int count = countOccurences(getCode(),"chorus();");
          boolean passed = count > 1;
          passed = getResults("> 1 chorus call",  count  + " chorus call(s)", "Added a call to chorus?", passed);
          assertTrue(passed);
        }

    }
  

Here is another song with a repeated chorus. 
The Song's print method calls the chorus() and animal() methods to help it 
print out the whole song. 

When you call the chorus() method, it skips to the chorus code, 
executes and prints out the chorus, and then returns back to the method 
that called it.  

.. codelens:: songviz2
    :language: java 
    :optional:
    
    public class OldMacDonald
    {
        
      public static void chorus()
      {
        System.out.println("E-I-E-I-O");
      }

      public static void animal() 
      {
        System.out.println("duck");
      }
        
      public static void main(String[] args) 
      {
        System.out.println("Old MacDonald had a farm");
        chorus();
        System.out.print("And on that farm he had a ");
        animal();
        chorus();
      }
    }
    

|Exercise| **Check your understanding**

.. mchoice:: songMethods
   :practice: T
   :answer_a: I like to eat eat eat.
   :answer_b: I like to eat eat eat fruit.
   :answer_c: I like to apples and bananas eat.
   :answer_d: I like to eat eat eat apples and bananas!
   :answer_e: Nothing, it does not compile.
   :correct: d
   :feedback_a: Try tracing through the print method and see what happens when it calls the other methods.
   :feedback_b: There is a fruit() method but it does not print out the word fruit.
   :feedback_c: The order things are printed out depends on the order in which they are called from the print method.
   :feedback_d: Yes, the print method calls the consume method 3 times and then the fruit method to print this.
   :feedback_e: Try the code in an active code window to see that it does work.

   What does the following code print out?

   .. code-block:: java

      public class Song 
      {
        
        public static void fruit()
        {
            System.out.println("apples and bananas!");
        }

        public static void consume() 
        {
           System.out.print("eat ");
        }
        
        public static void main(String[] args) 
        {
            System.out.print("I like to ");
            consume();
            consume();
            consume();
            fruit();
        }
    }


Summary
-------

- **Procedural Abstraction** (creating methods) reduces the complexity and repetition of code. We can name a block of code as a method and call it whenever we need it, abstracting away the details of how it works.  

- A programmer breaks down a large problem into smaller subproblems by creating methods to solve each individual subproblem.

- To write a method, write a **method definition** with a **method signature** like "public void chorus()" and a **method body** that consists of statements nested within {}.

- Call the method using its name to execute the statements in the method body.