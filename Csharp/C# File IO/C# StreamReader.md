In the C# programming language, the StreamReader class is commonly used to read characters from a byte stream in a particular encoding. It is part of the System.IO namespace, which gives an easy way to read text files line by line, character by character, or the entire file content at once. Developers prefer to work with readable human text, such as strings, words, or lines.

StreamReader serves as a bridge that translates raw bytes from the file into meaningful text, which makes it easy to process in C#. It is also used to read a string from the stream. It inherits the [TextReader](https://www.tpointtech.com/c-sharp-textreader) class. It provides Read() and ReadLine() methods to read data from the stream.

### Syntax:

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-streamreader#)[](https://www.tpointtech.com/c-sharp-streamreader#)[](https://www.tpointtech.com/c-sharp-streamreader#)

1. using System.IO;  
2. StreamReader sr = new StreamReader("file_path");  

In this syntax,

- **file_path:** It is the file path to be read.

## Synchronous and Asynchronous Reads

StreamReader provides both synchronous and asynchronous operations, which helps to enhance performance and scalability in modern applications:

- **Read, ReadLine, ReadToEnd:** Standard synchronous reading for whole files, lines, or designated chunks.
- **ReadAsync, ReadLineAsync, ReadToEndAsync:** These non-blocking, asynchronous equivalents allow other operations to continue while large files are being read, which prevents the user interface or application from freezing. They are best suited for responsive GUI applications, server-side programming, or cloud functions handling large files because they make applications more responsive and scalable when processing extensive or slow I/O operations.

## Important StreamReader Methods

StreamReader offers a number of valuable methods for various reading purposes. Some of them are as follows:

- **Read():** It is used to read the following character from the input stream and reads it as an integer. It is suitable to read character by character.

**Example:**

