A zip file is a type of compressed file that makes it possible to store several files inside of one file, making it the best option for storing big data. To read and print the contents of a zip file using Java, you can use the java.util.zip package, which provides classes for reading and writing zip files.

The ZipEntry class is used to mark the zip file and its contents, while the ZipFile class is used to read the contents of the zip file. In the code, we create a ZipFile object for the zip file we want to read and then get a list of entries in the zip file using the entries() method.

We then loop through each entry in the zip file and print its Name using the getName() method. To read the contents of each entry, we get an input stream for the entry using the getInputStream() method. We then create a buffer to hold the input stream data and read the data into the buffer using a loop. Finally, we convert the buffer data to a string and print it.

If the zip file is not found, the code will throw an IOException with the message "File not found" which can be handled using a try-catch block.

## Approach: Reading and Printing All Files from a Zip File

Considering a system that stores a zip file named Reference.zip. It creates objects of these classes and initializes them to null. Then, it opens a file input stream to read the zip file and a buffered input stream to read its contents. The while loop is used to read and print the zip file names until the very last line.

### Algorithm:

1. Initialize FileInputStream, ZipInputStream, and ZipEntry object to null.
2. Allow the user to provide the zip file's location while reading the input.  
    ![Read and Print All Files From a Zip File in Java](https://images.tpointtech.com/core/images/read-and-print-all-files-from-a-zip-file-in-java.png)
3. Open a FileInputStream and enter the zip file's path(C:\\Users\\maddu\\OneDrive\\Desktop\\Watcher\\Reference.zip).  
    ![Read and Print All Files From a Zip File in Java](https://images.tpointtech.com/core/images/read-and-print-all-files-from-a-zip-file-in-java2.png)
4. Create a BufferedInputStream to read the zip file's contents.
5. Construct a ZipInputStream so that you can read zip file entries and output their names while using a while loop.
6. Handle exceptions during file handling and close the ZipInputStream and BufferedInputStream.

### Implementation:

**Filename:** ReadFile.java

[](https://www.tpointtech.com/read-and-print-all-files-from-a-zip-file-in-java#)[](https://www.tpointtech.com/read-and-print-all-files-from-a-zip-file-in-java#)[](https://www.tpointtech.com/read-and-print-all-files-from-a-zip-file-in-java#)

1. import java.io.BufferedInputStream;  
2. import java.io.FileInputStream;  
3. import java.io.FileNotFoundException;  
4. import java.io.IOException;  
5. import java.util.zip.ZipEntry;  
6. import java.util.zip.ZipInputStream;  

7. public class ReadFile {  

8.   // The method reads and prints the content of the zip file  
9.   public void printFileContent(String filePath) {  
10.     FileInputStream fs = null;  
11.     ZipInputStream Zs = null;  
12.     ZipEntry ze = null;  

13.     try {  
14.       // Display a message when program compiles successfully  
15.       System.out.println("Files in the zip are as follows: ");  

16.       // Open a file input stream to read the zip file  
17.       fs = new FileInputStream(filePath);  
18.       // Create a buffered input stream to read the contents of the zip file  
19.       Zs = new ZipInputStream(new BufferedInputStream(fs));  

20.       // Loop to read and print the zip file name till the end  
21.       while ((ze = Zs.getNextEntry()) != null) {  
22.         System.out.println(ze.getName());  
23.       }  

24.       // Close the file connection  
25.       Zs.close();  
26.     } catch (FileNotFoundException fe) {  
27.       // Catch block to handle if zip file is not found  
28.       fe.printStackTrace();  
29.     } catch (IOException ie) {  
30.       // Catch block to handle any generic IO exception  
31.       ie.printStackTrace();  
32.     }  
33.   }  

34.   public static void main(String[] args) {  
35.     // Enter the path of the zip file here  
36.     String filePath = "C:\\Users\\maddu\\OneDrive\\Desktop\\Watcher\\Reference.zip";  

37.     // Create an object of the ReadFile class  
38.     ReadFile zf = new ReadFile();  

39.     // Call the printFileContent method to read and print the zip file content  
40.     zf.printFileContent(filePath);  
41.   }  
42. }  

**Output:**

Files in the zip are as follows:
Bad Operand Types Error in Java.docx
Chained Exceptions in Java.docx
ConcurrentSkipListSet in Java.docx
Final static variable in Java.docx
Image1.jpg
Image2.jpg
Image3.jpg
Minimum number of subsets with distinct elements.docx
Separators In Java.docx