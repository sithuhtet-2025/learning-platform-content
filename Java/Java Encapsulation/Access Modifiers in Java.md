Access modifiers in Java are keywords that define where a class, method, or variable can be accessed. These modifiers help to protect data and control access to code. In this chapter, we will learn about the access modifiers and how they control the visibility of classes, methods, and variables.

## What are Access Modifiers in Java?

Access modifiers are keywords that define the visibility or accessibility of classes, methods, constructors, and variables. They control where these members can be accessed from such as inside the same class, within the same package, or from other packages. By applying the access modifiers, we can restrict or allow access.

There are four types of access modifiers in Java:

- public
- private
- protected
- default

Let us understand each access modifiers in details.

## 1. public Access Modifier

The access level of a public modifier is everywhere. It can be accessed from within the class, outside the class, within the package and outside the package. It has the widest scope among all other modifiers.

### Example

The following example demonstrates the use of public access modifiers.

[](https://www.tpointtech.com/access-modifiers-in-java#)[](https://www.tpointtech.com/access-modifiers-in-java#)[](https://www.tpointtech.com/access-modifiers-in-java#)

1. //save by A.java      
2. package pack;    
3. public class A {    
4. public void msg() { System.out.println("Hello"); }    
5. }    

 

[](https://www.tpointtech.com/access-modifiers-in-java#)[](https://www.tpointtech.com/access-modifiers-in-java#)[](https://www.tpointtech.com/access-modifiers-in-java#)

1. //save by Main.java      
2. package mypack;    
3. import pack.*;    
4. class Main {    
5.   public static void main (String args[]) {    
6.    A obj = new A();    
7.    obj.msg();    
8.   }    
9. }    

**Output:**

Hello

## 2. private Access Modifier

The access level of a private modifier is only within the class. It cannot be accessed from outside the class.

### Example

The following example demonstrates the use of private access modifiers.

[](https://www.tpointtech.com/access-modifiers-in-java#)[](https://www.tpointtech.com/access-modifiers-in-java#)[](https://www.tpointtech.com/access-modifiers-in-java#)

1. class A{    
2. private int data=40;    
3. private void msg(){System.out.println("Hello java");}    
4. }     
5. public class Main{    
6.  public static void main(String args[]){    
7.    A obj=new A();    
8.    System.out.println(obj.data);//Compile Time Error    
9.    obj.msg();//Compile Time Error    
10.    }    
11. }    

When we compile the above program, it shows the following compile-time error

Main.java:8: error: data has private access in A
System.out.println(obj.data);//Compile Time Error
^
Main.java:9: error: msg() has private access in A
obj.msg();//Compile Time Error
^
2 errors

### Role of Private Constructor

If you make any class constructor private, you cannot create an instance of that class from outside the class. For example:

[](https://www.tpointtech.com/access-modifiers-in-java#)[](https://www.tpointtech.com/access-modifiers-in-java#)[](https://www.tpointtech.com/access-modifiers-in-java#)

1. class A{    
2. private A(){}//private constructor    
3. void msg(){System.out.println("Hello java");}    
4. }    
5. public class Main{    
6.  public static void main(String args[]){    
7.    A obj=new A();//Compile Time Error    
8.  }    
9. }    

When we compile the above program, it shows the following compile-time error.

Main.java:7: error: A() has private access in A
A obj=new A();//Compile Time Error
^
1 error

#### Note: A class cannot be private or protected except nested class.

## 3. protected Access Modifier

The protected access modifier is accessible within the package and outside the package, but through inheritance only. The protected access modifier can be applied to the data member, method and constructor. It cannot be applied to the class. It provides more accessibility than the default modifier.

### Example

The following example demonstrates the use of protected access modifiers.

[](https://www.tpointtech.com/access-modifiers-in-java#)[](https://www.tpointtech.com/access-modifiers-in-java#)[](https://www.tpointtech.com/access-modifiers-in-java#)

1. //save by A.java    
2. package pack;    
3. public class A {    
4. protected void msg() { System.out.println("Hello"); }    
5. }    

 

[](https://www.tpointtech.com/access-modifiers-in-java#)[](https://www.tpointtech.com/access-modifiers-in-java#)[](https://www.tpointtech.com/access-modifiers-in-java#)

1. //save by Main.java    
2. package mypack;    
3. import pack.*;    
4. class Main extends A {    
5.   public static void main (String args[]) {    
6.    B obj = new B();    
7.    obj.msg();    
8.   }    
9. }    

**Output:**

Hello

## 4. Default Access Modifier

When we do not specify any specifier, the default access specifier is prefixed by default. The default modifier is accessible within a package only. It cannot be accessed from outside the package. It provides more accessibility than private. But it is more restrictive than protected and public.

### Example

The following example demonstrates the use of default access modifiers.

[](https://www.tpointtech.com/access-modifiers-in-java#)[](https://www.tpointtech.com/access-modifiers-in-java#)[](https://www.tpointtech.com/access-modifiers-in-java#)

1. //save by A.java    
2. package pack;    
3. class A {    
4.   void msg() {System.out.println("Hello"); }    
5. }    

 

[](https://www.tpointtech.com/access-modifiers-in-java#)[](https://www.tpointtech.com/access-modifiers-in-java#)[](https://www.tpointtech.com/access-modifiers-in-java#)

1. //save by Main.java    
2. package mypack;    
3. import pack.*;    
4. public class Main {    
5.   public static void main (String args[])   {    
6.    A obj = new A();//Compile Time Error    
7.    obj.msg();           //Compile Time Error    
8.   }    
9. }    

**Output:**

Compile Time Error

In the above example, the scope of class A and its method msg() is default, so it cannot be accessed from outside the package. When we compile the above program, we get a compile-time error.

## Access Modifiers with Method Overriding

Access modifiers also affect [method overriding](https://www.tpointtech.com/method-overriding-in-java) in [inheritance](https://www.tpointtech.com/inheritance-in-java). When a subclass overrides a method from its parent class, the overridden method cannot have a more restrictive access modifier than the original method.

### Rules

Follow the below given rules while using the access modifiers with the method overriding:

- A method declared as **public** in the parent class must be **public** in the child class.
- A method declared as **protected** in the parent class can be protected or **public** in the child class.
- A method with **default** (no modifier) in the parent class can be **default** or **protected** or **public** in the child class, but **not private**.
- A method declared as **private** in the parent class is **not inherited**, so it cannot be overridden.

### Example

The following example demonstrates the access specifiers with method overloading.

[](https://www.tpointtech.com/access-modifiers-in-java#)[](https://www.tpointtech.com/access-modifiers-in-java#)[](https://www.tpointtech.com/access-modifiers-in-java#)

1. class A {    
2. protected void msg() { System.out.println("Hello java"); }    
3. }    
4. public class Main extends A {    
5. void msg(){System.out.println("Hello java"); }             //C.T.Error    
6.  public static void main (String args[]) {    
7.    Main obj=new Main();    
8.    obj.msg();    
9.    }    
10. }    

The default modifier is more restrictive than protected. That is why there is a compile-time error.

### Accessibility or Scope of Java Access Modifiers

The following table shows the accessibility or scope of Java access modifiers:

|Access Modifier|Within Class|Within Package|Outside Package by Subclass Only|Outside Package|
|---|---|---|---|---|
|**Private**|Y|N|N|N|
|**Default**|Y|Y|N|N|
|**Protected**|Y|Y|Y|N|
|**Public**|Y|Y|Y|Y|

### 1. public

- Accessible from anywhere (inside/outside the package).
- Has the widest accessibility.
- Used for methods and classes that need to be globally accessible.

### 2. private

- Strictly the most restrictive modifier.
- Limits access only to within the same class.
- Essential for encapsulation and protecting sensitive data.
- Not accessible outside the class, even in the same package.
- Private constructor prevents object creation outside the class.

### 3. protected

- Accessible within the same package.
- Accessible outside the package, but only through inheritance.
- More accessible than the default, but more restrictive than the public.

### 4. default

- When no modifier is specified.
- Limited access only to other classes within the same package.
- Cannot be accessed outside the package, even by subclasses.