Exception Handling in Java is one of the most powerful mechanisms to handle runtime errors so that the normal flow of the application can be maintained.

In this chapter, we will learn about Java exceptions, their types, and the difference between checked and unchecked exceptions, along with how to handle them to make your programs robust and error-free.

## What is an Exception in Java?

In Java, an **exception** is an event that occurs during the execution of a program and disrupts the normal flow of instructions. **Exceptions** can occur for various reasons, such as invalid user input, a file not being found, or division by zero. When an exception occurs, it is typically represented by an object of a subclass of the **java.lang.Exception** class.

## What is Exception Handling in Java?

**Exception Handling** is a mechanism that allows a program to handle **runtime errors** such as ClassNotFoundException, IOException, SQLException, RemoteException, and others, so that the normal flow of the application can be maintained.

## Hierarchy of Java Exception classes

Exceptions are represented by classes, and all exception classes are part of the **java.lang package**. They are organized in a hierarchical structure with **Throwable** at the top. The main hierarchy is as follows:

- **Throwable**: The superclass of all errors and exceptions in Java.
    - **Error**: Represents serious system errors that applications usually cannot handle (e.g., OutOfMemoryError).
    - **Exception**: Represents conditions that a program might want to catch.
        - **Checked Exceptions**: Must be either **handled using try-catch** or **declared using throws** (e.g., IOException, SQLException).
        - **Unchecked Exceptions (RuntimeException)**: Do **not need explicit handling**, typically caused by programming errors (e.g., NullPointerException, ArithmeticException).

The following diagram demonstrates the same:

