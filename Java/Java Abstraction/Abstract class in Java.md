In Java programming, **abstract classes** are used to define the structure and behavior of classes within an inheritance hierarchy. They act as a blueprint for other classes, where some methods may be declared without implementation. In this chapter, we will learn the concept of abstract classes including their features, advantages, and examples.

Before learning about abstract classes in Java, it is necessary to first understand the concept of **abstraction**.

## What is Abstraction in Java?

Abstraction is the process of **hiding implementation details** and showing **only the required functionality** to the user. In other words, it displays only the essential features while hiding internal details.

For example, when sending an SMS, we type the message and send it without knowing how the message is processed or delivered internally.

Abstraction allows you to focus on **what an object does** rather than **how it does it**.

There are two ways to achieve abstraction in Java:

- **Using Abstract Class** (can provide 0% to 100% abstraction)
- **Using Interface** (provides 100% abstraction)

## What is Abstract Class in Java?

A class declared using the **abstract** keyword is known as an **abstract class** in Java. It can contain both **abstract methods** (methods without a body) and **non-abstract methods** (methods with a body).

An abstract class provides **partial abstraction**. It cannot be created on its own and is used only as a parent class. It defines a common structure and shared behavior, while child classes provide their own implementations. Abstract methods do not have a body and must be implemented by the subclasses.

### Points to Remember

- An abstract class must be declared with an **abstract** keyword.

- It can have abstract and non-abstract methods.

- It cannot be instantiated.

- It can have constructors and static methods also.

- It can have final methods which will force the subclass not to change the body of the method.

