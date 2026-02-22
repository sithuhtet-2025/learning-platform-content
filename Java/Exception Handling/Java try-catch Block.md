The Java try block is used to enclose the code that might throw an exception. It must be used within the method.

If an exception occurs at a particular statement in the try block, the rest of the block code will not execute. So, it is recommended not to keep the code in a try block that will not throw an exception.

## Java try-catch Block

The **try block** is used to enclose the code that might throw an exception during execution. Any code that has the potential to cause an error, such as division by zero, accessing an invalid array index, or reading a file, should be placed inside the try block.

The **catch block** is used to handle the exception thrown by the **try** block. You specify the type of exception to catch inside parentheses. When an exception occurs in the try block, the corresponding catch block executes.

### Syntax

The syntax of the try-catch block is as follows:

[](https://www.tpointtech.com/try-catch-in-java#)[](https://www.tpointtech.com/try-catch-in-java#)[](https://www.tpointtech.com/try-catch-in-java#)

1. try {      
2. // code that may throw an exception      
3. } catch(Exception_class_Name ref) { }        

**Here:**

- The **try block** contains the code that might cause an exception.
- The **catch block** handles the exception if it occurs.
- **ExceptionType** can be a specific exception like ArithmeticException, IOException, or the general Exception class.
- The catch block receives an **exception object** (commonly named e) that contains details about the exception.

## How Java Handles Exceptions Using try-catch Block?

When an exception occurs, the [Java Virtual Machine (JVM)](https://www.tpointtech.com/jvm-java-virtual-machine) first checks whether the exception is handled by the program.

- **If the exception is not handled:**
    - The JVM provides a **default exception handler** that performs the following tasks:
        1. Prints the exception description.
        2. Prints the stack trace (the hierarchy of methods where the exception occurred).
        3. Terminates the program.
- **If the exception is handled by the programmer:**
    - The normal flow of the application is **maintained**, and the rest of the code continues to execute.

This mechanism makes sure that exceptions do not always crash the program and gives programmers a way to recover from runtime errors gracefully.

The following image demonstrates how try-catch block works.

![Java try-catch block](https://images.tpointtech.com/core/images/java-try-catch-block.png)

## Example of try-catch Block

The following example demonstrates how a divide by zero scenario is handled using a try-catch block.

[](https://www.tpointtech.com/try-catch-in-java#)[](https://www.tpointtech.com/try-catch-in-java#)[](https://www.tpointtech.com/try-catch-in-java#)

1. // Java Program to demonstrate try-catch block  
2. public class Main {  
3.     public static void main(String[] args) {  
4.         try {  
5.             int dividend = 10;  
6.             int divisor = 0;  
7.             int result = dividend / divisor; // May throw ArithmeticException  
8.             System.out.println("Result: " + result);  
9.         } catch (ArithmeticException e) {  
10.             System.out.println("Error: Division by zero is not allowed.");  
11.         }  

12.         System.out.println("Program continues after exception handling.");  
13.     }  
14. }  

**Output:**

Error: Division by zero is not allowed.
Program continues after exception handling.

## Nested Try-Catch Block

You can also use the nested try-catch block that means a try-catch block placed inside another try or catch block. This is useful when you want to handle different types of exceptions separately at different levels of your code.

- The outer try block handles general exceptions.
- The inner try block handles specific exceptions that may occur within a particular code segment.

### Syntax

Here is the syntax of using nested try-catch block:

[](https://www.tpointtech.com/try-catch-in-java#)[](https://www.tpointtech.com/try-catch-in-java#)[](https://www.tpointtech.com/try-catch-in-java#)

1. try {  
2.     // Outer try block code  
3.     try {  
4.         // Inner try block code that may throw an exception  
5.     } catch (InnerExceptionType e) {  
6.         // Handle inner exception  
7.     }  
8. } catch (OuterExceptionType e) {  
9.     // Handle outer exception  
10. }  

### Example

The following example demonstrates nested try catch block:

[](https://www.tpointtech.com/try-catch-in-java#)[](https://www.tpointtech.com/try-catch-in-java#)[](https://www.tpointtech.com/try-catch-in-java#)

1. // Java Program to demonstrate Nested try-catch  
2. public class Main {  
3.     public static void main(String[] args) {  
4.         try {  
5.             int[] numbers = {1, 2, 3};  
6.             System.out.println("Outer try block starts");  

7.             try {  
8.                 // Inner try block  
9.                 int result = numbers[1] / 0; // May throw ArithmeticException  
10.             } catch (ArithmeticException e) {  
11.                 System.out.println("Inner catch: Arithmetic Exception occurred");  
12.             }  

13.             // Code that may throw another exception  
14.             System.out.println(numbers[5]); // May throw ArrayIndexOutOfBoundsException  

15.         } catch (ArrayIndexOutOfBoundsException e) {  
16.             System.out.println("Outer catch: Array Index Out Of Bounds Exception occurred");  
17.         }  

18.         System.out.println("Program continues after nested exception handling.");  
19.     }  
20. }  

**Output:**

Outer try block starts
Inner catch: Arithmetic Exception occurred
Outer catch: Array Index Out Of Bounds Exception occurred
Program continues after nested exception handling.

**Explanation:**

1. The inner try block handles the **ArithmeticException** caused by division by zero.
2. The outer try block catches the **ArrayIndexOutOfBoundsException** when accessing an invalid array index.

## Problem Without Exception Handling

Let's try to understand the problem if we do not use a try-catch block to handle the exception.

### Example: Throwing Arithmetic Exception (Divide by Zero)

[](https://www.tpointtech.com/try-catch-in-java#)[](https://www.tpointtech.com/try-catch-in-java#)[](https://www.tpointtech.com/try-catch-in-java#)

1. public class Main {   
2.     public static void main(String[] args) {    
3.         int data=50/0; //may throw exception     
4.         System.out.println("rest of the code");    
5.     }    
6. }    

**Output:**

Exception in thread "main" java.lang.ArithmeticException: / by zero

As we see in the above example, the rest of the code is not executed (in such a case, the rest of the code statement is not printed).

There might be 100 lines of code after the exception. If the exception is not handled, all the code below the exception will not execute.

## Handling Exception

Let's see the solution to the above problem by using a Java try-catch block.

### Example: Handling Arithmetic Exception (Divide by Zero)

### Example

[](https://www.tpointtech.com/try-catch-in-java#)[](https://www.tpointtech.com/try-catch-in-java#)[](https://www.tpointtech.com/try-catch-in-java#)

1. public class Main {    
2.     public static void main(String[] args) {    
3.         try  {    
4.         int data=50/0; //may throw exception     
5.         }    
6.         //handling the exception    
7.         catch(ArithmeticException e)   {    
8.             System.out.println(e);    
9.         }    
10.         System.out.println("rest of the code");    
11.     }    
12. }    

**Output:**

java.lang.ArithmeticException: / by zero
rest of the code

As we see in the above program, the rest of the code is executed, i.e., the rest of the code statement is printed on the console.