![hierarchy of exception handling](https://d2jdgazzki9vjm.cloudfront.net/core/images/hierarchy-of-exception-handling.png)

## Types of Java Exceptions

The exceptions are categorized into two main types: checked exceptions and unchecked exceptions. Additionally, there is a third category known as errors. Let's delve into each of these types:

- **Checked Exception:** Exceptions that must be handled or declared in the code.
- **Unchecked Exception:** Exceptions that do not require explicit handling and usually occur due to programming errors.
- **Error:** Serious problems that are not meant to be caught by applications, usually system-related.

![hierarchy of exception handling](https://d2jdgazzki9vjm.cloudfront.net/core/images/types-of-exception-handling.png)

## Java Checked Exceptions

Checked exceptions are the exceptions that are checked at compile-time. This means that the compiler verifies that the code handles these exceptions either by catching them or declaring them in the method signature using the throws keyword. Examples of checked exceptions include:

- **IOException:**An exception is thrown when an input/output operation fails, such as when reading from or writing to a file.
- **SQLException:**It is thrown when an error occurs while accessing a database.
- **ParseException:**Indicates a problem while parsing a string into another data type, such as parsing a date.
- **ClassNotFoundException:**It is thrown when an application tries to load a class through its string name using methods like Class.forName(), but the class with the specified name cannot be found in the classpath.

### Example

The following example demonstrates a checked exception using IOException:

[](https://www.tpointtech.com/exception-handling-in-java#)[](https://www.tpointtech.com/exception-handling-in-java#)[](https://www.tpointtech.com/exception-handling-in-java#)

1. import java.io.File;  
2. import java.io.FileReader;  
3. import java.io.IOException;  

4. public class CheckedExceptionExample {  
5.     public static void main(String[] args) {  
6.         try {  
7.             File file = new File("example.txt");  
8.             FileReader fr = new FileReader(file); // May throw IOException  
9.             System.out.println("File opened successfully.");  
10.             fr.close();  
11.         } catch (IOException e) {  
12.             System.out.println("An IOException occurred: " + e.getMessage());  
13.         }  
14.     }  
15. }  

**Output:**

An IOException occurred: example.txt (No such file or directory)

**Explanation:**

- FileReader may throw an **IOException**, which is a **checked exception**.
- The exception is handled using a try-catch block.

## Java Unchecked Exceptions (Runtime Exceptions)

Unchecked exceptions, also known as runtime exceptions, are not checked at compile-time. These exceptions usually occur due to programming errors, such as logic errors or incorrect assumptions in the code. They do not need to be declared in the method signature using the throws keyword, making it optional to handle them. Examples of unchecked exceptions include:

- **NullPointerException:**It is thrown when trying to access or call a method on an object reference that is null.
- **ArrayIndexOutOfBoundsException:**It occurs when we try to access an array element with an invalid index.
- **ArithmeticException:**It is thrown when an arithmetic operation fails, such as division by zero.
- **IllegalArgumentException:**It indicates that a method has been passed an illegal or inappropriate argument.

### Example

The following example demonstrates unchecked exceptions:

[](https://www.tpointtech.com/exception-handling-in-java#)[](https://www.tpointtech.com/exception-handling-in-java#)[](https://www.tpointtech.com/exception-handling-in-java#)

1. public class UncheckedExceptionExample {  
2.     public static void main(String[] args) {  
3.         // Example 1: NullPointerException  
4.         String str = null;  
5.         try {  
6.             System.out.println(str.length()); // May throw NullPointerException  
7.         } catch (NullPointerException e) {  
8.             System.out.println("Caught NullPointerException: " + e.getMessage());  
9.         }  

10.         // Example 2: ArrayIndexOutOfBoundsException  
11.         int[] arr = {1, 2, 3};  
12.         try {  
13.             System.out.println(arr[5]); // Invalid index  
14.         } catch (ArrayIndexOutOfBoundsException e) {  
15.             System.out.println("Caught ArrayIndexOutOfBoundsException: " + e.getMessage());  
16.         }  

17.         // Example 3: ArithmeticException  
18.         try {  
19.             int result = 10 / 0; // Division by zero  
20.         } catch (ArithmeticException e) {  
21.             System.out.println("Caught ArithmeticException: " + e.getMessage());  
22.         }  
23.     }  
24. }  

**Output:**

Caught NullPointerException: null
Caught ArrayIndexOutOfBoundsException: Index 5 out of bounds for length 3
Caught ArithmeticException: / by zero

**Explanation:**

- These exceptions occur **at runtime** due to programming mistakes.
- Handling them is **optional**, but using try-catch can prevent the program from crashing.
- Examples demonstrate **NullPointerException**, **ArrayIndexOutOfBoundsException**, and **ArithmeticException**.

## Java Errors

Errors represent exceptional conditions that are not expected to be caught under normal circumstances. They are typically caused by issues outside the control of the application, such as system failures or resource exhaustion. Errors are not meant to be caught or handled by application code. Examples of errors include:

- **OutOfMemoryError:**It occurs when the Java Virtual Machine (JVM) cannot allocate enough memory for the application.
- **StackOverflowError:**It is thrown when the stack memory is exhausted due to excessive recursion.
- **NoClassDefFoundError:**It indicates that the JVM cannot find the definition of a class that was available at compile-time.

### Example

The following example demonstrates errors in Java:

[](https://www.tpointtech.com/exception-handling-in-java#)[](https://www.tpointtech.com/exception-handling-in-java#)[](https://www.tpointtech.com/exception-handling-in-java#)

1. public class ErrorExample {  
2.     // Example 1: StackOverflowError  
3.     public static void recursiveCall() {  
4.         recursiveCall(); // Infinite recursion  
5.     }  

6.     public static void main(String[] args) {  
7.         try {  
8.             recursiveCall();  
9.         } catch (StackOverflowError e) {  
10.             System.out.println("Caught StackOverflowError: " + e.getMessage());  
11.         }  

12.         // Example 2: OutOfMemoryError  
13.         try {  
14.             int[] largeArray = new int[Integer.MAX_VALUE]; // Request too much memory  
15.         } catch (OutOfMemoryError e) {  
16.             System.out.println("Caught OutOfMemoryError: " + e.getMessage());  
17.         }  
18.     }  
19. }  

**Output:**

Caught StackOverflowError: null
Caught OutOfMemoryError: Java heap space

**Explanation:**

- Errors indicate serious problems that applications generally cannot recover from.
- Unlike checked and unchecked exceptions, handling errors is optional, and they are usually left to the JVM.
- Examples show **StackOverflowError** caused by recursion and **OutOfMemoryError** caused by excessive memory allocation.

## Java Exception Handling Keywords

Java provides five keywords that are used to handle the exception. The following table describes each.

|Keyword|Description|
|---|---|
|try|The "try" keyword is used to specify a block where we should place an exception code. It means we can't use try block alone. The try block must be followed by either catch or finally.|
|catch|The "catch" block is used to handle the exception. It must be preceded by try block which means we can't use catch block alone. It can be followed by finally block later.|
|finally|The "finally" block is used to execute the necessary code of the program. It is executed whether an exception is handled or not.|
|throw|The "throw" keyword is used to throw an exception.|
|throws|The "throws" keyword is used to declare exceptions. It specifies that there may occur an exception in the method. It doesn't throw an exception. It is always used with method signature.|

## The try-catch Block

The [try-catch block](https://www.tpointtech.com/try-catch-in-java) is the primary mechanism for handling exceptions. The **try block** contains code that may throw an exception, and the **catch block** handles that exception.

### Syntax

The syntax to handle an expectation using try-catch block is:

[](https://www.tpointtech.com/exception-handling-in-java#)[](https://www.tpointtech.com/exception-handling-in-java#)[](https://www.tpointtech.com/exception-handling-in-java#)

1. try {  
2.     // Code that may throw an exception  
3. } catch (ExceptionType e) {  
4.     // Code to handle the exception  
5. }  

### Example

Consider the below example, demonstrating handling an exception using try-catch block:

[](https://www.tpointtech.com/exception-handling-in-java#)[](https://www.tpointtech.com/exception-handling-in-java#)[](https://www.tpointtech.com/exception-handling-in-java#)

1. // Java Program to understand the   
2. // use of exception handling   
3. public class Main {      
4.     public static void main(String args[]) {      
5.         try {      
6.             int data = 100 / 0; // May raise ArithmeticException      
7.         } catch (ArithmeticException e) {  
8.             System.out.println(e); // Handling the exception  
9.         }      
10.         System.out.println("rest of the code...");      
11.     }      
12. }      

**Output:**

java.lang.ArithmeticException: / by zero
rest of the code...

**Explanation:**

- Division by zero raises an **ArithmeticException** that is caught and handled in the catch block.
- The program continues execution after the exception that demonstrates how normal flow is maintained.

## Handling Multiple Exceptions

Java allows handling different types of exceptions using [multiple catch blocks](https://www.tpointtech.com/multiple-catch-block-in-java). Each catch block is used for a specific exception type.

### Syntax

Here is the syntax to handle multiple exceptions:

[](https://www.tpointtech.com/exception-handling-in-java#)[](https://www.tpointtech.com/exception-handling-in-java#)[](https://www.tpointtech.com/exception-handling-in-java#)

1. try {  
2.     // Code that may throw an exception  
3. } catch (IOException e) {  
4.     // Handle IOException  
5. } catch (NumberFormatException e) {  
6.     // Handle NumberFormatException  
7. } catch (Exception e) {  
8.     // Handle any other exceptions  
9. }  

### Example

The following example demonstrates handling multiple exceptions:

[](https://www.tpointtech.com/exception-handling-in-java#)[](https://www.tpointtech.com/exception-handling-in-java#)[](https://www.tpointtech.com/exception-handling-in-java#)

1. //Java Program to illustrate handling multiple exceptions  
2. import java.io.*;  
3. public class Main {  
4.     public static void main(String[] args) {  
5.         try {  
6.             // Code that may throw multiple exceptions  
7.             int[] numbers = {1, 2, 3};  
8.             System.out.println(numbers[10]); // May throw ArrayIndexOutOfBoundsException  

9.             String str = "abc";  
10.             int num = Integer.parseInt(str); // May throw NumberFormatException  

11.             FileReader file = new FileReader("test.txt"); // May throw FileNotFoundException  

12.         } catch (ArrayIndexOutOfBoundsException e) {  
13.             System.out.println("Error: Array index is out of bounds.");  
14.         } catch (NumberFormatException e) {  
15.             System.out.println("Error: Invalid number format.");  
16.         } catch (FileNotFoundException e) {  
17.             System.out.println("Error: File not found.");  
18.         } catch (Exception e) {  
19.             System.out.println("Error: An unexpected exception occurred.");  
20.         }  

21.         System.out.println("Program continues after handling exceptions...");  
22.     }  
23. }  

**Output:**

Error: Array index is out of bounds.
Program continues after handling exceptions...

### The finally Block

The [finally block](https://www.tpointtech.com/finally-block-in-java) is executed regardless of whether an exception occurs or not. It is commonly used to release resources like files or database connections.

### Syntax

Here is the syntax to use finally block along with the try-catch block:

[](https://www.tpointtech.com/exception-handling-in-java#)[](https://www.tpointtech.com/exception-handling-in-java#)[](https://www.tpointtech.com/exception-handling-in-java#)

1. try {  
2.     // Code that may throw an exception  
3. } catch (Exception e) {  
4.     // Exception handling code  
5. } finally {  
6.     // Cleanup code  
7. }  

### Example

The following example demonstrates the use of the finally block:

[](https://www.tpointtech.com/exception-handling-in-java#)[](https://www.tpointtech.com/exception-handling-in-java#)[](https://www.tpointtech.com/exception-handling-in-java#)

1. //Java Program to illustrate the use of finally block  
2. public class Main {  
3.     public static void main(String[] args) {  
4.         try {  
5.             int data = 25 / 0; // May throw ArithmeticException  
6.             System.out.println("Result: " + data);  
7.         } catch (ArithmeticException e) {  
8.             System.out.println("Error: Division by zero is not allowed.");  
9.         } finally {  
10.             System.out.println("This block always executes.");  
11.         }  

12.         System.out.println("Program continues after finally block...");  
13.     }  
14. }  

**Output:**

Error: Division by zero is not allowed.
This block always executes.
Program continues after finally block...

## Common Scenarios of Java Exceptions

There are given some scenarios where unchecked exceptions may occur. They are as follows:

### 1. A scenario where ArithmeticException occurs

If we divide any number by zero, there occurs an ArithmeticException.

[](https://www.tpointtech.com/exception-handling-in-java#)[](https://www.tpointtech.com/exception-handling-in-java#)[](https://www.tpointtech.com/exception-handling-in-java#)

1. int a=50/0;//ArithmeticException  

Here's a simple Java code example where an ArithmeticException occurs:

### Example

[](https://www.tpointtech.com/exception-handling-in-java#)[](https://www.tpointtech.com/exception-handling-in-java#)[](https://www.tpointtech.com/exception-handling-in-java#)

1. //Java Program to illustrate the use of Arithmetic Exception in Java  
2. public class Main {    
3.     public static void main(String[] args) {    
4.         int dividend = 10;    
5.         int divisor = 0;    
6.         try {    
7.             int result = dividend / divisor; // Division by zero    
8.             System.out.println("Result: " + result);    
9.         } catch (ArithmeticException e) {    
10.             System.out.println("Error: Division by zero is not allowed.");    
11.             // Additional error handling code can be added here    
12.         }    
13.     }    
14. }    

**Output:**

Error: Division by zero is not allowed.

**Explanation**

We have a main() method where we attempt to perform division by zero that is not allowed in arithmetic.

Inside the try block, we perform the division operation dividend / divisor, where divisor is assigned the value of 0.

When the division by zero occurs, an ArithmeticException is thrown. We catch this exception using a catch block specifically for ArithmeticException.

In the catch block, we handle the exception by printing an error message, indicating that division by zero is not allowed. Additional error handling logic can be added here if needed.

### 2. A scenario where NullPointerException occurs

If we have a null value in any variable, performing any operation on the variable throws a NullPointerException.

[](https://www.tpointtech.com/exception-handling-in-java#)[](https://www.tpointtech.com/exception-handling-in-java#)[](https://www.tpointtech.com/exception-handling-in-java#)

1. String s=null;  
2. System.out.println(s.length());//NullPointerException  

Here's a Java code example where a NullPointerException occurs:

### Example

[](https://www.tpointtech.com/exception-handling-in-java#)[](https://www.tpointtech.com/exception-handling-in-java#)[](https://www.tpointtech.com/exception-handling-in-java#)

1. //Java Program to illustrate the use of Null Pointer Exception in Java  
2. public class Main {    
3.     public static void main(String[] args) {    
4.         String str = null; // Initializing a String variable to null    
5.         try {    
6.             int length = str.length(); // Attempting to call a method on a null reference    
7.             System.out.println("Length of the string: " + length);    
8.         } catch (NullPointerException e) {    
9.             System.out.println("Error: Null reference encountered.");    
10.             // Additional error handling code can be added here    
11.         }    
12.     }    
13. }    

**Output:**

Error: Null reference encountered.

**Explanation**

We have a main() method where we initialize a String variable str to null.

Inside the try block, we attempt to call the length() method on the str reference, which is null.

When attempting to call a method on a null reference, a NullPointerException is thrown.

We catch this exception using a catch block specifically for NullPointerException.

In the catch block, we handle the exception by printing an error message indicating that a null reference was encountered. Additional error handling logic can be added here if needed.

### 3. A scenario where NumberFormatException occurs

If the formatting of any variable or number is mismatched, it may result into NumberFormatException. Suppose we have a string variable that has characters; converting this variable into digit will cause NumberFormatException.

[](https://www.tpointtech.com/exception-handling-in-java#)[](https://www.tpointtech.com/exception-handling-in-java#)[](https://www.tpointtech.com/exception-handling-in-java#)

1. String s="abc";  
2. int i=Integer.parseInt(s);//NumberFormatException  

Here's a Java code example where a NumberFormatException occurs:

### Example

[](https://www.tpointtech.com/exception-handling-in-java#)[](https://www.tpointtech.com/exception-handling-in-java#)[](https://www.tpointtech.com/exception-handling-in-java#)

1. //Java Program to illustrate the use of Number Format Exception in Java  
2. public class Main {    
3.     public static void main(String[] args) {    
4.         String str = "abc"; // Initializing a String with non-numeric characters    
5.         try {    
6.             int num = Integer.parseInt(str); // Attempting to parse a non-numeric string to an integer    
7.             System.out.println("Parsed number: " + num);    
8.         } catch (NumberFormatException e) {    
9.             System.out.println("Error: Unable to parse the string as an integer.");    
10.             // Additional error handling code can be added here    
11.         }    
12.     }    
13. }   

**Output:**

Error: Unable to parse the string as an integer.

**Explanation:**

We have a main() method where we initialize a String variable str with non-numeric characters.

Inside the try block, we attempt to parse the string str to an integer using the Integer.parseInt() method.

Since the string contains non-numeric characters, the parsing operation throws a NumberFormatException.

We catch this exception using a catch block specifically for NumberFormatException.

In the catch block, we handle the exception by printing an error message indicating that the string could not be parsed as an integer. Additional error handling logic can be added here if needed.

### 4. A scenario where ArrayIndexOutOfBoundsException occurs

When an array exceeds to it's size, the ArrayIndexOutOfBoundsException occurs. there may be other reasons to occur ArrayIndexOutOfBoundsException. Consider the following statements.

[](https://www.tpointtech.com/exception-handling-in-java#)[](https://www.tpointtech.com/exception-handling-in-java#)[](https://www.tpointtech.com/exception-handling-in-java#)

1. int a[]=new int[5];  
2. a[10]=50; //ArrayIndexOutOfBoundsException  

Here's a Java code example where an ArrayIndexOutOfBoundsException occurs:

### Example

[](https://www.tpointtech.com/exception-handling-in-java#)[](https://www.tpointtech.com/exception-handling-in-java#)[](https://www.tpointtech.com/exception-handling-in-java#)

1. //Java Program to illustrate the use of ArrayIndexOutOfBoundsException in Java  
2. public class Main {    
3.     public static void main(String[] args) {    
4.         int[] numbers = {1, 2, 3, 4, 5}; // Initializing an array with 5 elements    
5.         try {    
6.             int index = 10; // Accessing an index that is out of bounds    
7.             int value = numbers[index]; // Attempting to access an element at an invalid index    
8.             System.out.println("Value at index " + index + ": " + value);    
9.         } catch (ArrayIndexOutOfBoundsException e) {    
10.             System.out.println("Error: Index is out of bounds.");    
11.             // Additional error handling code can be added here    
12.         }    
13.     }    
14. }   

**Output:**

Error: Index is out of bounds.

**Explanation**

We have a main() method where we initialize an array numbers with 5 elements.

Inside the try block, we attempt to access an element at index 10, which is out of bounds for the array numbers.

Since the index is out of bounds, an ArrayIndexOutOfBoundsException is thrown.

We catch this exception using a catch block specifically for ArrayIndexOutOfBoundsException.

In the catch block, we handle the exception by printing an error message indicating that the index is out of bounds. Additional error handling logic can be added here if needed.