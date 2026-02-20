In the C# programming language, the deserialization is the common way to convert the JSON data into .NET objects. It is the reverse process of serialization. It helps to retrieve structured data from files, APIs, or databases.

![C# deserialization](https://images.tpointtech.com/csharp/images/c-sharp-deserialization-1.png)

If we want to perform deserialization, we need to import the System.Text.Json or Newtonsoft.Json namespace in [C#](https://www.tpointtech.com/c-sharp-tutorial). If the data is being read from a file, we also use the System.IO namespace to handle the file operation.

### Syntax:

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-deserialization#)[](https://www.tpointtech.com/c-sharp-deserialization#)[](https://www.tpointtech.com/c-sharp-deserialization#)

1. ClassName objectName = JsonSerializer.Deserialize< ClassName >( jsonString );  

In this syntax,

- **ClassName:** It defines the name of the class for which the JSON data will be converted.
- **objectName:** It defines the name of the object that will store the deserialized data.
- **JsonSerializer:** It is a built-in class in the System.Text.Json namespace. It provides the method of serializing and deserializing JSON data.
- **Deserialize<ClassName>():** It is a generic method that converts the JSON string into an object of the specified class.
- **JsonString:** It is the input string that contains the JSON data to be deserialized.

### C# Simple Deserialization Example

Let us take an illustrate example to define the deserialization in C#.

### Example

[](https://www.tpointtech.com/c-sharp-deserialization#)[](https://www.tpointtech.com/c-sharp-deserialization#)[](https://www.tpointtech.com/c-sharp-deserialization#)

1. using System;  
2. using System.Text.Json;  
3. namespace Deserialization  
4. {  
5.     public class Student  
6.     {  
7.         public int Id { get; set; }  
8.         public string Name { get; set; }  
9.         public int Age { get; set; }  
10.     }  
11.     class Tpoint  
12.     {  
13.         static void Main( string[] args )  
14.         {  
15.             string jsonString = @"{  
16.                 ""Id"": 1,  
17.                 ""Name"": "" Peterson "",  
18.                 ""Age"": 25  
19.             }";  
20.             Student ss = JsonSerializer.Deserialize<Student>( jsonString );  
21.             Console.WriteLine( " The Student Details are " );  
22.             Console.WriteLine( " The id is " + ss.Id );  
23.             Console.WriteLine( " The name is " + ss.Name );  
24.             Console.WriteLine( " The age is " + ss.Age );  
25.         }  
26.     }  
27. }  

**Output:**

The Student Details are
The id is 1
The name is Peterson
The age is 25

**Explanation:**

In this example, we demonstrate the concept of deserialization in C#. First, we have defined a class with three properties named Id, Name, and Age. Inside the Main() function, the [JSON string](https://www.tpointtech.com/parsing-string-to-jsonnode-jackson) is passed to the JsonSerializer.Deserilizer <Student> (jsonString) method, which converts the JSON data into a Student object named ss. Finally, we use the Console.WriteLine () method to print the output.

## JSON

JSON stands for JavaScript Object Notation. It is a lightweight data interchange format that is easy to read and write for humans. JSON is a text format that is completely language-independent. It is widely used in web applications to send and receive data between a server and a client.

JSON has the following styles:

- Object
- Array
- String

Here, we will discuss these JSON concepts one by one.

### 1) Object (in JSON)

The object in JSON is a fundamental data structure that represents a collection of unordered key-value pairs. It is enclosed by curly braces {}. Each key is a string that is followed by a colon (:), and each key is associated with a value.

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-deserialization#)[](https://www.tpointtech.com/c-sharp-deserialization#)[](https://www.tpointtech.com/c-sharp-deserialization#)

1. {  
2.   "key1": "value1",  
3.   "key2": "value2"  
4. }  

### 2) Array (in JSON)

An array in JSON is an ordered collection of values. It is represented by square brackets [] that contains a separate list of elements.

**Syntax:**

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-deserialization#)[](https://www.tpointtech.com/c-sharp-deserialization#)[](https://www.tpointtech.com/c-sharp-deserialization#)

1. [  
2.   "value1",  
3.   "value2",  
4.   "value3"  
5. ]  

### 3) String (in JSON)

A string in JSON is a sequence of zero or more Unicode characters and is enclosed by double quotes. Strings are commonly used to represent text values, such as names, messages, or identifiers in JSON data.

**Syntax:**

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-deserialization#)[](https://www.tpointtech.com/c-sharp-deserialization#)[](https://www.tpointtech.com/c-sharp-deserialization#)

1. {  
2.   "Name": "Johnson"  
3. }  

## Error Handling in Deserialization

In the C# programming language, the Error-handling is important to create robust applications that process external data, such as JSON or XML. The best approach for error handling depends on the type of serialization or deserialization.

### C# Error-handling Example in Deserialization

Let us take an example to illustrate the error handling in deserialization in C#.

### Example

[](https://www.tpointtech.com/c-sharp-deserialization#)[](https://www.tpointtech.com/c-sharp-deserialization#)[](https://www.tpointtech.com/c-sharp-deserialization#)

1. using System;  
2. using System.Text.Json;  
3. public class Tpoint  
4. {  
5.     public int Id {get; set;}  
6.     public string Name {get; set;}  
7.     public int Age {get; set;}  
8. }  
9. class TPT  
10. {  
11.     static void Main()  
12.     {  
13.         string jsonString = @"{  
14.             ""Id"": 1,  
15.             ""Name"": ""Mehta"",  
16.             ""Age"": ""Twenty-Two""  
17.         }";  
18.         try  
19.         {  
20.             Tpoint m = JsonSerializer.Deserialize<Tpoint>(jsonString);  
21.             Console.WriteLine("Deserialization successful!");  
22.             Console.WriteLine($"The id is {m.Id}");  
23.             Console.WriteLine($"The name is {m.Name}");  
24.             Console.WriteLine($"The age is {m.Age}");  
25.         }  
26.         catch (JsonException mx)  
27.         {  
28.             // Handle errors  
29.             Console.WriteLine("Error during deserialization!");  
30.             Console.WriteLine("Message: " + mx.Message);  
31.         }  
32.     }  
33. }  

**Output:**

Error during deserialization!
Message: The JSON value could not be converted to System.Int32. Path: $.Age | LineNumber: 3 | BytePositionInLine: 31.

**Explanation:**

In this example, we create a class named Management. The management class defines the structure of the JSON object with three properties: id, Name, and Age. Inside the main method, the program attempts to deserialize a JSON string inside a try block. If the JSON matches the class structure, the program prints the deserialized values. The Age value is assigned to the integer data type, but defined as a string. So the program throws an exception and prints the error message.

## Nested JSON Object

In C#, a nested JSON is a JSON object that contains another JSON object. It allows us to represent hierarchical or structured data in a clear and organized way.

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-deserialization#)[](https://www.tpointtech.com/c-sharp-deserialization#)[](https://www.tpointtech.com/c-sharp-deserialization#)

1. {  
2.   "Key1": "Value1",  
3.   "Key2": {  
4.       "SubKey1": "SubValue1",  
5.       "SubKey2": "SubValue2"  
6.   }  
7. }  

In this syntax:

The Key1 holds a simple value, and the Key2 contains another JSON object with its own keys and values.

### Nested JSON Object Example in C#:

Let us take an illustrate example to demonstrate the use of nested JSON objects in C#.

### Example

[](https://www.tpointtech.com/c-sharp-deserialization#)[](https://www.tpointtech.com/c-sharp-deserialization#)[](https://www.tpointtech.com/c-sharp-deserialization#)

1. using System;  
2. using System.Text.Json;  
3. public class Address  
4. {  
5.     public string City {get; set;}  
6.     public string ZipCode {get; set;}  
7. }  
8. public class Teacher  
9. {  
10.     public int Id {get; set;}  
11.     public string Name {get; set;}  
12.     public Address Address {get; set;}   
13. }  
14. class Tpoint  
15. {  
16.     static void Main()  
17.     {  
18.         string jsonStr = @"{  
19.             ""Id"": 1,  
20.             ""Name"": ""Abhay"",  
21.             ""Address"": {  
22.                 ""City"": ""Delhi"",  
23.                 ""ZipCode"": ""110001""  
24.             }  
25.         }";  
26.         Teacher tt = JsonSerializer.Deserialize<Teacher>(jsonStr);  
27.         Console.WriteLine("The Id is " + tt.Id);  
28.         Console.WriteLine("The name is " + tt.Name);  
29.         Console.WriteLine("The city is " + tt.Address.City);  
30.         Console.WriteLine("The zipCode is " + tt.Address.ZipCode);  
31.     }  
32. }  

**Output:**

The Id is 1
The name is Abhay
The city is Delhi
The zipCode is 110001

**Explanation:**

In the above example, we create two classes: Address and Teacher. The Address class contains properties City and ZipCode, and the Teacher class includes Id, Name, and an Address object. Inside the Main method, we create a JSON string, jsonStr, that represents a JSON object. After the deserialization, we are using the Console.WriteLine() method to print the deserialized value.

## Advantages of Deserializations in C#

Let's discuss some common advantages of deserialization in C#:

- We can easily recreate complex objects by reconstructing objects from data formats such as JSON, XML, or binary data.
- It allows us to smooth data transfer between systems, API, or application. It converts the serialized data into .NET objects.
- It helps to identify errors such as missing data, incorrect formats, or unexpected errors in the JSON or XML data.
- It helps in improving the readability of the code and understanding, which makes it comparatively easier to maintain and modify.

## Conclusion:

In conclusion, deserialization is the common way to convert the JSON data into [.NET](https://www.tpointtech.com/net-framework) objects. It is the inverse operation of serialization. It allows us to reconstruct objects from structured data formats such as JSON, XML, or binary data. It allows developers to easily recreate complex objects.