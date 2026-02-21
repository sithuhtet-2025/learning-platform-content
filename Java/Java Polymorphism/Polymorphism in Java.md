Polymorphism in Java is an object-oriented concept that allows the same method name to perform different tasks based on the object or parameters. This chapters explains everything about polymorphism with usages and examples.

## What is Polymorphism in Java?

The polymorphism is an object-oriented programming concept that allows a single action or method to behave in different ways. It enables the same method name to perform different tasks depending on the object that calls it or the parameters passed to it.

The word polymorphism is derived from two Greek words: **poly** and **morphs**. The word <**poly** means many, and **morphs** means forms. Therefore, polymorphism means **many forms**.

There are two types of polymorphism in Java:

1. Compile-time Polymorphism
2. Runtime Polymorphism.

We can perform polymorphism in Java by method overloading and method overriding.

## 1. Java Compile-Time Polymorphism

In Java, **method overloading** is used to achieve **compile-time polymorphism**. Using method overloading, a class can have multiple methods with the same name but different parameter lists. The compiler determines which method to call **at compile time** based on the **number, type, and order of parameters** passed.

In method overloading, methods must have the same name but must differ in the **number or data types of parameters**. When a method is called, the compiler selects the most suitable overloaded method based on the arguments provided. If an exact match is found, that method is invoked; otherwise, the compiler applies **type promotion** to find the closest matching method.

### Example of Compile-Time Polymorphism

The following example demonstrates the implementation of compiler-time polymorphism using method overloading:

### Example

