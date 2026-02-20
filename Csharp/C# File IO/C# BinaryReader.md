In the C# programming language, a BinaryReader is a class that is used to read binary data from a stream. It is found in the System.IO namespace. It also supports reading a string in a specific encoding. The BinaryReader class belongs to the System.IO namespace, and it is used to read primitive data types. The BinaryReader uses the UTF-8 encoding, which helps to read the data until we define another character encoding during the creation of its object.

![C# BinaryReader](https://images.tpointtech.com/cpp/images/c-sharp-binaryreader.png)

### Syntax:

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-binaryreader#)[](https://www.tpointtech.com/c-sharp-binaryreader#)[](https://www.tpointtech.com/c-sharp-binaryreader#)

1. BinaryReader reader = new BinaryReader(Stream input);  

Or with encoding:

[](https://www.tpointtech.com/c-sharp-binaryreader#)[](https://www.tpointtech.com/c-sharp-binaryreader#)[](https://www.tpointtech.com/c-sharp-binaryreader#)

1. BinaryReader reader = new BinaryReader(Stream input, Encoding encoding);  

In this syntax,

- **Stream input:** It represents the stream, such as a FileStream from which the binary data is to be read.
- **Encoding encoding:** It specifies the character encoding according to need.

### Simple C# BinaryReader Class Example

Let us take an example to illustrate the BinaryReader class in C#.

### Example

[](https://www.tpointtech.com/c-sharp-binaryreader#)[](https://www.tpointtech.com/c-sharp-binaryreader#)[](https://www.tpointtech.com/c-sharp-binaryreader#)

1. using System;  
2. using System.IO;  
3. class Tpoint  
4. {  
5.     static void Main()  
6.     {  
7.         string filePath = "example.bin";  
8.         using(BinaryWriter writer = new BinaryWriter(File.Open(filePath, FileMode.Create)))  
9.         {  
10.             writer.Write(555);           // Write an integer  
11.             writer.Write(45.67);         // Write a double  
12.             writer.Write("Hello, Welcome to Tpoint tech");    // Write a string  
13.         }  
14.         // Reading the data of BinaryReader  
15.         using (BinaryReader reader = new BinaryReader(File.Open(filePath, FileMode.Open)))  
16.         {  
17.             int intValue = reader.ReadInt32();  
18.             double doubleValue = reader.ReadDouble();  
19.             string stringValue = reader.ReadString();  
20.             Console.WriteLine("The integer value is " + intValue);  
21.             Console.WriteLine("The double value is " + doubleValue);  
22.             Console.WriteLine("The string value is " + stringValue);  
23.         }  
24.     }  
25. }  

**Output:**

The integer value is 555
The double value is 45.67
The string value is Hello, Welcome to Tpoint tech

**Explanation:**

In this example, we demonstrate the use of the BinaryReader classes in C#. First, we create a binary file named example.bin, which writes three types of data: integer, double, and string. After that, we use the BinaryReader class to read the data from the file. At last, we are using the Console.WriteLine() method to print the read data.

## Methods of the BinaryReader Class in C#

In [C#](https://www.tpointtech.com/c-sharp-tutorial), the BinaryReader Class has several functions, which are as follows.

|Method|Description|
|---|---|
|**Read()**|The Read() method is commonly utilized to read the characters from the current stream.|
|**ReadByte()**|The ReadByte() method is utilized to read the next byte from the latest position in the binary stream.|
|**ReadBoolean()**|The ReadBoolean() method is commonly utilized to read the Boolean value from the current position in the binary stream.|
|**ReadDouble()**|The ReadDouble() method is commonly utilized to read the floating point value from the current position in the binary stream.|
|**ReadString()**|The ReadStriing() method is utilized to read the string value from the current stream.|
|**ReadChar()**|The ReadChar() method is commonly utilized to extract data from a file.|
|**ReadChars(int count)**|It is used to read the specified number of characters from a stream or source.|
|**ReadInt32()**|It is commonly utilized to read the 4-byte signed integer from the existing stream and enhance the current position of the stream by four bytes.|
|**ReadInt16()**|It is commonly utilized to read the 2-byte signed integer from the current position of the stream.|
|**ReadDecimal()**|It is utilized to read the decimal value from the current position of the stream.|
|**Close()**|The Close() method is utilized to close the BinaryReader and the underlying stream.|

### C# Example to Read and Write Multiple Data Types Using BinaryReader and BinaryWriter

Let us take an example to define the methods of the BinaryReader class in C#.

### Example

[](https://www.tpointtech.com/c-sharp-binaryreader#)[](https://www.tpointtech.com/c-sharp-binaryreader#)[](https://www.tpointtech.com/c-sharp-binaryreader#)

1. using System;  
2. using System.IO;  
3. class Tpoint  
4. {  
5.     static void Main()  
6.     {  
7.         string filePath = "ex.bin";  
8.         using (BinaryWriter writer = new BinaryWriter(File.Open(filePath, FileMode.Create)))  
9.         {  
10.             writer.Write(125);  
11.             writer.Write(35.75);  
12.             writer.Write(true);                      
13.             writer.Write('M');                        
14.             writer.Write("Hello, Welcome to Tpoint Tech");     
15.         }  
16.         using (BinaryReader reader = new BinaryReader(File.Open(filePath, FileMode.Open)))  
17.         {  
18.             int n = reader.ReadInt32();           
19.             double p = reader.ReadDouble();         
20.             bool s = reader.ReadBoolean();  
21.             char g = reader.ReadChar();   
22.             string m = reader.ReadString();       
23.             Console.WriteLine("The integer value is " + n);  
24.             Console.WriteLine("The double value is " + p);  
25.             Console.WriteLine("The boolean value is " + s);  
26.             Console.WriteLine("TThe character value is " + g);  
27.             Console.WriteLine("The string value is " + m);  
28.         }  
29.     }  
30. }  

**Output:**

The integer value is 125
The double value is 35.75
The boolean value is True
The character value is M
The string value is Hello, Welcome to Tpoint Tech

**Explanation:**

In this example, we create a file named ex.bin using [BinaryWriter](https://www.tpointtech.com/c-sharp-binarywriter). The BinaryWriter class converts each value into its binary representation. The BinaryReader class reads the same file and retrieves the data in the same order. After that, we use the Console.WriteLine() method to print the retrieved values.

### C# BinaryReader() Function Example with ReadString() Method

Let us take an example to illustrate the ReadString() method in the BinaryReader class in C#.

### Example

[](https://www.tpointtech.com/c-sharp-binaryreader#)[](https://www.tpointtech.com/c-sharp-binaryreader#)[](https://www.tpointtech.com/c-sharp-binaryreader#)

1. using System;  
2. using System.IO;  
3. class Tpoint  
4. {  
5.     static void Main()  
6.     {  
7.         string path = "exp.bin";  
8.         // Writing data to a binary file  
9.         using (BinaryWriter writer = new BinaryWriter(File.Open(path, FileMode.Create)))  
10.         {  
11.             writer.Write("Welcome to Tpoint Tech");  
12.         }  
13.         // Reading data from the binary file  
14.         using (BinaryReader reader = new BinaryReader(File.Open(path, FileMode.Open)))  
15.         {  
16.             string mes = reader.ReadString();  
17.             Console.WriteLine("Message: " + mes);  
18.         }  
19.     }  
20. }  

**Output:**

Message: Welcome to Tpoint Tech

**Explanation:**

In the example, we have taken a class named Tpoint. In the main() method, we have created a binary file named exp.bin using the Binary class. After that, we use the BinaryReader class to read the same string from the file, and use the Console.WriteLine() function to display the result.

## Features of the BinaryReader Method in C#

Several features of the BinaryReader Method in C# sare as follows:

- It is commonly used to read primitive data types as binary values rather than text.
- It is very helpful to read the data in the same order in which it was written in BinaryWriter in C#.
- It uses IDisposable in C# programs, which enables the resources to be released automatically.
- It provides read characters with custom text encodings.
- It helps in error handling during the binary tasks in C#.

## Conclusion

In conclusion, a BinaryReader is a class that is used to read binary information from a stream. It also supports readinsg a string in a specific encoding. It provides several methods to read primitive data types, including integers, doubles, booleans, [strings](https://www.tpointtech.com/c-sharp-strings), and many others. It helps to read the code easily and safely from different sources.