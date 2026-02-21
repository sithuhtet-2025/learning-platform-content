An Array is an essential and most used data structure in [Java](https://www.tpointtech.com/java-tutorial). It is one of the most used data structure by programmers due to its efficient and productive nature; The Array is a collection of similar data type elements. It uses a contiguous memory location to store the elements.

## What is a String Array?

**_A String Array is an Array of a fixed number of String values_**. A String is a sequence of characters. Generally, a string is an immutable object, which means the value of the string can not be changed. The String Array works similarly to other data types of Array.

Similar to arrays, in string array only a fixed set of elements can be stored. It is an index-based data structure, which starts from the 0th position. The first element will take place in Index 0, and the 2nd element will take place in Index 1, and so on.

The main method {Public static void main[ String [] args]; } in Java is also an String Array.

Consider the below points about the String Array:

- It is an object of the Array.
- It can be declared by the two methods; by specifying the size or without specifying the size.
- It can be initialized either at the time of declaration or by populating the values after the declaration.
- The elements can be added to a String Array after declaring it.
- The String Array can be iterated using the for loop.
- The searching and sorting operation can be performed on the String Array.

## Declaration of String Array

The Array declaration is of two types, either we can specify the size of the Array or without specifying the size of the Array. A String Array can be declared as follows:

[](https://www.tpointtech.com/string-array-in-java#)[](https://www.tpointtech.com/string-array-in-java#)[](https://www.tpointtech.com/string-array-in-java#)

1. String[] stringArray1   //Declaration of the String Array without specifying the size  
2. String[] stringArray2 = new String[2];   //Declarartion by specifying the size  

Another way of declaring the Array is **_String strArray[]_**, but the above-specified methods are more efficient and recommended.

## Initialization of String Array

The String Array can be initialized easily. Below is the initialization of the String Array:

[](https://www.tpointtech.com/string-array-in-java#)[](https://www.tpointtech.com/string-array-in-java#)[](https://www.tpointtech.com/string-array-in-java#)

1. 1. String[] strAr1=new String[] {"Ani", "Sam", "Joe"}; //inline initialization  
2. 2. String[] strAr2 = {"Ani", "Sam", " Joe"};  
3. 3. String[] strAr3= new String[3]; //Initialization after declaration with specific size  
4.    strAr3[0]= "Ani";  
5.    strAr3[1]= "Sam";  
6.    strAr3[2]= "Joe";  

All of the above three ways are used to initialize the String Array and have the same value.

The 3rd method is a specific size method. In this, the value of the index can be found using the ( **arraylength - 1**) formula if we want to access the elements more than the index 2 in the above Array. It will throw the **Java.lang.ArrayIndexOutOfBoundsException** exception.

## Iteration (Traversing) of String Array

A string array can be traversed using both the [for loop](https://www.tpointtech.com/java-for-loop) and the [enhanced for-each loop](https://www.tpointtech.com/for-each-loop-in-java). These loops allow you to access and process each element of the array by iterating through the index of each element in the case of a for loop, or directly accessing each element in the case of a for-each loop.

### Example

The following example demonstrates how to iterate through a string array containing names of students in a class using both a for loop and a for-each loop:

[](https://www.tpointtech.com/string-array-in-java#)[](https://www.tpointtech.com/string-array-in-java#)[](https://www.tpointtech.com/string-array-in-java#)

1. public class Main {  
2.     public static void main(String[] args) {  
3.         // Array of student names  
4.         String[] students = {"Ani", "Sam", "Joe"};  

5.         // Using for loop  
6.         System.out.println("Using for loop:");  
7.         for (int i = 0; i < students.length; i++) {  
8.             System.out.println(students[i]);  
9.         }  

10.         // Using for-each loop  
11.         System.out.println("\nUsing for-each loop:");  
12.         for (String student : students) {  
13.             System.out.println(student);  
14.         }  
15.     }  
16. }  

**Output:**

Using for loop:
Ani
Sam
Joe

Using for-each loop:
Ani
Sam
Joe

## Adding Elements to a String Array

We can easily add the elements to the String Array just like other data types. It can be done using the following three methods:

- **Using Pre-Allocation of the Array**
- **Using the Array List**
- **By creating a new Array**

let's understand the above methods:

### 1. Using Pre-Allocation of the Array

In this method, we already have an Array of larger size. For example, if we require to store the 10 elements, then we will create an Array of size 20. It is the easiest way to expand the Array elements.

Consider the below example to add elements in a pre-allocated array.

[](https://www.tpointtech.com/string-array-in-java#)[](https://www.tpointtech.com/string-array-in-java#)[](https://www.tpointtech.com/string-array-in-java#)

1. // Java Program to add elements in a pre-allocated Array  
2. import java.util.Arrays;  
3. public class StringArrayDemo {  
4.         public static void main(String[] args) {  
5.             String[] sa = new String[7]; // Creating a new Array of Size 7  
6.             sa[0] = "A"; // Adding Array elements  
7.             sa[1] = "B";  
8.             sa[2] = "C";  
9.             sa[3] = "D";  
10.             sa[4] = "E";  
11.             System.out.println("Original Array Elements:" + Arrays.toString(sa));  
12.             int numberOfItems = 5;  
13.             String newItem = "F"; // Expanding Array Elements Later  
14.             String newItem2 ="G";  
15.             sa[numberOfItems++] = newItem;  
16.             sa[numberOfItems++] = newItem2;  
17.             System.out.println("Array after adding two elements:" +    
18.                       Arrays.toString(sa));  
19.         }  
20.     }  

**Output:**

Original Array Elements:[A, B, C, D, E, null, null]
Array after adding two elements:[A, B, C, D, E, F, G]

From the above example, we have added two elements in a pre-allocated Array.

### 2. Using ArrayList

The [ArrayList](https://www.tpointtech.com/java-arraylist) is a fascinating data structure of the [Java collection framework](https://www.tpointtech.com/collections-in-java). We can easily add elements to a [String](https://www.tpointtech.com/java-string) Array using an ArrayList as an intermediate data structure.

Consider the below example to understand how to add elements to a [String Array using ArrayList](https://www.tpointtech.com/convert-arraylist-to-string-array-in-java):

[](https://www.tpointtech.com/string-array-in-java#)[](https://www.tpointtech.com/string-array-in-java#)[](https://www.tpointtech.com/string-array-in-java#)

1. import java.util.ArrayList;  
2. import java.util.Arrays;  
3. import java.util.List;  

4. public class StringArrayDemo1 {   
5.         public static void main(String[] args)   
6.         {   
7.               // Defining a String Array   
8.               String sa[] = { "A", "B", "C", "D", "E", "F" };  
9.           //   
10.             System.out.println("Initial Array:\n"  
11.                                + Arrays.toString(sa));   
12.             String ne = "G"; // Define new element to add  
13.             List<String>l = new ArrayList<String>(  
14.                       Arrays.asList(sa)); // Convert Array to ArrayList  
15.             l.add(ne); // Add new element in ArrayList l  
16.             sa = l.toArray(sa); // Revert Conversion from ArrayList to Array  
17.             // printing the new Array  
18.             System.out.println("Array with added Value: \n"  
19.                                + Arrays.toString(sa)) ;   
20.         }   
21.     }  

**Output:**

Initial Array:
[A, B, C, D, E, F]
Array with added value:
[A, B, C, D, E, F, G]

### 3. By Creating a New Array

In this method, we will create a new Array with a larger size than the initial Array and accommodate the elements in it. We will copy all the elements to the newly added Array. Consider the following example:

[](https://www.tpointtech.com/string-array-in-java#)[](https://www.tpointtech.com/string-array-in-java#)[](https://www.tpointtech.com/string-array-in-java#)

1. // Java Program to add elements in a String Array by creating a new Array  
2. import java.util.Arrays;  
3. public class StringArrayDemo2 {  
4.         public static void main(String[] args) {  
5.             //Declaring Initial Array  
6.             String[] sa = {"A", "B", "C" };    
7.             // Printing the Original Array  
8.             System.out.println("Initial Array: " + Arrays.toString(sa));  
9.                 int length_Var = sa.length; //Defining the array length variable  
10.             String newElement = "D"; // Defining new element to add  
11.             //define new array with extended length           
12.             String[] newArray = new String[ length_Var + 1 ];  
13.             //Adding all the elements to initial Array  
14.             for (int i=0; i <sa.length; i++)  
15.             {  
16.                 newArray[i] = sa [i];  
17.              }  
18.             //Specifying the position of the added elements ( Last)  
19.             newArray[newArray.length- 1] = newElement;  
20.             //make it original and print  
21.             sa = newArray;     
22.             System.out.println("updated Array: " + Arrays.toString(sa));  
23.         }  
24.     }  

**Output:**

Initial Array: [A, B, C]
updated Array: [A, B, C, D]

This is how we can add elements to a String Array. Let's understand how to search and sort elements in String Array.

## Searching in String Array

To search for a specific string in a string array, we can use a **for loop** to iterate through each element and check if it matches the target string using the **equals()** method that returns the position of the string or verify if it exists in the array.

### Example

The following example demonstrates how to search for a name in a string array:

[](https://www.tpointtech.com/string-array-in-java#)[](https://www.tpointtech.com/string-array-in-java#)[](https://www.tpointtech.com/string-array-in-java#)

1. public class StringArrayExample {  
2.         public static void main(String[] args) {  
3.             String[] strArray = { "Ani", "Sam", "Joe" };  
4.             boolean x = false; //initializing x to false  
5.             int in = 0; //declaration of index variable  
6.             String s = "Sam";  // String to be searched  
7.             // Iteration of the String Array  
8.             for (int i = 0; i < strArray.length; i++) {  
9.                 if(s.equals(strArray[i])) {  
10.                     in = i; x = true; break;  
11.                 }  
12.             }  
13.             if(x)  
14.                 System.out.println(s +" String is found at index "+in);  
15.             else  
16.                 System.out.println(s +" String is not found in the array");  
17.         }  
18. }  

**Output:**

Sam String is found at index 1

In the above example, we have initialized a boolean variable **x** to false and an index variable to iterate through the string. Also, we have declared a local variable String variable **s** to be searched. Here, the break keyword will exit the loop as soon as the string is found.

## Sorting in String Array

The sorting in the String array is quite easy. It is performed like in a traditional array. We use a sort() method to sort the Array elements. Sorting is easier than searching.

Consider the below example to [sort a String Array](https://www.tpointtech.com/how-to-sort-string-array-in-java).

### Example

This example demonstrate how to sort string array in Java.

[](https://www.tpointtech.com/string-array-in-java#)[](https://www.tpointtech.com/string-array-in-java#)[](https://www.tpointtech.com/string-array-in-java#)

1. //Java Program to sort elements in a String Array  
2. import java.util.Arrays;  
3. public class StringArraySorting {  
4.        public static void main(String[] args)   
5.         {   
6.            // Adding String values  
7.            String[] colors = {"Cricket","Basketball","Football","Badminton","Tennis"};  
8.            // Print Original values   
9.            System.out.println("Entered Sports: "+Arrays.toString(colors));  
10.             Arrays.sort(colors); // Sorting Elements  
11.            // Print Sorted Values  
12.             System.out.println("Sorted Sports: "+Arrays.toString(colors));  
13.         }  
14.     }  

**Output:**

Entered Sports: [Cricket, Basketball, Football, Badminton, Tennis]
Sorted Sports: [Badminton, Basketball, Cricket, Football, Tennis]

From the above example, we can see the elements from a String Array is sorted using the sort() method.

We can also convert String Array to other data structures such as List, int Array, ArrayList, and more and vice-versa.

## Manipulating String Arrays

String arrays support various operations for manipulation, such as **modifying elements**. However, it's important to remember that [Java arrays](https://www.tpointtech.com/java-arrays) have a **fixed size** once initialized. Therefore, dynamic operations like adding or removing elements cannot be performed directly on arrays; for such operations, you may need to use other data structures like [ArrayList](https://www.tpointtech.com/java-arraylist).

### Example: Modifying Elements in a String Array

The following example demonstrates how to modify an element in a string array:

[](https://www.tpointtech.com/string-array-in-java#)[](https://www.tpointtech.com/string-array-in-java#)[](https://www.tpointtech.com/string-array-in-java#)

1. public class Main {  
2.     public static void main(String[] args) {  
3.         // Array of student names  
4.         String[] students = {"Ani", "Sam", "Joe"};  

5.         // Modifying the second element  
6.         students[1] = "Sara";  

7.         // Printing the modified array  
8.         for (String student : students) {  
9.             System.out.println(student);  
10.         }  
11.     }  
12. }  

**Output:**

Ani
Sara
Joe

## Common Use Cases

String arrays find application in numerous scenarios across Java programming. Some common use cases include:

- **Storing and Processing Data:** String arrays are often used to store and process lists of strings, such as names, addresses, or any textual data.
- **Command-Line Arguments:** In Java applications, string arrays are employed to handle command-line arguments passed to the main() method.
- **Data Structures:** String arrays serve as building blocks for implementing more complex data structures like stacks, queues, and hash tables.