**Serialization in Java** is a mechanism for writing an object's state into a byte stream. It is mainly used in Hibernate, RMI, JPA, EJB, and JMS technologies.

The reverse operation of serialization is called deserialization, where the byte stream is converted into an object. The serialization and deserialization process is platform-independent. It means we can serialize an object on one platform and deserialize it on a different platform.

For serializing the object, we call the **writeObject()** method of the ObjectOutputStream class, and for deserialization, we call the **readObject()** method of the ObjectInputStream class.

Java's serialization feature transforms an object into a stream of bytes, making it easier to store or send over a network. Many different technologies, including Hibernate, RMI (Remote Method Invocation), JPA (Java Persistence API), EJB (Enterprise JavaBeans), and JMS (Java Message Service), heavily utilize this method.

We must implement the Serializable interface for serializing the object.

## Advantages of Java Serialization

It is mainly used to travel object's state on the network (that is known as marshalling).

![java serialization](https://d2jdgazzki9vjm.cloudfront.net/core/images/java-serialization.png)

1. **Platform Independence:** There are no compatibility problems when transferring serialized objects between separate Java virtual machines (JVMs) running on different platforms. Java Serialization is an effective technique for inter-system communication because of its platform independence.
2. **Network Communication:** Java Serialization facilitates the transmission of object data over a network. This process, known as marshalling, allows objects to be serialized into a byte stream and sent across a network to be reconstructed on another machine. It is crucial for applications involving distributed systems, such as client-server architectures and web services.
3. **Object Persistence:** Serialization allows for indefinite storage of object state. Data can be kept between program executions by using serialized objects, which can be saved to a disc or a database and then retrieved.

## java.io.Serializable interface

**Serializable** is a marker interface (has no data member and method). It is used to "mark" Java classes so that the objects of these classes may get a certain capability. The **Cloneable** and **Remote** are also marker interfaces.

The **Serializable** interface must be implemented by the class whose object needs to be persisted.

The String class and all the wrapper classes implement the _java.io.Serializable_ interface by default.

Let's see the example given below:

**Student.java**

[](https://www.tpointtech.com/serialization-in-java#)[](https://www.tpointtech.com/serialization-in-java#)[](https://www.tpointtech.com/serialization-in-java#)

1. import java.io.Serializable;  
2. public class Student implements Serializable{  
3.  int id;  
4.  String name;  
5.  public Student(int id, String name) {  
6.   this.id = id;  
7.   this.name = name;  
8.  }  
9. }  

**Explanation**

This code defines a Java class named Student, implementing the Serializable interface. The Serializable interface serves as a marker, indicating that instances of the Student class can be serialized, meaning their state can be converted into a byte stream for storage or transmission.

The student class has two instance variables, id, and name, representing the student's ID and name, respectively. It also includes a constructor that initializes these variables with values passed as arguments. By implementing Serializable, instances of the Student class can be seamlessly serialized and deserialized, making them suitable for use in scenarios such as object persistence or network communication.

## ObjectOutputStream Class

The ObjectOutputStream class is used to write primitive data types, and Java objects to an OutputStream. Only objects that support the java.io.Serializable interface can be written to streams.

It acts as a link between byte streams and Java objects, enabling the serialization and writing of objects to a file or network connection, among other destinations. It is crucial to remember that only objects that are java.io are implementable.ObjectOutputStream can be used to write serializable interfaces to streams. The objects' ability to be serialized and have their state transformed into a byte stream is ensured by this interface.

### Constructors

|   |   |
|---|---|
|public ObjectOutputStream(OutputStream out) throws IOException|It creates an ObjectOutputStream that writes to the specified OutputStream.|
|public ObjectOutputStream(OutputStream out, int bufferSize) throws IOException|It creates an ObjectOutputStream that writes to the specified OutputStream with the given buffer size.|
|protected ObjectOutputStream() throws IOException, SecurityException|It is used for subclass construction. Creates an ObjectOutputStream instance.|
|protected ObjectOutputStream(OutputStream out) throws IOException|It is used for subclass construction. Creates an ObjectOutputStream that writes to the specified OutputStream.|

### Important Methods

|Method|Description|
|---|---|
|public final void writeObject(Object obj) throws IOException {}|It writes the specified object to the ObjectOutputStream.|
|public void flush() throws IOException {}|It flushes the current output stream.|
|public void close() throws IOException {}|It closes the current output stream.|

### ObjectInputStream class

An ObjectInputStream deserializes objects and primitive data written using an ObjectOutputStream.

**Constructor**

|   |   |
|---|---|
|1) public ObjectInputStream(InputStream in) throws IOException {}|It creates an ObjectInputStream that reads from the specified InputStream.|

**Important Methods**

|Method|Description|
|---|---|
|1) public final Object readObject() throws IOException, ClassNotFoundException{}|It reads an object from the input stream.|
|2) public void close() throws IOException {}|It closes ObjectInputStream.|

