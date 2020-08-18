.. qnum::
   :prefix: 9-6-
   :start: 1

   
Multiple Choice Exercises
=================================

Easier Multiple Choice Questions
----------------------------------


.. mchoice:: q9_6_1
   :practice: T
   :answer_a: 2
   :answer_b: 4
   :answer_c: 8
   :correct: b
   :feedback_a: The size of outer array is the number of rows.  Remember that two-dimensional arrays are actually an array of arrays in Java.
   :feedback_b: The size of the inner array is the number of columns.
   :feedback_c: This is the total number of items in the array.

   How many columns does ``a`` have if it is created as follows ``int[][] a = { {2, 4, 6, 8}, {1, 2, 3, 4}};``?	
   
You can see how the array looks by clicking on the following `Ex-9-7-1 <http://cscircles.cemc.uwaterloo.ca/java_visualize/#code=public+class+ClassNameHere+%7B%0A+++public+static+void+main(String%5B%5D+args)+%7B%0A++++++%0A++++++int%5B%5D%5B%5D+a+%3D+%7B%7B2,+4,+6,+8%7D,+%7B1,+2,+3,+4%7D%7D%3B%0A++++++System.out.println(a%5B0%5D%5B0%5D)%3B%0A++++++System.out.println(a%5B0%5D%5B1%5D)%3B%0A++++++System.out.println(a%5B0%5D%5B2%5D)%3B%0A++++++System.out.println(a%5B0%5D%5B3%5D)%3B%0A++++++System.out.println(a%5B1%5D%5B0%5D)%3B%0A++++++System.out.println(a%5B1%5D%5B1%5D)%3B%0A++++++System.out.println(a%5B1%5D%5B2%5D)%3B%0A++++++System.out.println(a%5B1%5D%5B3%5D)%3B%0A++++++%0A++++++%0A+++%7D%0A%7D&mode=display&curInstr=0>`_.

.. mchoice:: q9_6_2
   :practice: T
   :answer_a: <code>strGrid[0][2] = "S";</code>
   :answer_b: <code>strGrid[1][3] = "S";</code>
   :answer_c: <code>strGrid[3][1] = "S";</code>
   :answer_d: <code>strGrid[2][0] = "S";</code> 
   :answer_e: <code>strGrid[0][0] = "S";</code>
   :correct: d  
   :feedback_a: The code <code>letterGrid[0][2] = "S";</code> actually sets the 1st row and 3rd column to hold a reference to the <code>String</code> object "S".
   :feedback_b: This would be true if row and column indicies started at 1 instead of 0 and if this was in column major order. 
   :feedback_c: This would be true if row and column indicies started at 1 instead of 0.  
   :feedback_d: In row-major order the row is specified first followed by the column.  Row and column indicies start with 0.  So <code>letterGrid[2][0]</code> is the 3rd row and 1st column. 
   :feedback_e: This would set the element at the first row and column.   

   Which of the following statements assigns the letter S to the third row and first column of a two-dimensional array named ``strGrid`` (assuming row-major order).
   
.. mchoice:: q9_6_3
   :practice: T
   :answer_a: a[0][3]
   :answer_b: a[1][3]
   :answer_c: a[0][2]
   :answer_d: a[2][0]
   :answer_e: a[3][1]
   :correct: c
   :feedback_a: This would be true if the row index started at 0, but the column index started at 1.
   :feedback_b: Both the row and column indicies start with 0.  
   :feedback_c: The value 6 is at row 0 and column 2.  
   :feedback_d: The row index is specified first, then the column index.
   :feedback_e: The row index is specified first and the indicies start at 0.  

   How would you get the value 6 out of the following array ``int[][] a = { {2, 4, 6, 8}, {1, 2, 3, 4}};``?
   


Medium Multiple Choice Questions
----------------------------------


