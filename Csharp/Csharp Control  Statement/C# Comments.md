
In C#, comments are a pieces of text in programming that is the non-executable code line. It allows the programmers to explain their code in their own words. Programmers help document their work by providing descriptions of [variables](https://www.tpointtech.com/csharp-variables), methods, [classes](https://www.tpointtech.com/c-sharp-object-and-class), or particular code segments. The compiler ignores comments, so they have no impact on how the program executes. In [C#](https://www.tpointtech.com/c-sharp-tutorial), comments can be defined via double forward slashes (//).

### C# Simple Comments Example

Let us take a simple example to illustrate the comments in C# programming.

### Example

[](https://www.tpointtech.com/c-sharp-comments#)[](https://www.tpointtech.com/c-sharp-comments#)[](https://www.tpointtech.com/c-sharp-comments#)

1. using System;  
2. public class program  
3. {  
4.     public static void Main(string[] args)     
5.     {  
6.         // Single line comment is used like this  
7.         /* multi line comment is used like this*/  
8.         Console.WriteLine ("Welcome to Tpoint tech");  
9.     }  
10. }  

**Output:**

Welcome to Tpoint tech

**Explanation:**

In this example, we represent the single-line and multi-line comments in C#. These lines cannot be compiled by the Compiler. After that, we use the Console.WriteLine() function to print the program.

## Types of Comments in C#

There are three types of comments in C#.

- Single-line Comments
- Multi-line Comments
- XML Comments

Here, we will discuss these comments one by one.

### Single-line Comments

In C#, single-line comments are used to explain the short description of the line of code. It begins with two forward slashes (//). The compiler ignores any text between forward slash (//). These are commonly used during testing or debugging to highlight specific code segments, provide brief explanations, or temporarily disable particular lines of code.

**Syntax**

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-comments#)[](https://www.tpointtech.com/c-sharp-comments#)[](https://www.tpointtech.com/c-sharp-comments#)

1. // This is a single-line comment that can be used like this  

**C# Single-line Comments Example**

Let us take an example to illustrate the single-line comments in C#.

### Example

[](https://www.tpointtech.com/c-sharp-comments#)[](https://www.tpointtech.com/c-sharp-comments#)[](https://www.tpointtech.com/c-sharp-comments#)

1. using System;  

2. class AdditionProgram  
3. {  
4.     static void Main()  
5.     {  
6.         // Declare two integer variables  
7.         int x, y, sum;  

8.         // Take input from the user  
9.         Console.Write("Enter the first number: ");  
10.         x = Convert.ToInt32(Console.ReadLine());  

11.         Console.Write("Enter the second number: ");  
12.         y = Convert.ToInt32(Console.ReadLine());  

13.         // Perform addition  
14.         sum = x + y;  

15.         // Display the result  
16.         Console.WriteLine("The sum of {0} and {1} is {2}", x, y, sum);  
17.     }  
18. }  

**Output:**

Enter the first number: 15
Enter the second number: 20
The sum of 15 and 20 is 35

**Explanation:**

In this example, we demonstrate how to write the single-line comment in C#. It starts with two forward slashes (//). In this example, we take three integer inputs x, y, and sum. Finally, the output is displayed using the Console.WriteLine() function.

### Multi-line Comments

In C#, multi-line comments are used to provide detailed descriptions of the line of code. It starts with **/*** and ends with ***/.** The compiler ignores any text between /* and */. Any content written between these markers is completely disregarded by the compiler and has no behavior on how the program executes. Multi-line comments are helpful for adding documentation, explaining complex logic, or temporarily disabling several lines of code for debugging.

**Syntax**

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-comments#)[](https://www.tpointtech.com/c-sharp-comments#)[](https://www.tpointtech.com/c-sharp-comments#)

1. /* This is a multi-line comment which can be used like this */  

**C# multi-line Comments Example**

Let us take an example to illustrate the multi-line comments in C#.

### Example

[](https://www.tpointtech.com/c-sharp-comments#)[](https://www.tpointtech.com/c-sharp-comments#)[](https://www.tpointtech.com/c-sharp-comments#)

1. using System;  

2. class FactorialProgram  
3. {  
4.     static void Main()  
5.     {  
6.         int num, fact = 1;  

7.         Console.Write("Enter a number: ");  
8.         num = Convert.ToInt32(Console.ReadLine());  

9.         /* This given loop calculates the factorial of the number. 
10.            It starts from 1 and multiplies up to the given number. 
11.            For example, if number = 6 factorial = 1*2*3*4*5*6 = 720. */  
12.         for (int i = 1; i <= num; i++)  
13.         {  
14.             fact *= i;  
15.         }  

16.         /* Displaying the result to the user */  
17.         Console.WriteLine("Factorial of {0} is {1}", num, fact);  
18.     }  
19. }  

**Output:**

Enter a number: 6
Factorial of 6 is 720

**Explanation:**

In this example, we demonstrate how to write the multi-line comment in C#. Here, the program prompts the user to enter the integer and calculates its factorial using a for loop. Multi-line comments are used to explain the logic and steps clearly within the code. After that, the Console.WriteLine() function is used to print the output.

### XML Comments

In C#, XML comments are a special type of comment in C# that is used to create the code documentation by adding the xml elements. It provides the IntelliSense information and improves the code readability. It starts with **the ///** symbol. The compiler ignores any text following the /// symbol.

**Syntax**

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-comments#)[](https://www.tpointtech.com/c-sharp-comments#)[](https://www.tpointtech.com/c-sharp-comments#)

1. /// This is the XML Comments which can be used like this  

**C# XML Comments Example**

Let us take an example to illustrate the XML comments in C#.

### Example

[](https://www.tpointtech.com/c-sharp-comments#)[](https://www.tpointtech.com/c-sharp-comments#)[](https://www.tpointtech.com/c-sharp-comments#)

1. using System;  
2. public class Number  
3. {  
4.     /// <summary>  
5.     /// Multiplication of two numbers.  
6.     /// <param name="s">The first integer value.</param>  
7.     /// <param name="p">The second integer value.</param>  
8.     public int Multiply(int s, int p)  
9.     {  
10.         return s * p;  
11.     }  
12.     public static void Main()  
13.     {  
14.         Number num = new Number();  
15.         Console.WriteLine("The product of two numbers is " + num.Multiply(3, 5));  
16.     }  
17. }  

**Output:**

The product of two numbers is 15

**Explanation:**

In this example, we demonstrate how to write the XML comments in C#. The compiler ignores any text that starts with /// symbol. First, we create a class named **Number** and a function named **Multiply** that takes two integer values, a and b, and returns their product. After that, we create the object of the class in the main function and print the output using the Console.WriteLIne() function.

## Advantage of C# Comments:

There are several advantages of comments in C#. Some of them are as follows:

- In C#, comments improve the readability and maintainability of code.
- It allows the compiler to ignore a piece of code while debugging.
- It is very helpful for the testing team to provide the comments line in the code.
- It helps to determine the utilization of the specific methods, functions, and constructors in the program.

## Conclusion

In C#, comments are the key factor for any programmers to explain their code. It is very beneficial to understand the code. It allows the compiler to ignore the piece of code while debugging. It enhances the readability and maintainability of code.