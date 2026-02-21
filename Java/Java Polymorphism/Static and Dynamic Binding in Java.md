This chapter explains the concepts of Static (compile-time) and Dynamic (runtime) binding in Java, showing how method calls are resolved either at compile time or runtime, with examples.

## What is Binding in Java?

**Binding** refers to the process of linking a method call to its corresponding method body (the actual code that gets executed).

When you write a method call in your code, the Java compiler or JVM must decide which method implementation to execute. This decision is called **binding**.

There are two types of binding in Java:

1. **Static (Compile-time) Binding:** The method to be called is determined at **compile time**. It happens with private, final, and static methods and method overloading. **Static binding** is also known as **Early binding**.
2. **Dynamic (Runtime) Binding:** The method to be called is determined **at runtime** based on the **actual object**, not the reference type. It happens with method overriding. **Dynamic binding** is also known as **Late binding**.

![Static vs. Dynamic Binding in java](https://images.tpointtech.com/images/types-of-binding.jpg)

Before learning the static and dynamic binding, you must be familiar with Types. Let us understand the types first:

### Understanding Type

To understand binding in Java, it is important to first understand the types of variables, references, and objects.

**1. variables have a type**

Every variable in Java has a type, which can be primitive or non-primitive.

[](https://www.tpointtech.com/static-and-dynamic-binding-in-java#)[](https://www.tpointtech.com/static-and-dynamic-binding-in-java#)[](https://www.tpointtech.com/static-and-dynamic-binding-in-java#)

1. int data=30;  

Here data variable is a type of int.

**2. References have a type**

A reference variable also has a type, which is the class it can refer to.

[](https://www.tpointtech.com/static-and-dynamic-binding-in-java#)[](https://www.tpointtech.com/static-and-dynamic-binding-in-java#)[](https://www.tpointtech.com/static-and-dynamic-binding-in-java#)

1. class Dog{  
2.  public static void main(String args[]){  
3.   Dog d1;//Here d1 is a type of Dog  
4.  }  
5. }  

**3. Objects have a type**

An object is an instance of a particular Java class. However, it is also considered an instance of its superclass.

[](https://www.tpointtech.com/static-and-dynamic-binding-in-java#)[](https://www.tpointtech.com/static-and-dynamic-binding-in-java#)[](https://www.tpointtech.com/static-and-dynamic-binding-in-java#)

1. class Animal{}  

2. class Dog extends Animal{  
3.  public static void main(String args[]){  
4.   Dog d1=new Dog();  
5.  }  
6. }  

Here d1 is an instance of Dog class, but it is also an instance of Animal.

## 1. Static Binding in Java

When the type of an object is determined at compile time (by the compiler), it is known as static binding. Static binding occurs with private, final, or static methods, as well as with method overloading, because the compiler knows exactly which method to call.

### Example of Static Binding

The following example demonstrates the static binding:

[](https://www.tpointtech.com/static-and-dynamic-binding-in-java#)[](https://www.tpointtech.com/static-and-dynamic-binding-in-java#)[](https://www.tpointtech.com/static-and-dynamic-binding-in-java#)

1. class Dog{  
2.  private void eat(){System.out.println("dog is eating...");}  

3.  public static void main(String args[]){  
4.   Dog d1=new Dog();  
5.   d1.eat();  
6.  }  
7. }  

## 2.Dynamic Binding in Java

When the type of the object is determined at **run-time**, it is known as **dynamic binding**. Dynamic binding occurs with overridden methods, where the method call depends on the actual object being referred to, not the reference type.

### Example of Dynamic Binding

The following example demonstrates the dynamic binding:

[](https://www.tpointtech.com/static-and-dynamic-binding-in-java#)[](https://www.tpointtech.com/static-and-dynamic-binding-in-java#)[](https://www.tpointtech.com/static-and-dynamic-binding-in-java#)

1. class Animal{  
2.  void eat(){System.out.println("animal is eating...");}  
3. }  

4. class Dog extends Animal{  
5.  void eat(){System.out.println("dog is eating...");}  

6.  public static void main(String args[]){  
7.   Animal a=new Dog();  
8.   a.eat();  
9.  }  
10. }  

**Output:**

dog is eating...

In the above example object type cannot be determined by the compiler, because the instance of Dog is also an instance of Animal. So compiler doesn't know its type, only its base type.

## Difference Between Static and Dynamic Binding

The following table shows the difference between static and dynamic binding in Java:

|Static Binding|Dynamic Binding|
|---|---|
|Static binding occurs at compile time, when the compiler determines which method to call.|Dynamic binding occurs at run time, when the method to be called is determined based on the actual object.|
|It is used with private, final, static methods, and method overloading.|It is used with overridden methods to achieve runtime polymorphism.|
|In static binding, the method call depends on the reference type.|In dynamic binding, the method call depends on the actual object type.|
|Static binding provides compile-time polymorphism.|Dynamic binding provides runtime polymorphism.|