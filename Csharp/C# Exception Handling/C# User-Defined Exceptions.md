In the C# programming language, a custom exception is a user-defined class that inherits from the built-in System.Exception class. It allows us to create our own specific error types to handle special situations in the program. A common use case for custom exceptions is input validation.

![C# User-Defined Exceptions](https://images.tpointtech.com/csharp/images/c-sharp-user-defined-exceptions.png)

For instance, we can create an InvalidAgeException to throw an error when a user enters an age below 18, which may be invalid in certain business rules, such as age-restricted registration.

Custom exceptions help us represent the specific errors in code. It makes it easier to understand and fix problems by giving clear and meaningful messages. It allows us to handle the different errors in different ways, which helps to make the code cleaner and more organized.

## Creating a Custom Exception in C#

In the [C# programming language](https://www.tpointtech.com/c-sharp-tutorial), custom exceptions are created by defining a new class that inherits from [System.Exception](https://www.tpointtech.com/c-sharp-systemexception) class or any of its derived types. It allows us to handle application-specific errors in a more meaningful and structured way.

### Syntax:

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-user-defined-exceptions#)[](https://www.tpointtech.com/c-sharp-user-defined-exceptions#)[](https://www.tpointtech.com/c-sharp-user-defined-exceptions#)

1. public class MyCustomException : Exception  
2. {  
3.     public MyCustomException()  
4.     {  
5.     }  
6.     public MyCustomException(string message)  
7.         : base(message)  
8.     {  
9.     }  
10.     public MyCustomException(string message, Exception innerException)  
11.         : base(message, innerException)  
12.     {  
13.     }  
14. }  

In the given syntax, the MyCustomException inherits from System.Exception that includes three constructors, which enables us to specify a custom error message and optionally pass an inner exception.

## Handling Custom Exceptions

In C#, custom exceptions can be handled in the same manner as built-in exceptions using a [try-catch](https://www.tpointtech.com/c-sharp-try-catch) block. When a custom exception is thrown in the program, it can be caught in a catch block that mainly targets the custom exception type. It enables the developers to give more expressive and specific error handling for different cases.

### Syntax:

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-user-defined-exceptions#)[](https://www.tpointtech.com/c-sharp-user-defined-exceptions#)[](https://www.tpointtech.com/c-sharp-user-defined-exceptions#)

1. try  
2. {  
3.     CustomExceptionDemo demo = new CustomExceptionDemo();  
4.     demo.DoSomething();  
5. }  
6. catch (CustomException ex)  
7. {  
8.     Console.WriteLine($" Custom Exception Caught: {ex.Message} " );  
9.     // Handle the exception or log it  
10. }  

In this syntax, we catch the CustomException that can be thrown by the DoSomething() method. It allows us to handle the specific error scenario in a controlled way, such as logging the error or providing a user-friendly message.

## C# Custom Exception Handling Example

Let us take an example to illustrate the custom exception in C#.

### Example

[](https://www.tpointtech.com/c-sharp-user-defined-exceptions#)[](https://www.tpointtech.com/c-sharp-user-defined-exceptions#)[](https://www.tpointtech.com/c-sharp-user-defined-exceptions#)

1. using System;  
2. public class InvalidAgeException : Exception  
3. {  
4.     // default constructor  
5.     public InvalidAgeException() : base("Age is not valid.")  
6.     {  
7.     }  
8.     // Constructor with custom message  
9.     public InvalidAgeException(string message) : base(message)  
10.     {  
11.     }  
12. }  
13. public class TestUserDefinedException  
14. {  
15.     static void Validate(int age)  
16.     {  
17.         if (age < 18)  
18.         {  
19.             throw new InvalidAgeException("Sorry, Age must be at least 18 years. ");  
20.         }  
21.     }  
22.     public static void Main(string[] args)  
23.     {  
24.         try  
25.         {  
26.             Validate(15);  
27.         }  
28.         catch (InvalidAgeException m)  
29.         {  
30.             Console.WriteLine("Exception caught: " + m.Message);  
31.         }  
32.         Console.WriteLine("Program continues... ");  
33.     }  
34. }  

**Output:**

Exception caught: Sorry, Age must be at least 18 years.
Program continues...

**Explanation:**

In this example, we create a custom exception called InvalidAgeException, which is thrown when the age is less than 18. If the age is less than 18, it throws exceptions with the message "Sorry, Age must be at least 18 years". Inside the main() method, the exception is handled using a try-catch block, which allows it to run smoothly without crashing.

## Why Use Custom Exception in C#

In the C# programming language, custom exceptions can be utilized in several cases. Some of them are as follows:

- **Clarity**

In the C# programming language, a custom exception enables us to define a meaningful error message that can simply define the accurate problem.

- **Error Handling**

In C#, if we create specific exception types, we can find and handle errors differently according to type. It can help to make more reliable and organized code.

- **Maintainability**

In C#, when the custom exception uses the centralized error-handling logic, it makes the code cleaner and maintainable.

- **Documentation**

Custom exception in C# performs as self-documenting code. By doing this, we can easily understand the main purpose of an exception and when it should be thrown.

## Types of Exceptions in C#

In C#, there are mainly two types of exceptions as follows.

- System Exception
- Application Exception

![C# User-Defined Exceptions](https://images.tpointtech.com/csharp/images/c-sharp-user-defined-exceptions2.png)

Here, we will discuss these custom exceptions one by one.

## System Exception

In the C# programming language, the System.Exception is the base class for all exceptions in the .NET Framework. An exception represents an unwanted or unexpected event that occurs at runtime and affects the normal flow of a program. The examples of System Exceptions include NullReferenceException, IndexOutOfRangeException, DivideByZeroException, and FileNotFoundException. We can also create custom exceptions by inheriting from this class.

### C# System-defined Exception Example

Let us take a simple example to demonstrate how a system-defined exception works in C#.

### Example

[](https://www.tpointtech.com/c-sharp-user-defined-exceptions#)[](https://www.tpointtech.com/c-sharp-user-defined-exceptions#)[](https://www.tpointtech.com/c-sharp-user-defined-exceptions#)

1. using System;  
2. class Point  
3. {  
4.     static void Main()  
5.     {  
6.         try  
7.         {  
8.             int num = 10;  
9.             int z = 0;  
10.             int res = num / z;   
11.             Console.WriteLine(res);  
12.         }  
13.         catch (DivideByZeroException m)  
14.         {  
15.             Console.WriteLine("System Exception Caught: " + m.Message);  
16.         }  
17.     }  
18. }  

**Output:**

System Exception Caught: Attempted to divide by zero.

**Explanation:**

In this example, we demonstrate the system exception in C#. Inside the try block, the program attempts to divide an integer value num by zero, which is mathematically undefined. Hence, the operation throws an exception. When the exception is thrown, the control immediately jumps to the catch block. The catch block handles the error by printing an error message.

### System-defined Exception Examples

There are several examples of system-defined exceptions in C#. Some of them are as follows:

**1) Handling IndexOutOfRangeException in C#**

Let's take an example to illustrate an IndexOutOfRangeException in C# using a try-catch block.

### Example

[](https://www.tpointtech.com/c-sharp-user-defined-exceptions#)[](https://www.tpointtech.com/c-sharp-user-defined-exceptions#)[](https://www.tpointtech.com/c-sharp-user-defined-exceptions#)

1. using System;  
2. class Tpoint  
3. {  
4.     static void Main()  
5.     {  
6.         int[] num = {10, 20, 30};  
7.         try  
8.         {  
9.             Console.WriteLine(num [3]); //throws IndexOutOfRangeException  
10.         }  
11.         catch (IndexOutOfRangeException m)  
12.         {  
13.       Console.WriteLine("Error: This index number is not available in the array. ");  
14.             Console.WriteLine("Exception message: " + m.Message);  
15.         }  
16.         Console.WriteLine("Program continues running after handling the exception. ");  
17.     }  
18. }  

**Output:**

ERROR!
Error: This index number is not available in the array.
Exception message: Index was outside the bounds of the array.
Program continues running after handling the exception.

**Explanation:**

In this example, we create an array named num with three numbers. After that, we tried to access the fourth item, which does not exist. The try-catch block catches the error and prints the error message without crashing the program.

**2) Handling NullReferenceException in C#**

Let's take an example to illustrate a NullReferenceException in C# using a try-catch block.

### Example

[](https://www.tpointtech.com/c-sharp-user-defined-exceptions#)[](https://www.tpointtech.com/c-sharp-user-defined-exceptions#)[](https://www.tpointtech.com/c-sharp-user-defined-exceptions#)

1. using System;  
2. class Tpoint  
3. {  
4.     static void Main()  
5.     {  
6.         string t = null;  
7.         try  
8.         {  
9.             Console.WriteLine(t.ToUpper());  
10.         }  
11.         catch (NullReferenceException m)  
12.         {  
13.             Console.WriteLine("Error: You tried to use an object that is null. ");  
14.             Console.WriteLine("Exception message: " + m.Message);  
15.         }  
16.         Console.WriteLine("Program continues running after handling the exception. ");  
17.     }  
18. }  

**Output:**

ERROR!
Error: You tried to use an object that is null.
Exception message: Object reference not set to an instance of an object
Program continues running after handling the exception.

**Explanation:**

In this example, a string variable t is declared and set to a null value, which means it has no value. When the program tries to call the ToUpper() method on this null variable, it throws a NullReferenceException because we cannot use methods on a null object. The exception is caught using a try-catch block and prints the error message without crashing the program.

## Application Exception

In the C# programming language, an application exception is a class that is derived from the System.Excpetion. It is used to represent errors related to the application's own logic or rules, rather than system-level errors.

For example, if we define a rule that during a division operation, and if the divisor is an odd number, the program should throw an exception.

### C# Application Exception Example

Let us take an example to illustrate the application exception in C#.

### Example

[](https://www.tpointtech.com/c-sharp-user-defined-exceptions#)[](https://www.tpointtech.com/c-sharp-user-defined-exceptions#)[](https://www.tpointtech.com/c-sharp-user-defined-exceptions#)

1. using System;  
2. class Tpoint : Exception  
3. {  
4.     public Tpoint(string message) : base(message) { }  
5. }  
6. class tech  
7. {  
8.     static void Main()  
9.     {  
10.         try  
11.         {  
12.             int n = -5;  
13.             if (n < 0)  
14.             {  
15.                 throw new Tpoint("Negative values are not allowed. ");  
16.             }  

17.             Console.WriteLine("Number is: " + n);  
18.         }  
19.         catch (Tpoint m)  
20.         {  
21.             Console.WriteLine("Application error message: " + m.Message);  
22.         }  
23.     }  
24. }  

**Output:**

Application error message: Negative values are not allowed.

**Explanation:**

In this example, we define a custom exception Tpoint that inherits from Exception. In the main() method, if the number n is negative, it throws a custom exception. After that, the catch block handles it and shows a meaningful error message.

## Conclusion

In conclusion, a C# custom exception allows developer to create their own error types that are more meaningful and specific to their application logic. By using custom exceptions, developers can write clearer and more maintainable code, which makes it easier to identify and handle the specific error conditions.