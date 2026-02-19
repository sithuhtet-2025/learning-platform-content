

In the C# programming language, an array is a collection of the same types of data items in a single variable. It does not save any memory space. It works on the basis of an index. The array start index is 0, and the last element of the index is size-1.

![C# array](https://images.tpointtech.com/csharp/images/c-sharp-arrays-1.png)

## Simple Array Example in C#

Let us take an example to illustrate how we define arrays.

### Example

[](https://www.tpointtech.com/c-sharp-arrays#)[](https://www.tpointtech.com/c-sharp-arrays#)[](https://www.tpointtech.com/c-sharp-arrays#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {  
6.         // defining an array and assigning values  
7.         int [] num_bers = { 10, 20, 30 };  
8.         //using for loop      
9.         for (int i = 0; i < num_bers.Length; i++)  
10.         {  
11.             Console.WriteLine("Element at index " + i + " is: " + num_bers[i]);  
12.         }  
13.     }  
14. }  

**Output:**

Element at index 0 is: 10
Element at index 1 is: 20
Element at index 2 is: 30

**Explanation:**

In this example, we explain the array in a very simple way. First, we define the integer type array named number and initializing it with some initial values. After that, we are using a for loop to iterate over the numbers. Finally, we use the Console.WriteLine() function to print the numbers.

Here, we will discuss the array declaration, initialization, accessing, and many others.

## Array Declaration