![Rules for Java Abstract class](https://d2jdgazzki9vjm.cloudfront.net/images/abstract-class-in-java.jpg)

## Creating / Declaring an Abstract Class

An abstract class is created using the **abstract** keyword. It is used as a parent class and cannot be instantiated directly.

### Syntax

Here is the syntax to create an abstract class:

[](https://www.tpointtech.com/abstract-class-in-java#)[](https://www.tpointtech.com/abstract-class-in-java#)[](https://www.tpointtech.com/abstract-class-in-java#)

1. public abstract class Shape {  
2.     public abstract double area();  
3.     public void display() {  
4.         System.out.println("This is a shape.");  
5.     }  
6. }  

In this example, **Shape** is an abstract class. It contains one abstract method **area()** without a body and one concrete method **display()** with an implementation. Any subclass of **Shape** must implement the **area()** method, while it can directly use the **display()** method.

## Abstract Method

A method that is declared using the **abstract** keyword and does not have an implementation (method body) is known as an **abstract method**.

### Example

Here is an example how an abstract method looks like:

[](https://www.tpointtech.com/abstract-class-in-java#)[](https://www.tpointtech.com/abstract-class-in-java#)[](https://www.tpointtech.com/abstract-class-in-java#)

1. abstract void printStatus(); // no method body  

An abstract method only declares the method signature. Its implementation must be provided by the subclass that extends the abstract class.

## Abstract Class with an Abstract Method

The following example shows an abstract class that contains an abstract method. Subclasses must provide the implementation for the abstract method.

Here, **Bike** is an abstract class with the abstract method **run()**. The subclass **Honda** provides the implementation of **run()**. This shows how abstract classes define a method structure while leaving the details to subclasses.

### Example

[](https://www.tpointtech.com/abstract-class-in-java#)[](https://www.tpointtech.com/abstract-class-in-java#)[](https://www.tpointtech.com/abstract-class-in-java#)

1. //Creating an abstract class having abstract method  
2. abstract class Bike{    
3.   abstract void run();    
4. }    
5. //Creating a child class and override abstract method  
6. class Honda extends Bike{    
7. void run(){System.out.println("running safely");}    
8. }  
9. //Creating a Main class to create object and call methods  
10. public class Main{  
11. public static void main(String args[]){    
12.  Bike obj = new Honda();    
13.  obj.run();    
14. }    
15. }   

**Output:**

running safely

## More Examples of Abstract Class

Practice the following examples to better understand the concept of **abstract classes** and how they are used in Java.

### Example 1: Shape Abstract Class

In this example, Shape is an abstract class, and its implementation is provided by the Rectangle and Circle classes. The specific implementation is usually hidden from the end user and may be provided through a **factory method**.

### Example

[](https://www.tpointtech.com/abstract-class-in-java#)[](https://www.tpointtech.com/abstract-class-in-java#)[](https://www.tpointtech.com/abstract-class-in-java#)

1. abstract class Shape{    
2.  abstract void draw();    
3. }    
4. //In real scenario, implementation is provided by others i.e. unknown by end user    
5. class Rectangle extends Shape{    
6.  void draw(){System.out.println("drawing rectangle");}    
7. }    
8. class Circle extends Shape{    
9.  void draw(){System.out.println("drawing circle");}    
10. }    
11. //In real scenario, method is called by programmer or user    
12. public class Main{    
13.  public static void main(String args[]){    
14.   //In a real scenario, object is provided through method, e.g., getShape() method    
15.   Shape s=new Circle();  
16.   s.draw();    
17. }    
18. }    

**Output:**

drawing circle

### Example 2: Bank Abstract Class

This example shows how abstract classes can define a **common interface** for related classes, while subclasses provide their own implementation.

### Example

[](https://www.tpointtech.com/abstract-class-in-java#)[](https://www.tpointtech.com/abstract-class-in-java#)[](https://www.tpointtech.com/abstract-class-in-java#)

1. abstract class Bank{      
2.     abstract int getRateOfInterest();      
3. }      
4. class SBI extends Bank{      
5.     int getRateOfInterest(){return 7;}      
6. }      
7. class PNB extends Bank{      
8.     int getRateOfInterest(){return 8;}      
9. }      

10. public class Main{      
11.  public static void main(String args[]){      
12.   Bank b;    
13.   b=new SBI();    
14.   System.out.println("Rate of Interest is: "+b.getRateOfInterest()+" %");      
15.   b=new PNB();    
16.   System.out.println("Rate of Interest is: "+b.getRateOfInterest()+" %");      
17.  }  
18. }     

**Output:**

Rate of Interest is: 7 %
Rate of Interest is: 8 %

## Abstract Class having Constructor, Data Members, and Methods

An abstract class in Java can contain **data members, abstract methods, concrete methods, constructors**, and even the main() method.

### Example

The following example shows an abstract class Bike with:

- A **constructor** that runs when an object of the subclass is created.
- An **abstract method** run() that must be implemented by subclasses.
- A **concrete method** changeGear() that can be inherited as-is.

### Example

[](https://www.tpointtech.com/abstract-class-in-java#)[](https://www.tpointtech.com/abstract-class-in-java#)[](https://www.tpointtech.com/abstract-class-in-java#)

1. //Example of an abstract class that has abstract and non-abstract methods    
2. abstract class Bike{    
3.    Bike(){System.out.println("bike is created");}    
4.    abstract void run();    
5.    void changeGear(){System.out.println("gear changed");}    
6. }    
7. //Creating a Child class which inherits Abstract class    
8. class Honda extends Bike{    
9.  void run(){System.out.println("running safely..");}    
10. }    
11. //Creating a Main class which calls abstract and non-abstract methods    
12. public class Main{    
13.  public static void main(String args[]){    
14.   Bike obj = new Honda();    
15.   obj.run();    
16.   obj.changeGear();    
17.  }    
18. }    

**Output:**

bike is created
running safely..
gear changed

### Rules of Abstract Classes

1. If a class contains an abstract method, the class itself must be declared abstract.

[](https://www.tpointtech.com/abstract-class-in-java#)[](https://www.tpointtech.com/abstract-class-in-java#)[](https://www.tpointtech.com/abstract-class-in-java#)

1. class Bike12 {    
2.     abstract void run();    
3. }  

**Output:**

compile time error

2. If a subclass extends an abstract class with abstract methods, it must either implement all abstract methods or be declared abstract itself.

[](https://www.tpointtech.com/abstract-class-in-java#)[](https://www.tpointtech.com/abstract-class-in-java#)[](https://www.tpointtech.com/abstract-class-in-java#)

1. abstract class Vehicle {  
2.     abstract void start();  
3. }  

4. // Subclass not implementing abstract method must be abstract  
5. abstract class Car extends Vehicle {  
6. }  

7. // Subclass implementing abstract method can be instantiated  
8. class Honda extends Vehicle {  
9.     void start() {  
10.         System.out.println("Honda started");  
11.     }  
12. }  

13. public class Main {  
14.     public static void main(String[] args) {  
15.         Vehicle v = new Honda();  
16.         v.start();  // Output: Honda started  
17.     }  
18. }  

**Output:**

Honda started

## Another Real Scenario of Abstract Class

The abstract class can also be used to provide some implementation of the interface. In such case, the end user may not be forced to override all the methods of the interface.

#### Note: If we are beginner to Java, learn interface first then see this example.

### Example

[](https://www.tpointtech.com/abstract-class-in-java#)[](https://www.tpointtech.com/abstract-class-in-java#)[](https://www.tpointtech.com/abstract-class-in-java#)

1. interface A{    
2.     void a();    
3.     void b();    
4.     void c();    
5.     void d();    
6. }    

7. abstract class B implements A{    
8.     public void c(){System.out.println("I am c");}    
9. }    

10. class M extends B{    
11.     public void a(){System.out.println("I am a");}    
12.     public void b(){System.out.println("I am b");}    
13.     public void d(){System.out.println("I am d");}    
14. }    

15. public class Main{    
16.     public static void main(String args[]){    
17.         A a=new M();    
18.         a.a();    
19.         a.b();    
20.         a.c();    
21.         a.d();    
22.     }  
23. }   

**Output:**

I am a
I am b
I am c
I am d