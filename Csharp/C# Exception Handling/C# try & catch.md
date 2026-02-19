
In the C# programming language, exception handling is performed using a try/catch statement. The try block is utilized to write the code that might cause exceptions during execution. When an error occurs, the program immediately moves to the catch block to handle the run-time error. It enables multiple catch blocks to handle the different types of exceptions, such as DivideByZeroException, NullReferenceException, and IndexOutOfRangeException.

### Syntax:

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-try-catch#)[](https://www.tpointtech.com/c-sharp-try-catch#)[](https://www.tpointtech.com/c-sharp-try-catch#)

1. try  
2. {  
3.     // Code inside the try block that can throw an error  
4. }  
5. catch (ExceptionType1 ex)  
6. {  
7.     // Error handling code  
8. }  

In this syntax,

- The try block contains the code that can cause an exception.
- The catch block is used to handle the exception if it occurs.

### C# Simple try/catch Example

Let us take an example to illustrate the try/catch block in C#.

### Example

[](https://www.tpointtech.com/c-sharp-try-catch#)[](https://www.tpointtech.com/c-sharp-try-catch#)[](https://www.tpointtech.com/c-sharp-try-catch#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {  
6.         try  
7.         {  
8.             int n1 = 10;  
9.             int n2 = 0;    
10.             int res = n1 / n2;   
11.            Console.WriteLine($"The divide of two number is {res}");  
12.         }  
13.         catch (DivideByZeroException ex)  
14.         {  
15.             Console.WriteLine("Error: Cannot divide by Zero.");  
16.         }  
17.     }  
18. }  

**Output:**

ERROR!
Error: Cannot divide by Zero.

**Explanation:**