.. mchoice:: q9_6_4
   :practice: T
   :answer_a: 4
   :answer_b: 8
   :answer_c: 9
   :answer_d: 12
   :answer_e: 10
   :correct: b
   :feedback_a: This would be correct if the variable col was 0 because then it would add 1 + 1 + 1 + 1 which is 4.   
   :feedback_b: Since col is matrix[0].length - 2 it is 4 - 2 which is 2.  This code will loop through all the rows and add all the numbers in the third column (index is 2) which is 2  + 2 + 3 + 1 which is 8.
   :feedback_c: This would be correct if the variable col was 1 because then it would add 1 + 2 + 2 + 4 which is 9.  
   :feedback_d: This would be correct if the variable col was 3 becuase then it would add 2 + 4 + 4+ 2 which is 12. 
   :feedback_e: This would be true if we were adding the values in the 3rd row (row = 2) instead of the 3rd column.  This would be 1 + 2 + 3 + 4 which is 10.   

   Given the following code segment, what is the value of sum after this code executes?
   
   .. code-block:: java 

      int[][] matrix = { {1,1,2,2},{1,2,2,4},{1,2,3,4},{1,4,1,2}};

      int sum = 0;
      int col = matrix[0].length - 2;
      for (int row = 0; row < 4; row++)
      {
         sum = sum + matrix[row][col];
      }
      
You can step through this code using the following link `Example-9-8-1 <http://cscircles.cemc.uwaterloo.ca/java_visualize/#code=public+class+ClassNameHere+%7B%0A+++public+static+void+main(String%5B%5D+args)+%7B%0A++++++%0A++++++int%5B%5D%5B%5D+matrix+%3D+%7B%7B1,1,2,2%7D,%7B1,2,2,4%7D,%7B1,2,3,4%7D,%7B1,4,1,2%7D%7D%3B%0A%0A++++++int+sum+%3D+0%3B%0A++++++int+col+%3D+matrix%5B0%5D.length+-+2%3B%0A++++++for+(int+row+%3D+0%3B+row+%3C+4%3B+row%2B%2B)%0A++++++%7B%0A+++++++++sum+%3D+sum+%2B+matrix%5Brow%5D%5Bcol%5D%3B%0A++++++%7D%0A++++++System.out.println(sum)%3B%0A++++++%0A+++%7D%0A%7D&mode=display&curInstr=2>`_.
      
.. mchoice:: q9_6_5
   :practice: T
   :answer_a: { {2 3 3}, {1 2 3}, {1 1 2}, {1 1 1}} 
   :answer_b: { {2 1 1}, {3 2 1}, {3 3 2}, {3 3 3}} 
   :answer_c: { {2 1 1 1}, {3 2 1 1}, {3 3 2 1}} 
   :answer_d: { {2 3 3 3}, {1 2 3 3}, {1 1 2 3}} 
   :answer_e: { {1 1 1 1}, {2 2 2 2}, {3 3 3 3}} 
   :correct: b
   :feedback_a: This woud be true if the code put a 3 in the array when the row index is less than the column index and a 2 in the array when the row and column index are the same, and a 1 in the array when the row index is greater than the column index. 
   :feedback_b: This code will put a 1 in the array when the row index is less than the column index and a 2 in the array when the row and column index are the same, and a 3 in the array when the row index is greater than the column index. 
   :feedback_c: This code creates a 2D array with 4 rows and 3 columns so this can't be right.  
   :feedback_d: This code creates a 2D array with 4 rows and 3 columns so this can't be right.  
   :feedback_e: This code creates a 2D array with 4 rows and 3 columns so this can't be right.    

   What are the contents of ``mat`` after the following code segment has been executed? 
   
   .. code-block:: java 

      int [][] mat = new int [4][3];
      for (int row = 0; row < mat.length; row++) { 
         for (int col = 0; col < mat[0].length; col++) { 
            if (row < col) 
               mat[row][col] = 1;
            else if (row == col)    
               mat[row][col] = 2; 
            else 
               mat[row][col] = 3; } } 
               
