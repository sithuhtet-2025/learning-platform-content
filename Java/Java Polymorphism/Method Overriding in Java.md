**Method Overriding** in Java is used to achieve runtime polymorphism and dynamic behavior. In this chapter, we will learn about the method overloading, rules to implement with the help of examples.

## What is Method Overriding in Java?

Method Overriding allows a subclass to provide its own specific implementation of a method that is already defined in its parent class. Method overriding supports runtime polymorphism by enabling dynamic method binding, where the method call is resolved at runtime based on the actual object type.

## Usage of Java Method Overriding

The following points describe the uses of method overriding in Java:

1. Method overriding is used to provide the specific implementation of a method that is already provided by its superclass.
2. Method overriding is used for runtime polymorphism.
3. Method overriding allows subclasses to reuse and build upon the functionality provided by their superclass, reducing redundancy and promoting modular code design.
4. Subclasses can override methods to tailor them to their specific needs or to implement specialized behavior that is unique to the subclass.
5. Method overriding enables dynamic method dispatch, where the actual method implementation to be executed is determined at runtime based on the type of object, supporting flexibility and polymorphic behavior.

## Rules for Java Method Overriding

The following are the important rules of method overriding in Java:

1. **Same Method Name:** The overriding method in the subclass must have the same name as the method in the superclass that it is overriding.
2. **Same Parameters:** The overriding method must have the same number and types of parameters as the method in the superclass. This ensures compatibility and consistency with the method signature defined in the superclass.
3. **IS-A Relationship (Inheritance):** Method overriding requires an IS-A relationship between the subclass and the superclass. This means that the subclass must inherit from the superclass, either directly or indirectly, to override its methods.
4. **Same Return Type or Covariant Return Type:** The return type of the overriding method can be the same as the return type of the overridden method in the superclass, or it can be a subtype of the return type in the superclass. This is known as the covariant return type, introduced in Java 5.
5. **Access Modifier Restrictions:** The access modifier of the overriding method must be the same as or less restrictive than the access modifier of the overridden method in the superclass. Specifically, a method declared as public in the superclass can be overridden as public or protected but not as private. Similarly, a method declared as protected in the superclass can be overridden as protected or public but not as private. A method declared as default (package-private) in the superclass can be overridden with default, protected, or public, but not as private.
6. **No Final Methods:** Methods declared as final in the superclass cannot be overridden in the subclass. Because final methods cannot be modified or extended.
7. **No Static Methods:** Static methods in Java are resolved at compile time and cannot be overridden. Instead, they are hidden in the subclass if a method with the same signature is defined in the subclass.

## Understanding the problem without method overriding

Let's understand the problem that we may face in the program if we do not use method overriding.

### Example

