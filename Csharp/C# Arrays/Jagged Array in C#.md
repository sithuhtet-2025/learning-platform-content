

In C#, the jagged array is also known as an "array of arrays", where each element in the main array is itself an array. The length of each element inside the jagged array can be different. Jagged arrays store the arrays instead of literal values. Unlike multidimensional arrays, jagged arrays enable the inner array to be of differing lengths, which gives more flexibility in storing elements. It makes them more efficient when working with uneven data structures.

### Simple Example:

Let us take a simple example of a jagged array in [C#](https://www.tpointtech.com/c-sharp-tutorial), which declares, initializes, and traverses jagged arrays.

### Example

[](https://www.tpointtech.com/c-sharp-jagged-array#)[](https://www.tpointtech.com/c-sharp-jagged-array#)[](https://www.tpointtech.com/c-sharp-jagged-array#)

1. using System;  
2. public class JaggedArrayTest    
3. {    
4.     public static void Main()    
5.     {    
6.         int[][] arr = new int[2][];// Declare the array    

7.         arr[0] = new int[] { 15, 25, 38, 45 };// Initialize the array            
8.        arr[1] = new int[] { 75, 28, 19, 41, 35, 39 };    

9.         // Traverse array elements    
10.         for (int i = 0; i < arr.Length; i++)    
11.         {    
12.             for (int j = 0; j < arr[i].Length; j++)    
13.             {    
14.                 System.Console.Write(arr[i][j]+" ");    
15.             }    
16.             System.Console.WriteLine();    
17.         }    
18.     }    
19. }  

**Output:**

15 25 38 45
75 28 19 41 35 39

Here, we will discuss the declaration, initialization, and accessing elements of jagged arrays in C#.

### Declaration of Jagged Array:

In a [C#](https://www.tpointtech.com/c-sharp-tutorial) jagged array, we only need to specify the number of rows, not column numbers. If we define the number of columns in the jagged array, the array loses its jagged feature and becomes a multidimensional array. It is declared with two square brackets [][], which indicates that it is an array of arrays.

Here, the first square bracket [] refers to the size of the main array. On the other side, the second bracket [] does not specify the array dimensions, but instead, it indicates that each element in the main array is another array, which can have different lengths.

**Syntax:**

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-jagged-array#)[](https://www.tpointtech.com/c-sharp-jagged-array#)[](https://www.tpointtech.com/c-sharp-jagged-array#)

1. Data-type[][] name_of_array = new data-type[rows][];  

Let us illustrate the declaration of the jagged array with an example:

[](https://www.tpointtech.com/c-sharp-jagged-array#)[](https://www.tpointtech.com/c-sharp-jagged-array#)[](https://www.tpointtech.com/c-sharp-jagged-array#)

1. //declare the jagged array  
2. int[][] arr = new int[2][];    
3. In this example,  

- **int:** It defines the data type of the array.
- **[][]:** Square brackets represent the jagged array.
- **arr:** It represents the name of the jagged array.
- **[2][]:** It defines the number of arrays inside the jagged array.

### Initialization of Jagged Array:

We can individually assign the size of elements because every member of a jagged array is itself an array. Let us take an example to initialize a jagged array in C#.

[](https://www.tpointtech.com/c-sharp-jagged-array#)[](https://www.tpointtech.com/c-sharp-jagged-array#)[](https://www.tpointtech.com/c-sharp-jagged-array#)

1. //set the size of the first array as 4  
2. arr[0] = new int[4];    
3. //set the size of the first array as 4  
4. arr[1] = new int[6];    

## Initialization and filling elements in the jagged array

In C#, there are several methods to initialize the array in the jagged array. Some of them are as follows:

### 1. Using the Index Number:

Once the jagged array is initialized in C#, we may utilize the index number to initialize it. It enables us to dynamically initialize values for each element in the array by accessing its specific index position.

**Example:**

Let us consider an example to illustrate how we can initialize the jagged array using the Index number in C#.

### Example

[](https://www.tpointtech.com/c-sharp-jagged-array#)[](https://www.tpointtech.com/c-sharp-jagged-array#)[](https://www.tpointtech.com/c-sharp-jagged-array#)

1. // Declare a jagged array with 2 rows  
2. int[][] jagged_array = new int[2][];  

3. // Initialize each row with a specific size  
4. jagged_array[0] = new int[3]; // Initialize first row with 3 elements  
5. jagged_array[1] = new int[2]; // Initialize second row with 2 elements  

6. // Initialize the first array  
7. jagged_array[0][0] = 4;  
8. jagged_array[0][1] = 3;  
9. jagged_array[0][2] = 7;  

10. // Initialize the second array  
11. jagged_array[1][0] = 2;  
12. jagged_array[1][1] = 5;  

Where,

- The index at the first bracket [] specifies the index of the row in the jagged array.
- The index at the second bracket [] specifies the index of the element inside that specific row of the jagged array.

### 2. Initialize without defining the size of array elements:

When the jagged array's size is not predetermined, we may directly initialize its elements using the inline initialization with specific values.

**Example:**

Let us consider an example to illustrate how we can initialize the jagged array without using the size of the array in C#.

### Example

[](https://www.tpointtech.com/c-sharp-jagged-array#)[](https://www.tpointtech.com/c-sharp-jagged-array#)[](https://www.tpointtech.com/c-sharp-jagged-array#)

1. // declaring an integer jagged array  
2. int[][] arr = new int[2][];  

3. // initializing each row with values  
4. arr[0] = new int[4] { 11, 21, 56, 78  }; // First row  
5. arr[1] = new int[6] { 42, 61, 37, 41, 59, 63 };     // Second row  

### 3. Initialize while declaring Jagged Array:

In C# programming, we may directly utilize array initializers to initialize a jagged array at the time of declaration. It allows us to declare and populate the array in a single step, which makes the code more concise and expressive.

**Example:**

Let us consider an example to illustrate how to initialize the array while declaring a jagged array in C#.

### Example

[](https://www.tpointtech.com/c-sharp-jagged-array#)[](https://www.tpointtech.com/c-sharp-jagged-array#)[](https://www.tpointtech.com/c-sharp-jagged-array#)

1. int[][] jagged_array = {  
2.     new int[] {17, 24, 31, 42 }  // First row (4 elements)  
3.     new int[] {18, 27, 16};  // Second row (3 elements)  
4.     new int[] {22, 15};  // Third row (2 elements)  
5. };  

**Example 1:** A program to implement the jagged array in C#.

### Example

[](https://www.tpointtech.com/c-sharp-jagged-array#)[](https://www.tpointtech.com/c-sharp-jagged-array#)[](https://www.tpointtech.com/c-sharp-jagged-array#)

1. using System; // Importing the System namespace  

2. public class Tpointtech   
3. {  
4.     public static void Main()  
5.     {  
6.         int[][] jaggedArr = new int[4][]; // Array Declaration    
7.           // Array Initialization  
8.         jaggedArr[0] = new int[] { 4, 2, 5, 9 }; // First row with 4 elements  
9.         jaggedArr[1] = new int[] { 8, 1, 7 }; // second row with 3 elements  
10.         jaggedArr[2] = new int[] { 6, 3, 2, 5 }; // third row with 4 elements  
11.         jaggedArr[3] = new int[] { 9, 4, 8, 1, 6 }; // fourth row with 5 elements  

12.           // Iterating the elements  
13.         for (int i = 0; i < jaggedArr.Length; i++)   
14.         {  
15.             Console.Write("Row " + i + ": "); // Printing row index  
16.              foreach (int num in jaggedArr[i])   
17.                 Console.Write(num + " "); // Printing elements of the row  

18.             Console.WriteLine(); // Moving to the next line after printing a row  
19.         }  
20.     }  
21. }  

**Output:**

Row 0: 4 2 5 9
Row 1: 8 1 7
Row 2: 6 3 2 5
Row 3: 9 4 8 1 6

**Explanation:**

In this example, we have taken a public class named Tpointtech. After that, a jaggedArr function is declared as a jagged array with 4 elements, and each can hold an array of integers. At this point, the inner arrays are not initialized. Every element of the given jagged array is initialized as an array of integers.

After that, the outer loop iterates over each row of the jagged array. The inner foreach loop iterates over every element in the current row, which prints the element that is separated by spaces. At the end, the console.WriteLine() function moves the cursor to the next line after printing all the elements of the current row, which ensures that each row is displayed on a separate line.

**Example 2: Jagged Array upon declaration**

Let us take a simple example of the jagged array, which initializes the jagged arrays upon declaration in C#.

### Example

[](https://www.tpointtech.com/c-sharp-jagged-array#)[](https://www.tpointtech.com/c-sharp-jagged-array#)[](https://www.tpointtech.com/c-sharp-jagged-array#)

1. using System;  
2. public class JaggedArrayTest    
3. {    
4.     public static void Main()    
5.     {    
6.         // Declare and initialize a jagged array with 4 rows  
7.         int[][] arr = new int[4][]{    
8.         new int[] { 25, 45, 41, 78, 34 },    
9.         new int[] { 4, 52, 36, 15, 27, 73 },    
10.         new int[] { 2, 5, 28, 31, 47  },  
11.         new int[] { 13, 53, 72  }  
12.         };   

13.         // Iterate through each row of the jagged array    
14.         for (int i = 0; i < arr.Length; i++)    
15.         {    
16.             // Iterate through each element in the current row  
17.             for (int j = 0; j < arr[i].Length; j++)    
18.             {    
19.                 // Print the current element followed by a space  
20.                 System.Console.Write(arr[i][j]+" ");    
21.             }    
22.             System.Console.WriteLine();    
23.         }    
24.     }    
25. }   

**Output:**

25 45 41 78 34
4 52 36 15 27 73
2 5 28 31 47
13 53 72

**Explanation:**

In this example, we have taken a JaggedArrayTest class. After that, we declare a jagged array with 4 elements upon declaration, and each of them can handle an array of integers. After that, the outer loop iterates over each row of the jagged array.

The inner foreach loop iterates over every element in the current row, which prints the element that is separated by spaces. At the end, the console.WriteLine() function moves the cursor to the next line after printing all the elements of the current row, which ensures that each row is displayed on a separate line.

### Accessing and Modifying the Elements of a Jagged Array:

In C#, we can access the jagged array elements using the two indices. The first indices refer to the outer array (row), and the second indices refer to the inner array(column).

[](https://www.tpointtech.com/c-sharp-jagged-array#)[](https://www.tpointtech.com/c-sharp-jagged-array#)[](https://www.tpointtech.com/c-sharp-jagged-array#)

1. //Accessing the first elements of a jagged array of a second row  
2. int element = jaggedArray[1][0];   

On the other hand, we can modify the element of a jagged array by allocating a new value using their indices.

[](https://www.tpointtech.com/c-sharp-jagged-array#)[](https://www.tpointtech.com/c-sharp-jagged-array#)[](https://www.tpointtech.com/c-sharp-jagged-array#)

1. // Modify the second element of the first row to 15  
2. jaggedArr[0][1] = 15;   

**Example:**

Let us take an example to illustrate how to access and modify the elements in C#.

### Example

[](https://www.tpointtech.com/c-sharp-jagged-array#)[](https://www.tpointtech.com/c-sharp-jagged-array#)[](https://www.tpointtech.com/c-sharp-jagged-array#)

1. using System;  
2. public class Tpointtech    
3. {  
4.     static void Main(string[] args)  
5.     {  
6.         // Here is the declaration of a jagged array with 3 rows  
7.         int[][] arr = new int[3][];  

8.         // Here is the initialization of each row of the jagged array     
9.         arr[0] = new int[] { 5, 7, 8, 4}; // First row  
10.         arr[1] = new int[] { 3, 9, 12 };  // Second row  
11.         arr[2] = new int[] { 17, 19, 45, 16 };  // Third row  

12.         // Accessing the third element in the second row  
13.         int value = arr[1][2];    
14.         // Here, we are modifying the third element in  
15.           // the second row (from 12 to 15)  
16.         arr[1][2] = 15;       
17.                 Console.WriteLine("Accessed Value: " + value); // Print the accessed value   
18.         Console.WriteLine("Modified Value: " + arr[1][2]);  // Print the modified value   
19.     }  
20. }  

**Output:**

Accessed Value: 12
Modified Value: 15

**Explanation:**

In this example, we have taken a class named Tpointtech. Here, we declare a jagged array named arr that contain 3 rows. Every element of an arr function is an array that can have a different length. Every row of the jagged array is initialized with a specific value.

After that, we access the third element in the second row that contains the value 12, and then we update the previously accessed element from 12 to 15. At the end, it prints the output in the console.

### Jagged Arrays with Multidimensional Arrays

In C#, we can also utilize the jagged arrays in multi-dimensional arrays to create complex data structures. In order to iterate a jagged array, we may utilize the nested loops. The outer loop iterates via the rows, and the inner loop iterates via the elements in every row.

**Syntax:**

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-jagged-array#)[](https://www.tpointtech.com/c-sharp-jagged-array#)[](https://www.tpointtech.com/c-sharp-jagged-array#)

1. //initializing 4 2-Dimensional array elements in 1-Dimensional array  
2. int[][, ] jagged_array = new int[4][, ]   
3. {  
4.     new int[, ] { {3, 4}, {2, 7}, {5, 8} },  
5.     new int[, ] { {18, 12}, {19, 22}, {35, 55} },  
6.     new int[, ] { {23, 54}, {26, 84}, {67, 37}, {49, 73} },  
7.     new int[, ] { {81, 32}, {5, 7}, {45, 94} },  
8. };  

**Example:**

Let us take an example to demonstrate the iteration of the jagged array in a multidimensional array in C#.

### Example

[](https://www.tpointtech.com/c-sharp-jagged-array#)[](https://www.tpointtech.com/c-sharp-jagged-array#)[](https://www.tpointtech.com/c-sharp-jagged-array#)

1. using System;  
2. public class MultiJaggedArray  
3. {  
4.     public static void Main()  
5.     {  
6.         // Declare and initialize a jagged array where each element is a two-dimensional array  
7.         int[][,] jag_array = new int[4][,]  
8.         {  
9.             // First 2D array with 3 rows and 2 columns  
10.             new int[,] { {3, 4}, {2, 7}, {5, 8} },  
11.             // Second 2D array   
12.             new int[,] { {18, 12}, {19, 22}, {35, 55} },  
13.             // Third 2D array with 4 rows and 2 columns  
14.             new int[,] { {23, 54}, {26, 84}, {67, 37}, {49, 73} },  
15.             // Fourth 2D array  
16.             new int[,] { {81, 32}, {5, 7}, {45, 94} },  
17.         };  

18.         // Iterate through each 2D array in the jagged array  
19.         for (int i = 0; i < jag_array.Length; i++)  
20.         {  
21.             Console.WriteLine($"Elements of the Jagged Array {i+1}:");  
22.             // GetLength method takes an integer that indicates the array's dimension.  
23.             for (int j = 0; j < jag_array[i].GetLength(0); j++)  
24.             {  
25.                 for (int k = 0; k < jag_array[i].GetLength(1); k++)  
26.                 {  
27.             // Print the element at position [j, k] in the current 2D array  
28.                     Console.Write("{0} ",jag_array[i][j, k]);  
29.                 }  
30.                 Console.WriteLine();  
31.             }  
32.             Console.WriteLine();  
33.         }    
34.     }    
35. }    

**Output:**

Elements of the Jagged Array 1:
3 4
2 7
5 8
Elements of the Jagged Array 2:
18 12
19 22
35 55
Elements of the Jagged Array 3:
23 54
26 84
67 37
49 73
Elements of the Jagged Array 4:
81 32
5 7
45 94

**Explanation:**

In this example, we have taken a MultiJaggedArray class. After that, we declare a jagged array that contains 4 elements and each element is a two-dimensional array. Every element of the jagged array is initialized with a two-dimensional array that has different sizes.

For every 2D array, it retrieves the number of rows and columns using GetLength(0) and GetLength(1). After that, it iterates via each row and column to access and print the element.