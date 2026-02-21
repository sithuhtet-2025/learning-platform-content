The **final keyword in Java** is used to restrict the user. It is also known as a non-access modifier. We can use the final keyword with:

1. Variable
2. Method
3. Class
4. Parameter

## 1. Java final variable

When a variable is declared as final, it is known as a final variable. Its value cannot be changed once initialized. It behaves like a constant.

### Syntax

Here is the syntax to declare a final variable:

[](https://www.tpointtech.com/final-keyword-in-java#)[](https://www.tpointtech.com/final-keyword-in-java#)[](https://www.tpointtech.com/final-keyword-in-java#)

1. final datatype VARIABLE_NAME=VALUE;  

### Example of final Variable

In the following code, the Main class has a final variable named SPEED_LIMIT. When we try to update the value of final variable SPEED_LIMIT to 400 by invoking the run() method, value does not change because final variable once initialized cannot be changed.

The following example demonstrates that a final variable cannot be modified once it is assigned a value.

[](https://www.tpointtech.com/final-keyword-in-java#)[](https://www.tpointtech.com/final-keyword-in-java#)[](https://www.tpointtech.com/final-keyword-in-java#)

1. class Main {    
2.   final int SPEED_LIMIT=90;    //final variable    
3.   void run() {    
4.    SPEED_LIMIT=400;   //we cannot change the final variable    
5.   }    
6.   public static void main(String args[]) {    
7.   Main obj=new  Main();    
8.   obj.run();    
9.   }    
10.  }  

When we compile the above code, it shows a compile-time error, as follows:

error: cannot assign a value to final variable SPEED_LIMIT

## 2. Java final Method

A method declared as final is known as a final method. Subclasses cannot override the final method.  

### Syntax:

Here is the syntax to declare a final method:

[](https://www.tpointtech.com/final-keyword-in-java#)[](https://www.tpointtech.com/final-keyword-in-java#)[](https://www.tpointtech.com/final-keyword-in-java#)

1. final void paint() {  
2. }  

### Example of final Method

The following example demonstrates that a final method cannot be overridden in a subclass.

[](https://www.tpointtech.com/final-keyword-in-java#)[](https://www.tpointtech.com/final-keyword-in-java#)[](https://www.tpointtech.com/final-keyword-in-java#)

1. class Bike {    
2.   final void run() {   //final method  
3.    System.out.println("running"); }    
4. }    
5. public class Main extends Bike {    
6.    //We cannot override the final method    
7.    void run(){System.out.println("running safely with 100kmph");  
8. }    
9.     public static void main(String args[]) {    
10.    Main obj= new Main();    
11.    obj.run();    
12.    }    
13. }    

When we compile the above code, it shows a compile-time error, as follows:

Main.java:7: error: run() in Main cannot override run() in Bike
void run(){System.out.println("running safely with 100kmph");
^
overridden method is final
1 error

## 3. Java final Class

A class declared with the final keyword is known as a final class. Note that the final class cannot be inherited.

### Syntax:

Here is the syntax to declare a final class:

[](https://www.tpointtech.com/final-keyword-in-java#)[](https://www.tpointtech.com/final-keyword-in-java#)[](https://www.tpointtech.com/final-keyword-in-java#)

1. final class Square {  
2. //statement   
3. }  

### Example of final Class

The following example demonstrates that a final class cannot be inherited by another class.

[](https://www.tpointtech.com/final-keyword-in-java#)[](https://www.tpointtech.com/final-keyword-in-java#)[](https://www.tpointtech.com/final-keyword-in-java#)

1. final class Bike {}    
2. //We cannot inherit the final class    
3. public class Main extends Bike   
4. {    
5.    void run()  
6.    {  
7.        System.out.println("running safely with 100kmph");     
8.    }    
9.      public static void main(String args[])   
10.      {    
11.        Main obj = new Main();    
12.        obj.run();    
13.    }    
14. }    

When we compile the above code, it shows a compile-time error, as follows:

Main.java:3: error: cannot inherit from final Bike
public class Main extends Bike
^
1 error

## Inheriting a Final Method

A **final method** can be inherited by a child class, but it cannot be overridden. This is useful when you want to keep method implementation remains unchanged in subclasses.

### Example

The following example demonstrates inheriting a final method:

[](https://www.tpointtech.com/final-keyword-in-java#)[](https://www.tpointtech.com/final-keyword-in-java#)[](https://www.tpointtech.com/final-keyword-in-java#)

1. class Bike {      
2.     final void run() {   
3.         System.out.println("running...");     
4.     }      
5. }      

6. public class Main extends Bike {      
7.     public static void main(String args[]) {      
8.         new Main().run();      
9.     }      
10. }  

**Output:**

running...

## Blank or Uninitialized Final Variable

A **blank final variable** is a final variable that is not initialized at the time of declaration. Once initialized, its value cannot be changed. These variables are useful when the value must be set during object creation, such as an employee’s PAN card number.

### Example

The following code snippet showing the use of blank or uninitialized final variable:

[](https://www.tpointtech.com/final-keyword-in-java#)[](https://www.tpointtech.com/final-keyword-in-java#)[](https://www.tpointtech.com/final-keyword-in-java#)

1. class Student {      
2.     int id;      
3.     String name;      
4.     final String PAN_CARD_NUMBER;      
5.     ...  
6. }   

## Initialization of a Blank Final Variable

A **blank final variable** can be initialized only inside a constructor.

### Example

The following example demonstrates the initialization of a blank final variable:

[](https://www.tpointtech.com/final-keyword-in-java#)[](https://www.tpointtech.com/final-keyword-in-java#)[](https://www.tpointtech.com/final-keyword-in-java#)

1. public class Main {      
2.     final int speedlimit;   // blank final variable      

3.     Main() {      
4.         speedlimit = 70;      
5.         System.out.println(speedlimit);      
6.     }      

7.     public static void main(String args[]) {      
8.         new Main();      
9.     }      
10. }  

**Output:**

70

## Static Blank Final Variable

A static blank final variable is a static final variable that is not initialized at the time of declaration. It can be initialized only inside a static block.

### Example

The following example demonstrates the use of static blank final variable:

[](https://www.tpointtech.com/final-keyword-in-java#)[](https://www.tpointtech.com/final-keyword-in-java#)[](https://www.tpointtech.com/final-keyword-in-java#)

1. public class Main {      
2.     static final int data;   // static blank final variable      

3.     static {      
4.         data = 50;      
5.     }      

6.     public static void main(String args[]) {      
7.         System.out.println(Main.data);      
8.     }      
9. }  

**Output:**

50

## Final Parameter

A final parameter is a method parameter whose value cannot be changed inside the method.

### Example

The following example demonstrates the use of final parameter:

[](https://www.tpointtech.com/final-keyword-in-java#)[](https://www.tpointtech.com/final-keyword-in-java#)[](https://www.tpointtech.com/final-keyword-in-java#)

1. public class Main {    
2.     public void value(final int num) {    
3.         System.out.println(num);    
4.     }    

5.     public static void main(String args[]) {    
6.         Main obj = new Main();    
7.         obj.value(500);    
8.     }    
9. }  

**Output:**

500

## Advantages of the final Keyword

Here are the key advantages of using the final Keyword in Java, which enhance the security, performance, and maintainability of our code:

1. **Improved Performance:** The final keyword enables the compiler to optimise code execution because final variables have fixed values, which results in enhanced efficiency.
2. **Security:** Declaring classes and methods as final prevents unintended modifications, ensuring core functionality remains intact.
3. **Clear Design Intent:** It signals to developers that a class or method should remain unchanged, improving code readability and maintainability.
4. **Immutability:** Helps create immutable objects, which are essential for functional programming and multi-threaded applications.
5. **Thread Safety:** Final fields ensure consistency in concurrent environments, preventing unexpected modifications by different threads.

## Final Constructor Limitation

A constructor cannot be declared as final because constructors are never inherited, and the **final keyword** is mainly used to restrict inheritance and overriding.

## Characteristics of the final Keyword

There are several characteristics of the final keyword in Java. Some of them are as follows:

1. **Immutability:** When applied to variables, classes, or methods, the final keyword ensures that values remain unchanged once assigned, preventing modifications.
2. **Method Overriding Restrictions:** A final method cannot be overridden in subclasses, helping maintain security and ensuring consistent behavior.
3. **Thread Safety:** The final keyword enhances clarity in multi-threaded applications by ensuring that values remain constant, reducing unintended modifications.