In Java, **writing to a file** involve writing and saving text in a designated file located in the directory. It enables applications to create, edit, and update binary or text files. For effective file operations and resource management, Java provides built-in classes. Managing exceptions is necessary when writing data to a file in order to avoid runtime errors and ensure seamless operation.

In Java, there are **various ways to write to a file** because Java provides various classes and methods for file handing.

1. Using writeString() Method
2. Using FileWriter Class
3. Using BufferedWriter Class
4. Using FileOutputStream Class

## 1. Using writeString() Method

The writeString() method is defined in the Files class that belongs to java.nio.file package. It is introduced since JDK 11. The method writes a CharSequence to the target file. Note that characters are encoded into bytes using the UTF-8 charset.

There are the following two versions of the writeString() method is available.

**Syntax:**

[](https://www.tpointtech.com/how-to-write-to-a-file-in-java#)[](https://www.tpointtech.com/how-to-write-to-a-file-in-java#)[](https://www.tpointtech.com/how-to-write-to-a-file-in-java#)

1. public static Path writeString (Path path, CharSequence csq, OpenOption... options) throws IOException  

**Parameters:**

- **path:** It defines the path of the target file in which we want to write.
- **csq:** Character sequence to be written.
- **options:** It specifies how the file is opened.

It returns the path. In this method the first two parameters must be present and the third one is optional. It throws IllegalArgumentException, IOException, UnSupportedOperationException, and SecqurityException.

Let's use the writeString() method to write to a file.

### Example

[](https://www.tpointtech.com/how-to-write-to-a-file-in-java#)[](https://www.tpointtech.com/how-to-write-to-a-file-in-java#)[](https://www.tpointtech.com/how-to-write-to-a-file-in-java#)

1. import java.io.BufferedReader;  
2. import java.io.BufferedWriter;  
3. import java.io.FileWriter;  
4. import java.io.IOException;  
5. import java.io.InputStreamReader;  
6. import java.util.*;  
7. public class Main  
8. {  
9.     public static void main(String[] args)  
10.     {  
11.         // Assigning the file content  
12.         String txt = "Welcome to TpointTech\nHello World!\n WELCOME";  
13.         try {  
14.             BufferedReader buffread = new BufferedReader(new InputStreamReader(System.in));  
15.             System.out.print("Enter the Path : ");  
16.             // Reading the File name  
17.             String path = buffread.readLine();  
18.             // Create a BufferedWriter object  
19.             BufferedWriter file_writer = new BufferedWriter(new FileWriter(path));  
20.             // Write the text(content) to the file  
21.             file_writer.write(txt);  
22.             // displaying the content that is there in file  
23.             System.out.print(txt);  
24.             // Close the BufferedWriter object  
25.             file_writer.close();  
26.         }  
27.         // Catch block to handle if exceptions occur  
28.         catch (IOException ex) {  
29.             System.out.print(ex.getMessage());  
30.         }  
31.     }  
32. }  

**Output:**

![How to Write to a File in Java](https://images.tpointtech.com/core/images/how-to-write-to-a-file-in-java.png)

## 2. Using FileWriter Class

Java FileWriter class belongs to java.io package. The class writes stream of character to a file. Usually, it is used when we have to write short content to a file. The constructors of this class assume that the default character encoding and the default byte-buffer size are acceptable.

Let's use the FileWriter class to write to a file.

### Example

[](https://www.tpointtech.com/how-to-write-to-a-file-in-java#)[](https://www.tpointtech.com/how-to-write-to-a-file-in-java#)[](https://www.tpointtech.com/how-to-write-to-a-file-in-java#)

1. import java.io.*;  
2. import java.nio.file.Files;  
3. import java.nio.file.Path;  
4. import java.util.*;  
5. public class Main  
6. {  
7.     public static void main(String[] args) throws IOException   
8.     {  
9.         // Data that has to be written in the file  
10.         String txt = "Welcome to TpointTech\nHello World!\n WELCOME";  
11.         BufferedReader buffread = new BufferedReader(new InputStreamReader(System.in));  
12.         try {  
13.             System.out.print("Enter the Path : ");    
14.             String path = buffread.readLine();  
15.             // Create a FileWriter object so   
16.             // that we can write to the file.  
17.             FileWriter fileWrite = new FileWriter(path);  
18.             // Writing inside the file  
19.             fileWrite.write(txt);  
20.             // Displaying the contents of the file  
21.             System.out.println(txt);  
22.             // Closing the file writing connection  
23.             fileWrite.close();  
24.         }  
25.           catch (IOException ex) {  
26.             System.err.println("An error occurred in the file: " + ex.getMessage());  
27.         }  
28.     }  
29. }  

**Output:**

![How to Write to a File in Java](https://images.tpointtech.com/core/images/how-to-write-to-a-file-in-java2.png)

## 3. Using BufferedWriter Class

Java BufferedWriter class java.io package. It is used for writing text to a stream of character output. It can have a huge buffer size assigned, but it has a default size. Writing characters, strings, and arrays can be done with it. If no prompt output is needed, it is preferable to wrap this class with any writer class for writing data to a file.

Let's use the BufferedWriter class in Java program that writes to a file.

### Example

[](https://www.tpointtech.com/how-to-write-to-a-file-in-java#)[](https://www.tpointtech.com/how-to-write-to-a-file-in-java#)[](https://www.tpointtech.com/how-to-write-to-a-file-in-java#)

1. import java.io.BufferedReader;  
2. import java.io.BufferedWriter;  
3. import java.io.FileWriter;  
4. import java.io.IOException;  
5. import java.io.InputStreamReader;  
6. import java.util.*;  
7. public class Main  
8. {  
9.     public static void main(String[] args)  
10.     {  
11.         // Assigning the file content  
12.         String txt = "Welcome to TpointTech\nHello World!\n WELCOME";  
13.         try {  
14.             BufferedReader buffread = new BufferedReader(new InputStreamReader(System.in));  
15.             System.out.print("Enter the Path : ");  
16.             // Reading the File name  
17.             String path = buffread.readLine();  
18.             // Create a BufferedWriter object  
19.             BufferedWriter file_writer = new BufferedWriter(new FileWriter(path));  
20.             // Write the text(content) to the file  
21.             file_writer.write(txt);  
22.             // displaying the content that is there in file  
23.             System.out.print(txt);  
24.             // Close the BufferedWriter object  
25.             file_writer.close();  
26.         }  
27.         // Catch block to handle if exceptions occurs  
28.         catch (IOException ex) {  
29.             System.out.print(ex.getMessage());  
30.         }  
31.     }  
32. }  

**Output:**

![How to Write to a File in Java](https://images.tpointtech.com/core/images/how-to-write-to-a-file-in-java3.png)

### 4. Using FileOutputStream Class

A file output stream is an output stream for writing data to a File or to a FileDescriptor. Java FileOutputStream class belongs to java.io package. FileOutputStream is meant for writing streams of raw bytes such as binary data or image data. For writing streams of characters, use FileWriter class.

Let's sue the FileOutputStream clas in a Java program that writes to a file.

### Example

[](https://www.tpointtech.com/how-to-write-to-a-file-in-java#)[](https://www.tpointtech.com/how-to-write-to-a-file-in-java#)[](https://www.tpointtech.com/how-to-write-to-a-file-in-java#)

1. import java.io.FileOutputStream;  
2. import java.io.IOException;  
3. import java.util.*;  
4. public class Main  
5. {  
6.     public static void main(String[] args)  
7.     {  
8.         // Assign the file content  
9.         String fileContent = "Welcome to TechTpoint\nHello World!\n WELCOME";  
10.         FileOutputStream output = null;  
11.         try {  
12.             // Create an object of FileOutputStream  
13.             output = new FileOutputStream("test.txt");  
14.             // Store byte content from string  
15.             byte[] strToBytes = fileContent.getBytes();  
16.             // Write into the file  
17.             output.write(strToBytes);  
18.             System.out.print("File is created successfully with the content.");  
19.         }  
20.         catch (IOException ex) {  
21.             System.out.print(ex.getMessage());  
22.         }  
23.         finally {  
24.             // Close the object  
25.             if (output != null) {  
26.                 // Note: Second try catch block ensures that  
27.                 // the file is closed even if an error  
28.                 // occurs  
29.                 try {  
30.                     // Closing the file connections  
31.                     // if no exception has occurred  
32.                     output.close();  
33.                 }  
34.                 catch (IOException ex) {  
35.                     System.out.print(ex.getMessage());  
36.                 }  
37.             }  
38.         }  
39.     }  
40. }  

**Output:**

![How to Write to a File in Java](https://images.tpointtech.com/core/images/how-to-write-to-a-file-in-java4.png)