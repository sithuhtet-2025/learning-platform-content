In Java, both **abstract classes** and **interfaces** help in achieving abstraction, but they are used in different ways. **Abstract classes** are for sharing common functionality among related classes, while **interfaces** define a set of methods that any class can implement. In this chapter, we will learn the main differences between them.

## Abstract Class

A class that is declared with the **abstract** keyword is known as an abstract class. It can have abstract and non-abstract methods (methods with a body). An [abstract class](https://www.tpointtech.com/abstract-class-in-java) is a class that cannot be instantiated directly. It serves as a blueprint for other classes.

### Example

The following example demonstrates the abstract class in Java:

### Source Code

[](https://www.tpointtech.com/difference-between-abstract-class-and-interface#)[](https://www.tpointtech.com/difference-between-abstract-class-and-interface#)[](https://www.tpointtech.com/difference-between-abstract-class-and-interface#)

1. //Simple Example of Abstract Class in Java    
2. abstract class Shape{      
3.     abstract void draw();      
4. }      
5. //Child class that provides implementation    
6. class Rectangle extends Shape{      
7.     void draw(){System.out.println("drawing rectangle");}      
8. }      
9. //Main class to create objects and call methods    
10. public class Main{      
11.  public static void main(String args[]){      
12.     Shape s=new Rectangle();    
13.     s.draw();      
14.  }      
15. }     

**Output:**

drawing rectangle

## Interface

An [interface](https://www.tpointtech.com/interface-in-java) is a blueprint of a class. It has static constants and abstract methods.

Interface is a mechanism to achieve abstraction and multiple inheritance in Java. It can have only abstract methods (methods without a body).

- Java Interface also represents the IS-A relationship.

- It cannot be instantiated just like the abstract class.

- Since Java 8, we can have default and static methods in an interface.

- Since Java 9, we can have private methods in an interface.

### Example

The following example demonstrates implementation of an interface:

### Source Code

[](https://www.tpointtech.com/difference-between-abstract-class-and-interface#)[](https://www.tpointtech.com/difference-between-abstract-class-and-interface#)[](https://www.tpointtech.com/difference-between-abstract-class-and-interface#)

1. //Simple Example of Interface in Java    
2. interface Shape{      
3.     void draw();  //by default public and abstract    
4. }      
5. //Child class that provides implementation    
6. class Rectangle implements Shape{      
7.     //Overridden Method must be public    
8.     public void draw(){System.out.println("drawing rectangle");}      
9. }      
10. //Main class to create objects and call methods    
11. public class Main{      
12.  public static void main(String args[]){      
13.     Shape s=new Rectangle();    
14.     s.draw();      
15.  }      
16. }  

**Output:**

drawing rectangle

## Difference between Abstract Class and Interface

The abstract class achieves partial abstraction (0 to 100%), whereas the interface achieves full abstraction (100%). The following table shows the key differences between difference between abstract class and interface:

|Abstract Class|Interface|
|---|---|
|Abstract classes can have abstract and non-abstract methods.|An interface can have only abstract methods. Since Java 8, it can have default and static methods also.|
|Abstract class does not support multiple inheritance.|Interface supports multiple inheritance.|
|Abstract class can have final, non-final, static and non-static variables.|An interface has only static and final variables.|
|Abstract class can provide the implementation of the interface.|An interface cannot provide the implementation of an abstract class.|
|The abstract keyword is used to declare an abstract class.|The interface keyword is used to declare an interface.|
|An abstract class can extend another Java class and implement multiple Java interfaces.|An interface can extend another Java interface only.|
|An abstract class can be extended using the keyword "extends".|An interface can be implemented using the keyword "implements".|
|A Java abstract class can have class members like private, protected, etc.|Members of a Java interface are public by default.|
|**Example:**  <br>public abstract class Shape{  <br>public abstract void draw();  <br>}|**Example:**  <br>public interface Drawable{  <br>void draw();  <br>}|

### Example to Understand Abstract Class Vs Interface

The following example demonstrates how an abstract class can provide partial implementation of an interface, while a subclass completes the remaining methods.

### Example Code

[](https://www.tpointtech.com/difference-between-abstract-class-and-interface#)[](https://www.tpointtech.com/difference-between-abstract-class-and-interface#)[](https://www.tpointtech.com/difference-between-abstract-class-and-interface#)

1. //Creating an interface that has four methods      
2. interface A{      
3.     void a();//by default, public and abstract      
4.     void b();      
5.     void c();      
6.     void d();      
7. }      
8. //Creating an abstract class that provides the implementation of one method of A   
9. // interface      
10. abstract class B implements A{      
11.     public void c(){System.out.println("I am C");}      
12. }      
13. //Creating subclass of the abstract class, now we need to provide the implementation   
14. // of the rest of the methods      
15. class C extends B{      
16.     public void a(){System.out.println("I am a");}      
17.     public void b(){System.out.println("I am b");}      
18.     public void d(){System.out.println("I am d");}      
19. }      
20. // Creating a Main class that calls the methods of an interface      
21. public class Main {      
22.  public static void main(String args[]){      
23.     A a=new C();      
24.     a.a();      
25.     a.b();      
26.     a.c();      
27.     a.d();      
28.  }    
29. }   

**Output:**

I am a
I am b
I am c
I am d

## Abstract Class Vs Interface Summary

The quick summary of this chapter is:

- **Abstraction Level:** Abstract classes provide partial abstraction (0–100%), while interfaces provide full abstraction (100%).
- **Multiple Inheritance:** Interfaces support multiple inheritance; a class can implement multiple interfaces, but can extend only one abstract class.
- **Members and Constructors:** Abstract classes can have constructors, instance variables, and any access modifiers; interface members are public, static, and final by default, and interfaces have no constructors.
- **Use Cases:** Use abstract classes to share code among related classes; use interfaces to define a contract or capability for multiple classes.