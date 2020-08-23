.. qnum::
   :prefix: 8-11-
   :start: 1
   
   
Multiple-Choice Exercises
=========================


Easier Multiple Choice Questions
----------------------------------


.. mchoice:: qale_1
   :practice: T
   :answer_a: nums.length
   :answer_b: nums.length - 1
   :answer_c: nums.size()
   :answer_d: nums.size() - 1
   :correct: d
   :feedback_a: You can't use length on lists and the last index is one less than the size.
   :feedback_b: You can't use length on lists, use size instead.
   :feedback_c: Since the first element in a list is at index 0 the last element is at the size minus 1.
   :feedback_d: The last element is at the size of the list minus 1.

   Which index is the last element in a list called ``nums`` at?

.. mchoice:: qale_2
   :practice: T
   :answer_a: An array has faster access to its elements than a list does.
   :answer_b: An array knows it length, but a list doesn't know its length.
   :answer_c: An ArrayList can allocate more space than it needs.
   :correct: c
   :feedback_a: Since an ArrayList is implemented by an array, it has the same access time.
   :feedback_b: Lists do know their length, but they don't make it public.
   :feedback_c: Every time an ArrayList fills up a new array is created that is twice as big.  This can lead to extra space that is wasted.

   Which of the following is a reason to use an array instead of an ArrayList?

.. mchoice:: qale_3
   :practice: T
   :answer_a: An ArrayList can grow or shrink as needed, while an array is always the same size.
   :answer_b: You can use a for-each loop on an ArrayList, but not in an array.
   :answer_c: You can store objects in an ArrayList, but not in an array.
   :correct: a
   :feedback_a: This is the main advantage to an ArrayList.
   :feedback_b: You can use a for-each loop on either an ArrayList or array.
   :feedback_c: Arrays can also store objects of the same type.

   Which of the following is a reason to use an ArrayList instead of an array?

.. mchoice:: qale_4
   :practice: T
   :answer_a: nums[0]
   :answer_b: nums[1]
   :answer_c: nums.first()
   :answer_d: nums.get(0)
   :answer_e: nums.get(1)
   :correct: d
   :feedback_a: This is how you get the first value in an array, but not in a list.
   :feedback_b: This is how you get the second value in an array.  Remember that this is a list and that the first item in an array is at index 0.
   :feedback_c: The <code>List</code>  doesn't have a <code>first</code> method.
   :feedback_d: Use the <code>get</code> method to get a value from a list and the first element in a list is at index 0.
   :feedback_e: This would return the second element in a list.  Remember that the first element in a list or array is at index 0.

   Which of the following is the correct way to get the first value in a list called ``nums``?


.. mchoice:: qale_5
   :practice: T
   :answer_a: nums[1] = 5;
   :answer_b: nums[2] = 5;
   :answer_c: nums.set(5, 1);
   :answer_d: nums.set(1, 5);
   :answer_e: nums.set(2, 5);
   :correct: d
   :feedback_a: This is how you set the second value in an array, but not in a list.
   :feedback_b: This is how you set the third value in an array, but not in a list.
   :feedback_c: This would the value at index 5 to 1.
   :feedback_d: This sets the second value in the list to 5.
   :feedback_e: This would set the third value in the list to 5.  Remember that the first value is at index 0.

   Which of the following is the correct way to set the second value in a list called ``nums`` to 5?

.. mchoice:: qale_6
   :practice: T
   :answer_a: nums.remove(3);
   :answer_b: nums.remove(0);
   :answer_c: nums.remove(1);
   :answer_d: nums.remove(2);
   :correct: c
   :feedback_a: This would remove the value at index 3 which is 1.
   :feedback_b: This would remove the value at index 0 which is 5. 
   :feedback_c: This would remove the value at index 1 which is 3.
   :feedback_d: This would remove the value at index 2 which is 2.

   Which of the following is the correct way to remove the value 3 from the list ``nums = [5, 3, 2, 1]``?

.. mchoice:: qale_7
   :practice: T
   :answer_a: nums.add(2, 0);
   :answer_b: nums.add(2, 1);
   :answer_c: nums.add(0, 2);
   :answer_d: nums.add(1, 2);
   :answer_e: nums.add(2, 2);
   :correct: d
   :feedback_a: This would add 0 at index 2.  Remember that the method is <code>add(index, obj)</code>.
   :feedback_b: This would add 1 at index 2.  Remember that the method is <code>add(index, obj)</code>
   :feedback_c: This would add 2 at index 0 which would result in <code>[2, 1, 3, 4]</code>
   :feedback_d: This would add 2 at index 1 which would result in <code>[1, 2, 3, 4]</code>
   :feedback_e: This would add 2 at index 2 which would result in <code>[1, 3, 2, 4]</code>

   Which of the following is the correct way to add 2 between the 1 and 3 in the following list ``nums = [1, 3, 4]``?

.. .. mchoice:: qale_8
   :practice: T
   :answer_a: It is a type of class.
   :answer_b: The methods in an interface will be public and abstract.
   :answer_c: It is like a contract in that the class that implements the interface must provide the methods defined in the interface.
   :answer_d: You can create an object of an interface type.
   :correct: d
   :feedback_a: An interface is a special type of abstract class in Java.
   :feedback_b: The methods defined in an interface are public and abstract.
   :feedback_c: An interface is like a contract for the implementing classes.
   :feedback_d: You can not create an object of an interface type.  This is why you create a ``List`` using the <code>ArrayList</code> class which implements the ``List`` interface.

   Which of the following is *false* about an interface?

