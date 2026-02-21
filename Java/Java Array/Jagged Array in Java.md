In Java, a **jagged array** is a type of multidimensional array in which each row can have a different number of columns. In this chapter, we will learn what a jagged array is, how it is declared and initialized, and how to work with jagged arrays using simple examples.

## What is Jagged Array in Java?

A **jagged array** is a collection of arrays where each array may contain a varying number of elements. A [two-dimensional array](https://www.tpointtech.com/multidimensional-arrays-in-java), in contrast, requires all rows and columns to have the same length.

**Jagged arrays** are also known as "**ragged arrays**" or "**irregular arrays**". They can be created by specifying the size of each array in the declaration.

For example, a jagged array with three rows can have the first row with three elements, the second with two elements, and the third with four elements.

## Jagged Array Declaration

A jagged array is declared by first specifying the number of rows and then allocating each row separately with different column sizes.

### Syntax

Here is the syntax of declaring a jagged array:

[](https://www.tpointtech.com/jagged-array-in-java#)[](https://www.tpointtech.com/jagged-array-in-java#)[](https://www.tpointtech.com/jagged-array-in-java#)

1. datatype[][] arrayName = new datatype[numRows][];  
2. arrayName[0] = new datatype[numColumns1];  
3. arrayName[1] = new datatype[numColumns2];  
4. ...  
5. arrayName[numRows-1] = new datatype[numColumnsN];  

Here, the **datatype** is the data type of the elements in the array, **numRows** is the number of rows in the jagged array, and **numColumns1, numColumns2, ..., numColumnsN** are the number of columns in each row. Users should be aware that the number of columns in each row is flexible.

The first line creates an array of arrays with **numRows** rows. Each row is initialized to **null** by default.

The subsequent lines initialize each row of the jagged array. You create a new one-dimensional array of **numColumns** elements for each row and assign it to the corresponding row in the jagged array.

## Ways to Initialize a Jagged Array

Apart from the standard approach of declaring and initializing a jagged array, there are several different ways to initialize a jagged array in Java.

### 1. Using Array Literals

We can use array literals to initialize the jagged array elements like this directly:

[](https://www.tpointtech.com/jagged-array-in-java#)[](https://www.tpointtech.com/jagged-array-in-java#)[](https://www.tpointtech.com/jagged-array-in-java#)

1. int[][] jaggedArray = { {1, 2}, {3, 4, 5}, {6, 7, 8, 9} };  

Here, we create a jagged array with three rows, where the first row has two elements, the second row has three elements, and the third row has four elements.

### Example

[](https://www.tpointtech.com/jagged-array-in-java#)[](https://www.tpointtech.com/jagged-array-in-java#)[](https://www.tpointtech.com/jagged-array-in-java#)

1. public class Main {    
2.     public static void main(String[] args) {    
3.         // create a jagged array with three rows    
4.         int[][] jaggedArray = {    
5.             {1, 2, 3},   // first row has three columns    
6.             {4, 5},      // second row has two columns    
7.             {6, 7, 8, 9}   };  // third row has four columns    
8.         // loop through each row of the jagged array    
9.         for (int i = 0; i < jaggedArray.length; i++) {    
10.             // loop through each column of the current row    
11.             for (int j = 0; j < jaggedArray[i].length; j++) {    
12.                 // print the value at the current position in the array    
13.                 System.out.print(jaggedArray[i][j] + " ");    
14.             }    
15.             // move to the next line for the next row    
16.             System.out.println();    
17.         }    
18.     }    
19. }    

**Output:**

1 2 3
4 5
6 7 8 9

### 2. Using Nested Loops

We can also use nested loops to initialize the jagged array elements when the elements are to be programmatically generated. Utilizing such an approach can be beneficial.

[](https://www.tpointtech.com/jagged-array-in-java#)[](https://www.tpointtech.com/jagged-array-in-java#)[](https://www.tpointtech.com/jagged-array-in-java#)

1. int[][] jaggedArray = new int[3][];  
2. for (int i = 0; i < jaggedArray.length; i++) {  
3.     jaggedArray[i] = new int[i + 1];  
4.     for (int j = 0; j < jaggedArray[i].length; j++) {  
5.         jaggedArray[i][j] = i + j;  
6.     }  
7. }  

Here, we design a jagged array with three rows, the first of which contains one element, the second two, and the third three. Using a simple formula, the nested loops generate the elements in the jagged array.

### Example

[](https://www.tpointtech.com/jagged-array-in-java#)[](https://www.tpointtech.com/jagged-array-in-java#)[](https://www.tpointtech.com/jagged-array-in-java#)

1. public class Main {    
2.     public static void main(String[] args) {    
3.         // Create a 2-D jagged array with 4 rows    
4.         int[][] jaggedArray = new int[4][];    
5.         // Set the number of columns for each row    
6.         jaggedArray[0] = new int[1];    
7.         jaggedArray[1] = new int[2];    
8.         jaggedArray[2] = new int[3];    
9.         jaggedArray[3] = new int[4];    
10.         // Fill the array with values starting from 1    
11.         int value = 1;    
12.         for (int i = 0; i < jaggedArray.length; i++) {    
13.             for (int j = 0; j < jaggedArray[i].length; j++) {    
14.                 jaggedArray[i][j] = value;    
15.                 value++;    
16.             }    
17.         }    
18.         // Print the values in the array    
19.         for (int i = 0; i < jaggedArray.length; i++) {    
20.             for (int j = 0; j < jaggedArray[i].length; j++) {    
21.                 System.out.print(jaggedArray[i][j] + " ");    
22.             }    
23.             System.out.println();    
24.         }    
25.     }    
26. }    

**Output:**

1
2 3
4 5 6
7 8 9 10

## Jagged Array Using Java 8 Streams

With Java 8 streams, you can create and initialize a jagged array in a single line using the Arrays.stream and toArray methods like this:

[](https://www.tpointtech.com/jagged-array-in-java#)[](https://www.tpointtech.com/jagged-array-in-java#)[](https://www.tpointtech.com/jagged-array-in-java#)

1. int[][] jaggedArray = Stream.of(  
2.         new int[]{1, 2},  
3.         new int[]{3, 4, 5},  
4.         new int[]{6, 7, 8, 9})  
5.         .toArray(int[][]::new);  

Here, we make a three-row jagged array with two elements in the first row, three in the second row, and four in the third row. The **Arrays.stream** method converts each one-dimensional array into a stream of integers, and then the **toArray** method collects the stream into a jagged array.

### Example

The following example demonstrates how to create jagged array using Java 8 streams.

[](https://www.tpointtech.com/jagged-array-in-java#)[](https://www.tpointtech.com/jagged-array-in-java#)[](https://www.tpointtech.com/jagged-array-in-java#)

1. import java.util.*;    
2. public class Main {    
3.     public static void main(String[] args) {           
4.         // create a jagged array with three rows    
5.         int[][] jaggedArray = {    
6.             {1, 2, 3},   // first row has three columns    
7.             {4, 5},      // second row has two columns    
8.             {6, 7, 8, 9} // third row has four columns    
9.         };    
10.         // loop through each row of the jagged array using streams    
11.         Arrays.stream(jaggedArray)    
12.             .forEach(row -> {    
13.                 // loop through each element of the current row using streams    
14.                 Arrays.stream(row)    
15.                     .forEach(element -> System.out.print(element + " "));    
16.                 // move to the next line for the next row    
17.                 System.out.println();    
18.             });    
19.     }    
20. }    

**Output:**

1 2 3
4 5
6 7 8 9

## Dynamic Jagged Array

In Java, we can create a dynamic jagged array by creating an array of arrays, where each sub-array represents a row in the two-dimensional array. After thar, we can allocate memory to each sub-array to specify its number of columns.

### Example

The following example shows the working of dynamic jagged array in Java.

[](https://www.tpointtech.com/jagged-array-in-java#)[](https://www.tpointtech.com/jagged-array-in-java#)[](https://www.tpointtech.com/jagged-array-in-java#)

1. import java.util.Scanner;    
2. public class Main {    
3. public static void main(String[] args) {    
4. // Create a Scanner object to get user input    
5. Scanner scanner = new Scanner(System.in);    
6.     // Prompt the user to enter the number of sub-arrays    
7.     System.out.print("Enter the number of sub-arrays: ");    
8.     int numberOfArrays = scanner.nextInt();    
9.     // Declare the jagged array with the number of sub-arrays    
10.     int[][] jaggedArray = new int[numberOfArrays][];    
11.     //Loop through each sub-array to allocate memory and get user input for each element    
12.     for (int i = 0; i < numberOfArrays; i++) {    
13.         // Prompt the user to enter the size of the current sub-array    
14.         System.out.print("Enter the size of sub-array " + (i + 1) + ": ");    
15.         int sizeOfSubArray = scanner.nextInt();    
16.         // Allocate memory to the current sub-array    
17.         jaggedArray[i] = new int[sizeOfSubArray];    
18.         //Loop through each element of the current sub-array to get user input    
19.         for (int j = 0; j < sizeOfSubArray; j++) {    
20.             System.out.print("Enter the element at index " + j + " of sub-array " + (i + 1) + ": ");    
21.             jaggedArray[i][j] = scanner.nextInt();    
22.         }    
23.     }    
24.     // Print the jagged array    
25.     System.out.println("The jagged array is:");    
26.     for (int i = 0; i < numberOfArrays; i++) {    
27.         for (int j = 0; j < jaggedArray[i].length; j++) {    
28.             System.out.print(jaggedArray[i][j] + " ");    
29.         }    
30.         System.out.println();    
31.     }    
32.     // Close the scanner object    
33.     scanner.close();    
34. }    
35. }    

**Output:**

Enter the number of sub-arrays: 3
Enter the size of sub-array 1: 2
Enter the element at index 0 of sub-array 1: 1
Enter the element at index 1 of sub-array 1: 2
Enter the size of sub-array 2: 3
Enter the element at index 0 of sub-array 2: 3
Enter the element at index 1 of sub-array 2: 4
Enter the element at index 2 of sub-array 2: 5
Enter the size of sub-array 3: 1
Enter the element at index 0 of sub-array 3: 6
The jagged array is:
1 2
3 4 5
6

## Jagged Arrays Vs Multi-Dimensional Arrays

A jagged array is not the same as a multi-dimensional array. There are some differences between Jagged array and multi-dimensional array that are described in the following table.

|Aspect|Jagged Array|Multi-dimensional Array|
|---|---|---|
|**Structure**|Each row (or sub-array) can have a different length.|All rows must have the same number of columns.|
|**Memory Allocation**|Memory is allocated separately for each sub-array, making it more memory-efficient when varying row sizes are needed.|It allocates a continuous block of memory for all elements, potentially wasting memory when row lengths vary.|
|**Declaration**|int[][] jaggedArray = {  <br>    {1, 2, 3},  <br>    {4, 5},  <br>    {6, 7, 8, 9}  <br>};|int[][] multiArray = new int[3][3]; // Fixed size: 3 rows, 3 columns|
|**Accessing Elements**|Jagged Array: jaggedArray[row][column]|Multi-dimensional Array: multiArray[row][column]|
|**Uses Cases**|It is useful when dealing with irregular data structures like variable-length rows in tables.|It is ideal for grids, matrices, or fixed-size tables.|