The **Object class** is the parent class of all the classes in java by default. In other words, it is the topmost class of java.

The Object class is beneficial if you want to refer any object whose type you don't know. Notice that parent class reference variable can refer the child class object, know as upcasting.

Let's take an example, there is getObject() method that returns an object but it can be of any type like Employee,Student etc, we can use Object class reference to refer that object. For example:

[](https://www.tpointtech.com/object-class-in-java#)[](https://www.tpointtech.com/object-class-in-java#)[](https://www.tpointtech.com/object-class-in-java#)

1. Object obj=getObject();//we don't know what object will be returned from this method  

The Object class provides some common behaviors to all the objects such as object can be compared, object can be cloned, object can be notified etc.

![object class in java](https://images.tpointtech.com/images/core/objectclass.gif)

## public class Object

The Object class is the **root class** in Java from which every class implicitly inherits.

### Syntax

Here is the syntax:

[](https://www.tpointtech.com/object-class-in-java#)[](https://www.tpointtech.com/object-class-in-java#)[](https://www.tpointtech.com/object-class-in-java#)

1. public class Object {  
2.     // class body  
3. }  

## Constructor Summary

The Object class provides a **default constructor** to create a new object instance.

### Syntax

The following is the syntax of invoking default constructor of Object class:

[](https://www.tpointtech.com/object-class-in-java#)[](https://www.tpointtech.com/object-class-in-java#)[](https://www.tpointtech.com/object-class-in-java#)

1. Object obj = new Object();  

## Constructor Detail

The constructor of the Object class has **no parameters** and initializes a new instance of the object.

### Syntax

The following is the syntax of constructor detail:

[](https://www.tpointtech.com/object-class-in-java#)[](https://www.tpointtech.com/object-class-in-java#)[](https://www.tpointtech.com/object-class-in-java#)

1. public Object() {  
2.     // default constructor  
3. }  

## Methods of Object class

The following tables lists the commonly used methods of object class:

|Method|Description|
|---|---|
|public final Class getClass()|returns the Class class object of this object. The Class class can further be used to get the metadata of this class.|
|public int hashCode()|returns the hashcode number for this object.|
|public boolean equals(Object obj)|compares the given object to this object.|
|protected Object clone() throws CloneNotSupportedException|creates and returns the exact copy (clone) of this object.|
|public String toString()|returns the string representation of this object.|
|public final void notify()|wakes up single thread, waiting on this object's monitor.|
|public final void notifyAll()|wakes up all the threads, waiting on this object's monitor.|
|public final void wait(long timeout)throws InterruptedException|causes the current thread to wait for the specified milliseconds, until another thread notifies (invokes notify() or notifyAll() method).|
|public final void wait(long timeout,int nanos)throws InterruptedException|causes the current thread to wait for the specified milliseconds and nanoseconds, until another thread notifies (invokes notify() or notifyAll() method).|
|public final void wait()throws InterruptedException|causes the current thread to wait, until another thread notifies (invokes notify() or notifyAll() method).|
|protected void finalize()throws Throwable|is invoked by the garbage collector before object is being garbage collected.|

## Examples of Object Class Methods

Here are examples of commonly used methods of the Object class:

### Example 1: Use of toString() Method

The following example demonstrates the toString() method that returns a string representation of the object:

[](https://www.tpointtech.com/object-class-in-java#)[](https://www.tpointtech.com/object-class-in-java#)[](https://www.tpointtech.com/object-class-in-java#)

1. public class Main {  
2.     public static void main(String[] args) {  
3.         Object obj = new Object();  
4.         System.out.println("Object as String: " + obj.toString());  
5.     }  
6. }  

**Output:**

Object as String: java.lang.Object@1b6d3586

### Example 2: Use of equals() Method

The following example demonstrates the equals() method that checks whether two objects are equal:

[](https://www.tpointtech.com/object-class-in-java#)[](https://www.tpointtech.com/object-class-in-java#)[](https://www.tpointtech.com/object-class-in-java#)

1. public class Main {  
2.     public static void main(String[] args) {  
3.         String str1 = "Java";  
4.         String str2 = "Java";  
5.         System.out.println("Are the strings equal? " + str1.equals(str2));  
6.     }  
7. }  

**Output:**

Are the strings equal? True

### Example 3: Use of hashCode() Method

The following example demonstrates the hashCode() method that returns the hash code value of an object.

[](https://www.tpointtech.com/object-class-in-java#)[](https://www.tpointtech.com/object-class-in-java#)[](https://www.tpointtech.com/object-class-in-java#)

1. public class Main {  
2.     public static void main(String[] args) {  
3.         Object obj = new Object();  
4.         System.out.println("Hash code of the object: " + obj.hashCode());  
5.     }  
6. }  

**Output:**

Hash code of the object: 460141958