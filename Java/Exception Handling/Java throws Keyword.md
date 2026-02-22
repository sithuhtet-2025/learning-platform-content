The throws keyword in Java is used in a method declaration to specify that the method may pass one or more exceptions to the calling method. In this chapter, we will learn how the throws keyword works, when it should be used, how it differs from the throw keyword, and how it helps in handling checked exceptions effectively in Java programs.

## What is throws Keyword in Java?

The **throws** keyword is a keyword that is used to declare possible exceptions that a method can generate and allow those exceptions to be handled by the method that invokes it rather than within the method itself.

### Syntax

The syntax of throws keyword for single exception is as follows:

[](https://www.tpointtech.com/java-throws#)[](https://www.tpointtech.com/java-throws#)[](https://www.tpointtech.com/java-throws#)

1. return_type method_name() throws exception_class_name {  
2.     // method code  
3. }  

The syntax of throws keyword for multiple exceptions is as follows:

[](https://www.tpointtech.com/java-throws#)[](https://www.tpointtech.com/java-throws#)[](https://www.tpointtech.com/java-throws#)

1. return_type method_name() throws exception_class_name1, exception_class_name2, ... {  
2.     // method code  
3. }  

## Examples of throws Keyword

Here are examples of the throws keyword for single and multiple exceptions.

### Example 1: Throws with Single Exception

The following example demonstrates the throws keyword with a single exception:

[](https://www.tpointtech.com/java-throws#)[](https://www.tpointtech.com/java-throws#)[](https://www.tpointtech.com/java-throws#)

1. static void checkAge(int age) throws ArithmeticException {  
2.         if (age < 18) {  
3.             throw new ArithmeticException("Not eligible to vote");  
4.         }  
5.         System.out.println("Eligible to vote");  
6.     }  

7.     public static void main(String[] args) {  
8.         try {  
9.             checkAge(15);  
10.         } catch (ArithmeticException e) {  
11.             System.out.println("Exception caught: " + e.getMessage());  
12.         }  
13.     }  
14. }    

**Output:**

Exception caught: Not eligible to vote

### Example 2: Throws with Multiple Exceptions

The following example demonstrates the throws keyword with multiple exceptions:

[](https://www.tpointtech.com/java-throws#)[](https://www.tpointtech.com/java-throws#)[](https://www.tpointtech.com/java-throws#)

1. import java.io.*;  

2. class Main {  
3.     static void readFile(String fileName) throws IOException, FileNotFoundException {  
4.         FileReader file = new FileReader(fileName);  
5.         BufferedReader fileInput = new BufferedReader(file);  
6.         System.out.println(fileInput.readLine());  
7.         fileInput.close();  
8.     }  

9.     public static void main(String[] args) {  
10.         try {  
11.             readFile("test.txt");  
12.         } catch (FileNotFoundException e) {  
13.             System.out.println("File not found: " + e.getMessage());  
14.         } catch (IOException e) {  
15.             System.out.println("IO Exception: " + e.getMessage());  
16.         }  
17.     }  
18. }  

**Output:**

File not found: test.txt (No such file or directory)

**Rule:** If we are calling a method that declares an exception, we must either catch or declare the exception.

## When to Use the throws Keyword?

The throws keyword is used when a method might cause a checked exception but does not handle it itself. It tells the caller that the method can throw an exception, so the caller can decide how to handle it.

It is commonly used in methods that work with files, databases, or network operations that helps to keep the code clean by passing the responsibility of handling exceptions to higher-level methods.

## Handling or Declaring Exceptions

If we are calling a method that declares an exception, we must **either catch the exception** or **declare it** using the throws keyword.

There are **two cases**:

1. **Handle the exception using a try-catch block**
2. **Declare the exception using the throws keyword**

### Case 1: Handle Exception Using try-catch

When we handle the exception, the program executes normally whether the exception occurs or not.

The following example demonstrates handling an exception using a try-catch block:

[](https://www.tpointtech.com/java-throws#)[](https://www.tpointtech.com/java-throws#)[](https://www.tpointtech.com/java-throws#)

1. import java.io.*;    
2. class M{    
3.  void method()throws IOException{    
4.   throw new IOException("device error");    
5.  }    
6. }    
7. public class Main{    
8.    public static void main(String args[]){    
9.     try{    
10.      M m=new M();    
11.      m.method();    
12.     }catch(Exception e){System.out.println("exception handled");}       
13.     System.out.println("normal flow...");    
14.   }    
15. }    

**Output:**

exception handled
normal flow...

### Case 2: Declare Exception Using throws

If we declare the exception and it does not occur, the program runs normally. If the exception occurs, it is thrown at runtime, because throws only declare the exception - it does not handle it.

**A) Exception Does Not Occur**

The following example demonstrates declaring an exception using the throws keyword when no exception occurs:

[](https://www.tpointtech.com/java-throws#)[](https://www.tpointtech.com/java-throws#)[](https://www.tpointtech.com/java-throws#)

1. import java.io.*;    
2. class M{    
3.  void method()throws IOException {    
4.   System.out.println("Device operation performed");    
5.  }    
6. }    
7. class Main {    
8.    public static void main(String args[])throws IOException{//declare exception    
9.      M m=new M();    
10.      m.method();    
11.     System.out.println("normal flow...");    
12.   }    
13. }    

**Output:**

Device operation performed
normal flow...

**B) Exception Occurs**

The following example demonstrates declaring an exception using the throws keyword when the exception occurs at runtime:

[](https://www.tpointtech.com/java-throws#)[](https://www.tpointtech.com/java-throws#)[](https://www.tpointtech.com/java-throws#)

1. import java.io.*;    
2. class M{    
3.  void method()throws IOException{    
4.   throw new IOException("device error");    
5.  }    
6. }    
7. class Main{    
8.    public static void main(String args[])throws IOException{//declare exception    
9.      M m=new M();    
10.      m.method();    
11.     System.out.println("normal flow...");    
12.   }    
13. }    

When we run the above code, we get the following exception

Exception in thread "main" java.io.IOException: device error
at M.method(Main.java:4)
at Main.main(Main.java:10)