.. mchoice:: qale_9
   :practice: T
   :answer_a: [2, 3]
   :answer_b: [1, 2, 3]
   :answer_c: [1, 2]
   :answer_d: [1, 3]
   :correct: d
   :feedback_a: This would be true if it was <code>remove(0)</code>
   :feedback_b: The <code>remove</code> will remove a value from the list, so this can't be correct.
   :feedback_c: This would be true if it was <code>remove(2)</code>
   :feedback_d: This removes the value at index 1 which is 2.

   What will print when the following code executes?

   .. code-block:: java

      List<Integer> list1 = new ArrayList<Integer>();
      list1.add(new Integer(1));
      list1.add(new Integer(2));
      list1.add(new Integer(3));
      list1.remove(1);
      System.out.println(list1);


.. mchoice:: qale_10
   :practice: T
   :answer_a: ["Sarah", "Destini", "Layla", "Sharrie"]
   :answer_b: ["Sarah", "Destini", "Anaya", "Layla", "Sharrie"]
   :answer_c: ["Sarah", "Layla", "Sharrie"]
   :answer_d: ["Destini", "Layla", "Sharrie", "Sarah"]
   :correct: a
   :feedback_a: The list is first ["Anaya", "Layla", "Sharrie"] and then ["Destini, "Layla", "Sharrie"] and finally ["Sarah", "Destini, "Layla", "Sharrie"]
   :feedback_b: The set replaces the value at index 0.
   :feedback_c: This would be true if the second add was a set.
   :feedback_d: This would be true if the last add didn't have an index of 0.

   What will print when the following code executes?

   .. code-block:: java

      List<String> list1 = new ArrayList<String>();
      list1.add("Anaya");
      list1.add("Layla");
      list1.add("Sharrie");
      list1.set(0, "Destini");
      list1.add(0, "Sarah");
      System.out.println(list1);



Easier Search/Sort Multiple Choice Questions
---------------------------------------------


.. mchoice:: qsearchse_1
   :practice: T
   :answer_a: -1
   :answer_b: 0
   :answer_c: 1
   :answer_d: 2
   :answer_e: 50
   :correct: d
   :feedback_a: This value is returned if the target is not in the list since this is a sequential search.
   :feedback_b: This would be true if the target was 90 since this is a sequential search.
   :feedback_c: This would be true if the target was -30 since this is a sequential search.
   :feedback_d: This is a sequential search that returns the index where the target appears in the elements list
   :feedback_e: A sequential search returns the index, not the value.  What is the index of the 50?

   What would the following code return from mystery([90, -30, 50], 50)?

   .. code-block:: java

      public static int mystery(int[] elements, int target)
      {
        for (int j = 0; j < elements.length; j++)
        {
           if (elements[j] == target)
           {
              return j;
           }
       }
       return -1;
     }


.. mchoice:: qsearchse_2
   :practice: T
   :answer_a: -1
   :answer_b: 0
   :answer_c: 1
   :answer_d: 2
   :answer_e: -20
   :correct: a
   :feedback_a: A sequential search returns -1 if the target value is not found in the list.
   :feedback_b: This would be true if the target was 90 since this is a sequential search.
   :feedback_c: This would be true if the target was -30 since this is a sequential search.
   :feedback_d: This would be true if the target was
   :feedback_e: A sequential search returns negative one when the value isn't found in the list.

   What would the following code return from mystery([90, -30, 50], -20)?

   .. code-block:: java

      public static int mystery(int[] elements, int target)
      {
        for (int j = 0; j < elements.length; j++)
        {
           if (elements[j] == target)
           {
              return j;
           }
       }
       return -1;
     }


.. mchoice:: qsearchse_3
   :practice: T
   :answer_a: 1
   :answer_b: 2
   :answer_c: 3
   :correct: b
   :feedback_a: This would be true if we were looking for 23.
   :feedback_b: It first compares 23 at index 2 (5 / 2 is 2) to 2.  The second time it compares the 2 at index 0 (1 / 2 = 0) to 2 and returns 0.
   :feedback_c: This would be true if we were looking for 10.

   Consider the ``binarySearch`` method below.  How many times would the while loop execute if you first do int[] arr = {2, 10, 23, 31, 55, 86} and then call  binarySearch(arr,2)?

   .. code-block:: java

      public static int binarySearch(int[] elements, int target) {
         int left = 0;
         int right = elements.length - 1;
         while (left <= right)
         {
            int middle = (left + right) / 2;
            if (target < elements[middle])
            {
               right = middle - 1;
            }
            else if (target > elements[middle])
            {
               left = middle + 1;
            }
            else {
               return middle;
            }
          }
          return -1;
      }


.. mchoice:: qsearchse_4
   :practice: T
   :answer_a: selection sort
   :answer_b: insertion sort
   :answer_c: merge sort
   :correct: c
   :feedback_a: A selection sort has nested for loops.
   :feedback_b: An insertion sort has a while loop inside a for loop.
   :feedback_c: A merge sort has a recursive call to mergeSortHelper in mergeSortHelper.

   Which sort contains a recursive call?

.. mchoice:: qsearchse_5
   :practice: T
   :answer_a: If the data is already sorted in ascending order
   :answer_b: If the data is already sorted in descending order
   :answer_c: It will always take the same amount of time to execute
   :correct: b
   :feedback_a: If the data is already sorted in the correct order you don't need to move any values.
   :feedback_b: All values will have to be moved multiple times since the data was sorted into descending order.
   :feedback_c: This would be true if it was a selection sort.

   Under what condition will an ascending insertion sort execute the slowest?




