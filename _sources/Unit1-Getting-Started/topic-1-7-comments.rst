.. qnum::
   :prefix: 1-7-
   :start: 1
   
   
Comments
---------

Adding comments to your code helps to make it more readable and maintainable. 
In the commercial world, software development is usually a team effort where many 
programmers will use your code and maintain it for years. Commenting is essential in this kind of 
environment and a good habit to develop. Comments will also help you to remember what you 
were doing when you look back to your code a month or a year from now.

There are 3 types of comments in Java:

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

There is also a special version of the multi-line comment, ``/**``  ``*/``, called the documentation comment. Java has a cool tool called |javadoc| that comes with the |Java JDK| that will pull out all of these comments to make documentation of a class as a web page.  This tool generates the official Java documentation too, for example for the |String class|. 
It's a good idea to use the documentation comment in front of classes, methods, and instance variables in case you want ot use this tool. 

|Exercise| **Check your understanding**

.. dragndrop:: comments
    :feedback: Review the section above.
    :match_1: single-line comment|||//
    :match_2: multi-line comment|||/* */
    :match_3: Java documentation comment|||/** */
    
    Drag the definition from the left and drop it on the correct symbols on the right.  Click the "Check Me" button to see if you are correct.
    

The compiler will skip over comments, and they don't affect how your program runs. 
They are for you  and other programmers working with you.  Here are some examples of good commenting:

.. code-block:: java 

    /**
    * MyClass.java
    * @author My Name
    * @since Date 
    * This class keeps track of the max score.
    */   
    public class MyClass() 
    {
       
       // The shippingCost() method prints  shipping cost based on the weight 
       public static void shippingCost(int weight) {  ..... }

    }


There are some special tags that you can use in Java documentation. 
These are not required but many programmers use them. Here are some common tags:

- @author  Author of the program
- @since   Date released
- @version Version of program 
- @param   Parameter of a method
- @return  Return value for a method


Note that most IDEs will tend to show comments formatted in italics -- to make them easier to spot.

 