You can step through this code using the following link `Example-9-8-2 <http://cscircles.cemc.uwaterloo.ca/java_visualize/#code=public+class+ClassNameHere+%7B%0A+++public+static+void+main(String%5B%5D+args)+%7B%0A++++++%0A++++++int+%5B%5D%5B%5D+mat+%3D+new+int+%5B4%5D%5B3%5D%3B%0A++++++for+(int+row+%3D+0%3B+row+%3C+mat.length%3B+row%2B%2B)+%7B+%0A+++++++++for+(int+col+%3D+0%3B+col+%3C+mat%5B0%5D.length%3B+col%2B%2B)+%7B+%0A++++++++++++if+(row+%3C+col)+%0A+++++++++++++++mat%5Brow%5D%5Bcol%5D+%3D+1%3B%0A++++++++++++else+if+(row+%3D%3D+col)++++%0A+++++++++++++++mat%5Brow%5D%5Bcol%5D+%3D+2%3B+%0A++++++++++++else+%0A+++++++++++++++mat%5Brow%5D%5Bcol%5D+%3D+3%3B+%7D+%7D+%0A++++++%0A++++++%0A+++%7D%0A%7D&mode=display&curInstr=0>`_.

.. mchoice:: q9_6_6
   :practice: T
   :answer_a: 4
   :answer_b: 6
   :answer_c: 9
   :answer_d: 10
   :answer_e: 20
   :correct: c
   :feedback_a: This would be correct if it was adding up all the values in the first row.  Does it?
   :feedback_b: This would be correct if it was adding up all the values in column 0.  
   :feedback_c: This adds all the values in column 1 starting with the one in the last row (row 3).    
   :feedback_d: This would be correct if it was adding up all the values in the second row.  
   :feedback_e: This would be correct if it was adding up all the values in the last row.    

   Given the following code segment, what is the value of sum after this code executes?
   
   .. code-block:: java 

      int[][] m = { {1,1,1,1},{1,2,3,4},{2,2,2,2},{2,4,6,8}};

      int sum = 0;
      for (int k = 0; k < m.length; k++) {
          sum = sum + m[m.length-1-k][1];
      }
      
You can step through this code using the following link `Example-9-8-3 <http://cscircles.cemc.uwaterloo.ca/java_visualize/#code=import+java.util.*%3B%0Apublic+class+Test+%7B%0A+++public+static+void+main(String%5B%5D+args)+%7B%0A+++++int%5B%5D%5B%5D+m+%3D+%7B%7B1,1,1,1%7D,%7B1,2,3,4%7D,%7B2,2,2,2%7D,%7B2,4,6,8%7D%7D%3B%0A%0A+++++int+sum+%3D+0%3B%0A+++++for+(int+k+%3D+0%3B+k+%3C+m.length%3B+k%2B%2B)+%7B%0A+++++++++sum+%3D+sum+%2B+m%5Bm.length-1-k%5D%5B1%5D%3B%0A+++++%7D%0A+++++System.out.println(sum)%3B%0A+++%7D%0A%7D&mode=display&curInstr=0>`_.

      
Hard Multiple Choice Questions
----------------------------------

      
.. mchoice:: q9_6_7
   :practice: T
   :answer_a: { {6, 4, 2}, {2, 4, 6}}
   :answer_b: { {3, 2, 1}, {1, 4, 6}}
   :answer_c: { {3, 2, 1}, {1, 4, 8}}
   :answer_d: { {4, 4, 2}, {2, 4, 4}}
   :answer_e: { {3, 2, 1}, {2, 4, 4}}
   :correct: c
   :feedback_a: Check the starting values on the nested loops.
   :feedback_b: Notice that there are two if's, not an if and else.
   :feedback_c: The first if will change an odd number to an even.  The second if will also execute after an odd number has been made even.  Both loops start at index 1 so this only changes the items in the second row and second and third column.   
   :feedback_d: Both if's will execute.  Also, check the bounds on the nested loop. 
   :feedback_e: Both if's will execute.  Check the bounds on the inner loop.  When does it stop?    

   What are the contents of ``arr`` after the following code has been executed? 
   
   .. code-block:: java 

      int[][] arr = { {3,2,1},{1,2,3}};
      int value = 0;
      for (int row = 1; row < arr.length; row++) {
         for (int col = 1; col < arr[0].length; col++) {
            if (arr[row][col] % 2 == 1) 
            {
                arr[row][col] = arr[row][col] + 1;
            }
            if (arr[row][col] % 2 == 0) 
            {
                arr[row][col] = arr[row][col] * 2;
            }
         }
      }
      
