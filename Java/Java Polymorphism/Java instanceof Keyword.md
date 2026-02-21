This chapter explains the **instanceof operator in Java**, which is used to **check an object's type at runtime**, compare it with a class, subclass, or interface, and determine the relationship between objects and their types.

## What is the instanceof Operator in Java?

The **instanceof operator** is used to check whether an object is an instance of a specific class, subclass, or interface. It is also called the **type comparison operator** because it compares an object with a type and returns **true** or **false**. If the object being tested is null, the operator always returns **false**.

## Syntax of instanceof Operator

The following is the syntax of instanceof Operator:

[](https://www.tpointtech.com/downcasting-with-instanceof-operator#)[](https://www.tpointtech.com/downcasting-with-instanceof-operator#)[](https://www.tpointtech.com/downcasting-with-instanceof-operator#)

1. objectReference instanceof ClassName  

**Here**

- **objectReference:** The reference variable of the object to be tested.
- **ClassName:** the class, subclass, or interface against which the object is tested.
- The operator returns true if the object is an instance of the specified type; otherwise, it returns false.

## Examples of instanceof Operator

Practice these examples to understand how the instanceof operator works?

### Example 1

The following example demonstrates a simple use of the instanceof operator to test an object against its own class.

[](https://www.tpointtech.com/downcasting-with-instanceof-operator#)[](https://www.tpointtech.com/downcasting-with-instanceof-operator#)[](https://www.tpointtech.com/downcasting-with-instanceof-operator#)

1. class Simple1{  
2.  public static void main(String args[]){  
3.  Simple1 s=new Simple1();  
4.  System.out.println(s instanceof Simple1);//true  
5.  }  
6. }  

**Output:**

true

An object of subclass type is also a type of parent class. For example, if Dog extends Animal then object of Dog can be referred by either Dog or Animal class.

### Example 2

The following example shows that an object of a subclass is also considered an instance of its parent class.

[](https://www.tpointtech.com/downcasting-with-instanceof-operator#)[](https://www.tpointtech.com/downcasting-with-instanceof-operator#)[](https://www.tpointtech.com/downcasting-with-instanceof-operator#)

1. class Animal{}  
2. class Dog1 extends Animal{//Dog inherits Animal  

3.  public static void main(String args[]){  
4.  Dog1 d=new Dog1();  
5.  System.out.println(d instanceof Animal);//true  
6.  }  
7. }  

**Output:**

true

## The instanceof Operator with a Null Variable

If we apply the instanceof operator to a variable that has a **null value**, it always returns **false**.

### Example

Let's see the example given below where we apply instanceof operator with the variable that have null value.

[](https://www.tpointtech.com/downcasting-with-instanceof-operator#)[](https://www.tpointtech.com/downcasting-with-instanceof-operator#)[](https://www.tpointtech.com/downcasting-with-instanceof-operator#)

1. class Dog2{  
2.  public static void main(String args[]){  
3.   Dog2 d=null;  
4.   System.out.println(d instanceof Dog2);//false  
5.  }  
6. }  

**Output:**

false

## Downcasting with the instanceof Operator

When Subclass type refers to the object of Parent class, it is known as downcasting. If we perform it directly, compiler gives Compilation error. If you perform it by typecasting, ClassCastException is thrown at runtime. But if we use instanceof operator, downcasting is possible.

[](https://www.tpointtech.com/downcasting-with-instanceof-operator#)[](https://www.tpointtech.com/downcasting-with-instanceof-operator#)[](https://www.tpointtech.com/downcasting-with-instanceof-operator#)

1. Dog d=new Animal();//Compilation error  

If we perform downcasting by typecasting, ClassCastException is thrown at runtime.

[](https://www.tpointtech.com/downcasting-with-instanceof-operator#)[](https://www.tpointtech.com/downcasting-with-instanceof-operator#)[](https://www.tpointtech.com/downcasting-with-instanceof-operator#)

1. Dog d=(Dog)new Animal();  
2. //Compiles successfully but ClassCastException is thrown at runtime  

## Safe Downcasting Using instanceof

The instanceof operator allows safe downcasting by checking the object type before casting.

### Example

The following example demonstrates the safe downcasting using instanceof operator:

[](https://www.tpointtech.com/downcasting-with-instanceof-operator#)[](https://www.tpointtech.com/downcasting-with-instanceof-operator#)[](https://www.tpointtech.com/downcasting-with-instanceof-operator#)

1. class Animal { }  

2. class Dog3 extends Animal {  
3.   static void method(Animal a) {  
4.     if(a instanceof Dog3){  
5.        Dog3 d=(Dog3)a;//downcasting  
6.        System.out.println("ok downcasting performed");  
7.     }  
8.   }  

9.   public static void main (String [] args) {  
10.     Animal a=new Dog3();  
11.     Dog3.method(a);  
12.   }  

13.  }  

**Output:**

ok downcasting performed

## Downcasting Without instanceof

Downcasting can also work without instanceof if the actual object type matches the reference type.

### Example

The following example demonstrates the downcasting without using the instanceof operator:

[](https://www.tpointtech.com/downcasting-with-instanceof-operator#)[](https://www.tpointtech.com/downcasting-with-instanceof-operator#)[](https://www.tpointtech.com/downcasting-with-instanceof-operator#)

1. class Animal { }  
2. class Dog4 extends Animal {  
3.   static void method(Animal a) {  
4.        Dog4 d=(Dog4)a;//downcasting  
5.        System.out.println("ok downcasting performed");  
6.   }  
7.    public static void main (String [] args) {  
8.     Animal a=new Dog4();  
9.     Dog4.method(a);  
10.   }  
11. }  

**Output:**

ok downcasting performed

**Note:** If the actual object is not a Dog4, a ClassCastException is thrown. Using instanceof avoids this runtime error.

[](https://www.tpointtech.com/downcasting-with-instanceof-operator#)[](https://www.tpointtech.com/downcasting-with-instanceof-operator#)[](https://www.tpointtech.com/downcasting-with-instanceof-operator#)

1. Animal a=new Animal();  
2. Dog.method(a);  
3. //Now ClassCastException but not in case of instanceof operator  

## Real Use of instanceof Operator

The instanceof operator is very useful when you work with interfaces or polymorphic objects. It lets you safely convert types and calls the right method when the program runs.

### Example

The following example demonstrates the real use of the instanceof operator to safely perform downcasting and invoke subclass-specific methods when working with interface references.

[](https://www.tpointtech.com/downcasting-with-instanceof-operator#)[](https://www.tpointtech.com/downcasting-with-instanceof-operator#)[](https://www.tpointtech.com/downcasting-with-instanceof-operator#)

1. interface Printable{}  
2. class A implements Printable{  
3. public void a(){System.out.println("a method");}  
4. }  
5. class B implements Printable{  
6. public void b(){System.out.println("b method");}  
7. }  

8. class Call{  
9. void invoke(Printable p){//upcasting  
10. if(p instanceof A){  
11. A a=(A)p;//Downcasting   
12. a.a();  
13. }  
14. if(p instanceof B){  
15. B b=(B)p;//Downcasting   
16. b.b();  
17. }  

18. }  
19. }//end of Call class  

20. class Test4{  
21. public static void main(String args[]){  
22. Printable p=new B();  
23. Call c=new Call();  
24. c.invoke(p);  
25. }  
26. }  

**Output:**

b method