In Java, multiple catch blocks allow us to handle different types of exceptions separately. This is useful when a single try block contains code that may throw different types of exceptions.

A **try** block can be followed by one or more catch blocks, and each catch block must handle a different type of exception. This allows you to perform specific actions depending on the type of exception that occurs.

Alternatively, starting from Java 7, we can combine multiple exceptions in a single catch block using the | (pipe) symbol.

## Using Multiple Catch Blocks

A multiple catch block is used when a try block can throw different types of exceptions. Each catch handles a specific exception, and more specific exceptions should come before general ones. From Java 7 onward, multiple exceptions can be handled in a single catch block using the | (pipe) symbol.

### Flowchart

The following image shows the flowchart of the working of multiple catch blocks:

![Java Catch Multiple Exceptions](https://images.tpointtech.com/core/images/multiple-catch-block-in-java.png)

### Syntax

The syntax for using multiple catch blocks:

[](https://www.tpointtech.com/multiple-catch-block-in-java#)[](https://www.tpointtech.com/multiple-catch-block-in-java#)[](https://www.tpointtech.com/multiple-catch-block-in-java#)

1. try {  
2.     // Code that may throw multiple exceptions  
3. } catch (FirstExceptionType e) {  
4.     // Handle first type of exception  
5. } catch (SecondExceptionType e) {  
6.     // Handle second type of exception  
7. } catch (Exception e) {  
8.     // Handle any other exceptions  
9. }  

### Syntax Using Multi-Catch (Java 7 and above)

Here is the syntax to use multiple catch blocks together using the pipe (|) sign:

[](https://www.tpointtech.com/multiple-catch-block-in-java#)[](https://www.tpointtech.com/multiple-catch-block-in-java#)[](https://www.tpointtech.com/multiple-catch-block-in-java#)

1. try {  
2.     // Code that may throw multiple exceptions  
3. } catch (FirstExceptionType | SecondExceptionType e) {  
4.     // Handle either exception  
5. }  

### Example

The following example demonstrates using multiple catch blocks:

[](https://www.tpointtech.com/multiple-catch-block-in-java#)[](https://www.tpointtech.com/multiple-catch-block-in-java#)[](https://www.tpointtech.com/multiple-catch-block-in-java#)

1. // Java Program to demonstrate Multiple Catch Blocks  
2. public class Main {  
3.     public static void main(String[] args) {  
4.         try {  
5.             int[] numbers = {1, 2, 3};  
6.             System.out.println("Number: " + numbers[5]); // May throw ArrayIndexOutOfBoundsException  

7.             int result = 10 / 0; // May throw ArithmeticException  

8.         } catch (ArithmeticException e) {  
9.             System.out.println("Caught ArithmeticException: Division by zero is not allowed.");  
10.         } catch (ArrayIndexOutOfBoundsException e) {  
11.             System.out.println("Caught ArrayIndexOutOfBoundsException: Invalid array index accessed.");  
12.         } catch (Exception e) {  
13.             System.out.println("Caught Exception: Some other exception occurred.");  
14.         }  

15.         System.out.println("Program continues after handling multiple exceptions.");  
16.     }  
17. }  

**Output:**

Caught ArrayIndexOutOfBoundsException: Invalid array index accessed.
Program continues after handling multiple exceptions.

## More Examples on Multiple Catch Blocks

Practice the following examples to understand how multiple catch blocks work in Java.

### Example 1: Handling ArithmeticException

The following example demonstrates how an ArithmeticException is caught using multiple catch blocks.

[](https://www.tpointtech.com/multiple-catch-block-in-java#)[](https://www.tpointtech.com/multiple-catch-block-in-java#)[](https://www.tpointtech.com/multiple-catch-block-in-java#)

1. public class Main {    
2.     public static void main(String[] args) {    
3.            try{      
4.                 int a[]=new int[5];      
5.                 a[5]=30/0;      
6.                }      
7.                catch(ArithmeticException e)    
8.                   {    
9.                    System.out.println("Arithmetic Exception occurs");    
10.                   }      
11.                catch(ArrayIndexOutOfBoundsException e)    
12.                   {    
13.                    System.out.println("ArrayIndexOutOfBounds Exception occurs");    
14.                   }      
15.                catch(Exception e)    
16.                   {    
17.                    System.out.println("Parent Exception occurs");    
18.                   }               
19.                System.out.println("rest of the code");      
20.     }    
21. }  

**Output:**

Arithmetic Exception occurs
rest of the code

### Example 2: Handling ArrayIndexOutOfBoundsException

The following example demonstrates how an ArrayIndexOutOfBoundsException is caught using multiple catch blocks.

[](https://www.tpointtech.com/multiple-catch-block-in-java#)[](https://www.tpointtech.com/multiple-catch-block-in-java#)[](https://www.tpointtech.com/multiple-catch-block-in-java#)

1. public class Main {    
2.     public static void main(String[] args) {    
3.            try{      
4.                 int a[]=new int[5];      
5.                 System.out.println(a[10]);    
6.                }      
7.                catch(ArithmeticException e)    
8.                   {    
9.                    System.out.println("Arithmetic Exception occurs");    
10.                   }      
11.                catch(ArrayIndexOutOfBoundsException e)    
12.                   {    
13.                    System.out.println("ArrayIndexOutOfBounds Exception occurs");    
14.                   }      
15.                catch(Exception e)    
16.                   {    
17.                    System.out.println("Parent Exception occurs");    
18.                   }               
19.                System.out.println("rest of the code");      
20.     }    
21. }    

**Output:**

ArrayIndexOutOfBounds Exception occurs
rest of the code

In this example, the try block contains two exceptions. But at a time only one exception occurs and its corresponding catch block is executed.

### Example 3: Handling the First Occurring Exception

In this example, the try block may throw multiple exceptions, but only the first occurring exception is handled.

[](https://www.tpointtech.com/multiple-catch-block-in-java#)[](https://www.tpointtech.com/multiple-catch-block-in-java#)[](https://www.tpointtech.com/multiple-catch-block-in-java#)

1. public class Main {    
2.     public static void main(String[] args) {    
3.            try{      
4.                 int a[]=new int[5];      
5.                 a[5]=30/0;      
6.                 System.out.println(a[10]);    
7.                }      
8.                catch(ArithmeticException e)    
9.                   {    
10.                    System.out.println("Arithmetic Exception occurs");    
11.                   }      
12.                catch(ArrayIndexOutOfBoundsException e)    
13.                   {    
14.                    System.out.println("ArrayIndexOutOfBounds Exception occurs");    
15.                   }      
16.                catch(Exception e)    
17.                   {    
18.                    System.out.println("Parent Exception occurs");    
19.                   }               
20.                System.out.println("rest of the code");      
21.     }    
22. }  

**Output:**

Arithmetic Exception occurs
rest of the code

### Example 4: Using Parent Exception for Unmatched Exceptions

If the exception does not match a specific catch block, the parent Exception catch block is executed.

[](https://www.tpointtech.com/multiple-catch-block-in-java#)[](https://www.tpointtech.com/multiple-catch-block-in-java#)[](https://www.tpointtech.com/multiple-catch-block-in-java#)

1. public class Main {    
2.     public static void main(String[] args) {    
3.            try{      
4.                 String s=null;    
5.                 System.out.println(s.length());    
6.                }      
7.                catch(ArithmeticException e)    
8.                   {    
9.                    System.out.println("Arithmetic Exception occurs");    
10.                   }      
11.                catch(ArrayIndexOutOfBoundsException e)    
12.                   {    
13.                    System.out.println("ArrayIndexOutOfBounds Exception occurs");    
14.                   }      
15.                catch(Exception e)    
16.                   {    
17.                    System.out.println("Parent Exception occurs");    
18.                   }               
19.                System.out.println("rest of the code");      
20.     }    
21. }   

**Output:**

Parent Exception occurs
rest of the code

### Example 5: General Exception Before Specific Ones (Compile-time Error)

Placing a general exception catch block before specific ones causes a compile-time error.

[](https://www.tpointtech.com/multiple-catch-block-in-java#)[](https://www.tpointtech.com/multiple-catch-block-in-java#)[](https://www.tpointtech.com/multiple-catch-block-in-java#)

1. public class Main {      
2.   public static void main(String args[])  
3.   {      
4.        try  
5.        {      
6.             int a[]=new int[5];      
7.             a[5]=30/0;      
8.        }      
9.        catch(Exception e)  
10.        {  
11.            System.out.println("common task completed");  
12.        }      
13.        catch(ArithmeticException e)  
14.        {  
15.            System.out.println("task1 is completed");  
16.        }      
17.        catch(ArrayIndexOutOfBoundsException e)  
18.        {  
19.            System.out.println("task 2 completed");  
20.        }      
21.        System.out.println("rest of the code...");      
22.      }      
23. }    

**Output:**

Main.java:13: error: exception ArithmeticException has already been caught
catch(ArithmeticException e)
^
Main.java:17: error: exception ArrayIndexOutOfBoundsException has already been caught
catch(ArrayIndexOutOfBoundsException e)