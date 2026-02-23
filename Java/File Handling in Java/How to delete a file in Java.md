Java provides simple methods to delete files and directories. In this chapter, we will learn how to delete a file in Java using commonly used methods with examples.

## What is file deletion in Java?

The file deletion means removing an existing file or directory from the system using predefined methods provided by the Java File class.

There are following ways to delete a file in Java.

- Using File.delete() method
- Using File.deleteOnExit() method

## File Deletion Using File.delete() Method

The **delete()** method is provided by the [File class](https://www.tpointtech.com/java-file-class) to delete a file or an empty directory. If the file is deleted successfully, the method returns true; otherwise, it returns false.

### Method Signature

The syntax of the method is as follows:

[](https://www.tpointtech.com/how-to-delete-a-file-in-java#)[](https://www.tpointtech.com/how-to-delete-a-file-in-java#)[](https://www.tpointtech.com/how-to-delete-a-file-in-java#)

1. public boolean delete()  

This method deletes the file immediately. If the file does not exist or the directory is not empty, deletion fails.

### Example: Delete File Using File.delete() Method

In this example, a text file named demo.txt is deleted using the delete() method.

[](https://www.tpointtech.com/how-to-delete-a-file-in-java#)[](https://www.tpointtech.com/how-to-delete-a-file-in-java#)[](https://www.tpointtech.com/how-to-delete-a-file-in-java#)

1. import java.io.File;  

2. public class FileDeleteExample {  
3.     public static void main(String[] args) {  
4.         try {  
5.             File f = new File("E:\\demo.txt");  

6.             if (f.delete()) {  
7.                 System.out.println(f.getName() + " deleted");  
8.             } else {  
9.                 System.out.println("failed");  
10.             }  
11.         } catch (Exception e) {  
12.             e.printStackTrace();  
13.         }  
14.     }  
15. }  

**Output (when file exists):**

demo.txt deleted

**Output (when file does not exist):**

failed

## File Deletion Using File.deleteOnExit() Method

The deleteOnExit() method deletes a file or directory when the [Java Virtual Machine (JVM)](https://www.tpointtech.com/jvm-java-virtual-machine) terminates. This method does not delete the file immediately.

### Method Signature

The syntax of the method is as follows:

[](https://www.tpointtech.com/how-to-delete-a-file-in-java#)[](https://www.tpointtech.com/how-to-delete-a-file-in-java#)[](https://www.tpointtech.com/how-to-delete-a-file-in-java#)

1. public void deleteOnExit()  

Once this method is called, the delete request cannot be canceled. It is commonly used for deleting temporary files.

### Example: Delete Temporary File Using deleteOnExit()

In this example, a temporary file is created and automatically deleted when the program terminates.

[](https://www.tpointtech.com/how-to-delete-a-file-in-java#)[](https://www.tpointtech.com/how-to-delete-a-file-in-java#)[](https://www.tpointtech.com/how-to-delete-a-file-in-java#)

1. import java.io.File;  
2. import java.io.IOException;  

3. public class DeleteOnExitExample {  
4.     public static void main(String[] args) {  
5.         try {  
6.             File temp = File.createTempFile("abc", ".temp");  

7.             System.out.println("Temp file created at location: " + temp.getAbsolutePath());  
8.             temp.deleteOnExit();  
9.             System.out.println("Temp file exists : " + temp.exists());  
10.         } catch (IOException e) {  
11.             e.printStackTrace();  
12.         }  
13.     }  
14. }  

**Output:**

Temp file created at location: ...
Temp file exists : true

### Example: Delete Text File Using deleteOnExit()

In this example, a text file is scheduled for deletion when the JVM terminates.

[](https://www.tpointtech.com/how-to-delete-a-file-in-java#)[](https://www.tpointtech.com/how-to-delete-a-file-in-java#)[](https://www.tpointtech.com/how-to-delete-a-file-in-java#)

1. import java.io.File;  

2. public class DeleteTextFileExample {  
3.     public static void main(String[] args) {  
4.         try {  
5.             File file = new File("F:\\newfile.txt");  
6.             file.deleteOnExit();  
7.             System.out.println("Done");  
8.             Thread.sleep(1000);  
9.         } catch (Exception e) {  
10.             e.printStackTrace();  
11.         }  
12.     }  
13. }  

**Output:**

Done