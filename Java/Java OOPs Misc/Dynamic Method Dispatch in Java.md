Dynamic method dispatch in Java allows method calls to be resolved at runtime based on the object's actual type. In this chapter, we will learn how Java achieves runtime polymorphism using method overriding and inheritance.

Before learning dynamic method dispatch, you must be familiar with polymorphism.

## Polymorphism

[Polymorphism](https://www.tpointtech.com/polymorphism-in-java) allows objects to be treated as instances of their parent class, so the same code can work with different types of objects in a simple and uniform way.

### Example

For example, if we have a superclass Animal and subclasses Dog and Cat, we can create an array of Animal objects and store instances of both Dog and Cat in it. We can then iterate through the array and call a method like makeSound() on each element, and the appropriate version of makeSound() from either Dog or Cat will be executed.

[](https://www.tpointtech.com/dynamic-method-dispatch-in-java#)[](https://www.tpointtech.com/dynamic-method-dispatch-in-java#)[](https://www.tpointtech.com/dynamic-method-dispatch-in-java#)

1. class Animal {  
2.     void makeSound() {  
3.         System.out.println("Generic Animal Sound");  
4.     }  
5. }  
6. class Dog extends Animal {  
7.     @Override  
8.     void makeSound() {  
9.         System.out.println("Bark");  
10.     }  
11. }  
12. class Cat extends Animal {  
13.     @Override  
14.     void makeSound() {  
15.         System.out.println("Meow");  
16.     }  
17. }  
18. public class Demo {  
19.     public static void main(String[] args) {  
20.         Animal[] animals = {new Dog(), new Cat()};  

21.         for (Animal animal : animals) {  
22.             animal.makeSound();  
23.         }  
24.     }  
25. }  

**Output:**

Bark
Meow

## What is Dynamic Method Dispatch in Java?

**Dynamic method dispatch** is a technique by which a call to an overridden method is resolved **at runtime** based on the actual object type rather than the reference type. This technique allows runtime polymorphism through [inheritance](https://www.tpointtech.com/inheritance-in-java) and [method overriding](https://www.tpointtech.com/method-overloading-in-java).

**Dynamic method dispatch** or **run-time polymorphism** is the mechanism through which the correct version of an [overridden method](https://www.tpointtech.com/method-overriding-in-java) is called at runtime. When a subclass overrides a method from its superclass, the overridden method in the subclass is executed when called on an instance of the subclass, even if the reference to the object is of the superclass type.

## Syntax of Dynamic Method Dispatch

The following syntax shows how dynamic method dispatch works using **method overriding** and **parent class references**:

[](https://www.tpointtech.com/dynamic-method-dispatch-in-java#)[](https://www.tpointtech.com/dynamic-method-dispatch-in-java#)[](https://www.tpointtech.com/dynamic-method-dispatch-in-java#)

1. class ParentClass {  
2.     void methodName() {  
3.         // Parent class method  
4.     }  
5. }  

6. class ChildClass extends ParentClass {  
7.     @Override  
8.     void methodName() {  
9.         // Overridden method in child class  
10.     }  
11. }  

12. public class Demo {  
13.     public static void main(String[] args) {  
14.         ParentClass obj = new ChildClass();  // Parent reference, child object  
15.         obj.methodName();                     // Calls child’s overridden method at runtime  
16.     }  
17. }  

**Explanation:**

- A parent class reference can refer to a child class object.
- The method call is resolved **at runtime**, not compile time, which is the essence of dynamic method dispatch.

## Example of Dynamic Method Dispatch

For example, in a program with different types of animals, an **Animal** superclass can have a **makeSound()** method, and each subclass (**Dog**, **Cat**) overrides it with its own implementation. This allows writing code that can handle any type of animal without needing to know the specific details of how each one makes a sound.

The following is the complete Java program that demonstrates dynamic method dispatch along with input and output.

[](https://www.tpointtech.com/dynamic-method-dispatch-in-java#)[](https://www.tpointtech.com/dynamic-method-dispatch-in-java#)[](https://www.tpointtech.com/dynamic-method-dispatch-in-java#)

1. class Animal {  
2.     void makeSound() {  
3.         System.out.println("Generic Animal Sound");  
4.     }  
5. }  
6. class Dog extends Animal {  
7.     @Override  
8.     void makeSound() {  
9.         System.out.println("Bark");  
10.     }  
11. }  
12. class Cat extends Animal {  
13.     @Override  
14.     void makeSound() {  
15.         System.out.println("Meow");  
16.     }  
17. }  
18. public class DynamicMethod {  
19.     public static void main(String[] args) {  
20.         Animal[] animals = {new Dog(), new Cat()};  
21.         for (Animal animal : animals) {  
22.             animal.makeSound();  
23.         }  
24.     }  
25. }  

**Output:**

Bark
Meow

In the Main class, we have created an array of **Animal** objects called animals and populate it with an instance of **Dog** and an instance of **Cat**. We then iterate through the animals array using a [for-each loop](https://www.tpointtech.com/for-each-loop-in-java) and call the **makeSound()** method on each element. Due to dynamic method dispatch, the appropriate version of **makeSound()** from either **Dog** or **Cat** will be executed based on the actual type of the object.

## Dynamic Method Dispatch With Abstract Classes

Dynamic method dispatch works very well with abstract classes, because [abstract classes](https://www.tpointtech.com/abstract-class-in-java) can declare methods without implementations, and child classes provide their own versions. This allows the program to decide at **runtime** which implementation to execute based on the actual object type.

### Example

The following example demonstrates dynamic method dispatch with abstract classes.

[](https://www.tpointtech.com/dynamic-method-dispatch-in-java#)[](https://www.tpointtech.com/dynamic-method-dispatch-in-java#)[](https://www.tpointtech.com/dynamic-method-dispatch-in-java#)

1. abstract class Animal {  
2.     // Abstract method  
3.     abstract void makeSound();  
4. }  

5. class Dog extends Animal {  
6.     @Override  
7.     void makeSound() {  
8.         System.out.println("Bark");  
9.     }  
10. }  

11. class Cat extends Animal {  
12.     @Override  
13.     void makeSound() {  
14.         System.out.println("Meow");  
15.     }  
16. }  

17. public class DemoAbstract {  
18.     public static void main(String[] args) {  
19.         // Parent reference holding child objects  
20.         Animal[] animals = {new Dog(), new Cat()};  

21.         for (Animal animal : animals) {  
22.             animal.makeSound();  // Resolved at runtime  
23.         }  
24.     }  
25. }  

**Output:**

Bark
Meow

**Explanation:**

The **Animal** class is abstract and defines an abstract method **makeSound()**, while the **Dog** and **Cat** classes provide their own implementations of this method. By using a parent class reference (**Animal**) to hold child objects, the above code is able to call the appropriate method at runtime.