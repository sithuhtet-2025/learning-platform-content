Reversing an array is a common task that can be achieved using **multiple approaches**, such as using auxiliary array, two pointers, stack, or using the built-in methods. Here, we will learn these different techniques to reverse an array.

## Problem Statement

In the input, an integer array is provided, and the task is to reverse the array. Reversing an array means the last element of the input array becomes the first element of the reversed array, the second-last element becomes the second element, and so on. Observe the following examples.

**Example 1:**

**Input:**

arr[] = {1, 2, 3, 4, 5, 6, 7, 8}

**Output**

arr[] = {8, 7, 6, 5, 4, 3, 2, 1}

**Example 2:**

**Input:**

arr[] = {4, 8, 3, 9, 0, 1}

**Output:**

arr[] = {1, 0, 9, 3, 8, 4}

## Reverse an Array Using an Auxiliary Array

We can traverse the array from end to beginning, i.e., in reverse order, and store the element pointed by the loop index in the auxiliary array. The auxiliary array now contains the elements of the input array in reversed order. After that, we can display the auxiliary array on the console. See the following program.

### Example

The following example demonstrates reversing an array using an auxiliary array.

[](https://www.tpointtech.com/reverse-an-array-in-java#)[](https://www.tpointtech.com/reverse-an-array-in-java#)[](https://www.tpointtech.com/reverse-an-array-in-java#)

1. public class ReverseArr  
2. {  
3. // method for reversing an array  
4. public int[]  reverseArray(int arr[])  
5. {  
6.     // computing the size of the array arr  
7.     int size = arr.length;  

8.     // auxiliary array for reversing the   
9.     // elements of the array arr  
10.     int temp[] = new int[size];  

11.     int index = 0;  
12.     for(int i = size - 1; i >= 0; i--)  
13.     {  
14.         temp[i] = arr[index];  
15.         index = index + 1;  
16.     }  

17.     return temp;  

18. }  

19. // main method  
20. public static void main(String argvs[])   
21. {  
22.   // creating an object of the class ReverseArr  
23.   ReverseArr obj = new ReverseArr();  

24.   // input array - 1  
25.   int arr[] = {1, 2, 3, 4, 5, 6, 7, 8};  

26.   // computing the length  
27.   int len = arr.length;  
28.   int ans[] = obj.reverseArray(arr);  

29.   System.out.println("For the input array: ");  
30.   for(int  i = 0; i < len; i++)  
31.   {  
32.      System.out.print(arr[i] + " ");  
33.   }  

34.   System.out.println();  
35.   System.out.println("The reversed array is: ");  
36.   for(int  i = 0; i < len; i++)  
37.   {  
38.      System.out.print(ans[i] + " ");  
39.   }  

40.   System.out.println("\n ");  

41.   // input array - 2  
42.   int arr1[] = {4, 8, 3, 9, 0, 1};  

43.   // computing the length  
44.   len = arr1.length;  
45.   int ans1[] = obj.reverseArray(arr1);  

46.   System.out.println("For the input array: ");  
47.   for(int  i = 0; i < len; i++)  
48.   {  
49.      System.out.print(arr1[i] + " ");  
50.   }  

51.   System.out.println();  
52.   System.out.println("The reversed array is: ");  
53.   for(int  i = 0; i < len; i++)  
54.   {  
55.      System.out.print(ans1[i] + " ");  
56.   }  

57. }  
58. }  

**Output:**

For the input array:
1 2 3 4 5 6 7 8
The reversed array is:
8 7 6 5 4 3 2 1

For the input array:
4 8 3 9 0 1
The reversed array is:
1 0 9 3 8 4

**Complexity Analysis:** A for loop is required to reverse the array, which makes the time complexity of the program O(n). Also, an auxiliary array is required to reverse the array making the space complexity of the program O(n), where n is the total number of elements present in the array.

## Reverse an Array Using Two Pointers

We can also use two pointers to reverse the input array. The first pointer will go to the first element of the array. The second pointer will point to the last element of the input array. Now we will start swapping elements pointed by these two pointers. After swapping, the second pointer will move in the leftward direction, and the first pointer will move in the rightward direction. When these two pointers meet or cross each other, we stop the swapping, and the array we get is the reversed array of the input array.

### Example

The following example demonstrates reversing an array using two pointers.

[](https://www.tpointtech.com/reverse-an-array-in-java#)[](https://www.tpointtech.com/reverse-an-array-in-java#)[](https://www.tpointtech.com/reverse-an-array-in-java#)

1. public class ReverseArr1  
2. {  
3. // method for reversing an array  
4. public int[]  reverseArray(int arr[])  
5. {  
6.     // computing the size of the array arr  
7.     int size = arr.length;  

8.     // two pointers for reversing   
9.     // the input array  
10.     int ptr1 = 0;  
11.     int ptr2 = size - 1;  

12.     // reversing the input array  
13.     // using a while loop  
14.     while(ptr1 < ptr2)  
15.     {  
16.         int temp = arr[ptr1];  
17.         arr[ptr1] = arr[ptr2];  
18.         arr[ptr2] = temp;  

19.         ptr1 = ptr1 + 1;  
20.         ptr2 = ptr2 - 1;  
21.     }  

22.     return arr;  

23. }  

24. // main method  
25. public static void main(String argvs[])   
26. {  
27.   // creating an object of the class ReverseArr1  
28.   ReverseArr1 obj = new ReverseArr1();  

29.   // input array - 1  
30.   int arr[] = {1, 2, 3, 4, 5, 6, 7, 8};  

31.   // computing the length  
32.   int len = arr.length;  

33.   System.out.println("For the input array: ");  
34.   for(int  i = 0; i < len; i++)  
35.   {  
36.      System.out.print(arr[i] + " ");  
37.   }  

38.   int ans[] = obj.reverseArray(arr);  

39.   System.out.println();  
40.   System.out.println("The reversed array is: ");  
41.   for(int  i = 0; i < len; i++)  
42.   {  
43.      System.out.print(ans[i] + " ");  
44.   }  

45.   System.out.println("\n ");  

46.   // input array - 2  
47.   int arr1[] = {4, 8, 3, 9, 0, 1};  

48.   // computing the length  
49.   len = arr1.length;  

50.   System.out.println("For the input array: ");  
51.   for(int  i = 0; i < len; i++)  
52.   {  
53.      System.out.print(arr1[i] + " ");  
54.   }  

55.   int ans1[] = obj.reverseArray(arr1);  

56.   System.out.println();  
57.   System.out.println("The reversed array is: ");  
58.   for(int  i = 0; i < len; i++)  
59.   {  
60.      System.out.print(ans1[i] + " ");  
61.   }  

62. }  
63. }  

**Output:**

For the input array:
1 2 3 4 5 6 7 8
The reversed array is:
8 7 6 5 4 3 2 1

For the input array:
4 8 3 9 0 1
The reversed array is:
1 0 9 3 8 4

**Complexity Analysis:** The time complexity of the program is the same as the previous program. There is no extra space used in the program, making the space complexity of the program O(1).

## Reverse an Array Using Stack

Since a Stack works on the LIFO (Last In First Out) principle, it can be used to reverse the input array. All we have to do is to put all the elements of the input array in the stack, starting from left to right. We will do it using a loop.

### Example

The following example demonstrates reversing an array using stack.

[](https://www.tpointtech.com/reverse-an-array-in-java#)[](https://www.tpointtech.com/reverse-an-array-in-java#)[](https://www.tpointtech.com/reverse-an-array-in-java#)

1. // importing Stack  
2. import java.util.Stack;  

3. public class ReverseArr2  
4. {  
5. // method for reversing an array  
6. public int[]  reverseArray(int arr[])  
7. {  
8.     // computing the size of the array arr  
9.     int size = arr.length;  

10.     Stack<Integer> stk = new Stack<Integer>();  

11.     // pusing all the elements into stack  
12.     // starting from left  
13.     for(int i = 0; i < size; i++)  
14.     {  
15.         stk.push(arr[i]);  
16.     }  

17.     int i = 0;  
18.     while(!stk.isEmpty())  
19.     {  
20.         int ele = stk.pop();  
21.         arr[i] = ele;  
22.         i = i + 1;  
23.     }  

24.     return arr;  

25. }  

26. // main method  
27. public static void main(String argvs[])   
28. {  
29.   // creating an object of the class ReverseArr2  
30.   ReverseArr2 obj = new ReverseArr2();  

31.   // input array - 1  
32.   int arr[] = {1, 2, 3, 4, 5, 6, 7, 8};  

33.   // computing the length  
34.   int len = arr.length;  

35.   System.out.println("For the input array: ");  
36.   for(int  i = 0; i < len; i++)  
37.   {  
38.      System.out.print(arr[i] + " ");  
39.   }  

40.   int ans[] = obj.reverseArray(arr);  

41.   System.out.println();  
42.   System.out.println("The reversed array is: ");  
43.   for(int  i = 0; i < len; i++)  
44.   {  
45.      System.out.print(ans[i] + " ");  
46.   }  

47.   System.out.println("\n ");  

48.   // input array - 2  
49.   int arr1[] = {4, 8, 3, 9, 0, 1};  

50.   // computing the length  
51.   len = arr1.length;  

52.   System.out.println("For the input array: ");  
53.   for(int  i = 0; i < len; i++)  
54.   {  
55.      System.out.print(arr1[i] + " ");  
56.   }  

57.   int ans1[] = obj.reverseArray(arr1);  

58.   System.out.println();  
59.   System.out.println("The reversed array is: ");  
60.   for(int  i = 0; i < len; i++)  
61.   {  
62.      System.out.print(ans1[i] + " ");  
63.   }  

64. }  
65. }  

**Output:**

For the input array:
1 2 3 4 5 6 7 8
The reversed array is:
8 7 6 5 4 3 2 1

For the input array:
4 8 3 9 0 1
The reversed array is:
1 0 9 3 8 4

**Complexity Analysis:** The time complexity of the program is the same as the previous program. There is stack used in the program, making the space complexity of the program O(n).

## Reverse an Array Using Recursion

Using recursion also, we can achieve the same result. Observe the following.

### Example

The following example demonstrates reversing an array using recursion.

[](https://www.tpointtech.com/reverse-an-array-in-java#)[](https://www.tpointtech.com/reverse-an-array-in-java#)[](https://www.tpointtech.com/reverse-an-array-in-java#)

1. // importing ArrayList  
2. import java.util.ArrayList;  

3. public class ReverseArr3  
4. {  
5. ArrayList<Integer> reverseArr;  

6. // constructor of the class  
7. ReverseArr3()  
8. {  
9. reverseArr = new  ArrayList<Integer>();  
10. }  

11. // method for reversing an array  
12. public void  reverseArray(int arr[], int i, int size)  
13. {  
14. // dealing with the base case  
15. if(i >= size)  
16. {  
17.     return;  
18. }  

19. // recursively calling the method  
20. reverseArray(arr, i + 1, size);  
21. reverseArr.add(arr[i]);  

22. }  

23. // main method  
24. public static void main(String argvs[])   
25. {  
26.   // creating an object of the class ReverseArr3  
27.   ReverseArr3 obj = new ReverseArr3();  

28.   // input array - 1  
29.   int arr[] = {1, 2, 3, 4, 5, 6, 7, 8};  

30.   // computing the length  
31.   int len = arr.length;  

32.   System.out.println("For the input array: ");  
33.   for(int  i = 0; i < len; i++)  
34.   {  
35.      System.out.print(arr[i] + " ");  
36.   }  

37.   obj.reverseArray(arr, 0 , len);  

38.   System.out.println();  
39.   System.out.println("The reversed array is: ");  
40.   for(int  i = 0; i < len; i++)  
41.   {  
42.      System.out.print(obj.reverseArr.get(i) + " ");  
43.   }  

44.   System.out.println("\n ");  

45.   obj = new ReverseArr3();  

46.   // input array - 2  
47.   int arr1[] = {4, 8, 3, 9, 0, 1};  

48.   // computing the length  
49.   len = arr1.length;  

50.   System.out.println("For the input array: ");  
51.   for(int  i = 0; i < len; i++)  
52.   {  
53.      System.out.print(arr1[i] + " ");  
54.   }  

55.   obj.reverseArray(arr1, 0, len);  

56.   System.out.println();  
57.   System.out.println("The reversed array is: ");  
58.   for(int  i = 0; i < len; i++)  
59.   {  
60.       System.out.print(obj.reverseArr.get(i) + " ");  
61.   }  

62. }  
63. }  

**Output:**

For the input array:
1 2 3 4 5 6 7 8
The reversed array is:
8 7 6 5 4 3 2 1

For the input array:
4 8 3 9 0 1
The reversed array is:
1 0 9 3 8 4

**Explanation:** The statement _reverseArr.add(arr[i]);_ is written after the recursive call goes in the stack (note that the stack is implicit in this case). So, when the base case is hit in the recursive call, stack unwinding happens, and whatever is there in the stack pops out. The last element goes into the stack during the last recursive call. Therefore, the last element is popped out first. Then the penultimate element is popped out, and so on. The statement _reverseArr.add(arr[i]);_ stores that popped element. In the end, we are displaying the elements that are stored in the list _reverseArr_.

**Complexity Analysis:** Same as the first program of approach-3.

## Reverse an Array Using Collections.reverse() Method

The build method Collections.reverse() can be used to reverse the list. The use of it is shown in the following program.

### Example

The following example demonstrates reversing an array using Collections.reverse() method.

[](https://www.tpointtech.com/reverse-an-array-in-java#)[](https://www.tpointtech.com/reverse-an-array-in-java#)[](https://www.tpointtech.com/reverse-an-array-in-java#)

1. // importing Collections, Arrays, ArrayList & List  
2. import java.util.Collections;  
3. import java.util.Arrays;  
4. import java.util.List;  
5. import java.util.ArrayList;  

6. public class ReverseArr4  
7. {  

8. // method for reversing an array  
9. public List<Integer>  reverseArray(Integer arr[])  
10. {  
11. List<Integer> l = (Arrays.asList(arr));  
12. Collections.reverse(l);  
13. return l;  
14. }  

15. // main method  
16. public static void main(String argvs[])   
17. {  
18.   // creating an object of the class ReverseArr4  
19.   ReverseArr4 obj = new ReverseArr4();  

20.   // input array - 1  
21.   Integer arr[] = {1, 2, 3, 4, 5, 6, 7, 8};  

22.   // computing the length  
23.   int len = arr.length;  

24.   System.out.println("For the input array: ");  
25.   for(int  i = 0; i < len; i++)  
26.   {  
27.      System.out.print(arr[i] + " ");  
28.   }  

29.   List<Integer> ans = obj.reverseArray(arr);  

30.   System.out.println();  
31.   System.out.println("The reversed array is: ");  
32.   for(int  i = 0; i < len; i++)  
33.   {  
34.      System.out.print(ans.get(i) + " ");  
35.   }  

36.   System.out.println("\n ");  

37.   // input array - 2  
38.   Integer arr1[] = {4, 8, 3, 9, 0, 1};  

39.   // computing the length  
40.   len = arr1.length;  

41.   System.out.println("For the input array: ");  
42.   for(int  i = 0; i < len; i++)  
43.   {  
44.      System.out.print(arr1[i] + " ");  
45.   }  

46.   ans = obj.reverseArray(arr1);  

47.   System.out.println();  
48.   System.out.println("The reversed array is: ");  
49.   for(int  i = 0; i < len; i++)  
50.   {  
51.       System.out.print(ans.get(i) + " ");  
52.   }  

53. }  
54. }  

**Output:**

For the input array:
1 2 3 4 5 6 7 8
The reversed array is:
8 7 6 5 4 3 2 1

For the input array:
4 8 3 9 0 1
The reversed array is:
1 0 9 3 8 4

**Complexity Analysis:** The program uses _Collections.reverse()_ method that reverses the list in linear time, making the time complexity of the program O(n). The program uses using list, making the space complexity of the program O(n), where n is the total number of elements present in the array.

#### Note 1: _Collections.reverse()_ method is also used to reverse the linked list.

#### Note 2: All the approaches discussed above are applicable to different data types too.

## Reverse an Array Using StringBuilder.append() Method

It is evident from the heading that this approach is applicable to string arrays. Using the StringBuilder.append() method, we can reverse the string array. All we have to do is to start appending the string elements of the array from the last to the beginning.

### Example

The following example demonstrates reversing an array using StringBuilder.append() method.

[](https://www.tpointtech.com/reverse-an-array-in-java#)[](https://www.tpointtech.com/reverse-an-array-in-java#)[](https://www.tpointtech.com/reverse-an-array-in-java#)

1. import java.util.*;  

2. public class ReverseArr5  
3. {  

4. // method for reversing an array  
5. public String[]  reverseArray(String arr[])  
6. {  
7. StringBuilder reversedSB = new StringBuilder();  

8. for (int j = arr.length; j > 0; j--)   
9. {  
10.   reversedSB.append(arr[j - 1]).append(" ");  
11. };  

12. String[] reversedArr = reversedSB.toString().split(" ");  
13. return reversedArr;  
14. }  

15. // main method  
16. public static void main(String argvs[])   
17. {  
18.   // creating an object of the class ReverseArr5  
19.   ReverseArr5 obj = new ReverseArr5();  

20.   // input array - 1  
21.   String arr[] = {"javaTpoint", "is", "the", "best", "website"};  

22.   // computing the length  
23.   int len = arr.length;  

24.   System.out.println("For the input array: ");  
25.   for(int  i = 0; i < len; i++)  
26.   {  
27.      System.out.print(arr[i] + " ");  
28.   }  

29.   String[] ans = obj.reverseArray(arr);  

30.   System.out.println();  
31.   System.out.println("The reversed array is: ");  
32.   for(int  i = 0; i < len; i++)  
33.   {  
34.      System.out.print(ans[i] + " ");  
35.   }  

36.   System.out.println("\n ");  

37.   // input array - 2  
38.   String arr1[] = {"India", "is", "my", "country"};  

39.   // computing the length  
40.   len = arr1.length;  

41.   System.out.println("For the input array: ");  
42.   for(int  i = 0; i < len; i++)  
43.   {  
44.      System.out.print(arr1[i] + " ");  
45.   }  

46.   String[] ans1 = obj.reverseArray(arr1);  

47.   System.out.println();  
48.   System.out.println("The reversed array is: ");  
49.   for(int  i = 0; i < len; i++)  
50.   {  
51.       System.out.print(ans1[i] + " ");  
52.   }  

53. }  
54. }  

**Output:**

For the input array:
javaTpoint is the best website
The reversed array is:
website best the is javaTpoint

For the input array:
India is my country
The reversed array is:
country my is India

**Complexity Analysis:** The time and space complexity of the program is the same as the previous program.