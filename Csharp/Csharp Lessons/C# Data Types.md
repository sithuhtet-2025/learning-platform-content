# 

In C#, data types specify the types of data variables. These are mainly used to define the type of data that a variable can store, including integers, floating-point numbers, characters, or Boolean values. It also defines the memory size and range of a memory.

## Types of Data Types in C#

There are three types of data type in C#. These are as follows:

![CSHRAP Data types 1](https://images.tpointtech.com/csharp/images/csharp-data-type-1.png)

Here, we will discuss these different data types one by one.

## Primitive Data Types

In [C#](https://www.tpointtech.com/c-sharp-tutorial), primitive data types are fundamental, predefined types that represent simple values. Primitive data types contain several data types, including integer types, floating-point, decimal type, char type, and bool type. 

|Data Type|Size|
|---|---|
|int|2-byte or 4-byte|
|float|4-byte|
|double|8 byte|
|char|8-bit / 1 byte|
|long int|8-byte|
|long double|12 byte|
|boolean|1byte or 8bits|
|short int|2 byte|

Here, we will discuss these primitive data types one by one.

### 1) Integer Types

In C#, the integer data type is used to store the numeric values except for decimal values.

**i. Signed int:** It is used to store both positive and negative integer values. Generally, it has 4-byte memory spaces. It is used to store the values between 2,147,483,648 and 2,147,483,647.

**Example:**

[](https://www.tpointtech.com/csharp-data-types#)[](https://www.tpointtech.com/csharp-data-types#)[](https://www.tpointtech.com/csharp-data-types#)

1. signed int number = -50  

**ii. Unsigned int:** Unsigned data type is used for storing the positive integer values. It has 4 bytes of memory space and stores the value between (0 to 4,294,967,295).

**Example:**

[](https://www.tpointtech.com/csharp-data-types#)[](https://www.tpointtech.com/csharp-data-types#)[](https://www.tpointtech.com/csharp-data-types#)

1. Unsigned int number = 50  

**iii. Short int:** The short int data type has a limited range (-32,768 to 32,767) to store the values.

**Example:**

[](https://www.tpointtech.com/csharp-data-types#)[](https://www.tpointtech.com/csharp-data-types#)[](https://www.tpointtech.com/csharp-data-types#)

1. Short int number = 100;  

**iv. Long int:** The long int data type is mainly utilized to store large numbers. It takes 4 to 8 bytes of memory space.

**Example:**

[](https://www.tpointtech.com/csharp-data-types#)[](https://www.tpointtech.com/csharp-data-types#)[](https://www.tpointtech.com/csharp-data-types#)

1. long int number a = 1000  

### C# Integer Types Example

Let us take an example to illustrate the integer type in C#.

### Example

[](https://www.tpointtech.com/csharp-data-types#)[](https://www.tpointtech.com/csharp-data-types#)[](https://www.tpointtech.com/csharp-data-types#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {  
6.         int regularInt = 100;     // regular signed 32-bit integer  
7.         uint unsignedInt = 200;  // Unsigned 32-bit integer   
8.         short shortInt = -32000;    // Signed 16-bit integer  
9.         long longInt = 9223372036854775807;     // Signed 64-bit integer  
10.         Console.WriteLine("int: " + regularInt);  
11.         Console.WriteLine("uint: " + unsignedInt);  
12.         Console.WriteLine("short: " + shortInt);  
13.         Console.WriteLine("long: " + longInt);  
14.     }  
15. }  

**Output:**

int: 100
uint: 200
short: -32000
long: 9223372036854775807

**Explanation:**

In this example, we have taken the signed, unsigned, short, and long integer data types. After that, we use the Console.WriteLine() function to display the output.

### 2) Floating-Point Type

C# provides two main floating-point data types to store real numbers, including fractions and decimals. These types offer different levels of precision and memory usage, which makes them suitable for a variety of numerical computations.

**a. Float (single precision):** It takes 4-bytes memory space. It is also known as single precision.

**Example:**

[](https://www.tpointtech.com/csharp-data-types#)[](https://www.tpointtech.com/csharp-data-types#)[](https://www.tpointtech.com/csharp-data-types#)

1. float number = 32.4f;  

**b. Double (double precision):** The double value needs 8 bytes of memory space. It provides 15-16 decimal digits of precision.

**Example:**

[](https://www.tpointtech.com/csharp-data-types#)[](https://www.tpointtech.com/csharp-data-types#)[](https://www.tpointtech.com/csharp-data-types#)

1. double number = 5.222222220000000  

### C# Floating-Point Types Example

Let us take an example to illustrate the floating-point types in C#.

### Example

[](https://www.tpointtech.com/csharp-data-types#)[](https://www.tpointtech.com/csharp-data-types#)[](https://www.tpointtech.com/csharp-data-types#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {  
6.         // floating-point data  
7.         float h1 = 5.9f;  
8.         // This is a double-point data  
9.         double h2 = 72.5;  
10.         // Define h3 explicitly  
11.         double h3 = 180.3;  

12.         // Showing the values  
13.         Console.WriteLine("h1 is " + h1 + " ft");  
14.         Console.WriteLine("h2 is " + h2 + " ft");  
15.         Console.WriteLine("h3 is " + h3 + " ft");  
16.     }     
17. }  

**Output:**

h1 is 5.9 ft
h2 is 72.5 ft
h3 is 180.3 ft

**Explanation:**

In this example, we have taken three variables h1, h2, and h3 for float and double data type. After that, it prints the output using the Console.WriteLine function.

### 3) Character Type:

In C#, character data type is used to store the single character. It requires 8 bits or 1-byte of memory space. These data types can be used to represent any character from the ASCII or Unicode set, including numbers, letters, symbols, etc.

**Example:**

[](https://www.tpointtech.com/csharp-data-types#)[](https://www.tpointtech.com/csharp-data-types#)[](https://www.tpointtech.com/csharp-data-types#)

1. char alphabet = 's';  

### C# Character Type Example

Let us take an example to illustrate the character type in C#.

### Example

[](https://www.tpointtech.com/csharp-data-types#)[](https://www.tpointtech.com/csharp-data-types#)[](https://www.tpointtech.com/csharp-data-types#)

1. using System;  
2. public class program  
3. {  
4.     public static void Main(string[] args)  
5.     {  
6.            char letter = 'A';  
7.            Console.WriteLine("The character is " + letter);  
8.     }  
9. }  

**Output:**

The character is A

**Explanation:**

In this example, we have taken the letter character data type. After that, we use the Console.WriteLine() function to display the output.

### 4) Boolean type (bool):

In C#, the boolean data type is used for storing the logical values, true or false. It is used for conditional statements or decision-making, and it is primarily used for the effective evaluation of logical expressions and conditions.

**Example:**

[](https://www.tpointtech.com/csharp-data-types#)[](https://www.tpointtech.com/csharp-data-types#)[](https://www.tpointtech.com/csharp-data-types#)

1. bool b = true;  
2. bool d = false;  

### C# Boolean Type Example

Let us take an example to illustrate the Boolean type in C#.

### Example

[](https://www.tpointtech.com/csharp-data-types#)[](https://www.tpointtech.com/csharp-data-types#)[](https://www.tpointtech.com/csharp-data-types#)

1. using System;  
2. public class program  
3. {  
4.     public static void Main(string[] args)  
5.     {  
6.                bool isRaining = true;  
7.                Console.WriteLine("Is it raining? " + isRaining);  
8.     }  
9. }  

**Output:**

Is it raining? True

**Explanation:**

In this example, we have taken the isRaining boolean data type. After that, we use the Console.WriteLine() function to display the output.

## Derived Data Type

In C#, the derived data type is a data type that is created by the programmer to improve functionality and make complex data processing. These types of features allow structured programming approaches to handle data efficiently and provide efficient memory management. There are several types of derived data types, including [arrays](https://www.tpointtech.com/c-sharp-arrays), pointers, and references.

### 1) Arrays

In C#, an array is a fixed-size collection of elements with the same type that is stored in consecutive memory places. Arrays helps to improve the efficiency of data manipulation by storing multiple values under a single variable name.

**i. One-dimensional array**

In C#, a one-dimensional array is mainly utilized to store the linear collection of elements. It is also known as a linear array.

**Example:**

[](https://www.tpointtech.com/csharp-data-types#)[](https://www.tpointtech.com/csharp-data-types#)[](https://www.tpointtech.com/csharp-data-types#)

1. int number[3] = {10,20,30}  

**ii. Multi-dimensional array**

The multi-dimensional array is used to store multiple arrays of arrays. It uses rows and columns and stores the data in matrix format.

**iii. Dynamic array**

In C#, a dynamic array is implemented by using the List<S> class. It allows to store and manage data during runtime.

**Syntax**

It has the following syntax:

[](https://www.tpointtech.com/csharp-data-types#)[](https://www.tpointtech.com/csharp-data-types#)[](https://www.tpointtech.com/csharp-data-types#)

1. List<int> newlist = new List<int>(arr);  

### C# Array Example

Let us consider the following examples of one-dimensional arrays, multi-dimensional arrays, and dynamic arrays.

### Example

[](https://www.tpointtech.com/csharp-data-types#)[](https://www.tpointtech.com/csharp-data-types#)[](https://www.tpointtech.com/csharp-data-types#)

1. using System;  
2. using System.Collections.Generic;  
3. class Program  
4. {  
5.     static void Main()  
6.     {  
7.         int[] arr1 = { 10, 20, 30, 40, 50 };  // one-dimensional array  
8.         Console.WriteLine("One-Dimensional Array:");  
9.         foreach (int item in arr1)  // for each loop  
10.         {  
11.             Console.Write(item + " ");  
12.         }  
13.         Console.WriteLine("\n");  
14.         int[,] arr2 = {    // multi-dimensional array  
15.             { 1, 2 },  
16.             { 3, 4 },  
17.             { 5, 6 }  
18.         };  
19.         Console.WriteLine("Two-Dimensional Array:");  
20.         for (int i = 0; i < arr2.GetLength(0); i++)  //nested for loop  
21.         {  
22.             for (int j = 0; j < arr2.GetLength(1); j++)  
23.             {  
24.                 Console.Write(arr2[i, j] + " ");  
25.             }  
26.             Console.WriteLine();  
27.         }  
28.         Console.WriteLine();  
29.         List<string> arr3 = new List<string>();  // dynamic-array  
30.         arr3.Add("A");  
31.         arr3.Add("B");  
32.         arr3.Add("C");  
33.         Console.WriteLine("Dynamic Array:");  
34.         foreach (string alphabet in arr3)  // foreach loop  
35.         {  
36.             Console.WriteLine(alphabet);  
37.         }  
38.     }  
39. }  

**Output:**

One-Dimensional Array:
10 20 30 40 50

Two-Dimensional Array:
1 2
3 4
5 6

Dynamic Array:
A
B
C

**Explanation:**

In this example, we demonstrate three types of arrays, a one-dimensional array, a two-dimensional array, and a dynamic array using List<T>. First, it displays the values of a simple integer array using a foreach loop. After that, it displays a two-dimensional array (matrix) with nested for loops to access rows and columns. Finally, it uses a List<string> as a dynamic array that can grow at runtime, which prints its results with another foreach loop.

### 2) Pointer

In C#, pointers are a variable that is used to store the address of another variable. It is a reference-type variable that can store the memory address of another variable. Pointers are fast because we can access and store the memory address of another variable. Pointers are represented by the * symbol.

**Syntax**

It has the following syntax:

[](https://www.tpointtech.com/csharp-data-types#)[](https://www.tpointtech.com/csharp-data-types#)[](https://www.tpointtech.com/csharp-data-types#)

1. type*var-name;  

In C#, when we used the pointers variable, it must use the unsafe modifier. The declaration of a pointer variable in C# as follows:

[](https://www.tpointtech.com/csharp-data-types#)[](https://www.tpointtech.com/csharp-data-types#)[](https://www.tpointtech.com/csharp-data-types#)

1. int *sp;  // integer type of pointer  
2. double *dp;  // double type of pointer  

Here, we declared the pointer variable are as follows

### Example

[](https://www.tpointtech.com/csharp-data-types#)[](https://www.tpointtech.com/csharp-data-types#)[](https://www.tpointtech.com/csharp-data-types#)

1. static unsafe void Main(string[] args) {  
2.  int num = 100;  
3.    int* p = &var;  
4.    Console.WriteLine("Number is: {0} ", num);  
5.    Console.WriteLine("Address is: {0}", (int)p);  
6.    Console.ReadKey();  
7. }  

### 3) Reference Type

In C#, a reference type is a copy of the reference (address) that is passed to the method. It is an alias for any other variable.

**C# Reference Type Example**

Let us take an example to illustrate a reference type in C#.

### Example

[](https://www.tpointtech.com/csharp-data-types#)[](https://www.tpointtech.com/csharp-data-types#)[](https://www.tpointtech.com/csharp-data-types#)

1. using System;  
2. class Program  
3. {  
4.     class P  //declaring class P  
5.     {  
6.         public string Name;  
7.     }  
8.     static void Main()  
9.     {  
10.         P p1 = new P();  // p1 is the object of P  
11.         p1.Name = "John";  
12.         P p2 = p1;   // p2 is the reference to the same object as p1  
13.         p2.Name = "Albert";   // modify the name by using p2  
14.         // both refer to the same object, p1.Name also changes  
15.         Console.WriteLine("p1.Name: " + p1.Name);  
16.         Console.WriteLine("p2.Name: " + p2.Name);   
17.     }  
18. }  

**Output:**

p1.Name: Albert
p2.Name: Albert

**Explanation:**

In this example, we create the class named **P,** where we declare the string type variable. After that, we create the object of the class **p1** in the main function and assign the value. Next, we create the p2 object as the same class P, and then we assign the modified name. Finally, it prints the output by using the Console.WriteLine().

## User-defined data type

In C#, the user-defined data types are mainly created by the programmer to fulfill the custom need. These data types help to organize and manage real-world entities effectively.

### Types of User-Defined Data Types:

There are several types of user-defined data types in C# as follows:

- Struct
- Class
- Union
- Enumeration

Here, we will discuss these user-defined data types one by one in C#.

### 1) Struct

In C#, a struct is a user user-defined data type that allows us to store several variables of data types.

**Syntax**

It has the following syntax:

[](https://www.tpointtech.com/csharp-data-types#)[](https://www.tpointtech.com/csharp-data-types#)[](https://www.tpointtech.com/csharp-data-types#)

1. struct StructName {  
2.     datatype member;  
3. };  

**C# Struct Example**

Let us take an example to illustrate the struct data type in C#.

### Example

[](https://www.tpointtech.com/csharp-data-types#)[](https://www.tpointtech.com/csharp-data-types#)[](https://www.tpointtech.com/csharp-data-types#)

1. using System;  
2. namespace Program  
3. {  
4.     struct detail   //define the struct  
5.     {  
6.         public int num;  
7.         public string performance;  
8.     }  
9.     class Program  
10.     {  
11.         static void Main()  
12.         {  
13.             detail p;  // create the struct   
14.             p.num = 10;  
15.             p.performance = "Excellent";  
16.             Console.WriteLine($"Num: {p.num}, Performance: {p.performance}");    
17.         }  
18.     }  
19. }  

**Output:**

Num: 10, Performance: Excellent

**Explanation:**

In this example, we create a struct data type using the **struct** keyword to store the integer and string type values. After that, we create the variable p and assign the integer and string value. Finally, it prints the output by using the Console.Writeline function.

### 2) Class

In C#, [class](https://www.tpointtech.com/c-sharp-object-and-class) is the collection of data members and data methods. It is mainly utilized in Object-Oriented Programming languages (OOPs). It is declared using the class keyword.

**Syntax**

It has the following syntax:

[](https://www.tpointtech.com/csharp-data-types#)[](https://www.tpointtech.com/csharp-data-types#)[](https://www.tpointtech.com/csharp-data-types#)

1. Class classname  
2. {  
3. // data member  
4. // data method  
5. }  

**C# Class Example**

Let us take an example to illustrate the Class in C#.

### Example

[](https://www.tpointtech.com/csharp-data-types#)[](https://www.tpointtech.com/csharp-data-types#)[](https://www.tpointtech.com/csharp-data-types#)

1. using System;     
2. namespace Example  
3. {  
4.     class Vehicle   // create a class  
5.     {  
6.         string car = "Innova";     
7.         public void DisplayCar()  
8.         {  
9.             Console.WriteLine(car);  
10.         }  
11.     }  
12.     class Program  
13.     {  
14.         static void Main(string[] args)  
15.         {  
16.             Vehicle myObj = new Vehicle();   
17.             myObj.DisplayCar();               
18.         }  
19.     }  
20. }  

**Output:**

Innova

**Explanation:**

In this example, we create a class named Vehicle. We create the DisplayCar() method to assign the value of cars. After that, we create the object myObj of the class Vehicle and finally call the method (DisplayCar) in the main function.

### 3) Union

In C#, a union is a user-defined data type that allows us to store multiple data items into a single entity, such as a [structure](https://www.tpointtech.com/c-sharp-structs).

**Syntax**

It has the following syntax:

[](https://www.tpointtech.com/csharp-data-types#)[](https://www.tpointtech.com/csharp-data-types#)[](https://www.tpointtech.com/csharp-data-types#)

1. union UnionName {  
2.     dataType1 member1;  
3.     dataType2 member2;  
4.     ...  
5. };  

**C# Union Example**

Let us take an example to illustrate the Union in C#.

### Example

[](https://www.tpointtech.com/csharp-data-types#)[](https://www.tpointtech.com/csharp-data-types#)[](https://www.tpointtech.com/csharp-data-types#)

1. using System;  
2. using System.Runtime.InteropServices;  
3. [StructLayout(LayoutKind.Explicit)]  
4. struct Union  
5. {  
6.     [FieldOffset(0)]  
7.     public int Value;  

8.     [FieldOffset(0)]  
9.     public float FloatValue;  
10. }  
11. class Program  
12. {  
13.     static void Main()  
14.     {  
15.         Union u = new Union();  
16.         u.Value = 42;  
17.         Console.WriteLine("Int: " + u.Value);  
18.         Console.WriteLine("Float: " + u.FloatValue);  
19.     }  
20. }  

**Output:**

int: 42
Float: 5.885454E-44

**Explanation:**

In this example, we hold the int, float value, but it can hold one value at a time. The main function demonstrates how a union overwrites earlier data. When a new data is assigned by sequentially assigning different values to the union variable u. Finally, it prints the output using the Console.WriteLine() function.

### 4) Enumeration

In C#, [enumeration](https://www.tpointtech.com/c-sharp-enum) is the user-defined data type that allows us to store the group of constant values. It is created using the enum keyword. It helps the code to be more readable and maintainability.

**Syntax**

It has the following syntax.

[](https://www.tpointtech.com/csharp-data-types#)[](https://www.tpointtech.com/csharp-data-types#)[](https://www.tpointtech.com/csharp-data-types#)

1. enum enum_variable{  
2. // string  
3. //string  
4. …  
5. }  

**C# Enumeration Example**

Let us take an example to illustrate the Enumeration data type in C#.

### Example

[](https://www.tpointtech.com/csharp-data-types#)[](https://www.tpointtech.com/csharp-data-types#)[](https://www.tpointtech.com/csharp-data-types#)

1. using System;  
2. class Program  
3. {  
4.     enum DaysOfWeek   // create the enum for days of week.  
5.     {  
6.         Sunday,  
7.         Monday,  
8.         Tuesday,  
9.         Wednesday,  
10.         Thursday,  
11.         Friday,  
12.         Saturday  
13.     }  
14.     static void Main()  
15.     {  
16.         DaysOfWeek today = DaysOfWeek.Wednesday;  
17.         Console.WriteLine("Today is " + today);  
18.     }  
19. }  

**Output:**

Today is Wednesday

**Explanation:**

In this example, we create the enum for the days of the week. After that, the main function declares and assigns the value, Wednesday assigns the todays value. Finally, we print the output using the Console.WriteLine function.

## Conclusion:

In conclusion, the C# data type is the key factor for any developer creating a software application. It is the main objective of the development. It is used to define the type of data that the variable can store. It also defines the memory size and range of the memory.