In the [C# programming language](https://www.tpointtech.com/c-sharp-tutorial), an array is built by first defining the [data type](https://www.tpointtech.com/csharp-data-types) and then the array name and size, which are both surrounded in square brackets [].

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-arrays#)[](https://www.tpointtech.com/c-sharp-arrays#)[](https://www.tpointtech.com/c-sharp-arrays#)

1. data_type array_name [size];  

The syntax defines an array named array_name with a size.

The data_type represents the type of an array, such as int, float, char, etc.

**For Example:**

[](https://www.tpointtech.com/c-sharp-arrays#)[](https://www.tpointtech.com/c-sharp-arrays#)[](https://www.tpointtech.com/c-sharp-arrays#)

1. int my_arr [10];  

In this example,

- **int:** It represents the type of value that can be stored in an array.
- **arr:** It declares the name of an array.
- **10:** It represents the size of an array.

## Initializing an Array in C#

The array is initializing when it is declared. An array can be initialized in two typical ways.

- Initializing an array during declaration
- Assigning values after declaration

### a) Initializing an array during declaration

In the C# programming language, an array is initialized inside curly braces {} after the declaring of an array.

**For Example:**

[](https://www.tpointtech.com/c-sharp-arrays#)[](https://www.tpointtech.com/c-sharp-arrays#)[](https://www.tpointtech.com/c-sharp-arrays#)

1. int myarr [5] = {1, 2, 3, 4, 5};  

### b) Assigning values after declaration

An array is initialized based on the index. It is initialized by declaring it first.

**For Example:**

Let's take an illustrative example to assign the value after the declaration of an array.

[](https://www.tpointtech.com/c-sharp-arrays#)[](https://www.tpointtech.com/c-sharp-arrays#)[](https://www.tpointtech.com/c-sharp-arrays#)

1. int arr[4]; // declaration of an array  
2. // Assigning values to each element  
3. arr [0] = 5;  
4. arr [1] = 10;  
5. arr [2] = 15;  
6. arr [3] = 20;  
7. arr [4] = 25;  

## Accessing Array Elements in C#

In the C# programming language, indexing is the process of accessing the element in an array by following the array name with the index number enclosed in square brackets ([]). The first element of an index is 0, and the last element of an index is size-1. It enables us to direct access, retrieval, and modification of particular array elements.

![C# array](https://images.tpointtech.com/csharp/images/c-sharp-arrays-2.png)

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-arrays#)[](https://www.tpointtech.com/c-sharp-arrays#)[](https://www.tpointtech.com/c-sharp-arrays#)

1. name_of_the_array[index];  

### Accessing Array Elements Example in C#

Let us take an example to illustrate accessing array elements in C#.

### Example

[](https://www.tpointtech.com/c-sharp-arrays#)[](https://www.tpointtech.com/c-sharp-arrays#)[](https://www.tpointtech.com/c-sharp-arrays#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {  
6.         // defining an array and assigning some values  
7.         int [] num_bers = { 10, 20, 30, 40, 50 };  
8.         // Displaying specific elements from the array  
9.         Console.WriteLine("The starting element at the index 0: " + num_bers[0]);  
10.         Console.WriteLine("The middle element at the index 2: " + num_bers[2]);  
11.         Console.WriteLine("The last element at the index 4: " + num_bers[4]);  
12.         Console.Write("The complete array elements: ");  
13.         for (int index = 0; index < num_bers.Length; index++)  
14.         {  
15.             Console.Write(num_bers[index] + " ");  
16.         }  
17.         Console.WriteLine(); // To move to the next line after the loop  
18.     }  
19. }  

**Output:**

The starting element at the index 0: 10
The middle element at the index 2: 30
The last element at the index 4: 50
Complete array elements: 10 20 30 40 50

**Explanation:**

In this example, we create an array named num_bers and then initializing the array. After that, we use the num_bers[0], num_bers[2], and numbers[4] to access the 0, 2, and 4 indexing value of numbers. We are using the foreach loop to iterate over the numbers. Finally, we are using the Console.WriteLine() function to print the output.

### Taking inputs from the user and storing them in an Array in C#

Let us take an example to take inputs from the user and store them in an array.

### Example

[](https://www.tpointtech.com/c-sharp-arrays#)[](https://www.tpointtech.com/c-sharp-arrays#)[](https://www.tpointtech.com/c-sharp-arrays#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {  
6.         int[] num_bers = new int[3];  
7.         Console.WriteLine("Enter 3 numbers:");  
8.         for (int i = 0; i < 3; i++)  
9.         {  
10.             Console.Write("Number " + (i + 1) + ": ");  
11.             num_bers[i] = Convert.ToInt32(Console.ReadLine());  
12.         }     
13.         Console.WriteLine("You entered:");  
14.         for (int i = 0; i < 3; i++)  
15.         {  
16.             Console.WriteLine(num_bers[i]);  
17.         }  
18.     }  
19. }  

**Output:**

Enter 3 numbers:
Number 1: 5
Number 2: 10
Number 3: 15
You entered:
5
10
15

**Explanation:**

In this example, we create an array named numbers with a size of 3 to store three user-input values. The user entered the number one by one. Each input is read using Console.ReadLine() function and convert an integer using Convert.ToInt32(). After that, we are using a for loop to iterate over the number. Finally, we are using the Console.WriteLine() function to print the output.

## Types of Arrays in C#

There are three types of the C# Programming language. These are as follows:

![C# array](https://images.tpointtech.com/csharp/images/c-sharp-arrays-3.png)

## 1) Single-dimensional Array

In the C# programming language, a single-dimensional array is a type of array that can hold a fixed number of elements of the same type in a sequence.

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-arrays#)[](https://www.tpointtech.com/c-sharp-arrays#)[](https://www.tpointtech.com/c-sharp-arrays#)

1. type arrayname = new type [size];  

In this syntax,

- **type:** It defines the data type of the value that the array can store.
- **arrayname:** It defines the name of an array.
- **Size:** It represents the size of an array.

### C# Single-dimensional Array Example

Let's take an example to define the Single-dimensional array in C#.

### Example

[](https://www.tpointtech.com/c-sharp-arrays#)[](https://www.tpointtech.com/c-sharp-arrays#)[](https://www.tpointtech.com/c-sharp-arrays#)

1. using System;  
2. public class ArrayExample  
3. {     
4.     public static void Main(string[] args)  
5.     {  
6.         // defining and initializing an array of size 5  
7.         int [] con = new int[5];  
8.         con [0] = 10;  
9.         con [2] = 20;  
10.         con [4] = 30;  
11.         // Traversing the array and printing elements  
12.         for (int i = 0; i < con.Length; i++)  
13.         {  
14.             Console.WriteLine("Element at index " + i + ": " + con[i]);  
15.         }  
16.     }  
17. }  

**Output:**

Element at index 0: 10
Element at index 1: 0
Element at index 2: 20
Element at index 3: 0
Element at index 4: 30

**Explanation:**

In this example, we are using a single-dimensional array in C#. First, we are declaring the array named numbers and initialize one by one. After that, we are using the foreach loop to iterate over the numbers. Finally, we are using the Console.WriteLine() function to print the output.

### C# Array Example: Initialization and Declaration at the same time

There are three ways to initialize an array at the time of declaration.

[](https://www.tpointtech.com/c-sharp-arrays#)[](https://www.tpointtech.com/c-sharp-arrays#)[](https://www.tpointtech.com/c-sharp-arrays#)

1. int [] arr = new int[5]{1, 2, 3, 4, 5};  

We can omit the size of an array.

[](https://www.tpointtech.com/c-sharp-arrays#)[](https://www.tpointtech.com/c-sharp-arrays#)[](https://www.tpointtech.com/c-sharp-arrays#)

1. Int[] arr = new int[] {10, 20, 30, 40, 50};  

We can omit the new operator also.

[](https://www.tpointtech.com/c-sharp-arrays#)[](https://www.tpointtech.com/c-sharp-arrays#)[](https://www.tpointtech.com/c-sharp-arrays#)

1. Int arr[] = {10,20,30,40,50};  

Let us see the example of an array where we declare and initializing array at the same time.

### Example

[](https://www.tpointtech.com/c-sharp-arrays#)[](https://www.tpointtech.com/c-sharp-arrays#)[](https://www.tpointtech.com/c-sharp-arrays#)

1. using System;    
2. public class ArrayExample    
3. {    
4.     public static void Main(string[] args)    
5.     {    
6.         int[] arr = { 100, 200, 300, 400, 500 };//defining and Initialization of array    
7.         //traversing array    
8.         for (int i = 0; i < arr.Length; i++)    
9.         {    
10.             Console.WriteLine(arr[i]);    
11.         }    
12.     }    
13. }    

**Output:**

100
200
300
400
500

**Explanation:**

In this example, first we define an integer type array named arr and then initialize with some initial value. After that, we are using the for loop to iterate over the numbers. Finally, we use the Console.WriteLine() function to print the number.

### C# Array Example: Traversal Using foreach loop

We can also traverse the array elements using a foreach loop. It returns the array element one by one.

### Example

[](https://www.tpointtech.com/c-sharp-arrays#)[](https://www.tpointtech.com/c-sharp-arrays#)[](https://www.tpointtech.com/c-sharp-arrays#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {  
6.         // defining and initialize a string array  
7.         string[] fruits = { "Apple", "Banana", "Cherry", "Date" };  
8.         // Traverse the array using foreach loop  
9.         Console.WriteLine("The Fruits in an array:");  
10.         foreach (string fruit in fruits)  
11.         {  
12.             Console.WriteLine(fruit);  
13.         }  
14.     }  
15. }  

**Output:**

The Fruits in an array:
Apple
Banana
Cherry
Date

**Explanation:**

In this example, we build an illustrative example of an array. First, we define a string type array named fruits. After that, we are using the foreach loop to iterate over the elements and print the elements using Console.WriteLine() function.

## 2) Multidimensional Array

In the C# programming language, a [multidimensional array](https://www.tpointtech.com/c-sharp-multidimensional-array) is an array of arrays that contains more than one array as its elements. It is a set of items where the elements are accessed using multiple indices.

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-arrays#)[](https://www.tpointtech.com/c-sharp-arrays#)[](https://www.tpointtech.com/c-sharp-arrays#)

1. data_type array_name[a1][a2]…[an];  

Here, a1, a2, …, an define the size of the array.

### C# Multidimensional Array Example

Let us take an illustrative example to define the multidimensional array in C#.

### Example

[](https://www.tpointtech.com/c-sharp-arrays#)[](https://www.tpointtech.com/c-sharp-arrays#)[](https://www.tpointtech.com/c-sharp-arrays#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {     
6.         // define the 2-dimensional array  
7.         int[,] mat = {  
8.             {4, 3, 2},  
9.             {6, 1, 5},  
10.             {9, 7, 8}  
11.         };  
12.         // display the 2-dimensional array  
13.         Console.WriteLine("The matrix elements are:");  
14.         for (int i = 0; i < 3; i++)  
15.         {  
16.             for (int j = 0; j < 3; j++)  
17.             {  
18.                 Console.Write(mat[i, j] + " ");  
19.             }  
20.             Console.WriteLine();  
21.         }  
22.     }  
23. }  

**Output:**

The matrix elements are:
4 3 2
6 1 5
9 7 8

**Explanation:**

In this example, we use a multidimensional array in C#. First, we create the two-dimensional array, which has 3 rows and 3 columns. After that, we use the nested for loop to iterate over the values of the matrix. In the end, we are using the Console.WriteLine() function to print the output.

### C# Example to display the sum and average of the array Elements

Let's take an example to find the sum and average of the array elements in C#.

### Example

[](https://www.tpointtech.com/c-sharp-arrays#)[](https://www.tpointtech.com/c-sharp-arrays#)[](https://www.tpointtech.com/c-sharp-arrays#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {  
6.         // Initializaton of an array  
7.         double[] num1 = { 7, 5, 6, 12, 35, 27 };  
8.         double sum1 = 0;  
9.         double count1 = 0;  
10.         double avg1;  
11.         Console.Write("The numbers are: ");  
12.         // Use of the foreach loop to iterate over the value  
13.         foreach (double n in num1)  
14.         {  
15.             Console.Write(n + "  ");  
16.             // calculate the sum of the numbers  
17.             sum1 += n;  
18.             // Count the number of elements  
19.            count1++;  
20.         }  
21.         // Print the sum of the numbers  
22.         Console.WriteLine("\n The sum of numbers = " + sum1);  
23.         // Find the average of the numbers  
24.         avg1 = sum1 / count1;  
25.         Console.WriteLine("The average of the numbers = " + avg1);  
26.     }  
27. }  

**Output:**

The numbers are: 7 5 6 12 35 27
The sum of numbers = 92
The average of the numbers = 15.3333333333333

**Explanation:**

In this example, we demonstrate how to use an array to calculate the sum and average of the numbers. First, we create an array named numbers. After that, we are using the foreach loop to iterate over the numbers. After the loop, we compute the sum and average of the numbers. In the end, we are using the Console.WriteLine() function to print the output.

### C# Example to display the Array Element

Here, we will discuss an example to display the array element in C#.

### Example

[](https://www.tpointtech.com/c-sharp-arrays#)[](https://www.tpointtech.com/c-sharp-arrays#)[](https://www.tpointtech.com/c-sharp-arrays#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {  
6.         int[] num1 = { 7, 5, 6, 12, 35 };  
7.         Console.Write("The numbers are: ");  
8.         foreach (int n in num1)  
9.         {     
10.             Console.Write(n + "  ");  
11.         }  
12.         Console.Write("\n The numbers are: ");  
13.         for (int i = 0; i < num1.Length; i++)  
14.         {  
15.             Console.Write(num1[i] + "  ");  
16.         }  
17.         Console.WriteLine(); // To move to the next line after output  
18.     }  
19. }  

**Output:**

The numbers are: 7 5 6 12 35
The numbers are: 7 5 6 12 35

**Explanation:**

In this program, we are using to display the array elements using two for loops. First, we create an array named numbers and initialized it with five values. After that, we use the foreach loop to print the element directly. Finally, we use the Console.WriteLine() function to display the output.

## Advantages of C# Array:

Several advantages of arrays in C# are as follows:

- **Code Optimization:** An array is used to store multiple values in a single variable. This reduces the requirements for multiple individual variables.
- **Random Access:** An array element is accessed using an index that represents the position of an array. It allows direct access to the value stored at a specific position.
- **Easy to traverse data:** In C#, an array can be traversed very easily with a loop. We can easily access the elements one by one.
- **Easy to manipulate data:** In C#, arrays can be manipulated very easily with a loop. We can easily modify the elements one by one.
- **Easy to sort data:** In C#, arrays have several built-in function such as sort () function.

## Disadvantages of C# Array:

Several disadvantages of the C# array are as follows:

- **Fixed size:** Array sizes are fixed, and cannot be modified once it declared.
- **Wastage of Memory:** When we declare a large-sized array, we cannot reduce the memory once it is declared.
- **Lack of flexibility:** In C#, array sizes are static, and it cannot be resized dynamically.

## Conclusion

In C#, the array is the key factor for any programmer to create a software application. It is the main objective for the development. It is a collection of the same or different types of data items in a single variable. It reduces the requirements for multiple individual variables.

## C# Array FAQs

**1) What is an array in C#?**

In the C# programming language, an array is a collection of the same or different types of data items in a single variable. It does not save any memory space. It works on the basis of an index. The array start index is 0, and the last element of the index is size-1.

**2) What does the Length property of an array represent?**

The Length property is used to analyse the total number of elements.

[](https://www.tpointtech.com/c-sharp-arrays#)[](https://www.tpointtech.com/c-sharp-arrays#)[](https://www.tpointtech.com/c-sharp-arrays#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {  
6.         int[] my_arr = { 1, 2, 3 };  
7.         Console.WriteLine("The length of an array is " + my_arr.Length);  
8.     }  
9. }   

**Output:**

The length of an array is 3

**3) What is a multi-dimensional array in C#?**

In the C# programming language, a multi-dimensional array is an array of arrays that contains more than one array as its elements. It is a set of items where the elements are accessed using multiple indices.

**4) Can we change the size of an array after it is declared?**

No, in C#, the Array size is fixed. If we declared the size once, we cannot modify the size of an array.

**5) How do we declare and initialize the array?**

The declaration and initialization of an array are as follows.

**Declaration:**

Here's the following syntax of array declaration.

[](https://www.tpointtech.com/c-sharp-arrays#)[](https://www.tpointtech.com/c-sharp-arrays#)[](https://www.tpointtech.com/c-sharp-arrays#)

1. int arr [10];  

**Initialization: o**

Here's the following syntax of array initialization.

[](https://www.tpointtech.com/c-sharp-arrays#)[](https://www.tpointtech.com/c-sharp-arrays#)[](https://www.tpointtech.com/c-sharp-arrays#)

1. int my_arr [5] = {1, 2, 3, 4, 5};