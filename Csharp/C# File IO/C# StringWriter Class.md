This class is used to write and deal with string data rather than files. It is derived class of TextWriter class. The string data written by StringWriter class is stored into StringBuilder.

The purpose of this class is to manipulate string and save result into the StringBuilder.

### StringWriter Class Signature

[](https://www.tpointtech.com/c-sharp-stringwriter#)[](https://www.tpointtech.com/c-sharp-stringwriter#)[](https://www.tpointtech.com/c-sharp-stringwriter#)

1. [SerializableAttribute]  
2. [ComVisibleAttribute(true)]  
3. public class StringWriter : TextWriter  

### C# StringWriter Constructors

|Constructors|Description|
|---|---|
|StringWriter()|It is used to initialize a new instance of the StringWriter class.|
|StringWriter(IFormatProvider)|It is used to initialize a new instance of the StringWriter class with the specified format control.|
|StringWriter(StringBuilder)|It is used to initialize a new instance of the StringWriter class that writes to the specified StringBuilder.|
|StringWriter(StringBuilder,?IFormatProvider)|It is used to initialize a new instance of the StringWriter class that writes to the specified StringBuilder and has the specified format provider.|

### C# StringWriter Properties

|Property|Description|
|---|---|
|Encoding|It is used to get the Encoding in which the output is written.|
|FormatProvider|It is used to get an object that controls formatting.|
|NewLine|It is used to get or set the line terminator string used by the current **TextWriter.**|

### C# StringWriter Methods

|Methods|Description|
|---|---|
|Close()|It is used to close the current StringWriter and the underlying stream.|
|Dispose()|It is used to release all resources used by the TextWriter object.|
|Equals(Object)|It is used to determine whether the specified object is equal to the current object or not.|
|Finalize()|It allows an object to try to free resources and perform other cleanup operations.|
|GetHashCode()|It is used to serve as the default hash function.|
|GetStringBuilder()|It returns the underlying StringBuilder.|
|ToString()|It returns a string containing the characters written to the current StringWriter.|
|WriteAsync(String)|It is used to write a string to the current string asynchronously.|
|Write(Boolean)|It is used to write the text representation of a Boolean value to the string.|
|Write(String)|It is used to write a string to the current string.|
|WriteLine(String)|It is used to write a string followed by a line terminator to the string or stream.|
|WriteLineAsync(String)|Writes a string followed by a line terminator asynchronously to the current string.(Overrides TextWriter.WriteLineAsync(String).)|

---

### C# StringWriter Example

In the following program, we are using StringWriter class to write string information to the StringBuilder class. The StringReader class is used to read written information to the StringBuilder.

[](https://www.tpointtech.com/c-sharp-stringwriter#)[](https://www.tpointtech.com/c-sharp-stringwriter#)[](https://www.tpointtech.com/c-sharp-stringwriter#)

1. using System;  
2. using System.IO;  
3. using System.Text;  
4. namespace CSharpProgram  
5. {  
6.     class Program  
7.     {  
8.         static void Main(string[] args)  
9.         {  
10.             string text = "Hello, Welcome to the javatpoint \n" +  
11.                 "It is nice site. \n" +  
12.                 "It provides technical tutorials";  
13.             // Creating StringBuilder instance  
14.             StringBuilder sb = new StringBuilder();  
15.             // Passing StringBuilder instance into StringWriter  
16.             StringWriter writer = new StringWriter(sb);  
17.             // Writing data using StringWriter  
18.             writer.WriteLine(text);  
19.             writer.Flush();  
20.             // Closing writer connection  
21.             writer.Close();  
22.             // Creating StringReader instance and passing StringBuilder  
23.             StringReader reader = new StringReader(sb.ToString());  
24.             // Reading data  
25.             while (reader.Peek() > -1)  
26.             {  
27.                 Console.WriteLine(reader.ReadLine());  
28.             }  
29.         }  
30.     }  
31. }  

Output:

Hello, Welcome to the javatpoint
It is nice site.
It provides technical tutorials