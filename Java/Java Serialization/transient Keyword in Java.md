In Java, the transient keyword is a modifier used in serialization (the process of converting an object into a byte stream). In a class, if a field is marked as transient, it is excluded from this process. It means that the field's value will not be saved during object serialization; instead, during deserialization, it will be initialized to its default value (for example, null for objects and 0 for integers).

## Why use the transient keyword?

The transient keyword can be used with the data members of a class to avoid their serialization. For example, if a program accepts a user's login details and password, but we do not want to store the original password in the file. In such cases, we can use the transient keyword. When the JVM reads the transient keyword, it ignores the original value of the object and instead stores the default value of the object.

1. It prevents sensitive or non-essential data from being serialized.
2. Transient fields are reset to their default values during deserialization.

**Syntax:**

[](https://www.tpointtech.com/transient-keyword-in-java#)[](https://www.tpointtech.com/transient-keyword-in-java#)[](https://www.tpointtech.com/transient-keyword-in-java#)

1. private transient variableName;  

Or

[](https://www.tpointtech.com/transient-keyword-in-java#)[](https://www.tpointtech.com/transient-keyword-in-java#)[](https://www.tpointtech.com/transient-keyword-in-java#)

1. transient private variableName;  

Or

[](https://www.tpointtech.com/transient-keyword-in-java#)[](https://www.tpointtech.com/transient-keyword-in-java#)[](https://www.tpointtech.com/transient-keyword-in-java#)

1. transient datatype variableName;    

## When to use the transient keyword?

1. It can be used in cases where data members are derived from other data members within the same instance of the class.
2. It can be applied to data members that do not represent the state of the object.
3. The data members of a non-serialized object or class can utilize a transient modifier.

## Example of transient Keyword

In the following example, we have defined a class **Student** that has two data members**: name** and **age**. If we serialize the object, all the values will be serialized, but we do not want to serialize the **_age_**. So, we have declared the **age** data. When we deserialize the object, we get the default value for the transient variable. Note that the age field is excluded from serialization, so its value is reset during deserialization.

As we can see, the age of the student returns 0 because the value of age was not serialized.

### Example

[](https://www.tpointtech.com/transient-keyword-in-java#)[](https://www.tpointtech.com/transient-keyword-in-java#)[](https://www.tpointtech.com/transient-keyword-in-java#)

1. import java.io.*;  
2. class Student implements Serializable {  
3.     String name;  
4.     transient int age; // This field won't be serialized  
5.     Student(String name, int age) {  
6.         this.name = name;  
7.         this.age = age;  
8.     }  
9. }  
10. public class Main {  
11.     public static void main(String[] args) throws Exception {  
12.         Student student= new Student("Peter", 25);  
13.         // Serialize the object  
14.         FileOutputStream fileOut = new FileOutputStream("student.ser");  
15.         ObjectOutputStream out = new ObjectOutputStream(fileOut);  
16.         out.writeObject(student);  
17.         out.close();  
18.         fileOut.close();  
19.         // Deserialize the object  
20.         FileInputStream fileIn = new FileInputStream("student.ser");  
21.         ObjectInputStream in = new ObjectInputStream(fileIn);  
22.         Student deserializedStudent = (Student) in.readObject();  
23.         in.close();  
24.         fileIn.close();  
25.         // prints name and age to the console  
26.         System.out.println("Name: " + deserializedStudent.name); // Prints Peter  
27.         System.out.println("Age: " + deserializedStudent.age);   // Prints 0 (default value)  
28.     }  
29. }  

**Output:**

Name: Peter
Age: 0