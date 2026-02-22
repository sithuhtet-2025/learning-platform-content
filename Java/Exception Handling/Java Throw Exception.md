
In Java, the throw keyword is used to explicitly throw an exception within a method or block of code. It allows developers to signal that an error has occurred and needs to be handled. The thrown exception must be an instance of Throwable or one of its subclasses, such as Exception or RuntimeException.

## Purpose of throw Keyword

The Java throw keyword is used to throw an exception explicitly from a method or a block of code. It can be used to throw both checked and unchecked exceptions. It is mainly used to throw a custom exception and allows developers to manually trigger an exception when an undesirable situation occurs.

## Exception Object and Error Message

When using the throw keyword, we specify the exception object that needs to be thrown. The exception object contains a message that describes the error. These exceptions may be related to user input, server issues, hardware malfunctions, invalid computations, or other conditions based on the program’s requirements.

## Rules for Throwing Exceptions

The following rules must be followed during throwing expectations:

- The **object** that is thrown must be of type **Throwable** or one of its subclasses.
- The **Exception** class is a direct subclass of **Throwable**.
- User-defined exceptions, also known as custom exceptions, usually extend the **Exception**
- If a checked exception is thrown and not handled within the method, it must be declared using the throws keyword in the method signature.

## Throwing an Exception Using throw Keyword

The **throw** keyword is used to explicitly throw an exception from a method or a block of code. It allows the programmer to manually trigger an exception when a specific condition occurs that disrupts the normal flow of the program.

### Syntax

The below syntax creates an exception object and throws it explicitly at runtime.

