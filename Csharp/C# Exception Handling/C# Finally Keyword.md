
In the C# programming language, the finally block is a key feature of [exception handling](https://www.tpointtech.com/c-sharp-exception-handling). It is used to write clean-up code that will always execute, whether an exception occurs or not. It is useful for several tasks, such as closing files, releasing the database, or disconnecting from a database. A finally block is written at the end, after the [try/catch block](https://www.tpointtech.com/c-sharp-try-catch). The finally statement code always runs in the program, which makes it a reliable place for resource management.

### Syntax of Finally keyword:

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-finally#)[](https://www.tpointtech.com/c-sharp-finally#)[](https://www.tpointtech.com/c-sharp-finally#)

1. try  
2. {  
3.     // Statements that can cause errors  
4. }  
5. catch (ExceptionType1 ex)  
6. {  
7.     // Error handling code  
8. }  
9. Finally  
10. {     
11. // clean up code that always executes  
12. }  

In this syntax,

- **Try:** The try block holds the code that might throw an exception.
- **Catch:** The catch block handles the exception if it occurs.
- **Finally:** The finally block executes in every case, whether an exception is raised or not.

### Simple finally block Example in C#

Let's take an example to illustrate the finally block in C# exception handling.

### Example

[](https://www.tpointtech.com/c-sharp-finally#)[](https://www.tpointtech.com/c-sharp-finally#)[](https://www.tpointtech.com/c-sharp-finally#)

1. using System;  
2. class Tpt  
3. {  
4.     static void Main()  
5.     {     
6.         try  
7.         {  
8.             Console.WriteLine("Enter any positive number:");  
9.             int x, r;  
10.             x = Convert.ToInt32(Console.ReadLine());  
11.             r = 10 / x;   
12.             Console.WriteLine("The result is " + r);  
13.         }  
14.         catch (FormatException m)  
15.         {  
16.             Console.WriteLine("Please enter any valid number.");  
17.         }  
18.         catch (DivideByZeroException m)  
19.         {  
20.             Console.WriteLine("Division by zero is not allowed.");  
21.         }  
22.         finally  
23.         {  
24.             Console.WriteLine("Finally block has been executed.");  
25.         }  
26.         Console.WriteLine("The program continues execution after exception handling.");  
27.     }  
28. }  

**Output:**

It has the following output:

**Case 1: (Valid Input)**

If we enter a positive number, the output would be:

Enter any positive number:
5
The result is 2
Finally block has been executed.
The program continues execution after exception handling.

**Case 2: (Invalid Input)**

If we enter the alphabetic value, the output would be:

Enter any number for your choice:
abc
Please enter any valid number.
Finally block has been executed.
The program continues execution after exception handling.

**Case 3: (Divide by Zero)**

If we enter the 0 number, the output would be:

Enter any number for your choice:
0
Division by zero is not allowed.
Finally block has been executed.
The program continues execution after exception handling.

**Explanation:**

In this example, we demonstrate how the finally block works in C# exception handling. First, we have taken the try block where the user is prompted to enter a number to perform the division operation. If the user enters a valid input, the program runs and shows the output. If the user enters invalid input, such as zero or an alphabet, an exception occurs. However, the finally block always executes, whether the user input is valid or not.

## Characteristics of Finally Blocks in C#

Several characteristics of the finally block in C# are as follows:

- The finally block runs in all cases, no matter whether an exception is thrown or not.
- A finally block can be utilized without the catch block.
- It is used for tasks like closing files, releasing the database, or disconnecting from a database.
- A finally block doesn't allow the conditional statement, including break, continue, or return.

## Execution of the finally block without a catch block

In the [C# programming language](https://www.tpointtech.com/c-sharp-tutorial), the finally block can be used without a catch block, and it always executes after the try block. These features are very helpful if we want to run cleanup code without handling the exceptions directly.

### C# finally block Example without a catch block:

Let us take an example to use the finally block without using a catch block in C#.

### Example

[](https://www.tpointtech.com/c-sharp-finally#)[](https://www.tpointtech.com/c-sharp-finally#)[](https://www.tpointtech.com/c-sharp-finally#)

1. using System;  
2. class TPT  
3. {  
4.     static void Main()  
5.     {  
6.         try  
7.         {  
8.             Console.WriteLine("Welcome to Tpointtech");  
9.             int n1 = 80;  
10.             int res1 = n1 / 2;  
11.             Console.WriteLine($"The division of two numbers is: {res1}");          
12. }  
13.         finally  
14.         {  
15.             Console.WriteLine("Finally block has been executed successfully.");  
16.         }  
17.         Console.WriteLine("The program continues after the try finally.");  
18.     }  
19. }  

**Output:**

Welcome to Tpointtech
The division of two numbers is: 40
Finally block has been executed successfully.
The program continues after the try finally.

**Explanation:**

In this example, we illustrate the use of finally blocks without a catch block. Inside the try block, we print a message and perform a division operation. After that, the final block executes automatically and prints the confirmation message.

## Execution of the finally block with an exception

In C# programming, the execution of the finally block with an exception means that if an error happens in the try block, the code inside the finally block will still run. It ensures that tasks like clean up or resource release are always completed.

### C# Example using a finally block with exceptions

Let us take an example to illustrate the finally block with exceptions in C#.

### Example

[](https://www.tpointtech.com/c-sharp-finally#)[](https://www.tpointtech.com/c-sharp-finally#)[](https://www.tpointtech.com/c-sharp-finally#)

1. using System;  
2. class Tpoint  
3. {  
4.     static void Main()  
5.     {     
6.         try  
7.         {  
8.             int n = 1000;  
9.             int x = n / 0;   
10.             Console.WriteLine("The division  of two numbers is " + x);  
11.         }  
12.         catch ( DivideByZeroException m )  
13.         {  
14.             Console.WriteLine("Error: " + m.Message );  
15.         }  
16.         finally  
17.         {  
18.             Console.WriteLine("Finally block executed.");  
19.         }  
20.     }  
21. }  

**Output:**

Error: Attempted to divide by zero.
Finally block executed.

**Explanation:**

In this example, we try to divide the number 10 by 0 inside a try block. The divide by zero operation is invalid, so it causes a runtime error. After that, the program moves to the catch block. It finds the error and displays the error message. After the catch block, the finally block executes.

### C# Example using a finally block for resource clean-up

Let us take an example to illustrate the finally block for clean-up resources.

### Example

[](https://www.tpointtech.com/c-sharp-finally#)[](https://www.tpointtech.com/c-sharp-finally#)[](https://www.tpointtech.com/c-sharp-finally#)

1. using System;  
2. using System.IO;  
3. class Program  
4. {  
5.     static void Main()  
6.     {  
7.         StreamReader r = null;  
8.         try  
9.         {  
10.             r = new StreamReader("test.txt");  
11.             string content = r.ReadToEnd();  
12.             Console.WriteLine(content);  
13.         }  
14.         catch (FileNotFoundException m)  
15.         {  
16.             Console.WriteLine("File not found: " + m.Message);  
17.         }  
18.         finally  
19.         {  
20.             if (r != null)  
21.             {  
22.                 r.Close();   // Clean up resource  
23.                 Console.WriteLine("File stream closed successfully.");  
24.             }  
25.         }  
26.     }  
27. }  

**Output:**

File not found: Could not find file "/home/compiler/ test.txt "

**Explanation:**

In this example, the program attempts to open or read the file. If the file is not found, the catch block handles the FileNotFoundException and displays an error message. At last, the finally block executed. The finally block checks if the r object is not null and then closes it to release system resources.

## Important Points in the finally block in C#

Several important points of the finally block in C# are as follows:

- In C#, multiple finally blocks in the same block of the program are not allowed.
- It is an optional block.
- A single try block contains multiple catch blocks, but only one finally block is permitted.

## Conclusion

In conclusion, the C# finally block is an important factor in exception handling by handling the run-time errors and maintaining the normal flow of the program. The finally block is the key feature of exception handling. It ensures that the clean-up code will always execute, whether an exception occurs or not. It is useful for tasks like closing files, releasing the database, or disconnecting from a database.