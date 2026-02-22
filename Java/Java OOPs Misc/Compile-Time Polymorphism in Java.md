Compile-time polymorphism in Java allows the compiler to decide which method to call based on the method signature. In this chapter, you will learn how Java achieves this using method overloading with practical examples.

## What is Compile-Time Polymorphism?

**Compile-time polymorphism**, also known as **static polymorphism** or **early binding**, is the ability of a programming language to determine which method or function to invoke **at compile time** based on the number, type, and order of parameters. The compile-time polymorphism is achieved through [method overloading](https://www.tpointtech.com/method-overloading-in-java) that allows multiple methods with the same name but different parameter lists to exist within the same class.

## Syntax of Compile-Time Polymorphism

The following syntax shows how compile-time polymorphism is achieved using method overloading:

[](https://www.tpointtech.com/compile-time-polymorphism-in-java#)[](https://www.tpointtech.com/compile-time-polymorphism-in-java#)[](https://www.tpointtech.com/compile-time-polymorphism-in-java#)

1. class ClassName {  
2.     // Method with one parameter  
3.     returnType methodName(dataType param1) {  
4.         // method body  
5.     }  

6.     // Overloaded method with different parameters  
7.     returnType methodName(dataType param1, dataType param2) {  
8.         // method body  
9.     }  
10. }  

## Examples of Compile-Time Polymorphism

Practice the following examples to understand how compile-time polymorphism works using method overloading.

### Example 1: Method Overloading Using Different Data Types

The following example demonstrates compile-time polymorphism by overloading the **add()** method with different parameter data types.

Here's a complete Java code example that demonstrates compile-time polymorphism through method overloading:

[](https://www.tpointtech.com/compile-time-polymorphism-in-java#)[](https://www.tpointtech.com/compile-time-polymorphism-in-java#)[](https://www.tpointtech.com/compile-time-polymorphism-in-java#)

1. public class Calculator {  
2.     public int add(int a, int b) {  
3.         return a + b;  
4.     }  
5.     public double add(double a, double b) {  
6.         return a + b;  
7.     }  
8.     public static void main(String[] args) {  
9.         Calculator calc = new Calculator();  
10.         int sum1 = calc.add(5, 10);  
11.         System.out.println("Sum of 5 and 10 (integers): " + sum1);  
12.         double sum2 = calc.add(2.5, 3.7);  
13.         System.out.println("Sum of 2.5 and 3.7 (doubles): " + sum2);  
14.     }  
15. }  

**Output:**

Sum of 5 and 10 (integers): 15
Sum of 2.5 and 3.7 (doubles): 6.2

A Calculator class with two add methods can be found in the code above. The second method accepts two doubles as arguments and returns the sum as a double, in contrast to the first method's use of two integers and return of their sum as an integer.

In the main method, we construct a Calculator class instance and call the add methods with various arguments. The outcome is displayed on the console, indicating the appropriate compile-time selection of the overloaded methods depending on the argument types.

When you run the code, you ought to see the output that was previously indicated, which verifies that the correct add methods were called based on the parameter types provided during the method calls.

### Example 2: Method Overloading Using Different Number of Parameters

The following example shows compile-time polymorphism by overloading a method with a different number of parameters.

[](https://www.tpointtech.com/compile-time-polymorphism-in-java#)[](https://www.tpointtech.com/compile-time-polymorphism-in-java#)[](https://www.tpointtech.com/compile-time-polymorphism-in-java#)

1. public class MathOperations {  

2.     public int multiply(int a, int b) {  
3.         return a * b;  
4.     }  

5.     public int multiply(int a, int b, int c) {  
6.         return a * b * c;  
7.     }  

8.     public static void main(String[] args) {  
9.         MathOperations obj = new MathOperations();  

10.         int result1 = obj.multiply(2, 3);  
11.         System.out.println("Multiplication of 2 and 3: " + result1);  

12.         int result2 = obj.multiply(2, 3, 4);  
13.         System.out.println("Multiplication of 2, 3, and 4: " + result2);  
14.     }  
15. }  

**Output:**

Multiplication of 2 and 3: 6
Multiplication of 2, 3, and 4: 24

Here, the compiler determines which multiply() method to call based on the number of arguments provided, demonstrating compile-time polymorphism.

## Compile-Time Polymorphism Using Constructor Overloading

Constructor overloading is a form of compile-time polymorphism where a class has multiple constructors with the same name but different parameter lists. The compiler decides which constructor to call based on the arguments provided at the time of object creation.

### Example

The following example demonstrates compile-time polymorphism using constructor overloading.

[](https://www.tpointtech.com/compile-time-polymorphism-in-java#)[](https://www.tpointtech.com/compile-time-polymorphism-in-java#)[](https://www.tpointtech.com/compile-time-polymorphism-in-java#)

1. class Student {  
2.     int id;  
3.     String name;  

4.     // Constructor with one parameter  
5.     Student(int i) {  
6.         id = i;  
7.         name = "Unknown";  
8.     }  

9.     // Overloaded constructor with two parameters  
10.     Student(int i, String n) {  
11.         id = i;  
12.         name = n;  
13.     }  

14.     public static void main(String[] args) {  
15.         Student s1 = new Student(101);  
16.         Student s2 = new Student(102, "Rahul");  

17.         System.out.println(s1.id + " " + s1.name);  
18.         System.out.println(s2.id + " " + s2.name);  
19.     }  
20. }  

**Output:**

101 Unknown
102 Rahul

## Compile-Time Polymorphism Using Method Overloading with Type Promotion

Method overloading with type promotion occurs when the compiler automatically converts a smaller data type into a larger compatible data type to match a method’s parameter list. This decision is made at compile time.

### Example

The following example demonstrates compile-time polymorphism using method overloading with type promotion:

[](https://www.tpointtech.com/compile-time-polymorphism-in-java#)[](https://www.tpointtech.com/compile-time-polymorphism-in-java#)[](https://www.tpointtech.com/compile-time-polymorphism-in-java#)

1. class TypePromotionExample {  

2.     void display(int a) {  
3.         System.out.println("Integer value: " + a);  
4.     }  

5.     void display(long a) {  
6.         System.out.println("Long value: " + a);  
7.     }  

8.     public static void main(String[] args) {  
9.         TypePromotionExample obj = new TypePromotionExample();  
10.         obj.display(10);  
11.     }  
12. }  

**Output:**

Integer value: 10