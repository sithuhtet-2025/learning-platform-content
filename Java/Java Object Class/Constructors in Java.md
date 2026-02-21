In Java, a constructor is a special method used to initialize objects when a class is created. In this chapter, we will learn about the constructors and their types with the help of examples.

## What is a Constructor in Java?

A Constructor in Java is a block of codes like the method. It is called when an instance of the class is created. At the time of calling constructor, memory for the object is allocated in the memory. It is a special type of method which is used to initialize the object.

Every time when we create an object by using the new keyword, it calls a default constructor. If there is no constructor available in the [class](https://www.tpointtech.com/java-classes-and-objects). In such case, [Java](https://www.tpointtech.com/java-tutorial) compiler provides a default constructor by default.

> **Note:** It is called constructor because it constructs the values at the time of object creation. It is not necessary to write a constructor for a class. Because Java compiler creates a default constructor if your class does not have any.

## Rules for Creating Java Constructor

Here are the rules, you must follow to create constructors in Java:

### 1. Constructor name must be the same as its class name

A constructor must have the **same name as the class**. This helps the Java compiler identify the constructor and use it while creating an object.

**Syntax:**

It has the following syntax:

[](https://www.tpointtech.com/java-constructor#)[](https://www.tpointtech.com/java-constructor#)[](https://www.tpointtech.com/java-constructor#)

1. class Student {  
2.     Student() {  
3.         System.out.println("Constructor called");  
4.     }  
5. }  

Here, Student() is the constructor because its name matches the class name Student.

### 2. A constructor must have no explicit return type

A constructor **does not return any value**, not even void. If you specify a return type, it will be treated as a normal method, not a constructor.

**Incorrect Example:**

[](https://www.tpointtech.com/java-constructor#)[](https://www.tpointtech.com/java-constructor#)[](https://www.tpointtech.com/java-constructor#)

1. class Test {  
2.     void Test() {   // This is NOT a constructor  
3.         System.out.println("Not a constructor");  
4.     }  
5. }  

**Correct Example:**

[](https://www.tpointtech.com/java-constructor#)[](https://www.tpointtech.com/java-constructor#)[](https://www.tpointtech.com/java-constructor#)

1. class Test {  
2.     Test() {  
3.         System.out.println("This is a constructor");  
4.     }  
5. }  

Here, in the correct example, we removed the return type "void" so it makes Test() a valid constructor.

### 3. A Java constructor cannot be abstract, static, final, or synchronized

Constructors are used to create and initialize objects, so Java does not allow these modifiers with constructors.

**Incorrect Example:**

[](https://www.tpointtech.com/java-constructor#)[](https://www.tpointtech.com/java-constructor#)[](https://www.tpointtech.com/java-constructor#)

1. class Demo {  
2.     static Demo() {   // Compilation error  
3.     }  
4. }  

**Correct Example:**

[](https://www.tpointtech.com/java-constructor#)[](https://www.tpointtech.com/java-constructor#)[](https://www.tpointtech.com/java-constructor#)

1. class Demo {  
2.     Demo() {  
3.         System.out.println("Object created");  
4.     }  
5. }  

Here, in the correct example, we removed "static" keyword that makes Demo() constructor valid.

> **Note:** We can use [access modifiers](https://www.tpointtech.com/access-modifiers-in-java) while declaring a constructor. It controls the object creation. A constructor may be private, protected, public or default.

## Types of Java Constructors

There are two types of constructors in Java:

1. **Default Constructor (No-arg Constructor):**  
    The default constructor does not take any parameters and is used to initialize an object with default values. If no constructor is defined, Java automatically provides a default constructor.
2. **Parameterized Constructor:**  
    The parameterized constructor accepts parameters and is used to initialize an object with specific values at the time of object creation.
3. **Copy Constructor:**  
    A copy constructor is a special type of constructor that is commonly utilized to create a new object by copying the values of an existing object of the same class.

![Java Constructors](https://d2jdgazzki9vjm.cloudfront.net/images/core/java-constructor.png)

Let's learn these types of the constructors in detail with the help of syntaxes and appropriate examples.

## 1. Java Default Constructor

When a constructor does not have any parameter, is known as default constructor.

### Syntax

It has the following syntax:

[](https://www.tpointtech.com/java-constructor#)[](https://www.tpointtech.com/java-constructor#)[](https://www.tpointtech.com/java-constructor#)

1. <class_name>(){}  

### Example of Default Constructor

In this example, we are creating the no-arg constructor in the Bike class. It will be invoked at the time of object creation.

[](https://www.tpointtech.com/java-constructor#)[](https://www.tpointtech.com/java-constructor#)[](https://www.tpointtech.com/java-constructor#)

1. //Java Program to create and call a default constructor    
2. class Bike{    
3.     //creating a default constructor    
4.     Bike(){System.out.println("Bike is created");}    
5. }  
6. public class Main{  
7.     //main method    
8.     public static void main(String args[]){    
9.         //calling a default constructor    
10.         Bike b=new Bike();    
11.     }    
12. }    

**Output:**

Bike is created

> Rule: If there is no constructor in a class, compiler automatically creates a default constructor.

![Java default constructor](https://d2jdgazzki9vjm.cloudfront.net/images/default-constructor1.png)

### Purpose of a default constructor

The default constructor is used to provide the default values to the object like 0, null, etc., depending on the type.

### Another Example: Displaying the default values

[](https://www.tpointtech.com/java-constructor#)[](https://www.tpointtech.com/java-constructor#)[](https://www.tpointtech.com/java-constructor#)

1. //Let us see another example of default constructor    
2. //which displays the default values    
3. class Student{    
4.     int id;    
5.     String name;    
6.     //method to display the value of id and name    
7.     void display(){System.out.println(id+" "+name);}    
8. }  
9. //Main class to create objects and calling methods  
10. public class Main{  
11.     public static void main(String args[]){    
12.         //creating objects    
13.         Student s1=new Student();    
14.         Student s2=new Student();    
15.         //displaying values of the object    
16.         s1.display();    
17.         s2.display();    
18.     }    
19. }    

**Output:**

0 null
0 null

In the above class, we are not creating any constructor so compiler provides us a default constructor. Here, 0 and null values are provided by default constructor.

## 2. Java Parameterized Constructor

A constructor that has a specific number of parameters is called a parameterized constructor.

### Syntax

[](https://www.tpointtech.com/java-constructor#)[](https://www.tpointtech.com/java-constructor#)[](https://www.tpointtech.com/java-constructor#)

1. class ClassName {  
2.     ClassName(dataType parameter1, dataType parameter2, ...) {  
3.         // constructor body  
4.     }  
5. }  

### Use of Parameterized Constructor

The parameterized constructor is used to provide different values to distinct objects. However, you can provide the same values also.

### Example of Parameterized Constructor

In this example, we have created the constructor of Student class that have two parameters. We can have any number of parameters in the constructor.

[](https://www.tpointtech.com/java-constructor#)[](https://www.tpointtech.com/java-constructor#)[](https://www.tpointtech.com/java-constructor#)

1. //Java Program to demonstrate the use of the parameterized constructor.    
2. class Student{    
3.     int id;    
4.     String name;    
5.     //creating a parameterized constructor    
6.     Student(int i,String n){    
7.     id = i;    
8.     name = n;    
9.     }    
10.     //method to display the values    
11.     void display(){System.out.println(id+" "+name);}    
12. }  
13. //Main class to create objects and class methods  
14. public class Main{  
15.     public static void main(String args[]){    
16.     //creating objects and passing values    
17.     Student s1 = new Student(111,"Joseph");    
18.     Student s2 = new Student(222,"Sonoo");    
19.     //calling method to display the values of object    
20.     s1.display();    
21.     s2.display();    
22.    }    
23. }    

**Output:**

111 Joseph
222 Sonoo

## Java Copy Constructor

Java does not support the copy constructor. However, we can copy the values from one object to another, like a copy constructor in C++.

There are the following three ways to copy the values of one object into another:

- By Using a Constructor
- By Assigning the Values of One Object to Another
- By Using the clone() Method of the Object Class

### Java Copy Constructor Example

In this example, we are going to copy the values of one object into another using a Java constructor.

[](https://www.tpointtech.com/java-constructor#)[](https://www.tpointtech.com/java-constructor#)[](https://www.tpointtech.com/java-constructor#)

1. //Java program to initialize the values from one object to another object.    
2. class Student{    
3.     int id;    
4.     String name;    
5.     //constructor to initialize integer and string    
6.     Student(int i,String n){    
7.     id = i;    
8.     name = n;    
9.     }    
10.     //constructor to initialize another object    
11.     Student(Student s){    
12.     id = s.id;    
13.     name =s.name;    
14.     }    
15.     void display(){System.out.println(id+" "+name);}    
16. }  
17. public class Main{  
18.     public static void main(String args[]){    
19.     Student s1 = new Student(111,"Karan");    
20.     Student s2 = new Student(s1);    
21.     s1.display();    
22.     s2.display();    
23.    }    
24. }    

**Output:**

111 Karan
111 Karan

### Copying Values Without using a Constructor

We can copy the values of one object into another by assigning the object's values to another object. In this case, there is no need to create the constructor.

### Example

Let us take an example to demonstrate how to copy values without using a constructor in Java.

[](https://www.tpointtech.com/java-constructor#)[](https://www.tpointtech.com/java-constructor#)[](https://www.tpointtech.com/java-constructor#)

1. class Student{    
2.     int id;    
3.     String name;    
4.     Student(int i,String n){    
5.     id = i;    
6.     name = n;    
7.     }    
8.     Student(){}    
9.     void display(){System.out.println(id+" "+name);}    
10. }  
11. public class Main{  
12.     public static void main(String args[]){    
13.     Student s1 = new Student(111,"Karan");    
14.     Student s2 = new Student();    
15.     s2.id=s1.id;    
16.     s2.name=s1.name;    
17.     s1.display();    
18.     s2.display();    
19.    }    
20. }    

**Output:**

111 Karan
111 Karan

## Constructor Overloading in Java

In Java, a constructor is just like a method but without return type. It can also be overloaded like Java methods.

[Constructor overloading in Java](https://www.tpointtech.com/method-overloading-in-java) is a technique of having more than one constructor with different parameter lists. They are arranged in a way that each constructor performs a different task. They are differentiated by the compiler on the basis of the number of parameters in the list and their types.

### Example of Constructor Overloading

Let us take an example to demonstratethe working of constructor overloading in Java.

[](https://www.tpointtech.com/java-constructor#)[](https://www.tpointtech.com/java-constructor#)[](https://www.tpointtech.com/java-constructor#)

1. //Java program to overload constructors    
2. class Student{    
3.     int id;    
4.     String name;    
5.     int age;    
6.     //creating two arg constructor    
7.     Student(int i,String n){    
8.     id = i;    
9.     name = n;    
10.     }    
11.     //creating three arg constructor    
12.     Student(int i,String n,int a){    
13.     id = i;    
14.     name = n;    
15.     age=a;    
16.     }    
17.     //creating method to display values  
18.     void display(){System.out.println(id+" "+name+" "+age);}    
19. }  
20. //creating a Main class to create instance and call methods  
21. public class Main{  
22.     public static void main(String args[]){    
23.     Student s1 = new Student(111,"Karan");    
24.     Student s2 = new Student(222,"Aryan",25);    
25.     s1.display();    
26.     s2.display();    
27.    }    
28. }    

**Output:**

111 Karan 0
222 Aryan 25

## Constructor Chaining

Constructor chaining in Java is a practice where one constructor calls another constructor of the same class or a superclass during object creation. It is typically done using either this() to call another constructor in the same class or super() to call a constructor in the superclass. By centralizing common construction logic, constructor chaining helps reduce code redundancy and increases the code's readability.

To read more [Constructor Chaining in Java](https://www.tpointtech.com/what-is-constructor-chaining-in-java)

If you are a beginner to Java, it is better to skip this part because we will learn about this and super keywords later.

## Difference Between Constructor and Method in Java

There are many differences between constructors and methods. They are given below.

|Java Constructor|Java Method|
|---|---|
|A constructor is used to initialize the state of an object.|A method is used to expose the behavior of an object.|
|A constructor must not have a return type.|A method must have a return type.|
|The constructor is invoked implicitly.|The method is invoked explicitly.|
|The Java compiler provides a default constructor if we do not have any constructor in a class.|The method is not provided by the compiler in any case.|
|The constructor's name must be same as the class name.|The method name may or may not be same as the class name.|

  

## Important Points about Constructors

There are several important points about constructors in Java. Some of them are as follows:

1. A constructor is automatically called when an object is created using the new keyword.
2. If no constructor is defined, Java provides a default constructor that initializes instance variables to default values (0, null, etc.).
3. Constructors do not have a return type, not even void.
4. A constructor's name must match the class name exactly.
5. Constructor overloading is allowed, meaning multiple constructors can be defined with different parameters.
6. A constructor can call another constructor within the same class using this(), which is known as constructor chaining.
7. A constructor can call a superclass constructor using super(), which must be the first statement in the constructor.
8. Constructors cannot be static, final, abstract, or synchronized in Java.
9. Constructors can have access modifiers (public, private, protected, or default). A private constructor is used in singleton patterns.
10. Constructors can perform other tasks beyond initialization, such as opening database connections, starting threads, or calling methods.