[](https://www.tpointtech.com/c-sharp-streamreader#)[](https://www.tpointtech.com/c-sharp-streamreader#)[](https://www.tpointtech.com/c-sharp-streamreader#)

1. int character = reader.Read();  
2. Console.WriteLine((char)character);  

- **ReadLine():** It reads one line of text from the file. It also returns null at the end of the file.

**Example:**

[](https://www.tpointtech.com/c-sharp-streamreader#)[](https://www.tpointtech.com/c-sharp-streamreader#)[](https://www.tpointtech.com/c-sharp-streamreader#)

1. string line;  
2. while ((line = reader.ReadLine()) != null)  
3. {  
4.     Console.WriteLine(line);  
5. }  

- **ReadToEnd():** This function is used to read all the characters from the current point to the end of the stream. It is suitable for small or medium files, but not advisable for very large files because it loads everything into memory.
- **Peek():** It is used to try to return the next available character without moving the reader position. It is very useful to try to see what comes next before reading it.
- **BaseStream:** It offers access to the base stream so that complex scenarios where developers may need to directly manipulate the stream are possible.

## C# StreamReader example to read one line

Let us take the simple example of the StreamReader class that reads a single line of data from the file.

### Example

[](https://www.tpointtech.com/c-sharp-streamreader#)[](https://www.tpointtech.com/c-sharp-streamreader#)[](https://www.tpointtech.com/c-sharp-streamreader#)

1. using System;    
2. using System.IO;    
3. public class StreamReaderExample    
4. {    
5.     public static void Main(string[] args)    
6.     {    
7.         FileStream f = new FileStream("output.txt", FileMode.OpenOrCreate);    
8.         StreamReader s = new StreamReader(f);    

9.         string line=s.ReadLine();    
10.         Console.WriteLine(line);    

11.         s.Close();    
12.         f.Close();    
13.     }    
14. }   

**Output:**

Hello C#

**Explanation:**

In this example, we open or create a file named output.txt. After that, we use a StreamReader to read the first line from the file and display the result on the console. After reading, both the StreamReader and FileStream are closed to free system resources.

## C# StreamReader Example to read all lines

Let us take an example to illustrate the StreamReader function to read all lines in C#.

### Example

[](https://www.tpointtech.com/c-sharp-streamreader#)[](https://www.tpointtech.com/c-sharp-streamreader#)[](https://www.tpointtech.com/c-sharp-streamreader#)

1. using System;    
2. using System.IO;    
3. public class StreamReaderExample    
4. {    
5.     public static void Main(string[] args)    
6.     {    
7.         FileStream f = new FileStream("a.txt", FileMode.OpenOrCreate);    
8.         StreamReader s = new StreamReader(f);    

9.         string line = "";    
10.         while ((line = s.ReadLine()) != null)    
11.         {    
12.             Console.WriteLine(line);    
13.         }    
14.         s.Close();    
15.         f.Close();    
16.     }    
17. }    

**Output:**

Hello C#
This is file handling

**Explanation:**

In this example, we open or create a file named a.txt and read its contents line by line using a StreamReader function. Each line is printed on the console until the end of the file is reached, after which the StreamReader and FileStream are closed.

## StreamReader with Peek() method

In the C# programming language, the Peek() method of the StreamReader class allows us to look at the next available character in the stream without actually reading it. It returns the ASCII value of the next character or -1 if the end of the stream is reached. It is very helpful when we need to check the next character before deciding how to process it.

### C# StreamReader with peek() method example

Let us take an example to illustrate the streamReader with the peek() method in C#.

### Example

[](https://www.tpointtech.com/c-sharp-streamreader#)[](https://www.tpointtech.com/c-sharp-streamreader#)[](https://www.tpointtech.com/c-sharp-streamreader#)

1. using System;  
2. using System.IO;  
3. class PeekExample  
4. {  
5.     static void Main()  
6.     {  
7.         string path = "sample.txt";  
8.         File.WriteAllText(path, "Hello\nWorld");  

9.         using (StreamReader reader = new StreamReader(path))  
10.         {          
11.             int peekChar = reader.Peek();  
12.             Console.WriteLine("First character: " + (char)peekChar);  
13.             string line = reader.ReadLine();  
14.             Console.WriteLine("First line: " + line);  
15.             int nextChar = reader.Peek();  
16.             Console.WriteLine("Next character after first line: " + (char)nextChar);  
17.             string secondLine = reader.ReadLine();  
18.             Console.WriteLine("Second line: " + secondLine);  
19.         }  
20.     }  
21. }  

**Output:**

First character: H
First line: Hello
Next character after first line: W
Second line: World

**Explanation:**

This example shows the string "Hello\nWorld" in a file named sample.txt and reads it back with a StreamReader. The Peek() function is employed to see the next character without advancing the reader's position. It first peeks at the character H, then reads the first line, "Hello". After that, it peeks again and observes W, which is the beginning of the second line, and finally reads the second line "World". It shows how Peek() allows us to inspect the next character without reading it.

## StreamReader using FileInfo.OpenText

In the [C# programming language](https://www.tpointtech.com/c-sharp-tutorial), the FileInfo.OpenText() method is used for opening a text file as a read-only StreamReader. The file is opened in read mode with UTF-8 encoding automatically, and a StreamReader object is returned

### C# StreamReader with FileInfo.OpenText() method Example

Let us take an example to illustrate the StreamReader with FileInfo.OpenText() method in C#.

### Example

[](https://www.tpointtech.com/c-sharp-streamreader#)[](https://www.tpointtech.com/c-sharp-streamreader#)[](https://www.tpointtech.com/c-sharp-streamreader#)

1. using System;  
2. using System.IO;  
3. class Example  
4. {  
5.     static void Main()  
6.     {  
7.         string file = "example.txt";  
8.         File.WriteAllText(file, "Line 1: Welcome\nLine 2: C# StreamReader with FileInfo");  
9.         FileInfo fileInfo = new FileInfo(file);  
10.         using (StreamReader reader = fileInfo.OpenText())  
11.         {  
12.             string l;  
13.             while ((l = reader.ReadLine()) != null)  
14.             {  
15.                 Console.WriteLine(l);  
16.             }  
17.         }  
18.     }  
19. }  

**Output:**

Line 1: Welcome
Line 2: C# StreamReader with FileInfo

**Explanation:**

In this example, we initially create a text file example.txt and write two lines to it. After that, it creates a FileInfo instance for the file and uses OpenText() to obtain a StreamReader. By using this reader, it reads each line from the file in a loop and prints it to the console, which demonstrates how to use FileInfo.OpenText() to read text files line by line.

## Reading from a MemoryStream in C#

In the C# programming language, the MemoryStream is a stream that stores data in computer memory instead of disk. While FileStream (operating on physical files) involves the file system, MemoryStream operates entirely in memory. Therefore, it is very fast and good for temporary data storage, processing, or testing stream operations without accessing the file system.

### C# StreamReader from a MemoryStream in C#

Let us take an example to illustrate the StreamReader from a MemoryStream in C#.

### Example

[](https://www.tpointtech.com/c-sharp-streamreader#)[](https://www.tpointtech.com/c-sharp-streamreader#)[](https://www.tpointtech.com/c-sharp-streamreader#)

1. using System;  
2. using System.IO;  
3. using System.Text;  
4. class Example  
5. {  
6.     static void Main()  
7.     {  
8.         string text = "Hello from MemoryStream!\nThis is the next line.";  
9.         byte[] buffer = Encoding.UTF8.GetBytes(text);  
10.         using (MemoryStream ms = new MemoryStream(buffer))  
11.         using (StreamReader reader = new StreamReader(ms, Encoding.UTF8))  
12.         {  
13.             string line;  
14.             while ((line = reader.ReadLine()) != null)  
15.             {  
16.                 Console.WriteLine(line);  
17.             }  
18.         }  
19.     }  
20. }  

**Output:**

Hello from MemoryStream!
This is the next line.

**Explanation:**

In this example, the code encodes a string to a byte array with UTF-8, stores it in a MemoryStream, and then reads the content line by line from memory rather than a file using a StreamReader. After that, it prints each line to the console, which demonstrates how to read text directly from a stream-based in memory stream.

## Exception Handling using StreamReader

In the C# programming language, [exception handling](https://www.tpointtech.com/c-sharp-exception-handling) with the StreamReader function is essential to handle several errors, including IOException (unavailable stream) or OutOfMemoryException (insufficient memory). When we use the StreamReader function inside a using block, it ensures automatic disposal of the stream, which releases resources and avoids file locks or memory leaks.

### C# Exception Handling Example using StreamReader

Let us take an example to demonstrate the exception handling using StreamReader in C#.

### Example

[](https://www.tpointtech.com/c-sharp-streamreader#)[](https://www.tpointtech.com/c-sharp-streamreader#)[](https://www.tpointtech.com/c-sharp-streamreader#)

1. using System;  
2. using System.IO;  
3. class ExceptionExample  
4. {  
5.     static void Main()  
6.     {  
7.         string path = "text1.txt";   
8.         try  
9.         {  
10.             using (StreamReader reader = new StreamReader(path))  
11.             {  
12.                 string content = reader.ReadToEnd();  
13.                 Console.WriteLine(content);  
14.             }  
15.         }  
16.         catch (FileNotFoundException)  
17.         {  
18.             Console.WriteLine("Error: The file was not found.");  
19.         }  
20.         catch (IOException ex)  
21.         {  
22.             Console.WriteLine("I/O Error: " + ex.Message);  
23.         }  
24.         catch (Exception ex)  
25.         {  
26.             Console.WriteLine("Unexpected Error: " + ex.Message);  
27.         }  
28.         finally  
29.         {  
30.             Console.WriteLine("Operations on file are completed.");  
31.         }  
32.     }  
33. }  

**Output:**

Error: The file was not found.
Operations on file are completed.

**Explanation:**

In this example, we try to open and read the file text1.txt. If the file does not exist, a FileNotFoundException is caught and displays an error message. If another input/output issues are handled with IOException, and any unexpected errors are caught by a general Exception block. After that, the finally block ensures a completion message that is always printed.

## Features of C# StreamReader:

There are several features of StreamReader in C#. Some main features are as follows:

- It is used to read text files line by line.
- It is used to efficiently handle big files without reading the entire file into memory at one time.
- It is used to deal with various text encodings.
- We need asynchronous reading for improved performance in I/O-intensive applications.

## Conclusion

In conclusion, C# StreamReader is a powerful, flexible, and efficient way to read text streams. It simplifies by converting raw bytes to text, which allows developers to read files by line, character, or entire file. Its encoding, asynchronous, and large file support make it an essential part of System.IO.