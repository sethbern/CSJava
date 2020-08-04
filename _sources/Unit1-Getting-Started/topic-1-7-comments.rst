.. qnum::
   :prefix: 1-7-
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

There is also a special version of the multi-line comment, ``/**``  ``*/``, called the documentation comment. 
Java has a cool tool called |javadoc| that will pull out all of these 
comments to make documentation of a class as a web page.  

|Exercise| **Check your understanding**

.. dragndrop:: q1_7_1
    :feedback: Review the section above.
    :match_1: single-line comment|||//
    :match_2: multi-line comment|||/* */
    :match_3: Java documentation comment|||/** */
    
    Drag the definition from the left and drop it on the correct symbols on the right.  Click the "Check Me" button to see if you are correct.
    

The compiler will skip over comments, and they don't affect how your program runs. 
They are for you and other programmers working with you.  


 