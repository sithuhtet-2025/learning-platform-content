In **Java,** the array length is the number of elements that an array can hold. There is no predefined method to obtain the **length of an array**. We can find the **array length in Java** by using the array attribute **length**. We use this attribute with the array name.

## Array length Attribute

[Java](https://www.tpointtech.com/java-tutorial) provides an attribute **length** that determines the **length of an array**. Every array has an in-built **length** property whose value is the size of the array. Size implies the total number of elements that an array can contain. The length property can be invoked by using the **dot (.) operator** followed by the array name. We can find the length of int[], double[], String[], etc. For example:

[](https://www.tpointtech.com/java-array-length#)[](https://www.tpointtech.com/java-array-length#)[](https://www.tpointtech.com/java-array-length#)

1. int[] arr=new int[5];  
2. int arrayLength=arr.length  

In the above code snippet, **arr** is an array of type int that can hold 5 elements. The **arrayLength** is a variable that stores the length of an array. To find the length of the array, we have used the array name (arr) followed by the dot operator and length attribute, respectively. It determines the size of the array.

![How to Find Array Length in Java](https://images.tpointtech.com/core/images/how-to-find-array-length-in-java.png)

Note that length determines the maximum number of elements that the array can contain or the capacity of the array. It does not count the elements that are inserted into the array. That is, length returns the total size of the array. For arrays whose elements are initialized at the time of its creation, length and size are the same.

If we talk about the logical size, the index of the array, then simply int **arrayLength=arr.length-1**, because the array index starts from 0. So, the logical or array index will always be less than the actual size by 1.

![How to Find Array Length in Java](https://images.tpointtech.com/core/images/how-to-find-array-length-in-java2.png)

## Finding Array Length Using .length Attribute

The following example demonstrates finding the length of an array using .length attribute.

### Example

[](https://www.tpointtech.com/java-array-length#)[](https://www.tpointtech.com/java-array-length#)[](https://www.tpointtech.com/java-array-length#)

1. public class Main  {     
2. public static void main(String[] args)   {     
3. //defining an array of type int named num    
4. //The square bracket contains the length of an array    
5. int[] num = new int[10];     
6. //length is an Array attribute that determines the array length     
7. int arrayLength=num.length;    
8. //prints array length    
9. System.out.println("The length of the array is: "+ arrayLength);     
10. }     
11. }    

**Output:**

The length of the array is: 10

**Explanation**

This Java code, which is part of the ArrayLengthExample1 class, shows how to find an array's length. The syntax int[] num = new int[10]; is used in the main method to declare and initialise an array of type int with a length of 10. When an array is declared, its length is specified by the square brackets. The code then determines the length of the num array by using the length attribute, which is built into all Java arrays, and assigning the result to the variable arrayLength. Finally, the program prints out the length of the array using System.out.println, providing information about the number of elements the array can hold.

## Finding Array Length Using length with String Array

The following example demonstrates finding the length of an array of strings using .length attribute.

### Example

[](https://www.tpointtech.com/java-array-length#)[](https://www.tpointtech.com/java-array-length#)[](https://www.tpointtech.com/java-array-length#)

1. public class Main   {     
2. public static void main(String[] args)   {     
3. //Initialising an array of type String named country     
4. String[] country = { "India", "Australia", "Japan", "USA", "UAE", "Canada", "Brazil"};    
5. //length is an Array attribute that determines the array length     
6. int arrayLength=country.length;     
7. //prints array length    
8. System.out.println("The size of the array is: " + arrayLength);     
9. }     
10. }    

**Output:**

The size of the array is: 7

**Explanation**

With a main method, the class ArrayLengthExample2 is defined in the Java code that is provided. Several country names are initialised into an array of type String called country inside the main procedure. Next, the code calculates the length of the nation array, or the total number of entries it may contain, using Java's length attribute for arrays. The variable arrayLength is given the length. The array's size and the number of elements it contains are finally printed by the programme using System.out.println. This code basically shows how to use Java's length attribute to find the length of an array and how to output the length for reference.

## Finding Array Length Using a Method

The following example demonstrates finding the length of an array by creating a user-defined method.

### Example

[](https://www.tpointtech.com/java-array-length#)[](https://www.tpointtech.com/java-array-length#)[](https://www.tpointtech.com/java-array-length#)

1. public class Main   {    
2. private static void LengthOfArray(String[] array)   {    
3. //checks array is empty or not        
4. if (array == null)   {    
5. //if the array is empty, prints the following statement    
6. System.out.println("The array is empty, can't be determined the length.");    
7. }     
8. else   {    
9. //The length attribute of the Array class determines the length of an array    
10. int arrayLength = array.length;    
11. //prints the array length    
12. System.out.println("The length of the array is: "+arrayLength);    
13. }    
14. }    
15. public static void main(String[] args)   {    
16. String[] fruits = { "Guava", "Banana", "Apple", "Papaya", "Melon", "Strawberry"};    
17. String[] alphabets = { "m", "p", "k", "l", "t" };    
18. String[] numbers = { "12", "25", "63", "84", "90", "11", "54"};    
19. //passing a null value to the function    
20. LengthOfArray(null);    
21. //passing the fruits array to the function    
22. LengthOfArray(fruits);    
23. //passing the alphabet array to the function    
24. LengthOfArray(alphabets);    
25. //passing the numbers array to the function    
26. LengthOfArray(numbers);    
27. }    
28. }    

**Output:**

The array is empty, can't be determined the length.
The length of the array is: 6
The length of the array is: 5
The length of the array is: 7

**Explanation**

The Java code that is provided defines a class called Main, and in that class, there is a method called LengthOfArray that is used to find and report the length of a specified array of strings. The procedure initially determines if the supplied array is null or empty by looking at its value. It prints a message saying that the length cannot be computed if the array is empty. If not, it uses the Array class's length attribute to determine the array's length and displays it. LengthOfArray's usefulness is demonstrated in the main method by passing several arrays, such as a null value, an array of fruits, alphabets, and numerals. The length of each array is output by the programme when it runs.

## Finding Array Length by Traversing Array

Another method involves iterating through the array and counting the number of elements encountered. This approach provides more flexibility and control over the counting process.

### Example

[](https://www.tpointtech.com/java-array-length#)[](https://www.tpointtech.com/java-array-length#)[](https://www.tpointtech.com/java-array-length#)

1. public class Main {    
2.     public static void main(String[] args) {    
3.         int[] arr = new int[5];    
4.         int count = 0;    
5.         for (int element : arr) {    
6.             count++;    
7.         }    
8.         int arrayLength = count;    
9.         System.out.println("The length of the array is: " + arrayLength);    
10.     }    
11. }    

**Output:**

The length of the array is: 5

**Explanation**

The array's length is ascertained by initialising a variable called count to 0. Next, each element of the array is iterated through using a for-each loop. The loop does nothing to the items themselves; instead, it iterates over every element in the array. For every iteration, it only increases the count variable. Count effectively counts the number of elements in the array by performing this.

Following the loop, the array's length is represented by the variable arrayLength, to which the value of count is assigned. Lastly, the programme uses System.out.println() to print the array's length and the maximum number of elements it can contain.