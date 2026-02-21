In Java, a method is used to do a specific work and helps make the program simple and reusable.

## What Is a Method in Java?

A method is a block of code or a collection of statements or a set of code grouped to perform a certain task or operation. It is used to achieve the reusability of code. We write a method once and use it many times. We do not need to write code again and again. It also provides easy modification and readability of code, just by adding or removing a chunk of code. The method is executed only when we call or invoke it.

The most important method in Java is the main() method. If you want to read more about the main() method, refer to the link [Java Main Method](https://www.tpointtech.com/java-main-method).

## Advantages of Using Methods

The following are the advantages of using methods in Java:

- **Reusability:** Methods provide code reusability. Once a method is defined, it can be called multiple times from various parts of the program.
- **Modularity:** Methods help break down complex problems into smaller, manageable pieces.
- **Maintainability:** With methods, updating and debugging code becomes easier since changes in one part of the program do not necessarily impact other parts.
- **Abstraction:** Methods provide a way to encapsulate implementation details, exposing only the necessary parts to the users.

## Method Naming Rules

While defining a method, remember that the method name must be a verb and start with a lowercase letter. If the method name has more than two words, the first name must be a verb followed by an adjective or noun. In the multi-word method name, the first letter of each word must be in uppercase except the first word. For example:

**Single-Word Method Name:** sum(), area()

**Multi-Word Method Name:** areaOfCircle(), stringComparision()

It is also possible that a method has the same name as another method in the same class; it is known as method overloading.

To read more [Java Naming Convention](https://www.tpointtech.com/java-naming-conventions)

## Method Declaration

The method declaration provides information about method attributes, such as visibility, return type, name, and arguments. It has six components that are known as method header, as we have shown in the following figure.

![Method in Java](https://images.tpointtech.com/core/images/method-in-java.png)

### Method Signature

Every method has a method signature. It is a part of the method declaration. It includes the method name and parameter list.

### Access Specifier

Access specifier or modifier is the access type of the method. It specifies the visibility of the method. Java provides four types of access specifiers:

- **public:** The method is accessible to all classes when we use the public specifier in our application.
- **private:** When we use a private access specifier, the method is accessible only in the classes in which it is defined.
- **protected:** When we use a protected access specifier, the method is accessible within the same package or subclasses in a different package.
- **default:** When we do not use any access specifier in the method declaration, Java uses the default access specifier by default. It is visible only from the same package.

### Return Type

Return type is a data type that the method returns. It may have a primitive data type, object, collection, void, etc. If the method does not return anything, we use the void keyword.

### Method Name

It is a unique name that is used to define the name of a method. It must correspond to the functionality of the method. Suppose, if we are creating a method for subtraction of two numbers, the method name must be subtraction(). A method is invoked by its name.

### Parameter List

It is the list of parameters separated by a comma and enclosed in a pair of parentheses. It contains the data type and variable name. If the method has no parameter, leave the parentheses blank.

### Method Body

It is a part of the method declaration. It contains all the actions to be performed. It is enclosed within a pair of curly braces.

The method body is enclosed in curly braces {} and contains the statements that define the functionality or working of the method. For example, consider the following code snippet.

[](https://www.tpointtech.com/method-in-java#)[](https://www.tpointtech.com/method-in-java#)[](https://www.tpointtech.com/method-in-java#)

1. public class Example {  
2.     // Method definition  
3.     public int add(int a, int b) {  
4.         int sum = a + b; // Method body  
5.         return sum; // Return statement  
6.     }  
7. }  

## Types of Methods

There are two types of methods in Java:

- Predefined Method
- User-defined Method

To read more [Types of Methods in Java](https://www.tpointtech.com/types-of-methods-in-java)

### 1. Predefined Method

The methods that are already defined in the Java class libraries are known as **predefined methods**. It is also known as the **standard library method** or **built-in method**. We can directly use these methods just by calling them in the program at any point.

For example, **String.length(), String.equals(), String.compareTo(), Math.sqrt(), Math.pow(),** etc, are predefined methods.

When we call any of the predefined methods in our program, a series of code related to the corresponding method runs in the background.

### Example

[](https://www.tpointtech.com/method-in-java#)[](https://www.tpointtech.com/method-in-java#)[](https://www.tpointtech.com/method-in-java#)

1. public class Main {  
2.   public static void main(String[] args) {  
3.     // pow() is an in-built function defined in the Math class  
4.     System.out.println("2 raised to the power of 5 is: " + Math.pow(2, 5));  
5.   }  
6. }  

**Output:**

2 raised to the power of 5 is: 32.0

### 2. User-Defined Method

The method written by the user or programmer is known as **a user-defined** method. These methods can be modified or customized according to the requirements.

### Calling User defined Method

In Java, calling or invoking a method depends on whether the method is static or non-static.

If the method is static, we can call it directly using the class name or from within the same class. Note that we need to create an object for calling static methods.

### Syntax

It has the following syntax:

[](https://www.tpointtech.com/method-in-java#)[](https://www.tpointtech.com/method-in-java#)[](https://www.tpointtech.com/method-in-java#)

1. static void display() {  
2. // code  
3. }   
4. Empolyee.display(); // no need to create an object  

If the method is non-static, we must create an object of the class and use it to call the method.

**Note:** We will get a compile-time error if we try to call a non-static method from a static context without an object because non-static methods belong to instances, not the class itself.

[](https://www.tpointtech.com/method-in-java#)[](https://www.tpointtech.com/method-in-java#)[](https://www.tpointtech.com/method-in-java#)

1. Empolyee emp = new Empolyee();  
2. emp.display(); // method called using object reference  

### Example

Let us take an example to demonstrate how we can call the user defined function in Java.

[](https://www.tpointtech.com/method-in-java#)[](https://www.tpointtech.com/method-in-java#)[](https://www.tpointtech.com/method-in-java#)

1. public class Main {  
2.     // Static method  
3.     static void greet() {  
4.         System.out.println("Hello from the static method!");  
5.     }  
6.     // Non-static method  
7.     void farewell() {  
8.         System.out.println("Goodbye from a non-static method!");  
9.     }  
10.     public static void main(String args[]) {  
11.         Main obj = new Main();  
12.         obj.farewell(); //calling non-static method  
13.         Main.greet(); //calling static method  
14.     }  
15. }  

**Output:**

Goodbye from a non-static method!
Hello from the static method!