
In the C# programming language, the multidimensional array is also known as a rectangular array. It can be two-dimensional or three-dimensional. The data is stored in tabular form (row-column), which is also known as a matrix. It is a set of items where the elements are accessed using multiple indices.

![Multidimensional Arrays in C#](https://images.tpointtech.com/csharp/images/c-sharp-multidimensional-array.png)

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-multidimensional-array#)[](https://www.tpointtech.com/c-sharp-multidimensional-array#)[](https://www.tpointtech.com/c-sharp-multidimensional-array#)

1. data_type[,] array2D;  
2. data_type[,,] array3D;  

In this syntax,

- **data_type:** It represents the type of elements.

## C# Multidimensional Array Example

Let us take an illustrative example to define the multidimensional array in C#.

### Example

[](https://www.tpointtech.com/c-sharp-multidimensional-array#)[](https://www.tpointtech.com/c-sharp-multidimensional-array#)[](https://www.tpointtech.com/c-sharp-multidimensional-array#)

1. using System;  

2. class MultiDimensionalArrayExample  
3. {  
4.     static void Main()  
5.    {  
6.         // Initializing a 2D matrix  
7.         int[,] numbers = new int[2, 3]  
8.         {  
9.             { 1, 2, 3 },  
10.             { 4, 5, 6 }  
11.         };  

12.         // Print the array elements  
13.         Console.WriteLine("2D Array Elements:");  
14.         for (int i = 0; i < numbers.GetLength(0); i++) // rows  
15.         {  
16.             for (int j = 0; j < numbers.GetLength(1); j++) // columns  
17.             {  
18.                 Console.Write(numbers[i, j] + " ");  
19.             }  
20.             Console.WriteLine(); // New line after each row  
21.         }  
22.     }  
23. }   

**Output:**

2D Array Elements:
1 2 3
4 5 6

**Explanation:**

In this example, we demonstrate a multidimensional array in C#. First, we create the two-dimensional array, which has 2 rows and 3 columns. After that, we use the nested for loop to iterate over the values of the matrix. Finally, we use the Console.WriteLine() function to print the output.

### Size of Multidimensional Array in C#

In [C# programming](https://www.tpointtech.com/c-sharp-tutorial), the size of an [array](https://www.tpointtech.com/c-sharp-arrays) is calculated by the number of elements it contains. When it comes to the multidimensional array, the total size of an array is calculated by multiplying their number of rows and their number of columns. Similarly, if we want to calculate a three-dimensional array, the size of the array is the product of its elements (length x width x height).

**Size of Multidimensional Array Example**

Let us take an illustrative example to determine the size of an array in C#.

### Example

[](https://www.tpointtech.com/c-sharp-multidimensional-array#)[](https://www.tpointtech.com/c-sharp-multidimensional-array#)[](https://www.tpointtech.com/c-sharp-multidimensional-array#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {  
6.         // Creating a 2D array (3 rows, 2 columns)  
7.         int[,] arr = new int[ 3, 2 ];  

8.         // Calculating total number of bytes  
9.         int totalElements = arr.Length; // 3 * 2 = 6  
10.         int sizeOfElement = sizeof(int); // 4 bytes  
11.         int totalBytes = totalElements * sizeOfElement;  

12.         Console.WriteLine("Total no of bytes: " + totalBytes );  
13.     }  
14. }  

**Output:**

Total no of bytes: 24

**Explanation:**

In this example, we are using a two-dimensional array to determine the size of the 2D array. First, we define the 2D array, which has 3 rows and 2 columns. After that, we use the Length property to calculate the length of an array, and then we multiply the length of an array by the size of an array. Finally, we use the Console.WriteLine() function to print the output.

## 2D Array in C#

In the C# programming language, a two-dimensional is a rectangular array that are used to store data in rows and columns. It allows us to access the elements using two indices rows and columns.

### Created a 2D array in C#

If we want to create a 2D array, we can use the following syntax to create a 2D array in C#.

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-multidimensional-array#)[](https://www.tpointtech.com/c-sharp-multidimensional-array#)[](https://www.tpointtech.com/c-sharp-multidimensional-array#)

1. data_type [,] array_name = new data_type [row, column];   

In this syntax,

- **data_type:** It defines the type of elements that can be stored in a 2D array.
- **array_name:** It represents the name of an array.
- **row:** It represents the size of the row.
- **Column:** It represents the size of the column.

### 2D Array Declaration

The two-dimensional (2D) array is declared by specifying the [data type](https://www.tpointtech.com/cpp-data-types), and then the array name with two comma-separated indices in square brackets [].

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-multidimensional-array#)[](https://www.tpointtech.com/c-sharp-multidimensional-array#)[](https://www.tpointtech.com/c-sharp-multidimensional-array#)

1. int[,] my_array = new int[3, 4];    

In this syntax,

- **int:** It represents the type of value that can be stored in an array.
- **my_arr:** It declares the name of an array.

### Initializing a 2D Array

When a 2D array is declared, it can be initialized as well. It can be initialized in two typical ways.

- Initializing an array during declaration
- Assigning values after declaration

**a) Initializing a 2D Array during Declaration:**

In C#, we can initialize the 2D array at the time of declaration inside the curly braces. It is very useful if we already know the values that the array should hold.

**For Example:**

[](https://www.tpointtech.com/c-sharp-multidimensional-array#)[](https://www.tpointtech.com/c-sharp-multidimensional-array#)[](https://www.tpointtech.com/c-sharp-multidimensional-array#)

1. int [,] numbers = new int[,]  
2. {  
3.     { 10, 20, 30 },  
4.     { 40, 50, 60 },  
5.     { 70, 80, 90 }  
6. };  

**b) Assigning 2D values after declaration:**

In C#, we have to declare a 2D array by specifying row and column indices before assigning the values to the array.

**For Example:**

[](https://www.tpointtech.com/c-sharp-multidimensional-array#)[](https://www.tpointtech.com/c-sharp-multidimensional-array#)[](https://www.tpointtech.com/c-sharp-multidimensional-array#)

1. int[,] num_bers = new int[2, 3];   
2. num_bers[0, 0] = 10;  
3. num_bers[0, 1] = 20;  
4. num_bers[0, 2] = 30;  
5. num_bers[1, 0] = 40;  
6. num_bers[1, 1] = 50;  
7. num_bers[1, 2] = 60;  

### Traversing a 2D Array

In 2D array traversing, we can access all elements in the array and print all elements that are contained inside the array.

**Traversing a 2D Array Example in C#**

Let us take an illustrative example of an array to show how to access and display the elements of an array.

### Example

[](https://www.tpointtech.com/c-sharp-multidimensional-array#)[](https://www.tpointtech.com/c-sharp-multidimensional-array#)[](https://www.tpointtech.com/c-sharp-multidimensional-array#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {  
6.         int[,] arr = { { 1, 2, 3 }, { 4, 5, 6 } };  
7.         // Traversing and printing the array element  
8.         for ( int i = 0; i < 2; i++ )  
9.         {  
10.             for ( int j = 0; j < 3; j++ )  
11.             {  
12.                 Console.Write(arr[i, j] + " ");  
13.             }  
14.             Console.WriteLine();  
15.         }  
16.     }  
17. }    

**Output:**

1 2 3
4 5 6

**Explanation:**

In this example, first we declare the 2D array named arr and then initializing the values in it. After that, we use the nested for loop to iterate over the rows and columns elements. Here, i represents the rows and j represents the columns of the [loop](https://www.tpointtech.com/cpp-for-loop). Finally, we use the Console.WriteLine() function to print the output.

### Updating a 2D Array

If we want to update a specific element in a two-dimensional array in C#, we can use its row and column index. It allows us to access directly the desired position in the array and assign it a new value.

**Updating a 2D Array Example in C#**

Let us take an illustrative example to update the 2D array in C#.

### Example

[](https://www.tpointtech.com/c-sharp-multidimensional-array#)[](https://www.tpointtech.com/c-sharp-multidimensional-array#)[](https://www.tpointtech.com/c-sharp-multidimensional-array#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {  
6.         int[,] arr = { { 1, 2, 3 }, { 4, 5, 6 } };  
7.         // Updating element at row 1, column 2 (i.e., 2nd row, 3rd column)  
8.         arr[1, 2] = 9;  
9.         // Print the array to confirm the update  
10.         for (int m = 0; m < 2; m++)  
11.         {  
12.             for (int n = 0; n < 3; n++)  
13.             {  
14.                 Console.Write(arr[m, n] + " ");  
15.             }  
16.             Console.WriteLine();  
17.         }  
18.     }  
19. }    

**Output:**

1 2 3
4 5 9

**Explanation:**

In this example, we demonstrate how to update an element a 2D array. First, we declare and initialize the 2D array named arr with two rows and three columns, and then we update the element at row 1, column 2 by assigning it the value 9.

After that, we use a nested for loop to traverse the array. Finally, we use the Console.WriteLine() function to print the output.

## 3D Array in C#

A three-dimensional (3D) array is an advanced representation of a Multidimensional array that holds multiple 2D arrays. It works same as collection of multiple layers or tables. It is declared by using the three indices such as row, column, and depth.

### Create a 3D Array in C#

The declaration of a 3D array depends on three indices.

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-multidimensional-array#)[](https://www.tpointtech.com/c-sharp-multidimensional-array#)[](https://www.tpointtech.com/c-sharp-multidimensional-array#)

1. data_type[,,] array_name = new data_type[depth, rows, columns];   

In this example,

- **data_type:** It defines the type of elements that can be stored in a 3D array.
- **array_name:** It represents the name of an array.
- **row:** It represents the number of rows.
- **Column:** It represents the number of columns.
- **Depth:** It represents the number of layers.

**For Example:**

[](https://www.tpointtech.com/c-sharp-multidimensional-array#)[](https://www.tpointtech.com/c-sharp-multidimensional-array#)[](https://www.tpointtech.com/c-sharp-multidimensional-array#)

1. int[,,] cube = new int[2, 3, 3];   

### Initialize 3D Array

There are several ways to initialize the 3D array in C#. These are as follows:

**a) Initializing a 3D Array during Declaration**

In C#, we can initialize the 3D array at the time of declaration using the nested curly braces.

**For Example:**

[](https://www.tpointtech.com/c-sharp-multidimensional-array#)[](https://www.tpointtech.com/c-sharp-multidimensional-array#)[](https://www.tpointtech.com/c-sharp-multidimensional-array#)

1. int[, ,] array3D = {  
2.     {  
3.         {1, 2},  
4.         {3, 4}  
5.     },  
6.     {  
7.         {5, 6},  
8.         {7, 8}  
9.     }  
10. };  

**b) Assigning 3D values after declaration:**

In C#, we can declare a 3D array with three dimensions, and values can be assigned after declaration using index notation.

**For Example:**

[](https://www.tpointtech.com/c-sharp-multidimensional-array#)[](https://www.tpointtech.com/c-sharp-multidimensional-array#)[](https://www.tpointtech.com/c-sharp-multidimensional-array#)

1. int[, ,] array3D = new int[ 2, 2, 2 ];  
2. // Assigning values  
3. array3D[0, 0, 0] = 1;  
4. array3D[0, 0, 1] = 2;  
5. array3D[0, 1, 0] = 3;  
6. array3D[0, 1, 1] = 4;  
7. array3D[1, 0, 0] = 5;  
8. array3D[1, 0, 1] = 6;  
9. array3D[1, 1, 0] = 7;  
10. array3D[1, 1, 1] = 8;  

### Traverse a 3D Array

In 3D array traversing, we can access all elements in the array using the three nested loops, and one for every dimension.

**Traversing a 3D Array Example in C#**

Let us take an example to illustrate how to traverse a 3D array in C#.

### Example

[](https://www.tpointtech.com/c-sharp-multidimensional-array#)[](https://www.tpointtech.com/c-sharp-multidimensional-array#)[](https://www.tpointtech.com/c-sharp-multidimensional-array#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {  
6.         int[,,] arr = new int[ 2, 2, 3 ] {  
7.             { {1, 2, 3}, {4, 5, 6} },  
8.             { {7, 8, 9}, {10, 11, 12} }  
9.         };  
10.         // Traversing and printing the 3D array  
11.         for ( int i = 0; i < 2; i++ )  // Layers  
12.         {  
13.             for ( int j = 0; j < 2; j++ )  // Rows  
14.             {  
15.                 for ( int k = 0; k < 3; k++ )  // Columns  
16.                 {  
17.                     Console.Write(arr[i, j, k] + " ");  
18.                 }  
19.                 Console.WriteLine();  // New row  
20.             }  
21.             Console.WriteLine();  // Space between layers  
22.         }  
23.     }  
24. }   

**Output:**

1 2 3
4 5 6

7 8 9
10 11 12

**Explanation**

In this example, we demonstrate how to traverse a 3D array in C#. First, we create a 3D array named arr and then initialize it with values using nested curly braces. After that, we use a nested for loop to traverse and print each element. The outer loop iterates over layers, the middle loop over rows, and the inner loop over columns of the 3-D array.

### Update a 3D Array in C#

In the C# programming language, we can update or change the value of a specific element in a 3-dimensional array. It requires the three indices and needs three loops that handle layers after rows, followed by columns.

**Updating a 3D Array Example**

Let us take an example to illustrate how to update the 3D array in C#.

### Example

[](https://www.tpointtech.com/c-sharp-multidimensional-array#)[](https://www.tpointtech.com/c-sharp-multidimensional-array#)[](https://www.tpointtech.com/c-sharp-multidimensional-array#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {  
6.         // Declare and initialize a 3D array  
7.         int[, ,] array3D = {  
8.             {  
9.                 {1, 2},  
10.                 {3, 4}  
11.             },  
12.             {  
13.                 {5, 6},  
14.                 {7, 8}  
15.             }  
16.         };  
17.         // Update some values  
18.         array3D[ 0, 0, 1 ] = 20;  
19.         array3D[ 1, 1, 0 ] = 70;  
20.         // Print updated array  
21.         for ( int i = 0; i < 2; i++ )      // layers   
22.         {  
23.             for ( int j = 0; j < 2; j++ )  // rows  
24.             {  
25.                 for ( int k = 0; k < 2; k++ )  // columns  
26.                 {  
27.                     Console.Write( array3D[ i, j, k ] + " " );  
28.                 }  
29.                 Console.WriteLine();  
30.             }  
31.             Console.WriteLine();  
32.         }  
33.     }  
34. }   

**Output:**

1 20
3 4

5 6
70 8

**Explanation:**

In this instance, we declare and initialize the 3D array named array3D with two layers, each contains a 2x2 matrix. After that, we use a nested for loop to iterate and each iteration (layer, row, column) to print the new updated values. The outer loop (i) handles the layer, the middle loop (j) handles rows, and the inner loop (k) handles columns.

### Passing a Multidimensional Array in C#

In the C# programming language, we can pass a multidimensional array (2D or 3D) to methods by declaring the methods. It allows the method to access, modify, or traverse the elements of the array.

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-multidimensional-array#)[](https://www.tpointtech.com/c-sharp-multidimensional-array#)[](https://www.tpointtech.com/c-sharp-multidimensional-array#)

1. void DisplayMatrix(int[,] array, int rowCount)      

In this example, the number of columns must be specified, while the number of rows can be omitted.

**Passing a 2D Array Example in C#**

Let us take an instance to illustrate how to pass a 2D array in C#.

### Example

[](https://www.tpointtech.com/c-sharp-multidimensional-array#)[](https://www.tpointtech.com/c-sharp-multidimensional-array#)[](https://www.tpointtech.com/c-sharp-multidimensional-array#)

1. using System;  
2. class Program  
3. {  
4.     // Method to display a 2D array  
5.     static void DisplayMatrix(int[,] data, int rowCount)  
6.     {  
7.         for (int i = 0; i < rowCount; i++)  
8.         {  
9.             for (int j = 0; j < data.GetLength(1); j++)  
10.             {  
11.                 Console.Write(data[i, j] + " ");  
12.             }  
13.             Console.WriteLine();  
14.         }  
15.     }  
16.     static void Main()  
17.     {  
18.         int[,] numbers = {  
19.             {1, 2, 3},  
20.             {4, 5, 6}  
21.         };  
22.         Console.WriteLine("2D Array Elements: ");  
23.         DisplayMatrix(numbers, 2);  // Passing the 2D array  
24.     }  
25. }    

**Output:**

2D Array Elements:
1 2 3
4 5 6

**Explanation:**

In this example, we demonstrate how to pass a 2D array in C#. First, we create a 2D array and then initialized it with two rows and three columns. After that, we use a nested for loop to iterate over each element. Finally, we use the Console.WriteLine() function to print the output.

## Conclusion

In conclusion, C# multidimensional array provides a powerful way to organize and manage data in rows, columns, and layers. They are mainly useful in several cases, including matrix operations, image processing, and 3D modeling where data is naturally structured in multiple dimensions. The multidimensional array allows us to access the elements using multiple indices, which provides a clean and efficient way to store related values in a grid-like format.