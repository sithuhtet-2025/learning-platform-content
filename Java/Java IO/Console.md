# Java Console Class

The Console class in Java is used to read input from the system console, including text and passwords.

In this chapter, we will learn what the Console class is, why it is used, its declaration, important methods, how to obtain a Console object, and how to read text and passwords using examples.

## What is Console Class in Java?

The **Console class** is used to interact with the system console, and it is used to read text input and passwords securely from the user.

When a password is read using the Console class, the characters are not displayed on the screen. The Console class is internally connected to the system console and was introduced in Java 1.5.

## Java Console class declaration

The following declaration shows how the Console class is defined in Java.

[](https://www.tpointtech.com/java-console-class#)[](https://www.tpointtech.com/java-console-class#)[](https://www.tpointtech.com/java-console-class#)

1. public final class Console extends Object implements Flushable  

## Constructor of Console Class

The Console class does not provide any public constructors.

The Console class is created internally by the Java runtime and is tightly bound to the system console. Because of this, you cannot create a Console object using the new keyword.

Instead, the Console object is obtained using the **System.console()** method.

## Getting Console Object

The System class provides a method to obtain the Console object.

[](https://www.tpointtech.com/java-console-class#)[](https://www.tpointtech.com/java-console-class#)[](https://www.tpointtech.com/java-console-class#)

1. Console c = System.console();  

> **Note:** If the program is not run from a real console (for example, inside some IDEs), this method may return null.

## Methods of Console Class

The Console class provides methods to read input and write output to the console.

|Method|Description|
|---|---|
|Reader reader()|It is used to retrieve the reader [object](https://www.tpointtech.com/object-and-class-in-java) associated with the console|
|String readLine()|It is used to read a single line of text from the console.|
|String readLine(String fmt, Object... args)|It provides a formatted prompt then reads the single line of text from the console.|
|char[] readPassword()|It is used to read password that is not being displayed on the console.|
|char[] readPassword(String fmt, Object... args)|It provides a formatted prompt then reads the password that is not being displayed on the console.|
|Console format(String fmt, Object... args)|It is used to write a formatted [string](https://www.tpointtech.com/java-string) to the console output stream.|
|Console printf(String format, Object... args)|It is used to write a string to the console output stream.|
|PrintWriter writer()|It is used to retrieve the [PrintWriter](https://www.tpointtech.com/java-printwriter-class) object associated with the console.|
|void flush()|It is used to flushes the console.|

## Examples of Java Console Class

The following examples demonstrate how to use the Console class to read user input.

### Example 1: Reading Text from Console

This example demonstrates how to read a line of text from the console using the Console class.

[](https://www.tpointtech.com/java-console-class#)[](https://www.tpointtech.com/java-console-class#)[](https://www.tpointtech.com/java-console-class#)

1. import java.io.Console;  
2. class ReadStringTest{    
3. public static void main(String args[]){    
4. Console c=System.console();    
5. System.out.println("Enter your name: ");    
6. String n=c.readLine();    
7. System.out.println("Welcome "+n);    
8. }    
9. }  

**Output:**

Enter your name: Nakul Jain
Welcome Nakul Jain

### Example 2: Reading Password from Console

This example demonstrates how to read a password from the console without displaying it on the screen.

[](https://www.tpointtech.com/java-console-class#)[](https://www.tpointtech.com/java-console-class#)[](https://www.tpointtech.com/java-console-class#)

1. import java.io.Console;  
2. class ReadPasswordTest{    
3. public static void main(String args[]){    
4. Console c=System.console();    
5. System.out.println("Enter password: ");    
6. char[] ch=c.readPassword();    
7. String pass=String.valueOf(ch);//converting char array into string    
8. System.out.println("Password is: "+pass);    
9. }    
10. }  

**Output:**

Enter password:
Password is: 123