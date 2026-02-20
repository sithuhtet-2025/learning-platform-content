In C#, serialization is the process of converting object into byte stream so that it can be saved to memory, file or database. The reverse process of serialization is called deserialization.

Serialization is internally used in remote applications.

![C# serialization](https://images.tpointtech.com/csharp/images/c-sharp-serialization.png)

## C# SerializableAttribute

To serialize the object, you need to apply _SerializableAttribute_ attribute to the type. If you don't apply _SerializableAttribute_ attribute to the type, _SerializationException_ exception is thrown at runtime.

## C# Serialization example

Let's see the simple example of serialization in C# where we are serializing the object of Student class. Here, we are going to use **BinaryFormatter.Serialize(stream, reference)** method to serialize the object.

[](https://www.tpointtech.com/c-sharp-serialization#)[](https://www.tpointtech.com/c-sharp-serialization#)[](https://www.tpointtech.com/c-sharp-serialization#)

1. using System;  
2. using System.IO;  
3. using System.Runtime.Serialization.Formatters.Binary;  
4. [Serializable]  
5. class Student  
6. {  
7.     int rollno;  
8.     string name;  
9.     public Student(int rollno, string name)  
10.     {  
11.         this.rollno = rollno;  
12.         this.name = name;  
13.     }  
14. }  
15. public class SerializeExample  
16. {  
17.     public static void Main(string[] args)  
18.     {  
19.         FileStream stream = new FileStream("e:\\sss.txt", FileMode.OpenOrCreate);  
20.         BinaryFormatter formatter=new BinaryFormatter();  

21.         Student s = new Student(101, "sonoo");  
22.         formatter.Serialize(stream, s);  

23.         stream.Close();  
24.     }  
25. }  

sss.txt:

JConsoleApplication1, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null Student rollnoname e sonoo

As you can see, the serialized data is stored in the file. To get the data, you need to perform deserialization.