
In the C# programming language, a "Hello, world!" program is a simple program that prints only "Hello, world!". This program is commonly used to introduce beginners to a new programming language. With this simple program, beginners can understand how the [C# programming language](https://www.tpointtech.com/c-sharp-tutorial) works. The Hello World program can be written in multiple ways. Let's see the top 4 ways to create a simple C# example:

- Simple Example
- Using System
- Using a public modifier
- Using namespace

Here, we will discuss these four ways to print Hello World one by one.

## C# Simple Example

Let us take an example to print Hello World in a simple way.

### Example

[](https://www.tpointtech.com/c-sharp-example#)[](https://www.tpointtech.com/c-sharp-example#)[](https://www.tpointtech.com/c-sharp-example#)

1. class Tpoint    
2.     {    
3.         static void Main(string[] args)    
4.         {    
5.             System.Console.WriteLine("Hello World!");    
6.         }    
7.     }    

**Output:**

Hello World!

## Working of C# Program

There are several main concepts that need to be learn while writing a C# program. By using the above program, we will understand the working of a C# program.

- **class:** It is used to represent a keyword that is used to define a class.
- **ClassName (Program) :**It is used to represent the name of the class. A class is a blueprint or template from which objects are created. It can have data members and methods.
- **static:** It is a keyword that means that the object is not required to access static members. Therefore, it saves memory.
- **void:** It is the return type of the method. It does not return any value. In such a case, a return statement is not required.
- **Main:** It is used to represent the method name. It is the entry point for any C# program. Whenever we run the C# program, the Main() method is called first before any other method. It represents the startup of the program.
- **string[] args:** It is used for command-line arguments in the C# programming language. While running the C# program, we can pass values. These values are known as arguments that we can use in the program.
- **Console.WriteLine("Hello World!"):** Here, System is used to represent the namespace, Console is the class defined in the System namespace, and the WriteLine() is the static method of the Console class that is used to write the text on the console.

## C# Hello World Program Using System

In the C# programming language, we can use the using directive that enables us to access any class inside a namespace by defining its complete qualified name. [Namespace](https://www.tpointtech.com/c-sharp-namespaces) for accessing any class of this namespace. If we use the "using System;" at the start of the program, we can use the Console class without specifying System.Console.

Let's take an example to print Hello World by using System in C#.

### Example

[](https://www.tpointtech.com/c-sharp-example#)[](https://www.tpointtech.com/c-sharp-example#)[](https://www.tpointtech.com/c-sharp-example#)

1. using System;    
2.     class Tpoint    
3.     {    
4.         static void Main(string[] args)    
5.         {    
6.             Console.WriteLine("Hello World!");    
7.         }    
8.     }   

**Output:**

Hello World!

**Explanation:**

In this example, we have taken the using System; directive that helps to access the Console class directly without specifying System.Console. In the Main() method, we print "Hello World!" on the console using the Console.Writeline function.

## C# Hello World Example Using public modifier

In the C# language, we can also specify the public modifier before the class and the Main() method. It can be accessed from outside the class, and make sure that the program's entry point is visible to the runtime.

Let us take an example to print Hello World by using the public modifier in C#.

### Example

[](https://www.tpointtech.com/c-sharp-example#)[](https://www.tpointtech.com/c-sharp-example#)[](https://www.tpointtech.com/c-sharp-example#)

1. using System;    
2.     public class Tpoint    
3.     {    
4.         public static void Main(string[] args)    
5.         {    
6.             Console.WriteLine("Hello World!");    
7.         }    
8.     }    

**Output:**

Hello World!

**Explanation:**

In this example, we have taken both the Tpoint class and the Main() method as public. It means that they can be accessed from outside the class, which is very helpful for larger applications.

## C# Hello World Example Using namespace

In the C# programming language, we can create classes inside a namespace to group related classes together. It is used to categorize classes, organize code, and avoid naming conflicts, which helps to make the program easier to maintain and understand.

Let us take an example to print Hello World using a namespace in C#.

### Example

[](https://www.tpointtech.com/c-sharp-example#)[](https://www.tpointtech.com/c-sharp-example#)[](https://www.tpointtech.com/c-sharp-example#)

1. using System;    
2. namespace ConsoleApplication1    
3. {    
4.     public class Tpoint    
5.     {    
6.         public static void Main(string[] args)    
7.         {    
8.             Console.WriteLine("Hello World!");    
9.         }    
10.     }    
11. }    

**Output:**

Hello World!

**Explanation:**

In this example, we have taken a class Tpoint that is defined inside the namespace ConsoleApplication1. After that, we declare the Main() method as public and show the "Hello World!" using the Console.WriteLine() function.

## Conclusion

In conclusion, the Hello World Program in C# is a simple example that helps beginners to get started with the C# language. In this article, we have covered the basic structure of a C# program, such as namespaces, [classes](https://www.tpointtech.com/c-sharp-object-and-class), methods, and Console.WriteLine() method is used to print the output.