In Java, creating a file is easy by using pre-defined classes and packages. There are three ways to create a file.

- **Using File.createNewFile() method**
- **Using FileOutputStream class**
- **Using File.createFile() method**

## Create a File Using File.createNewFile() method

The **File.createNewFile()** is a method of [File class](https://www.tpointtech.com/java-file-class) which belongs to a **java.io** package. It does not accept any argument. The method automatically creates a new, empty file. The method returns a boolean value:

- true, if the file created successfully.
- false, if the file already exists.

When we initialize File class object, we provide the file name and then we can call createNewFile() method of the File class to create a new file in Java.

The File.createNewFile() method throws java.io.IOException if an I/O error occurred. It also throws SecurityException if a security manager exists and its SecurityManager.checkWriter(java.lang.String) method denies write access to the file.

### Method Signature

The signature of the method is:

[](https://www.tpointtech.com/how-to-create-a-file-in-java#)[](https://www.tpointtech.com/how-to-create-a-file-in-java#)[](https://www.tpointtech.com/how-to-create-a-file-in-java#)

1. public boolean createNewFile() throws IOException  

We can pass the file name or absolute path or relative path as an argument in the File class object. For a non-absolute path, File object tries to locate the file in the current directory.

Example

The following example creates a new, empty text file. The first run creates music.txt successfully while on the second run it failed. We can create any type of file by changing the file extension only.

[](https://www.tpointtech.com/how-to-create-a-file-in-java#)[](https://www.tpointtech.com/how-to-create-a-file-in-java#)[](https://www.tpointtech.com/how-to-create-a-file-in-java#)

1. import java.io.File;  
2. import java.io.IOException;  
3. public class CreateFileExample1   
4. {  
5. public static void main(String[] args)   
6. {     
7. File file = new File("C:\\demo\\music.txt"); //initialize File object and passing path as argument  
8. boolean result;  
9. try   
10. {  
11. result = file.createNewFile();  //creates a new file  
12. if(result)      // test if successfully created a new file  
13. {  
14. System.out.println("file created "+file.getCanonicalPath()); //returns the path string  
15. }  
16. else  
17. {  
18. System.out.println("File already exist at location: "+file.getCanonicalPath());  
19. }  
20. }   
21. catch (IOException e)   
22. {  
23. e.printStackTrace();    //prints exception if any  
24. }         
25. }  
26. }  

**Output**

When file does not exists.

![How to Create a File in Java](https://images.tpointtech.com/core/images/how-to-create-a-file-in-java.png)

When file already exists.

![How to Create a File in Java1](https://images.tpointtech.com/core/images/how-to-create-a-file-in-java1.png)

## Create a File Using FileOutputStream

A file Output stream writes data to a file. [Java FileOutputStream class](https://www.tpointtech.com/java-fileoutputstream-class) also provide support for files. It belongs to the java.io package. It stores the data into bytes. We use FileOutputStream class when we need to write some data into the created file. The FileOutputStream class provides a constructor to create a file.

### Constructor Signature

The signature of the constructor is:

[](https://www.tpointtech.com/how-to-create-a-file-in-java#)[](https://www.tpointtech.com/how-to-create-a-file-in-java#)[](https://www.tpointtech.com/how-to-create-a-file-in-java#)

1. public FileOutputStream(String name, boolean append) throws FileNotFoundException  

### Parameters

- **name:**is the file name
- **append:**if true, byte will be written to the end of the file, not in the beginning.

### Example

In the following example, we have created a file using FileOutputStream.

[](https://www.tpointtech.com/how-to-create-a-file-in-java#)[](https://www.tpointtech.com/how-to-create-a-file-in-java#)[](https://www.tpointtech.com/how-to-create-a-file-in-java#)

1. import java.io.FileOutputStream;  
2. import java.util.Scanner;  
3. public class CreateFileExample  
4. {  
5. public static void main(String args[])  
6. {  
7. try  
8. {  
9. Scanner sc=new Scanner(System.in);         //object of Scanner class  
10. System.out.print("Enter the file name: ");  
11. String name=sc.nextLine();              //variable name to store the file name  
12. FileOutputStream fos=new FileOutputStream(name, true);  // true for append mode  
13. System.out.print("Enter file content: ");         
14. String str=sc.nextLine()+"\n";      //str stores the string which we have entered  
15. byte[] b= str.getBytes();       //converts string into bytes  
16. fos.write(b);           //writes bytes into file  
17. fos.close();            //close the file  
18. System.out.println("file saved.");  
19. }  
20. catch(Exception e)  
21. {  
22. e.printStackTrace();          
23. }  
24. }  
25. }  

**Output**

![How to Create a File in Java2](https://images.tpointtech.com/core/images/how-to-create-a-file-in-java2.png)

## Create a File Using File.createFile() Method

The File.createFile() is a method of File class which belongs to **java.nio.file** package. It also provides support for files. The nio package is buffer-oriented. The createFile() method is also used to create a new, empty file. We don't need to close the resources when using this method. It is an advantage.

### Method Signature

The signature of the method is:

[](https://www.tpointtech.com/how-to-create-a-file-in-java#)[](https://www.tpointtech.com/how-to-create-a-file-in-java#)[](https://www.tpointtech.com/how-to-create-a-file-in-java#)

1. public static Path createFile(Path, Attribute) throws IOException  

Here,

- **Path:** The path of the file.
- **Attribute:** An optional list of file attributes.

The method returns the file.

### Example

The following example also creates a new, empty file. We create a Path instance using a static method in the Paths class (java.nio.file.Paths) named Paths.get(). Notice the following statement:

[](https://www.tpointtech.com/how-to-create-a-file-in-java#)[](https://www.tpointtech.com/how-to-create-a-file-in-java#)[](https://www.tpointtech.com/how-to-create-a-file-in-java#)

1. Path path = Paths.get("C:\\demo\\javaprogram.txt");  

In the above line Path is an interface and Paths is a class. Both belongs to same package. The Paths.get() method creates the Path Instance.

[](https://www.tpointtech.com/how-to-create-a-file-in-java#)[](https://www.tpointtech.com/how-to-create-a-file-in-java#)[](https://www.tpointtech.com/how-to-create-a-file-in-java#)

1. import java.io.IOException;  
2. import java.nio.file.*;  
3. public class CreateFileExample3  
4. {  
5. public static void main(String[] args)   
6. {  
7. Path path = Paths.get("C:\\demo\\javaprogram.txt"); //creates Path instance  
8. try   
9. {  
10. Path p= Files.createFile(path);     //creates file at specified location  
11. System.out.println("File Created at Path: "+p);  
12. }   
13. catch (IOException e)   
14. {  
15. e.printStackTrace();  
16. }  
17. }  
18. }  

**Output**

![How to Create a File in Java3](https://images.tpointtech.com/core/images/how-to-create-a-file-in-java3.png)