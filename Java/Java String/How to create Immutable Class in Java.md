In Java, immutability refers an object's state that cannot be changed once it is created. Immutable classes, like String and wrapper classes (Integer, Boolean, etc.), provided benefits such as thread safety and easier debugging. In this chapter, we will learn what immutability is and how to create immutable classes.

## What is an Immutable Class?

An immutable class is a class whose objects cannot be modified after they are created; if you make any change that results in a new object instead of altering the existing one.

For example, the String class in Java is immutable, once a String object is created, its value cannot be changed; if you make any modification, it creates a new String object.

## How to Create an Immutable Class?

The following are the key rules to create an immutable class:

1. **Declare the class as final**  
    This prevents the class from being extended and modified by subclasses.
2. **Make all fields private and final**  
    This ensures that fields cannot be changed once they are initialized.
3. **Initialize fields using a constructor**  
    Set all values at the time of object creation.
4. **Do not provide setter methods**  
    Avoid methods that can modify the state of the object.
5. Return copies of mutable fields (deep copy)  
    If the class contains mutable objects, return a copy instead of the original reference.

## Syntax to Create an Immutable Class

Use the following syntax to create an immutable class by following the above mentioned rules:

[](https://www.tpointtech.com/how-to-create-immutable-class-in-java#)[](https://www.tpointtech.com/how-to-create-immutable-class-in-java#)[](https://www.tpointtech.com/how-to-create-immutable-class-in-java#)

1. final class ClassName {  
2.     private final dataType field1;  
3.     private final dataType field2;  

4.     public ClassName(dataType field1, dataType field2) {  
5.         this.field1 = field1;  
6.         this.field2 = field2;  
7.     }  

8.     public dataType getField1() {  
9.         return field1;  
10.     }  

11.     public dataType getField2() {  
12.         return field2;  
13.     }  
14. }  

## Example of an Immutable Class

The following example demonstrates how to create an immutable Student class:

[](https://www.tpointtech.com/how-to-create-immutable-class-in-java#)[](https://www.tpointtech.com/how-to-create-immutable-class-in-java#)[](https://www.tpointtech.com/how-to-create-immutable-class-in-java#)

1. final class Student {  
2.     private final int id;  
3.     private final String name;  
4.     private final String course;  

5.     public Student(int id, String name, String course) {  
6.         this.id = id;  
7.         this.name = name;  
8.         this.course = course;  
9.     }  

10.     public int getId() {  
11.         return id;  
12.     }  

13.     public String getName() {  
14.         return name;  
15.     }  

16.     public String getCourse() {  
17.         return course;  
18.     }  
19. }  

20. public class TestImmutable {  
21.     public static void main(String[] args) {  
22.         Student s = new Student(101, "Rahul", "Java");  
23.         System.out.println(s.getId() + " " + s.getName() + " " + s.getCourse());  
24.     }  
25. }  

**Output:**

101 Rahul Java

**Explanation:**

The **Student** class is declared as **final**, its fields are **private** and **final**, and no setter methods are provided. This ensures that once a Student object is created, its data cannot be modified, making the class immutable.

## Limitations of Immutable Classes

Although immutable classes provide many benefits, they also have some limitations:

- **Higher Memory Usage:** Every modification creates a new object that can increase memory consumption.
- **Performance Overhead:** Frequent object creation may affect performance in applications that require many changes.
- **Complex Design:** Creating immutable classes with mutable fields requires deep copying, which can make the code more complex.
- **Not Suitable for All Scenarios:** Immutable objects are not ideal when data needs to be updated frequently.

## Importance of Deep Copy in Immutable Classes

When an immutable class contains mutable objects (such as arrays, lists, or custom objects), it returns direct references that can break immutability. To prevent this, **deep copying** is used so that the internal state cannot be modified from outside the class.

### Syntax

It has the following syntax:

[](https://www.tpointtech.com/how-to-create-immutable-class-in-java#)[](https://www.tpointtech.com/how-to-create-immutable-class-in-java#)[](https://www.tpointtech.com/how-to-create-immutable-class-in-java#)

1. public returnType getField() {  
2.     return new returnType(originalField);  
3. }  

### Example: Immutable Class Using Deep Copy

The following example demonstrates how deep copy helps maintain immutability:

[](https://www.tpointtech.com/how-to-create-immutable-class-in-java#)[](https://www.tpointtech.com/how-to-create-immutable-class-in-java#)[](https://www.tpointtech.com/how-to-create-immutable-class-in-java#)

1. final class Student {  
2.     private final int id;  
3.     private final String name;  
4.     private final int[] marks;  

5.     public Student(int id, String name, int[] marks) {  
6.         this.id = id;  
7.         this.name = name;  
8.         this.marks = marks.clone(); // deep copy  
9.     }  

10.     public int getId() {  
11.         return id;  
12.     }  

13.     public String getName() {  
14.         return name;  
15.     }  

16.     public int[] getMarks() {  
17.         return marks.clone(); // deep copy  
18.     }  
19. }  

20. public class TestDeepCopy {  
21.     public static void main(String[] args) {  
22.         int[] marks = {80, 85, 90};  
23.         Student s = new Student(101, "Amit", marks);  

24.         marks[0] = 50; // modifying original array  
25.         System.out.println(s.getMarks()[0]); // remains unchanged  
26.     }  
27. }  

**Output:**

80

**Explanation:**

In this above example, even though the original array is modified, the internal state of the **Student** object remains unchanged because deep copies are used.