To step through this code in the Java Visualizer click on the following link: `Hard 1 <http://cscircles.cemc.uwaterloo.ca/java_visualize/#code=public+class+ClassNameHere+%7B%0A+++public+static+void+main(String%5B%5D+args)+%7B%0A++++++int%5B%5D%5B%5D+arr+%3D+%7B%7B3,2,1%7D,%7B1,2,3%7D%7D%3B%0A++++++for+(int+row+%3D+1%3B+row+%3C+arr.length%3B+row%2B%2B)+%7B%0A+++++++++for+(int+col+%3D+1%3B+col+%3C+arr%5B0%5D.length%3B+col%2B%2B)+%7B%0A++++++++++++if+(arr%5Brow%5D%5Bcol%5D+%25+2+%3D%3D+1)+%0A++++++++++++%7B%0A+++++++++++++++arr%5Brow%5D%5Bcol%5D+%3D+arr%5Brow%5D%5Bcol%5D+%2B+1%3B%0A++++++++++++%7D%0A++++++++++++if+(arr%5Brow%5D%5Bcol%5D+%25+2+%3D%3D+0)+%0A++++++++++++%7B%0A+++++++++++++++arr%5Brow%5D%5Bcol%5D+%3D+arr%5Brow%5D%5Bcol%5D+*+2%3B%0A++++++++++++%7D%0A+++++++++%7D%0A++++++%7D%0A++++++%0A+++%7D%0A%7D&mode=display&curInstr=0>`_.

.. mchoice:: q9_6_8
   :practice: T
   :answer_a: The maximum brightness value for all pixels in imagePixel
   :answer_b: The column with the greatest brightness sum
   :answer_c: The most frequent brightness value in imagePixels
   :answer_d: The row with the greatest brightness sum
   :answer_e: The sum of the total brightness of imagePixels
   :correct: a
   :feedback_a: The method works by scanning all the pixels in imagePixels and comparing them to the current iMax value. If the current is greater, it replaces iMax and becomes the new maximum brightness. This is the value that is returned.
   :feedback_b: This could be accomplished by adding the brightness in the second loop and comparing the sum to iMax after the second loop finishes and before the first loop starts again.
   :feedback_c: To do this you would need a third loop and an array, 256 in size. In the second loop you would track how many pixels of a certain brightness had occurred using, countBright[i]++, and then in the third loop find the item in countBright with the highest value.
   :feedback_d: Firstly, you would need to traverse the 2D array in the opposite order, going through the rows instead of the columns. Then, you would sum each row's brightness in the second loop and compare it to the max in the first loop.
   :feedback_e: This would be accomplished by instead of having an if statement to track the currentmax, simply using, sum += imagePixels[r][c];

   A two-dimensional array, ``imagePixels``, holds the brightness values for the pixels in an image. The brightness can range from 0 to 255. What does the following method compute?
   
   .. code-block:: java
     :linenos:

     public int findMax(int[][] imagePixels) {
        int r, c;
        int i, iMax = 0;

        for (r = 0; r < imagePixels.length; r++) {
           for (c = 0; c < imagePixels[0].length; c++) {
              i = imagePixels[r][c];
              if (i > iMax)
                 iMax = i;
            }
         }
         return iMax;
      }
      
