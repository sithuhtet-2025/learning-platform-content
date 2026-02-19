
In the C# programming language, arrays are a collection of elements of the same [data type](https://www.tpointtech.com/csharp-data-types) that are in a single [variable](https://www.tpointtech.com/csharp-variables). If we need to reuse array-related logic, we can define a method and pass the array to it as a parameter. We only need to pass the array's name (without brackets) when calling the method, and it will be passed by reference.

**Syntax**

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-passing-array-to-function#)[](https://www.tpointtech.com/c-sharp-passing-array-to-function#)[](https://www.tpointtech.com/c-sharp-passing-array-to-function#)

1. function_name(array_name);  // passing array to the method  

In this syntax,

- **function_name:** It represents the name of the method.
- **array_name:** It represents the array being passed as an argument.

#### Note: An array is a reference type. It means when we pass an array to a function, we are actually passing a link to the original array, not a new copy. Therefore, any modification of an array inside the function will affect the original array.

## Passing 1-D Arrays as arguments to the methods

In the [C# programming language](https://www.tpointtech.com/c-sharp-tutorial), there are several ways to pass one-dimensional arrays as arguments to a method.

- The [array](https://www.tpointtech.com/c-sharp-arrays) can be declared and initialized the before passing it to the method.
- The array can be declared, initialized, and passed to the method all in a single line of code.

**Syntax**

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-passing-array-to-function#)[](https://www.tpointtech.com/c-sharp-passing-array-to-function#)[](https://www.tpointtech.com/c-sharp-passing-array-to-function#)

1. void Method_name(int[] arr)  
2. {  
3.     // Access or modify array elements  
4. }  

### Passing an Array to a Function Example in C#

Let us take an example to illustrate how we can pass one-dimensional arrays as arguments to methods.

### Example

[](https://www.tpointtech.com/c-sharp-passing-array-to-function#)[](https://www.tpointtech.com/c-sharp-passing-array-to-function#)[](https://www.tpointtech.com/c-sharp-passing-array-to-function#)

1. using System;  
2. class Program     
3. {  
4.     // Declare Method that takes a 1D array as a parameter  
5. static void PrintArray(int[] num_bers)  
6.     {  
7. Console.WriteLine("Array elements:");  
8. foreach (int num in num_bers)  
9.         {  
10. Console.WriteLine(num);  
11.         }  
12.     }  

13. static void Main()  
14.     {  
15.         // declaration and initialization of a 1-D array  
16. int[] my_array = { 10, 20, 30, 40, 50 };  
17.         // Passing to the array in the method  
18. PrintArray(my_array);  
19.     }  
20. }  

**Output:**

Array elements:
10
20
30
40
50

**Explanation:**

In this example, we demonstrate how to pass a 1-D array as arguments to a method. First, we create a method named PrintArray() that takes a multidimensional array as a parameter. After that, we use the foreach loop to print each element. In the main() function, we declare an integer type array and assign a value. These arrays are passed to the PrintArray() method, and then the program shows the output.

## Passing multidimensional arrays as arguments to Methods

In C# programming, we can also pass [multidimensional arrays](https://www.tpointtech.com/c-sharp-multidimensional-array) to a method. We can declare and initialized the array separately before passing it, or it can be declared, initialized, and passed to the method all in a single line of code.

**Syntax**

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-passing-array-to-function#)[](https://www.tpointtech.com/c-sharp-passing-array-to-function#)[](https://www.tpointtech.com/c-sharp-passing-array-to-function#)

1. returnType MethodName(dataType[], arrayName)  
2. {  
3.     // code to be executed  
4. }  

### Passing Multidimensional arrays as arguments Example in C#

Let us take an example to illustrate how we can pass the multidimensional arrays as arguments to methods.

### Example

[](https://www.tpointtech.com/c-sharp-passing-array-to-function#)[](https://www.tpointtech.com/c-sharp-passing-array-to-function#)[](https://www.tpointtech.com/c-sharp-passing-array-to-function#)

1. using System;  
2. class Program  
3. {  
4.     // Create a Method   
5. static void ShowNumbers(int[,] numbers)  
6.     {  
7.         // Iterate over each rows and columns  
8. for (int i = 0; i< 2; i++)  // 2 rows  
9.         {  
10. for (int j = 0; j < 3; j++)  // 3 columns  
11.             {  
12. Console.Write(numbers[i, j] + " ");  
13.             }  
14. Console.WriteLine(); // New line after each row  
15.         }  
16.     }  
17. static void Main()  
18.     {  
19.         // Declaration and Initialization of 2D array  
20. int[,] myNumbers = {  
21. { 1, 2, 3 },  
22. { 4, 5, 6 }  
23.         };  
24.         // Pass the 2D array   
25. ShowNumbers(myNumbers);  
26.     }  
27. }  

**Output:**

1 2 3
4 5 6

**Explanation:**

In this example, we demonstrate how to pass a multidimensional array as arguments to a method. First, we create a method named ShowNumbers() that takes a dimensional array as a parameter. After that, we use the nested for loop to print each element. In the main() function, we declare an integer type array and assign the values. These arrays are passed to the ShowNumbers () method, and then the program shows the output.

### C# Passing an Array to the function Example: Prints the array elements

Let us take an example to define passing an array to a function in C#.

### Example

[](https://www.tpointtech.com/c-sharp-passing-array-to-function#)[](https://www.tpointtech.com/c-sharp-passing-array-to-function#)[](https://www.tpointtech.com/c-sharp-passing-array-to-function#)

1. using System;  
2. public class ArrayExample  
3. {  
4. static void DisplayArr(int[] numbers)  
5.     {  
6. Console.WriteLine("Printing array elements:");  
7. for (int index = 0; index <numbers.Length; index++)  
8.         {  
9. Console.WriteLine(numbers[index]);  
10.         }  
11.     }  
12. public static void Main(string[] args)  
13.     {  
14. int[] data_Set1 = { 100, 200, 300, 400, 500, 600 };  
15. int[] data_Set2 = { 120, 220, 330, 440, 540 };  
16. DisplayArr(data_Set1); // passing array to function  
17. DisplayArr(data_Set2);  
18.     }  
19. }  

**Output:**

Printing array elements:
100
200
300
400
500
600
Printing array elements:
120
220
330
440
540

**Explanation:**

In this example, we demonstrate how to pass an array to a function and display its elements. First, we create a method named DisplayArr(), which takes an array as a parameter. After that, we use a for loop to print each element. In the main() method, we create two integer-type variables dataSet1, dataSet2, that are defined with two different values. These arrays are passed to the DisplayArr() method one by one, and then the program displays the output.

### C# Passing an Array to the function Example: Print the minimum number

Let us take an example to illustrate how we can pass an array of functions that print the minimum number in the array.

### Example

[](https://www.tpointtech.com/c-sharp-passing-array-to-function#)[](https://www.tpointtech.com/c-sharp-passing-array-to-function#)[](https://www.tpointtech.com/c-sharp-passing-array-to-function#)

1. using System;  
2. public class ArrayExample  
3. {  
4. static void FindMinimum(int[] numbers)  
5.     {  
6. int smallest = numbers[0];  
7. for (int i = 1; i<numbers.Length; i++)  
8.         {  
9. if (smallest > numbers[i])  
10.             {  
11. smallest = numbers[i];  
12.             }  
13.         }  
14. Console.WriteLine("Minimum element is: " + smallest);  
15.     }  
16. public static void Main(string[] args)  
17.     {  
18. int[] data1 = { 25, 5, 20, 15, 40, 50 };  
19. int[] data2 = { 12, 23, 44, 15, 54 };  
20. FindMinimum(data1); // passing array to function  
21. FindMinimum(data2);  
22.     }  
23. }  

**Output:**

Minimum element is: 5
Minimum element is: 12

**Explanation:**

In this example, we demonstrate how to pass arrays to a function to find and print the minimum element of an array. First, we create a method named FindMinimum that takes an array as a parameter. After that, we use a for loop to print each element. In the main() method, we create an integer type variable data1, and data2 is defined with two different values. These arrays are passed to the FindMinimum method one by one.

### C# Passing an Array to a function Example: Print the maximum number

Let us take an example to illustrate how we can pass an array to the function that prints the maximum number.

### Example

[](https://www.tpointtech.com/c-sharp-passing-array-to-function#)[](https://www.tpointtech.com/c-sharp-passing-array-to-function#)[](https://www.tpointtech.com/c-sharp-passing-array-to-function#)

1. using System;    
2. public class ArrayExample  
3. {    
4. static void printMax(int[] arr)    
5.     {    
6. int max = arr[0];    
7. for (int i = 1; i<arr.Length; i++)    
8.         {    
9. if (max <arr[i])    
10.             {    
11. max = arr[i];    
12.             }    
13.         }    
14. Console.WriteLine("Maximum element is: " + max);    
15.     }    
16. public static void Main(string[] args)    
17.     {    
18. int[] arr1 = { 25, 10, 20, 15, 40, 50 };    
19. int[] arr2 = { 12, 23, 64, 11, 54 };    
20. printMax(arr1);//passing array to function    
21. printMax(arr2);    
22.     }    
23. }   

**Output:**

Maximum element is: 50
Maximum element is: 64

**Explanation:**

In this example, we demonstrate how to pass arrays to a function to find and print the maximum element of an array. First, we create a method named printMax() that takes an array as a parameter. After that, we use a for loop to print each element. In the main() method, we create an integer type variable arr1, and arr2 is defined with two different values. These arrays are passed to the FindMaximum method one by one.

## Conclusion

In conclusion, passing arrays to functions enables code reusability and modularity, which makes the programs clear and easy to maintain. C# allows us to pass single or multidimensional arrays to methods either by using reference or parameters, which enables efficient data manipulation and processing within methods.