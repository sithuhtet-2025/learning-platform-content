DirectoryInfo class is a part of System.IO namespace. It is used to create, delete and move directory. It provides methods to perform operations related to directory and subdirectory. It is a sealed class so, we cannot inherit it.

The DirectoryInfo class provides constructors, methods and properties that are listed below.

### C# DirectoryInfo Syntax

[](https://www.tpointtech.com/c-sharp-directoryinfo#)[](https://www.tpointtech.com/c-sharp-directoryinfo#)[](https://www.tpointtech.com/c-sharp-directoryinfo#)

1. [SerializableAttribute]  
2. [ComVisibleAttribute(true)]  
3. public sealed class DirectoryInfo : FileSystemInfo  

### C# DirectoryInfo Constructors

The following table contains the constructors for the DirectoryInfo class.

|Constructor|Description|
|---|---|
|DirectoryInfo(String)|It is used to initialize a new instance of the DirectoryInfo class on the specified path.|

### C# DirectoryInfo Properties

The following table contains the properties of the DirectoryInfo class.

|Property|Description|
|---|---|
|Attributes|It is used to get or set the attributes for the current file or directory.|
|CreationTime|It is used to get or set the creation time of the current file or directory.|
|CreationTimeUtc|It is used to get or set creation time, in coordinated universal time (UTC).|
|Exists|It is used to get a value indicating whether the directory exists.|
|Extension|It is used to get the string representing the extension part of the file.|
|FullName|It is used to get the full path of the directory.|
|LastAccessTime|It is used to get or set the time the current file or directory was last accessed.|
|LastAccessTimeUtc|It is used to get or set the time, in coordinated universal time (UTC) that the current file or directory was last accessed.|
|LastWriteTime|It is used to get or set the time when the current file or directory was last written.|
|LastWriteTimeUtc|It is used to get or set the time, in coordinated universal time (UTC), when the current file or directory was last written.|
|Name|It is used to get the name of this DirectoryInfo instance.|
|Parent|It is used to get the parent directory of a specified subdirectory.|
|Root|It is used to get the root portion of the directory.|

### C# DirectoryInfo Methods

The following table contains the methods of the DirectoryInfo class.

|Method|Description|
|---|---|
|Create()|It is used to create a directory.|
|Create(DirectorySecurity)|It is used to create a directory using a DirectorySecurity object.|
|CreateObjRef(Type)|It is used to create an object that contains all the relevant information required to generate a proxy used to communicate with a remote object.|
|CreateSubdirectory(String)|It is used to create a subdirectory or subdirectories on the specified path.|
|CreateSubdirectory(String,DirectorySecurity)|It is used to create a subdirectory or subdirectories on the specified path with the specified security.|
|Delete()|It is used to delete this DirectoryInfo if it is empty.|
|Delete(Boolean)|It is used to delete this instance of a DirectoryInfo, specifying whether to delete subdirectories and files.|
|EnumerateDirectories()|It returns an enumerable collection of directory information in the current directory.|
|EnumerateFiles()|It returns an enumerable collection of file information in the current directory.|
|GetAccessControl()|It is used to get a DirectorySecurity object that encapsulates the access control list (ACL) entries for the directory.|
|GetDirectories()|It returns the subdirectories of the current directory.|
|GetFiles()|It returns a file list from the current directory.|
|GetType()|It is used to get the Type of the current instance.|
|MoveTo(String)|It is used to move a DirectoryInfo instance and its contents to a new path.|
|Refresh()|It is used to refresh the state of the object.|
|SetAccessControl(DirectorySecurity)|It is used to set access control list (ACL) entries described by a DirectorySecurity object.|
|ToString()|It returns the original path that was passed by the user.|

---

### C# DirectoryInfo Example

In the following example, we are creating a **javatpoint** directory by specifying the directory path.

[](https://www.tpointtech.com/c-sharp-directoryinfo#)[](https://www.tpointtech.com/c-sharp-directoryinfo#)[](https://www.tpointtech.com/c-sharp-directoryinfo#)

1. using System;  
2. using System.IO;  
3. namespace CSharpProgram  
4. {  
5.     class Program  
6.     {  
7.         static void Main(string[] args)  
8.         {  
9.             // Provide directory name with complete location.  
10.             DirectoryInfo directory = new DirectoryInfo(@"F:\javatpoint");  
11.             try  
12.             {  
13.                 // Check, directory exist or not.  
14.                 if (directory.Exists)  
15.                 {  
16.                     Console.WriteLine("Directory already exist.");  
17.                     return;  
18.                 }  
19.                 // Creating a new directory.  
20.                 directory.Create();  
21.                 Console.WriteLine("The directory is created successfully.");  
22.             }  
23.             catch (Exception e)  
24.             {  
25.                 Console.WriteLine("Directory not created: {0}", e.ToString());  
26.             }  
27.         }  
28.     }  
29. }  

Output:

The directory is created successfully.

In below screenshot, we can see that a directory is created.

![CSharp Directory info 1](https://images.tpointtech.com/csharp/images/c-sharp-directory-info1.png)

The **DirectoryInfo** class also provides a delete method to delete created directory. In the following program, we are deleting a directory that we created in previous program.

---

### C# DirectoryInfo Example: Deleting Directory

[](https://www.tpointtech.com/c-sharp-directoryinfo#)[](https://www.tpointtech.com/c-sharp-directoryinfo#)[](https://www.tpointtech.com/c-sharp-directoryinfo#)

1. using System;  
2. using System.IO;  
3. namespace CSharpProgram  
4. {  
5.     class Program  
6.     {  
7.         static void Main(string[] args)  
8.         {  
9.             // Providing directory name with complete location.  
10.             DirectoryInfo directory = new DirectoryInfo(@"F:\javatpoint");  
11.             try  
12.             {  
13.                 // Deleting directory  
14.                 directory.Delete();  
15.                 Console.WriteLine("The directory is deleted successfully.");  
16.             }  
17.             catch (Exception e)  
18.             {  
19.                 Console.WriteLine("Something went wrong: {0}", e.ToString());  
20.             }  
21.         }  
22.     }  
23. }  

Output:

The directory is deleted successfully.

It throws a **System.IO.DirectoryNotFoundException** exception if the specified directory not present at the location.