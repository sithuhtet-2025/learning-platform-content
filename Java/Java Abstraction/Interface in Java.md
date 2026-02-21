An **interface** in Java is used to define a common set of methods that a class must implement. An interface helps in achieving abstraction and supports multiple inheritance. In this chapter, we will learn how to define an interface, how to achieve abstraction and multiple inheritance using interfaces.

## What is Interface in Java?

An **interface** is a blueprint of a class that contains **static constants** and **abstract methods**. Interfaces are used to achieve **abstraction**. An interface contains only abstract methods (methods without a body) and variables. It cannot be instantiated, similar to an [abstract class](https://www.tpointtech.com/abstract-class-in-java), and represents an **IS-A relationship**.

Since **Java 8**, interfaces can include **default** and **static** methods. Since **Java 9**, interfaces can also contain **private** methods.

## Why Use an Interface in Java?

An interface is used in Java for the following reasons:

- **To achieve abstraction** by defining method signatures without implementation.
- **To support multiple inheritance**, as a class can implement multiple interfaces.
- **To achieve loose coupling**, making the code more flexible and easier to maintain.

## Declaring an Interface

An interface is declared using the **interface** keyword. It provides **complete abstraction**, which means all methods are abstract by default, and all fields are **public, static, and final**. A class that implements an interface must provide implementations for all the methods declared in the interface.

### Syntax of Interface Declaration

Here is the syntax to declare an interface:

[](https://www.tpointtech.com/interface-in-java#)[](https://www.tpointtech.com/interface-in-java#)[](https://www.tpointtech.com/interface-in-java#)

1. interface <interface_name> {  
2.     // declare constant fields  
3.     // declare abstract methods  
4. }  

### Example of Declaring an Interface

Here is an example to declare an interface:

[](https://www.tpointtech.com/interface-in-java#)[](https://www.tpointtech.com/interface-in-java#)[](https://www.tpointtech.com/interface-in-java#)

1. interface Animal {  
2.     void eat();  
3.     void sleep();  
4. }  

In this example, the **Animal** interface declares two methods: **eat()** and **sleep()**. Any class that implements the **Animal** interface must provide concrete implementations for these methods.

## Implicit Modifiers Added by the Java Compiler

In a Java interface, the compiler automatically adds certain modifiers to its members. All **methods** are implicitly declared as **public** and **abstract**, even if these keywords are not explicitly written. Similarly, all **fields** declared in an interface are implicitly **public**, **static**, and **final**.

In other words, interface methods are **public and abstract by default**, while interface fields are **public, static, and final by default**.

Since Java 8, interfaces can include **default** and **static** methods, which are discussed later in this chapter.

## Relationship Between Classes and Interfaces

As shown in the following figure, a class extends another class, an interface extends another interface, and a class implements an interface. This relationship defines how classes and interfaces interact and support inheritance and abstraction in Java.

![The relationship between class and interface](https://d2jdgazzki9vjm.cloudfront.net/core/images/interface-in-java.png)

## Interface Examples

Practice the following examples to understand how interfaces are declared, implemented, and used in Java.

### Example 1: Printable Interface

The following example shows an interface with a single method. The implementation of the interface is provided by a class.

### Example

[](https://www.tpointtech.com/interface-in-java#)[](https://www.tpointtech.com/interface-in-java#)[](https://www.tpointtech.com/interface-in-java#)

1. //Creating an interface  
2. interface Printable{      
3.   void print();      
4. }    
5. //Creating a class that implements Printable    
6. class Printer implements Printable{      
7.   public void print(){System.out.println("Hello");}   
8. }  
9. //Creating a class that creates objects and call methods  
10. public class Main{  
11.   public static void main(String args[]){      
12.     Printable p=new Printer();  
13.     p.print();    
14.  }      
15. }      

**Output:**

Hello

### Example 2: Drawable Interface

The following example demonstrates how multiple classes can implement the same interface. In a real scenario, the interface is usually defined by one party, while different classes provide their own implementations. The implementation details remain hidden from the user.

### Example

[](https://www.tpointtech.com/interface-in-java#)[](https://www.tpointtech.com/interface-in-java#)[](https://www.tpointtech.com/interface-in-java#)

1. //Creating an interface    
2. interface Drawable{    
3.   void draw();    
4. }    
5. //Implementation of Interface   
6. class Rectangle implements Drawable{    
7.   public void draw(){System.out.println("drawing rectangle");}    
8. }    
9. class Circle implements Drawable{    
10.   public void draw(){System.out.println("drawing circle");}    
11. }    
12. //Using interface   
13. public class Main{    
14.   public static void main(String args[]){    
15.     Drawable d=new Circle();//In real scenario, object is provided by method e.g. getDrawable()    
16.     d.draw();    
17.   }  
18. }    

**Output:**

drawing circle

### Example 3: Bank Interface

This example shows how an interface can be used to provide a common structure for related classes. Each bank class provides its own implementation of the interface method.

### Example

[](https://www.tpointtech.com/interface-in-java#)[](https://www.tpointtech.com/interface-in-java#)[](https://www.tpointtech.com/interface-in-java#)

1. interface Bank{    
2.   float rateOfInterest();    
3. }    
4. class SBI implements Bank{    
5.   public float rateOfInterest(){return 9.15f;}    
6. }    
7. class PNB implements Bank{    
8.   public float rateOfInterest(){return 9.7f;}    
9. }    
10. class HDFC implements Bank{    
11.   public float rateOfInterest(){return 8.7f;}    
12. }    

13. public class Main{    
14.   public static void main(String[] args){    
15.     Bank b;  
16.     b=new SBI();    
17.     System.out.println("SBI ROI: "+b.rateOfInterest());   
18.     b=new PNB();    
19.     System.out.println("PNB ROI: "+b.rateOfInterest());   
20.     b=new HDFC();    
21.     System.out.println("HDFC ROI: "+b.rateOfInterest());   
22.   }  
23. }   

**Output:**

SBI ROI: 9.15
PNB ROI: 9.7
HDFC ROI: 8.7

## Implementing Multiple Inheritance Using Interfaces

When a class implements multiple interfaces, or an interface extends more than one interface, it is known as **multiple inheritance**.

In other words, **multiple inheritance** is implemented by allowing a class to implement multiple interfaces or an interface to extend **multiple interfaces**.

![multiple inheritance in java](https://d2jdgazzki9vjm.cloudfront.net/core/images/interface-in-java2.png)

### Example

The following example demonstrates how a class can implement multiple interfaces to achieve multiple inheritance.

[](https://www.tpointtech.com/interface-in-java#)[](https://www.tpointtech.com/interface-in-java#)[](https://www.tpointtech.com/interface-in-java#)

1. //Creating two interfaces  
2. interface Printable{    
3.   void print();    
4. }    
5. interface Showable{    
6.   void show();    
7. }    
8. //Creating a class that implements two interfaces  
9. class Computer implements Printable,Showable{    
10.   public void print(){System.out.println("printing data...");}    
11.   public void show(){System.out.println("showing data...");}    
12. }  
13. //Creating a Main class to create object and call methods  
14. public class Main{  
15.   public static void main(String args[]){    
16.     Computer c = new Computer();    
17.     c.print();    
18.     c.show();    
19.  }    
20. }    

**Output:**

printing data...
showing data...

## Inheritance of Interfaces

A class implements an interface, whereas an interface can extend another interface. When one interface extends another, it inherits all the abstract methods of the parent interface.

A class that implements the child interface must provide implementations for all methods declared in both the parent and child interfaces.

### Example

The following example demonstrates how one interface can inherit another interface and how a class implements the child interface by providing implementations for all inherited methods.

[](https://www.tpointtech.com/interface-in-java#)[](https://www.tpointtech.com/interface-in-java#)[](https://www.tpointtech.com/interface-in-java#)

1. interface Printable{    
2. void print();    
3. }    
4. interface Showable extends Printable{    
5. void show();    
6. }    
7. class Main implements Showable{    
8. public void print(){System.out.println("Hello");}    
9. public void show(){System.out.println("Welcome");}    

10. public static void main(String args[]){    
11. Main obj = new Main();    
12. obj.print();    
13. obj.show();    
14.  }    
15. }    

**Output:**

Hello
Welcome

## Interfaces and Polymorphism

One of the main benefits of interfaces is that they support polymorphism. An interface reference can point to any object of a class that implements it. This allows the program to decide at runtime which method implementation to use.

### Example

The following example demonstrates how an interface reference can point to an object of a class that implements it, showing polymorphic behavior.

[](https://www.tpointtech.com/interface-in-java#)[](https://www.tpointtech.com/interface-in-java#)[](https://www.tpointtech.com/interface-in-java#)

1. // Interface  
2. interface Animal {  
3.     void eat();  
4.     void sleep();  
5. }  

6. // Implementation class  
7. class Dog implements Animal {  
8.     public void eat() {  
9.         System.out.println("Dog is eating");  
10.     }  
11.     public void sleep() {  
12.         System.out.println("Dog is sleeping");  
13.     }  
14. }  

15. // Main class  
16. public class Main {  
17.     public static void main(String[] args) {  
18.         // Interface reference pointing to Dog object  
19.         Animal myAnimal = new Dog();  
20.         myAnimal.eat();  
21.         myAnimal.sleep();  
22.     }  
23. }  

**Output:**

Dog is eating
Dog is sleeping

In this example, myAnimal is an interface reference variable of type Animal, referring to a Dog object. It demonstrates polymorphic behavior, where the method calls are resolved at runtime based on the actual object type.

## Java 8 Default Method in Interface

Since Java 8, we can have method body in interface. But we need to make it default method. Let's see an example:

### Example

[](https://www.tpointtech.com/interface-in-java#)[](https://www.tpointtech.com/interface-in-java#)[](https://www.tpointtech.com/interface-in-java#)

1. interface Drawable{    
2. void draw();    
3. default void msg(){System.out.println("default method");}    
4. }    
5. class Rectangle implements Drawable{    
6. public void draw(){System.out.println("drawing rectangle");}    
7. }    
8. public class Main{    
9. public static void main(String args[]){    
10. Drawable d=new Rectangle();    
11. d.draw();    
12. d.msg();    
13. }  
14. }    

**Output:**

drawing rectangle
default method

## Java 8 Static Method in Interface

Since Java 8, we can have static methods in the interface. Let's see an example:

### Example

[](https://www.tpointtech.com/interface-in-java#)[](https://www.tpointtech.com/interface-in-java#)[](https://www.tpointtech.com/interface-in-java#)

1. interface Drawable{    
2. void draw();    
3. static int cube(int x){return x*x*x;}    
4. }    
5. class Rectangle implements Drawable{    
6. public void draw(){System.out.println("drawing rectangle");}    
7. }    

8. class Main{    
9. public static void main(String args[]){    
10. Drawable d=new Rectangle();    
11. d.draw();    
12. System.out.println(Drawable.cube(3));    
13. }}    

**Output:**

drawing rectangle
27

## Nested Interface

An interface can be declared inside another interface. Such interfaces are called [nested interfaces](https://www.tpointtech.com/nested-interface). A class can implement the **outer interface**, the **nested interface**, or both, depending on the requirement.

### Example

The following example demonstrates how to declare and implement a nested interface:

[](https://www.tpointtech.com/interface-in-java#)[](https://www.tpointtech.com/interface-in-java#)[](https://www.tpointtech.com/interface-in-java#)

1. // Outer interface  
2. interface Printable {    
3.     void print();    

4.     // Nested interface  
5.     interface MessagePrintable {    
6.         void msg();    
7.     }    
8. }    

9. // Class implementing the outer interface  
10. class Printer implements Printable {    
11.     public void print() {    
12.         System.out.println("Printing document...");    
13.     }    
14. }    

15. // Class implementing the nested interface  
16. class MessagePrinter implements Printable.MessagePrintable {    
17.     public void msg() {    
18.         System.out.println("Printing message...");    
19.     }    
20. }    

21. // Main class to test the implementation  
22. public class Main {    
23.     public static void main(String[] args) {    
24.         Printable p = new Printer();    
25.         p.print();    

26.         Printable.MessagePrintable mp = new MessagePrinter();    
27.         mp.msg();    
28.     }    
29. }    

**Output:**

Printing document...
Printing message...

## Interface Vs. Abstract Class

An **abstract class** can have both abstract and concrete methods, constructors, and different types of variables, but it does not support multiple inheritance. An **interface** can only declare abstract methods (with default and static methods allowed since Java 8), has no constructors, and supports multiple inheritance.

Read more about the differences between abstract class and interfaces here: [Java - Abstract Class Vs. Interfaces](https://www.tpointtech.com/difference-between-abstract-class-and-interface)