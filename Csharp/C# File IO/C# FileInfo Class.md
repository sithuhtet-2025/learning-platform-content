The FileInfo class is used to deal with file and its operations in C#. It provides properties and methods that are used to create, delete and read file. It uses StreamWriter class to write data to the file. It is a part of System.IO namespace.

### C# FileInfo Class Signature

[](https://www.tpointtech.com/c-sharp-fileinfo#)[](https://www.tpointtech.com/c-sharp-fileinfo#)[](https://www.tpointtech.com/c-sharp-fileinfo#)

1. [SerializableAttribute]  
2. [ComVisibleAttribute(true)]  
3. public sealed class FileInfo : FileSystemInfo  

### C# FileInfo Constructors

The following table contains constructors for the FileInfo class.

|Constructor|Description|
|---|---|
|FileInfo(String)|It is used to initialize a new instance of the FileInfo class which acts as a wrapper for a file path.|

### C# FileInfo Properties

The following table contains properties of the FileInfo class.

|Properties|Description|
|---|---|
|Attributes|It is used to get or set the attributes for the current file or directory.|
|CreationTime|It is used to get or set the creation time of the current file or directory.|
|Directory|It is used to get an instance of the parent directory.|
|DirectoryName|It is used to get a string representing the directory's full path.|
|Exists|It is used to get a value indicating whether a file exists.|
|FullName|It is used to get the full path of the directory or file.|
|IsReadOnly|It is used to get or set a value that determines if the current file is read only.|
|LastAccessTime|It is used to get or set the time from current file or directory was last accessed.|
|Length|It is used to get the size in bytes of the current file.|
|Name|It is used to get the name of the file.|

### C# FileInfo Methods

The following table contains methods of the FileInfo class.

|Method|Description|
|---|---|
|AppendText()|It is used to create a StreamWriter that appends text to the file represented by this instance of the FileInfo.|
|CopyTo(String)|It is used to copy an existing file to a new file.|
|Create()|It is used to create a file.|
|CreateText()|It is used to create a StreamWriter that writes a new text file.|
|Decrypt()|It is used to decrypt a file that was encrypted by the current account using the Encrypt method.|
|Delete()|It is used to permanently delete a file.|
|Encrypt()|It is used to encrypt a file so that only the account used to encrypt the file can decrypt it.|
|GetAccessControl()|It is used to get a FileSecurity object that encapsulates the access control list (ACL) entries.|
|MoveTo(String)|It is used to move a specified file to a new specified location.|
|Open(FileMode)|It is used to open a file in the specified mode.|
|OpenRead()|It is used to create a read-only FileStream.|
|OpenText()|It is used to create a StreamReader with UTF8 encoding that reads from an existing text file.|
|OpenWrite()|It is used to create a write-only FileStream.|
|Refresh()|It is used to refresh the state of the object.|
|Replace(String,String)|It is used to replace the contents of a specified file with the file described by the current FileInfo object.|
|ToString()|It is used to return the path as a string.|

---

### C# FileInfo Example: Creating a File

[](https://www.tpointtech.com/c-sharp-fileinfo#)[](https://www.tpointtech.com/c-sharp-fileinfo#)[](https://www.tpointtech.com/c-sharp-fileinfo#)

1. using System;  
2. using System.IO;  
3. namespace CSharpProgram  
4. {  
5.     class Program  
6.     {  
7.         static void Main(string[] args)  
8.         {  
9.             try  
10.             {  
11.                 // Specifying file location  
12.                 string loc = "F:\\abc.txt";  
13.                 // Creating FileInfo instance  
14.                 FileInfo file = new FileInfo(loc);  
15.                 // Creating an empty file  
16.                 file.Create();  
17.                 Console.WriteLine("File is created Successfuly");  
18.             }catch(IOException e)  
19.             {  
20.                 Console.WriteLine("Something went wrong: "+e);  
21.             }  
22.         }  
23.     }  
24. }  

Output:

File is created Successfully

We can see inside the **F** drive a file **abc.txt** is created. A screenshot is given below.

![CSharp File info 1](https://images.tpointtech.com/csharp/images/c-sharp-file-info1.png)

### C# FileInfo Example: writing to the file

[](https://www.tpointtech.com/c-sharp-fileinfo#)[](https://www.tpointtech.com/c-sharp-fileinfo#)[](https://www.tpointtech.com/c-sharp-fileinfo#)

1. using System;  
2. using System.IO;  
3. namespace CSharpProgram  
4. {  
5.     class Program  
6.     {  
7.         static void Main(string[] args)  
8.         {  
9.             try  
10.             {  
11.                 // Specifying file location  
12.                 string loc = "F:\\abc.txt";  
13.                 // Creating FileInfo instance  
14.                 FileInfo file = new FileInfo(loc);  
15.                 // Creating an file instance to write  
16.                 StreamWriter sw = file.CreateText();  
17.                 // Writing to the file  
18.                 sw.WriteLine("This text is written to the file by using StreamWriter class.");  
19.                 sw.Close();  
20.             }catch(IOException e)  
21.             {  
22.                 Console.WriteLine("Something went wrong: "+e);  
23.             }  
24.         }  
25.     }  
26. }  

Output:

![CSharp File info 2](https://images.tpointtech.com/csharp/images/c-sharp-file-info2.png)

### C# FileInfo Example: Reading text from the file

[](https://www.tpointtech.com/c-sharp-fileinfo#)[](https://www.tpointtech.com/c-sharp-fileinfo#)[](https://www.tpointtech.com/c-sharp-fileinfo#)

1. using System;  
2. using System.IO;  
3. namespace CSharpProgram  
4. {  
5.     class Program  
6.     {  
7.         static void Main(string[] args)  
8.         {  
9.             try  
10.             {  
11.                 // Specifying file to read  
12.                 string loc = "F:\\abc.txt";  
13.                 // Creating FileInfo instance  
14.                 FileInfo file = new FileInfo(loc);  
15.                 // Opening file to read  
16.                 StreamReader sr = file.OpenText();  
17.                 string data = "";  
18.                 while ((data = sr.ReadLine()) != null)  
19.                 {  
20.                      Console.WriteLine(data);  
21.                 }  
22.             }  
23.             catch (IOException e)  
24.             {  
25.                 Console.WriteLine("Something went wrong: " + e);  
26.             }  
27.         }  
28.     }  
29. }  

Output:

![CSharp File info 3](https://images.tpointtech.com/csharp/images/c-sharp-file-info3.png)