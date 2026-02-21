In this chapter, you will learn about the **static keyword in Java**, its purpose, and how it is used with variables, methods, blocks, and nested classes to manage memory and access class-level members.

## What is the Static Keyword in Java?

The **static keyword** in [Java](https://www.tpointtech.com/java-tutorial) is used for memory management mainly. We can apply static keyword with [variables](https://www.tpointtech.com/java-variables), methods, blocks and [nested classes](https://www.tpointtech.com/java-inner-class). The static keyword belongs to the class than an instance of the class.

## Types of Static Members

The static keyword can be used with the following:

1. Variable (also known as a class variable)
2. Method (also known as a class method)
3. Block
4. Nested class

![Static in Java](https://d2jdgazzki9vjm.cloudfront.net/core/images/java-static-keyword.png)

## Uses of static Keyword

Beyond memory management, the static keyword in Java has several other uses. When it comes to variables, it means that all instances of the class share the variable and belong to the class as a whole, not just any one instance.

Static methods are available throughout the program since they can be called without first generating an instance of the class. When the class loads, static blocks are used to initialise static variables or carry out one-time operations.

Furthermore, nested static classes can be instantiated individually but are still linked to the outer class. Moreover, class names can be used to access static variables and methods directly, eliminating the need to build an object instance. This is especially helpful for constants or utility methods.

## Characteristics of static Keyword

Here are the characteristics of the static keyword:

1. **Belongs to the Class, Not the Object:** Anything marked as static is tied to the class itself, not individual objects. It means all objects share the same static variables and methods.
2. **Access Without an Object:** Since static members belong to the class, you can access them directly using the class name (ClassName.methodName()). No need to create an object.
3. **Static Methods Cannot Use Instance Variables Directly:** A static method does not know about specific objects, so it cannot directly access non-static (instance) variables or methods.
4. **Main Method is Static:** The main method in Java is static so that Java can run the program without creating an object first.
5. **Executed Once When the Class is Loaded:** A static block runs once when the class is first loaded, making it useful for initializing things like constants.
6. **Not Overridden Like Normal Methods:** Static methods do not follow typical method overriding. If a subclass defines the same static method, it's more like re-declaring it rather than overriding it.

## 1. Java Static Variable

If we declare any variable as static, it is known as a static variable.

- The static variable can be used to refer to the common property of all objects (which is not unique for each object), for example, the company name of employees, college name of students, etc.
- The static variable gets memory only once in the class area at the time of class loading.
- Static variables in Java are also initialized to default values if not explicitly initialized by the programmer. They can be accessed directly using the class name without needing to create an instance of the class.
- Static variables are shared among all instances of the class, meaning if the value of a static variable is changed in one instance, it will reflect the change in all other instances as well.

### Example of Static Variable

The following example demonstrate the static variable in Java.

[](https://www.tpointtech.com/static-keyword-in-java#)[](https://www.tpointtech.com/static-keyword-in-java#)[](https://www.tpointtech.com/static-keyword-in-java#)

1. //Java Program to demonstrate the use of static variable    
2. class Student{    
3.    int rollno;//instance variable    
4.    String name;    
5.    static String college ="ITS";//static variable    
6.    //constructor    
7.    Student(int r, String n){    
8.    rollno = r;    
9.    name = n;    
10.    }    
11.    //method to display the values    
12.    void display (){System.out.println(rollno+" "+name+" "+college);}    
13. }    
14. //Main class to show the values of objects    
15. public class Main{    
16.  public static void main(String args[]){    
17.  Student s1 = new Student(111,"Karan");    
18.  Student s2 = new Student(222,"Aryan");    
19.  //we can change the college of all objects by the single line of code    
20.  //Student.college="BBDIT";    
21.  s1.display();    
22.  s2.display();    
23.  }    
24. }  

**Output:**

111 Karan ITS
222 Aryan ITS

**Explanation:**

The usage of static variables is demonstrated in this Java program. In addition to a static variable called college, the Student class defines two instance variables: rollno and name. It has a constructor to set the instance variables' initial values and a display() function to output the rollno, name, and college values.

Two Student objects, s1 and s2, with different roll numbers and names, are created via the TestStaticVariable1 class. After that, each object's display() method is called printing its details. The college name can be modified for all objects at once by uncommenting the line Student.college="BBDIT", demonstrating how static variables are shared by all instances of a class.

![Static in Java](https://d2jdgazzki9vjm.cloudfront.net/core/images/java-static-keyword2.png)

### Example: Counter Without Using Static Variable

In this example, we have created an instance variable named count, which is incremented in the constructor. Since the instance variable gets the memory at the time of object creation, each object will have a copy of the instance variable. If it is incremented, it would not reflect other objects. So each object will have the value 1 in the count variable.

[](https://www.tpointtech.com/static-keyword-in-java#)[](https://www.tpointtech.com/static-keyword-in-java#)[](https://www.tpointtech.com/static-keyword-in-java#)

1. //Java Program to demonstrate the use of an instance variable    
2. //which get memory each time when we create an object of the class.    
3. class Counter{    
4.     int count=0;//will get memory each time when the instance is created    

5.     Counter(){    
6.         count++;//incrementing value    
7.         System.out.println(count);    
8.     }    
9. }  
10. public class Main{  
11.     public static void main(String args[]){    
12.         //Creating objects    
13.         Counter c1=new Counter();    
14.         Counter c2=new Counter();    
15.         Counter c3=new Counter();    
16.     }    
17. }    

**Output:**

1
1
1

**Explanation:**

The idea of instance variables that are specific to each object derived from a class is demonstrated by this Java program. The count variable in the Counter class is an instance variable that is allocated memory each time an object of the class is instantiated. It is initialized to zero.

Every time an object is produced, the constructor prints the current value of the count variable and increases it. Three Counter objects (c1, c2, and c3) with separate instances of the count variable are generated in the main procedure. Because of this, the count is increased independently for each object that is generated, and the output shows the count value for each object that increases successively.

### Example: Counter Using Static Variable

As we have mentioned above, a static variable will get the memory only once; if an object changes the value of the static variable, it will retain its value.

[](https://www.tpointtech.com/static-keyword-in-java#)[](https://www.tpointtech.com/static-keyword-in-java#)[](https://www.tpointtech.com/static-keyword-in-java#)

1. //Java Program to illustrate the use of static variable which    
2. //is shared with all objects.    
3. class Counter{    
4.     static int count=0;//will get memory only once and retains its value    

5.     Counter(){    
6.         count++;//incrementing value of static variable   
7.         System.out.println(count);    
8.     }    
9. }  
10. public class Main{  
11.     public static void main(String args[]){    
12.         //Creating objects    
13.         Counter c1=new Counter();    
14.         Counter c2=new Counter();    
15.         Counter c3=new Counter();    
16.     }    
17. }    

**Output:**

1
2
3

**Explanation:**

This Java program demonstrates the utilization of a static variable, which is shared among all objects created from the class. In the Counter2 class, the count variable is declared as static, ensuring it is allocated memory only once and retains its value across all instances of the class.

Each time an object of the class is created, the constructor increments the value of the static variable count and prints its current value. In the main method, three Counter2 objects (c1, c2, and c3) are instantiated, and as they share the same static variable count, its value increments sequentially across the objects, reflecting the shared nature of static variables among all instances of a class.

## 2. Java Static Method

If we apply a static keyword with any method, it is known as a static method.

- A static method belongs to the class rather than the object of a class.
- A static method can be invoked without the need for creating an instance of a class.
- A static method can access static data members and can change their value of it.

### Example of Static Method

Let us take another example to demonstrat the static method in Java.

[](https://www.tpointtech.com/static-keyword-in-java#)[](https://www.tpointtech.com/static-keyword-in-java#)[](https://www.tpointtech.com/static-keyword-in-java#)

1. //Java Program to demonstrate the use of a static method.    
2. class Student{    
3.      int rollno;    
4.      String name;    
5.      static String college = "ITS";    
6.      //static method to change the value of static variable    
7.      static void change(){    
8.         college = "BBDIT";    
9.      }    
10.      //constructor to initialize the variable    
11.      Student(int r, String n){    
12.         rollno = r;    
13.         name = n;    
14.      }    
15.      //method to display values    
16.      void display(){System.out.println(rollno+" "+name+" "+college);}    
17. }    
18. //Main class to create and display the values of object    
19. public class Main{    
20.     public static void main(String args[]){    
21.         Student.change();//calling change method    
22.         //creating objects    
23.         Student s1 = new Student(111,"Karan");    
24.         Student s2 = new Student(222,"Aryan");    
25.         Student s3 = new Student(333,"Sonoo");    
26.         //calling display method    
27.         s1.display();    
28.         s2.display();    
29.         s3.display();    
30.     }    
31. }    

**Output:**

111 Karan BBDIT
222 Aryan BBDIT
333 Sonoo BBDIT

This Java program demonstrates how to use a static method inside of a class. In addition to a static variable called college, the Student class defines two instance variables: rollno and name. To alter the value of the static variable college, it has a static function called change().

In addition, the class has a constructor for initialising instance variables and a display() method for printing the rollno, name, and college values. The main method of the TestStaticMethod class shows how to use the change() method to modify the college value.

After that, the display() method is used to create three Student objects (s1, s2, and s3) with distinct roll numbers and names, and their details are shown. This illustrates how the static method change() influences the static variable college for all instances of the class.

### Example: Performing Normal Calculations

Let's see another example of a static method that performs a normal calculation.

[](https://www.tpointtech.com/static-keyword-in-java#)[](https://www.tpointtech.com/static-keyword-in-java#)[](https://www.tpointtech.com/static-keyword-in-java#)

1. //Java Program to get the cube of a given number using the static method    

2. class Calculate{    
3.   static int cube(int x){    
4.   return x*x*x;    
5.   }    
6. }  
7. public class Main{  
8.   public static void main(String args[]){    
9.   int result=Calculate.cube(5);    
10.   System.out.println(result);    
11.   }    
12. }    

**Output:**

125

**Explanation:**

This Java program shows how to find the cube of a given number by using a static function. The static method cube(int x) in the Calculate class multiplies an integer parameter x three times to return its cube.

The same class's main method demonstrates how to use the class name Calculate to access the static method cube() directly without first having to create an instance of the class.

The cube() method is used in this example with argument 5, and the outcome is saved in the variable result before being printed to the console. This program demonstrates how easy and effective it is to use static methods for routine computations or actions that do not call for object creation.

### Restrictions for the Static Method

There are the following two main restrictions for the static method.

1. The static method cannot use non-static data members or call a non-static method directly.
2. this and super keyword cannot be used in static context.

**Example:**

[](https://www.tpointtech.com/static-keyword-in-java#)[](https://www.tpointtech.com/static-keyword-in-java#)[](https://www.tpointtech.com/static-keyword-in-java#)

1. class A{  
2.  int a=40;//non static  

3.  public static void main(String args[]){  
4.   System.out.println(a);  
5.  }  
6. }        

**Output:**

Compile Time Error

**Explanation:**

The Java code provided contains a class called A. A defined instance variable with the value 40 that is designated as non-static is present in class A. Nonetheless, an attempt is made to use System.out.println(a); to directly access the instance variable an in the class A main() method.

Because static methods in Java cannot directly access non-static variables, this will lead to a compilation problem. An instance of class A must first be generated in order to access the non-static variable inside the static main() method. The variable a can then be accessed using that instance. It would, therefore, be OK to use A obj = new A(); System.out.println(obj.a); to access an in the main method.

## 3. Java Static Block

- It is used to initialize the static data member.
- It is executed before the main() method at the time of class loading.

### Example of Static Block

Let us take an example to demonstrate the static block in Java.

[](https://www.tpointtech.com/static-keyword-in-java#)[](https://www.tpointtech.com/static-keyword-in-java#)[](https://www.tpointtech.com/static-keyword-in-java#)

1. //Java program to illustrate the use of static block  
2. public class Main{    
3.   static{System.out.println("static block is invoked");}    
4.   public static void main(String args[]){    
5.    System.out.println("main() method is invoked");    
6.   }    
7. }    

**Output:**

static block is invoked
main() method is invoked

**Explanation:**

In the given Java code, there's a class named A2. Inside this class, there's a static block, which is a block of code enclosed within curly braces and marked with the static keyword. Static blocks are executed only once when the class is loaded into memory, before the execution of the main method or the creation of any object of the class.

In this case, the static block contains the statement System.out.println("static block is invoked"), which prints the message "static block is invoked" to the console when the class A2 is loaded into memory.

Additionally, there's a main() method in the class A2 that prints "Hello main" to the console when executed. However, since the main method is the entry point of the program, it needs to be invoked explicitly, typically by the Java Virtual Machine (JVM) when executing the program.

Therefore, when you run the program, the static block is executed first, printing the message from the static block, followed by the execution of the main method, printing "Hello main" to the console.

### Using Static Block to Run a Program

Earlier, it was possible to execute a Java program using only a static block, which ran when the class was loaded. However, since JDK 1.7, a main() method is required, and a program cannot run using a static block alone.

Here, we are going to take an example to demonstrate a Java program using static block.

[](https://www.tpointtech.com/static-keyword-in-java#)[](https://www.tpointtech.com/static-keyword-in-java#)[](https://www.tpointtech.com/static-keyword-in-java#)

1. class A3{  
2.   static{  
3.   System.out.println("static block is invoked");  
4.   System.exit(0);  
5.   }  
6. }  

**Output:**

static block is invoked
Since JDK 1.7 and above, output would be:
Error: Main method not found in class A3, please define the main method as:
public static void main(String[] args)
or a JavaFX application class must extend javafx.application.Application

**Explanation:**

Class A3 in the provided Java code has a static block that uses System.exit(0); to end the program after printing "static block is invoked" to the console. Because of this, the static block runs when the class loads into memory, printing the message and stopping the program right away to stop more code from running.

## 4. Static Nested Classes

A static nested class is declared with the static keyword. It behaves like a regular top-level class but is nested for packaging convenience. Static nested classes cannot directly access non-static members of the enclosing class.

### Syntax

It has the following syntax:

[](https://www.tpointtech.com/static-keyword-in-java#)[](https://www.tpointtech.com/static-keyword-in-java#)[](https://www.tpointtech.com/static-keyword-in-java#)

1. class A{  
2.      static class B{}//static nested class  
3. }  

### Example of Nested Static Class

The following example demonstrates a nested static class representing a Library and its Book:

[](https://www.tpointtech.com/static-keyword-in-java#)[](https://www.tpointtech.com/static-keyword-in-java#)[](https://www.tpointtech.com/static-keyword-in-java#)

1. class Library {  
2.     static class Book {  
3.         void info() {  
4.             System.out.println("This is a library book");  
5.         }  
6.     }  
7. }  

8. public class Test {  
9.     public static void main(String[] args) {  
10.         Library.Book myBook = new Library.Book();  
11.         myBook.info();  
12.     }  
13. }  

**Output:**

This is a library book

> **Note:** We will learn about the nested classes later.