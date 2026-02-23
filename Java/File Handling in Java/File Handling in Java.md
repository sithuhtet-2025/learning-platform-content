File handling in Java allows us to create, read, write, update, and delete files stored on the system. In this chapter, we will learn what file handling is, why it is used, the concept of streams, common file methods, and different file operations with complete examples.

## What is File Handling in Java?

In Java, a **file** is a named location on disk used to store related information. File handling refers to the process of managing files programmatically, such as:

- Creating a file
- Retrieving file information
- Writing data into a file
- Reading data from a file
- Deleting a file

Java provides the java.io package to perform file handling operations.

## Stream in Java

A stream represents a sequence of data. File handling is performed using streams, which are classified into two types.

### 1. Byte Stream

Byte Stream is used to handle byte-oriented data, such as images, audio files, and binary files.  
Classes like [FileInputStream](https://www.tpointtech.com/java-fileinputstream-class) and [FileOutputStream](https://www.tpointtech.com/java-fileoutputstream-class) are used for byte stream operations.

### 2. Character Stream

Character Stream is used to handle character-oriented data, such as text files.  
Classes like [FileReader](https://www.tpointtech.com/java-filereader-class), [FileWriter](https://www.tpointtech.com/java-filewriter-class), [BufferedReader](https://www.tpointtech.com/java-bufferedreader-class), and [BufferedWriter](https://www.tpointtech.com/java-bufferedwriter-class) are used for character stream operations.

## File Class Methods

The following are some commonly used methods of the File class:

|S.No.|Method|Return Type|Description|
|---|---|---|---|
|1.|canRead()|Boolean|The **canRead()** method is used to check whether we can read the data of the file or not.|
|2.|createNewFile()|Boolean|The **createNewFile()** method is used to create a new empty file.|
|3.|canWrite()|Boolean|The **canWrite()** method is used to check whether we can write the data into the file or not.|
|4.|exists()|Boolean|The **exists()** method is used to check whether the specified file is present or not.|
|5.|delete()|Boolean|The **delete()** method is used to delete a file.|
|6.|getName()|String|The **getName()** method is used to find the file name.|
|7.|getAbsolutePath()|String|The **getAbsolutePath()** method is used to get the absolute pathname of the file.|
|8.|length()|Long|The **length()** method is used to get the size of the file in bytes.|
|9.|list()|String[]|The **list()** method is used to get an array of the files available in the directory.|
|10.|mkdir()|Boolean|The **mkdir()** method is used for creating a new directory.|

## Create a File

The create a file operation is used to [create a new file](https://www.tpointtech.com/how-to-create-a-file-in-java) in the system. This operation is performed using the **createNewFile()** method of the File class. This method returns **true** if the file is created successfully and **false** if the file already exists at the specified location.

### Example

This example demonstrates how a new file is created using the createNewFile() method.

[](https://www.tpointtech.com/file-handling-in-java#)[](https://www.tpointtech.com/file-handling-in-java#)[](https://www.tpointtech.com/file-handling-in-java#)

1. // Importing File class  
2. import java.io.File;  
3. // Importing the IOException class for handling errors  
4. import java.io.IOException;   
5.  class CreateFile {  
6.                public static void main(String args[]) {  
7.                try {  
8.                        // Creating an object of a file  
9.                        File f0 = new File("D:FileOperationExample.txt");   
10.                        if (f0.createNewFile()) {  
11.                                   System.out.println("File " + f0.getName() + " is created successfully.");  
12.                        } else {  
13.                                   System.out.println("File is already exist in the directory.");  
14.                        }  
15.                      } catch (IOException exception) {  
16.                               System.out.println("An unexpected error is occurred.");  
17.                               exception.printStackTrace();  
18.                   }   
19.         }  
20. }  

**Output:**

![File Operations in Java](https://images.tpointtech.com/core/images/file-operations-in-java3.png)  
![File Operations in Java](https://images.tpointtech.com/core/images/file-operations-in-java4.png)

**Explanation:**

In the above code, we import the File and IOException class for performing file operation and handling errors, respectively. We create the **f0** object of the File class and specify the location of the directory where we want to create a file. In the try block, we call the **createNewFile()** method through the **f0** object to create a new file in the specified location. If the method returns false, it will jump to the else section. If there is any error, it gets handled in the catch block.

## Get File Information

The get file Information operation is used to retrieve details about a file. Java provides several methods to obtain information such as the file name, absolute path, readability, writability, and file size (length).

### Example

This example demonstrates how to access and display different properties of a file, including its name, path, permissions, and size.

[](https://www.tpointtech.com/file-handling-in-java#)[](https://www.tpointtech.com/file-handling-in-java#)[](https://www.tpointtech.com/file-handling-in-java#)

1. // Import the File class  
2. import java.io.File;   
3. class FileInfo {  
4.     public static void main(String[] args) {  
5.         // Creating file object  
6.         File f0 = new File("D:FileOperationExample.txt");  
7.         if (f0.exists()) {  
8.             // Getting file name  
9.             System.out.println("The name of the file is: " + f0.getName());  

10.             // Getting path of the file   
11.             System.out.println("The absolute path of the file is: " + f0.getAbsolutePath());     

12.             // Checking whether the file is writable or not  
13.             System.out.println("Is file writeable?: " + f0.canWrite());    

14.             // Checking whether the file is readable or not  
15.             System.out.println("Is file readable " + f0.canRead());    

16.             // Getting the length of the file in bytes  
17.             System.out.println("The size of the file in bytes is: " + f0.length());    
18.         } else {  
19.             System.out.println("The file does not exist.");  
20.         }  
21.     }  
22. }  

**Output:**

![File Operations in Java](https://images.tpointtech.com/core/images/file-operations-in-java5.png)

**Description:**

In the above code, we import the **java.io.File** package and create a class **FileInfo**. In the main method, we create an object of the text file which we have created in our previous example. We check the existence of the file using a conditional statement, and if it is present, we get the following information about that file:

1. We get the name of the file using the **getName()**
2. We get the absolute path of the file using the **getAbsolutePath()** method of the file.
3. We check whether we can write data into a file or not using the **canWrite()**
4. We check whether we can read the data of the file or not using the **canRead()**
5. We get the length of the file by using the **length()**

If the file doesn't exist, we show a custom message.

## Write to a File

The [write to a file](https://www.tpointtech.com/how-to-write-to-a-file-in-java) operation allows data to be stored inside a file. To write data, Java uses the **FileWriter** class along with its **write()** method. After writing data, it is important to close the stream using the close() method to release system resources.

### Example

This example demonstrates how data is written into a file using FileWriter and how closing the stream ensures that all data is saved properly.

[](https://www.tpointtech.com/file-handling-in-java#)[](https://www.tpointtech.com/file-handling-in-java#)[](https://www.tpointtech.com/file-handling-in-java#)

1. // Importing the FileWriter class  
2. import java.io.FileWriter;   

3. // Importing the IOException class for handling errors  
4. import java.io.IOException;   

5. class WriteToFile {  
6.     public static void main(String[] args) {  

7.     try {  
8.         FileWriter fwrite = new FileWriter("D:FileOperationExample.txt");  
9.         // writing the content into the FileOperationExample.txt file  
10.         fwrite.write("A named location used to store related information is referred to as a File.");   

11.         // Closing the stream  
12.         fwrite.close();   
13.         System.out.println("Content is successfully wrote to the file.");  
14.     } catch (IOException e) {  
15.         System.out.println("Unexpected error occurred");  
16.         e.printStackTrace();  
17.         }  
18.     }  
19. }  

**Output:**

![File Operations in Java](https://images.tpointtech.com/core/images/file-operations-in-java6.png)  
![File Operations in Java](https://images.tpointtech.com/core/images/file-operations-in-java7.png)

**Explanation:**

In the above code, we import the **java.io.FileWriter** and **java.io.IOException** classes. We create a class WriteToFile, and in its main method, we use the **try-catch** block. In the try section, we create an instance of the FileWriter class, i.e., **fwrite**. We call the **write** method of the FileWriter class and pass the content to that function which we want to write. After that, we call the **close()** method of the FileWriter class to close the file stream. After writing the content and closing the stream, we print a custom message.

If we get any error in the try section, it jumps to the catch block. In the catch block, we handle the **IOException** and print a custom message.

## Read from a File

The read from a file operation is used to read data stored in a file. Java commonly uses the Scanner class for this purpose. An instance of the Scanner class is created, and methods like hasNextLine() and nextLine() are used to read file content. After reading the data, the stream must be closed using the close() method.

### Example

This example demonstrates how file data is read line by line using the Scanner class.

[](https://www.tpointtech.com/file-handling-in-java#)[](https://www.tpointtech.com/file-handling-in-java#)[](https://www.tpointtech.com/file-handling-in-java#)

1. // Importing the File class  
2. import java.io.File;   
3. // Importing FileNotFoundException class for handling errors  
4. import java.io.FileNotFoundException;   
5. // Importing the Scanner class for reading text files  
6. import java.util.Scanner;   

7. class ReadFromFile {  
8.     public static void main(String[] args) {  
9.         try {  
10.             // Create f1 object of the file to read data  
11.             File f1 = new File("D:FileOperationExample.txt");    
12.             Scanner dataReader = new Scanner(f1);  
13.             while (dataReader.hasNextLine()) {  
14.                 String fileData = dataReader.nextLine();  
15.                 System.out.println(fileData);  
16.             }  
17.             dataReader.close();  
18.         } catch (FileNotFoundException exception) {  
19.             System.out.println("Unexcpected error occurred!");  
20.             exception.printStackTrace();  
21.         }  
22.     }  
23. }  

**Output:**

![File Operations in Java](https://images.tpointtech.com/core/images/file-operations-in-java8.png)

**Expalnation:**

In the above code, we import the **"java.util.Scannner", "java.io.File"** and **"java.io.IOException"** classes. We create a class **ReadFromFile**, and in its main method, we use the **try-catch block**. In the try section, we create an instance of both the **Scanner** and the **File** classes. We pass the **File** class object to the **Scanner** class object and then iterate the scanner class object using the **"While"** loop and print each line of the file. We also need to close the scanner class object, so we use the close() function. If we get any error in the try section, it jumps to the catch block. In the catch block, we handle the IOException and print a custom message.

## Delete a File

The delete a file operation is used to [remove a file from the system](https://www.tpointtech.com/how-to-delete-a-file-in-java). Java provides the **delete()** method of the File class to perform this task. Since no input or output stream is used while deleting a file, there is no need to close any stream.

### Example

This example demonstrates how an existing file is deleted using the delete() method and how Java confirms the deletion status.

[](https://www.tpointtech.com/file-handling-in-java#)[](https://www.tpointtech.com/file-handling-in-java#)[](https://www.tpointtech.com/file-handling-in-java#)

1. // Importing the File class  
2. import java.io.File;   
3. class DeleteFile {  
4.   public static void main(String[] args) {   
5.     File f0 = new File("D:FileOperationExample.txt");   
6.     if (f0.delete()) {   
7.       System.out.println(f0.getName()+ " file is deleted successfully.");  
8.     } else {  
9.       System.out.println("Unexpected error found in deletion of the file.");  
10.     }   
11.   }   
12. }  

**Output:**

![File Operations in Java](https://images.tpointtech.com/core/images/file-operations-in-java9.png)

**Explanation:**

In the above code, we import the **File** class and create a class **DeleteFile**. In the main() method of the class, we create **f0** object of the file which we want to delete. In the **if** statement, we call the **delete()** method of the file using the f0 object. If the delete() method returns true, we print the success custom message. Otherwise, it jumps to the else section where we print the unsuccessful custom message.

All the above-mentioned operations are used to read, write, delete, and create file programmatically.

## Check Whether a File Exists

To check whether a file exists, the **exists()** method of the File class is used. This method checks the presence of a file or directory at the specified location and returns true if it is found; otherwise, it returns false.

### Example

This example demonstrates how Java checks the existence of a file before performing any file operation.

[](https://www.tpointtech.com/file-handling-in-java#)[](https://www.tpointtech.com/file-handling-in-java#)[](https://www.tpointtech.com/file-handling-in-java#)

1. import java.io.File;  

2. public class FileExistsExample {  
3.     public static void main(String[] args) {  
4.         File file = new File("test.txt");  

5.         if (file.exists()) {  
6.             System.out.println("File exists");  
7.         } else {  
8.             System.out.println("File does not exist");  
9.         }  
10.     }  
11. }  

**Output:**

File exists

## Create a Directory

Java also allows creating directories (folders), which is useful when files need to be organized into specific locations. To create a directory, the **mkdir()** method of the File class is used that creates a single directory and returns true if the directory is created successfully or false if it already exists or cannot be created.

### Example

This example demonstrates how a new directory is created using Java file-handling methods.

[](https://www.tpointtech.com/file-handling-in-java#)[](https://www.tpointtech.com/file-handling-in-java#)[](https://www.tpointtech.com/file-handling-in-java#)

1. import java.io.File;  

2. public class CreateDirectoryExample {  
3.     public static void main(String[] args) {  
4.         File dir = new File("MyFolder");  

5.         if (dir.mkdir()) {  
6.             System.out.println("Directory created successfully");  
7.         } else {  
8.             System.out.println("Directory already exists");  
9.         }  
10.     }  
11. }  

**Output:**

Directory created successfully

## List Files in a Directory

You can list out all files and subdirectories present inside a directory by using the **list()** or **listFiles()** method of the File class. These methods retrieve the names or file objects of all entries available in the specified directory.

### Example

This example demonstrates how lists all files and folders available inside a directory.

[](https://www.tpointtech.com/file-handling-in-java#)[](https://www.tpointtech.com/file-handling-in-java#)[](https://www.tpointtech.com/file-handling-in-java#)

1. import java.io.File;  

2. public class ListFilesExample {  
3.     public static void main(String[] args) {  
4.         File folder = new File("MyFolder");  
5.         String[] files = folder.list();  

6.         for (String file : files) {  
7.             System.out.println(file);  
8.         }  
9.     }  
10. }  

**Output:**

file1.txt
file2.txt
subFolder

## Rename a File

You can rename a file or move it to another location by using the **renameTo()** method of the File class. This method changes the name or path of the file and returns true if the operation is successful; otherwise, it returns false.

### Example

This example demonstrates how an existing file is renamed using Java file-handling functionality.

[](https://www.tpointtech.com/file-handling-in-java#)[](https://www.tpointtech.com/file-handling-in-java#)[](https://www.tpointtech.com/file-handling-in-java#)

1. import java.io.File;  

2. public class RenameFileExample {  
3.     public static void main(String[] args) {  
4.         File oldFile = new File("old.txt");  
5.         File newFile = new File("new.txt");  

6.         if (oldFile.renameTo(newFile)) {  
7.             System.out.println("File renamed successfully");  
8.         } else {  
9.             System.out.println("File rename failed");  
10.         }  
11.     }  
12. }  

**Output:**

File renamed successfully

## File Permissions

You can check and modify file permissions by using methods such as **canRead()**, **canWrite()**, **canExecute()**, **setReadable()**, **setWritable()**, and **setExecutable()** provided by the File class. You can also use the [FilePermission class](https://www.tpointtech.com/java-filepermission-class) and its methods to read, write, and change the file's permissions.

### Example

This example demonstrates how Java checks and updates file access permissions.

[](https://www.tpointtech.com/file-handling-in-java#)[](https://www.tpointtech.com/file-handling-in-java#)[](https://www.tpointtech.com/file-handling-in-java#)

1. import java.io.File;  

2. public class FilePermissionExample {  
3.     public static void main(String[] args) {  
4.         File file = new File("test.txt");  

5.         System.out.println(file.canRead());  
6.         System.out.println(file.canWrite());  
7.     }  
8. }  

**Output:**

true
true

## File Size and Last Modified Time

You can determine the size of a file and the last modified date by using the **length()** and **lastModified()** methods of the File class. These methods return the file size in bytes and the last modification time.

### Example

This example demonstrates how Java retrieves the file size and last modified timestamp.

[](https://www.tpointtech.com/file-handling-in-java#)[](https://www.tpointtech.com/file-handling-in-java#)[](https://www.tpointtech.com/file-handling-in-java#)

1. import java.io.File;  

2. public class FileInfoExample {  
3.     public static void main(String[] args) {  
4.         File file = new File("test.txt");  

5.         System.out.println(file.length());  
6.         System.out.println(file.lastModified());  
7.     }  
8. }  

**Output:**

1024
1707052800000

## Handling File Exceptions

File operations may cause exceptions such as file not found or access denied. These situations are handled using [Java's exception handling](https://www.tpointtech.com/exception-handling-in-java) mechanism (try, catch, and finally).

### Example

This example demonstrates how Java handles exceptions that may occur during file operations.

[](https://www.tpointtech.com/file-handling-in-java#)[](https://www.tpointtech.com/file-handling-in-java#)[](https://www.tpointtech.com/file-handling-in-java#)

1. import java.io.File;  
2. import java.io.FileReader;  

3. public class FileExceptionExample {  
4.     public static void main(String[] args) {  
5.         try {  
6.             FileReader fr = new FileReader("missing.txt");  
7.         } catch (Exception e) {  
8.             System.out.println("File not found");  
9.         }  
10.     }  
11. }  

**Output:**

File not found