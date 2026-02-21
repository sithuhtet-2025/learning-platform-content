The [Java](https://www.tpointtech.com/java-tutorial) comments are the statements in a program that are not executed by the compiler and interpreter.

## Why do we use comments in a code?

- Comments are used to make the program more readable by adding the details of the code.
- It makes easy to maintain the code and to find the errors easily.
- The comments can be used to provide information or explanation about the [variable](https://www.tpointtech.com/java-variables), method, [class](https://www.tpointtech.com/object-and-class-in-java), or any statement.
- It can also be used to prevent the execution of program code while testing the alternative code.

## Types of Java Comments

There are three types of comments in Java.

1. Single Line Comment
2. Multi Line Comment
3. Documentation Comment

![Java Types of Comments](https://images.tpointtech.com/images/java-types-of-comments.png)

## 1) Java Single Line Comment

The single-line comment is used to comment only one line of the code. It is the widely used and easiest way of commenting the statements.

Single line comments starts with two forward slashes **(//)**. Any text in front of // is not executed by Java.

### Syntax

It has the following syntax:

[](https://www.tpointtech.com/java-comments#)[](https://www.tpointtech.com/java-comments#)[](https://www.tpointtech.com/java-comments#)

1. //This is single line comment  

### Example

The following example shows **single-line comments** in Java. Comments starting with // are ignored by the compiler. The program prints 10.

[](https://www.tpointtech.com/java-comments#)[](https://www.tpointtech.com/java-comments#)[](https://www.tpointtech.com/java-comments#)

1. public class CommentExample1 {    
2. public static void main(String[] args) {    
3. int i=10; // i is a variable with value 10  
4. System.out.println(i);  //printing the variable i  
5. }    
6. }    

**Output:**

10

## 2) Java Multi Line Comment

The multi-line comment is used to comment multiple lines of code. It can be used to explain a complex code snippet or to comment multiple lines of code at a time (as it will be difficult to use single-line comments there).

Multi-line comments are placed between /* and */. Any text between /* and */ is not executed by Java.

### Syntax

It has the following syntax:

[](https://www.tpointtech.com/java-comments#)[](https://www.tpointtech.com/java-comments#)[](https://www.tpointtech.com/java-comments#)

1. /*  
2. This   
3. is   
4. multi line   
5. comment  
6. */    

### Example

The following example shows **multi-line comments** in Java. Comments enclosed between /* and */ are ignored by the compiler. The program prints 10 and skips the commented code.

[](https://www.tpointtech.com/java-comments#)[](https://www.tpointtech.com/java-comments#)[](https://www.tpointtech.com/java-comments#)

1. public class CommentExample2 {    
2. public static void main(String[] args) {    
3. /* Let's declare and  
4.  print variable in java. */    
5.   int i=10;    
6.     System.out.println(i);    
7. /* float j = 5.9; 
8.     float k = 4.4; 
9.     System.out.println( j + k ); */    
10. }    
11. }    

**Output:**

10

#### Note: Usually // is used for short comments and /* */ is used for longer comments.

## 3) Java Documentation Comment

Documentation comments are usually used to write large programs for a project or software application as it helps to create documentation API. These APIs are needed for reference, i.e., which classes, methods, arguments, etc., are used in the code.

To create documentation API, we need to use the [**javadoc tool**](https://www.tpointtech.com/creating-api-document). The documentation comments are placed between /** and */.

### Syntax

It has the following syntax:

[](https://www.tpointtech.com/java-comments#)[](https://www.tpointtech.com/java-comments#)[](https://www.tpointtech.com/java-comments#)

1. /**  
2. * 
3. *We can use various tags to depict the parameter 
4. *or heading or author name 
5. *We can also use HTML tags   
6. * 
7. */    

### Example

The following example demonstrates the use of a **Java documentation comment**. The comment starts with /** and ends with */ and is used to describe the class and its functionality.

[](https://www.tpointtech.com/java-comments#)[](https://www.tpointtech.com/java-comments#)[](https://www.tpointtech.com/java-comments#)

1. /** 
2.  * This program prints a welcome message. 
3.  */  
4. public class DocCommentExample {  
5.     public static void main(String[] args) {  
6.         System.out.println("Welcome to Java!");  
7.     }  
8. }  

**Output:**

Welcome to Java!

## javadoc tags

Some of the commonly used tags in documentation comments:

|Tag|Syntax|Description|
|---|---|---|
|{@docRoot}|{@docRoot}|to depict relative path to root directory of generated document from any page.|
|@author|@author name - text|To add the author of the class.|
|@code|{@code text}|To show the text in code font without interpreting it as html markup or nested javadoc tag.|
|@version|@version version-text|To specify "Version" subheading and version-text when -version option is used.|
|@since|@since release|To add "Since" heading with since text to generated documentation.|
|@param|@param parameter-name description|To add a parameter with given name and description to 'Parameters' section.|
|@return|@return description|Required for every method that returns something (except void)|

Let's use the Javadoc tag in a Java program.

### Example using Javadoc tag

The following example shows **Java documentation comments** used to describe a class and its methods. These comments start with /** */ and can include tags like @author, @param, and @return.

[](https://www.tpointtech.com/java-comments#)[](https://www.tpointtech.com/java-comments#)[](https://www.tpointtech.com/java-comments#)

1. import java.io.*;  

2. /** 
3.  * <h2> Calculation of numbers </h2> 
4.  * This program implements an application 
5.  * to perform operation such as addition of numbers  
6.  * and print the result  
7.  * <p> 
8.  * <b>Note:</b> Comments make the code readable and  
9.  * easy to understand. 
10.  *  
11.  * @author Anurati  
12.  * @version 16.0 
13.  * @since 2021-07-06 
14.  */  

15.  public class Calculate{  
16.     /** 
17.      * This method calculates the summation of two integers. 
18.      * @param input1 This is the first parameter to sum() method 
19.      * @param input2 This is the second parameter to the sum() method. 
20.      * @return int This returns the addition of input1 and input2 
21.      */  
22.     public int sum(int input1, int input2){  
23.         return input1 + input2;  
24.     }  
25.     /** 
26.     * This is the main method uses of sum() method. 
27.     * @param args Unused 
28.     * @see IOException  
29.     */    
30.     public static void main(String[] args) {  
31.         Calculate obj = new Calculate();  
32.         int result = obj.sum(40, 20);  

33.         System.out.println("Addition of numbers: " + result);  
34.     }    
35.  }   

Compile it by javac tool:

Create Document

![java comments](https://images.tpointtech.com/core/images/java-comments.png)

Create documentation API by **javadoc** tool:

![java comments](https://images.tpointtech.com/core/images/java-comments2.png)

Now, the [HTML](https://www.tpointtech.com/html-tutorial) files are created for the **Calculate** class in the current directory, i.e., **abcDemo**. Open the HTML files, and we can see the explanation of Calculate class provided through the documentation comment.

## Are Java comments executable?

**Ans:** As we know, Java comments are not executed by the compiler or interpreter, however, before the lexical transformation of code in compiler, contents of the code are encoded into ASCII in order to make the processing easy.

**Test.java**

[](https://www.tpointtech.com/java-comments#)[](https://www.tpointtech.com/java-comments#)[](https://www.tpointtech.com/java-comments#)

1. public class Test{  
2.     public static void main(String[] args) {  
3.         //the below comment will be executed  
4. // \u000d System.out.println("Java comment is executed!!");  
5.     }  
6. }  

**Output:**

![java comments](https://images.tpointtech.com/core/images/java-comments3.png)

The above code generate the output because the compiler parses the Unicode character \**u000d** as a **new line** before the lexical transformation, and thus the code is transformed as shown below:

**Test.java**

[](https://www.tpointtech.com/java-comments#)[](https://www.tpointtech.com/java-comments#)[](https://www.tpointtech.com/java-comments#)

1. public class Test{  
2.     public static void main(String[] args) {  
3.         //the below comment will be executed  
4. //  
5. System.out.println("Java comment is executed!!");  
6.     }  
7. }  

Thus, the Unicode character shifts the print statement to next line and it is executed as a normal Java code.