Medium Multiple Choice Questions
----------------------------------


.. mchoice:: qalm_1
   :practice: T
   :answer_a: [1, 2, 3, 4, 5]
   :answer_b: [1, 2, 4, 5, 6]
   :answer_c: [1, 2, 5, 4, 6]
   :answer_d: [1, 5, 2, 4, 6]
   :correct: c
   :feedback_a: The set replaces the 3 at index 2 with the 4 so this can't be right.
   :feedback_b: The add with an index of 2 and a value of 5 adds the 5 at index 2 not 3.  Remember that the first index is 0. 
   :feedback_c: The add method that takes just an object as a parameter adds that object to the end of the list.  The set replaces the value at that index with the new value.  The add with parameters of an index and an object puts the passed object at that index and moves any existing values by one index to the right (increments the index).  
   :feedback_d: The add with an index of 2 and a value of 5 adds the 5 at index 2 not 1.  Remember that the first index is 0.   

   What is printed as a result of executing the following code segment?
   
   .. code-block:: java
   
      List<Integer> list1 = new ArrayList<Integer>();
      list1.add(new Integer(1));
      list1.add(new Integer(2));
      list1.add(new Integer(3));
      list1.set(2, new Integer(4));
      list1.add(2, new Integer(5));
      list1.add(new Integer(6));
      System.out.println(list1);
      

   
.. mchoice:: qalm_2
   :practice: T
   :answer_a: [0, 4, 2, 5, 3]   
   :answer_b: [3, 5, 2, 4, 0, 0, 0]   
   :answer_c: [0, 0, 0, 4, 2, 5, 3]  
   :answer_d: [4, 2, 5, 3]     
   :answer_e: [0, 0, 4, 2, 5, 0, 3]     
   :correct: d
   :feedback_a: This code will loop through the array list and if the current value at the current index (k) is 0 it will remove it.  When you remove a value from an array list it moves all values to the right of that one to the the left. It only increments the index when it doesn't find a zero so it work work correctly.
   :feedback_b: This shows all zeros at the end and this code removes 0's so this can't be right.     
   :feedback_c: This shows all zeros at the beginning and this code removes zeros so this can't be right.  
   :feedback_d: This shows all zeros removed.  Since k is only incremented if a value wasn't removed this will work correctly. 
   :feedback_e: This shows the original values, but this code does remove some zeros so this can't be right.

   Given the following code and assume that ``nums`` initially contains [0, 0, 4, 2, 5, 0, 3], what will ``nums`` contain as a result of executing numQuest?
   
   .. code-block:: java 

      private List<Integer> nums;

      // precondition: nums.size() > 0;
      // nums contains Integer objects
      public void numQuest()
      {
        int k = 0;
        Integer zero = new Integer(0);
        while (k < nums.size())
        {
         if (nums.get(k).equals(zero))
           nums.remove(k);
         else
            k++;
        }
      }
      

.. mchoice:: qalm_3
   :practice: T
   :answer_a: Both methods produce the same result, and process1 is faster than process2.    
   :answer_b: The two methods produce different results and take the same amount of time.  
   :answer_c: The two methods produce different results, and process1 is faster than process2. 
   :answer_d: The two methods produce different results, and process2 is faster than process1.    
   :answer_e: Both methods produce the same result and take the same amount of time.   
   :correct: e
   :feedback_a: In this case they do the same thing.  The only difference would be if there were values in the list in process2. 
   :feedback_b: These produce the same result on an empty list when you add to the end. 
   :feedback_c: These produce the same result on an empty list when you add to the end.   
   :feedback_d: These produce the same result on an empty list when you add to the end.  
   :feedback_e: The method process1 adds to the end of the list each time through the loop.  The method process2 also adds to the end of the list each time through the loop.  The only difference would be if there were values in the list in process2.  Any existing values would be moved to the right.  But, there are no existing values in the list at that index or beyond.  

   Which of the following best describes the behavior of process1 and process2 (shown below)?
   
   .. code-block:: java 
   
      public static List<Integer> process1(int n)
      {
         List<Integer> someList = new ArrayList<Integer>();
         for (int k = 0; k < n; k++)
            someList.add(k);
         return someList;
      }
      
      public static List<Integer> process2(int n)
      {
         List<Integer> someList = new ArrayList<Integer>();
         for (int k = 0; k < n; k++)
            someList.add(k, k);
         return someList;
      }
      
      
.. mchoice:: qalm_4
   :practice: T
   :answer_a: [1, 2, 5, 4, 6, 3]
   :answer_b: [6, 5, 4, 3, 2, 1]
   :answer_c: [1, 2, 3, 4, 5, 6]
   :answer_d: [1, 4, 2, 6, 3]
   :answer_e: [1, 2, 4, 6, 3]
   :correct: d
   :feedback_a: The set replaces the 3 with the 4 so this can't be right.
   :feedback_b: The add with an index of 2 and a value of 5 adds the 5 at index 2 not 3.  Remember that the first index is 0. 
   :feedback_c: The add method that takes just a value as a parameter adds that value to the end of the list.  The set replaces the value at that index with the new value.  The add with parameters of an index and a value puts the passed value at that index and moves any existing values by one index to the right (increments the index).  
   :feedback_d: The add with an index of 2 and a value of 5 adds the 5 at index 2 not 1.  Remember that the first index is 0.   
   :feedback_e: When you declare and create a collection class you can specify the type of the items in it.  

   What is printed as a result of executing the following code segment?
   
   .. code-block:: java
   
     List<Integer> aList = new ArrayList<Integer>();
     aList.add(new Integer(1)); 
     aList.add(new Integer(2)); 
     aList.add(1, new Integer(5)); 
     aList.set(1, new Integer(4));
     aList.add(new Integer(6)); 
     aList.add(new Integer(3));
     System.out.println(aList); 
     
     
