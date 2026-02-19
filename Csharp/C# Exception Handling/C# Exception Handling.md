Exception handling in C# programming is a technique to handle runtime errors. We perform exception handling so that the normal flow of the application can be maintained even after runtime errors. It enables us to identify and handle errors in code without terminating the program by using try, catch, throw, and finally blocks.

## Understanding Exception

An exception in C# is an unexpected event or object that is thrown during the program execution and interrupts its normal flow. It is a runtime error that can be handled. It can occur due to several situations, such as invalid input, division by zero, file not found, and network loss. If we don't handle the exception, it prints the exception message and terminates the program.

## Exception Handling Keywords

In [C#](https://www.tpointtech.com/c-sharp-tutorial), there are mainly four keywords used in exception handling. These are as follows:

![C# Exception Handling](https://images.tpointtech.com/csharp/images/c-sharp-exception-handling.png)

Here, we will discuss these keywords one by one.

### 1) Try Block

In the [C# programming language](https://www.tpointtech.com/c-sharp-tutorial), the try block is used to write the code that might cause exceptions. If the error occurs, it jumps to the catch block to handle the error, which prevents the program from crashing.

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-exception-handling#)[](https://www.tpointtech.com/c-sharp-exception-handling#)[](https://www.tpointtech.com/c-sharp-exception-handling#)

1. try  
2. {  
3.     // Code block that might cause an exception  
4. }  

### 2) Catch Block

In C#, the catch block is used to handle the exceptions of the code. It executes only when an error is thrown in the try block, which enables us to manage the error effectively instead of terminating unexpectedly. Multiple catch blocks can also be used to handle different types of exceptions.

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-exception-handling#)[](https://www.tpointtech.com/c-sharp-exception-handling#)[](https://www.tpointtech.com/c-sharp-exception-handling#)

1. catch (Exception ex)  
2. {  
3.     // code block that handles errors  
4. }  

**To Read More:** [C# try/Catch](https://www.tpointtech.com/c-sharp-try-catch)

### 3) Throw Block

In C#, the throw keyword is used to create and raise an exception when an error occurs in the program. It tells the program to stop running normally and move to the nearest catch block to handle the error.

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-exception-handling#)[](https://www.tpointtech.com/c-sharp-exception-handling#)[](https://www.tpointtech.com/c-sharp-exception-handling#)

1. throw new ExceptionType("Error message");  

### 4) Finally Block

In C#, the finally block is a code block that always runs after the [try and catch block](https://www.tpointtech.com/c-sharp-try-catch), whether the condition is true or not. It is used to cleanup several operations, such as closing files, releasing resources, or disposing of objects.

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-exception-handling#)[](https://www.tpointtech.com/c-sharp-exception-handling#)[](https://www.tpointtech.com/c-sharp-exception-handling#)

1. finally  
2. {  
3.     // Code block that executes always  
4. }  

**To Read More:** [C# Finally](https://www.tpointtech.com/c-sharp-finally)

### C# Simple Exception Handling Example

Let us take a simple example to demonstrate the exception handling in C#.

### Example

[](https://www.tpointtech.com/c-sharp-exception-handling#)[](https://www.tpointtech.com/c-sharp-exception-handling#)[](https://www.tpointtech.com/c-sharp-exception-handling#)

1. using System;     

2. class ExceptionHandling  
3. {  
4.     static void Main()  
5.     {  
6.         try //using try block  
7.         {  
8.             Console.Write("Enter a Positive Number: ");  
9.             int a = Convert.ToInt32(Console.ReadLine());  

10.             if (a < 0)  
11.             {  
12.                 // using throw block  
13.                 throw new Exception("Negative numbers are not allowed.");    
14.             }  

15.             Console.WriteLine($"Square of {a} is: {a * a}");  
16.         }  
17.         catch (FormatException ex)   //using catch block  
18.         {  
19.             Console.WriteLine("Error: Please enter a valid Number.");  
20.         }  
21.         catch (Exception ex)  
22.         {  
23.             Console.WriteLine("Exception Message: " + ex.Message);  
24.         }  
25.         finally   //using finally block  
26.         {  
27.             Console.WriteLine("Program execution finished successfully.\nFinally block always executes.");  
28.         }  
29.     }  
30. }  

**Output:**

Enter a Positive Number: 15
Square of 15 is: 225
Program execution finished successfully.
Finally block always executes.

**Explanation:**

In this example, we demonstrate the exception handling using try, catch, throw, and finally. First, we take a try block that prompts us to enter a positive number; if the input is negative, a custom exception is thrown. After that, we use the catch block to handle both FormatException and general exceptions. Lastly, we use the finally block that always executes, which ensures final messages or cleanup operations run regardless of errors.

## Custom Exception in C#

In the C# programming language, a custom exception is a user-defined exception that extends the built-in Exception class. It is utilized when predefined exceptions do not effectively define the error condition. A custom exception can be inherited from the exception class. It can also define the custom error messages and several properties if the program requires.

**Syntax:**

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-exception-handling#)[](https://www.tpointtech.com/c-sharp-exception-handling#)[](https://www.tpointtech.com/c-sharp-exception-handling#)

1. public class MyCustomExcept : Exception  
2. {  
3.     public MyCustomExcept() : base("custom exception")   
4.     {   
5.     }  

6.     public MyCustomExcect(string msg) : base(msg)   
7.     {   
8.     }  

9.     public MyCustomExcept(string msg, Exception inner) : base(msg, inner)   
10.     {   
11.     }  
12. }  

### C# Custom Exception Example

Let us take an example to illustrate a custom exception in C#.

### Example

[](https://www.tpointtech.com/c-sharp-exception-handling#)[](https://www.tpointtech.com/c-sharp-exception-handling#)[](https://www.tpointtech.com/c-sharp-exception-handling#)

1. using System;  
2. // Define a custom exception class  
3. public class AgeResException : Exception  
4. {     
5.     public AgeResException(string message) : base(message)  
6.     {  
7.     }  
8. }  
9. class Tpoint  
10. {  
11.     static void Main()  
12.     {  
13.         try  
14.         {  
15.             Console.Write("Please input your age: \n");  
16.             int age = Convert.ToInt32(Console.ReadLine());  
17.             // Checking age criteria for voting  
18.             if (age < 18)  
19.             {  
20.                 throw new AgeResException("Minimum voting age is 18 years. ");  
21.             }     
22.             Console.WriteLine("You are eligible to vote.");  
23.         }  
24.         catch (AgeResException m)  
25.         {  
26.             Console.WriteLine("Exception: " + m.Message);  
27.         }  
28.         catch (Exception m)  
29.         {  
30.             Console.WriteLine("The general Error: " + m.Message);  
31.         }  
32.         finally  
33.         {  
34.             Console.WriteLine("Program execution successfully.");  
35.         }  
36.     }  
37. }  

**Output:**

**Case 1:**

If we enter an age less than 18, the output would be:

Please input your age:
12
Exception: Minimum voting age is 18 years.
Program execution successfully.

**Case 2:**

If we enter an age of 18 or more, the output would be:

Please input your age:
18
You are eligible to vote.
Program execution successfully.

**Explanation:**

In this example, we demonstrate the use of a custom exception for age validation. First, we define an AgeResException class and check if the entered age is below 18; if the age is less than, the custom exception is thrown. After that, we use the try-catch blocks to handle both custom and general exceptions, while the finally block ensures that a completion message is always displayed.

## C# Exception Class

In C#, the exceptions are defined under the System.Exception class that is the parent class for handling the run-time errors. There are several common exception classes in C#. Some of them are as follows.

|Exception|Description|
|---|---|
|**System.Exception**|It is used to represent the parent class in C# for all exceptions.|
|**System.SystemException**|It represents all the errors that occur automatically during the run-time of the program.|
|**DivideByZeroException**|It throws the run-time error when division by zero occurs.|
|**IndexOutOfRangeException**|It throws the error when the array or collection index is out of range.|
|**NullReferenceException**|It throws the error when trying to use the null object reference.|
|**InvalidCastException**|It throws the error when an invalid type casting is performed.|
|**OutOfMemoryException**|It throws the error when the system does not have enough space to continue running the program.|
|**System.ApplicationException**|It is the main class for all the errors that are created by the programmer.|

### Exception Handling Example Using Multiple Catch Blocks in C#

Let us take a simple example to illustrate the exception handling using multiple catch blocks in C#.

### Example

[](https://www.tpointtech.com/c-sharp-exception-handling#)[](https://www.tpointtech.com/c-sharp-exception-handling#)[](https://www.tpointtech.com/c-sharp-exception-handling#)

1. using System;  
2. class Tpoint  
3. {  
4.     static void Main()  
5.     {  
6.         try  
7.         {     
8.             Console.Write("Please enter a number:");  
9.             int unum = Convert.ToInt32(Console.ReadLine());   
10.             int[] number= {2, 4, 6, 8};  
11.             Console.Write("Enter an array indexing position: ");  
12.             int ind = Convert.ToInt32(Console.ReadLine());  
13.             Console.WriteLine($"Value at position {ind} is: {number[ind]}");   
14.         }     
15.         catch (FormatException)  
16.         {  
17.             Console.WriteLine("Please input number only.");  
18.         }  
19.         catch (IndexOutOfRangeException)  
20.         {  
21.             Console.WriteLine("Choose a valid position from the array.");  
22.         }  
23.         catch (Exception m)  
24.         {  
25.             Console.WriteLine("Unexpected error: " + m.Message);  
26.         }  
27.     }  
28. }  

**Output:**

**Case 1:**

If we choose the valid value from an array index between 0 to 3, the output would be:

Please enter a number: 10
Enter an array indexing position: 2
Value at position 2 is: 6

**Case 2:**

If we choose the invalid value (more than 3) from the array index, the output would be:

Please enter a number: 5
Enter an array indexing position: 4
Choose a valid position from the array.

**Case 3:**

If we choose the invalid value (like alphabetic values) from the array index, the output would be:

Please enter a number: abc
Please input number only.

**Explanation:**

In this example, we demonstrate multiple exception handling using try-catch. First, it prompts us to enter a number, and then asks for an array index to display the value at that position. If we enter a non-numeric value, a FormatException is handled; if an invalid array index is given, an IndexOutOfRangeException is caught.

## Purpose of Exception Handling in C#

There are several purposes of exception handling in the C# programming language. Some of them are as follows.

- It is used to detect and handle the run-time errors without crashing the program.
- It is used to maintain the flow of the program even when an expected error occurs.
- It provides a way to catch and record errors in code, so that they can be identified, managed, and fixed without terminating the application.

## Difference between the Errors and Exceptions in C#

There are several differences between errors and exceptions in C#. Some of them are as follows:

|Features|Errors|Exception|
|---|---|---|
|**Definition**|Errors are caused by incorrect code written by the programmer.|An exception is an event or object that occurs during the execution of the program.|
|**Occurrence Time**|It is mostly a compile-time issue.|It is a run-time issue.|
|**Examples**|Syntax errors, missing semicolon, and undeclared variables are examples of errors.|Examples of exceptions include DivideByZeroException, NullReferenceException, and IndexOutOfRangeException.|
|**Handling**|It must be handled to fix their issues.|It must be handled using try, catch and finally blocks to fix their issues.|
|**Code Indication**|Errors indicate invalid code or a mistake in the code.|Exceptions indicate the valid issue with unexceptional situations during execution.|

## Conclusion

In conclusion, C# exception handling is an important aspect of code execution. It helps to handle runtime errors and maintain the normal flow of the program. The try, catch, throw, and finally blocks help to make the code more reliable, which prevents the crashing of the program.