In this example, we demonstrate the [exception handling](https://www.tpointtech.com/c-sharp-exception-handling) in C#. First, we have taken the two variables n1 and n2 with values 10 and 0. After that, we divide n1 by n2, which causes a DivideByZeroException. Rather than crashing the program, the catch block handles the error and shows the error message.

## C# Try block

In the [C# programming language](https://www.tpointtech.com/c-sharp-tutorial), the try block is used to wrap the code that may throw an exception during the run-time of the program. The try block contains the code that may cause an error, and if an error occurs, the program immediately jumps to the catch block to handle it.

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-try-catch#)[](https://www.tpointtech.com/c-sharp-try-catch#)[](https://www.tpointtech.com/c-sharp-try-catch#)

1. try  
2. {  
3.     // Code inside the try block that can throw an error  
4. }  

## C# Catch block

In C#, the catch block is used to handle the exceptions of the code. This block executes only when an error occurs in the try block. It can also access the exception object to get the details, such as the error message and stack trace. It allows us to prevent the program from crashing and enables us to handle errors in an effective manner.

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-try-catch#)[](https://www.tpointtech.com/c-sharp-try-catch#)[](https://www.tpointtech.com/c-sharp-try-catch#)

1. catch (Exception ex)  
2. {  
3.     // Error handling code  
4. }  

## Finally block

In C#, the [finally block](https://www.tpointtech.com/c-sharp-finally) is a code block that always runs whether the condition is true or not. It is always executed after the try and catch block. It is mainly utilized to perform cleanup operations, such as releasing resources, closing files, and disconnecting from a database.

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-try-catch#)[](https://www.tpointtech.com/c-sharp-try-catch#)[](https://www.tpointtech.com/c-sharp-try-catch#)

1. try  
2. {  
3.     // Code that may throw an exception  
4. }  
5. catch (ExceptionType ex)  
6. {  
7.     // Handle the exception  
8. }  
9. finally  
10. {  
11.     // Code that always executes.  
12. }  

### C# Simple Example of handling all exceptions:

Let us take an example of handling all exceptions in the try catch block.

### Example

[](https://www.tpointtech.com/c-sharp-try-catch#)[](https://www.tpointtech.com/c-sharp-try-catch#)[](https://www.tpointtech.com/c-sharp-try-catch#)

1. using System;  
2. class Division  
3. {  
4.     static void Main()  
5.     {  
6.         float S = 75, P = 0, res;  
7.         try  
8.         {  
9.             if (P == 0)  
10.                 throw new Exception("Division by zero is not allowed");  

11.             res = S / P;  
12.             Console.WriteLine(S + " / " + P + " = " + res);  
13.         }  
14.         catch (Exception ex)  
15.         {  
16.             Console.WriteLine("Error: " + ex.Message);  
17.         }  
18.         finally  
19.         {  
20.             Console.WriteLine("Finally block executed: Cleaning up resources or finishing tasks.");  
21.         }  
22.     }  
23. }  

**Output:**

Error: Division by zero is not allowed
Finally block executed: Cleaning up resources or finishing tasks.

**Explanation:**

In this example, we have taken a class Division, and declared two floating point numbers A and B, where A is 75 and B is 0. After that, the try block checks for division by zero and throws an exception if the divisor is 0. The catch block handles the exception and prints an error message. The finally block always executes, which ensures clean-up or final tasks are performed regardless of whether an exception occurred.

## Multiple Catch block

In C#, the multiple catch block provides a powerful mechanism to handle the different types of exceptions that may occur at runtime. A single try block can be followed by several catch blocks, and every block is used to handle a specific exception type. It enables us to respond to different types of error conditions in the program according to the requirements.

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-try-catch#)[](https://www.tpointtech.com/c-sharp-try-catch#)[](https://www.tpointtech.com/c-sharp-try-catch#)

1. try  
2. {  
3. // code that may throw an exception  
4. }  
5. catch  
6. {  
7. // Handle ExceptionType1  
8. }  
9. catch  
10. {  
11. // Handle ExceptionType2  
12. }  
13. catch( exception ex )  
14. {  
15. // Handle any other exception  
16. }  

### C# Simple Example Multiple Catch block

Let us take an example to illustrate the multiple catch blocks in C#.

### Example

[](https://www.tpointtech.com/c-sharp-try-catch#)[](https://www.tpointtech.com/c-sharp-try-catch#)[](https://www.tpointtech.com/c-sharp-try-catch#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {  
6.         int [] numbers = {5, 20, 35, 50, 65};  
7.         try  
8.         {  
9.             Console.Write("Please input a number for your choice: \n");  
10.             int index = Convert.ToInt32(Console.ReadLine());  
11.             Console.WriteLine("The Value at index " + index + " = " + numbers[index]);  
12.         }  
13.         catch (IndexOutOfRangeException m)  
14.         {  
15.             Console.WriteLine("The index you entered is invalid. ");  
16.         }  
17.         catch (FormatException m)  
18.         {  
19.             Console.WriteLine("Please enter a valid number ");  
20.         }  
21.         catch (Exception m)  
22.         {  
23.             Console.WriteLine("An unexpected error occurs: " + m.Message);  
24.         }  
25.         finally  
26.         {  
27.             Console.WriteLine("The Program execution completed.");  
28.         }  
29.     }  
30. }  

**Output:**

It has the following output.

**Case 1:**

Enter any number for your choice: 2
The Value at index 2 = 35
The Program finished.

**Case 2:**

Please input a number for your choice 5
The index you entered is invalid.
The Program finished.

**Case 3:**

Please input a number for your choice abc
Please enter a valid number
The Program finished.

**Explanation:**

In this example, we have taken an integer type array and assigned the values. After that, we take a number from the user and use it as an index to display a value from the array. If the index value is invalid, it shows an error message. If the input is not a number, it gives another error, and any other errors are also handled. In the end, it always prints that the program has finished.

## C# Nested try/catch block

In the C# programming language, a nested try/catch block refers to placing one try/catch block inside another to handle errors at multiple levels. The inner try/catch handles the error that happens in the part of the code. If it does not catch an exception, the outer try/catch block can handle errors in the runtime environment.

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-try-catch#)[](https://www.tpointtech.com/c-sharp-try-catch#)[](https://www.tpointtech.com/c-sharp-try-catch#)

1. try  
2. {     
3.     // Code inside the try block that can throw an error  
4. }  
5. try  
6. {  
7.     // Code inside the try block that can throw an error  
8. }  
9. catch  
10. {  
11.     // Error handling code  
12. }  
13. catch  
14. {  
15.     // Error handling code  
16. }  

### C# Nested try/catch Example

Let us take an example to illustrate the nested try/catch in C#.

### Example

[](https://www.tpointtech.com/c-sharp-try-catch#)[](https://www.tpointtech.com/c-sharp-try-catch#)[](https://www.tpointtech.com/c-sharp-try-catch#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {     
6.         try  
7.         {  
8.             Console.WriteLine("The Outer try block starts.");     
9.             try  
10.             {  
11.                 Console.WriteLine("The Inner try block starts.");  
12.                 int[] n = { 100, 200, 300 };  
13.                 Console.WriteLine(n[5]); // throw IndexOutOfRangeException  
14.                 int num = 10, den = 0;  
15.                 int result = num / den; // throw DivideByZeroException  
16.                 Console.WriteLine("The Inner try block finished.");  
17.             }  
18.             catch ( DivideByZeroException m )  
19.             {  
20.                 Console.WriteLine("Cannot divide by zero. ");  
21.             }  
22.             Console.WriteLine("The Code continues after inner try-catch.");  
23.         }  
24.         catch (IndexOutOfRangeException m)  
25.         {  
26.             Console.WriteLine("Index out of range.");  
27.         }  
28.         catch (Exception m)  
29.         {  
30.             Console.WriteLine("The Outer general catch: " + m.Message);  
31.         }  
32.         finally  
33.         {  
34.             Console.WriteLine("The Finally block has been executed.");  
35.         }  
36.     }  
37. }  

**Output:**

The Outer try block starts.
The Inner try block starts.
Index out of range.
The Finally block executed.

**Explanation:**

In this example, we demonstrate the nested try/catch block along with a finally block in C#. Inside the inner try block, it tries to access numbers[5], which does not exist and throws an IndexOutOfException. The outer catch block deals with the IndexOutOfRangeException and shows the corresponding error message. After that, when exceptions are handled, the finally block executes, which always runs and shows the message "Finally block executed".

## Conclusion

In conclusion, the try/catch block is an important feature to handle run-time errors without crashing the program. Using the try, catch, and finally blocks makes the code more reliable and prevents the crashing of the program. It enables multiple catch blocks to handle the different types of exceptions.