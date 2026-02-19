
In C#, a function is a block of code or set of instructions that can perform a specific task. It can be executed when calling the function. It is also known as a method. The method is defined within a class. It is used to improve the code readability, reusability and maintainability.

**Syntax**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-function#)[](https://www.tpointtech.com/c-sharp-function#)[](https://www.tpointtech.com/c-sharp-function#)

1. Class program  
2. {  
3. <access_specifier> <return_type> Method_Name()  
4. {  
5. // block of code  
6. }  
7. }  

Where,

- **access_specifier:** It defines the accessibility of the method.
- **Return_type:** It specifies the return type value that the function returns.
- **Method_Name:** It defines the name of the function.

### C# Example of Functions

Let us take an example to illustrate the functions in C#.

### Example

[](https://www.tpointtech.com/c-sharp-function#)[](https://www.tpointtech.com/c-sharp-function#)[](https://www.tpointtech.com/c-sharp-function#)

1. using System;  
2. class Program  
3. {  
4.     static void welcome()  // create the function   
5.     {  
6.         Console.WriteLine("Hello, welcome to TPoint tech.");  
7.     }  
8.     static void Main()  
9.     {  
10.         welcome();  // call the function  
11.     }  
12. }  

**Output:**

Hello, welcome to TPoint tech.

**Explanation:**

In this example, we create the static function named welcome. After that, we use the Console.WriteLine() function to print the output and then call the function inside the main method.

## Definition, Declaration, and Initialization of Function

Here, we will discuss how we can define, declare, and initialize a function in C#.

### 1) Function Declaration

In [C#](https://www.tpointtech.com/c-sharp-tutorial), a function declaration is the first step to creating the function. A function should be declared before calling it.

**Syntax:**

[](https://www.tpointtech.com/c-sharp-function#)[](https://www.tpointtech.com/c-sharp-function#)[](https://www.tpointtech.com/c-sharp-function#)

1. Return_Type FunctionName(Parameters);  

**Example:**

Let us take a simple example to declare the function in C#.

[](https://www.tpointtech.com/c-sharp-function#)[](https://www.tpointtech.com/c-sharp-function#)[](https://www.tpointtech.com/c-sharp-function#)

1. int sum(int a, int b);  

### 2) Function Definition:

In C#, the function definition is used to define the task or work of a function.

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-function#)[](https://www.tpointtech.com/c-sharp-function#)[](https://www.tpointtech.com/c-sharp-function#)

1. ReturnType FunctionName(Parameters)  
2. {  
3. // statements  
4. }  

**Function Definition Example:**

Let us take a simple example to illustrate the function definition in C#.

[](https://www.tpointtech.com/c-sharp-function#)[](https://www.tpointtech.com/c-sharp-function#)[](https://www.tpointtech.com/c-sharp-function#)

1. int sum(int a, int b)  
2. {  
3. int s;  
4. s = a+b;  
5. return s;  
6. }  

### Function Initialization

In C#, it refers to defining a function and then calling it with actual values.

**Syntax:**

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-function#)[](https://www.tpointtech.com/c-sharp-function#)[](https://www.tpointtech.com/c-sharp-function#)

1. FunctionName(arguments);  

**Example:**

Let us take a simple example to define the function initialization in C#.

Sum(20.30);

## Simple Function Example in C#

Let us take a simple example to illustrate function in C#.

### Example

[](https://www.tpointtech.com/c-sharp-function#)[](https://www.tpointtech.com/c-sharp-function#)[](https://www.tpointtech.com/c-sharp-function#)

1. using System;  

2. class Program  
3. {  
4.     // Simple function that adds two numbers  
5.     static void AddNumbers(int x, int y)  
6.     {  
7.         int sum = x + y;  
8.         Console.WriteLine("Sum: " + sum);  
9.     }  

10.     static void Main()  
11.     {  
12.         // Calling the function  
13.         AddNumbers(15, 25);  
14.     }  
15. }  

**Output:**

Sum: 40

**Explanation:**

In this example, we have taken AddNumbers method that contains two parameters. After that, it calculates the sum and displays the output using the Console.WriteLine() function. Finally, the method is called from the main() function that contains two argument 15 and 20.

## Needs of Functions

In C# language, there are several cases where functions are required. Some of them are as follows:

- It is utilized to reduce the length of the source code.
- It is utilized to find errors easily.
- It is utilized to call the block of code one or many times.
- It is utilized to make the program more understandable.

## Types of Function

The function can be called many times. It provides the modularity and reusability of code. There are mainly two types of functions in C#.  

- Pre-define Function
- User-define Function

Here, we will discuss these functions one by one.

### Pre-defined Function

In C# language, the predefined functions are the built-in functions that are already created by the compiler. It is also known as a library function. There are several pre-defined functions, such as Console.WriteLine(), Console.ReadLine(), Console.Clear(), Math.Abs(),  Math,Sqrt(), Math.Pow(), Math.Round(), etc.

**Syntax**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-function#)[](https://www.tpointtech.com/c-sharp-function#)[](https://www.tpointtech.com/c-sharp-function#)

1. ClassName.MethodName(arguments);  

Where,

- **ClaasName:** It represents the classname that stores the methods. The examples of ClassName are Console, Math, and String.
- **MethodName():** It has stored the predefined function. Examples of predefined functions are Sqrt, WriteLine, and ToUpper.
- **Arguments:** The arguments are used to pass the value to the methods.

**C# Example of Predefined Function**

Let us take an example to illustrate the predefined function in C#.

### Example

[](https://www.tpointtech.com/c-sharp-function#)[](https://www.tpointtech.com/c-sharp-function#)[](https://www.tpointtech.com/c-sharp-function#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {  
6.         double number = 25;  // Assign the value   
7.         double sq = Math.Sqrt(number); // Predefined function    
8.         Console.WriteLine("The square root of " + number + " is " + sq);  
9.     }  
10. }  

**Output:**

The square root of 25 is 5

**Explanation:**

In this example, we have taken the predefined function to calculate the square root of numbers. At first, we have taken the double type of data and assigned the value. After that, we use the Math.Sqrt() function to calculate the square root of a number. Finally, we use the Console.WriteLine() function to print the output.

### User-defined function

In C# language, a user-defined function refers to a function that is created by the programmer to perform a specific operation. We do not need any specific library or function to perform the task. It is utilized to improve the code reusability, readability, and maintainability.

**C# Example of User-defined Function**

Let us take an example to illustrate the user-defined function in C#.

### Example

[](https://www.tpointtech.com/c-sharp-function#)[](https://www.tpointtech.com/c-sharp-function#)[](https://www.tpointtech.com/c-sharp-function#)

1. using System;  
2. class Program  
3. {  
4.     static void Addition()  // user define function  
5.     {  
6.         int m = 10;  
7.         int n = 20;  
8.         int sum = m + n;  

9.         Console.WriteLine(" The Sum of the number is " + sum);  
10.     }  

11.     static void Main()  
12.     {  
13.         Addition();  // call the function  
14.     }  
15. }  

**Output:**

The Sum of the numbers is 30

**Explanation:**

In this example, we demonstrate the addition of two numbers using a user-defined function. First, define the function named **Add,** including two integer [data types](https://www.tpointtech.com/csharp-data-types). After that, it adds two numbers and displays the output by using the Console.WriteLine() function. Finally, we call the function in the main method to execute it.

## Types of User-defined Function

In C#, there are four types of user-defined functions

- Function with no Arguments and no return type
- Function with Arguments and no return type.
- Function with no Arguments and with a return type.
- Functions with Arguments and with Return Type.

Here, we will discuss the different user-defined function in C# one by one.

### Function with no Arguments and no return type

In C#, a function with no arguments and no return type is a user-defined function that does not take any parameters and has no return value to the function caller. We can use the function with **a void** return type.

**Syntax**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-function#)[](https://www.tpointtech.com/c-sharp-function#)[](https://www.tpointtech.com/c-sharp-function#)

1. void FunctionName()  // function with no arguments and no return type  
2. {  
3. // no return value  
4. Return;  
5. }  

**Function with no arguments and no return type Example in C#**

Let us take a simple example to illustrate the C# functions with no arguments and no return type.

### Example

[](https://www.tpointtech.com/c-sharp-function#)[](https://www.tpointtech.com/c-sharp-function#)[](https://www.tpointtech.com/c-sharp-function#)

1. using System;  
2. class Program  
3. {  
4.     // Void function with no arguments  
5.     static void Intro()  
6.     {  
7.         Console.WriteLine("Hello! Welcome to Tpoint tech");  
8.     }  
9.     static void Main()  
10.     {  
11.         Intro(); // Call the function  
12.     }  
13. }  

**Output:**

Hello! Welcome to Tpoint tech

**Explanation:**

In this example, we have created a function with no arguments and no return type named **Intro,** and then we use the Console.WriteLine() function to display the output. After that, we call the function in the main method to execute it.

### Function with Arguments and no return type

In C#, a function with arguments and no return type is a user-defined function that takes parameters but does not return a value to the calling function.

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-function#)[](https://www.tpointtech.com/c-sharp-function#)[](https://www.tpointtech.com/c-sharp-function#)

1. void FunctionName (type1 argument1, type2 argument2)  
2. {  
3. // program  
4. return;  
5. }  

**Function with Arguments and no return type Example in C#**

Let us take a simple example to illustrate the C# functions with arguments and no return type.

### Example

[](https://www.tpointtech.com/c-sharp-function#)[](https://www.tpointtech.com/c-sharp-function#)[](https://www.tpointtech.com/c-sharp-function#)

1. using System;  
2. class Program  
3. {  
4.     static void Sum(int m, int n)  // create function as arguments but no return type  
5.     {  
6.         int s = m * n;  // multiply two numbers   
7.         Console.WriteLine("The Multiplication is: " +s);   
8.     }  
9.     static void Main(string[] args)  
10.     {  
11.         Sum(5, 10);   // calling function  
12.     }  
13. }  

**Output:**

The sum is: 50

**Explanation:**

In this example, we have taken a sum function that takes two integer arguments, multiplies them, and displays the result. After that, the method is called from the main() function with the values 5 and 10. Finally, it displays the output using the Console.WriteLine() function.

### Function with no Arguments and with Return Type

In C#, a function with no arguments and with a return type is a user-defined function that does not take any parameters but has a return type value to the function caller.

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-function#)[](https://www.tpointtech.com/c-sharp-function#)[](https://www.tpointtech.com/c-sharp-function#)

1. return_type FunctionName()  
2. {  
3. // block of code  
4. return value;  
5. }  

**Function with no Arguments and with Return Type Example**

Let us take a simple example to illustrate the C# functions with no arguments but with have return type.

### Example

[](https://www.tpointtech.com/c-sharp-function#)[](https://www.tpointtech.com/c-sharp-function#)[](https://www.tpointtech.com/c-sharp-function#)

1. using System;  
2. class Program  
3. {  
4.     // no arguments with string returns type function  
5.     static string GetWelcomeMessage()  
6.     {  
7.         return "Welcome to Tpoint tech!";  
8.     }  
9.     static void Main(string[] args)  
10.     {  
11.         // Call the method and store the returned string  
12.         string message = GetWelcomeMessage();  
13.         Console.WriteLine(message);  
14.     }  
15. }  

**Output:**

Welcome to Tpoint tech!

**Explanation:**

In this example, we have created the function with no arguments and a string return type value named **GetWelcomeMessage.** After that, call the method in the main function and store the string value. Finally, use the Console.WriteLine() to display the output.

### Functions with Arguments and with Return Type

In C#, a function with arguments and a return type is a user-defined function that takes the parameters and returns the type value to the function caller.

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-function#)[](https://www.tpointtech.com/c-sharp-function#)[](https://www.tpointtech.com/c-sharp-function#)

1. return_type FunctionName(type1 argument1, type2 arguments2, … typeN argumentN)  
2. {  
3. // block of code  
4. return value;  
5. }  

**Functions with Arguments and with Return Type Example**

Let us take a simple example to illustrate the C# functions with no arguments but have a string return type.

### Example

[](https://www.tpointtech.com/c-sharp-function#)[](https://www.tpointtech.com/c-sharp-function#)[](https://www.tpointtech.com/c-sharp-function#)

1. using System;  
2. class Program  
3. {  
4.     // create a function with an argument and with a return type  
5.     static int Multiply(int x, int y)  
6.     {  
7.         return x * y;  
8.     }  
9.     static void Main(string[] args)  
10.     {  
11.         // Call the method with arguments and store the result  
12.         int result = Multiply(3, 5);  
13.         Console.WriteLine("The product is: " + result);  
14.     }  
15. }  

**Output:**

The product is 15

**Explanation:**

In this example, we have created a function with arguments and a string return integer type value named **Multiply.** After that, call the method in the main function and store the string value. Finally, use the Console.WriteLine() to display the output. 

## Function Parameter in C#

There are three types of function parameters in C#. These are as follows.

- Pass-by value
- Pass-by reference
- Pass-by Pointer

### Pass by Value

In C#, the pass-by-value is used to pass a copy of the original value of the function rather than a reference.

**Pass by Value Example in C#**

Let us take a simple example to illustrate the pass by value function parameter in C#.

### Example

[](https://www.tpointtech.com/c-sharp-function#)[](https://www.tpointtech.com/c-sharp-function#)[](https://www.tpointtech.com/c-sharp-function#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {  
6.         int number = 5; // Declare and initialize a variable  
7.         Console.WriteLine("Before function call: " + number);   
8.         ChangeValue(number); // Pass the variable to the function (by value)  
9.         Console.WriteLine("After function call: " + number);   
10.     }  
11.     static void ChangeValue(int num)  
12.     {  
13.         num = 10; // Change the value of the parameter inside the method  
14.         Console.WriteLine("Inside method: " + num);   
15.     }  
16. }  

**Output:**

Before function call: 5
Inside method: 10
After function call: 5

**Explanation:**

In this example, we demonstrate the pass-by-value parameter. We have taken the ChangeValue method that receives a copy of the variable number that changes its value to 10, and display the output using the Console.WriteLine() function. However, the actual number in the main() function does not change because changes to the parameter inside the method don't affect the original value.

### Pass by Reference

In C#, the pass by reference is a function that receives the actual memory address of the arguments instead of a copy because any changes made inside the function directly affect the original value.

**Pass by Reference Example in C#**

Let us take a simple example to illustrate the Pass-by-reference function parameter in C#.

### Example

[](https://www.tpointtech.com/c-sharp-function#)[](https://www.tpointtech.com/c-sharp-function#)[](https://www.tpointtech.com/c-sharp-function#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {  
6.         int number = 5;  
7.         Console.WriteLine("Before: " + number);  
8.         Change(ref number); // Pass by reference  
9.         Console.WriteLine("After: " + number);    
10.     }  
11.     static void Change(ref int x)  
12.     {  
13.         x = 10; // Changes the original variable  
14.     }  
15. }  

**Output:**

Before: 5
After: 10

**Explanation:**

In this example, we demonstrate the pass-by-reference using the ref keyword in C#. After that, the variable number is passed to the Change method by reference, which allows the method to modify the original variable's value.

### Pass by Pointer

In C#, we pass the reference or address to the variable in a pointer. The function modifies the value stored at a given address.

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-function#)[](https://www.tpointtech.com/c-sharp-function#)[](https://www.tpointtech.com/c-sharp-function#)

1. using System;  
2. class ClassName  
3. {  
4.     static unsafe void Main()  
5.     {  
6.         DataType variableName = value;  
7.         Console.WriteLine("Before: " + variableName);  
8.         FunctionName(&variableName);  
9.         Console.WriteLine("After: " + variableName);  
10.     }  
11.     static unsafe void FunctionName(DataType* pointerName)  
12.     {  
13.         *pointerName = newValue;  
14.     }  
15. }  

## Advantages of functions in C#

Several advantages of functions in C# are as follows:

- **Code Reusability:** The main advantage of a function is code reusability. It means that create the function in C#, we can call it many times. Therefore, we don't need to write the same code again and again.
- **Code Optimization:** The function is used to make the code optimized. Suppose we have to check 10 numbers, whether it is even or not. Without using the function, we need to write the even number logic 10 times. Therefore, there is a repetition of code. However, if we use a function, we need to write the logic at once, and we can reuse it several times.
- **Improved Readability and Maintainability:** The programs are more efficient and readable it is easy for the programmer to maintain the code.
- **Debugging and Testing Made Easier:** The function assists debugging and testing because the program error becomes confined to a single function.

## Conclusion

In conclusion, the C# function is the key factor for any programmer to create a software application. It is the main objective for the development. It is the set of instructions that can perform a specific task and is used to make the code optimised and easy to maintain the code.