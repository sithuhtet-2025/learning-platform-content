This chapter explains how to create and use custom (user-defined) exceptions in Java to handle application-specific errors.

## What is Custom (User-Defined) Exception in Java?

**A custom (user-defined) exception** is an exception created by the programmer to handle application-specific error conditions. These exceptions are implemented by creating a class that extends either the **Exception** class (for checked exceptions) or the **RuntimeException** class (for unchecked exceptions).

Custom exceptions allow developers to define meaningful error messages and handle errors in a way that better matches the program's requirements.

### Syntax

Here is the syntax to define a custom exception:

[](https://www.tpointtech.com/custom-exception-in-java#)[](https://www.tpointtech.com/custom-exception-in-java#)[](https://www.tpointtech.com/custom-exception-in-java#)

1. class CustomException extends Exception {    
2.     CustomException(String message) {    
3.         super(message);    
4.     }    
5. }  

### Custom Exception Example: WrongFileNameException

We can create a custom exception by extending the Exception class. In this example, we create a custom exception named WrongFileNameException.

[](https://www.tpointtech.com/custom-exception-in-java#)[](https://www.tpointtech.com/custom-exception-in-java#)[](https://www.tpointtech.com/custom-exception-in-java#)

1. // Creating a custom exception  
2. public class WrongFileNameException extends Exception {      
3.     // Constructor that accepts an error message  
4.     public WrongFileNameException(String errorMessage) {      
5.         super(errorMessage); // Pass message to parent Exception class  
6.     }      
7. }  

Here, the string passed to the constructor is stored in the parent Exception class and can be retrieved using the getMessage() method.

### Complete Example Using WrongFileNameException

Here is the complete example:

[](https://www.tpointtech.com/custom-exception-in-java#)[](https://www.tpointtech.com/custom-exception-in-java#)[](https://www.tpointtech.com/custom-exception-in-java#)

1. public class TestWrongFileNameException {  

2.     // Method to check file name  
3.     static void checkFileName(String fileName) throws WrongFileNameException {  
4.         if (!fileName.endsWith(".txt")) {  
5.             throw new WrongFileNameException("Invalid file name: must end with .txt");  
6.         } else {  
7.             System.out.println("File name is valid: " + fileName);  
8.         }  
9.     }  

10.     public static void main(String[] args) {  
11.         try {  
12.             checkFileName("document.pdf"); // Invalid file name  
13.             checkFileName("notes.txt");    // Valid file name  
14.         } catch (WrongFileNameException e) {  
15.             System.out.println("Caught Exception: " + e.getMessage());  
16.         }  
17.     }  
18. }  

**Output:**

Caught Exception: Invalid file name: must end with .txt

## Why use custom exceptions?

Java exceptions cover almost all the general types of exceptions that may occur during code execution. However, we sometimes need to create custom exceptions.

The following are a few of the reasons to use custom exceptions:

- It represents application-specific errors.
- To catch and provide specific treatment to a subset of existing Java exceptions.
- **Business Logic Exceptions:** These are the exceptions related to business logic and workflow. It is useful for users and developers to understand the exact problem in a meaningful way.
- It provides clear, descriptive error messages for better debugging.

## Creating a Custom Exception

To create a custom exception:

1. You need to extend the **Exception class** (for checked exceptions) or **RuntimeException** class (for unchecked exceptions).
2. After that, you need to initialize the exception with custom messages using the constructor.
3. Optionally, you can also add methods to provide additional details about the exception.

### Example 1: Custom Exception with Message

In this example, we create a custom exception InvalidAgeException that is thrown when the age is less than 18. The exception message is passed to the parent Exception class using super().

[](https://www.tpointtech.com/custom-exception-in-java#)[](https://www.tpointtech.com/custom-exception-in-java#)[](https://www.tpointtech.com/custom-exception-in-java#)

1. // Custom exception class  
2. class InvalidAgeException extends Exception {      
3.     public InvalidAgeException(String message) {      
4.         super(message); // Pass message to parent Exception class  
5.     }      
6. }  

7. // Class that uses the custom exception  
8. public class Main {      
9.     // Method to validate age  
10.     static void validate(int age) throws InvalidAgeException {        
11.         if (age < 18) {      
12.             throw new InvalidAgeException("Age is not valid to vote");        
13.         } else {       
14.             System.out.println("Welcome to vote");       
15.         }       
16.     }        

17.     public static void main(String[] args) {      
18.         try {      
19.             validate(13); // Invalid age  
20.         } catch (InvalidAgeException ex) {      
21.             System.out.println("Caught the exception");      
22.             System.out.println("An exception occurred: " + ex);      
23.         }      
24.         System.out.println("Rest of the code...");        
25.     }      
26. }  

**Output:**

Caught the exception
An exception occurred: InvalidAgeException: Age is not valid to vote
Rest of the code...

### Example 2: Custom Exception Without Message

In this example, we create a custom exception MyCustomException without a message. The exception is thrown and caught, demonstrating that getMessage() returns null if no message is provided.

[](https://www.tpointtech.com/custom-exception-in-java#)[](https://www.tpointtech.com/custom-exception-in-java#)[](https://www.tpointtech.com/custom-exception-in-java#)

1. // Custom exception class  
2. class MyCustomException extends Exception {      
3. }  

4. // Class that uses the custom exception  
5. public class Main {      
6.     public static void main(String[] args) {      
7.         try {      
8.             throw new MyCustomException();      
9.         } catch (MyCustomException ex) {      
10.             System.out.println("Caught the exception");      
11.             System.out.println(ex.getMessage());      
12.         }      
13.         System.out.println("Rest of the code...");        
14.     }      
15. }    

**Output:**

Caught the exception
null
Rest of the code...