[](https://www.tpointtech.com/java-throw-exception#)[](https://www.tpointtech.com/java-throw-exception#)[](https://www.tpointtech.com/java-throw-exception#)

1. throw new exception_class("error message");  

Where, instance refers to an object of a class that must extend Throwable (which includes the Exception class and its subclasses).

Let's see an example of throw IOException.

[](https://www.tpointtech.com/java-throw-exception#)[](https://www.tpointtech.com/java-throw-exception#)[](https://www.tpointtech.com/java-throw-exception#)

1. tthrow new IOException("sorry device error");  

Here:

- [new](https://www.tpointtech.com/new-keyword-in-java) is used to create an instance (object) of the [exception class](https://www.tpointtech.com/exception-class-in-java).
- The error message provides context about the reason for the exception.

Where the Instance must be of type Throwable or a subclass of Throwable, for example, Exception is a subclass of Throwable, and the user-defined exceptions usually extend the Exception class.

### Example

The following example demonstrates throwing an exception using the throw keyword.

[](https://www.tpointtech.com/java-throw-exception#)[](https://www.tpointtech.com/java-throw-exception#)[](https://www.tpointtech.com/java-throw-exception#)

1. class Main {  
2.     public static void main(String[] args) {  
3.         int age = 15;  

4.         if (age < 18) {  
5.             throw new ArithmeticException("Not eligible to vote");  
6.         }  

7.         System.out.println("Eligible to vote");  
8.     }  
9. }  

**Output:**

Exception in thread "main" java.lang.ArithmeticException: Not eligible to vote

## Throwing an Unchecked Exception

An unchecked exception is an exception that is not checked at compile time and usually occurs due to programming errors, such as invalid calculations or improper use of objects. In Java, unchecked exceptions extend the **RuntimeException** class and can be thrown using the **throw** keyword without declaring them using the throws clause.

### Example

In this example, we have created a method named validate() that accepts an integer as a parameter. If the age is less than 18, we are throwing the ArithmeticException; otherwise, print a message welcoming them to vote.

[](https://www.tpointtech.com/java-throw-exception#)[](https://www.tpointtech.com/java-throw-exception#)[](https://www.tpointtech.com/java-throw-exception#)

1. import java.lang.ArithmeticException;  
2. public class Main {     
3.     // Function to check if a person is eligible to vote or not     
4.     public static void validate(int age) {    
5.         if(age < 18) {    
6.             // Throw ArithmeticException if not eligible to vote    
7.             throw new ArithmeticException("Person is not eligible to vote");      
8.         } else {    
9.             System.out.println("Person is eligible to vote!!");    
10.         }    
11.     }    
12.     // Main method    
13.     public static void main(String args[]) {    
14.         // Calling the function    
15.         validate(13);    
16.         System.out.println("rest of the code...");      
17.     }      
18. }  

**Output:**

Exception in thread "main" java.lang.ArithmeticException: Person is not eligible to vote
at Main.validate(Main.java:8)
at Main.main(Main.java:17)

The above code throws an unchecked exception. Similarly, we can also throw unchecked and user-defined exceptions.

> **Note:** If we throw an unchecked exception from a method, it is not required to handle the exception or declare it in a throws clause. However, for checked exceptions, handling or declaration in the throws clause is mandatory.

If we throw a checked exception using the throw keyword, it is a must to handle the exception using the catch block, or the method must declare it using the throws declaration.

## Throwing a Checked Exception

A checked exception is an exception that is checked at compile time and must be either handled using a try-catch block or declared using the throws keyword in the method signature. In Java, checked exceptions extend the Exception class (excluding RuntimeException).

### Example

In this example, we demonstrate how to throw a checked exception (FileNotFoundException) using the throw keyword and how to handle it properly using a try-catch block.

> **Note:** Every subclass of Error and RuntimeException is an unchecked exception in Java. A checked exception is everything else under the Throwable class.

[](https://www.tpointtech.com/java-throw-exception#)[](https://www.tpointtech.com/java-throw-exception#)[](https://www.tpointtech.com/java-throw-exception#)

1. import java.io.*;    
2. public class Main {     
3.     //function to check if a person is eligible to vote or not     
4.     public static void method() throws FileNotFoundException {    
5.         FileReader file = new FileReader("C:\\Users\\Desktop\\abc.txt");    
6.         BufferedReader fileInput = new BufferedReader(file);    
7.         // Explicitly throwing a checked exception  
8.         throw new FileNotFoundException();    
9.     }    
10.     //main method    
11.     public static void main(String args[]){    
12.         try  {    
13.             method();    
14.         }     
15.         catch (FileNotFoundException e)     {    
16.             e.printStackTrace();    
17.         }    
18.         System.out.println("rest of the code...");      
19.     }      
20. }  

**Output:**

java.io.FileNotFoundException: C:\Users\Desktop\abc.txt (No such file or directory)
at java.base/java.io.FileInputStream.open0(Native Method)
at java.base/java.io.FileInputStream.open(FileInputStream.java:213)
at java.base/java.io.FileInputStream.<init>(FileInputStream.java:152)
at java.base/java.io.FileInputStream.<init>(FileInputStream.java:106)
at java.base/java.io.FileReader.<init>(FileReader.java:60)
at Main.method(Main.java:9)
at Main.main(Main.java:20)

## Throwing User-Defined Exception

The exception is everything else under the Throwable class. Java allows developers to create their own custom exceptions by extending the Exception class or one of its subclasses. These are known as **user-defined exceptions**. They are typically used when you want to enforce application-specific rules and constraints that are not covered by Java's built-in exceptions.

### Example

In this example, we will define a custom exception called UserDefinedException and throw it manually using the throw keyword. We'll also catch and handle it using a try-catch block, just like we would with any other checked exception.

[](https://www.tpointtech.com/java-throw-exception#)[](https://www.tpointtech.com/java-throw-exception#)[](https://www.tpointtech.com/java-throw-exception#)

1. import java.io.*;    
2. // class represents a user-defined exception    
3. class UserDefinedException extends Exception  {    
4.     public UserDefinedException(String str)  {    
5.         // Calling the constructor of the parent Exception    
6.         super(str);    
7.     }    
8. }   
9. // Class that uses the above MyException    
10. public class Main  {    
11.     public static void main(String args[])  {    
12.         try   {    
13.             // throw an object of user user-defined exception    
14.             throw new UserDefinedException("This is user-defined exception");    
15.         }    
16.         catch (UserDefinedException ude)   {    
17.             System.out.println("Caught the exception");    
18.             // Print the message from the MyException object    
19.             System.out.println(ude.getMessage());    
20.         }    
21.     }    
22. }    

**Output:**

Caught the exception
This is a user-defined exception