## Example of Java Serialization

In this example, we are going to serialize the object of **_Student_** class from above code. The writeObject() method of ObjectOutputStream class provides the functionality to serialize the object. We are saving the state of the object in the file named f.txt.

**Persist.java**

[](https://www.tpointtech.com/serialization-in-java#)[](https://www.tpointtech.com/serialization-in-java#)[](https://www.tpointtech.com/serialization-in-java#)

1. import java.io.*;    
2. class Persist{    
3.  public static void main(String args[]){    
4.   try{    
5.   //Creating the object    
6.   Student s1 =new Student(211,"ravi");    
7.   //Creating stream and writing the object    
8.   FileOutputStream fout=new FileOutputStream("f.txt");    
9.   ObjectOutputStream out=new ObjectOutputStream(fout);    
10.   out.writeObject(s1);    
11.   out.flush();    
12.   //closing the stream    
13.   out.close();    
14.   System.out.println("success");    
15.   }catch(Exception e){System.out.println(e);}    
16.  }    
17. }    

**Output:**

success

**Explanation**

The above Java code illustrates how to use the ObjectOutputStream class for object serialization. An instance of the Student class with the ID 211 and the name "ravi" is created within the main() method. Next, bytes are written to a file called "f.txt" using a FileOutputStream called fout that has been generated. The Student object s1 is then serialised and written to the file by creating an ObjectOutputStream with the name out and wrapping fout.

To relieve related system resources, the streams are terminated using close() after making sure that any buffered data has been sent to the file using flush(). The software prints "success" to the console if it is successful.

### Example of Java Deserialization

Deserialization is the process of reconstructing the object from the serialized state. It is the reverse operation of serialization. Let's see an example where we are reading the data from a deserialized object.

Deserialization is the process of reconstructing the object from the serialized state. It is the reverse operation of serialization. Let's see an example where we are reading the data from a deserialized object.

**Depersist.java**

[](https://www.tpointtech.com/serialization-in-java#)[](https://www.tpointtech.com/serialization-in-java#)[](https://www.tpointtech.com/serialization-in-java#)

1. import java.io.*;  
2. class Depersist{  
3.  public static void main(String args[]){  
4.   try{  
5.   //Creating stream to read the object  
6.   ObjectInputStream in=new ObjectInputStream(new FileInputStream("f.txt"));  
7.   Student s=(Student)in.readObject();  
8.   //printing the data of the serialized object  
9.   System.out.println(s.id+" "+s.name);  
10.   //closing the stream  
11.   in.close();  
12.   }catch(Exception e){System.out.println(e);}  
13.  }  
14. }  

**Output:**

211 ravi

**Explanation**

This Java code excerpt illustrates the use of the ObjectInputStream class for object deserialisation. A FileInputStream that reads data from the file "f.txt" is wrapped in an ObjectInputStream called in inside the main procedure. The serialized object that was previously written to the file is read using this stream. After that, the object is deserialised and cast to the Student class using the readObject() function.

The deserialised Student object's ID and name are then printed to the console along with other associated data. In order to free up related system resources, the stream is finally closed using the close() method. During deserialization, any exceptions are caught and their error messages are shown.

## Java Serialization with Inheritance (IS-A Relationship)

If a class implements **Serializable interface,** then all its sub classes will also be serializable. Let's see the example given below:

**SerializeISA.java**

[](https://www.tpointtech.com/serialization-in-java#)[](https://www.tpointtech.com/serialization-in-java#)[](https://www.tpointtech.com/serialization-in-java#)

1. import java.io.Serializable;    
2. class Person implements Serializable{    
3.  int id;    
4.  String name;    
5.  Person(int id, String name) {    
6.   this.id = id;    
7.   this.name = name;    
8.  }    
9. }    
10. class Student extends Person{    
11.  String course;    
12.  int fee;    
13.  public Student(int id, String name, String course, int fee) {    
14.   super(id,name);    
15.   this.course=course;    
16.   this.fee=fee;    
17.  }    
18. }    
19. public class SerializeISA  
20. {    
21.  public static void main(String args[])  
22.  {    
23.     try{    
24.   //Creating the object    
25.   Student s1 =new Student(211,"ravi","Engineering",50000);    
26.   //Creating stream and writing the object    
27.   FileOutputStream fout=new FileOutputStream("f.txt");    
28.   ObjectOutputStream out=new ObjectOutputStream(fout);    
29.   out.writeObject(s1);    
30.   out.flush();    
31.   //closing the stream    
32.   out.close();    
33.   System.out.println("success");    
34.   }catch(Exception e){System.out.println(e);}    
35.   try{    
36.   //Creating stream to read the object    
37.   ObjectInputStream in=new ObjectInputStream(new FileInputStream("f.txt"));    
38.   Student s=(Student)in.readObject();    
39.   //printing the data of the serialized object    
40.   System.out.println(s.id+" "+s.name+" "+s.course+" "+s.fee);    
41.   //closing the stream    
42.   in.close();    
43.   }catch(Exception e){System.out.println(e);}    
44.  }    
45. }  

**Output:**

success
211 ravi Engineering 50000

**Explanation**

The provided Java code showcases object serialization and deserialization, incorporating inheritance. In the code, the Person class serves as the superclass, defining basic attributes such as id and name, and implements the Serializable interface. The Student class, extending Person, adds specific attributes like course and fee, with a constructor initializing all properties, including inherited ones.

Within the SerializeISA class, serialization is demonstrated by creating a Student object (s1), writing it to a file named "f.txt" using an ObjectOutputStream, and then flushing and closing the stream. Deserialization occurs subsequently, reading the serialized object from "f.txt" via an ObjectInputStream, and printing its attributes to the console. Exception handling is implemented to manage potential errors during file operations or object manipulation.

## Java Serialization with Aggregation (HAS-A Relationship)

If a class has a reference to another class, all the references must be Serializable otherwise serialization process will not be performed. In such case, _NotSerializableException_ is thrown at runtime.

**Address.java**

[](https://www.tpointtech.com/serialization-in-java#)[](https://www.tpointtech.com/serialization-in-java#)[](https://www.tpointtech.com/serialization-in-java#)

1. class Address{    
2.  String addressLine,city,state;    
3.  public Address(String addressLine, String city, String state) {    
4.   this.addressLine=addressLine;    
5.   this.city=city;    
6.   this.state=state;    
7.  }    
8. }    

**Student.java**

[](https://www.tpointtech.com/serialization-in-java#)[](https://www.tpointtech.com/serialization-in-java#)[](https://www.tpointtech.com/serialization-in-java#)

1. import java.io.Serializable;  
2. public class Student implements Serializable{  
3.  int id;  
4.  String name;  
5.  Address address;//HAS-A  
6.  public Student(int id, String name) {  
7.   this.id = id;  
8.   this.name = name;  
9.  }  
10. }  

Since Address is not Serializable, you cannot serialize the instance of the Student class.

#### Note: All the objects within an object must be Serializable.

**Explanation**

Address and Student are the two classes in the code that is provided. Initialized by its constructor, the Address class has addressLine, city, and state information about an address. The Student class creates a HAS-A relationship by representing a student with attributes like name and id and by providing a reference to an Address object.

The class implements the Serializable interface in order to allow Student instances to be serialized. Nevertheless, there is no Serializable implementation in the Address class, which could cause problems with serialization. In order to fix this, the Address class should additionally implement Serializable, which will guarantee that Student objects with Address references are serialized seamlessly.

## Java Serialization with the Static Data Member

If a class has any static data members, they will not be serialized.

In other words, static variables are not serialized when a class is serialized; only its instance variables are. Static variables are not part of the object's state and are not serialized with the object because they belong to the class itself and not to any particular instance of the class.

As a result, rather than initializing from the serialized stream, when an object is deserialized, its static variables will be initialized using either their default values or the values they were initialized to when the class was loaded into memory. This behaviour is intended to preserve consistency and prevent possible problems arising from the shared nature of static variables among all instances within a class.

**Employee.java**

[](https://www.tpointtech.com/serialization-in-java#)[](https://www.tpointtech.com/serialization-in-java#)[](https://www.tpointtech.com/serialization-in-java#)

1. class Employee implements Serializable{  
2.  int id;  
3.  String name;  
4.  static String company="SSS IT Pvt Ltd";//it won't be serialized  
5.  public Student(int id, String name) {  
6.   this.id = id;  
7.   this.name = name;  
8.  }  
9. }  

**Explanation**

In the provided Employee class, there are three members: id, name, and company. The id and name fields represent instance-specific data for each employee and will be serialized when an Employee object is serialized. However, the company field is declared as static, making it a class-level variable shared among all instances of the Employee class. Static variables are not serialized because they are not part of the object's state; they belong to the class definition itself.

During the serialization process, only instance variables are serialized, while static variables are ignored. Therefore, when an Employee object is serialized and then deserialized, the id and name fields will be restored to their previous values, but the company field will retain its value from the class definition, not from the serialized stream. This behavior ensures that static variables maintain their consistency across all instances and are not affected by object serialization.

## Java Serialization with Array or Collection

**Rule:** In an array or collection, all the objects must be serializable. If any object is not serializable, serialization will fail.

When working with arrays or collections in Java serialization, it's crucial to make sure that every object inside of them can be serialized. It implies that every object in an array or collection of objects, such as an ArrayList, needs to implement the Serializable interface.

An attempt to serialize an array or collection will fail and usually throw a **NotSerializableException** if any of the objects in the array or collection are not serializable. It is due to the fact that serialization is a recursive operation, meaning that each object in an array or collection that is serialized likewise gets serialized.

To avoid serialization failures when dealing with arrays or collections, ensure that all objects stored within them are serializable. If a non-serializable object must be stored, consider alternatives such as transient fields or custom serialization methods to handle its serialization and deserialization. Additionally, always handle serialization exceptions gracefully to provide appropriate error handling and feedback to the user.

## Externalizable in Java

The Externalizable interface provides the facility of writing an object's state into a compressed byte stream. It is not a marker interface.

When a class implements the Externalizable interface, it must provide implementations for two methods: writeExternal() and readExternal(). These methods are invoked by the serialization mechanism to write the object's state to an ObjectOutput stream and to read the object's state from an ObjectInput stream, respectively.

The Externalizable interface provides two methods:

- **public void writeExternal(ObjectOutput out) throws IOException**
- **public void readExternal(ObjectInput in) throws IOException**

**1. writeExternal(ObjectOutput out):** This method is called during serialization and is responsible for writing the object's state to the specified ObjectOutput stream. Developers can customize the serialization process by writing specific fields or data to the stream in any desired format. It can be used to optimize serialization by only writing essential data or by compressing the output, as mentioned in your explanation.

**2. readExternal(ObjectInput in):** This method is called during deserialization and is responsible for reconstructing the object's state from the specified ObjectInput stream. Developers must read the data from the stream in the same order and format as it was written during serialization. It allows for custom deserialization logic, such as handling backward compatibility or performing additional validation checks on the input data.

## Java transient Keyword

If we do not want to serialize any data member of a class, we can mark it as transient.

**Employee.java**

[](https://www.tpointtech.com/serialization-in-java#)[](https://www.tpointtech.com/serialization-in-java#)[](https://www.tpointtech.com/serialization-in-java#)

1. class Employee implements Serializable{  
2.  transient int id;  
3.  String name;  
4.  public Student(int id, String name) {  
5.   this.id = id;  
6.   this.name = name;  
7.  }  
8. }  

Now, id will not be serialized, so when you deserialize the object after serialization, you will not get the value of id. It will return default value always. In such case, it will return 0 because the data type of id is an integer.

Visit next page for more details.

## SerialVersionUID

The serialization process at runtime associates an id with each Serializable class which is known as SerialVersionUID. It is used to verify the sender and receiver of the serialized object. The sender and receiver must be the same. To verify it, SerialVersionUID is used. The sender and receiver must have the same SerialVersionUID, otherwise, **InvalidClassException** will be thrown when we deserialize the object. We can also declare our own SerialVersionUID in the Serializable class. To do so, we need to create a field SerialVersionUID and assign a value to it. It must be of the long type with static and final. It is suggested to declare the serialVersionUID field in the class explicitly and have it private also.

The deserialisation operation goes without a hitch if the serialVersionUID values match. An InvalidClassException is raised, halting the object's deserialisation, if they do not match, suggesting a possible discrepancy in the class structure between the sender and the recipient. This method guards against unexpected behaviour brought on by mismatched class versions and aids in maintaining data integrity.

It is recommended to define a static final serialVersionUID field directly in Serializable classes, even though Java automatically produces a serialVersionUID for Serializable classes based on different variables like class structure, field types, and method signatures. Developers can guarantee constant serialization behaviour even in cases when class signatures change-for example, when new fields are added or removed-by explicitly defining the serialVersionUID.

For example:

[](https://www.tpointtech.com/serialization-in-java#)[](https://www.tpointtech.com/serialization-in-java#)[](https://www.tpointtech.com/serialization-in-java#)

1. private static final long serialVersionUID=1L;  

Now, the Serializable class will look like this:

**Employee.java**

[](https://www.tpointtech.com/serialization-in-java#)[](https://www.tpointtech.com/serialization-in-java#)[](https://www.tpointtech.com/serialization-in-java#)

1. import java.io.Serializable;    
2. class Employee implements Serializable{    
3.  private static final long serialVersionUID=1L;    
4.  int id;    
5.  String name;    
6.  public Student(int id, String name) {    
7.   this.id = id;    
8.   this.name = name;    
9.  }    
10. }    

**Explanation**

It is indicated that instances of this class can be serialized by the fact that the supplied Employee class implements the Serializable interface. A static final variable called serialVersionUID is declared within the class and acts as a version control mechanism for serialization.

This field makes sure that the class's serialized form is consistent between versions. The developer can better regulate versioning and retain control over the serialization process by explicitly setting a value (in this case, 1L) for serialVersionUID.

Two instance variables, name and id, which stand for the employee's name and identification number, respectively, are present in the Employee class. When an Employee object is serialized, these variables will also be serialized with the object's state.