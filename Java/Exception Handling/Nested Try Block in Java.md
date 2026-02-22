In Java, using a try block inside another try block is permitted. It is called as nested try block. Every statement that we enter a statement in try block, context of that exception is pushed onto the stack.

For example, the inner try block can be used to handle ArrayIndexOutOfBoundsException, while the outer try block can handle the ArithmeticException (division by zero).

## Why Use Nested Try Blocks?

Sometimes, a part of a block may cause one type of exception, while the entire block itself may cause another. In such cases, **nested try blocks** are useful to handle multiple exceptions separately.

## Syntax of Nested Try-Catch

A **nested try block** is a try block placed **inside another try block**. The outer try block can handle exceptions not caught by the inner try block(s).

Here is the syntax to use nested try blocks:

[](https://www.tpointtech.com/nested-try-block-in-java#)[](https://www.tpointtech.com/nested-try-block-in-java#)[](https://www.tpointtech.com/nested-try-block-in-java#)

1. try {    
2.     // Outer try block  
3.     // Code that may throw an exception  

4.     try {    
5.         // Inner try block  
6.         // Code that may throw a different exception  
7.     } catch (ExceptionType1 e1) {    
8.         // Inner catch block: handles ExceptionType1  
9.     }    

10.     // Optional: more inner try-catch blocks can be added  
11. } catch (ExceptionType2 e2) {    
12.     // Outer catch block: handles exceptions not caught by inner try  
13. }  

### Syntax Explanation

Steps by step explanation of nested try block is as follows:

- **Outer Try Block**
    - The outer try block contains the main code that may throw exceptions.
    - If an exception occurs that is not handled by any inner try-catch, it is passed to this outer try block.
- **Inner Try Block(s):**
    - The inner try block(s) is/are placed inside the outer try block.
    - These can handle exceptions specific to the inner code.
    - Multiple inner try-catch blocks can exist for different operations.
- **Catch Blocks:**
    - Each try block (inner or outer) must have at least one corresponding catch block to handle exceptions.
    - Catch blocks handle specific exceptions for better control.
    - The outer catch block acts as a backup handler for any exception not handled by inner catch blocks.

## Examples on Nested Try Blocks

Practice the following examples to understand nested exception handling.

### Example 1: Handling Two Different Exceptions

The following example demonstrates how nested try blocks can handle ArithmeticException and ArrayIndexOutOfBoundsException.

[](https://www.tpointtech.com/nested-try-block-in-java#)[](https://www.tpointtech.com/nested-try-block-in-java#)[](https://www.tpointtech.com/nested-try-block-in-java#)

1. public class Main {      
2.      public static void main(String args[])  
3.      {     
4.          //outer try block     
5.           try {      
6.               //inner try block 1    
7.                 try {      
8.                  System.out.println("cannot divide by 0");    
9.                  int b =39/0;      
10.                 }    
11.                 //catch block of the inner try block 1    
12.                 catch(ArithmeticException e)    
13.                 {    
14.                   System.out.println(e);    
15.                 }      
16.                 //inner try block 2    
17.                 try{      
18.                 int a[]=new int[5];      
19.                 //assigning the value out of array bounds    
20.                  a[5]=4;      
21.                  }    
22.                 //catch block of the inner try block 2    
23.                 catch(ArrayIndexOutOfBoundsException e)    
24.                 {    
25.                    System.out.println(e);    
26.                 }      
27.                 System.out.println("other statement");      
28.           }    
29.           //catch block of the outer try block    
30.           catch(Exception e)    
31.           {    
32.             System.out.println("handled the exception (outer catch)");    
33.           }      
34.           System.out.println("normal flow..");      
35.      }      
36. }    

**Output:**

cannot divide by 0
java.lang.ArithmeticException: / by zero
java.lang.ArrayIndexOutOfBoundsException: Index 5 out of bounds for length 5
other statement
normal flow..

When any try block does not have a catch block for a particular exception, then the catch block of the outer (parent) try block is checked for that exception, and if it matches, the catch block of the outer try block is executed.

If none of the catch blocks specified in the code are able to handle the exception, then the Java runtime system will handle the exception. Then, it displays the system-generated message for that exception.

### Example 2: Handling Exception by the Main Try Block

The following example demonstrates that if an inner try block does not handle an exception, it is passed to its parent (outer) try block.

[](https://www.tpointtech.com/nested-try-block-in-java#)[](https://www.tpointtech.com/nested-try-block-in-java#)[](https://www.tpointtech.com/nested-try-block-in-java#)

1. public class Main {    
2.     public static void main(String args[])    
3.     {    
4.         // outer (main) try block    
5.         try {    
6.             //inner try block 1     
7.             try {    
8.                 // inner try block 2    
9.                 try {    
10.                     int arr[] = { 1, 2, 3, 4 };    
11.                     //printing the array element out of its bounds    
12.                     System.out.println(arr[10]);    
13.                 }    
14.                 // to handle ArithmeticException    
15.                 catch (ArithmeticException e) {    
16.                     System.out.println("Arithmetic exception");    
17.                     System.out.println(" inner try block 2");    
18.                 }    
19.             }    
20.             // to handle ArithmeticException     
21.             catch (ArithmeticException e) {    
22.                 System.out.println("Arithmetic exception");   
23.                 System.out.println("inner try block 1");    
24.             }    
25.         }    
26.         // to handle ArrayIndexOutOfBoundsException     
27.         catch (ArrayIndexOutOfBoundsException e4) {    
28.             System.out.print(e4);    
29.             System.out.println(" outer (main) try block");    
30.         }    
31.         catch (Exception e5) {    
32.             System.out.print("Exception");    
33.             System.out.println(" handled in main try-block");    
34.         }    
35.     }    
36. }    

When we execute the above program, we get the following exception:

java.lang.ArrayIndexOutOfBoundsException: Index 10 out of bounds for length 4 outer (main) try block