Cloning means to create a replica of something. In programming, object cloning refers to create a copy of an object. [Java](https://www.tpointtech.com/java-tutorial) [Object class](https://www.tpointtech.com/object-class-in-java) provides the Object.clone() method to create a copy of an object (already existing). This feature is extremely handy when we must make copies of complex objects whose copying of properties would be time-consuming and prone to errors when doing it manually.

![Object Cloning in Java | Object.clone() Method](https://images.tpointtech.com/core/images/object-cloning-java-1.png)

## Object.clone() Method

The Object.clone() method is defined in the Object class. It means every Java class inherits it by default. Its primary purpose is to return a field-by-field copy of the object on which it is invoked. However, the method is protected in the Object class it means that it cannot be directly accessed by classes unless overridden with a public scope.

### Syntax:

[](https://www.tpointtech.com/object-cloning#)[](https://www.tpointtech.com/object-cloning#)[](https://www.tpointtech.com/object-cloning#)

1. protected Object clone() throws CloneNotSupportedException    

### Creating Clone of an Object

The **java.lang.Cloneable interface** must be implemented by the class whose object clone we want to create. If we do not implement Cloneable interface, Object.clone() method generates **CloneNotSupportedException**.

### Example: Cloning an Object

[](https://www.tpointtech.com/object-cloning#)[](https://www.tpointtech.com/object-cloning#)[](https://www.tpointtech.com/object-cloning#)

1. class Student implements Cloneable {  
2.     int id;  
3.     String name;  
4.     Student(int id, String name) {  
5.         this.id = id;  
6.         this.name = name;  
7.     }  
8.     // Overriding clone() method  
9.     public Object clone() throws CloneNotSupportedException {  
10.         return super.clone();  
11.     }  
12. }  
13. public class Main {  
14.     public static void main(String[] args) {  
15.         try {  
16.             Student s1 = new Student(101, "Jack");  
17.             Student s2 = (Student) s1.clone();  
18.             System.out.println("Original Student Object: " + s1.id + " - " + s1.name);  
19.             System.out.println("Cloned Student Object: " + s2.id + " - " + s2.name);  
20.             // Modifying cloned object  
21.             s2.name = "Smith";  
22.             System.out.println("\nAfter modifying cloned object:");  
23.             System.out.println("Original Student Object: " + s1.id + " - " + s1.name);  
24.             System.out.println("Cloned Student Object: " + s2.id + " - " + s2.name);  
25.         } catch (CloneNotSupportedException e) {  
26.             e.printStackTrace();  
27.         }  
28.     }  
29. }  

**Output:**

Original Student Object: 101 - Jack
Cloned Student Object: 101 - Jack

After modifying cloned object:
Original Student Object: 101 - Jack
Cloned Student Object: 101 - Smith

**Explanation**

In the above program, both reference variables have the same value. Thus, the Object.clone() method copies the values of an object to another object. So, we do not need to write explicit code to copy the value of an object to another.

If we create another object by using the new keyword and assign the values of another object to this one, it will require a lot of processing on this object. Therefore, to save the extra processing task we use Object.clone() method.

## Why use Object.clone() method?

The Object.clone() method saves the extra processing task for creating the exact copy of an object. If we perform it by using the new keyword, it will take a lot of processing time to be performed that is why we use object cloning.

## Advantage of Object Cloning

Although Object.clone() has some design issues but it is still a popular and easy way of copying objects.

- You do not need to write lengthy and repetitive codes. Just use an abstract class with a 4- or 5-line long clone() method.
- It is the easiest and most efficient way for copying objects, especially if we are applying it to an already developed or an old project. Just define a parent class, implement Cloneable in it, provide the definition of the clone() method and the task will be done.
- clone() method is the fastest way to copy array.

## Disadvantage of Object Cloning

- To use the Object.clone() method, we have to change a lot of syntaxes to our code, like implementing a Cloneable interface, defining the clone() method and handling CloneNotSupportedException, and finally, calling Object.clone() etc.
- We have to implement cloneable interface while it does not have any methods in it. We just have to use it to tell the JVM that we can perform clone() on our object.
- clone() is protected, so we have to provide our own clone() and indirectly call Object.clone() from it.
- clone() doesn't invoke any constructor so we do not have any control over object construction.
- If you want to write a clone() method in a child class then all of its superclasses should define the clone() method in them or inherit it from another parent class. Otherwise, the super.clone() chain will fail.
- clone() supports only shallow copying but we will need to override it if we need deep cloning.

## Conclusion

Java Object.clone() is a highly powerful technique somewhat deceitful and is capable of copying objects. With the implementation of the Cloneable interface and re-writing the clone method, developers can engage in shallow or deep copying of objects according to their needs.

Deep copying is slow and complex and shallow copying is very quick and easy. As much as cloning is convenient, the pros and cons of cloning need to be considered against the options such as copy constructors. With the current development, cloning may be either the right or wrong choice, depending on the complexity of the class, and the performance standards of the application.