.. mchoice:: qalm_5
   :practice: T
   :answer_a: [1, 2, 3, 4, 5]
   :answer_b: [1, 4, 5]
   :answer_c: [1, 4, 3, 5]
   :answer_d: [2, 4, 5]
   :answer_e: [2, 4, 3, 5]
   :correct: b
   :feedback_a: This would be true if the code just added each integer at the end of the list.  But, that is not what it does.
   :feedback_b: The list is [1], then [1, 2], then [1], then [1, 3], then [1, 4], then [1, 4, 5].
   :feedback_c: This would be true if the <code>set</code> was an add.  
   :feedback_d: This would be true it it was <code>remove(0)</code>.  Remember that it removes the object at the given index.  
   :feedback_e: This would be true if the <code>set</code> was an add and if it was <code>remove(0)</code>.

   What is printed as a result of executing the following code segment?
   
   .. code-block:: java
   
     List<Integer> aList = new ArrayList<Integer>();
     aList.add(new Integer(1)); 
     aList.add(new Integer(2)); 
     aList.remove(1);
     aList.add(1, new Integer(3)); 
     aList.set(1, new Integer(4));
     aList.add(new Integer(5)); 
     System.out.println(list); 
     

.. mchoice:: qalm_6
   :practice: T
   :answer_a: [c, d, e, b]
   :answer_b: [c, d, e, b, f]
   :answer_c: [c, a, e, b, f]
   :answer_d: [c, d, e, a, b, f]
   :answer_e: [c, a, e, d, b, f]
   :correct: b
   :feedback_a: What happened to the f?
   :feedback_b: This list is [a], then [a, b], then [c, a, b], then [c, d, a, b], then [c, d, e, b], then [c, d, e, b, f]
   :feedback_c: The a is pushed to position 2 and then replaced with the e.  
   :feedback_d: This would be true if it was <code>list1.add(2,"e")</code>
   :feedback_e: Remember that the set will replace the value at index 2.

   What is printed as a result of executing the following code segment?
   
   .. code-block:: java
   
     List<String> list1 = new ArrayList<String>();
     list1.add("a");
     list1.add("b");
     list1.add(0,"c");
     list1.add(1, "d");
     list1.set(2, "e");
     list1.add("f");
     System.out.println(list1);

     What is printed as a result of executing the following code segment?
     

.. mchoice:: qalm_7
   :practice: T
   :answer_a: [2, 3, 4, 5]
   :answer_b: [2, 3, 5]
   :answer_c: [4, 2, 3, 5]
   :answer_d: [4, 2, 3, 4]
   :correct: d
   :feedback_a: This would be true if it removed the first 4 but it removes the value at index 4.  
   :feedback_b: This would be true if it removed all the 4 values, but it removes the value at index 4.
   :feedback_c: This would be true if it removed the value at index 3.  
   :feedback_d: This removes the value at index 4 which is 5.  

   Given the list ``nums = [4, 2, 3, 4, 5]`` what is the result after executing ``nums.remove(4)``?
   
   
.. mchoice:: qalm_8
   :practice: T
   :answer_a: [e, d, b]
   :answer_b: [e, d, b, b]
   :answer_c: [e, d, a, b, b]
   :answer_d: [e, d, a, b]
   :correct: b
   :feedback_a: This would be true if you couldn't add a duplicate object to a list, but you can.
   :feedback_b: The list is [a], [a, b], [c, a, b], [c, d, b], [e, d, b], and then [e, d, b, b]
   :feedback_c: This would be true it <code>list1.set(1,"d");</code> was <code>list1.add(1,"d");</code> 
   :feedback_d: This would be true it <code>list1.set(1,"d");</code> was <code>list1.add(1,"d");</code> and if lists didn't allow duplicate objects.  

   What is printed as a result of executing the following code segment?
   
   .. code-block:: java
   
     List<String> list1 = new ArrayList<String>();
     list1.add("a");
     list1.add("b");
     list1.add(0,"c");
     list1.set(1, "d");
     list1.set(0, "e");
     list1.add("b");
     System.out.println(list1);

     What is printed as a result of executing the following code segment?
     

.. mchoice:: qalm_9
   :practice: T
   :answer_a: [4, 3, 2, 1, 0]
   :answer_b: [1, 2, 3, 4, 0]
   :answer_c: [0, 1, 2, 3, 4]
   :answer_d: [2, 3, 4, 0, 1]
   :answer_e: [4, 0, 1, 2, 3]
   :correct: c
   :feedback_a: This would be true if it was <code>numList.add(numList.size() - i, obj)</code>
   :feedback_b: This would be true if it was <code>mystery(1)</code>   
   :feedback_c: Each value is removed one at a time and added to the end of the list which results in the same list.
   :feedback_d: This would be true if it was <code>mystery(2)</code>  
   :feedback_e: This would be true if it was <code>mystery(4)</code>  
   
   Assume that ``numList`` has been initialized with the following Integer objects: [0, 1, 2, 3, 4].  What is the value of ``numList`` after ``mystery(5)`` executes?
   
   .. code-block:: java
   
     private List<Integer> numList;
     public void mystery(int n)
     {
         for (int i = 0; i < n; i++)
         { 
             Integer obj = numList.remove(0);
             numList.add(obj);
         }
     }
     
	 
