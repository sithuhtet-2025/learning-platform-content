In Java, there are two keywords i.e. [throw](https://www.tpointtech.com/throw-keyword) and [throws](https://www.tpointtech.com/throws-keyword-and-difference-between-throw-and-throws) are used in exception handling to declare exceptions.

## Java throw Keyword

The ["throw" keyword](https://www.tpointtech.com/java-throw-exception) in Java is used to explicitly throw an exception. It disrupts the normal flow of the program by transferring control to the nearest catch block that can handle the thrown exception. When an exception occurs within a method, the method creates an exception object and throws it using the "throw" keyword.

### Example

The following example demonstrates the use of the throw keyword to explicitly raise an exception when a method receives an invalid input.

[](https://www.tpointtech.com/difference-between-throw-and-throws-in-java#)[](https://www.tpointtech.com/difference-between-throw-and-throws-in-java#)[](https://www.tpointtech.com/difference-between-throw-and-throws-in-java#)

1. public class Main {  
2.     // defining a method  
3.     public static void checkNum(int n) {  
4.         if (n < 1) {  
5.             throw new ArithmeticException("\nNumber is negative, cannot calculate square");  
6.         } else {  
7.             System.out.println("Square of " + n + " is " + (n * n));  
8.         }  
9.     }  
10.     // main method  
11.     public static void main(String[] args) {  
12.         Main obj = new Main();  
13.         obj.checkNum(-3);  
14.         System.out.println("Rest of the code..");  
15.     }  
16. }  

**Output:**

Exception in thread "main" java.lang.ArithmeticException:
Number is negative, cannot calculate square
at Main.checkNum(Main.java:5)
at Main.main(Main.java:13)

**Explanation**

The Main class defines a method named "checkNum()" that takes an integer parameter. Within this method, it checks if the input number is less than 1. If so, it throws an ArithmeticException with a message indicating that the number is negative and its square cannot be calculated. Otherwise, if the number is positive or zero, it calculates and prints the square of the number.

In the main() method, an instance of Main is created, and the "checkNum()" method is called with a negative integer (-3) as an argument. Since the input number is negative, the method throws an ArithmeticException, which is not caught within the main method. Consequently, the program terminates prematurely after printing the exception message.

Therefore, the statement "Rest of the code." is not executed. The code illustrates how to use the "throw" keyword to explicitly throw an exception in Java when certain conditions are met, thereby controlling program flow based on runtime conditions.

## Java throws Keyword

On the other hand, the ["throws"](https://www.tpointtech.com/java-throws) clause is used in method signatures to indicate that the method may throw certain types of exceptions during its execution. It does not actually throw the exception; instead, it declares that the method may throw exceptions of specified types, thereby alerting the caller to handle them appropriately.

### Example

The following example demonstrates the use of the throws keyword to declare an exception and handle it in the calling method using a try-catch block.

[](https://www.tpointtech.com/difference-between-throw-and-throws-in-java#)[](https://www.tpointtech.com/difference-between-throw-and-throws-in-java#)[](https://www.tpointtech.com/difference-between-throw-and-throws-in-java#)

1. public class Main {  
2.     // defining a method  
3.     public static int divideNum(int m, int n) throws ArithmeticException {  
4.         int div = m / n;  
5.         return div;  
6.     }  
7.     // main method  
8.     public static void main(String[] args) {  
9.         Main obj = new Main();  
10.         try {  
11.             System.out.println(obj.divideNum(45, 0));  
12.         } catch (ArithmeticException e) {  
13.             System.out.println("Number cannot be divided by 0");  
14.         }  
15.         System.out.println("Rest of the code..");  
16.     }  
17. }  

**Output:**

Exception caught: Number is negative, cannot calculate square
Program continues...

**Explanation**

The Main class defines a method named "divideNum()" that takes two integer parameters and returns the result of dividing the first parameter by the second. The method is declared with a "throws ArithmeticException" clause, indicating that it may throw an ArithmeticException if the second parameter is zero, resulting in a division by zero error.

In the main() method, an instance of the Main class is created, and the "divideNum()" method is called within a try block. If an ArithmeticException is thrown during the method invocation, it is caught by the catch block, which prints a message indicating that division by zero is not allowed.

Regardless of whether an exception occurs, the program continues to execute the remaining code, printing "**Rest of the code**." to the console. The code demonstrates how to use the "throws" keyword to specify potential exceptions in a method signature and how to handle these exceptions using a try-catch block in Java.

## Difference Between throw and throws Keywords

The following table shows the key differences between difference between throw and throws keywords:

|Characteristics|throw|throws|
|---|---|---|
|**Definition**|Java throw keyword is used throw an exception explicitly in the code, inside the function or the block of code.|Java throws keyword is used in the method signature to declare an exception which might be thrown by the function while the execution of the code.|
|**Declaration**|It is used inside a method or block.|It is used with method signature.|
|**Usage**|Type of exception using throw keyword, we can only propagate unchecked exception i.e., the checked exception cannot be propagated using throw only.|Using throws keyword, we can declare both checked and unchecked exceptions. However, the throws keyword can be used to propagate checked exceptions only.|
|**Purpose**|It triggers the creation and throwing of an exception.|It informs the caller of the method about possible exceptions may occur.|
|**Syntax**|throw new ExceptionType("message");|public void myMethod() throws IOException|
|**Number of Exceptions**|It can throw only one exception at a time.|It can declare multiple exceptions separated by commas.|
|**Followed By**|An instance of Throwable (or subclass).|One or more exception classes (checked exception only).|
|**Internal Implementation**|We are allowed to throw only one exception at a time i.e. we cannot throw multiple exceptions.|We can declare multiple exceptions using throws keyword that can be thrown by the method. For example, main() throws IOException, SQLException.|

## Understanding throw vs throws Using Example

The following example demonstrates how the throws keyword is used to declare a potential exception and how the throw keyword is used to explicitly raise an exception inside a method. The exception is then handled in the calling method using a try-catch block.

### Example

[](https://www.tpointtech.com/difference-between-throw-and-throws-in-java#)[](https://www.tpointtech.com/difference-between-throw-and-throws-in-java#)[](https://www.tpointtech.com/difference-between-throw-and-throws-in-java#)

1. public class Main {    
2.     // creating a user-defined method that raises an ArithmeticException    
3.     static void method() throws ArithmeticException {    
4.         System.out.println("Inside the method()");    
5.         throw new ArithmeticException("Throwing ArithmeticException");    
6.     }    

7.     // main method    
8.     public static void main(String args[]) {    
9.         try {    
10.             method();    
11.         } catch (ArithmeticException err) {    
12.             System.out.println("Caught in main() method");    
13.         }    
14.     }    
15. }  

**Output:**

Inside the method()
Caught in main() method

**Explanation**

In this program, the method() is declared with throws ArithmeticException, indicating it may throw an exception. Inside method(), an ArithmeticException is explicitly thrown after printing a message. In main(), the method is called within a try block, and the exception is caught in the catch block. The output first shows "Inside the method()" and then "Caught in main() method". This demonstrates how throws declares potential exceptions and throw raises them, while try-catch handles them.