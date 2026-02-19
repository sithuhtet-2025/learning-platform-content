In the C# programming language, the TextReader is a class that is found in the System.IO namespace. It defines a reader text that provides a way to read text or a sequential series of characters. The TextReader class is part of .NET. It is a base class for the [StreamReader](https://www.tpointtech.com/c-sharp-streamreader) and [StringReader](https://www.tpointtech.com/c-sharp-stringreader) classes. The C# StreamReader is commonly utilized to read characters from a stream. The C# StringReader is commonly utilized to read characters from a String. However, we can use both classes to read the text.

![C# TextReader](https://images.tpointtech.com/cpp/images/c-sharp-textreader.png)

### Syntax:

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-textreader#)[](https://www.tpointtech.com/c-sharp-textreader#)[](https://www.tpointtech.com/c-sharp-textreader#)

1. TextReader reader = new DerivedTextReader ();  

In this syntax,

- **TextReader:** It is used to represent an abstract base class in the System.IO namespace.
- **reader:** It is the variable name that will hold the reference to the TextReader Object.
- **new:** It is the keyword that creates an instance of the derived class.
- **DerivedTextReader():** It represents the constructor of a class that derives from TextReader.

### Simple C# TextReader Example

Let us take an example to illustrate the TextReader in C#.

### Example

[](https://www.tpointtech.com/c-sharp-textreader#)[](https://www.tpointtech.com/c-sharp-textreader#)[](https://www.tpointtech.com/c-sharp-textreader#)

1. using System;    
2. using System.IO;    
3. namespace TextReaderExample    
4. {    
5.     class Tpoint    
6.     {    
7.         static void Main(string[] args)    
8.         {    
9.             using (TextReader tr = File.OpenText("e:\\f.txt"))    
10.             {  
11.                 Console.WriteLine(tr.ReadToEnd());    
12.             }    
13.         }    
14.     }    
15. }    

**Output:**

Hello C#
C# File Handling by TpointTech.

**Explanation:**

In this example, we are using the TextReader class in C#. First, we use the File.OpenText() method to open a text file named f.txt, and the file is located at the specified path (f.txt). After that, we are using the ReadToEnd() method to read all the file contents and display the output using the Console.WriteLine() method.

### C# TextReader Example to Read One Line

Let us take an example to illustrate the TextReader class to read a single line from the file.

### Example

[](https://www.tpointtech.com/c-sharp-textreader#)[](https://www.tpointtech.com/c-sharp-textreader#)[](https://www.tpointtech.com/c-sharp-textreader#)

1. using System;  
2. using System.IO;  
3. namespace Tpoint  
4. {    
5.     class Program    
6.     {    
7.         static void Main(string[] args)    
8.         {    
9.             using (TextReader tr = File.OpenText("e:\\f.txt"))    
10.             {    
11.                 Console.WriteLine(tr.ReadLine());    
12.             }    
13.         }    
14.     }    
15. }    

**Output:**

Hello C#

**Explanation:**

In this example, we use the File.OpenText() method to open the file f.txt. The file is located at the given path (e:\\f.txt). Inside the using block, we have used the ReadLine() method to read the first line of the file content. In the end, we are using the Console.WriteLine() method to print the output.

## How to read a file using StreamReader in C#

In [C#](https://www.tpointtech.com/c-sharp-tutorial), the StreamReader class is commonly used to read text files. It provides a method to read data from files line by line. It makes the file handling simple and convenient.

Here, we will discuss how to read a file step by step in C#.

### 1) Create an Object of FileInfo

If we want to create an object of the FileInfo, we can use the following syntax:

[](https://www.tpointtech.com/c-sharp-textreader#)[](https://www.tpointtech.com/c-sharp-textreader#)[](https://www.tpointtech.com/c-sharp-textreader#)

1. FileInfo file = new FileInfo(@" D:Tpointfile.txt " );  

In this syntax,

- The FileInfo class is used to get information about a file and perform operations like create, open, delete, or move.
- An object of FileInfo is created for the path D:Tpointfile.txt.

### 2) Open the File for Reading

We can use the following statement to open the file for reading.

[](https://www.tpointtech.com/c-sharp-textreader#)[](https://www.tpointtech.com/c-sharp-textreader#)[](https://www.tpointtech.com/c-sharp-textreader#)

1. FileStream fs = file.Open(FileMode.OpenOrCreate, FileAccess.Read , FileShare.Read);  

In this syntax,

- **FileStream:** The FileStream is a class in the System.IO namespace. It is utilized to read or write files.
- **fs:** The fs is the object of type Filestream that will store the reference to the opened file stream.
- **Open ():** The Open() method of FileInfo is utilized to open an existing file or create a new file.
- **OpenOrCreate:** It is the parameter that defines how we can open or create a file.

### 3) Create a Stream Reader Object

If we want to create a stream reader object, we can use the following syntax:

[](https://www.tpointtech.com/c-sharp-textreader#)[](https://www.tpointtech.com/c-sharp-textreader#)[](https://www.tpointtech.com/c-sharp-textreader#)

1. StreamReader sr = new StreamReader ( fs );  

In this syntax,

- **StreamReader:** It is the class that is used to read characters or text.
- **sr:** It is an object of the StreamReader class.
- **new:** It is the keyword that creates an instance of the StreamReader class.
- **fs:** It is an argument that is passed to the StreamReader.

### 4) Read All Content from the File

If we want to read all the file content, we can utilize the following syntax:

[](https://www.tpointtech.com/c-sharp-textreader#)[](https://www.tpointtech.com/c-sharp-textreader#)[](https://www.tpointtech.com/c-sharp-textreader#)

1. string fileContent = sr.ReadToEnd();  

In this syntax,

- **fileContent:** The fileContent is a string variable that will store the data read from the file.

### 5) Close the StreamReader and FileStream

If we want to close the StreamReader and FileStream, we can use the following syntax:

[](https://www.tpointtech.com/c-sharp-textreader#)[](https://www.tpointtech.com/c-sharp-textreader#)[](https://www.tpointtech.com/c-sharp-textreader#)

1. sr.Close();  
2. fs.Close();  

In this syntax,

- **Close():** The sr.Close() method is used to close the StreamReader object.
- **Close():** The fs.Close() method is used to close the FileStream object.

## C# TextReader Methods

There are several commonly used methods of TextReader in C#. Some of them are as follows. 

|Methods|Description|
|---|---|
|**Close()**|The Close() method is commonly utilized to close the TextReader and release any resources associated with it.|
|**Dispose()**|The Dispose() method is used to clean up and releasing the resources utilized by the TextReader object.|
|**Dispose (Boolean)**|The Dispose (Boolean) method is used to free the unmanaged resources utilized by the TextReader, and it can also release the managed resources.|
|**Equals(Object)**|The Equals (Object) method checks whether the current object and the given object have the same value.|
|**GetType()**|It retrieves the type information of the current object.|
|**Read()**|The Read() method is commonly utilized to read the next character from the input stream.|
|**Peek()**|The Peek() method reads the next character from the text reader without changing the current position.|
|**Read(Span<Char>)**|This method is commonly used to read a sequence of characters from the current text reader and writes them into the specified character span.|
|**ReadBlockAsync(Char[], int32, int32)**|It performs an asynchronous operation to read a certain number of characters from the text reader.|
|**ReadAsync(Memory<Char>, CancellationToken)**|It is commonly utilized to read the characters from the current stream into a memory block.|
|**ReadLine()**|The ReadLine() method is commonly utilized to read one line of text from the text reader. It returns the data in a string format.|
|**ReadLineAsync(Cancellation Token)**|It is commonly utilized to read characters asynchronously from the existing position to the end of the text reader, and it returns in a string format.|
|**ReadLineAsync()**|This method is used to read characters asynchronously, and it returns the data in a string format.|
|**ReadToEnd()**|This method reads all remaining characters from the current position to the end of the text reader, and it returns the data in a string format.|
|**ReadToEndAsync()**|The ReadToEndAsync() method reads all the characters from the existing position to the end of the text reader asynchronously, and it returns the data in a string format.|
|**ToString ()**|This method is commonly utilized to return a string that shows the current object.|
|**Synchronized (TextReader)**|It provides a synchronized wrapper for the given TextReader to ensure thread safety.|
|**ReadToEndAsync (Cancellation Token)**|This method reads all the characters asynchronously from the existing position to the end of the text reader, and it returns in a string format.|
|**GetLifetimeService ()**|This method is used to retrieve the object that handles the lifetime of the instance.|
|**MemberwiseClone ()**|This method is commonly utilized to create a shallow copy of the current object.|

### C# TextReader Example with different Methods

Let us take an example to illustrate the different methods of TextReader in C#.

### Example

[](https://www.tpointtech.com/c-sharp-textreader#)[](https://www.tpointtech.com/c-sharp-textreader#)[](https://www.tpointtech.com/c-sharp-textreader#)

1. using System;  
2. using System.IO;  
3. class Tpt  
4. {  
5.     static void Main()  
6.     {  
7.         // file exists at the specified path  
8.         string filePath = @" E:\sample.txt ";  
9.         // Using TextReader   
10.         using (TextReader reader = new StreamReader( filePath) )  
11.         {  
12.             // Read the first line  
13.             string line = reader.ReadLine();  
14.             Console.WriteLine(" The First Line: " + line);  
15.             // Peek at the next character   
16.             int nextChar = reader.Peek();  
17.             Console.WriteLine("Next Character ASCII Code: " + nextChar );  
18.             // Read the rest of the file  
19.             string remainingText = reader.ReadToEnd ();  
20.             Console.WriteLine(" Remaining Text:\n" + remainingText );  
21.         }  
22.     }  
23. }  

**Output:**

The First Line: Hello C#
Next Character ASCII Code: 10
Remaining Text:
This is a TextReader example.
Enjoy learning!

**Explanation:**

In this example, we create the TextReader object to read the contents of a text file located at E:\sample.txt. The ReadLine() method reads the first line of the file. After that, we are using the Peek() method to examine the next character in the file. The ReadToEnd() method is used to read all the characters from the current position. Finally, we are using the Console.WriteLine() method to print the output.

## Features of the TextReader Class in C#

There are several features of the TextReader Class in C#. Some of them are as follows:

- In the C# programming language, the TextReader class is an abstract class that can provide a platform for reading-based data from text files or streams.
- It can provide several asynchronous methods, such as ReadAsync(), ReadLineAsync(), and ReadToEndAsync() methods that allow us to perform non-blocking I/O operations.
- We can use the TextReader class with several input resources, including files or strings, which makes it versatile and flexible for several text-reading operations.
- We can utilize the TextReader class to read the sequential streams of characters, which makes it suitable to handle text input instead of binary data.
- It can be defined under the System.IO namespace.

## Conclusion

In conclusion, a TextReader is a base class in the C# programming language. It is commonly used to read a character from text sources like files or strings. It provides various methods, such as Read(), ReadLine(), ReadToEnd(), and Peek() methods, etc. It helps to read the code easily and safely from different sources. It helps to read the text efficiently, safely, and in a flexible way from different sources.