StringReader class is used to read data written by the StringWriter class. It is subclass of TextReader class. It enables us to read a string synchronously or asynchronously. It provides constructors and methods to perform read operations.

### C# StringReader Signature

[](https://www.tpointtech.com/c-sharp-stringreader#)[](https://www.tpointtech.com/c-sharp-stringreader#)[](https://www.tpointtech.com/c-sharp-stringreader#)

1. [SerializableAttribute]  
2. [ComVisibleAttribute(true)]  
3. public class StringReader : TextReader  

### C# StringReader Constructors

StringReader has the following constructors.

|Constructors|Description|
|---|---|
|StringReader(String)|Initializes a new instance of the StringReader class that reads from the specified string.|

### C# StringReader Methods

Following are the methods of StringReader class.

|Method|Description|
|---|---|
|Close()|It is used to close the StringReader.|
|Dispose()|It is used to release all resources used by the TextReader object.|
|Equals(Object)|It determines whether the specified object is equal to the current object or not.|
|Finalize()|It allows an object to try to free resources and perform other cleanup operations.|
|GetHashCode()|It serves as the default hash function.|
|GetType()|It is used to get the type of the current instance.|
|Peek()|It is used to return the next available character but does not consume it.|
|Read()|It is used to read the next character from the input string.|
|ReadLine()|It is used to read a line of characters from the current string.|
|ReadLineAsync()|It is used to read a line of characters asynchronously from the current string.|
|ReadToEnd()|It is used to read all the characters from the current position to the end of the string.|
|ReadToEndAsync()|It is used to read all the characters from the current position to the end of the string asynchronously.|
|ToString()|It is used to return a string that represents the current object.|

---

### C# StringReader Example

In the following example, StringWriter class is used to write the string information and StringReader class is used to read the string, written by the StringWriter class.

[](https://www.tpointtech.com/c-sharp-stringreader#)[](https://www.tpointtech.com/c-sharp-stringreader#)[](https://www.tpointtech.com/c-sharp-stringreader#)

1. using System;  
2. using System.IO;  
3. namespace CSharpProgram  
4. {  
5.     class Program  
6.     {  
7.         static void Main(string[] args)  
8.         {  
9.             StringWriter str = new StringWriter();  
10.             str.WriteLine("Hello, this message is read by StringReader class");  
11.             str.Close();  
12.             // Creating StringReader instance and passing StringWriter  
13.             StringReader reader = new StringReader(str.ToString());  
14.             // Reading data  
15.             while (reader.Peek() > -1)  
16.             {  
17.                 Console.WriteLine(reader.ReadLine());  
18.             }  
19.         }  
20.     }  
21. }  

Output:

Hello, this message is read by StringReader class