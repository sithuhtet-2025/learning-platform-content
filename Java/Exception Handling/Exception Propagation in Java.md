Exception propagation in Java is used for allowing exceptions to move up the call stack so they can be handled at a higher level in the program.

In this chapter, we will learn how exceptions travel through the call stack, how they can be caught at different levels, and how Java handles uncaught exceptions.

## What is Exception Propagation in Java?

Exception propagation is a mechanism that allows an exception to be passed from the method where it occurs to higher-level methods in the call stack. Exception propagation gives the flexibility to the programmers to decide where to catch and handle the exception.

When an exception is thrown, it first looks for a matching catch block in the current method. If not found, the exception propagates down the call stack to the previous method, continuing this process until it is caught or reaches the bottom of the stack. This process of moving an exception through the calling chain is why it is called **exception propagation**.

> **Note:** By default, [unchecked exceptions](https://www.tpointtech.com/unchecked-exceptions-in-java) (subclasses of RuntimeException) are automatically propagated up the calling chain.

## How Does Exception Propagation Work?

Exception propagation occurs when an exception is thrown from a method and is not caught within that method. The Java runtime system will look for a handler in the **calling method**-the method that is called the current method. If the calling method does not handle the exception, it gets propagated further up the call stack. This continues until either:

- A method catches the exception (i.e., a matching catch block is found).
- The exception reaches to the [**main() method**](https://www.tpointtech.com/java-main-method), which serves as the entry point to the program.

If no method handles the exception, the program terminates and displays the **stack trace**, which helps identify the origin and path of the exception.

## Why Is Exception Propagation Important?

Exception propagation helps us write cleaner and more modular code by letting us handle exceptions where it makes the most sense rather than cluttering every method with [try-catch blocks](https://www.tpointtech.com/try-catch-in-java). For instance, if several low-level methods can throw the same type of exception, it's often better to let that exception bubble up to a higher-level method that can handle it in a centralized way.

## Example: Propagation of Unchecked Exception

This first example demonstrates how an **unchecked exception** like ArithmeticException is propagated through the call stack and is eventually handled.

### Example

[](https://www.tpointtech.com/exception-propagation-in-java#)[](https://www.tpointtech.com/exception-propagation-in-java#)[](https://www.tpointtech.com/exception-propagation-in-java#)

1. class Main {  
2.     // Method m throws an ArithmeticException (division by zero)  
3.     void m() {  
4.         int a=50;  
5.         int b=a/0;         //divide by zero throws ArithmeticException  
6.     }  
7.     // Method n() calls method m()  
8.     void n() {  
9.         m(); // Exception is not handled here  
10.     }  
11.     // Method p() calls method n and handles any exception that is thrown  
12.     void p() {  
13.         try {  
14.             n(); // Exception propagates to here  
15.         } catch (Exception e) {  
16.             System.out.println("exception handled"); // Exception is caught and handled here  
17.         }  
18.     }  
19.     public static void main(String args[]) {  
20.         Main obj = new Main();  
21.         obj.p(); // Starts the chain of method calls  
22.         // The line is executed only if the exception is handled properly  
23.         System.out.println("normal flow...");  
24.     }  
25. }  

**Output:**

exception handled
normal flow...

**Explanation**

In this example, an exception occurs in the m() method (due to division by zero), which is not handled there. The exception is then propagated to the n() method, and from there, it moves to the p() method, where it is finally caught and handled. After the exception is dealt with, the message "normal flow..." is printed, indicating that the program continued without termination.

## Example: Propagation of Checked Exception

This second example demonstrates how a [**checked exception**](https://www.tpointtech.com/checked-exception-in-java) like IOException is propagated through the call stack and is eventually handled.

Exception can be handled in any method in call stack either in the main() method, p() method, n() method or m() method.

![exception propagation](https://images.tpointtech.com/core/images/exception-propagation.png)

> **Note:** By default, Checked Exceptions are not forwarded in calling chain (propagated).

### Example

[](https://www.tpointtech.com/exception-propagation-in-java#)[](https://www.tpointtech.com/exception-propagation-in-java#)[](https://www.tpointtech.com/exception-propagation-in-java#)

1. import java.io.*;  
2. class Main {  
3.     // Method m throws a checked exception, so it must declare it with throws  
4.     void m() throws IOException {  
5.         throw new IOException("device error"); // Explicitly throwing a checked exception  
6.     }  
7.     // Method n calls m(), so it must also declare the same exception  
8.     void n() throws IOException {  
9.         m(); // No handling here, so the exception is passed up the chain  
10.     }  
11.     // Method p catches the exception using a try-catch block  
12.     void p() {  
13.         try {  
14.             n(); // Exception propagates here and is caught  
15.         } catch (Exception e) {  
16.             System.out.println("exception handled"); // Exception is caught and handled  
17.         }  
18.     }  
19.     // Main method to start program execution  
20.     public static void main(String args[]) {  
21.         Main obj = new Main();  
22.         obj.p(); // Triggers the method chain  
23.         // Will be printed only if an exception is properly handled  
24.         System.out.println("normal flow");  
25.     }  
26. }  

**Output:**

exception handled
normal flow

**Explanation**

The code demonstrates how a **checked exception** (IOException) propagates through method calls. The m() method throws the exception, which is propagated to n() and then to p(). In p(), the exception is caught and handled, allowing the program to continue with normal execution.

## Important Points to Remember

### Call Stack Behavior

- When an exception occurs, Java looks for a handler in the current method.
- If none is found, the exception is passed to the calling method.
- It continues until a handler is found or the program terminates.

### Unchecked Exceptions (Runtime Exceptions)

- These propagate automatically up the stack if not handled.
- If no handler exists, JVM terminates the program.
- **Example:** ArithmeticException, NullPointerException.

### Checked Exceptions

- These exceptions must be either caught or declared using throws.
- If not handled, compilation error occurs.
- **Example:** IOException, SQLException.