.. mchoice:: qalm_10
   :practice: T
   :answer_a: [5, 7, 8, 12]
   :answer_b: [5, 7, 8, 11, 12]
   :answer_c: [11, 5, 7, 8, 12]
   :answer_d: [5, 7, 8, 12, 11]
   :answer_e: [5, 7, 11, 8, 12]
   :correct: b
   :feedback_a: What about the 11?
   :feedback_b: This will add the value at the correct location in a list in ascending order.
   :feedback_c: This would be true if it was <code>numList.add(0, value)</code>
   :feedback_d: This would be true if the while loop was from 0 to one less than the size of the list.
   :feedback_e: This would be true if it was <code>numList.add(i-1, value)</code> 
   
   Assume that ``numList`` has been initialized with the following Integer objects: [5, 7, 8, 12].  Which of the following shows the values in ``numList`` after a call to ``mystery(11)``?
   
   .. code-block:: java
   
     private List<Integer> numList; 
     public void mystery(int value)
     {
         int i = 0;
         while (i < numList.size() && numList.get(i) < value)
         { 
             i++;
         }
         numList.add(i, value);
     }

     
     

Medium Search/Sort Multiple Choice Questions
--------------------------------------------


.. mchoice:: qsearchsm_1
   :practice: T
   :answer_a: {3,7,8,5,2}, {3,7,8,5,2}, {3,5,7,8,2}, {2,3,5,7,8}
   :answer_b: {2,3,8,5,7}, {2,3,8,5,7}, {2,3,5,8,7}, {2,3,5,7,8}
   :answer_c: {3,7,8,5,2}, {3,5,7,8,2}, {2,3,5,7,8}
   :answer_d: {2,3,8,5,7}, {2,3,5,8,7}, {2,3,5,7,8}
   :answer_e: {2,7,3,8,5}, {2,3,7,8,5}, {2,3,5,7,8}
   :correct: a
   :feedback_a: The insertion sort starts at index 1 and inserts each value into the sorted list to the left by moving any larger values right.
   :feedback_b: This would be true if it was a selection sort.
   :feedback_c: This looks like an insertion sort, but it is missing one step.
   :feedback_d: This looks like a selection sort, but it is missing one step.
   :feedback_e: This is more like a selection sort, but not a correct one.

   Which of the following correctly shows the iterations of an ascending (from left to right) insertion sort on an array with the following elements: {7,3,8,5,2}?


.. mchoice:: qsearchsm_2
   :practice: T
   :answer_a: -1
   :answer_b: 0
   :answer_c: 1
   :answer_d: 2
   :answer_e: 3
   :correct: c
   :feedback_a: This would be true if the third value was something that wasn't in the array.
   :feedback_b: This would be true if the third value was 1
   :feedback_c: This is a binary search and it returns the index of the value 3, which is 1.
   :feedback_d: This would be true if the third value was 5.
   :feedback_e: This would be true if the third value was 8.

   What is printed when the following main method is executed?

   .. code-block:: java

      public class Searcher
      {
          private int[] arr = {1,3,5,8,9};

          public int mystery(int low, int high, int num)
          {
              int mid = (low + high) / 2;
              if (low > high) {
                  return -1;   }
              else if (arr[mid] < num) {
                  return mystery(mid + 1, high, num);   }
              else if (arr[mid] > num) {
                  return mystery(low, mid - 1, num);   }
              else
                  return mid;
          }

          public static void main(String[] args)
          {
              Searcher s = new Searcher();
              System.out.println(s.mystery(0,4,3));
          }
      }


.. mchoice:: qsearchsm_3
   :practice: T
   :answer_a: {6,10,3,2,8}, {3,6,10,2,8}, {2,3,6,10,8}, {2,3,6,8,10}
   :answer_b: {6,10,3,2,8}, {3,6,10,2,8}, {2,3,6,8,10}
   :answer_c: {2,6,3,10,8}, {2,3,6,10,8}, {2,3,6,8,10}
   :answer_d: {2,6,3,10,8}, {2,3,6,10,8}, {2,3,6,10,8}, {2,3,6,8,10}
   :correct: d
   :feedback_a: This would be true if it was an insertion sort.
   :feedback_b: This would be true if it was an insertion sort, but you are also missing a step.
   :feedback_c: This is almost right, but is missing one step.
   :feedback_d: This is the result from a selection sort.

   Which of the following correctly shows the iterations of an ascending (from left to right) selection sort on an array with the following elements: {10, 6, 3, 2, 8}?


