
In the C# programming language, the FileStream class provides a stream for file operations. It can be used to perform synchronous and asynchronous read and write operations. We can easily read and write data into a file with the help of the FileStream class.

![C# FileStream](https://images.tpointtech.com/cpp/images/c-sharp-filestream.png)

In C#, a stream is a continuous flow of data that is transferred from a source to a destination, such as disks, memory, sockets, or other software. When we use the FileStream in C#, operations are done on a byte basis. We can use the StreamWriter and StreamReader classes to facilitate easier manipulation of text data.

### Syntax:

The simplest way to create a FileStream object is by using the following constructor overload.

[](https://www.tpointtech.com/c-sharp-filestream#)[](https://www.tpointtech.com/c-sharp-filestream#)[](https://www.tpointtech.com/c-sharp-filestream#)

1. Public FileStream(string path, FileMode mode, FileAccess access, FileShare share);  

This overload creates a new System.IO.FileStream instance with the given path, creation mode, read/write permission, and sharing permission.

- **Path:** It represents an absolute or relative path to the file that the present FileStream object will encapsulate.
- **mode:** It represents a variable that determines how to open or create the file.
- **access:** It represents a constant that is utilized to specify how the file needs to be accessed through the FileStream object.
- **Share:** It represents an integer constant that specifies how the file is shared between processes.

If we want to access the FileStream class, we have to import the System.IO namespace, and then declare a FileStream Object to open a file or create a new one.

[](https://www.tpointtech.com/c-sharp-filestream#)[](https://www.tpointtech.com/c-sharp-filestream#)[](https://www.tpointtech.com/c-sharp-filestream#)

1. FileStream <object_name> = new FileStream( <file_name>, <FileMode Enumerator>, <FileAccess Enumerator>, <FileShare Enumerator>);  

### FileMode:

In the C# filestream, the FileMode refers to how the operating system must open the file. It has the following members.

|Function|Description|
|---|---|
|**Append**|It is used to open the file if it exists or create a new file. If the file already exists, position the cursor at the end of the file.|
|**Create**|It is used to tell the operating system to make a new file. If the file already exists, the old file will be replaced.|
|**CreateNew**|It is used to open a new file, and if the file exists, it throws an IOException.|
|**Open**|It is used to open an existing file.|
|**Open or Create**|It is used to open an existing file. If it is not present, it will create a new file.|
|**Truncate**|It is used to open an existing file and truncate all the stored data, which helps to decrease the file size to 0.|

### FileAccess:

In the C# programming language, the FileAccess grants file permission to open in Read, ReadWrite, or Write mode.

|Function|Description|
|---|---|
|**Read**|It is used to provide read access to the file. The data can be read from it. It is also used to write for read/write access.|
|**Write**|It allows Write permission to the file, and the data to be written to it. It should be used with Read for read/write permission.|
|**ReadWrite**|It gives read and write access to the file, so the data can be read and written to it.|

### FileShare:

In the C# programming language, FileShare creates a file with the following share permission.

|Functions|Description|
|---|---|
|Delete|It is used to give permission for the future deletion of the file.|
|Inheritable|It is used to pass the inheritance to the child process.|
|None|It denies the sharing of the current files.|
|Read|It gives permission for future opening of the file to read.|
|ReadWrite|It gives permission for further opening of the file to read or write.|
|Write|It allows further opening of the file in write mode.|

### C# FileStream Example to write a single byte into a file

Let's see the simple example of the FileStream class to write a single byte of data into a file. Here, we are using the OpenOrCreate file mode that can be used for read and write operations.

### Example

[](https://www.tpointtech.com/c-sharp-filestream#)[](https://www.tpointtech.com/c-sharp-filestream#)[](https://www.tpointtech.com/c-sharp-filestream#)

1. using System;    
2. using System.IO;    
3. public class FileStreamExample    
4. {    
5.     public static void Main(string[] args)    
6.     {    
7.         FileStream f = new FileStream("e:\\b.txt", FileMode.OpenOrCreate);//creating file stream    
8.         f.WriteByte(65);  //writing byte into stream    
9.         f.Close();  //closing stream    
10.     }    
11. }    

**Output:**

A

**Explanation:**

In this example, we read or create a file called b.txt on the E drive by using FileStream. The WriteByte(65) writes one byte of value 65, which represents the character A in ASCII. If the file is already present, the new byte will be written at the beginning of the file. Finally, we call the Close() method to save changes and release the system resources associated with the file.

### C# FileStream Example to write multiple bytes into a file

Let's see another example to write multiple bytes of data into a file using a loop in C#.

### Example

[](https://www.tpointtech.com/c-sharp-filestream#)[](https://www.tpointtech.com/c-sharp-filestream#)[](https://www.tpointtech.com/c-sharp-filestream#)

1. using System;    
2. using System.IO;    
3. public class FileStreamExample    
4. {    
5.     public static void Main(string[] args)    
6.     {    
7.         FileStream f = new FileStream("e:\\b.txt", FileMode.OpenOrCreate);    
8.         for (int i = 65; i <= 90; i++)    
9.         {    
10.             f.WriteByte((byte)i);    
11.         }    
12.         f.Close();    
13.     }    
14. }    

**Output:**

ABCDEFGHIJKLMNOPQRSTUVWXYZ

**Explanation:**

In this example, we open or create a file b.txt in the E drive by using FileStream. Inside the for loop, it adds byte values from 65 to 90, which represent the uppercase characters A through Z in ASCII. They are written one by one into the file. Finally, the stream is closed to write the data and free resources.

### C# FileStream example to read all bytes from a file

Let's consider the example of the FileStream class that demonstrates how to read data from the file. Here, we will use the ReadByte() method of the FileStream class that returns a single byte. After that, we need to use a loop to read all the bytes.

### Example

[](https://www.tpointtech.com/c-sharp-filestream#)[](https://www.tpointtech.com/c-sharp-filestream#)[](https://www.tpointtech.com/c-sharp-filestream#)

1. using System;    
2. using System.IO;    
3. public class FileStreamExample    
4. {    
5.     public static void Main(string[] args)    
6.     {    
7.         FileStream f = new FileStream("e:\\b.txt", FileMode.OpenOrCreate);    
8.         int i = 0;    
9.         while ((i = f.ReadByte()) != -1)    
10.         {    
11.             Console.Write((char)i);    
12.         }    
13.         f.Close();    
14.     }    
15. }    

**Output:**

ABCDEFGHIJKLMNOPQRSTUVWXYZ

**Explanation:**

In this example, we open or create a b.txt file on the E drive with FileStream. It reads the file one byte at a time with ReadByte(), which returns -1 if the end of the file has been reached. It prints each byte as a character to the console, so the application writes the contents of the file. After that, it closes the stream to release resources.

## C# FileStream with StreamWriter and StreamReader

In C#, FileStream allows low-level byte access to files, while StreamWriter and StreamReader are higher-level classes that simplify writing to and reading from text.

- **StreamWriter:** It is commonly used to write characters or strings out to a file by internally converting them to bytes.
- **StreamReader:** It is commonly used to read text from a file by reversing the process by converting bytes back into characters.

They can both be used with a FileStream, which determines how the file is opened, created, and accessed.

### C# FileStream Example with StreamWriter and StreamReader

Let's consider an example to illustrate the FileStream with StreamWriter and StreamReader in C#.

### Example

[](https://www.tpointtech.com/c-sharp-filestream#)[](https://www.tpointtech.com/c-sharp-filestream#)[](https://www.tpointtech.com/c-sharp-filestream#)

1. using System;  
2. using System.IO;  
3. class FileStreamReaderExample  
4. {  
5.     static void Main()  
6.     {  
7.         string path = "File1.txt";  
8.         if (!File.Exists(path))  
9.         {  
10.             using (FileStream fs = new FileStream(path, FileMode.Create, FileAccess.Write))  
11.             using (StreamWriter writer = new StreamWriter(fs))  
12.             {  
13.                 writer.WriteLine("Hello, this is a default text in the file.");  
14.                 writer.WriteLine("You can add more content here.");  
15.             }  
16.         }  
17.         using (FileStream fs = new FileStream(path, FileMode.Open, FileAccess.Read))  
18.         using (StreamReader reader = new StreamReader(fs))  
19.         {  
20.             string content = reader.ReadToEnd();  
21.             Console.WriteLine("File Content:");  
22.             Console.WriteLine(content);  
23.         }  
24.     }  
25. }  

**Output:**

File Content:
Hello, this is a default text in the file.
You can add more content here.

**Explanation:**

In this example, we check if a file named File1.txt is present or not. If the file is not present, it creates the file and writes two lines of text to it using the StreamWriter. After that, the file is opened again using a FileStream, and all the file content is read through a StreamReader before being printed to the console. Finally, the program checks that the file exists, writes the default text if it does not, and then reads out and prints the file content.

## FileStream with Buffering in C#

In C# programming, the buffer is a temporary area that is very useful to hold the data while transferring between two locations, such as memory and the disk. The buffering in FileStream helps to reduce the I/O overhead by reducing the number of direct disk accesses. When we create a FileStream object, we can easily specify a buffer size that defines how much data is stored temporarily in memory before being written or after being read.

### C# FileStream Example using Buffering

Let's take an example to demonstrate the FileStream using buffering in C#.

### Example

[](https://www.tpointtech.com/c-sharp-filestream#)[](https://www.tpointtech.com/c-sharp-filestream#)[](https://www.tpointtech.com/c-sharp-filestream#)

1. using System;  
2. using System.IO;  
3. using System.Text;  
4. class Tpoint  
5. {  
6.     static void Show()     
7.     {  
8.         string path = "buffered2.txt";  
9.         string info = "BufferedStream makes file I/O more efficient.";  
10.         using (FileStream fs = new FileStream(path, FileMode.Create, FileAccess.Write))  
11.         using (BufferedStream bs = new BufferedStream(fs))  
12.         using (StreamWriter writer = new StreamWriter(bs))  
13.         {  
14.             writer.WriteLine(info);  
15.         }  
16.         using (FileStream fs = new FileStream(path, FileMode.Open, FileAccess.Read))  
17.         using (BufferedStream bs = new BufferedStream(fs))  
18.         using (StreamReader reader = new StreamReader(bs))  
19.         {  
20.             Console.WriteLine("File Contains: \n" + reader.ReadToEnd());  
21.         }  
22.     }  
23.     static void Main()  
24.     {  
25.         Show();     
26.     }  
27. }  

**Output:**

File Contains:
BufferedStream makes file I/O more efficient.

**Explanation:**

In this example, we write a file named buffered2.txt using the FileStream inside BufferedStream and StreamWriter. After that, we open the same file using BufferedStream and StreamReader to read out the information and print it on the console. Finally, we use the Show() method to perform all the file operations, which is invoked by the Main() function.

## Features of the FileStream in C#

There are several features of the FileStream in C#. Some of them are as follows:

- The FileStream in C# gives direct and byte-level access to files on the disk. It is suitable to manage both text and binary data.
- In C#, FileStream allows us to open or create a file using the FileMode and FileAccess enumerations.
- The FileStream provides support for both synchronous and asynchronous file operations, which allows us to choose between code simplicity and performance.
- We can use the FileStream to work directly with bytes or wrap it with several functions, such as StreamReader, StreamWriter, BinaryReader, or BinaryWriter. These functions help to handle text or binary data.
- It can work effectively across all platforms that are supported by the .NET Framework, which ensures portability of file-handling operations.

## Conclusion

In conclusion, the C# FileStream class is a simple and effective method for file manipulation. It enables us to read from, write to, and manipulate files effectively while giving control over file modes, access permissions, buffering, sharing options, and many others. It ensures high performance and reliability in file handling by supporting both synchronous and asynchronous operations. Overall, FileStream acts as the base for efficient and secure file management, working with text, binary data, and large data files.