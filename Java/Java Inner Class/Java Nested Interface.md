A nested interface is an [interface](https://www.tpointtech.com/access-modifiers-in-java) declared within another interface or class. **Nested interfaces** are used to group related interfaces to make the code easier to organize and maintain. A nested interface must be accessed through its outer interface or class and cannot be accessed directly.

## Rules to Create a Nested Interface

When creating a nested interface, the following rules should be remembered:

1. A nested interface must be declared public if it is defined inside another interface.
2. If the nested interface is defined inside a class, it can have any [access modifier](https://www.tpointtech.com/access-modifiers-in-java) (public, protected, private, or default).
3. All nested interfaces are implicitly static, so you do not need to use the [static keyword](https://www.tpointtech.com/access-modifiers-in-java) explicitly.
4. A nested interface must be accessed through its outer interface or class; it cannot be accessed directly.

## Creating Nested Interface

A nested interface can be created by declaring it inside another interface or inside a class and it must be accessed through its outer interface or class and cannot be accessed directly.

### Syntax (Inside an Interface)

The syntax to create a nested interface inside an interface is as follows:

[](https://www.tpointtech.com/nested-interface#)[](https://www.tpointtech.com/nested-interface#)[](https://www.tpointtech.com/nested-interface#)

1. interface OuterInterface {    
2.     interface NestedInterface {    
3.         void method();    
4.     }    
5. }  

### Syntax (Inside a Class)

The syntax to create a nested interface inside ac class is as follows:

[](https://www.tpointtech.com/nested-interface#)[](https://www.tpointtech.com/nested-interface#)[](https://www.tpointtech.com/nested-interface#)

1. class OuterClass {    
2.     interface NestedInterface {    
3.         void method();    
4.     }    
5. }   

### Example: Nested Interface (Interface within an Interface)

The following example demonstrates creating and using a nested interface which is declared inside an interface:

[](https://www.tpointtech.com/nested-interface#)[](https://www.tpointtech.com/nested-interface#)[](https://www.tpointtech.com/nested-interface#)

1. interface Showable{  
2.   void show();  
3.   interface Message{  
4.    void msg();  
5.   }  
6. }  
7. class TestNestedInterface1 implements Showable.Message{  
8.  public void msg(){System.out.println("Hello nested interface");}  

9.  public static void main(String args[]){  
10.   Showable.Message message=new TestNestedInterface1();//upcasting here  
11.   message.msg();  
12.  }  
13. }  

**Output:**

hello nested interface

As you can see in the above example, we are accessing the Message interface by its outer interface Showable because it cannot be accessed directly. It is just like the almirah inside the room; we cannot access the almirah directly because we must enter the room first. In the collection framework, the sun microsystem has provided a nested interface Entry. Entry is the subinterface of Map, i.e., accessed by Map.Entry.

### Example: Nested Interface (Interface within a class)

The following example demonstrates creating and using a nested interface which is declared inside a class:

[](https://www.tpointtech.com/nested-interface#)[](https://www.tpointtech.com/nested-interface#)[](https://www.tpointtech.com/nested-interface#)

1. public static interface Showable$Message  
2. {  
3.   public abstract void msg();  
4. }  

### Example of nested interface which is declared within the class

Let's see how we can define an interface inside the class and how we can access it.

[](https://www.tpointtech.com/nested-interface#)[](https://www.tpointtech.com/nested-interface#)[](https://www.tpointtech.com/nested-interface#)

1. class A{  
2.   interface Message{  
3.    void msg();  
4.   }  
5. }  

6. class TestNestedInterface2 implements A.Message{  
7.  public void msg(){System.out.println("Hello nested interface");}  

8.  public static void main(String args[]){  
9.   A.Message message=new TestNestedInterface2();//upcasting here  
10.   message.msg();  
11.  }  
12. }  

**Output:**

hello nested interface

## Class Inside a Nested Interface

A class can be defined inside an interface, including a nested interface. When a class is defined inside an interface, the Java compiler automatically treats it as a [static nested class](https://www.tpointtech.com/static-nested-class). This allows the class to be accessed using the interface name without creating an instance of the interface.

### Example

The following example demonstrates creating a class inside an interface:

[](https://www.tpointtech.com/nested-interface#)[](https://www.tpointtech.com/nested-interface#)[](https://www.tpointtech.com/nested-interface#)

1. interface M {    
2.     class A {    
3.         void display() {    
4.             System.out.println("Class inside interface");    
5.         }    
6.     }    
7. }    

8. public class TestClassInInterface {    
9.     public static void main(String[] args) {    
10.         // Access the nested class using the interface name  
11.         M.A obj = new M.A();    
12.         obj.display();    
13.     }    
14. }  

**Output:**

Class inside interface