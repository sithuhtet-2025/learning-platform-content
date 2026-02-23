In Java, working with **zip** file is not the same as working with word file or text file. In the context of zip file Java provides different ways to create **zip** or **compressed** or **archive** file. In this section, we will learn **how to create zip file in Java**.

The necessary classes and interfaces that are required to create a zip file are defined in **java.util.zip** package. The package does not only provide classes for ZIP format but also provides classes for the **GZIP** format. The package also provides the classes to read from and write to the zip file.

![How to Create Zip File in Java](https://images.tpointtech.com/core/images/how-to-create-zip-file-in-java.png)

## Using java.util.Zip Package

Before creating the Java program, first we need to [download the apache common compress JAR file](https://repo1.maven.org/maven2/org/apache/commons/commons-compress/1.20/commons-compress-1.20.jar). Now create a Java project and add this JAR file to the project. Copy the following Java program and paste it in the class file that you have created.

**CreateZipFile1.java**

[](https://www.tpointtech.com/how-to-create-zip-file-in-java#)[](https://www.tpointtech.com/how-to-create-zip-file-in-java#)[](https://www.tpointtech.com/how-to-create-zip-file-in-java#)

1. import java.io.BufferedInputStream;  
2. import java.io.File;  
3. import java.io.FileInputStream;  
4. import java.io.FileOutputStream;  
5. import java.io.IOException;  
6. import java.util.zip.ZipEntry;  
7. import java.util.zip.ZipOutputStream;  
8. public class CreateZipFile1  
9. {  
10.   static final int BUFFER = 1024;  
11.   public static void main(String args[])   
12.   {  
13. //constructor of the ZipFile  
14.    zipFile();  
15.   }  
16.   //method that create zip file  
17.   private static void zipFile()  
18.   {  
19.     ZipOutputStream zos = null;  
20.     BufferedInputStream bis = null;  
21.     try  
22.     {  
23.       //path of the file that we want to compress  
24.       String fileName = "C:\\Users\\Anubhav\\Desktop\\file1.txt";  
25.       File file = new File(fileName);  
26.       FileInputStream fis = new FileInputStream(file);  
27.       bis = new BufferedInputStream(fis, BUFFER);        
28.       //creating ZipOutputStream  
29.       //creates a zip file with the specified name  
30.       FileOutputStream fos = new FileOutputStream("C:\\Users\\Anubhav\\Desktop\\demo.zip");  
31. //ZipOutputStream writes data to an output stream in zip format  
32.       zos = new ZipOutputStream(fos);                       
33.       // ZipEntry, here file name can be created using the source file  
34.       ZipEntry ze = new ZipEntry(file.getName());  
35.       //putting zipentry in zipoutputstream  
36.       zos.putNextEntry(ze);  
37.       byte data[] = new byte[BUFFER];  
38.       int count;  
39.       while((count = bis.read(data, 0, BUFFER)) != -1)   
40.       {  
41.         zos.write(data, 0, count);  
42.       }  
43.     }  
44.     catch(IOException ioExp)  
45.     {  
46.       System.out.println("Error while zipping " + ioExp.getMessage());  
47.     }  
48.     finally  
49.     {  
50.       if(zos != null)  
51.       {  
52.         try   
53.         {  
54.             //closing output stream  
55.           zos.close();  
56.         }   
57.         catch (IOException e)   
58.         {  
59.           e.printStackTrace();  
60.         }  
61.       }  
62.       if(bis != null)  
63.       {  
64.         try   
65.         {  
66.             //closing buffered input stream  
67.           bis.close();  
68.         }   
69.         catch (IOException e)   
70.         {  
71.         //prints exception  
72.           e.printStackTrace();  
73.         }  
74.       }  
75.     }  
76.   }  
77. }  

Let's compile and run the above program.

**Output:**

![How to Create Zip File in Java](https://images.tpointtech.com/core/images/how-to-create-zip-file-in-java2.png)

We observe that a zip file with the specified name is created. Let's open the zip file and see the specified file added to zip file or not.

![How to Create Zip File in Java](https://images.tpointtech.com/core/images/how-to-create-zip-file-in-java3.png)

## Zipping Multiple Files

**ZippingMultipleFiles.java**

[](https://www.tpointtech.com/how-to-create-zip-file-in-java#)[](https://www.tpointtech.com/how-to-create-zip-file-in-java#)[](https://www.tpointtech.com/how-to-create-zip-file-in-java#)

1. import java.io.BufferedInputStream;  
2. import java.io.File;  
3. import java.io.FileInputStream;  
4. import java.io.FileOutputStream;  
5. import java.io.IOException;  
6. import java.util.zip.ZipEntry;  
7. import java.util.zip.ZipOutputStream;  
8. public class ZippingMultipleFiles   
9. {  
10.   public static void main(String[] args)   
11.   {  
12.     try   
13.     {  
14.       //Source files  
15.     String fileName1 = "C:\\Users\\Anubhav\\Desktop\\file1.txt";  
16.       String fileName2 = "C:\\Users\\Anubhav\\Desktop\\file2.txt";  
17.       //Zipped file  
18.       String zipFilename = "C:\\Users\\Anubhav\\Desktop\\Allfiles.zip";  
19.       File zipFile = new File(zipFilename);  
20.       FileOutputStream fos  = new FileOutputStream(zipFile);              
21.       ZipOutputStream zos = new ZipOutputStream(fos);  
22.       zipFile(fileName1, zos);  
23.       zipFile(fileName2, zos);  
24.       zos.close();  
25.     }   
26.     catch (IOException e)   
27.     {  
28.       e.printStackTrace();  
29.     }  
30.   }  
31.   // Method to zip file  
32.   private static void zipFile(String fileName, ZipOutputStream zos) throws IOException  
33.   {  
34.     final int BUFFER = 1024;  
35.     BufferedInputStream bis = null;  
36.     try  
37.     {  
38.       File file = new File(fileName);  
39.       FileInputStream fis = new FileInputStream(file);  
40.       bis = new BufferedInputStream(fis, BUFFER);            

41.       // ZipEntry --- Here file name can be created using the source file  
42.       ZipEntry zipEntry = new ZipEntry(file.getName());          
43.       zos.putNextEntry(zipEntry);  
44.       byte data[] = new byte[BUFFER];  
45.       int count;  
46.       while((count = bis.read(data, 0, BUFFER)) != -1)   
47.       {  
48.         zos.write(data, 0, count);  
49.       }    
50.       // close entry every time  
51.       zos.closeEntry();  
52.     }   
53.     finally  
54.     {  
55.       try   
56.       {  
57.         bis.close();  
58.       }   
59.       catch (IOException e)   
60.       {  
61.         e.printStackTrace();  
62.       }    
63.     }  
64.   }  
65. }  

**Output:**

![How to Create Zip File in Java](https://images.tpointtech.com/core/images/how-to-create-zip-file-in-java4.png)

## Zipping a Directory

Create a zip of a directory is a bit different form the above approach. Java provides two way to zip a directory:

- Use Files.walkFileTree() Method
- Read all files from the folder and add that files to list, then perform compression.

### Using Files.walkFileTree()

- The method walkFileTree() is presented since Java 7. It is defined in the Files class that resides in the **nio.file** package. It is used to reclusively zip the file. It makes code short and simple. The method walks over a file tree.

**Syntax:**

[](https://www.tpointtech.com/how-to-create-zip-file-in-java#)[](https://www.tpointtech.com/how-to-create-zip-file-in-java#)[](https://www.tpointtech.com/how-to-create-zip-file-in-java#)

1. public static Path walkFileTree(Path start, FileVisitor<? super Path> visitor) throws IOException  

It accepts two parameters:

**start:** It denotes the starting file.

**visitor:** Th file visitor to invoke each file.

The **FileVisitor** is an interface that acts as an argument for the method. To walk over a file tree, we need to implement a FileVisitor interface. It specifies the required behavior at key points in the traversal process that are:

- When a file is visited
- Before a directory is accessed
- After a directory is accessed
- When a failure occurs

Let's implement the logic to create a zip file for a directory.

**ZippingDirectory.java**

[](https://www.tpointtech.com/how-to-create-zip-file-in-java#)[](https://www.tpointtech.com/how-to-create-zip-file-in-java#)[](https://www.tpointtech.com/how-to-create-zip-file-in-java#)

1. import java.io.BufferedInputStream;  
2. import java.io.File;  
3. import java.io.FileInputStream;  
4. import java.io.FileOutputStream;  
5. import java.io.IOException;  
6. import java.util.ArrayList;  
7. import java.util.List;  
8. import java.util.zip.ZipEntry;  
9. import java.util.zip.ZipOutputStream;  
10. public class ZippingDirectory   
11. {  
12.   static final int BUFFER = 1024;  
13.   // Source folder which has to be zipped  
14.   static final String FOLDER = "C:\\Users\\Anubhav\\Desktop\\demo folder";  
15.   List<File> fileList = new ArrayList<File>();  
16.   public static void main(String[] args)   
17.   {      
18.     ZippingDirectory zf = new ZippingDirectory();  
19.     // get list of files  
20.     List<File> fileList = zf.getFileList(new File(FOLDER));  
21.     //go through the list of files and zip them   
22.     zf.zipFiles(fileList);      
23.   }  

24.   private void zipFiles(List<File> fileList)  
25.   {  
26.     try  
27.     {  
28.       // Creating ZipOutputStream - Using input name to create output name  
29.       FileOutputStream fos = new FileOutputStream(FOLDER.concat(".zip"));  
30.       ZipOutputStream zos = new ZipOutputStream(fos);  
31.       // looping through all the files  
32.       for(File file : fileList)  
33.       {  
34.         // To handle empty directory  
35.         if(file.isDirectory())  
36.         {  
37.           // ZipEntry --- Here file name can be created using the source file  
38.           ZipEntry ze = new ZipEntry(getFileName(file.toString())+"/");  
39.           // Putting zipentry in zipoutputstream  
40.           zos.putNextEntry(ze);  
41.           zos.closeEntry();  
42.         }  
43.         else  
44.         {  
45.           FileInputStream fis = new FileInputStream(file);  
46.           BufferedInputStream bis = new BufferedInputStream(fis, BUFFER);  
47.           // ZipEntry --- Here file name can be created using the source file  
48.           ZipEntry ze = new ZipEntry(getFileName(file.toString()));  
49.           // Putting zipentry in zipoutputstream  
50.           zos.putNextEntry(ze);  
51.           byte data[] = new byte[BUFFER];  
52.           int count;  
53.           while((count = bis.read(data, 0, BUFFER)) != -1)   
54.           {  
55.               zos.write(data, 0, count);  
56.           }  
57.           bis.close();  
58.           zos.closeEntry();  
59.         }                 
60.       }                  
61.       zos.close();      
62.     }  
63.     catch(IOException ioExp)  
64.     {  
65.       System.out.println("Error while zipping " + ioExp.getMessage());  
66.       ioExp.printStackTrace();  
67.     }  
68.   }  

69.  //the method returns a list of files  
70.   private List<File> getFileList(File source)  
71.   {        
72.     if(source.isFile())  
73.     {  
74.       fileList.add(source);  
75.     }  
76.     else if(source.isDirectory())  
77.     {  
78.       String[] subList = source.list();  
79.       // this condition checks for empty directory  
80.       if(subList.length == 0)  
81.       {  
82.         //System.out.println("path -- " + source.getAbsolutePath());  
83.         fileList.add(new File(source.getAbsolutePath()));  
84.       }  
85.       for(String child : subList)  
86.       {  
87.         getFileList(new File(source, child));  
88.       }  
89.     }  
90.     return fileList;  
91.   }  

92.   private String getFileName(String filePath)  
93.   {  
94.     String name = filePath.substring(FOLDER.length() + 1, filePath.length());  
95.     //System.out.println(" name " + name);  
96.     return name;        
97.   }  
98. }  

**Output:**

![How to Create Zip File in Java](https://images.tpointtech.com/core/images/how-to-create-zip-file-in-java5.png)