[](https://www.tpointtech.com/method-overriding-in-java#)[](https://www.tpointtech.com/method-overriding-in-java#)[](https://www.tpointtech.com/method-overriding-in-java#)

1. //Java Program to demonstrate why we need method overriding    
2. //Here, we are calling the method of parent class with child class object   
3. //Creating a parent class    
4. class Vehicle{    
5.   void run(){System.out.println("Vehicle is running");}    
6. }    
7. //Creating a child class    
8. class Bike extends Vehicle{}  
9. //Creating a Main class to create object and call methods  
10. public class Main{  
11.   public static void main(String args[]){    
12.   //creating an instance of child class    
13.   Bike obj = new Bike();    
14.   //calling the method with child class instance    
15.   obj.run();    
16.   }    
17. }    

**Output:**

Vehicle is running

**Explanation**

We construct an instance of the Bike class and use it to invoke the run() method within the Bike class. As a result of Bike deriving from Vehicle, the run() function of the Vehicle class is overridden in the Bike class, resulting in the print "Vehicle is running" when the method is used on a Bike object. It demonstrates how method overriding, in which the method specified in the subclass overrides the method in the superclass with the identical signature, can result in polymorphic behaviour.

## Example of Method Overriding

In this example, we have defined the run() method in the subclass Bike and the same method also defined in in the parent class i.e. Vehicle, but it has some specific implementation. The method's name and parameters are the same, and there is an IS-A relationship between the classes, so there is method overriding.

### Example

[](https://www.tpointtech.com/method-overriding-in-java#)[](https://www.tpointtech.com/method-overriding-in-java#)[](https://www.tpointtech.com/method-overriding-in-java#)

1. //Java Program to illustrate the use of Java Method Overriding      
2. //Creating a parent class.      
3. class Vehicle{      
4.   //defining a method      
5.   void run(){System.out.println("Vehicle is running");}      
6. }      
7. //Creating a child class      
8. class Bike extends Vehicle{      
9.   //defining the same method as in the parent class      
10.   void run(){System.out.println("Bike is running safely");}     
11. }  
12. //Creating a Main class to create object and call method  
13. public class Main{   
14.   public static void main(String args[]){      
15.   Bike obj = new Bike();//creating object      
16.   obj.run();//calling method      
17.   }      
18. }      

**Output:**

Bike is running safely

**Explanation**

A method in a subclass (Bike) overrides the same method in its superclass (Vehicle), as this Java program illustrates. The run() method in this example is shared by both types, but the Bike class implements it differently, outputting "Bike is running safely." The overridden function in the Bike class gets executed when we create an instance of Bike and use the run() method on it, proving that the implementation of the subclass takes precedence over the implementation of the superclass. It demonstrates how Java's dynamic polymorphism feature allows methods with the same signature to behave differently in various classes, even if they are part of the same inheritance tree.

## A Real World Example of Java Method Overriding

Consider a scenario where Bank is a class that provides functionality to get the rate of interest. However, the rate of interest varies according to banks. For example, SBI, ICICI and AXIS banks could provide 8%, 7%, and 9% rate of interest.

![Method Overriding in Java](https://images.tpointtech.com/core/images/method-overriding-in-java.png)

### Example

[](https://www.tpointtech.com/method-overriding-in-java#)[](https://www.tpointtech.com/method-overriding-in-java#)[](https://www.tpointtech.com/method-overriding-in-java#)

1. //Java Program to demonstrate the real scenario of Java Method Overriding      
2. //where three classes are overriding the method of a parent class.      
3. //Creating a parent class.      
4. class Bank{      
5. int getRateOfInterest(){return 0;}      
6. }      
7. //Creating child classes      
8. class SBI extends Bank{      
9. int getRateOfInterest(){return 8;}      
10. }      
11. class ICICI extends Bank{      
12. int getRateOfInterest(){return 7;}      
13. }      
14. class AXIS extends Bank{      
15. int getRateOfInterest(){return 9;}      
16. }      
17. //Create a Main class to create objects and call the methods      
18. public class Main{      
19. public static void main(String args[]){      
20. SBI s=new SBI();      
21. ICICI i=new ICICI();      
22. AXIS a=new AXIS();      
23. System.out.println("SBI Rate of Interest: "+s.getRateOfInterest());      
24. System.out.println("ICICI Rate of Interest: "+i.getRateOfInterest());      
25. System.out.println("AXIS Rate of Interest: "+a.getRateOfInterest());      
26. }      
27. }    

**Output:**

SBI Rate of Interest: 8
ICICI Rate of Interest: 7
AXIS Rate of Interest: 9

**Explanation**

This Java programme uses a real-world scenario where three classes-SBI, ICICI, and AXIS-override a method from their parent class, Bank, to demonstrate the idea of method overriding. The getRateOfInterest() function of the Bank class yields 0. With their own implementation, each of the child classes overrides this method: SBI returns 8, ICICI returns 7, and AXIS returns 9. Each child class object is created in the Test2 class, and then each object's getRateOfInterest() method is used to print out the corresponding interest rates for each bank. This illustrates how polymorphic behaviour dependent on the type of object at runtime is made possible by method overriding, which enables each subclass to give its own implementation of a method inherited from the superclass.

## Static Methods and Method Overriding

Static methods **cannot be overridden in Java**. When a subclass declares a static method with the same signature as a static method in its superclass, it does not override the method; instead, it hides the superclass method. As a result, the method that gets executed is determined at compile time based on the reference type, not at runtime based on the actual object type. Therefore, **static methods do not support runtime polymorphism like instance methods**.

Method overriding is based on **dynamic method dispatch**, where the method call is resolved at runtime according to the actual object. However, static methods are associated with the **class itself**, not with individual objects, and hence they are resolved at compile time. Because of this, **static methods are not eligible for dynamic dispatch and cannot be overridden**.

Additionally, there is a difference in how static and instance methods are handled in memory. **Instance methods** are invoked through objects and are tied to the heap memory, while **static methods** are stored in the method area of the [JVM](https://www.tpointtech.com/jvm-java-virtual-machine) and are shared among all instances of the class. Due to these fundamental differences in behavior, binding, and memory allocation, static methods cannot participate in method overriding.

## Method Overriding and main() Method

The **main() method** in cannot be overridden because it is declared as static. The main() method is defined as **public static void main(String[] args)** and serves as the entry point of program execution.

Static methods belong to the class, not to objects, so they do not support runtime polymorphism. They are resolved at compile time, which makes method overriding impossible. Therefore, even if a subclass defines a main() method with the same signature, it does not override the superclass method, and the **main() method cannot be overridden in Java**.

## Method Overloading Vs. Method Overriding

The following table shows the demonstrate the difference between Method Overloading and Method Overriding:

|Aspect|Method Overloading|Method Overriding|
|---|---|---|
|**Purpose and Intent**|Method overloading is used to increase the readability of the program.|Method overriding is used to provide the specific implementation of the method that is already provided by its superclass.|
|**Relationship between Classes**|Method overloading is performed within class.|Method overriding occurs in two classes that have IS-A (inheritance) relationship.|
|**Parameter Requirements**|In case of method overloading, parameters must be different.|In case of method overriding, parameters must be the same.|
|**Polymorphism Type**|Method overloading is the example of compile-time polymorphism.|Method overriding is the example of runtime polymorphism.|
|**Return Type Constraints**|In Java, method overloading can't be performed by changing the return type of the method only. Return type can be the same or different in method overloading, but you must have to change the parameter.|Return type must be the same or covariant in method overriding.|
|**Access Modifiers**|It can have any access modifier.|The overriding method cannot have a more restrictive access modifier than the overridden method.|
|**Exceptions**|It can throw any exceptions.|It throws only checked exceptions declared in the superclass method or its subclasses.|
|**Invocation**|It resolved at compile-time.|It resolved at runtime using dynamic method dispatch.|
|**Inheritance Required**|Not required.|Required (through subclassing or interface implementation).|
|**Binding**|It uses static binding.|It uses dynamic binding.|
|**Early and Late Binding**|It is also known as early binding.|It is also known as late binding.|
|**Signature Matching**|Method signatures must be different.|Method signatures must be identical.|
|**Statis Method**|Static method can be overloaded.|Static method cannot be overridden.|
|**Final and Public Method**|It is applicable to both private and final methods.|It is not applicable to private and final methods.|
|**Error**|If any error occurs, can be caught at compile-time.|If any error occurs, can be caught at run-time.|

## Java Access Modifiers with Method Overriding

If you are overriding any method, overridden method (i.e. declared in subclass) must not be more restrictive.

### Example

Let us take an example to demonstrate the Access Modifiers with Method Overriding in Java.

[](https://www.tpointtech.com/method-overriding-in-java#)[](https://www.tpointtech.com/method-overriding-in-java#)[](https://www.tpointtech.com/method-overriding-in-java#)

1. class A{    
2. protected void msg(){System.out.println("Hello java");}    
3. }    
4. public class Simple extends A{    
5. void msg(){System.out.println("Hello java");}//C.T.Error    
6.  public static void main(String args[]){    
7.    Simple obj=new Simple();    
8.    obj.msg();    
9.    }    
10. }    

**Output:**

![Method Overriding in Java](https://images.tpointtech.com/core/images/method-overriding-in-java2.png)

**Explanation**

Class A declares a method called msg() with the protected access modifier in the provided Java code. By extending class A, class Simple aims to replace the message() function with a default access modifier. But because the default access modifier is more restricted than protected, this leads to a compile-time error. When overriding a method in Java, the overridden method's access level in the subclass needs to be at least as liberal as the method's access level in the superclass. Thus, in order to fix the issue, either the class Simple method's access modifier-such as protected or public-should be as liberal as protected, or the class A method should have a less permissive access modifier-such as default or public.