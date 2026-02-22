In Java, **abstraction** is one of the important concepts of [object-oriented programming system](https://www.tpointtech.com/java-oops-concepts). Abstraction is used to hide implementation details and showing only essential features to the user. In this chapter, we will learn about abstraction, how to achieve it with different approaches.

## What is Abstraction in Java?

features or capabilities that are necessary to the user. It emphasizes what an object does rather than how it does it.

The following are the important features of abstraction in Java:

- Abstraction shows only the essential functionality while hiding complex implementation details.
- Abstraction allows the use of abstract classes and interfaces to define methods without implementation.
- Changes in implementation do not affect the external code that uses the abstraction.
- Abstraction restricts direct access to internal details.
- Abstraction promotes loose coupling that makes the system easier to scale and maintain.
- Abstraction helps avoid code duplication by defining common behavior in a single place.

## Understanding Abstraction with Real-World Examples

The following real-world examples help explain this concept clearly:

- **ATM Machine:**  
    When we use an ATM, we interact with a simple interface such as entering a PIN, selecting a transaction, and withdrawing cash. The complex internal processes like user authentication, transaction verification, and communication with bank servers remain hidden from the user. This is a practical example of abstraction.
- **Car Driving:**  
    While driving a car, we control it using the steering wheel, accelerator, and brakes without understanding the internal working of the engine, transmission, or braking system. The car abstracts these complexities, allowing the driver to focus only on driving.

## Achieving Abstraction in Java

In Java, abstraction can be achieved in the following two ways:

1. **Using Abstract Class (For Partial Abstraction)**: Abstract class provides partial abstraction by allowing both abstract and implemented methods.
2. **Using Interface (For 100% abstraction)**: Interface provides 100% abstraction by allowing only method declarations, which must be implemented by classes.

Let's understand the both approaches to achieve abstraction in details.

## 1. Abstraction Using Abstract Class

Abstraction can be achieved using an [abstract class](https://www.tpointtech.com/abstract-class-in-java) that may contain **abstract methods** (without a body) as well as **concrete methods** (with implementation). The **abstract methods** define what needs to be done, while subclasses provide how it should be done by implementing those methods.

### Syntax

The following syntax shows how abstraction is implemented in Java using an abstract class with abstract and non-abstract methods:

[](https://www.tpointtech.com/abstraction-in-java#)[](https://www.tpointtech.com/abstraction-in-java#)[](https://www.tpointtech.com/abstraction-in-java#)

1. abstract class ClassName {  
2.     abstract void methodName(); // abstract method  

3.     void normalMethod() {  
4.         // method with implementation  
5.     }  
6. }  

7. class SubClass extends ClassName {  
8.     void methodName() {  
9.         // implementation of abstract method  
10.     }  
11. }  

### Example of Abstraction Using Abstract Class

The following example demonstrates abstraction using an abstract class, where the **Animal** class defines an abstract method and a concrete method, and the **Dog** class provides the implementation of the abstract method.

[](https://www.tpointtech.com/abstraction-in-java#)[](https://www.tpointtech.com/abstraction-in-java#)[](https://www.tpointtech.com/abstraction-in-java#)

1. abstract class Animal {  
2.     abstract void makeSound(); // Abstract method (no implementation)  
3.     void eat() { // Concrete method  
4.         System.out.println("I can eat.");  
5.     }  
6. }  
7. class Dog extends Animal {  
8.     void makeSound() {   //overrides the makeSound() method of the Animal class  
9.         System.out.println("Bark bark");  
10.     }  
11. }  
12. public class Main {  
13.     public static void main(String[] args) {  
14.         Dog d1 = new Dog();  
15.         d1.makeSound(); //invokes the Dog class makeSound() method  
16.         d1.eat();       //invokes the Animal class eat() method  
17.     }  
18. }