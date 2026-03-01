Multi-dimensional arrays in Java are used to store data in the form of rows and columns. In this chapter, we will learn what multi-dimensional arrays are and how to declare, create, and use them in Java programs.

## What are Multi-Dimensional Arrays in Java?

Multi-dimensional arrays are arrays of arrays, where each element of the main array holds another array. They are commonly used to represent data in table or matrix form, such as grids, charts, or spreadsheets.

A multi-dimensional array can be compared to a table. For example, storing marks of students where each row represents a student and each column represents a subject. This way, data is organized in rows and columns using a multi-dimensional array.

## Two-Dimensional (2D) Array

A two-dimensional (2D) array is a type of multi-dimensional array that stores data in the form of rows and columns. It is used to represent table-like structures, such as matrices, grids, or tables, where data is organized in two dimensions only.

### Declaration

You can use one of the following syntaxes to declare a two-dimensional array:

[](https://www.tpointtech.com/multidimensional-arrays-in-java#)[](https://www.tpointtech.com/multidimensional-arrays-in-java#)[](https://www.tpointtech.com/multidimensional-arrays-in-java#)

1. DataType[][] arrayName;    

or

[](https://www.tpointtech.com/multidimensional-arrays-in-java#)[](https://www.tpointtech.com/multidimensional-arrays-in-java#)[](https://www.tpointtech.com/multidimensional-arrays-in-java#)

1. DataType arrayName[][];   

or

[](https://www.tpointtech.com/multidimensional-arrays-in-java#)[](https://www.tpointtech.com/multidimensional-arrays-in-java#)[](https://www.tpointtech.com/multidimensional-arrays-in-java#)

1. arrayName = new DataType[rows][columns];   

We can declare and initialize a two-dimensional array in a single statement as follows.

[](https://www.tpointtech.com/multidimensional-arrays-in-java#)[](https://www.tpointtech.com/multidimensional-arrays-in-java#)[](https://www.tpointtech.com/multidimensional-arrays-in-java#)

1. datatype[][] arrayName = new datatype[rows][columns];   

### Assigning Values (Initialization)

Below is the syntax to initialize a two-dimensional array:

[](https://www.tpointtech.com/multidimensional-arrays-in-java#)[](https://www.tpointtech.com/multidimensional-arrays-in-java#)[](https://www.tpointtech.com/multidimensional-arrays-in-java#)

1. arrayName[rows][columns] = {values};   

**Examples**

[](https://www.tpointtech.com/multidimensional-arrays-in-java#)[](https://www.tpointtech.com/multidimensional-arrays-in-java#)[](https://www.tpointtech.com/multidimensional-arrays-in-java#)

1. // 2D Array with two rows and two columns Intialised and Assigned  
2. int[][] arr = { { 1, 2 }, { 3, 4 } };  
3. //array with three rows and three columns  
4.  int[][] arr = new int[3][3];  

### Representation of 2D Array

The following image shows the representation of the 2D Array:

![Multi-Dimensional Arrays in Java](https://images.tpointtech.com/core/images/multi-dimensional-arrays-in-java-1.png)

Note that [Java](https://www.tpointtech.com/java-tutorial) uses zero-based indexing. It means the indexing of arrays in Java starts with 0.

Also, note that in a multi-dimensional array, each row can be of different sizes. It means that each row may not have the same number of elements.

### Example of Two-Dimensional Array

The following example demonstrates how a two-dimensional array works in Java.

[](https://www.tpointtech.com/multidimensional-arrays-in-java#)[](https://www.tpointtech.com/multidimensional-arrays-in-java#)[](https://www.tpointtech.com/multidimensional-arrays-in-java#)

1. public class Main {      
2.     public static void main(String args[]) {      
3.         int arr[][] = {{1, 2, 3}, {4, 5, 6}, {7, 8, 9}}; // 3x3 matrix      
4.         // Printing the 2D array      
5.         for (int i = 0; i < 3; i++)   //loop for rows  
6. {      
7.             for (int j = 0; j < 3; j++)  //loop for columns  
8.    {      
9.                 System.out.print(arr[i][j] + " ");    //prints element with space  
10.             }      
11.             System.out.println();    //throws cursor to the next line  
12.         }      
13.     }      
14. }      

**Output:**

1 2 3
4 5 6
7 8 9

In the above program, we have declared and initialized a 3×3 matrix. The first [for loop](https://www.tpointtech.com/java-for-loop) iterates over the rows, and the second for loop iterates over the columns. The first print statement prints the elements of the array with space, and the second print statement throws the cursor to the next line.

## Two-Dimensional (2D) Array with User Input

In this example, values of a two-dimensional array are taken from the user. First, the number of rows and columns is defined, and then the user enters elements for each position in the array. Nested loops are used to read the input values row by row and column by column, and another set of nested loops is used to display the entered elements in matrix form.

### Example

[](https://www.tpointtech.com/multidimensional-arrays-in-java#)[](https://www.tpointtech.com/multidimensional-arrays-in-java#)[](https://www.tpointtech.com/multidimensional-arrays-in-java#)

1. import java.util.Scanner;  
2. public class Main {  
3.     public static void main(String[] args) {  
4.         Scanner scanner = new Scanner(System.in);  
5.         // Define the dimensions of the array  
6.         System.out.print("Enter the number of rows:");  
7.         int rows = scanner.nextInt();  //reading number of rows from the user  
8.         System.out.print("Enter the number of columns:");  
9.         int columns = scanner.nextInt();  //reading number of columns from the user  
10.         // Initialize the 2D array  
11.         int[][] array = new int[rows][columns];  
12.         //reading array elements from the user  
13.         System.out.println("Enter the elements of the array:");  
14.         for (int i = 0; i < rows; i++)    //loop for rows  
15.         {  
16.             for (int j = 0; j < columns; j++)   //loop for columns  
17.             {  
18.                 System.out.print("Enter element for position (" + i + ", " + j + "): ");  
19.                 //reading array elements one by one  
20.                 array[i][j] = scanner.nextInt();  
21.             }  
22.         }  
23.         // Printing the 2D array  
24.         System.out.println("The entered 2D array is:");  
25.         for (int i = 0; i < rows; i++) {  
26.             for (int j = 0; j < columns; j++) {  
27.                 System.out.print(array[i][j] + " ");  
28.             }  
29.             System.out.println();  
30.         }  
31.         scanner.close();  
32.     }  
33. }  

**Output:**

Enter the number of rows:3
Enter the number of columns:3
Enter the elements of the array:
Enter element for position (0, 0): 1
Enter element for position (0, 1): 2
Enter element for position (0, 2): 3
Enter element for position (1, 0): 4
Enter element for position (1, 1): 5
Enter element for position (1, 2): 6
Enter element for position (2, 0): 7
Enter element for position (2, 1): 8
Enter element for position (2, 2): 9
The entered 2D array is:
1 2 3
4 5 6
7 8 9

## Three-Dimensional (3D) Array

A **Three-Dimensional (3D) array** is an array that contains arrays of arrays. It is used to store data in three dimensions, such as layers, rows, and columns. A 3D array is commonly used to represent complex data structures like a collection of matrices or data arranged across multiple levels.

It is a complex form of a 2D array. In other words, it is an array of a two-dimensional array.

### Declaration

You can use one of the following syntaxes to declare a three-dimensional array:

[](https://www.tpointtech.com/multidimensional-arrays-in-java#)[](https://www.tpointtech.com/multidimensional-arrays-in-java#)[](https://www.tpointtech.com/multidimensional-arrays-in-java#)

1. DataType[][][] arrayName;        

or

[](https://www.tpointtech.com/multidimensional-arrays-in-java#)[](https://www.tpointtech.com/multidimensional-arrays-in-java#)[](https://www.tpointtech.com/multidimensional-arrays-in-java#)

1. DataType arrayName[][][];   

or

[](https://www.tpointtech.com/multidimensional-arrays-in-java#)[](https://www.tpointtech.com/multidimensional-arrays-in-java#)[](https://www.tpointtech.com/multidimensional-arrays-in-java#)

1. arrayName = new DataType[][][];   

We can declare and initialize a three-dimensional array in a single statement as follows.

[](https://www.tpointtech.com/multidimensional-arrays-in-java#)[](https://www.tpointtech.com/multidimensional-arrays-in-java#)[](https://www.tpointtech.com/multidimensional-arrays-in-java#)

1. datatype[][][] arrayName = new datatype[][][];   

### Assigning Values (Initialization)

Below is the syntax to initialize a three-dimensional array:

[](https://www.tpointtech.com/multidimensional-arrays-in-java#)[](https://www.tpointtech.com/multidimensional-arrays-in-java#)[](https://www.tpointtech.com/multidimensional-arrays-in-java#)

1. arrayName[][][] = {values};  

### Representation of 3D Array

![Multi-Dimensional Arrays in Java](https://images.tpointtech.com/core/images/multi-dimensional-arrays-in-java-2.png)

### Example of Three-Dimensional (3D) Array

Let us take the example to demonstrate the working of three dimensional array in Java.

[](https://www.tpointtech.com/multidimensional-arrays-in-java#)[](https://www.tpointtech.com/multidimensional-arrays-in-java#)[](https://www.tpointtech.com/multidimensional-arrays-in-java#)

1. public class Main {  
2.     public static void main(String[] args)   
3.     {  
4.         //declaring and initializing three-dimensional array  
5.         int[][][] threeDArray = {  
6.             {  
7.                 {1, 2, 3},  
8.                 {4, 5, 6}  
9.             },  
10.             {  
11.                 {7, 8, 9},  
12.                 {10, 11, 12}  
13.             }  
14.         };  
15.         //Print the elements of the 3D array  
16.         System.out.println("Elements of the 3D Array:");  
17.         for (int i = 0; i < threeDArray.length; i++) {  
18.             for (int j = 0; j < threeDArray[i].length; j++) {  
19.                 for (int k = 0; k < threeDArray[i][j].length; k++) {  
20.                     System.out.print(threeDArray[i][j][k] + " ");  
21.                 }  
22.                 System.out.println(); // Move to the next line for better readability  
23.             }  
24.             System.out.println(); // Add a blank line between blocks  
25.         }  
26.     }  
27. }  

**Output:**

Elements of the 3D Array:
1 2 3
4 5 6

7 8 9
10 11 12

## Size of Multidimensional Arrays

The size of a multidimensional array depends on the number of elements it contains in each dimension. For example, in a two-dimensional array, the size is determined by the number of rows and columns, while in a three-dimensional array, it depends on layers, rows, and columns.

The [**length** property](https://www.tpointtech.com/java-array-length) is used to find the size of an array. For a multidimensional array, **array.length** gives the number of rows (or first dimension), and **array[row].length** gives the number of columns for a specific row.

### Example

In this example, a two-dimensional array is created with multiple rows and columns. The **length** property is used to get the number of rows, and **array[row].length** is used to get the number of columns in each row.

[](https://www.tpointtech.com/multidimensional-arrays-in-java#)[](https://www.tpointtech.com/multidimensional-arrays-in-java#)[](https://www.tpointtech.com/multidimensional-arrays-in-java#)

1. public class Main {  
2.     public static void main(String[] args) {  
3.         // Creating a 2D array  
4.         int[][] arr = {  
5.             {1, 2, 3},  
6.             {4, 5},  
7.             {6, 7, 8, 9}  
8.         };  

9.         // Number of rows  
10.         System.out.println("Number of rows: " + arr.length);  

11.         // Number of columns in each row  
12.         for (int i = 0; i < arr.length; i++) {  
13.             System.out.println("Number of columns in row " + i + ": " + arr[i].length);  
14.         }  
15.     }  
16. }  

**Output:**

Number of rows: 3
Number of columns in row 0: 3
Number of columns in row 1: 2
Number of columns in row 2: 4