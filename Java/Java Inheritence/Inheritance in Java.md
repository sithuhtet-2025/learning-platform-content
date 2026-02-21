Inheritance in Java is a mechanism in which one object acquires all the properties and behaviors of a parent object. It is an important part of OOPs (Object Oriented programming system).

The idea behind inheritance in Java is that we can create new classes that are built upon existing classes. When we inherit methods from an existing class, we can reuse methods and fields of the parent class. However, we can add new methods and fields in your current class also.

## What is Inheritance?

Inheritance in Java enables a class to inherit properties and actions from another class, called a superclass or parent class. A class derived from a superclass is called a subclass or child group. Through inheritance, a subclass can access members of its superclass (fields and methods), enforce reuse rules, and encourage hierarchy.

Inheritance represents the IS-A relationship which is also known as a parent-child relationship.

## Why Use Inheritance in Java?

The inheritance is used for the following important reasons:

- **Method Overriding:** Inheritance allows a subclass to provide a specific implementation of a method already defined in its superclass. This is also known as [runtime polymorphism.](https://www.tpointtech.com/polymorphism-in-java)
- **Code Reusability:** Inheritance allows developers to reuse the existing code from a parent class which reduces the redundancy and makes the code easier to maintain.

## Terms used in Inheritance

Here are the important terms (terminologies) that are used in inheritance:

- **Class:** A class is a group of objects which have common properties. It is a template or blueprint from which objects are created.
- **Sub Class/Child Class:** Subclass is a class which inherits the other class. It is also called a derived class, extended class, or child class.
- **Super Class/Parent Class:** Superclass is the class from where a subclass inherits the features. It is also called a base class or a parent class.
- **Reusability:** As the name specifies, reusability is a mechanism which facilitates you to reuse the fields and methods of the existing class when you create a new class. You can use the same fields and methods already defined in the previous class.

## The extends Keyword

The **extends** keyword is used to create a new class (subclass) that derives from an existing class (superclass). It allows the subclass to inherit fields and methods from the superclass.

### Syntax

It has the following syntax:

[](https://www.tpointtech.com/inheritance-in-java#)[](https://www.tpointtech.com/inheritance-in-java#)[](https://www.tpointtech.com/inheritance-in-java#)

1. class Subclass-name extends Superclass-name  
2. {  
3.    //methods and fields  
4. }  

## Java Inheritance Example

![Inheritance in Java](https://d2jdgazzki9vjm.cloudfront.net/core/images/inheritance-in-java.png)

As displayed in the above figure, Programmer is the subclass and Employee is the superclass. The relationship between the two classes is **Programmer IS-A Employee**. It means that Programmer is a type of Employee.

This example demonstrate the single inheritance in Java, where the Programmer class inherits the salary variable from the Employee class and also defines its own bonus.

### Example

[](https://www.tpointtech.com/inheritance-in-java#)[](https://www.tpointtech.com/inheritance-in-java#)[](https://www.tpointtech.com/inheritance-in-java#)

1. class Employee{  
2.  float salary=40000;  
3. }  
4. class Programmer extends Employee{  
5.  int bonus=10000;  
6. }  
7. public class Main{  
8.  public static void main(String args[]){  
9.    Programmer p=new Programmer();  
10.    System.out.println("Programmer salary is:"+p.salary);  
11.    System.out.println("Bonus of Programmer is:"+p.bonus);  
12. }  
13. }  

**Output:**

Programmer salary is:40000.0
Bonus of programmer is:10000

In the above example, Programmer object can access the field of own class as well as of Employee class i.e. code reusability.

## Types of Inheritance

There are several types of inheritance supported in Java:

1. **Single Inheritance:**  
    Single inheritance allows a subclass inherits from one superclass only.
2. **Multilevel Inheritance:**  
    Multilevel inheritance allows a class is derived from a subclass, forming a chain of inheritance.
3. **Hierarchical Inheritance:**  
    Hierarchical inheritance allows multiple subclasses inherit from the same superclass.
4. **Hybrid Inheritance (Through Interfaces):**  
    Hybrid inheritance combines two or more types of inheritance using interfaces to avoid multiple inheritance issues.

In Java, multiple inheritance and hybrid inheritance are supported only through interfaces, because Java does not allow multiple inheritance with classes directly. We will learn more about interfaces later.

## Single Inheritance

When a class inherits another class, it is known as a [single inheritance](https://www.tpointtech.com/single-inheritance-in-java). In the example given below, Dog class inherits the Animal class, so there is the single inheritance.

![Inheritance in Java](https://d2jdgazzki9vjm.cloudfront.net/core/images/inheritance-in-java2.png)

Let us take an example to demonstrate the single inheritance in Java.

### Example

[](https://www.tpointtech.com/inheritance-in-java#)[](https://www.tpointtech.com/inheritance-in-java#)[](https://www.tpointtech.com/inheritance-in-java#)

1. class Animal{  
2. void eat(){System.out.println("eating...");}  
3. }  
4. class Dog extends Animal{  
5. void bark(){System.out.println("barking...");}  
6. }  
7. public class Main{  
8. public static void main(String args[]){  
9. Dog d=new Dog();  
10. d.bark();  
11. d.eat();  
12. }}  

**Output:**

barking...
eating...

## Multilevel Inheritance

When there is a chain of inheritance, it is known as [multilevel inheritance](https://www.tpointtech.com/multilevel-inheritance-in-java). As you can see in the example given below, BabyDog class inherits the Dog class which again inherits the Animal class, so there is a multilevel inheritance.

![Inheritance in Java](https://d2jdgazzki9vjm.cloudfront.net/core/images/inheritance-in-java3.png)  
 

Here, we are going to take an example to demonstrate the working of multilevel inheritance in Java.

### Example

[](https://www.tpointtech.com/inheritance-in-java#)[](https://www.tpointtech.com/inheritance-in-java#)[](https://www.tpointtech.com/inheritance-in-java#)

1. class Animal{  
2. void eat(){System.out.println("eating...");}  
3. }  
4. class Dog extends Animal{  
5. void bark(){System.out.println("barking...");}  
6. }  
7. class BabyDog extends Dog{  
8. void weep(){System.out.println("weeping...");}  
9. }  
10. public class Main{  
11. public static void main(String args[]){  
12. BabyDog d=new BabyDog();  
13. d.weep();  
14. d.bark();  
15. d.eat();  
16. }}  

**Output:**

weeping...
barking...
eating...

## Hierarchical Inheritance

When two or more classes inherits a single class, it is known as [hierarchical inheritance](https://www.tpointtech.com/hierarchical-inheritance-in-java). In the example given below, Dog and Cat classes inherits the Animal class, so there is hierarchical inheritance.

![Inheritance in Java](https://d2jdgazzki9vjm.cloudfront.net/core/images/inheritance-in-java4.png)  
 

Here, we are going to take an example to demonstrate the working of hierarchical inheritance in Java.

### Example

[](https://www.tpointtech.com/inheritance-in-java#)[](https://www.tpointtech.com/inheritance-in-java#)[](https://www.tpointtech.com/inheritance-in-java#)

1. class Animal{  
2. void eat(){System.out.println("eating...");}  
3. }  
4. class Dog extends Animal{  
5. void bark(){System.out.println("barking...");}  
6. }  
7. class Cat extends Animal{  
8. void meow(){System.out.println("meowing...");}  
9. }  
10. public class Main{  
11. public static void main(String args[]){  
12. Cat c=new Cat();  
13. c.meow();  
14. c.eat();  
15. //c.bark();//C.T.Error  
16. }}  

**Output:**

meowing...
eating...

## Multiple Inheritance

Multiple Inheritance A class's capacity to inherit traits from several classes is referred to as multiple inheritances. This notion may be quite helpful when a class needs features from many sources.

![Inheritance in Java](https://d2jdgazzki9vjm.cloudfront.net/core/images/inheritance-in-java5.png)

However, Multiple inheritances can result in issues like the diamond problem, which occurs when two superclasses share the same method or field and causes conflicts. Java uses interfaces to implement [multiple inheritances](https://www.tpointtech.com/multiple-inheritance-in-java) in order to prevent these conflicts.

Here, we are going to take an example to demonstrate the working of multiple inheritance in Java.

### Example

[](https://www.tpointtech.com/inheritance-in-java#)[](https://www.tpointtech.com/inheritance-in-java#)[](https://www.tpointtech.com/inheritance-in-java#)

1. interface Character {    
2.     void attack();    
3. }    
4. interface Weapon {    
5.     void use();    
6. }    
7. class Warrior implements Character, Weapon {    
8.     public void attack() {    
9.         System.out.println("Warrior attacks with a sword.");    
10.     }    
11.     public void use() {    
12.         System.out.println("Warrior uses a sword.");    
13.     }    
14. }    
15. class Mage implements Character, Weapon {    
16.     public void attack() {    
17.         System.out.println("Mage attacks with a wand.");    
18.     }    
19.     public void use() {    
20.         System.out.println("Mage uses a wand.");    
21.     }    
22. }    
23. public class Main {    
24.     public static void main(String[] args) {    
25.         Warrior warrior = new Warrior();    
26.         Mage mage = new Mage();    
27.         warrior.attack(); // Output: Warrior attacks with a sword.    
28.         warrior.use(); // Output: Warrior uses a sword.    
29.         mage.attack(); // Output: Mage attacks with a wand.    
30.         mage.use(); // Output: Mage uses a wand.    
31.     }    
32. }    

**Output:**

Warrior attacks with a sword.
Warrior uses a sword.
Mage attacks with a wand.
Mage uses a wand.

## Hybrid Inheritance in Java

The [hybrid inheritance](https://www.tpointtech.com/hybrid-inheritance-in-java) is the composition of two or more types of inheritance. The main purpose of using hybrid inheritance is to modularize the code into well-defined classes. It also provides the code reusability.

![Inheritance in Java](https://d2jdgazzki9vjm.cloudfront.net/core/images/inheritance-in-java6.png)

The hybrid inheritance can be achieved by using the following combinations:

- Single and Multiple Inheritance (not supported but can be achieved through interface)
- Multilevel and Hierarchical Inheritance
- Hierarchical and Single Inheritance
- Multiple and Multilevel Inheritance

Here, we are going to take an example to demonstrate the working of hybrid inheritance in Java.

### Example

[](https://www.tpointtech.com/inheritance-in-java#)[](https://www.tpointtech.com/inheritance-in-java#)[](https://www.tpointtech.com/inheritance-in-java#)

1. class C    
2. {    
3. public void disp()    
4. {    
5. System.out.println("C");    
6. }    
7. }    
8. class A extends C    
9. {    
10. public void disp()    
11. {    
12. System.out.println("A");    
13. }    
14. }    
15. class B extends C    
16. {    
17. public void disp()    
18. {    
19. System.out.println("B");    
20. }       
21. }    
22. public class D extends A    
23. {    
24. public void disp()    
25. {    
26. System.out.println("D");    
27. }    
28. public static void main(String args[])    
29. {    
30. D obj = new D();    
31. obj.disp();    
32. }    
33. }    

**Output:**

D

## FAQs about Inheritance

### 1. Why multiple inheritance is not supported in Java?

To reduce the complexity and simplify the language, multiple inheritance is not supported in Java.

Suppose there are three classes A, B, and C. The C class inherits A and B classes. If A and B classes have the same method and we call it from child class object, there will be ambiguity to call the method of A or B class. It is called diamond problem.

To read more [Diamond Problem in Java](https://www.tpointtech.com/what-is-diamond-problem-in-java)

Since compile-time errors are better than runtime errors, Java renders compile-time error if you inherit 2 classes. So, whether you have same method or different, there will be compile time error.

[](https://www.tpointtech.com/inheritance-in-java#)[](https://www.tpointtech.com/inheritance-in-java#)[](https://www.tpointtech.com/inheritance-in-java#)

1. class A {    
2. void msg(){System.out.println("Hello");}    
3. }    
4. class B {    
5. void msg(){System.out.println("Welcome");}    
6. }    
7. public class Main extends A,B {   
8.  public static void main(String args[]){    
9.    Main obj = new Main();  
10.    obj.msg();//Now which msg() method would be invoked?    
11. }    
12. }    

**Output:**

Compile Time Error

### 2. How to achieve Multiple Inheritance in Java?

Java supports multiple inheritance through interfaces only, where a class can implement multiple interfaces. Multiple inheritance in Java is not possible by class, but it is possible through interfaces.