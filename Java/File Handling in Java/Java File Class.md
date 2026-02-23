File class in Java is used to work with files and directories. In this chapter, we will learn what the File class is, why it is used, its declaration, fields, constructors, methods, and multiple examples to clearly understand how file and directory operations work.

## What is File Class in Java?

The **File class** is an abstract representation of file and directory pathnames. A pathname can be **absolute** (full path) or **relative** (path from the current directory).

The File class does not read or write file data, but it provides methods to:

- Create files and directories
- Delete or rename files and directories
- Check file properties
- List directory contents

## Why is File Class Used?

The File class is used to:

- Manage files and directories programmatically
- Check file existence and permissions
- Get file information like name, size, and path
- Perform directory listing operations

It acts as a bridge between Java programs and the file system.

## File Class Declaration

The File class belongs to the java.io package.

[](https://www.tpointtech.com/java-file-class#)[](https://www.tpointtech.com/java-file-class#)[](https://www.tpointtech.com/java-file-class#)

1. public class File implements Serializable, Comparable<File>  

## Fields of File Class

The following are commonly used static fields of the File class:

|   |   |
|---|---|
|**Field**|**Description**|
|**pathSeparator**|System-dependent path separator as a string|
|**pathSeparatorChar**|System-dependent path separator character|
|**separator**|System-dependent name separator as a string|
|**separatorChar**|System-dependent name separator character|

## Constructors of File Class

The File class provides several constructors to create file or directory path objects.

### 1. File(String pathname)

This constructor creates a new File instance using the given pathname.

Here is the syntax:

[](https://www.tpointtech.com/java-file-class#)[](https://www.tpointtech.com/java-file-class#)[](https://www.tpointtech.com/java-file-class#)

1. File file = new File("test.txt");  

### 2. File(String parent, String child)

This constructor creates a new File instance using a parent path and child path.

Here is the syntax:

[](https://www.tpointtech.com/java-file-class#)[](https://www.tpointtech.com/java-file-class#)[](https://www.tpointtech.com/java-file-class#)

1. File file = new File("D:/data", "test.txt");  

### 3. File(File parent, String child)

This constructor creates a new File instance from a parent File object and child pathname.

Here is the syntax:

[](https://www.tpointtech.com/java-file-class#)[](https://www.tpointtech.com/java-file-class#)[](https://www.tpointtech.com/java-file-class#)

1. File parent = new File("D:/data");</p>  
2. <p>File file = new File(parent, "test.txt");  

### 4. File(URI uri)

This constructor creates a new File instance by converting the given file: URI.

Here is the syntax:

[](https://www.tpointtech.com/java-file-class#)[](https://www.tpointtech.com/java-file-class#)[](https://www.tpointtech.com/java-file-class#)

1. File file = new File(new URI("file:///D:/test.txt"));  

### Example of File Class Constructors

The following example demonstrates different ways to create File objects.

[](https://www.tpointtech.com/java-file-class#)[](https://www.tpointtech.com/java-file-class#)[](https://www.tpointtech.com/java-file-class#)

1. import java.io.File;  

2. public class FileConstructorExample {  
3.     public static void main(String[] args) {  

4.         File f1 = new File("sample.txt");  
5.         File f2 = new File("D:/docs", "notes.txt");  
6.         File parent = new File("D:/docs");  
7.         File f3 = new File(parent, "report.txt");  

8.         System.out.println(f1.getPath());  
9.         System.out.println(f2.getPath());  
10.         System.out.println(f3.getPath());  
11.     }  
12. }  

## Methods of File Class

The File class provides the following methods to work with files and directories:

|Modifier and Type|Method|Description|
|---|---|---|
|static File|createTempFile(String prefix, String suffix)|It creates an empty file in the default temporary-file directory, using the given prefix and suffix to generate its name.|
|boolean|createNewFile()|It atomically creates a new, empty file named by this abstract pathname if and only if a file with this name does not yet exist.|
|boolean|canWrite()|It tests whether the application can modify the file denoted by this abstract pathname.String[]|
|boolean|canExecute()|It tests whether the application can execute the file denoted by this abstract pathname.|
|boolean|canRead()|It tests whether the application can read the file denoted by this abstract pathname.|
|boolean|isAbsolute()|It tests whether this abstract pathname is absolute.|
|boolean|isDirectory()|It tests whether the file denoted by this abstract pathname is a directory.|
|boolean|isFile()|It tests whether the file denoted by this abstract pathname is a normal file.|
|String|getName()|It returns the name of the file or directory denoted by this abstract pathname.|
|String|getParent()|It returns the pathname string of this abstract pathname's parent, or null if this pathname does not name a parent directory.|
|Path|toPath()|It returns a java.nio.file.Path object constructed from the this abstract path.|
|URI|toURI()|It constructs a file: URI that represents this abstract pathname.|
|File[]|listFiles()|It returns an [array](https://www.tpointtech.com/array-in-java) of abstract pathnames denoting the files in the directory denoted by this abstract pathname|
|long|getFreeSpace()|It returns the number of unallocated bytes in the partition named by this abstract path name.|
|String[]|list(FilenameFilter filter)|It returns an array of strings naming the files and directories in the directory denoted by this abstract pathname that satisfy the specified filter.|
|boolean|mkdir()|It creates the directory named by this abstract pathname.|

## Examples of Java File Class

Practice the following examples to understand different operations of the File class.

### Example 1: Creating a File

The following example demonstrates how to create a new file.

[](https://www.tpointtech.com/java-file-class#)[](https://www.tpointtech.com/java-file-class#)[](https://www.tpointtech.com/java-file-class#)

1. import java.io.File;  
2. import java.io.IOException;  

3. public class FileExample1 {  
4.     public static void main(String[] args) {  
5.         try {  
6.             File file = new File("javaFile123.txt");  
7.             if (file.createNewFile()) {  
8.                 System.out.println("New file is created!");  
9.             } else {  
10.                 System.out.println("File already exists.");  
11.             }  
12.         } catch (IOException e) {  
13.             e.printStackTrace();  
14.         }  
15.     }  
16. }  

**Output:**

New file is created!

### Example 2: Getting File Path Information

The following example demonstrates how to get absolute and canonical paths.

[](https://www.tpointtech.com/java-file-class#)[](https://www.tpointtech.com/java-file-class#)[](https://www.tpointtech.com/java-file-class#)

1. import java.io.File;  

2. public class FileExample2 {  
3.     public static void main(String[] args) {  
4.         try {  
5.             File file = new File("testFile1.txt");  
6.             file.createNewFile();  

7.             File canonical = file.getCanonicalFile();  
8.             System.out.println(canonical);  
9.             System.out.println(canonical.exists());  
10.             System.out.println(canonical.getAbsolutePath());  
11.         } catch (Exception e) {  
12.             e.printStackTrace();  
13.         }  
14.     }  
15. }  

**Output:**

testFile1.txt
true
/home/Work/Project/File/testFile1.txt

### Example 3: Listing Files in a Directory

The following example demonstrates how to list all file names in a directory.

[](https://www.tpointtech.com/java-file-class#)[](https://www.tpointtech.com/java-file-class#)[](https://www.tpointtech.com/java-file-class#)

1. import java.io.File;  

2. public class FileExample3 {  
3.     public static void main(String[] args) {  
4.         File dir = new File("/Users/sonoojaiswal/Documents");  
5.         String[] files = dir.list();  

6.         for (String name : files) {  
7.             System.out.println(name);  
8.         }  
9.     }  
10. }  

**Output:**

info.properties
info.properties.rtf
.DS_Store
.localized
Alok news
apache-tomcat-9.0.0.M19
apache-tomcat-9.0.0.M19.tar
bestreturn_org.rtf
BIODATA.pages
BIODATA.pdf
BIODATA.png
struts2jars.zip
workspace

### Example 4: Getting File Properties

The following example demonstrates how to read file properties such as size, hidden status, and write permission.

[](https://www.tpointtech.com/java-file-class#)[](https://www.tpointtech.com/java-file-class#)[](https://www.tpointtech.com/java-file-class#)

1. import java.io.File;  

2. public class FileExample4 {  
3.     public static void main(String[] args) {  
4.         File dir = new File("/Users/sonoojaiswal/Documents");  
5.         File[] files = dir.listFiles();  

6.         for (File file : files) {  
7.             System.out.println(  
8.                 file.getName() +  
9.                 " Can Write: " + file.canWrite() +  
10.                 " Is Hidden: " + file.isHidden() +  
11.                 " Length: " + file.length() + " bytes"  
12.             );  
13.         }  
14.     }  
15. }  

**Output:**

info.properties Can Write: true Is Hidden: false Length: 15 bytes
info.properties.rtf Can Write: true Is Hidden: false Length: 385 bytes
.DS_Store Can Write: true Is Hidden: true Length: 36868 bytes
.localized Can Write: true Is Hidden: true Length: 0 bytes
Alok news Can Write: true Is Hidden: false Length: 850 bytes
apache-tomcat-9.0.0.M19 Can Write: true Is Hidden: false Length: 476 bytes
apache-tomcat-9.0.0.M19.tar Can Write: true Is Hidden: false Length: 13711360 bytes
bestreturn_org.rtf Can Write: true Is Hidden: false Length: 389 bytes
BIODATA.pages Can Write: true Is Hidden: false Length: 707985 bytes
BIODATA.pdf Can Write: true Is Hidden: false Length: 69681 bytes
BIODATA.png Can Write: true Is Hidden: false Length: 282125 bytes
workspace Can Write: true Is Hidden: false Length: 1972 bytes

#### Note: File size, hidden status, and permissions may vary depending on the operating system and directory contents.