[](https://www.tpointtech.com/polymorphism-in-java#)[](https://www.tpointtech.com/polymorphism-in-java#)[](https://www.tpointtech.com/polymorphism-in-java#)

1. class Calculation {    
2.     int add(int a, int b) {    
3.         return a + b;    
4.     }    
5.     double add(double a, double b) {    
6.         return a + b;    
7.     }    
8. }    
9. public class Main {    
10.     public static void main(String[] args) {    
11.         Calculation calc = new Calculation();    
12.         // Compile-time polymorphism: selecting the appropriate add method based on parameter types    
13.         System.out.println("Sum of integers: " + calc.add(5, 3));    
14.         System.out.println("Sum of doubles: " + calc.add(2.5, 3.7));    
15.     }    
16. }    

**Output:**

Sum of integers: 8
Sum of doubles: 6.2

**Explanation**

In this example, the Calculation class has two add methods-one accepting two integers and the other allowing two doubles. The types of arguments given in the method call decide which add method the compiler calls during compilation. This choice is made at compile time, proving polymorphism.

## 2. Runtime Polymorphism in Java

Runtime polymorphism, also known as **Dynamic Method Dispatch**, is a process in which the call to an overridden method is resolved at runtime rather than at compile time.

In this process, an overridden method is invoked using a **superclass reference variable** that refers to a **subclass object**. The method that gets executed is determined by the actual object being referred to, not by the reference type.

Let's first understand the upcasting before Runtime Polymorphism.

### Upcasting

If the reference variable of Parent class refers to the object of Child class, it is known as upcasting. For example:

![Upcasting in Java](https://d2jdgazzki9vjm.cloudfront.net/core/images/runtime-polymorphism-in-java.png)

[](https://www.tpointtech.com/polymorphism-in-java#)[](https://www.tpointtech.com/polymorphism-in-java#)[](https://www.tpointtech.com/polymorphism-in-java#)

1. class A{}  
2. class B extends A{}  

[](https://www.tpointtech.com/polymorphism-in-java#)[](https://www.tpointtech.com/polymorphism-in-java#)[](https://www.tpointtech.com/polymorphism-in-java#)

1. A a=new B();//upcasting  

For upcasting, we can use the reference variable of class type or an interface type. For Example:

[](https://www.tpointtech.com/polymorphism-in-java#)[](https://www.tpointtech.com/polymorphism-in-java#)[](https://www.tpointtech.com/polymorphism-in-java#)

1. interface I{}  
2. class A{}  
3. class B extends A implements I{}  

Here, the relationship of B class would be:

B IS-A A
B IS-A I
B IS-A Object

Since Object is the root class of all classes in Java, so we can write B IS-A Object.

### Example of Runtime Polymorphism

In this example, we are creating two classes Bike and Splendor. Splendor class extends Bike class and overrides its run() method. We are calling the run method by the reference variable of Parent class. Since it refers to the subclass object and subclass method overrides the Parent class method, the subclass method is invoked at runtime.

Since method invocation is determined by the JVM not compiler, it is known as runtime polymorphism.

### Example

[](https://www.tpointtech.com/polymorphism-in-java#)[](https://www.tpointtech.com/polymorphism-in-java#)[](https://www.tpointtech.com/polymorphism-in-java#)

1. class Bike{    
2.   void run(){System.out.println("running");}    
3. }    
4. class Splendor extends Bike{    
5.   void run(){System.out.println("running safely with 60km");}    
6. }  
7. public class Main{  
8.   public static void main(String args[]){    
9.     Bike b = new Splendor();//upcasting    
10.     b.run();    
11.   }    
12. }    

**Output:**

running safely with 60km.

**Explanation**

This Java sample uses method overriding to illustrate runtime polymorphism. While the Splendour class extends Bike and overrides the run() method to output "running safely with 60km," the Bike class provides a method called run() that prints "running." Because of upcasting, a Bike reference variable called b is generated in the main method that points to a Splendour object. Runtime polymorphism is demonstrated by the overridden method from the Splendour class, which is called when the run() method is called using this reference variable. The JVM determines which method to call based on the actual object type at runtime.

## Real Life Examples of Runtime Polymorphism

Practice the following real-life examples of runtime polymorphism to understand the concept better:

### Example 1: Bank Class

Consider a scenario where Bank is a class that provides a method to get the rate of interest. However, the rate of interest may differ according to banks. For example, SBI, ICICI, and AXIS banks are providing 8.4%, 7.3%, and 9.7% rate of interest.

![Java Runtime Polymorphism example of bank](https://d2jdgazzki9vjm.cloudfront.net/core/images/runtime-polymorphism-in-java2.png)

#### Note: This example is also given in method overriding but there was no upcasting.

### Source Code

[](https://www.tpointtech.com/polymorphism-in-java#)[](https://www.tpointtech.com/polymorphism-in-java#)[](https://www.tpointtech.com/polymorphism-in-java#)

1. class Bank{    
2.     float getRateOfInterest(){return 0;}    
3. }    
4. class SBI extends Bank{    
5.     float getRateOfInterest(){return 8.4f;}    
6. }    
7. class ICICI extends Bank{    
8.     float getRateOfInterest(){return 7.3f;}    
9. }    
10. class AXIS extends Bank{    
11.     float getRateOfInterest(){return 9.7f;}    
12. }    
13. public class Main{    
14.  public static void main(String args[]){    
15.   Bank b;    
16.   b=new SBI();    
17.   System.out.println("SBI Rate of Interest: "+b.getRateOfInterest());    
18.   b=new ICICI();    
19.   System.out.println("ICICI Rate of Interest: "+b.getRateOfInterest());    
20.   b=new AXIS();    
21.   System.out.println("AXIS Rate of Interest: "+b.getRateOfInterest());    
22.  }    
23. }    

**Output:**

SBI Rate of Interest: 8.4
ICICI Rate of Interest: 7.3
AXIS Rate of Interest: 9.7

**Explanation**

This Java sample uses method overriding to demonstrate polymorphism. It provides a method called getRateOfInterest() on the Bank type, which returns 0. The Bank class is extended by the subclasses SBI, ICICI, and AXIS, which override the getRateOfInterest() function to return particular interest rates. Objects of SBI, ICICI, and AXIS are created and assigned to a Bank reference variable b in the TestPolymorphism class's main method. The relevant getRateOfInterest() method is dynamically executed through polymorphism, depending on the actual object type provided to b, and the interest rates for SBI, ICICI, and AXIS banks are printed out.

### Example 2: Shape Class

Let us take another example to demonstrate the shape class using runtime polymorphism.

### Source Code

[](https://www.tpointtech.com/polymorphism-in-java#)[](https://www.tpointtech.com/polymorphism-in-java#)[](https://www.tpointtech.com/polymorphism-in-java#)

1. class Shape{    
2.     void draw(){System.out.println("drawing...");}    
3. }    
4. class Rectangle extends Shape{    
5.     void draw(){System.out.println("drawing rectangle...");}    
6. }    
7. class Circle extends Shape{    
8.     void draw(){System.out.println("drawing circle...");}    
9. }    
10. class Triangle extends Shape{    
11.     void draw(){System.out.println("drawing triangle...");}    
12. }    
13. public class Main{    
14.     public static void main(String args[]){    
15.         Shape s;    
16.         s=new Rectangle();    
17.         s.draw();    
18.         s=new Circle();    
19.         s.draw();    
20.         s=new Triangle();    
21.         s.draw();    
22.     }    
23. }    

**Output:**

drawing rectangle...
drawing circle...
drawing triangle...

**Explanation**

In the context of shapes, this Java code serves as an example of polymorphism through method overriding. It defines a draw() method that prints "drawing..." on a base class Shape. Subclasses Rectangle, Circle, and Triangle extend Shape and provide particular implementations for each shape in their overrides of the draw() function. Objects of the Shape reference variables s are created and assigned to Rectangle, Circle, and Triangle in the TestPolymorphism2 class's main method. Through polymorphism, the appropriate implementation based on the actual object type allocated to s is dynamically triggered when the draw() method is called using this reference variable. As a result, for each shape, it outputs "drawing triangle...", "drawing circle...", and "drawing rectangle..." This demonstrates how Java programming's polymorphism allows for flexibility and dynamic behaviour.

### Example 3: Animal Class

Let us another example to demonstrate the runtime polymorphism using Animal Class.

### Source Code

[](https://www.tpointtech.com/polymorphism-in-java#)[](https://www.tpointtech.com/polymorphism-in-java#)[](https://www.tpointtech.com/polymorphism-in-java#)

1. class Animal{    
2.     void eat(){System.out.println("eating...");}    
3. }    
4. class Dog extends Animal{    
5.     void eat(){System.out.println("eating bread...");}    
6. }    
7. class Cat extends Animal{    
8.     void eat(){System.out.println("eating rat...");}    
9. }    
10. class Lion extends Animal{    
11.     void eat(){System.out.println("eating meat...");}    
12. }    
13. public class Main{    
14.     public static void main(String[] args){    
15.         Animal a;    
16.         a=new Dog();    
17.         a.eat();    
18.         a=new Cat();    
19.         a.eat();    
20.         a=new Lion();    
21.         a.eat();    
22.     }  
23. }    

**Output:**

eating bread...
eating rat...
eating meat...

**Explanation**

This Java sample uses method overriding to demonstrate polymorphism. It defines an eat() function for the basic class Animal, which is overridden by the subclasses Dog, Cat, and Lion with different eating habits. Polymorphic behaviour is demonstrated by assigning objects of various subclasses to an Animal reference variable an in the main function. This reference is then used to call the eat() method, which dynamically invokes the appropriate override implementation based on the actual object type.

## Java Runtime Polymorphism with Data Member

A method is overridden, not the data members, so runtime polymorphism can't be achieved by data members.

In the example given below, both the classes have a data member speedlimit. We are accessing the data member by the reference variable of Parent class which refers to the subclass object. Since we are accessing the data member which is not overridden, hence it will access the data member of the Parent class always.

#### Rule: Runtime polymorphism can't be achieved by data members.

### Example

[](https://www.tpointtech.com/polymorphism-in-java#)[](https://www.tpointtech.com/polymorphism-in-java#)[](https://www.tpointtech.com/polymorphism-in-java#)

1. class Bike{    
2.  int speedlimit=90;    
3. }    
4. class Honda extends Bike{    
5.  int speedlimit=150;    
6. }  
7. public class Main{  
8.  public static void main(String args[]){    
9.   Bike obj=new Honda();    
10.   System.out.println(obj.speedlimit);//90    
11.  }  
12. }  

**Output:**

90

**Explanation**

The base class Bike and the subclass Honda3 are part of the class hierarchy defined by this Java code. The speedlimit member variable for the Bike class is initialised to 90, whereas the speedlimit variable for the Honda3 class is initialised to 150. An object of type Bike is created in the Honda3 class's main method, but because of upcasting, it is referred to by the Honda3 reference variable obj. Obj.speedlimit produces 90 instead of 150 when it is accessed and printed.

It is due to the fact that member variables in Java are not polymorphism-prone; rather, compile-time member variable access is determined by the reference type. Because it's the reference to the speedlimit member variable, the Bike class is where it comes from even though obj refers to a Honda3 object.

## Java Runtime Polymorphism with Multilevel Inheritance

Let's see the simple example of Runtime Polymorphism with multilevel inheritance.

### Example

[](https://www.tpointtech.com/polymorphism-in-java#)[](https://www.tpointtech.com/polymorphism-in-java#)[](https://www.tpointtech.com/polymorphism-in-java#)

1. class Animal{    
2.     void eat(){System.out.println("eating");}    
3. }    
4. class Dog extends Animal{    
5.     void eat(){System.out.println("eating fruits");}    
6. }    
7. class BabyDog extends Dog{    
8.     void eat(){System.out.println("drinking milk");}    
9. }  
10. public class Main{  
11.     public static void main(String args[]){    
12.         Animal a1,a2,a3;    
13.         a1=new Animal();    
14.         a2=new Dog();    
15.         a3=new BabyDog();    
16.         a1.eat();    
17.         a2.eat();    
18.         a3.eat();    
19.     }    
20. }    

**Output:**

eating
eating fruits
drinking Milk

**Explanation**

This Java sample illustrates polymorphism and method overriding in an animal class hierarchy. While the Dog and BabyDog classes extend Animal and override eat() to print "eating fruits" and "drinking milk," respectively, the Animal class defines an eat() function that prints "eating." The main method exhibits polymorphic behaviour by creating and calling Animal, Dog, and BabyDog objects using the eat() method. This dynamically invokes the appropriate override implementation based on the actual object type supplied to the reference variable.

### Example

[](https://www.tpointtech.com/polymorphism-in-java#)[](https://www.tpointtech.com/polymorphism-in-java#)[](https://www.tpointtech.com/polymorphism-in-java#)

1. class Animal{    
2.     void eat(){System.out.println("animal is eating...");}    
3. }    
4. class Dog extends Animal{    
5.     void eat(){System.out.println("dog is eating...");}    
6. }    
7. class BabyDog extends Dog{}    

8. public class Main{    
9.     public static void main(String args[]){    
10.         Animal a=new BabyDog();    
11.         a.eat();    
12.     }  
13. }    

**Explanation**

This Java code exemplifies polymorphism and method overriding. The class hierarchy is defined as follows: Dog extends Animal and overrides eat() to print "dog is eating...", BabyDog extends Dog, and Animal has an eat() method that prints "animal is eating..." An object of BabyDog is generated and allocated to an Animal reference variable an in the main procedure. The override eat() function from the BabyDog class is dynamically invoked when a.eat() is called, exhibiting polymorphism behaviour in which the method used depends on the actual object type at runtime.

## Advantages of Polymorphism

There are several advantages of Polymorphism in Java. Some of them are as follows:

**1. Code Reusability**

Polymorphism allows methods in subclasses to override methods in their superclass, enabling code reuse and maintaining a consistent interface across related classes.

**2. Flexibility and Extensibility**

Polymorphism allows subclasses to provide their own implementations of methods defined in the superclass, making it easier to extend and customize behavior without modifying existing code.

**3. Dynamic Method Invocation:**

Polymorphism enables dynamic method invocation, where the method called is determined by the actual object type at runtime, providing flexibility in method dispatch.

**4. Interface Implementation:**

Interfaces in Java allow multiple classes to implement the same interface with their own implementations, facilitating polymorphic behavior and enabling objects of different classes to be treated interchangeably based on a common interface.

**5. Method Overloading:**

Polymorphism is also achieved through method overloading, where multiple methods with the same name but different parameter lists can be defined within a class or its subclasses, enhancing code readability and allowing flexibility in method invocation based on parameter types.

**6. Reduced Code Complexity:**

Polymorphism helps reduce code complexity by promoting a modular and hierarchical class structure, making it easier to understand, maintain, and extend large-scale software systems.