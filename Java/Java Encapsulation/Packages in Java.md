A **Java package** is a group of similar types of classes, interfaces and sub-packages. This chapter explains how Java packages work and how they help in organizing, managing, and using classes in Java programs.

## What is Package in Java?

A Java package groups related classes, interfaces, and sub-packages into one unit. It helps organize large programs, avoid name conflicts, control access, and make code reusable and modular.

There are two types of Java Packages:

- Built-in Packages
- User-defined Packages

## Java Built-in Packages

Built-in packages are predefined packages provided by Java that contain ready-to-use classes and interfaces. Some of the built-in packages that are commonly used are:

- [**lang**](https://www.tpointtech.com/java-lang-class-class-in-java)**:**It contains those classes that are required for language support, such as classes for primitive data types and math operations. This package is automatically imported into Java.
- [**io**](https://www.tpointtech.com/java-io)**:**It contains all those classes that are required for the input/output operations.
- **util:**It contains utility classes that are needed for the data structures, such as [Array](https://www.tpointtech.com/java-arrays), [List](https://www.tpointtech.com/java-list), [Map](https://www.tpointtech.com/java-map), etc.
- [**applet**](https://www.tpointtech.com/java-applet)**:**All those classes that are required for finding applets are found in this package.
- [**awt**](https://www.tpointtech.com/java-awt)**:**It contains all those classes that are required for creating components of the GUI (Graphical User Interface).
- [**net**](https://www.tpointtech.com/java-net-package)**:**It includes classes that are used for doing tasks in the field of networking.

## Java User-defined Packages

User-defined packages are packages created by programmers to group their own classes and interfaces. They help to avoid naming conflicts, support access control, and allow developers to structure large projects in a clean and modular way.

### Example

Here, we will create two Java files in two different packages (or folders). We will also create three files. One file each for both the folders, and the last file is of the main class.

Observe the following. The two folders, mypackage1 and mypackage2, have been created.

![Packages in Java](https://images.tpointtech.com/core/images/packages-in-java2.jpg)

Inside mypackage1, create a file Class1.java.

![Packages in Java](https://images.tpointtech.com/core/images/packages-in-java3.png)

The following code is written for the Class1.java file.

[](https://www.tpointtech.com/packages-in-java#)[](https://www.tpointtech.com/packages-in-java#)[](https://www.tpointtech.com/packages-in-java#)

1. // Note that Class1 is the part of the package mypackage1. Therefore, package   
2. // mypackage1; statement is written.  
3. package mypackage1;  
4. public class Class1 {  
5.     public void get1() {  
6.         System.out.println("Inside the package 1.");  
7.     }  
8. }  

Similarly, create Class2.java file inside mypackage2

![Packages in Java](https://images.tpointtech.com/core/images/packages-in-java4.png)

The following code is written for the Class2.java file.

[](https://www.tpointtech.com/packages-in-java#)[](https://www.tpointtech.com/packages-in-java#)[](https://www.tpointtech.com/packages-in-java#)

1. // Note that Class2 is the part of the package mypackage2. Therefore, package   
2. // mypackage2; statement is written.  
3. package mypackage2;  
4. public class Class2 {  
5.     public void get2() {  
6.         System.out.println("Inside the package 2.");  
7.     }  
8. }  

Now, outside of both packages, create the Main.java file.

![Packages in Java](https://images.tpointtech.com/core/images/packages-in-java5.png)

The following code is written for the Main.java file.

### Example

[](https://www.tpointtech.com/packages-in-java#)[](https://www.tpointtech.com/packages-in-java#)[](https://www.tpointtech.com/packages-in-java#)

1. // importing both the classes  
2. import mypackage1.Class1;  
3. import mypackage2.Class2;  
4. public class Main {  
5.     // main method  
6.     public static void main(String args[])  
7.     {  
8.          // instantiating both the classes Class1 and Class2  
9.         Class1 obj1 = new Class1();  
10.         Class2 obj2 = new Class2();  
11.         obj1.get1();  
12.         obj2.get2();  
13.     }  
14. }  

**Output:**

Inside the package 1.
Inside the package 2.

#### Note: If we change the access specifier of the classes Class1 and Class2 from public to protected, default, or private, then the compiler will give an error. Observe the following.

Save this file as Class1.java

[](https://www.tpointtech.com/packages-in-java#)[](https://www.tpointtech.com/packages-in-java#)[](https://www.tpointtech.com/packages-in-java#)

1. package mypackage1;  
2. // public class Class1 {  
3. protected class Class1 { // changed the access specifier to protected  
4.     public void get1() {  
5.         System.out.println("Inside the package 1.");  
6.     }  
7. }  

Save this file as Class2.java

[](https://www.tpointtech.com/packages-in-java#)[](https://www.tpointtech.com/packages-in-java#)[](https://www.tpointtech.com/packages-in-java#)

1. package mypackage2;  
2. // public class Class2 {  
3. class Class2 { // changed the access specifier to default  
4.     public void get2() {  
5.         System.out.println("Inside the package 2.");  
6.     }  
7. }  

Now, when we run the Main.java file, the following error is observed.

.\mypackage1\Class1.java:3: error: modifier protected not allowed here
protected class Class1 { // changed the access specifier to protected
^
Main.java:2: error: Class1 is not public in mypackage1; cannot be accessed from outside package
import mypackage1.Class1;
^
Main.java:4: error: Class2 is not public in mypackage2; cannot be accessed from outside package
import myPackage2.Class2;
^
Main.java:11: error: Class1 is not public in mypackage1; cannot be accessed from outside package
Class1 obj1 = new Class1();
^
Main.java:11: error: Class1 is not public in mypackage1; cannot be accessed from outside package
Class1 obj1 = new Class1();
^
Main.java:13: error: Class2 is not public in mypackage2; cannot be accessed from outside package
Class2 obj2 = new Class2();
^
Main.java:13: error: Class2 is not public in mypackage2; cannot be accessed from outside package
Class2 obj2 = new Class2();

**Explanation**

The error is coming because protected and default access specifiers restrict the visibility of the classes outside the package. Therefore, the main class cannot access Class1 and Class2.

#### Note: In this example, we have created the folders mypackage1 and mypackage2 explicitly. If we want to build it using the command prompt, then do the following.

First, put all three files (Class1.java, Class2.java, Main.java) in one location (in my case location is the test folder).

![Packages in Java](https://images.tpointtech.com/core/images/packages-in-java6.png)

Ensure that the access specifier of Class1 and Class2 is public in this case. Now, compile it using the following command.

[](https://www.tpointtech.com/packages-in-java#)[](https://www.tpointtech.com/packages-in-java#)[](https://www.tpointtech.com/packages-in-java#)

1. javac -d . *.java  

Here, -d is for the destination. After -d, we see a dot(.), which means in the current directory, and *.java means all the Java files.

After doing the compilation work, we see the following.

![Packages in Java](https://images.tpointtech.com/core/images/packages-in-java7.png)

We see that both the packages have been created. Now, run the Main.class file using the command

[](https://www.tpointtech.com/packages-in-java#)[](https://www.tpointtech.com/packages-in-java#)[](https://www.tpointtech.com/packages-in-java#)

1. java Main  

And we get the output as:

Inside the package 1.
Inside the package 2.

## Static Import of the Packages

The static import feature was first introduced in Java version 5 and is still present in later versions of Java. [Static import](https://www.tpointtech.com/java-static-import) allows **only public static members** (methods or fields) of a class to be used in the code without specifying the name of the class in which it is defined.

The following example demonstrate the static import of the packages in Java.

### Example

[](https://www.tpointtech.com/packages-in-java#)[](https://www.tpointtech.com/packages-in-java#)[](https://www.tpointtech.com/packages-in-java#)

1. import static java.lang.System.*; // notice the word static in the import statement  
2. public class Main {  
3.     public static void main(String args[]) {  
4.         // no need to write System.out.println  
5.         // only out.println will do the work  
6.         out.println("In the main method");  
7.     }  
8. }  

**Output:**

In the main method

**Explanation:**

"System" is a class present in the java.lang package, and out is a static variable present in the System class. By using static import, we are able to access the out variable without using the class name "System".

## Dealing With Name Conflicts Using Packages

As discussed earlier, name conflicts can be handled using packages. Let's see an example to understand it.

### Example

[](https://www.tpointtech.com/packages-in-java#)[](https://www.tpointtech.com/packages-in-java#)[](https://www.tpointtech.com/packages-in-java#)

1. import java.sql.*;  
2. import java.util.*;  
3. public class Main {  
4.     public static void main(String args[]) {  
5.        // creating an object of the class Date  
6.        Date d = new Date(44l);  
7.        System.out.println("Inside main method.");  
8.     }  
9. }  

**Output:**

Main.java:7: error: reference to Date is ambiguous
Date d = new Date(44l);
^
both class java.util.Date in java.util and class java.sql.Date in java.sql match
Main.java:7: error: reference to Date is ambiguous
Date d = new Date(44l);
^
both class java.util.Date in java.util and class java.sql.Date in java.sql match
2 errors

**Explanation**

In the program, java.sql and java.util packages have been imported. Each package contains the Date class. When the Date class is instantiated, the compiler does not know which Date class it should refer to, whether the compiler should refer to the Date class of the java.sql package or the Date class of java.util package. It leads to ambiguity. Therefore, the error has come.

To solve this error, we have to use the class name along with the package name. The fully qualified name clearly tells the compiler which Date class it should refer to.

### Example

[](https://www.tpointtech.com/packages-in-java#)[](https://www.tpointtech.com/packages-in-java#)[](https://www.tpointtech.com/packages-in-java#)

1. import java.sql.*;  
2. import java.util.*;  
3. public class Main {  
4.     public static void main(String args[]) {  
5.        // Date class comes with the java.sql package name. It indicates that  
6.        // Date class used here belongs to the java.sql package. Hence, there is no any   
7.        // ambiguity. Therefore, no error has occurred.          
8.        // creating an object of the class Date  
9.        java.sql.Date d = new java.sql.Date(44l);  
10.        System.out.println("Inside main method.");  
11.     }  
12. }  

**Output:**

Inside the main method.

## Java Subpackage

A package inside a package is called a **subpackage**. It should be created **to categorize the package further**.

Let's take an example, Sun Microsystems has defined a package named java that contains many classes like [System](https://www.tpointtech.com/java-system), [String](https://www.tpointtech.com/java-string), [Reader](https://www.tpointtech.com/java-reader-class), [Writer](https://www.tpointtech.com/java-writer-class), [Socket](https://www.tpointtech.com/java-socket-class), etc. These classes represent a particular group. For example, Reader and Writer classes are for Input/Output operations, [Socket and ServerSocket classes](https://www.tpointtech.com/difference-between-socket-and-server-socket-in-java) are for networking, etc. and so on.

So, Sun has subcategorized the Java package into subpackages such as lang, net, io, etc. and put the Input/Output related classes in the io package, Server and ServerSocket classes in the net package and so on.

The standard for defining a package is domain.company.package for examlle com.tpointtech.bean or org.sssit.dao.

The following example demonstrate the working of Subpackages in Java.

### Example

[](https://www.tpointtech.com/packages-in-java#)[](https://www.tpointtech.com/packages-in-java#)[](https://www.tpointtech.com/packages-in-java#)

1. package com.tpointtech.core;    
2. class Main {    
3.   public static void main(String args[]){    
4.    System.out.println("Hello subpackage");    
5.   }    
6. }    

**To Compile:** javac -d . Main.java

**To Run:** java com.tpointtech.core.Main

**Output:**

Hello subpackage

## Advantages of Using Packages

Several advantages of packages in Java are as follows:

### 1. Avoid Naming Conflicts

Packages are used to avoid naming conflicts among class names.

Suppose there is a class called Employee. We know that employees are in the HR as well as the IT department of a company. So, the question is, if we write Employee, then it is of which department? Here, packages come into the picture, and we can write Employee as the fully qualified name for both the department and _company.hr.Employee_ and _company.it.Employee_. Thus, the naming conflict is avoided.

### 2. Organize Classes

For organizing the class, interfaces and other components, packages are used.

Think of a library. There are different shelves for the various kinds of books. Maths books are stored in one place. Science books are stored in another place, etc. Similarly, we can also group similar types of classes in one place. Packages help in doing so. In [Java](https://www.tpointtech.com/java-tutorial), built-in classes are also organized using packages. Observe the following diagram.

![Packages in Java](https://images.tpointtech.com/core/images/packages-in-java.png)

- **Control Access:** It is the package that controls the access of the protected and default members. Think what would be the use of default and protected access specifiers if packages were absent?
- **Reusability:** Java enhances the reusability management of code and does the promotion of data encapsulation with the help of packages.

## Package Structure and Naming Rules

Here, we are going to discuss the package structure and naming rules in Java.

### 1. Naming Conventions

Java packages should be in lowercase, and the dot should separate the components (.). If the component is a class, then the first letter of the class name should be capitalized.

To read more [Java Naming Conventions](https://www.tpointtech.com/java-naming-conventions)

### 2. Structure of Directory

The names of the directories and the package names are closely related.

For example, if the package name is _company.hr.Employee_, then the company is the directory, and inside it, there is another directory called hr, and inside it, there is a class called Employee. Notice that E is in capital, indicating that it is a class name.

**Example:**

[](https://www.tpointtech.com/packages-in-java#)[](https://www.tpointtech.com/packages-in-java#)[](https://www.tpointtech.com/packages-in-java#)

1. import java.lang.*;  

Here, _lang_ is a subpackage inside the package _java_.

## Accessing Classes from Package

Here, we are going to discuss how we can access class from packages in Java.

### Importing a Specific Class

We can access classes of a package using the import keyword. For example, if we want to access a specific class of the _java.util_ package, then use the following statement:

[](https://www.tpointtech.com/packages-in-java#)[](https://www.tpointtech.com/packages-in-java#)[](https://www.tpointtech.com/packages-in-java#)

1. import java.util.ArrayList;  

Here, we are accessing a specific class called [ArrayList](https://www.tpointtech.com/java-arraylist) of the package _java.util_. Similarly, if we want to include another class of the different package, we can write

[](https://www.tpointtech.com/packages-in-java#)[](https://www.tpointtech.com/packages-in-java#)[](https://www.tpointtech.com/packages-in-java#)

1. import java.math.BigInteger;  

Here, we have imported BigInteger class of the _java.math_ package.

### Importing All Classes

If we want to use a class without using the import statement, then we have to write the following.

### Example

[](https://www.tpointtech.com/packages-in-java#)[](https://www.tpointtech.com/packages-in-java#)[](https://www.tpointtech.com/packages-in-java#)

1. public class Main {  
2.     static void foo() {  
3.                          // we are writing the class name along with the package name  
4.         java.util.ArrayList<Integer> al = new java.util.ArrayList<Integer>();  
5.     }  
6. public static void main(String args[]) {  
7.       foo();  
8.       System.out.println("Inside the main method");  
9. }  
10. }  

**Output:**

Inside the main method

#### Note: By applying the import package.*; statement, we know that it imports all the classes and interfaces present in that package. However, all the classes, interfaces, etc., will never be imported from their sub-packages.

Whenever we have two packages having classes of the same name (for example, _java.sql.Date_ and _java.util.Date_), it is suggested to use the fully qualified names to avoid name conflicts. We will see this later in this tutorial.