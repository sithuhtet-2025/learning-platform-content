Java anonymous inner class is an inner class without a name and for which only a single object is created. An anonymous inner class can be useful when making an instance of an object with certain "extras" such as overloading methods of a class or interface, without having to actually subclass a class.

In simple words, a class that has no name is known as an anonymous inner class. It should be used if you have to override a method of class or interface.

## Different Ways to Create Anonymous Inner Class

An anonymous inner class is a class without a name. It can be created in two ways:

1. **Using a class (abstract or concrete):**  
    The anonymous class **extends an existing class** and provides an implementation for its methods without creating a separate named subclass. It is often used for **short-term method overrides**.
2. **Using an interface:**  
    The anonymous class **implements an interface** and provides concrete implementations for its methods. This is commonly used for **callbacks, event handling, or single-use interface implementations****.**

## Creating Anonymous Inner Class Using a Class

An anonymous inner class can be created by extending a class ([abstract](https://www.tpointtech.com/interface-in-java) or concrete) without giving it a name. It allows you to [override methods of the class](https://www.tpointtech.com/method-overriding-in-java) in a concise way without creating a separate subclass.

### Example

The following example demonstrates creating anonymous inner class using a class:

[](https://www.tpointtech.com/anonymous-inner-class#)[](https://www.tpointtech.com/anonymous-inner-class#)[](https://www.tpointtech.com/anonymous-inner-class#)

1. abstract class Person{  
2.   abstract void eat();  
3. }  
4. class TestAnonymousInner{  
5.  public static void main(String args[]){  
6.   Person p=new Person(){  
7.   void eat(){System.out.println("nice fruits");}  
8.   };  
9.   p.eat();  
10.  }  
11. }  

**Output:**

nice fruits

## Creating Anonymous Inner Class Using an Interface

An anonymous inner class can also be created by implementing an [interface](https://www.tpointtech.com/interface-in-java). It provides the implementation of the interface's methods without creating a separate class.

### Example

The following example demonstrates creating anonymous inner class using an interface:

[](https://www.tpointtech.com/anonymous-inner-class#)[](https://www.tpointtech.com/anonymous-inner-class#)[](https://www.tpointtech.com/anonymous-inner-class#)

1. interface Eatable{  
2.  void eat();  
3. }  
4. class TestAnnonymousInner1{  
5.  public static void main(String args[]){  
6.  Eatable e=new Eatable(){  
7.   public void eat(){System.out.println("nice fruits");}  
8.  };  
9.  e.eat();  
10.  }  
11. }  

**Output:**

nice fruits