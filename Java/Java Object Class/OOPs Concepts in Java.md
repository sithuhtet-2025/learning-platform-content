Object-oriented programming is a paradigm that provides concepts, such as **inheritance, data binding, polymorphism**, etc.

**Simula** is considered the first object-oriented programming language. The programming paradigm where everything is represented as an object is known as a pure object-oriented programming language.

**Smalltalk** is considered the first truly object-oriented programming language.

The popular object-oriented languages are [Java](https://www.tpointtech.com/java-tutorial), [C#](https://www.tpointtech.com/c-sharp-tutorial), [PHP](https://www.tpointtech.com/php-tutorial), [Python](https://www.tpointtech.com/python-tutorial), [C++](https://www.tpointtech.com/cpp-tutorial), etc.

## OOPs (Object-Oriented Programming)

Object-oriented programming aims to implement real-world entities, for example, objects, classes, abstraction, inheritance, polymorphism, etc.

**Object** means a real-world entity such as a pen, chair, table, computer, watch, etc. **Object-oriented programming** is a methodology or paradigm for designing a program using classes and objects. It simplifies software development and maintenance by providing some concepts:

- [Object](https://www.tpointtech.com/java-oops-concepts#object)
- [Class](https://www.tpointtech.com/java-oops-concepts#class)
- [Inheritance](https://www.tpointtech.com/java-oops-concepts#inheritance)
- [Polymorphism](https://www.tpointtech.com/java-oops-concepts#polymorphism)
- [Abstraction](https://www.tpointtech.com/java-oops-concepts#abstraction)
- [Encapsulation](https://www.tpointtech.com/java-oops-concepts#encapsulation)

Apart from these concepts, there are some other terms which are used in Object-Oriented design:

- [Coupling](https://www.tpointtech.com/java-oops-concepts#coupling)
- [Cohesion](https://www.tpointtech.com/java-oops-concepts#cohesion)
- [Association](https://www.tpointtech.com/java-oops-concepts#association)
- [Aggregation](https://www.tpointtech.com/java-oops-concepts#aggregation)
- [Composition](https://www.tpointtech.com/java-oops-concepts#composition)

![Java OOPs Concepts](https://images.tpointtech.com/images/java-oops.png)

## Object

Any entity that has state and behavior is known as an object. For example, a chair, pen, table, keyboard, bike, etc. It can be physical or logical.

An [Object](https://www.tpointtech.com/object-in-java) can be defined as an instance of a class. It contains an address and takes up some space in memory. Objects can communicate without knowing the details of each other's data or code. The only necessary thing is the type of message accepted and the type of response returned by the objects.

**Example:** A dog is an object because it has states like color, name, breed, etc. as well as behaviors like wagging the tail, barking, eating, etc.

![Java Object](https://images.tpointtech.com/images/objects.png)

The primary elements of an object are:

- **State:** It is embodied in an object's properties. Additionally, it reflects an object's attributes.
- **Behavior:** An object's methods are a representation of it. Additionally, it represents how an object reacts to other objects.
- **Identity:** Identity is a special name that gives a thing the ability to communicate with other objects.
- **Method:** A method is a group of statements that carry out a certain operation and give an outcome. A method can complete a certain task without giving back any results. Methods are regarded as time savers since they enable us to reuse the code without having to type it again. Java differs from languages like C, C++, and Python in that each method needs to be a component of a class.

### Example of Object

The following example demonstrates how to create a class, instantiate an object, assign values to object fields, and invoke a method using that object.

[](https://www.tpointtech.com/java-oops-concepts#)[](https://www.tpointtech.com/java-oops-concepts#)[](https://www.tpointtech.com/java-oops-concepts#)

1. class Dog {  
2.     String name;  
3.     void bark() {  
4.         System.out.println(name + " says Woof!");  
5.     }  
6. }  
7. public class Main {  
8.     public static void main(String[] args) {  
9.         Dog myDog = new Dog();     // Creating an object  
10.         myDog.name = "Rocky";      // Assigning value to the object's field  
11.         myDog.bark();              // Calling method on the object  
12.     }  
13. }  

**Output:**

Rocky says Woof!

## Class

Class is a logical entity. A [class](https://www.tpointtech.com/class-definition-in-java) can also be defined as a blueprint from which we can create an individual object. Class does not consume any space.

In general, a class declaration includes the following in the order as it appears:

1. **Modifiers:** A class can be public or have default access.
2. **class keyword:** The class keyword is used to create a class.
3. **Class name:** The name must begin with an initial letter (capitalized by convention).
4. **Superclass (if any):** The name of the class's parent (superclass), if any, preceded by the keyword extends. A class can only extend (subclass) one parent.
5. **Interfaces (if any):** A comma-separated list of interfaces implemented by the class, if any, preceded by the keyword implements. A class can implement more than one interface.
6. **Body:** The class body surrounded by braces, { }.

## Inheritance

When one object acquires all the properties and behaviors of a parent object, it is known as [inheritance](https://www.tpointtech.com/inheritance-in-java). It provides code reusability. It is used to achieve runtime polymorphism.

### Example of Inheritance

The following example demonstrates inheritance, where the **Car** class extends the **Vehicle** class and accesses both inherited methods and its own method.

[](https://www.tpointtech.com/java-oops-concepts#)[](https://www.tpointtech.com/java-oops-concepts#)[](https://www.tpointtech.com/java-oops-concepts#)

1. // Superclass (Parent)  
2. class Vehicle {  
3.     void start() {  
4.         System.out.println("Vehicle is starting...");  
5.     }  
6.     void stop() {  
7.         System.out.println("Vehicle is stopping...");  
8.     }  
9. }  
10. // Subclass (Child) - Inherits from Vehicle  
11. class Car extends Vehicle {  
12.     void honk() {  
13.         System.out.println("Car is honking!");  
14.     }  
15. }  
16. public class MainExample {  
17.     public static void main(String[] args) {  
18.         Car myCar = new Car();  
19.         // Calling inherited methods (from Vehicle)  
20.         myCar.start();  
21.         myCar.stop();  
22.         // Calling child class method  
23.         myCar.honk();  
24.     }  
25. }  

**Output:**

Vehicle is starting...
Vehicle is stopping...
Car is honking!

## Polymorphism

![Polymorphism in Java](https://images.tpointtech.com/images/polymorphism.gif)

If one task is performed in different ways, it is known as [polymorphism](https://www.tpointtech.com/polymorphism-in-java). For example, to convince the customer differently, to draw something, for example, a shape, a triangle, a rectangle, etc.

In Java, we use method overloading and method overriding to achieve polymorphism.

Another example can be to speak something; for example, a cat says meow, a dog barks woof, etc.

### Example of Polymorphism

The following example demonstrates polymorphism by showing method overloading at compile time and method overriding at runtime.

[](https://www.tpointtech.com/java-oops-concepts#)[](https://www.tpointtech.com/java-oops-concepts#)[](https://www.tpointtech.com/java-oops-concepts#)

1. class Animal {  
2.     // Method Overloading (compile-time polymorphism)  
3.     void sound() {  
4.         System.out.println("An animal makes a sound");  
5.     }  
6.     void sound(String type) {  
7.         System.out.println("Animal sound: " + type);  
8.     }  
9. }  
10. class Dog extends Animal {  
11.     // Method Overriding (runtime polymorphism)  
12.     @Override  
13.     void sound(String type) {  
14.         System.out.println("Dog barking is: " + type);  
15.     }  
16. }  
17. public class Main {  
18.     public static void main(String[] args) {  
19.         Animal a = new Animal();  
20.         Dog d = new Dog();  
21.         Animal poly = new Dog();   
22.         // Method Overloading  
23.         a.sound();  
24.         a.sound("Generic");  
25.         // Method Overriding  
26.         d.sound("Loud");  
27.         // Performing the Polymorphism   
28.         poly.sound("Soft");  
29.     }  
30. }  

**Output:**

An animal makes a sound
Animal sound: Generic
Dog barking is: Loud
Dog barking is: Soft

## Abstraction

Hiding internal implementation and showing functionality only to the user is known as [abstraction](https://www.tpointtech.com/abstraction-in-java). For example, in phone calls, we do not know the internal processing. In Java, we use abstract classes and interfaces to achieve abstraction.

### Example of Abstraction

The following example demonstrates abstraction using an abstract class with both abstract and concrete methods.

[](https://www.tpointtech.com/java-oops-concepts#)[](https://www.tpointtech.com/java-oops-concepts#)[](https://www.tpointtech.com/java-oops-concepts#)

1. abstract class Animal {  
2.     abstract void makeSound();  
3.     // Creating a Concrete method   
4.     void breathe() {  
5.         System.out.println("Animal is breathing...");  
6.     }  
7. }  
8. // Concrete subclass  
9. class Dog extends Animal {  
10.     // implementation for an abstract method  
11.     @Override  
12.     void makeSound() {  
13.         System.out.println("Dog barking");  
14.     }  
15. }  
16. public class Main {  
17.     public static void main(String[] args) {  
18.         Animal myDog = new Dog();  
19.         myDog.breathe();  
20.         myDog.makeSound();  
21.     }  
22. }  

**Output:**

Animal is breathing...
Dog barking

## Encapsulation

![Encapsulation in Java OOPs Concepts](https://images.tpointtech.com/core/images/encapsulation.png)

Binding (or wrapping) code and data together into a single unit is known as [encapsulation](https://www.tpointtech.com/encapsulation-in-java). For example, a capsule is wrapped with different medicines.

A Java class is an example of encapsulation. A Java bean is a fully encapsulated class because all the data members are private.

### Example of Abstraction

The following example demonstrates encapsulation by using private data members along with public getter and setter methods.

[](https://www.tpointtech.com/java-oops-concepts#)[](https://www.tpointtech.com/java-oops-concepts#)[](https://www.tpointtech.com/java-oops-concepts#)

1. class Student {  
2.     // Private data members  
3.     private String name;  
4.     // Setter method  
5.     public void setName(String name) {  
6.         this.name = name;  
7.     }  
8.     // Getter method  
9.     public String getName() {  
10.         return name;  
11.     }  
12. }  
13. public class Main {  
14.     public static void main(String[] args) {  
15.         Student s = new Student();  
16.         // Setting value using setter  
17.         s.setName("John");  
18.         // Getting value using getter  
19.         System.out.println("Student Name: " + s.getName());  
20.     }  
21. }  

**Output:**

Student Name: John

## Coupling

[Coupling](https://www.tpointtech.com/loose-coupling-in-java) refers to the knowledge, information, or dependency of another class. It arises when classes are aware of each other. If a class has information about another class, there is strong coupling. In Java, we use private, protected, and public modifiers to display the visibility level of a class, method, and field. We can use interfaces for the weaker coupling because there is no concrete implementation.

### Example

The following example demonstrates coupling, where one class depends on another class to perform its operation.

[](https://www.tpointtech.com/java-oops-concepts#)[](https://www.tpointtech.com/java-oops-concepts#)[](https://www.tpointtech.com/java-oops-concepts#)

1. // Tightly coupled class  
2. class Engine {  
3.     void start() {  
4.         System.out.println("Engine started");  
5.     }  
6. }  

7. class Car {  
8.     private Engine engine;   // Car is dependent on Engine  

9.     Car() {  
10.         engine = new Engine();   // Strong coupling  
11.     }  

12.     void drive() {  
13.         engine.start();  
14.         System.out.println("Car is moving");  
15.     }  
16. }  

17. public class Main {  
18.     public static void main(String[] args) {  
19.         Car myCar = new Car();  
20.         myCar.drive();  
21.     }  
22. }  

**Output:**

Engine started
Car is moving

## Cohesion

[Cohesion](https://www.tpointtech.com/cohesion-in-java) refers to the level of a component that performs a single well-defined task. A single well-defined task is done by a highly cohesive method. The weakly cohesive method will split the task into separate parts. The java.io package is highly cohesive because it has I/O related classes and interfaces. However, the java.util package is a weakly cohesive package because it has unrelated classes and interfaces.

### Example

The following example demonstrates cohesion, where a class performs a single well-defined responsibility.

[](https://www.tpointtech.com/java-oops-concepts#)[](https://www.tpointtech.com/java-oops-concepts#)[](https://www.tpointtech.com/java-oops-concepts#)

1. // Highly cohesive class  
2. class Calculator {  

3.     int add(int a, int b) {  
4.         return a + b;  
5.     }  

6.     int subtract(int a, int b) {  
7.         return a - b;  
8.     }  
9. }  

10. public class Main {  
11.     public static void main(String[] args) {  
12.         Calculator calc = new Calculator();  

13.         System.out.println("Addition: " + calc.add(10, 5));  
14.         System.out.println("Subtraction: " + calc.subtract(10, 5));  
15.     }  
16. }  

**Output:**

Addition: 15
Subtraction: 5

## Association

The [association](https://www.tpointtech.com/association-in-java) represents the relationship between the objects. Here, one object can be associated with one object or many objects. There can be four types of association between the objects:

- One-to-One
- One to Many
- Many to One
- Many-to-Many

For example, a country can have one prime minister (one-to-one), and a prime minister can have many ministers (one-to-many). Also, many MPs can have one prime minister (many to one), and many ministers can have many departments (many to many).

### Example

The following example demonstrates association, where objects of one class are related to objects of another class.

[](https://www.tpointtech.com/java-oops-concepts#)[](https://www.tpointtech.com/java-oops-concepts#)[](https://www.tpointtech.com/java-oops-concepts#)

1. // Associated class  
2. class PrimeMinister {  
3.     String name;  

4.     PrimeMinister(String name) {  
5.         this.name = name;  
6.     }  
7. }  

8. // Another associated class  
9. class Country {  
10.     String countryName;  
11.     PrimeMinister pm;   // Association  

12.     Country(String countryName, PrimeMinister pm) {  
13.         this.countryName = countryName;  
14.         this.pm = pm;  
15.     }  

16.     void showDetails() {  
17.         System.out.println("Country: " + countryName);  
18.         System.out.println("Prime Minister: " + pm.name);  
19.     }  
20. }  

21. public class Main {  
22.     public static void main(String[] args) {  
23.         PrimeMinister pm = new PrimeMinister("John");  
24.         Country country = new Country("ABC Nation", pm);  

25.         country.showDetails();  
26.     }  
27. }  

**Output:**

Country: ABC Nation
Prime Minister: John

#### Note: The association can be unidirectional or bidirectional.

## Aggregation

[Aggregation](https://www.tpointtech.com/aggregation-in-java) is a way to achieve Association. It represents the relationship where one object contains other objects as a part of its state. It represents the weak relationship between objects. It is also termed as a HAS-A relationship in Java. Like, inheritance represents the IS-A relationship. It is another way to reuse objects.

### Example

The following example demonstrates aggregation, where one class contains a reference to another class as a part of its state.

[](https://www.tpointtech.com/java-oops-concepts#)[](https://www.tpointtech.com/java-oops-concepts#)[](https://www.tpointtech.com/java-oops-concepts#)

1. // Aggregated class  
2. class Department {  
3.     String deptName;  

4.     Department(String deptName) {  
5.         this.deptName = deptName;  
6.     }  
7. }  

8. // Aggregator class  
9. class University {  
10.     String universityName;  
11.     Department department;   // Aggregation (HAS-A relationship)  

12.     University(String universityName, Department department) {  
13.         this.universityName = universityName;  
14.         this.department = department;  
15.     }  

16.     void showDetails() {  
17.         System.out.println("University: " + universityName);  
18.         System.out.println("Department: " + department.deptName);  
19.     }  
20. }  

21. public class Main {  
22.     public static void main(String[] args) {  
23.         Department dept = new Department("Computer Science");  
24.         University uni = new University("ABC University", dept);  

25.         uni.showDetails();  
26.     }  
27. }  

**Output:**

University: ABC University
Department: Computer Science

## Composition

The composition is also a way to achieve Association. The [composition](https://www.tpointtech.com/composition-in-java) represents the relationship where one object contains other objects as a part of its state. There is a strong relationship between the containing object and the dependent object. It is the state where objects do not have an independent existence. If we delete the parent object, all the child objects will be deleted automatically.

### Example

The following example demonstrates composition, where a class owns another class and the contained object cannot exist independently.

[](https://www.tpointtech.com/java-oops-concepts#)[](https://www.tpointtech.com/java-oops-concepts#)[](https://www.tpointtech.com/java-oops-concepts#)

1. // Composed class  
2. class Engine {  
3.     void start() {  
4.         System.out.println("Engine started");  
5.     }  
6. }  

7. // Owner class  
8. class Car {  
9.     private Engine engine;   // Composition (strong HAS-A relationship)  

10.     Car() {  
11.         engine = new Engine();   // Engine created inside Car  
12.     }  

13.     void drive() {  
14.         engine.start();  
15.         System.out.println("Car is moving");  
16.     }  
17. }  

18. public class Main {  
19.     public static void main(String[] args) {  
20.         Car myCar = new Car();  
21.         myCar.drive();  
22.     }  
23. }  

**Output:**

Engine started
Car is moving

## Advantages of OOP Over Procedure-Oriented Programming Language

1. OOPs make development and maintenance easier, whereas in a procedure-oriented programming language, it is not easy to manage if the code grows as the project size increases.
2. OOP provides data hiding, whereas in a procedure-oriented programming language, global data can be accessed from anywhere.  
    ![Encapsulation in Java OOPs Concepts](https://images.tpointtech.com/core/images/java-oops-concepts-2.png)
3. OOPs provide the ability to simulate real-world events much more effectively. We can provide the solution to real-world problems if we use an Object-Oriented Programming language.