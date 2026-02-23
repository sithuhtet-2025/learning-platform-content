Java provides simple and efficient ways to read a text file line by line. In this chapter, we will learn the most commonly used methods with clear examples.

Reading a file line by line means accessing the content of a file one line at a time instead of reading the entire file at once. This approach is useful when working with large files.

There are following ways to read a file line by line in Java.

- Using BufferedReader Class
- Using Scanner Class

## Using BufferedReader Class

The [BufferedReader class](https://www.tpointtech.com/java-bufferedreader-class) is the most common and simple way to read a file line by line. It belongs to the [java.io package](https://www.tpointtech.com/java-io-package). This class provides the **readLine()** method to read text files line by line.

### Method Signature

Here is the syntax of the method:

[](https://www.tpointtech.com/how-to-read-file-line-by-line-in-java#)[](https://www.tpointtech.com/how-to-read-file-line-by-line-in-java#)[](https://www.tpointtech.com/how-to-read-file-line-by-line-in-java#)

1. public String readLine() throws IOException  

The **readLine()** method reads a single line of text and returns it as a String. It returns null when the end of the file is reached.

Here is the code to read file line by line using BufferedReader class:

[](https://www.tpointtech.com/how-to-read-file-line-by-line-in-java#)[](https://www.tpointtech.com/how-to-read-file-line-by-line-in-java#)[](https://www.tpointtech.com/how-to-read-file-line-by-line-in-java#)

1. try (BufferedReader reader = new BufferedReader(new FileReader("file.txt"))) {  
2.     String line;  
3.     while ((line = reader.readLine()) != null) {  
4.         // process each line  
5.     }  
6. } catch (IOException e) {  
7.     e.printStackTrace();  
8. }  

This approach is efficient for large files because it reduces the number of I/O operations by buffering the input.

### Example: Read File Line by Line Using BufferedReader Class

In the following example, Demo.txt is read using the BufferedReader class. The BufferedReader reads the file line by line, and each line is appended to a StringBuffer. Finally, the content is printed on the console.

[](https://www.tpointtech.com/how-to-read-file-line-by-line-in-java#)[](https://www.tpointtech.com/how-to-read-file-line-by-line-in-java#)[](https://www.tpointtech.com/how-to-read-file-line-by-line-in-java#)

1. import java.io.*;  

2. public class ReadLineByLineExample1 {  
3.     public static void main(String args[]) {  
4.         try {  
5.             File file = new File("Demo.txt");  
6.             FileReader fr = new FileReader(file);  
7.             BufferedReader br = new BufferedReader(fr);  

8.             StringBuffer sb = new StringBuffer();  
9.             String line;  

10.             while ((line = br.readLine()) != null) {  
11.                 sb.append(line);  
12.                 sb.append("\n");  
13.             }  

14.             fr.close();  

15.             System.out.println("Contents of File:");  
16.             System.out.println(sb.toString());  
17.         } catch (IOException e) {  
18.             e.printStackTrace();  
19.         }  
20.     }  
21. }  

**Output:**

![How to read file line by line in Java](https://images.tpointtech.com/core/images/how-to-read-file-line-by-line-in-java-output1.png)

## Using Scanner Class

The [Scanner class](https://www.tpointtech.com/scanner-class-in-java) provides utility methods to read input easily. It belongs to the [java.util package](https://www.tpointtech.com/java-util-date). The **nextLine()** method of the Scanner class is used to read a file line by line.

The **nextLine()** method works similar to the **readLine()** method and returns one complete line at a time.

Here is the code to read file line by line using Scanner class:

[](https://www.tpointtech.com/how-to-read-file-line-by-line-in-java#)[](https://www.tpointtech.com/how-to-read-file-line-by-line-in-java#)[](https://www.tpointtech.com/how-to-read-file-line-by-line-in-java#)

1. try (Scanner scanner = new Scanner(new File("file.txt"))) {  
2.     while (scanner.hasNextLine()) {  
3.         String line = scanner.nextLine();  
4.         // process each line  
5.     }  
6. } catch (FileNotFoundException e) {  
7.     e.printStackTrace();  
8. }  

The Scanner class is easy to use, but it may be slower than BufferedReader when working with very large files.

### Example: Read File Line by Line Using Scanner Class

In this example, the Scanner class is used to read a text file line by line using the nextLine() method and display each line on the console.

[](https://www.tpointtech.com/how-to-read-file-line-by-line-in-java#)[](https://www.tpointtech.com/how-to-read-file-line-by-line-in-java#)[](https://www.tpointtech.com/how-to-read-file-line-by-line-in-java#)

1. import java.io.*;  
2. import java.util.Scanner;  

3. public class ReadLineByLineExample2 {  
4.     public static void main(String args[]) {  
5.         try {  
6.             FileInputStream fis = new FileInputStream("Demo.txt");  
7.             Scanner sc = new Scanner(fis);  

8.             while (sc.hasNextLine()) {  
9.                 System.out.println(sc.nextLine());  
10.             }  

11.             sc.close();  
12.         } catch (IOException e) {  
13.             e.printStackTrace();  
14.         }  
15.     }  
16. }  

**Output:**

![How to read file line by line in Java](https://images.tpointtech.com/core/images/how-to-read-file-line-by-line-in-java-output2.png)