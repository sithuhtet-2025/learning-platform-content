
The C# programming language has an essential feature known as generics. It enables us to create classes, methods, structures, delegates, and interfaces with a type placeholder. These placeholders are changed by the compiler with the specified type during compilation, which guarantees type safety and also improves performance.

![C# Generics](https://images.tpointtech.com/csharp/images/c-sharp-generics.png)

Generics are mainly used to create general-purpose, reusable classes and methods that work with different data types without code duplication. We need to use angle brackets (<>) to define a generic class. The angle brackets are used to declare a class or method as a generic type and accept multiple type parameters.

### Syntax:

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-generics#)[](https://www.tpointtech.com/c-sharp-generics#)[](https://www.tpointtech.com/c-sharp-generics#)

1. public returnType MethodName<T>(T parameter)  
2. {  
3.     // Method body  
4. }  

In this syntax,

- **T:** It represents a generic type parameter.
- **returnType:** It specifies the method's return type.
- **MethodName:** It represents the name of the method.

### C# Generic Example

Let us take an example to illustrate the generic in C#.

### Example

[](https://www.tpointtech.com/c-sharp-generics#)[](https://www.tpointtech.com/c-sharp-generics#)[](https://www.tpointtech.com/c-sharp-generics#)

1. using System;  
2. class Tpoint  
3. {  
4.     // Generic method  
5.     public static void Display<T>(T value)  
6.     {  
7.         Console.WriteLine("The value is " + value);  
8.     }  
9.     static void Main()  
10.     {  
11.         // Calling Generic method  
12.         Display<int>(100);            
13.         Display<string>("John");     
14.         Display<double>(3.14);        
15.         Display<bool>(true);          
16.     }  
17. }  

**Output:**

The value is 100
The value is John
The value is 3.14
The value is True

**Explanation:**

In this example, we have taken the generic method named Display(), which can accept any type of value, such as int, string, double, or bool. After that, we call the Display() method, the compiler automatically replaces T with the actual type value, and prints the result.

## Types of Generics in C#

Generic allows the creation of flexible, reusable, and type-safe code. There are several ways to use generics in C#. Some of them are as follows:

![C# Generics](https://images.tpointtech.com/csharp/images/c-sharp-generics2.png)

Here, we will discuss these generics one by one.

### 1) Generic Class

A generic class is an important feature in C# that allows us to define type-safe data structures or classes that can run on different data types. The actual data type is specified when the class is instantiated, which provides greater flexibility and code reusability.

**C# Generic Class Example**

Let us take an example to illustrate the generic class in C#.

### Example

[](https://www.tpointtech.com/c-sharp-generics#)[](https://www.tpointtech.com/c-sharp-generics#)[](https://www.tpointtech.com/c-sharp-generics#)

1. using System;  
2. // Generic class  
3. class Box<T>  
4. {  
5.     public T item;  
6. }  
7. class Program  
8. {  
9.     static void Main(string[] args)  
10.     {  
11.         Box<int> b = new Box<int>();  
12.         b.item = 5;  
13.         Console.WriteLine("Integer: " + b.item);  
14.         Box<string> bb = new Box<string>();  
15.         bb.item = "Hello";  
16.         Console.WriteLine("String: " + bb.item);  
17.     }  
18. }  

**Output:**

Integer: 5
String: Hello

**Explanation:**

In this example, we have taken a class named Box<T>, where T can be any data type. In the main method, we create two instances of this generic class of integer and string type. The first instance is b, which holds the integer value, and the second instance is bb, which holds the string value.

### 2) Generic Method

In C#, a generic method is a method that is defined with multiple type parameters, which enables it to operate with different data types in a type-safe manner without code duplication. It is useful when we want to write a method that can handle different types without affecting performance or type safety.

**Example of a Generic Method in C#**

Let's take an example to illustrate the generic method in C#.

### Example

[](https://www.tpointtech.com/c-sharp-generics#)[](https://www.tpointtech.com/c-sharp-generics#)[](https://www.tpointtech.com/c-sharp-generics#)

1. using System;  
2. public class TPoint  
3. {  
4.     // Generic Method  
5.     public static void Swap<T>(ref T a, ref T b)  
6.     {  
7.         T tmp = a;  
8.         a = b;  
9.         b = tmp;  
10.     }  
11.     public static void Main()  
12.     {  
13.         int m = 5, n = 10;  
14.         Console.WriteLine("The values before swapping are: m = " + m + ", n = " + n);  
15.         Swap(ref m, ref n);  
16.         Console.WriteLine("After swapping: m = " + m + ", n = " + n);  
17.         string f = "TPoint", s = "Tech";  
18.         Console.WriteLine("\nBefore swapping: first = " + f + ", second = " + s);                        Swap(ref f, ref s);  
19.         Console.WriteLine("After swapping: first = " + f + ", second = " + s);  
20.     }  
21. }  

**Output:**

The values before swapping are: m = 5, n = 10
After swapping: m = 10, n = 5

Before swapping: first = TPoint, second = Tech
After swapping: first = Tech, second = Tpoint

**Explanation:**

In this example, we have taken a class named TPoint that contains the swapping<T> method, which takes two parameters by reference using the ref keyword. The method works to swap the values using a temporary variable. In the main method, the program first swaps two integers m and n, and prints their values before and after swapping. After that, it swaps the two strings f and s, and shows the output.

### 3) Generic Interface

In C#, a generic interface enables us to define a contract with multiple type parameters, which makes it flexible to work with various data types. It uses a type parameter, which avoids code duplication for multiple data types. It ensures type safety and code reusability.

**C# Generic Interface Example**

Let's take an example to illustrate a generic interface in C#.

### Example

[](https://www.tpointtech.com/c-sharp-generics#)[](https://www.tpointtech.com/c-sharp-generics#)[](https://www.tpointtech.com/c-sharp-generics#)

1. using System;  
2. // Generic interface  
3. public interface ICalc<m>  
4. {  
5.     void square_root(m value);  
6. }  
7. public class dCalc : ICalc<double>  
8. {  
9.     public void square_root(double v)  
10.     {  
11.         double result = v * v;  
12.    Console.WriteLine("The square of a number is " + result);  

13.     }  
14. }  
15. public class TPoint  
16. {  
17.     public static void Main()  
18.     {  
19.         ICalc<double> c = new dCalc();  
20.         c.square_root(10);   
21.     }  
22. }  

**Output:**

The square of a number is 100

**Explanation:**

In this example, we have taken an interface ICalc<m> that defines a method named square_root that takes a parameter of a generic type m. After that, it creates a class dCalc and implements the interface using the type double. In the square_root method, it calculates the square root of the number. In the main method, we create an object using the interface ICalc<double>, and then call the square_root method and print the output.

### 4) Generic Delegates

In C#, a generic delegate is a type of delegate that is defined with multiple type parameters, which enables it to work with any data type. If we don't want to create delegates for different data types, we can also define a generic delegate and reuse it with any type parameter.

**C# Generic Delegate Example**

Let us take an example to illustrate the generic delegates in C#.

### Example

[](https://www.tpointtech.com/c-sharp-generics#)[](https://www.tpointtech.com/c-sharp-generics#)[](https://www.tpointtech.com/c-sharp-generics#)

1. using System;  
2. namespace TPoint  
3. {         
4.     // Generic delegate   
5.     public delegate T Op<T>(T x, T y);  
6.     class tech  
7.     {  
8.         // Method   
9.         static int add( int p, int q )  
10.         {  
11.             return p + q;  
12.         }  
13.         static string addchar( string p, string q )  
14.         {  
15.             return p + q;  
16.         }  
17.         static void Main(string[] args)  
18.         {  
19.             Op<int> o = add;  
20.             Console.WriteLine("The Addition of integers: " + o(10, 20) );  
21.             Op<string> Os = addchar;  
22.             Console.WriteLine("The Concatenation of strings: " + Os("Hello, ", "World!") );  
23.         }  
24.     }  
25. }  

**Output:**

The Addition of integers: 30
The Concatenation of strings: Hello, World!

**Explanation:**

In this example, we have taken a generic delegate Op<T> that can work with different parameters. After that, we create methods to add integers and join strings. In the main method, the delegate is used with an integer to add numbers and with a string to concatenate text.

### 5) Generic Collection

In C#, a generic collection is a special type of collection that is used to store any data type safely. These collections are defined in the System.Collections.Generic namespace. It is generally used in several collections, such as List<T>, Dictionary<TKey, TValue>, Queue<T>, Stack<T>, and many others.

**C# Generic Collection Example**

Let's take an example to illustrate the generic collection in C#.

### Example

[](https://www.tpointtech.com/c-sharp-generics#)[](https://www.tpointtech.com/c-sharp-generics#)[](https://www.tpointtech.com/c-sharp-generics#)

1. using System;     
2. using System.Collections.Generic;  
3. class TPoint  
4. {  
5.     static void Main()  
6.     {  
7.         List<int> x = new List<int>();  
8.         x.Add(8);  
9.         x.Add(16);  
10.         x.Add(32);  
11.         Dictionary<string, int> a = new Dictionary<string, int>();  
12.         a.Add("Michael", 45);  
13.         a.Add("Bravo", 50);  
14.         a.Add("Johnson", 35);  
15.         Console.WriteLine("The numbers are: ");  
16.         foreach (int nn in x)  
17.         {  
18.             Console.WriteLine(nn);  
19.         }  
20.         Console.WriteLine("The ages are: ");  
21.         foreach (var item in a)  
22.         {  
23.             Console.WriteLine(item.Key + ": " + item.Value);  
24.         }  
25.     }  
26. }  

**Output:**

The numbers are:
8
16
32
The ages are:
Michael: 45
Bravo: 50
Johnson: 35

**Explanation:**

In this example, we have taken a List<int> to store integer values, and a Dictionary <string, int> to store names with their ages. After that, we take a foreach loop to print their value in a type-safe manner.

## Advantages of using Generics in C#

There are several advantages of generics in C#. Some of the main advantages are as follows.

Here, we will discuss these advantages one by one.

**1) Code Reusability**

In C#, generics provide code reusability by enabling us to define a single method, class, or interface that can work with different data types.

**2) Type Safety**

Generics provide better type safety by ensuring that only the specified data type is used. It helps to find errors at compile time instead of runtime, which makes the code more reliable and robust.

**3) Performance**

Generic type provides better performance compared to non-generic types. It reduces several unnecessary operations, such as boxing, unboxing, and explicit type casting.

**4) Support for Multiple Type Parameters**

In C#, Generic classes and methods can accept more than one type of parameter. It offers greater flexibility, a more versatile, and reusable code structure.

**5) Collections**

In C#, generics can be used in different collections, such as List<T>, Dictionary<T, U>, etc. It provides type-safe and efficient data structures.

## Conclusion

In conclusion, C# generics are an important feature that enables us to define classes and methods with a type placeholder for data types. The compiler replaces these placeholders with the specified type during compile time. It allows us to define a single method or class that can be reused with different data types. With the use of generic classes, methods, interfaces, delegates, and collections, we can create applications that are more efficient, flexible, and maintainable.