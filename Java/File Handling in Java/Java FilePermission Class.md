The FilePermission class is used to define access permissions for files and directories in Java. These permissions are always associated with a specific file or directory path.

## What is Java FilePermission Class?

The **FilePermission** class belongs to the [java.io package](https://www.tpointtech.com/java-io-package) and is used to control access to files and directories, such as read, write, execute, and delete operations.

## File Path Types in FilePermission

The path used in FilePermission can be defined in two ways:

- **D:\IO\-**  
    It represents all files and subdirectories recursively inside the specified directory.
- **D:\IO\***  
    It represents all files and directories inside the specified directory but excludes subdirectories.

## Java FilePermission Class Declaration

The declaration of the FilePermission class is as follows:

[](https://www.tpointtech.com/java-filepermission-class#)[](https://www.tpointtech.com/java-filepermission-class#)[](https://www.tpointtech.com/java-filepermission-class#)

1. public final class FilePermission extends Permission implements Serializable  

## Constructor of FilePermission Class

The **FilePermission** class provides the following constructor to create permission objects for files and directories.

[](https://www.tpointtech.com/java-filepermission-class#)[](https://www.tpointtech.com/java-filepermission-class#)[](https://www.tpointtech.com/java-filepermission-class#)

1. FilePermission(String path, String actions)  

This constructor creates a FilePermission object with the specified path and actions.

### Syntax

The syntax of FilePermission class constructor is as follows:

[](https://www.tpointtech.com/java-filepermission-class#)[](https://www.tpointtech.com/java-filepermission-class#)[](https://www.tpointtech.com/java-filepermission-class#)

1. FilePermission(String path, String actions)  

Here, actions can be read, write, execute, or delete.

## Methods of FilePermission Class

The FilePermission class provides methods to manage and verify file permissions.

|Method|Description|
|---|---|
|ByteArrayOutputStream()|Creates a new byte [array](https://www.tpointtech.com/array-in-java) output stream with the initial capacity of 32 bytes, though its size increases if necessary.|
|ByteArrayOutputStream(int size)|Creates a new byte array output stream, with a buffer capacity of the specified size, in bytes.|

## Java FilePermission class methods

|Method|Description|
|---|---|
|int hashCode()|It is used to return the hash code value of an [object](https://www.tpointtech.com/object-and-class-in-java).|
|String getActions()|It is used to return the "canonical string representation" of an action.|
|boolean equals(Object obj)|It is used to check the two FilePermission objects for equality.|
|boolean implies(Permission p)|It is used to check the FilePermission object for the specified permission.|
|PermissionCollection newPermissionCollection()|It is used to return the new PermissonCollection object for storing the FilePermission object.|

## Examples of FilePermission Class

The following examples show how to use the FilePermission class to manage file and directory permissions.

### Example 1: Grant Read and Write Permission to a File

In this example, read permission is given to a directory and write permission is given to a file inside that directory.

[](https://www.tpointtech.com/java-filepermission-class#)[](https://www.tpointtech.com/java-filepermission-class#)[](https://www.tpointtech.com/java-filepermission-class#)

1. import java.io.FilePermission;  
2. import java.security.PermissionCollection;  

3. public class FilePermissionExample1 {  
4.     public static void main(String[] args) {  

5.         String path = "D:\\IO Package\\java.txt";  

6.         FilePermission p1 = new FilePermission("D:\\IO Package\\-", "read");  
7.         PermissionCollection pc = p1.newPermissionCollection();  
8.         pc.add(p1);  

9.         FilePermission p2 = new FilePermission(path, "write");  
10.         pc.add(p2);  

11.         if (pc.implies(new FilePermission(path, "read,write"))) {  
12.             System.out.println("Read and Write permission granted");  
13.         } else {  
14.             System.out.println("Permission not granted");  
15.         }  
16.     }  
17. }  

**Output:**

Read and Write permission granted

### Example 2: Check Read Permission for a Directory

In this example, read permission is checked for all files inside a directory.

[](https://www.tpointtech.com/java-filepermission-class#)[](https://www.tpointtech.com/java-filepermission-class#)[](https://www.tpointtech.com/java-filepermission-class#)

1. import java.io.FilePermission;  
2. import java.security.PermissionCollection;  

3. public class FilePermissionExample2 {  
4.     public static void main(String[] args) {  

5.         FilePermission permission =  
6.                 new FilePermission("D:\\IO Package\\*", "read");  

7.         PermissionCollection pc = permission.newPermissionCollection();  
8.         pc.add(permission);  

9.         if (pc.implies(new FilePermission("D:\\IO Package\\test.txt", "read"))) {  
10.             System.out.println("Read permission is allowed");  
11.         } else {  
12.             System.out.println("Read permission is not allowed");  
13.         }  
14.     }  
15. }  

**Output:**

Read permission is allowed