.. mchoice:: qsearchsm_4
   :practice: T
   :answer_a: int k = j - 1; k >= 0; k--
   :answer_b: int k = j + 1; k < elem.length; k++
   :answer_c: int k = j; k < elem.length; k++
   :answer_d: int k = j; k >= 0; k--
   :answer_e: int k = j - 1; k > 0; k--
   :correct: b
   :feedback_a: The inner loop starts at the outer loop value plus one, not minus one.
   :feedback_b: The inner loop starts at the outer loop value plus one and ends at the last element.
   :feedback_c: The inner loop should start at the outer loop value plus one.
   :feedback_d: The inner loop should start at the outer loop value plus one and increment.
   :feedback_e: The inner loop should start at the outer loop value plus one and increment.

   Which of the following could be used to replace // missing code // in the code so that the method always sorts the array ``elem`` in ascending order?

   .. code-block:: java

      public class Searcher
      {

          public static void sort(int[] elem)
   		  {
              for (int j = 0; j < elem.length - 1; j++)
              {
                  int minIndex = j;

                  for (// missing code //)
                  {
                      if (elem [k] < elem [minIndex])
                      {
                          minIndex = k;
                      }
                  }
                  int temp = elem[j];
                  elem[j] = elem[minIndex];
                  elem[minIndex] = temp;
              }
          }

          public static void main(String[] args)
          {
              int[] nums = {28, -3, 2, 14, 30};
              Searcher.sort(nums);
          }
      }


.. mchoice:: qsearchsm_5
   :practice: T
   :answer_a: -1
   :answer_b: 0
   :answer_c: 1
   :answer_d: 2
   :answer_e: The code will not compile
   :correct: e
   :feedback_a: This would be true if the sequential search code was okay and v was a value that wasn't in the array, but the code is incorrect.  The <code>return -1</code> should be outside of the for loop.
   :feedback_b: This would be true if v was 1 and the code was correct for a sequential search.
   :feedback_c: This would be true if v was 2 and the code was correct for a sequential search.
   :feedback_d: This would be true if the code was correct for a sequential search, but it returns -1 inside the for loop instead of outside of it.
   :feedback_e: This method won't compile because it is supposed to return an integer and if the for loop doesn't execute it will not return anything.  The <code>return -1</code> should be outside the for loop to make this sequential search work as intended.

   What would test return if a = {1,2,3,4} and v =  3?

   .. code-block:: java

      public static int test(int[] a, int v)
      {
          for (int i = 0; i < a.length; i++)
          {
              if (a[i] == v)
                  return i;
              else return -1;
          }
      }

 

Hard Multiple Choice Questions
----------------------------------


.. mchoice:: qalh_1
   :practice: T
   :answer_a: [5, 3, 1, 6]
   :answer_b: [4, 3, 1, 6]
   :answer_c: [4, 3, 6]
   :answer_d: [5, 3, 6]
   :answer_e: [4, 5, 3, 6]
   :correct: b
   :feedback_a: The remove(1) removes the item at index 1 which will be 5 after the 4 is added at index 0.  
   :feedback_b: The add(6) adds the 6 at the end of the list. The add(0,4) will add 4 at index 0. The remove(1) removes the 5 at index 1. 
   :feedback_c: The remove(1) doesn't remove the 1, it removes the value at index 1.
   :feedback_d: The 5 will be removed with the remove(1).  
   :feedback_e: This would be true if remove(1) removed the item with that value, but it removes the item at that index.

   What is in the list ``nums`` if it initially contained {5, 3, 1} and the following code is executed?
   
   .. code-block:: java
   
      nums.add(6);
      nums.add(0,4);
      nums.remove(1);
      
      
.. mchoice:: qalh_2
   :practice: T
   :answer_a: [0, 0, 4, 2, 5, 0, 3, 0]
   :answer_b: [3, 5, 2, 4, 0, 0, 0, 0]
   :answer_c: [0, 0, 0, 0, 4, 2, 5, 3]
   :answer_d: [4, 2, 5, 3]
   :answer_e: [0, 4, 2, 5, 3]
   :correct: e
   :feedback_a: This shows the original values but this code does remove some zeros so this can't be right.
   :feedback_b: This shows all zeros at the end, but this code removes 0's so this can't be right.
   :feedback_c: This shows all zeros at the beginning, but this code removes zeros so this can't be right.
   :feedback_d: This shows all zeros removed. This would be correct if k was only incremented if a value wasn't removed.
   :feedback_e: This code will loop through the array list and if the current value at the current index (k) is 0, it will remove it. When you remove a value from an array list, it moves all values to the right of that down one. So the first 0 will be deleted but the second one will not since k is incremented even if you remove something. You should only increment k if you didn't remove something and then you would remove all 0's from the list.

   Assume that nums has been created as an ArrayList object and initially contains the following Integer values: [0, 0, 4, 2, 5, 0, 3, 0]. What will nums contain as a result of executing the following method numQuest?
   
   .. code-block:: java

     private List<Integer> nums;

     //precondition: nums.size() > 0
     //nums contains Integer objects
     public void numQuest() {
        int k = 0;
        Integer zero = new Integer(0);
        while (k < nums.size()) {
           if (nums.get(k).equals(zero))
              nums.remove(k);
           k++;
        }
     }
     


Hard Search/Sort Multiple Choice Questions
------------------------------------------


.. mchoice:: qssm_1
   :practice: T
   :answer_a: A B B C D
   :answer_b: E D C B B A
   :answer_c: A B B C D E
   :answer_d: E D C B A B
   :answer_e: E D C B B
   :correct: c
   :feedback_a: This would be true if the for loop inside the main method did not interate through every value in the array.
   :feedback_b: This would be true if the conditional statement inside the for loop stated "if (key.compareTo(letters[i]) < 0)", because that would put the array in a reverse alphabetical order.
   :feedback_c: This is an insertion sort which sorts the array in alphabetical order using the compareTo() method.
   :feedback_d: This would be true if array was not modified at all in the main method.
   :feedback_e: This would be true if the conditional statement inside the for loop stated "if (key.compareTo(letters[i]) < 0)" and if the loop did not iterate through every item of the letters array, because that would put the array in a reverse alphabetical order.

   What is printed when the following main method is executed? The break; statement used in this code breaks out of or terminates the loop at that point. It is not used on the AP CS A exam.

   .. code-block:: java

      public class AlphaSort
      {

          public static void main(String[] args)
          {
              int i, j;
              String key;
              String[] letters = {"E","D","C","B","A","B"};
              for (j = 1; j < letters.length; j++)
              {
                  key = letters[j];
                  i = j - 1;
                  while (i >= 0)
                  {
                      if (key.compareTo(letters[i]) > 0)
                      {
                          break;
                      }
                      letters[i + 1] = letters[i];
                      i--;
                  }
                  letters[i + 1] = key;
              }
              for (int t = 0; t < letters.length; t++)
              {
                  System.out.print((letters[t]) + "");
              }
          }
      }


.. mchoice:: qssm_2
   :practice: T
   :answer_a: 4
   :answer_b: 2
   :answer_c: 12
   :answer_d: 1
   :correct: b
   :feedback_a: This would be true if the if statement was not trying to check if the numbers in the array were negative and odd.
   :feedback_b: This answer is correct because the for loop iterates through every element and increments the count if the current number is negative and odd.
   :feedback_c: This may be a result of misunderstanding the question, as 12 cannot be an answer because the array length itself is only 6.
   :feedback_d: This would be true if the code was looking for the numbers in the array that were positive and odd.

   What is printed when the following main method is executed?

   .. code-block:: java

      public class NumberCount
      {
          public static void main(String[] args)
          {
              int count = 0;
              int[] numbers = {-5,4,-5,3,-2,-4};
              for (int j = 0; j < numbers.length; j++)
              {
                  if(numbers[j] < 0 && numbers[j] % 2 != 0)
                  {
                      count++;
                  }
              }
          System.out.println(count);
          }
      }

You can step through the code above by clicking on the following link `Ex-12-8-2 <https://goo.gl/MGwTeT>`_.

.. mchoice:: qssm_3
   :practice: T
   :answer_a: -3
   :answer_b: -4
   :answer_c: 4
   :answer_d: 0
   :correct: d
   :feedback_a: This would be true if there were three strings in the array that had the same first letter as the last letter.
   :feedback_b: This would be true if there were four strings in the array that had the same first letter as the last letter.
   :feedback_c: This would be true if there had been four strings in the array that had the first letter as an A and those strings' last letter was not an A.
   :feedback_d: This is the correct answer. The for loop is iterating through every element in the guestList array and the first if statement is checking to see if the current element in the array starts with the same letter and ends with the same letter. The variable, count decreases by one if that is true. However if that is false, the program goes to the else if statment and checks to see if the first letter is an A. If that is true count increases by one.

   What is printed when the following main method is executed?

   .. code-block:: java

	  public class GuestList
	  {
	      public static void main(String[] args)
	      {
	          int count = 0;
	          String[] guestList = {"Anna", "Briana", "Alex", "John"};
	          String subj1 = null;
	          String subj2 = null;
	          for (int j = 0; j < guestList.length; j++)
	          {
	              subj1 = guestList[j].substring(0,1);
	              subj2 = guestList[j].substring(guestList[j].length()-1);
	              if(subj1.equalsIgnoreCase(subj2))
	              {
	                  count--;
	              }
	              else if(subj1.equalsIgnoreCase("a"))
	              {
	                  count++;
	              }
	          }
	          System.out.println(count);
	      }
	  }


You can step through the code above by clicking on the following link `Ex-12-8-3 <https://goo.gl/MGXSF2>`_.

.. mchoice:: qssm_4
   :practice: T
   :answer_a: 8,7,7,3,4,1
   :answer_b: 4,7,7,3,8,1
   :answer_c: 4,8,7,1,3,7
   :answer_d: 1,8,7,7,4,3
   :correct: b
   :feedback_a: This would be true if the array was not modified at all.
   :feedback_b: This is the correct answer. The for loop is iterating through every element in the array. The if statement is checking to see if the current element is even or odd. If it is even, then the first element of the array and the current element will swap places in the array.
   :feedback_c: This would be true if the loop had brought all the even numbers to the beginning of the array.
   :feedback_d: This would be true if the if statement had said: if(arr[i] % 2 == 1).

   What is printed when the following main method is executed?

   .. code-block:: java

	  public class OddEvenMod
	  {
	      public static void main(String[] args)
	      {
	          int[] arr = {8,7,7,3,4,1};
	          for (int i = 0; i < arr.length; i++)
	          {
	              if(arr[i] % 2 == 0)
	              {
	                  int temp = arr[0];
	                  arr[0] = arr[i];
	                  arr[i] = temp;
	              }
	          }
	          for (int t = 0; t < arr.length; t++)
	          {
	              System.out.print((arr[t]) + ",");
	          }
	      }
	  }

You can step through the code above by clicking on the following link `Ex-12-8-4 <https://goo.gl/Rpc4o4>`_.

.. mchoice:: qssm_5
   :practice: T
   :answer_a: 3,5,3,9,2,4,
   :answer_b: 4,5,2,3,9,3,
   :answer_c: 5,3,2,9,3,4,
   :answer_d: 2,3,5,9,3,
   :correct: a
   :feedback_a: This is the correct answer. The check method is using a for loop and an if statement to return true if the parameter is prime and false if it is not prime. In the main method, the for loop iterates through every element in the array and checks to see if it is prime. If it is prime, then the program will swap that element with the first element in the array.
   :feedback_b: This would be true if the if statement had said: if(!check(arr[i])).
   :feedback_c: This would be true if the array had not been modified at all.
   :feedback_d: This would be true if the final for loop did not iterate through every element in the array.

   What is printed when the following main method is executed?

   .. code-block:: java

	  public class PrimeOrNot
	  {
	      private static boolean check(int n)
	      {
	          for(int i = 2; i < n; i++)
	          {
	              if(n % i == 0)
	                  return false;
	          }
	          return true;
	      }

	      public static void main(String[] args)
	      {
	          int[] arr = {5,3,2,9,3,4};
	          for (int i = 0; i < arr.length; i++)
	          {
	              if(check(arr[i]))
	              {
	                  int temp = arr[0];
	                  arr[0] = arr[i];
	                  arr[i] = temp;
	              }
	          }
	          for (int t = 0; t < arr.length; t++)
	          {
	              System.out.print((arr[t]) + ",");
	          }
	      }
	  }

You can step through the code above by clicking on the following link `Ex-12-8-5 <http://www.pythontutor.com/java.html#code=public%20class%20PrimeOrNot%0A%7B%0A%20%20%20%20private%20static%20boolean%20check%28int%20n%29%0A%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20for%28int%20i%20%3D%202%3B%20i%20%3C%20n%3B%20i%2B%2B%29%0A%20%20%20%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20if%28n%20%25%20i%20%3D%3D%200%29%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20return%20false%3B%0A%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%20%20return%20true%3B%0A%20%20%20%20%7D%0A%0A%20%20%20%20public%20static%20void%20main%28String%5B%5D%20args%29%0A%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20int%5B%5D%20arr%20%3D%20%7B5,3,2,9,3,4%7D%3B%0A%20%20%20%20%20%20%20%20for%20%28int%20i%20%3D%200%3B%20i%20%3C%20arr.length%3B%20i%2B%2B%29%0A%20%20%20%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20if%28check%28arr%5Bi%5D%29%29%0A%20%20%20%20%20%20%20%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20int%20temp%20%3D%20arr%5B0%5D%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20arr%5B0%5D%20%3D%20arr%5Bi%5D%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20arr%5Bi%5D%20%3D%20temp%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%20%20for%20%28int%20t%20%3D%200%3B%20t%20%3C%20arr.length%3B%20t%2B%2B%29%0A%20%20%20%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20System.out.print%28%28arr%5Bt%5D%29%20%2B%20%22,%22%29%3B%0A%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%7D%0A%7D&cumulative=false&curInstr=111&heapPrimitives=false&mode=display&origin=opt-frontend.js&py=java&rawInputLstJSON=%5B%5D&textReferences=false>`_.

.. mchoice:: qssm_6
   :practice: T
   :answer_a: Anna John Billy Bob Roger Dominic
   :answer_b: John Dominic Anna Roger Bob Billy
   :answer_c: Billy Bob Roger Anna Dominic John
   :answer_d: Anna John Billy Bob Roger
   :correct: b
   :feedback_a: This would be true if the program did not modify the names array at all.
   :feedback_b: This is the correct answer. The program is ordering the grades array from greatest to least as well as keeping the names with the grades.
   :feedback_c: This would be true if the program sorted the grades array from the smallest value to the largest value.
   :feedback_d: This would be true if the program did not modify the names array and if the for loop at the end of the program did not output all the values of the array.

   What is printed when the following main method is executed?

   .. code-block:: java

		public class GradeSort
		{
		   public static void main(String[] args)
		   {
			String[] names = {"Anna","John","Billy","Bob","Roger","Dominic"};
			int[] grades = {93,100,67,84,86, 93};
			int i, j, first, temp;
			String temp2;
			for (i = grades.length - 1; i > 0; i--)
			{
			    first = 0;
			    for (j = 1; j <= i; j++)
			    {
			        if (grades[j] < grades[first])
			            first = j;
			    }
			    temp = grades[first];
			    grades[first] = grades[i];
			    grades[i] = temp;
			    temp2 = names[first];
			    names[first] = names[i];
			    names[i] = temp2;
			}
			for (int t = 0; t < names.length; t++)
			{
			    System.out.print((names[t]) + " ");
			}
		   }
		}

You can step through the code above by clicking on the following link `Ex-12-8-6 <https://goo.gl/rXzB1c>`_.

.. mchoice:: qssm_7
   :practice: T
   :answer_a: 6 7 17 3 2 9 1 5
   :answer_b: 9 6 3 2 3 1 5 17
   :answer_c: 5 1 2 3 6 17 7 9
   :answer_d: 9 7 17 6 3 2 1 5
   :correct: d
   :feedback_a: This would be true if the program had not modified the array at all.
   :feedback_b: This would be true if the loop was moving the position of odd numbers in the array to arr.length-1.
   :feedback_c: This would be true if the array was printed in the reversed order.
   :feedback_d: This is the correct answer, because the divCheck method is checking to see if the values in the array are divisible by 2 or 3. If they are, they are swapped with the value at the first position (index 0).

   What is printed when the following main method is executed?

   .. code-block:: java

	  public class DivisibleBy2or3
	  {
	      private static boolean divCheck(int n)
	      {
	          if(n % 2 == 0 || n % 3 == 0)
	          {
	            return true;
	          }
	          return false;
	      }

	      public static void main(String[] args)
	      {
	          int[] arr = {6,7,17,3,2,9,1,5};
	          for (int i = 0; i < arr.length; i++)
	          {
	              if(divCheck(arr[i]))
	              {
	                  int temp = arr[0];
	                  arr[0] = arr[i];
	                  arr[i] = temp;
	              }
	          }
	          for (int t = 0; t < arr.length; t++)
	          {
	              System.out.print((arr[t]) + " ");
	          }
	      }
	  }

You can step through the code above by clicking on the following link `Ex-12-8-7 <https://goo.gl/LrbUuu>`_.



