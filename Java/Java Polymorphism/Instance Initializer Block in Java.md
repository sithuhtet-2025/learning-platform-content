In Java, when we create an object, we sometimes need to set values for its variables. While we can assign values directly, extra steps may be needed during initialization. This is where the Instance Initializer Block is useful. In this chapter, we will learn about the **Instance Initializer Block** and see how it works with the help of examples.

## What is Instance Initializer Block in Java?

An **Instance Initializer Block** is used to initialize instance variables. It runs every time when an object of the class is created and can perform additional operations while initializing.

## Syntax of Instance Initializer Block

An **Instance Initializer Block** is written inside a class but **outside any method or constructor**. It is enclosed within curly braces **{ }.**

### Syntax

The following is syntax to initialize instance variables:

[](https://www.tpointtech.com/instance-initializer-block-in-java#)[](https://www.tpointtech.com/instance-initializer-block-in-java#)[](https://www.tpointtech.com/instance-initializer-block-in-java#)

1. {  
2.     // code to initialize instance variables  
3. }  

### Points to Remember:

Some of the important points regarding instance initializer block are:

- It is used to initialize instance variables.
- You can have multiple instance initializer blocks in a class; they execute in the order they appear.
- It runs before the constructor when an object is created.

## Example of Instance Initializer Block

Let's see the simple example of instance initializer block that performs initialization.

[](https://www.tpointtech.com/instance-initializer-block-in-java#)[](https://www.tpointtech.com/instance-initializer-block-in-java#)[](https://www.tpointtech.com/instance-initializer-block-in-java#)

1. class Bike7{  
2.     int speed;  

3.     Bike7(){System.out.println("speed is "+speed);}  

4.     {speed=100;}  

5.     public static void main(String args[]){  
6.     Bike7 b1=new Bike7();  
7.     Bike7 b2=new Bike7();  
8.     }      
9. }  

**Output:**

speed is 100
speed is 100

There are three places in java where you can perform operations:

1. method
2. constructor
3. block

## Order of Execution: Instance Initializer Block and Constructor

In Java, when an object is created, both the **instance initializer block** and the [constructor](https://www.tpointtech.com/java-constructor) are executed. The instance initializer block may appear to run first, but internally, the Java compiler inserts the code of the instance initializer block into the constructor after the call to **super()**. This means the constructor starts execution first, and then the instance initializer block code is executed.

### Example

The following example demonstrates the order of execution of instance initializer block and constructor:

[](https://www.tpointtech.com/instance-initializer-block-in-java#)[](https://www.tpointtech.com/instance-initializer-block-in-java#)[](https://www.tpointtech.com/instance-initializer-block-in-java#)

1. class Bike8 {    
2.     int speed;    

3.     Bike8() {  
4.         System.out.println("constructor is invoked");  
5.     }    

6.     {    
7.         System.out.println("instance initializer block invoked");  
8.     }    

9.     public static void main(String args[]) {    
10.         Bike8 b1 = new Bike8();    
11.         Bike8 b2 = new Bike8();    
12.     }        
13. }  

**Output:**

instance initializer block invoked
constructor is invoked
instance initializer block invoked
constructor is invoked

In the above example, it seems that instance initializer block is firstly invoked but NO. Instance intializer block is invoked at the time of object creation. The [Java compiler](https://www.tpointtech.com/compiler/java) copies the instance initializer block in the constructor after the first statement super(). So firstly, constructor is invoked. Let's understand it by the figure given below:

#### Note: The java compiler copies the code of instance initializer block in every constructor.

![instance initializer block](https://images.tpointtech.com/images/instanceinitializerblock.jpg)

## Rules for instance initializer block

There are mainly three important rules of the instance initializer block in Java:

1. The instance initializer block is executed whenever an object of the class is created.
2. The instance initializer block is invoked **after the parent class constructor (super()) is called**.
3. If a class has multiple instance initializer blocks, they are executed **in the order in which they appear in the class**.

## Instance Initializer Block Executed After super() Call

The following program shows that the instance initializer block is executed after the parent class constructor (super()) is called and before the child class constructor body is executed:

### Example

[](https://www.tpointtech.com/instance-initializer-block-in-java#)[](https://www.tpointtech.com/instance-initializer-block-in-java#)[](https://www.tpointtech.com/instance-initializer-block-in-java#)

1. class A {    
2.     A() {    
3.         System.out.println("parent class constructor invoked");    
4.     }    
5. }    

6. class B2 extends A {    
7.     B2() {    
8.         super();    
9.         System.out.println("child class constructor invoked");    
10.     }    

11.     {    
12.         System.out.println("instance initializer block is invoked");    
13.     }    

14.     public static void main(String args[]) {    
15.         B2 b = new B2();    
16.     }    
17. }  

**Output:**

parent class constructor invoked
instance initializer block is invoked
child class constructor invoked

### Explanation

- When an object of the child class is created, the parent class constructor is called first using super().
- After that, the instance initializer block is executed.
- Finally, the child class constructor body is executed.

## Instance Initializer Block with Multiple Constructors

This example demonstrates that the instance initializer block is executed for every object creation, regardless of which constructor is called.

### Example

[](https://www.tpointtech.com/instance-initializer-block-in-java#)[](https://www.tpointtech.com/instance-initializer-block-in-java#)[](https://www.tpointtech.com/instance-initializer-block-in-java#)

1. class A {    
2.     A() {    
3.         System.out.println("parent class constructor invoked");    
4.     }    
5. }    

6. class B3 extends A {    
7.     B3() {    
8.         super();    
9.         System.out.println("child class constructor invoked");    
10.     }    

11.     B3(int a) {    
12.         super();    
13.         System.out.println("child class constructor invoked " + a);    
14.     }    

15.     {    
16.         System.out.println("instance initializer block is invoked");    
17.     }    

18.     public static void main(String args[]) {    
19.         B3 b1 = new B3();    
20.         B3 b2 = new B3(10);    
21.     }    
22. }  

**Output:**

parent class constructor invoked
instance initializer block is invoked
child class constructor invoked
parent class constructor invoked
instance initializer block is invoked
child class constructor invoked 10

### Explanation

- Each time an object of class B3 is created, the parent class constructor is invoked first.
- The instance initializer block is executed next.
- Finally, the corresponding child class constructor body is executed.
- The instance initializer block runs for **both constructors**, showing that it is independent of constructor overloading.