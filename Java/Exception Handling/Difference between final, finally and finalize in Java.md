The final, finally, and finalize are keywords in Java that are used in exception handling. Each of these keywords has a different functionality. The basic **difference between [final](https://www.tpointtech.com/final-keyword), [finally](https://www.tpointtech.com/finally-block-in-exception-handling) and [finalize](https://www.tpointtech.com/java-object-finalize-method)** is that **final is an access modifier, finally is the block in Exception Handling and finalize is the method of the object class.**

## final Keyword

A final is a keyword used to restrict changes. A final variable cannot be reassigned, a final method cannot be overridden, and a final class can't be subclassed. It ensures immutability and is often used for constants.

### Characteristics of final Keyword

There are several characteristics of the final keyword.

- **Used to declare constants:** A final variable's value cannot be changed once assigned.
- **Prevents method overriding:** A final method cannot be overridden in a subclass.
- **Restricts inheritance:** A final class cannot be extended by any other class.

### final Keyword Example

Let's consider the following example where we have declared a final variable age. Once declared, it cannot be modified.

[](https://www.tpointtech.com/difference-between-final-finally-and-finalize#)[](https://www.tpointtech.com/difference-between-final-finally-and-finalize#)[](https://www.tpointtech.com/difference-between-final-finally-and-finalize#)

1. public class Main {    
2.     //declaring final variable    
3.     final int age = 18;    
4.     void display() {    
5.     // reassigning value to age variable     
6.     // gives compile time error    
7.     age = 55;    
8.     }    
9.     public static void main(String[] args) {    
10.    Main obj = new Main();    
11.     // gives compile time error    
12.     obj.display();    
13.     }    
14. }    

When we compile the above program, we get the following error.

Main.java:7: error: cannot assign a value to final variable age
age = 55;
^
1 error

In the above example, we have declared a variable final. Similarly, we can declare the methods and classes final using the final keyword.

## finally Block

A finally is a block used with try-catch statements to execute important code like closing resources. It always runs whether an exception occurs or not, ensuring cleanup actions are performed.

### Characteristics of finally

There are several characteristics of the finally method in Java.

- **Part of exception handling**: It is used with try and catch blocks.
- **Always executes**: It runs regardless of whether an exception is thrown or caught.
- **Used for resource cleanup**: Like closing files, database connections, etc.

### Java finally Block Example

Let's see the example below where the [Java](https://www.tpointtech.com/java-tutorial) code throws an exception and the catch block handles that exception. Later, the finally block is executed after the [try-catch block](https://www.tpointtech.com/try-catch-block). Further, the rest of the code is also executed normally.

[](https://www.tpointtech.com/difference-between-final-finally-and-finalize#)[](https://www.tpointtech.com/difference-between-final-finally-and-finalize#)[](https://www.tpointtech.com/difference-between-final-finally-and-finalize#)

1. public class Main {      
2.       public static void main(String args[]){     
3.       try {      
4.         System.out.println("Inside try block");    
5.       //The below code throws a divide by zero exception    
6.        int data=25/0;      
7.        System.out.println(data);      
8.       }     
9.       // handles the Arithmetic Exception / Divide by zero exception    
10.       catch (ArithmeticException e){    
11.         System.out.println("Exception handled");    
12.         System.out.println(e);    
13.       }     
14.       // executes regardless of exception occurred or not     
15.       finally {    
16.         System.out.println("finally block is always executed");    
17.       }      
18.       System.out.println("rest of the code...");      
19.       }      
20.     }      

**Output:**

Inside try block
Exception handled
java.lang.ArithmeticException: / by zero
finally block is always executed
rest of the code...

## finalize() Method

A finalize() is a method called by the garbage collector before an object is destroyed. It's used to perform cleanup operations like releasing resources, but it is deprecated and not recommended in modern Java.

### Characteristics of finalize() Method

There are several characteristics of the finalize() method.

- **Defined in java.lang.Object class:** Can be overridden by any class.
- **Called by the garbage collector:** Just before destroying an object.
- **Used for cleanup:** Freeing resources like file handles or network sockets.
- **Not reliable:** No guarantee it will be executed timely or at all.

### finalize() Method Example

The following example demonstrate the finalize() method.

[](https://www.tpointtech.com/difference-between-final-finally-and-finalize#)[](https://www.tpointtech.com/difference-between-final-finally-and-finalize#)[](https://www.tpointtech.com/difference-between-final-finally-and-finalize#)

1. public class Main {  
2.     @Override  
3.     protected void finalize() throws Throwable {  
4.         System.out.println("finalize() method called before object is garbage collected.");  
5.     }  
6.     public static void main(String[] args) {  
7.         Main obj = new Main();  
8.         obj = null; // Eligible for garbage collection  
9.         // Request JVM to run Garbage Collector  
10.         System.gc();  
11.         System.out.println("Main method completed.");  
12.     }  
13. }  

**Output:**

Main method completed.
finalize() method called before object is garbage collected.

## final Vs. finally Vs. finalize() in Java

A list of differences between final, finally and finalize is given below:

|Aspect|final|finally|finalize()|
|---|---|---|---|
|**Definition**|final is the keyword and access modifier that is used to apply restrictions on a class, method or variable.|finally is the block in Java Exception Handling to execute the important code whether the exception occurs or not.|finalize is the method in Java that is used to perform cleanup processing just before an object is garbage collected.|
|Applicable to|The final keyword is used with the classes, methods and variables.|Finally block is always related to the try and catch block in exception handling.|The finalize() method is used with the objects.|
|**Functionality**|(1) Once declared, a final variable becomes a constant and cannot be modified.  <br>(2) The final method cannot be overridden by sub class.  <br>(3) The final class cannot be inherited.|(1) finally block runs the important code even if an exception occurs or not.  <br>(2) The finally block cleans up all the resources used in a try block|The finalize() method performs the cleaning activities with respect to the object before its destruction.|
|**Execution**|The final method is executed only when we call it.|Finally block is executed as soon as the try-catch block is executed.  <br>Its execution is not dependant on the exception.|The finalize() method is executed just before the object is destroyed.|
|**Inheritance/Overriding**|Prevents method overriding and class inheritance.|Not related to inheritance or overriding.|Can be overridden from the Object class.|
|**Use Case**|To create constants, prevent subclassing or method overriding.|To ensure resource cleanup, like closing files, streams, etc., in exception handling.|To perform cleanup activities like memory/resource release before the object is collected.|
|**Control**|Gives compile-time control to avoid unintended changes.|Provides runtime control to handle cleanup post-exception or normal flow.|Invoked by JVM (Java Virtual Machine); the programmer cannot call it directly for cleanup.|
|**Example**|final int x=10;|Finally{closeResource|protected void finalize|