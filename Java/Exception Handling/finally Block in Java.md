In Java, the **finally block** is used to execute important code such as closing files or releasing resources, regardless of whether an exception occurs or not. In this chapter, we will learn about the finally block along with the examples.

## What is the Finally Block in Java?

The **finally block** is a block of code that always executes after a try block, whether an exception is thrown or not. The finally block is useful when you want to cleanup activities or free the resources, like closing files, streams, or database connections.

### Key Points

The following key points of the finally block are as follows:

1. A finally block is **optional**, but when present, it always executes after the try and catch blocks.
2. It executes even if a return statement is encountered in the try or catch blocks.

### Flow Diagram

The following images shows the flow diagram (working) of the finally block:

![Java finally block](https://images.tpointtech.com/core/images/java-finally-block.png)

**Note:** If we do not handle the exception before terminating the program, the JVM executes the finally block (if any).

## Example of Using Finally Block

The following example demonstrates how a finally block is executed whether an exception occurs or not:

[](https://www.tpointtech.com/finally-block-in-java#)[](https://www.tpointtech.com/finally-block-in-java#)[](https://www.tpointtech.com/finally-block-in-java#)

1. // Java Program to demonstrate the use of finally block  
2. public class Main {  
3.     public static void main(String[] args) {  
4.         try {  
5.             int data = 25 / 0; // This will cause ArithmeticException  
6.         } catch (ArithmeticException e) {  
7.             System.out.println("Exception caught: " + e);  
8.         } finally {  
9.             System.out.println("Finally block executed: Cleanup code runs here.");  
10.         }  
11.         System.out.println("Rest of the program continues...");  
12.     }  
13. }  

**Output:**

Exception caught: java.lang.ArithmeticException: / by zero
Finally block executed: Cleanup code runs here.
Rest of the program continues...

## Usage of the finally Block

Let's see different scenarios where a finally block can be used.

### Case 1: When No Exception Occurs

If the code in the try block executes normally without throwing an exception, the finally block is still executed.

The following example demonstrates the execution of the finally block when no exception occurs:

[](https://www.tpointtech.com/finally-block-in-java#)[](https://www.tpointtech.com/finally-block-in-java#)[](https://www.tpointtech.com/finally-block-in-java#)

1. class Main   
2. {      
3.   public static void main(String args[])  
4.   {      
5.       try {      
6.     //The below code does not throw any exception    
7.        int data=25/5;      
8.        System.out.println(data);      
9.       }      
10.     //catch won't be executed    
11.       catch(NullPointerException e) {    
12.     System.out.println(e);    
13.     }      
14.     //executed regardless of exception occurred or not    
15.      finally {    
16.     System.out.println("Finally block is always executed");    
17.     }      
18.     System.out.println("rest of the code...");      
19.   }      
20. }    

**Output:**

5
Finally block is always executed
rest of the code...

### Case 2: When an Exception Occurs but Is Not Handled

If an exception occurs but the catch block cannot handle it, the finally block is still executed before the program terminates abnormally.

The following example demonstrates that the finally block is executed even if an exception occurs but is not handled by the catch block:

[](https://www.tpointtech.com/finally-block-in-java#)[](https://www.tpointtech.com/finally-block-in-java#)[](https://www.tpointtech.com/finally-block-in-java#)

1. public class Main  
2. {      
3.      public static void main(String args[])  
4.      {     
5.       try {      
6.         System.out.println("Inside the try block");    
7.         //The below code throws a divide by zero exception    
8.        int data=25/0;      
9.        System.out.println(data);      
10.       }      
11.       //cannot handle Arithmetic type exception can only accept a Null Pointer type exception    
12.       catch(NullPointerException e){    
13.         System.out.println(e);    
14.       }     
15.       //executes regardless of exception occurred or not     
16.       finally {    
17.         System.out.println("Finally block is always executed");    
18.       }      
19.       System.out.println("rest of the code...");      
20.     }      
21. }      

**Output:**

Inside the try block
Finally block is always executed
Runtime Error:
Exception in thread "main" java.lang.ArithmeticException: / by zero
at Main.main(Main.java:8)

### Case 3: When an Exception Occurs and Is Handled

If an exception occurs and the catch block handles it, the finally block is executed afterward, and the rest of the program continues normally.

The following example demonstrates the execution of the finally block when an exception occurs and is handled by the catch block:

[](https://www.tpointtech.com/finally-block-in-java#)[](https://www.tpointtech.com/finally-block-in-java#)[](https://www.tpointtech.com/finally-block-in-java#)

1. public class Main  
2. {      
3.     public static void main(String args[])  
4.     {     
5.       try {      
6.         System.out.println("Inside the try block");    
7.         //The below code throws a divide by zero exception    
8.        int data=25/0;      
9.        System.out.println(data);      
10.       }     
11.       //handles the Arithmetic Exception / Divide by zero exception    
12.       catch(ArithmeticException e){    
13.         System.out.println("Exception handled");    
14.         System.out.println(e);    
15.       }     
16.       //executes regardless of exception occurred or not     
17.       finally {    
18.         System.out.println("Finally block is always executed");    
19.       }      
20.       System.out.println("rest of the code...");      
21.     }      
22. }    

**Output:**

Inside the try block
Exception handled
java.lang.ArithmeticException: / by zero
Finally block is always executed
rest of the code...

**Rule:** For each try block, there can be zero or more catch blocks, but the finally block will be one.

**Note:** The finally block will not execute if the program exits (either by calling System.exit() or by causing a fatal error that causes the process to abort).