
In the C# programming language, the TextWriter class is an abstract class that is provided by the System.IO namespace. It is used to write text or a sequential series of characters into a file, stream, or text-based destination. Since the TextWriter is an abstract class, we cannot create an instance directly. However, we may utilize its derived classes, like StreamWriter and StringWriter, to perform text writing operations.

![C# TextWriter](https://images.tpointtech.com/csharp/images/c-sharp-textwriter.png)

In C#, the TextWriter class gives a base for writing text in a buffered manner and supports writing data synchronously and asynchronously.

## Methods of TextWriter in C#

The core operations of the TextWriter class in C# include different overloads for writing characters, [strings](https://www.tpointtech.com/c-sharp-strings), and primitive types, as well as handling resource management and thread safety. There are several methods of TextWriter in C#. Some of them are as follows:

|Method|Description|
|---|---|
|**Write()**|It is used to release characters, strings, object representations, or primitive values. There are multiple overloads to support various types, such as char, string, char[], int, double, long, and others.|
|**WriteLine()**|It is used to write data followed by a line terminator. It is overloaded to support different data types, just like the Write() function.|
|**Flush()**|It is used to flush all buffers and write the buffered data to the underlying device or stream.|
|**Close()**|It shuts down the writer and releases the resources.|
|**Dispose()**|It frees all resources that are commonly used by the TextWriter.|
|**Synchronized(TextWriter)**|It returns a thread-safe wrapper around a given TextWriter instance.|
|**WriteAsync() and WriteLineAsync()**|These methods write asynchronous data or a line terminator. Several overloads are available for async operations with strings and characters.|

## Creating a TextWriter Object in C#

In the [C# programming language](https://www.tpointtech.com/c-sharp-tutorial), the TextWriter class is an abstract base class in the System.IO namespace that is used to write an ordered sequence of characters to a text stream, like a file or memory. Because it is [abstract](https://www.tpointtech.com/abstract-class-in-c-sharp), we cannot directly create an instance of TextWriter. We instantiate an object using one of its descendants, like StreamWriter, or by implementing factory methods like File.CreateText(), which provides a StreamWriter instance.

**Syntax**

[](https://www.tpointtech.com/c-sharp-textwriter#)[](https://www.tpointtech.com/c-sharp-textwriter#)[](https://www.tpointtech.com/c-sharp-textwriter#)

1. TextWriter = File.CreateText(filePath);  
2. Or  
3. TextWriter textWriter = new StreamWriter("filePath.txt");  

### C# TextWriter Example

Let's see the simple example of the TextWriter class to write two lines data.

### Example

[](https://www.tpointtech.com/c-sharp-textwriter#)[](https://www.tpointtech.com/c-sharp-textwriter#)[](https://www.tpointtech.com/c-sharp-textwriter#)

1. using System;    
2. using System.IO;    
3. namespace TextWriterExample    
4. {    
5.     class Program    
6.     {    
7.         static void Main(string[] args)    
8.         {    
9.             using (TextWriter writer = File.CreateText("tpoint.txt"))    
10.             {    
11.                 writer.WriteLine("Hello C#");    
12.                 writer.WriteLine("C# File Handling by TpointTech");    
13.             }    
14.             Console.WriteLine("Data written successfully...");    
15.         }    
16.     }    
17. }    

**Output:**

Data written successfully...
tpoint.txt:
Hello C#
C# File Handling by TpointTech

**Explanation:**

In this example, we demonstrate the use of TextWriter with File.CreateText() to write data into a file named tpoint.txt. First, it writes two lines of text into the file and then closes it automatically due to the using statement, which ensures proper resource management. Finally, it prints a success message on the console.

## Using TextWriter with StreamWriter

TextWriter is the abstract base class, while StreamWriter is a concrete implementation for writing text to streams or files in C#.

- **StreamWriter Inheritance of TextWriter:** In C#, the StreamWriter class inherits from the TextWriter abstract class. Therefore, it implements all of the members of TextWriter, including Write, WriteLine, Flush, and Close, along with additional functionality for writing characters to streams (e.g., files, memory streams.
- **Instantiation:** Although we cannot instantiate TextWriter directly, we can utilize it as a reference type and assign it an instance of a derived class, such as StreamWriter. It enables [polymorphism](https://www.tpointtech.com/c-sharp-polymorphism), which allows us to work with different TextWriter-derived classes interchangeably.

### C# TextWriter Example Using StreamWriter

Let us take an example to illustrate the TextWriter using the StreamWriter class in C#.

### Example

[](https://www.tpointtech.com/c-sharp-textwriter#)[](https://www.tpointtech.com/c-sharp-textwriter#)[](https://www.tpointtech.com/c-sharp-textwriter#)

1. using System;  
2. using System.IO;  
3. class Tpoint  
4. {  
5.     static void Main()  
6.     {  
7.         using (TextWriter writer = new StreamWriter("Content.txt"))  
8.         {  
9.             writer.WriteLine("Writing the content using the TextWriter with the help of StreamWriter");  
10.         }  
11.         Console.WriteLine("Data written successfully to File");  
12.     }  
13. }  

**Output:**

Data written successfully to File

**Explanation:**

In this example, we demonstrate how to use TextWriter with StreamWriter to write text into a file named Content.txt. After that, the using block ensures the file is closed automatically after writing, and a success message is displayed on the console.

## Classes Derived from TextWriter in C#

Similar to the StreamWriter, there are other classes that are inherited from the TextWriter class and implement the members of TextWriter. The following is the list of inherited classes with the help of which we can use TextWriter:

|Classes|Description|
|---|---|
|**IndentedTextWriter**|It is utilized to insert a tab string and to keep track of the current indentation level.|
|**StreamWriter**|It is commonly utilized to write characters to a stream using a specific encoding.|
|**StringWriter**|It is utilized to write data to a string. The data is held in an underlying StringBuilder.|
|**HttpWriter**|It offers an object of the TextWriter class that is accessible via the intrinsic HttpResponse object.|
|**HtmlTextWriter**|It is utilized to emit markup characters and text to an ASP.NET server control output stream.|

## Specifying Text Encoding

In C#, classes such as StreamWriter and StreamReader use UTF-8 encoding by default for text operations (such as reading and writing). However, we need a different encoding, like ASCII, UTF-16, or UTF-32, based on system requirements or compatibility with other programs.

### C# TextWriter Example to Specify Text Encoding

Let us take an example to illustrate how to specify text encoding using the StreamWriter and StreamReader in C#.

### Example

[](https://www.tpointtech.com/c-sharp-textwriter#)[](https://www.tpointtech.com/c-sharp-textwriter#)[](https://www.tpointtech.com/c-sharp-textwriter#)

1. using System;  
2. using System.IO;  
3. using System.Text;  
4. class Tpoint  
5. {  
6.     static void Main()  
7.     {  
8.         string path = "EncodedFile.txt";  
9.         string content = "Hello, नमस्";  
10.         using (StreamWriter writer = new StreamWriter(path, false, Encoding.Unicode))  
11.         {  
12.             writer.WriteLine(content);  
13.         }  
14.         Console.WriteLine("Data written successfully with UTF-16 encoding.");  
15.         using (StreamReader reader = new StreamReader(path, Encoding.Unicode))  
16.         {  
17.             string fileContent = reader.ReadToEnd();  
18.             Console.WriteLine("File Content:\n" + fileContent);  
19.         }  
20.     }  
21. }  

**Output:**

Data written successfully with UTF-16 encoding.
File Content:
Hello, नमस्

**Explanation:**

In this example, we have taken the string "Hello, नमस्" to a file called EncodedFile.txt using StreamWriter with UTF-16 encoding and read it back using StreamReader with the same encoding. After that, the written data is saved properly with Unicode support, and lastly, the program prints the confirmation message and the file content to the console.

## Asynchronous Writing

In C#, the TextWriter offers asynchronous methods like WriteAsync() and WriteLineAsync() to write single characters, arrays, strings, or formatted text to a stream or file. These methods return a Task, so we can use the await keyword to resume execution after the write is complete, which keeps the application responsive.

### C# Asynchronous Writing Example Using TextWriter

Let us take an example to illustrate asynchronous writing using the TextWriter class in C#.

### Example

[](https://www.tpointtech.com/c-sharp-textwriter#)[](https://www.tpointtech.com/c-sharp-textwriter#)[](https://www.tpointtech.com/c-sharp-textwriter#)

1. using System;  
2. using System.IO;  
3. using System.Threading.Tasks;  
4. class Tpoint  
5. {  
6.     static void Main()  
7.     {  
8.         RunAsync().GetAwaiter().GetResult();  
9.     }  
10.     static async Task RunAsync()  
11.     {  
12.         string path = "AsyncFile.txt";  
13.         string content = "This is written asynchronously using StreamWriter.";  
14.         using (StreamWriter writer = new StreamWriter(path, false))  
15.         {  
16.             await writer.WriteLineAsync(content);  
17.             await writer.WriteLineAsync("Asynchronous writing allows non-blocking I/O operations.");  
18.         }  
19.         Console.WriteLine("Data written successfully using asynchronous writing.");  
20.     }  
21. }  

**Output:**

Data written successfully using asynchronous writing.

**Explanation:**

In this example, we demonstrate asynchronous file writing in C# using the StreamWriter.WriteLineAsync() method. After that, the Main method invokes RunAsync() with GetAwaiter().GetResult() to execute the async operation in a synchronous entry point. Within RunAsync, a StreamWriter writes two lines of text asynchronously with WriteLineAsync, which provides non-blocking I/O, and upon completion, a success message is output to the console.

## Writing formatted data

Writing formatted data with C# TextWriter enables writing values with particular layouts, padding, alignment, and number or date formats with format strings and placeholders in methods, such as Write and WriteLine.

### C# TextWriter Example to Write Formatted Data

Let us take an example to illustrate how to write formatted data using the TextWriter class in C#.

### Example

[](https://www.tpointtech.com/c-sharp-textwriter#)[](https://www.tpointtech.com/c-sharp-textwriter#)[](https://www.tpointtech.com/c-sharp-textwriter#)

1. using System;  
2. using System.IO;  
3. class Ex1  
4. {  
5.     static void Main()  
6.     {  
7.         string path = "FormattedData.txt";  
8.         using (TextWriter writer = new StreamWriter(path))  
9.         {  
10.             writer.WriteLine("Name: {0}, Age: {1}, Score: {2}", "Jhonson", 25, 89.5);  
11.             writer.WriteLine("{0,-10} {1,5} {2,8}", "Name", "Age", "Score");  
12.             writer.WriteLine("{0,-10} {1,5} {2,8}", "Maddy", 27, 92.3);  
13.             writer.WriteLine("{0,-10} {1,5} {2,8}", "Peter", 22, 76.8);  
14.             string city = "New York";  
15.             int population = 8500000;  
16.             writer.WriteLine($"City: {city}, Population: {population:N0}");  
17.         }  
18.         Console.WriteLine("Formatted data written successfully.");  
19.     }  
20. }  

**Output:**

Formatted data written successfully.

**Explanation:**

In this example, we demonstrate how to use TextWriter with StreamWriter to write formatted data into a file. Here, we use a composite formatting with placeholders {0}, {1}, etc., tabular output with width specifiers for alignment, and string interpolation for printing city and population. After writing the data, it prints the successful result on the screen.

## Writing to Multiple Writers

In the C# programming language, we can create multiple targets by creating a custom class that is inherited from TextWriter and overrides other methods, such as the Write and WriteLine methods. Inside those overrides, we can forward the output to multiple TextWriter objects.

### C# Example for Writing to Multiple Writers using TextWriter

Let us take an example to illustrate how to write multiple writers using the TextWriter class in C#.

### Example

[](https://www.tpointtech.com/c-sharp-textwriter#)[](https://www.tpointtech.com/c-sharp-textwriter#)[](https://www.tpointtech.com/c-sharp-textwriter#)

1. using System;  
2. using System.IO;  
3. using System.Text;  
4. class MultiWriter : TextWriter  
5. {  
6.     private readonly TextWriter[] writers;  
7.     public MultiWriter(params TextWriter[] writers)  
8.     {  
9.         this.writers = writers;  
10.     }  
11.     public override Encoding Encoding => Encoding.UTF8;  
12.     public override void WriteLine(string val)  
13.     {  
14.         foreach (var writer in writers)  
15.         {  
16.             writer.WriteLine(val);  
17.         }  
18.     }  
19.     public override void Write(char val)  
20.     {  
21.         foreach (var writer in writers)  
22.         {  
23.             writer.Write(val);  
24.         }  
25.     }  
26. }  
27. class New  
28. {  
29.     static void Main()  
30.     {  
31.         using (var fileWriter = new StreamWriter("a.txt"))  
32.         using (var multiWriter = new MultiWriter(Console.Out, fileWriter))  
33.         {  
34.             multiWriter.WriteLine("Writing to both Console and File at the same time.");  
35.             multiWriter.WriteLine("Have a great Day.");  
36.         }  
37.         Console.WriteLine("Data written successfully to console and file.");  
38.     }  
39. }  

**Output:**

Writing to both Console and File at the same time.
Have a great Day.
Data written successfully to console and file.

**Explanation:**

In this example, we have taken a custom MultiWriter class that inherits from TextWriter and overrides the Write and WriteLine methods to forward output to multiple targets. By passing both Console.Out and a StreamWriter function for a file, the program writes the same content simultaneously to the console and the file.

## Features of the TextWriter Class in C#

There are several features of the TextWriter class in C#. Some of them are as follows:

- In C#, this class provides several methods to write data in string, character, and line formats.
- The TextWriter class provides built-in support for async and await operations.
- This function can be extended by custom classes for specific writing.
- It provides buffered writing to enhance performance.
- This function belongs to the System.IO.namespace.

## Conclusion

In conclusion, C# TextWriter is an abstract class that offers a generic means to write text data to various targets like files, streams, or strings. Because it cannot be instantiated directly, it functions through inherited classes like StreamWriter and StringWriter. With the TextWriter class, developers have a shared interface for text writing, which provides code reusability, purer design, and automatic resource deallocation when used along with the using statement. It is essential for processing text-based output in C#.