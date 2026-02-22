Java inner classes are classes defined within another class that are used to improve encapsulation and code organization. In this chapter, we will learn creating and using inner classes with the help of examples.

## What is Inner Class (Nested Classes) in Java?

An **inner class** (or **nested class**) is a class declared inside another class or interface. **Inner classes** help logically group related classes in one place to make the code more readable and maintainable. They can also access all members of the outer class, including private fields and methods.

## Creating Inner Class

An inner class is created by defining a class inside another class. Here are the steps to create an inner class:

1. Define the outer class as usual.
2. Inside the outer class, define the inner class.
3. Access the inner class using an object of the outer class.

### Syntax

Here is the syntax to create an inner class:

[](https://www.tpointtech.com/java-inner-class#)[](https://www.tpointtech.com/java-inner-class#)[](https://www.tpointtech.com/java-inner-class#)

1. class OuterClass {  
2.     // Outer class members  

3.     class InnerClass {  
4.         // Inner class members  
5.     }  
6. }  

### Example

In this example, we have an outer class **Student** with an inner class **Address**. The inner class stores the student's address and displays it along with the student's name.

[](https://www.tpointtech.com/java-inner-class#)[](https://www.tpointtech.com/java-inner-class#)[](https://www.tpointtech.com/java-inner-class#)

1. class Student {  
2.     String name;  

3.     Student(String name) {  
4.         this.name = name;  
5.     }  

6.     // Inner class  
7.     class Address {  
8.         String city, state;  

9.         Address(String city, String state) {  
10.             this.city = city;  
11.             this.state = state;  
12.         }  

13.         void display() {  
14.             System.out.println("Student Name: " + name);  
15.             System.out.println("City: " + city);  
16.             System.out.println("State: " + state);  
17.         }  
18.     }  
19. }  

20. public class TestStudent {  
21.     public static void main(String[] args) {  
22.         // Create outer class object  
23.         Student student = new Student("Rahul");  

24.         // Create inner class object  
25.         Student.Address address = student.new Address("Delhi", "Delhi");  
26.         address.display();  
27.     }  
28. }  

**Output:**

Student Name: Rahul
City: Delhi
State: Delhi

## Advantages of Using Inner Classes

The following are the main two advantages of using inner classes:

- Inner classes can access all members (fields and methods) of the outer class, including private members that allows tight integration between the inner and outer class.
- Inner classes help logically group related classes in one place that makes the code easier to read and maintain.

## Types of Nested Classes

Nested classes are classified into two main types: **non-static nested classes** and **static nested classes**. The **non-static nested classes** are commonly referred to as **inner classes**.

### 1. Non-Static Nested Class (Inner Class)

Inner classes are non-static classes defined within another class. They are further categorized into:

1. [Member Inner Class](https://www.tpointtech.com/member-inner-class): A class defined **inside a class but outside any method**.
2. [Anonymous Inner Class](https://www.tpointtech.com/member-inner-class): A class without a name, typically used **to implement an interface or extend a class**. The compiler automatically assigns a name.
3. [Local Inner Class](https://www.tpointtech.com/local-inner-class): A class **defined inside a method**, available only within that method.

### 2. Static Nested Class

A [static nested class](https://www.tpointtech.com/local-inner-class) is a static class defined within another class. It can access only static members of the outer class directly.

### Nested Interface

An interface defined inside a class or another interface. [Nested interfaces](https://www.tpointtech.com/nested-interface) are often used to logically group related interfaces.