In object-oriented programming, classes and objects play a vital role in programming. These are the two main pillars of OOP (Object-Oriented Programming). Without classes and objects, we cannot create a program in Java. So, in this section, we are going to **discuss about classes and objects in Java.**

## What is a Class in Java?

A class is a group of objects that have common properties. It is a template or blueprint from which objects are created. It is a logical entity. It can't be physical.

A Java class contains:

![Class in Java](https://d2jdgazzki9vjm.cloudfront.net/core/images/class-in-java.png)

### 1. Fields

Variables stated inside a class that indicate the status of objects formed from that class are called fields, sometimes referred to as instance variables. They specify the data that will be stored in each class object. Different access modifiers, such as public, private, and protected, can be applied to fields to regulate their visibility and usability.

### 2. Methods

Methods are functions defined inside a class that include the actions or behaviors that objects of that class are capable of performing. These techniques allow the outside world to function and change the object's state (fields). Additionally, methods can be void (that is, they return nothing) or have different access modifiers. They can also return values.

### 3. Constructors

Constructors are unique methods that are used to initialize class objects. When an object of the class is created using the new keyword, they are called with the same name as the class. Constructors can initialize the fields of an object or carry out any additional setup that's required when an object is created.

### 4. Blocks

Within a class, Java allows two different kinds of blocks: instance blocks, commonly referred to as initialization blocks and static blocks. Static blocks, which are usually used for static initialization, are only executed once when the class is loaded into memory. Instance blocks can be used to initialize instance variables and are executed each time a class object is generated.

### 5. Nested Class and Interface

Java permits the nesting of classes and interfaces inside other classes and interfaces. The members (fields, methods) of the enclosing class are accessible to nested classes, which can be static or non-static. Nested interfaces can be used to logically group related constants and methods together because they are implicitly static.

### Java Class Syntax

[](https://www.tpointtech.com/java-classes-and-objects#)[](https://www.tpointtech.com/java-classes-and-objects#)[](https://www.tpointtech.com/java-classes-and-objects#)

1. class <class_name>{  
2.     field;  
3.     method;  
4. }  

## What is an object in Java?

An object is a real-world entity that has state and behaviour. In other words, an object is a tangible thing that can be touch and feel, like a car or chair, etc. The banking system is an example of an intangible object. Every object has a distinct identity, which is usually implemented by a unique ID that the JVM uses internally for identification.

![object in Java](https://d2jdgazzki9vjm.cloudfront.net/images/objects.jpg)

### Characteristics of an Object

- **State:** It represents the data (value) of an object.
- **Behavior:** It represents the behavior (functionality) of an object, such as deposit, withdraw, etc.
- **Identity:** An object's identity is typically implemented via a unique ID. The ID's value is not visible to the external user; however, it is internally used by the JVM to identify each object uniquely.

For Example, a Pen is an object. Its name is Reynolds; its color is white, known as its state. It is used to write, so writing is its behavior.

**An object is an instance of a class.** A class is a template or blueprint from which objects are created. So, an object is the instance (result) of a class.

### Object Definitions

- An object is _a real-world entity_.
- An object is _a runtime entity_.
- The object is an entity that has state and behavior.
- The object is _an instance of a class_.

### Syntax of an Object

[](https://www.tpointtech.com/java-classes-and-objects#)[](https://www.tpointtech.com/java-classes-and-objects#)[](https://www.tpointtech.com/java-classes-and-objects#)

1. <class_name> variable=new <class_name>();  

### new keyword in Java

The new keyword is used to allocate memory at runtime. All objects get memory in the Heap memory area.

In Java, an instance of a class (also referred to as an object) is created using the new keyword. The new keyword dynamically allocates memory for an object of that class and returns a reference to it when it is followed by the class name and brackets with optional arguments.

To read more [Java new keyword](https://www.tpointtech.com/new-keyword-in-java)

### Class Example: main() Method Within The Class

In Java, the main() method can be declared in a class, which is typically done in demonstration or basic programs. Having the main() method defined inside a class allows a program to run immediately without creating a separate class containing it.

In this example, we have created a Main class that has two data members, id and name. We are creating the object of the Main class by using the new keyword and printing the object's value.

### Example

[](https://www.tpointtech.com/java-classes-and-objects#)[](https://www.tpointtech.com/java-classes-and-objects#)[](https://www.tpointtech.com/java-classes-and-objects#)

1. //Java Program to illustrate how to define a class and fields    
2. //Defining a Student class.    
3. class Main{    
4.  //defining fields    
5.  int id;//field or data member or instance variable    
6.  String name;    
7.  //creating main method inside the Student class    
8.  public static void main(String args[]){    
9.   //Creating an object or instance    
10.   Main s1=new Main();//creating an object of Student    
11.   //Printing values of the object    
12.   System.out.println(s1.id);//accessing member through reference variable    
13.   System.out.println(s1.name);    
14.  }    
15. }    

**Output:**

0
null

**Explanation**

Two fields are defined for the Main class in this Java program: an int type for the id and a string type for the name. The Main class itself defines the primary method. The new keyword is used to create an object s1 of the class Main inside the main() method. The fields' default values, 0 for int and null for String, are printed because they are not explicitly initialized. The program finally prints the values of the s1 object's name and id fields.

### Class Example: main() Method Outside The Class

In real-world development, it is usual practice to organise Java classes into distinct files and to place the main() method outside of the class it is intended to execute from. This strategy improves the readability, maintainability, and reusability of the code.

In real-time development, we create classes and use them from another class. It is a better approach than the previous one. Let's see a simple example, where we have a main() method in another class.

We can have multiple classes in different Java files or a single Java file. If you define multiple classes in a single Java source file, it is a good idea to save the file name with the class name that has a main() method.

### Example

[](https://www.tpointtech.com/java-classes-and-objects#)[](https://www.tpointtech.com/java-classes-and-objects#)[](https://www.tpointtech.com/java-classes-and-objects#)

1. //Creating a Student class   
2. class Student{    
3.  //declaring fields or instance variables  
4.  int id;    
5.  String name;    
6. }    
7. //Creating another class which contains the main() method    
8. class Main{    
9.  public static void main(String args[]){    
10.   Student s1=new Student();    
11.   System.out.println(s1.id);    
12.   System.out.println(s1.name);    
13.  }    
14. }    

**Output:**

0
null

**Explanation**

In the above Java program, the main() method is shown in a different class than the Student class. There are no methods defined for the two fields, name and id, in the Student class. The main() method then resides in another class called Main, where the default constructor is used to generate an object s1 of type Student. The field's name and id are written with their default values, which are null for String and 0 for int, since they are not explicitly initialised.

## Initializing an Object in Java

There are the following three ways to initialize an object in Java:

1. By Reference Variable
2. By Method
3. By Constructor

### 1) Object Initialization through Reference Variable

Initializing an object means storing data in the object. Let's see a simple example where we are going to initialize the object through a reference variable.

### Example

[](https://www.tpointtech.com/java-classes-and-objects#)[](https://www.tpointtech.com/java-classes-and-objects#)[](https://www.tpointtech.com/java-classes-and-objects#)

1. class Student{    
2.  int id;    
3.  String name;    
4. }    
5. public class Main{    
6.  public static void main(String args[]){    
7.   //Creating instance of Student class  
8.   Student s1=new Student();    
9.   //assigning values through reference variable  
10.   s1.id=101;    
11.   s1.name="Sonoo";    
12.   //printing values of s1 object  
13.   System.out.println(s1.id+" "+s1.name);    
14.  }    
15. }    

**Output:**

101 Sonoo

**Explanation**

In the above Java program, there are two classes, Student and Main. In the student class, we have defined two fields, id and name. The main() method, which is the program's entry point, is specified in the Main class. The new keyword is used to create an object s1 of type Student inside the main() method. Next, values 101 and "Sonoo" are initialised in the id and name fields of s1.

We can also create multiple objects and store information in them through a reference variable.

### Example

[](https://www.tpointtech.com/java-classes-and-objects#)[](https://www.tpointtech.com/java-classes-and-objects#)[](https://www.tpointtech.com/java-classes-and-objects#)

1. class Student{    
2.  int id;    
3.  String name;    
4. }    
5. public class Main{    
6.  public static void main(String args[]){    
7.   //Creating objects    
8.   Student s1=new Student();    
9.   Student s2=new Student();    
10.   //Initializing objects    
11.   s1.id=101;    
12.   s1.name="Sonoo";    
13.   s2.id=102;    
14.   s2.name="Amit";    
15.   //Printing data    
16.   System.out.println(s1.id+" "+s1.name);    
17.   System.out.println(s2.id+" "+s2.name);    
18.  }    
19. }    

**Output:**

101 Sonoo
102 Amit

**Explanation**

The above Java program shows how to create and initialise multiple Student class objects in the Main class. We have created the objects s1 and s2 of the Student class by using the new keyword. Subsequently, each object's name and id fields are initialized independently. ID is set to 101, and the name is set to "Sonoo" for S1, and 102 and the name is set to "Amit" and S2, respectively.

### 2) Object Initialization through Method

In this example, we are creating the two objects of Student class and initializing the value to these objects by invoking the insertRecord method.

Here, we are displaying the state (data) of the objects by invoking the displayInformation() method.

### Example

[](https://www.tpointtech.com/java-classes-and-objects#)[](https://www.tpointtech.com/java-classes-and-objects#)[](https://www.tpointtech.com/java-classes-and-objects#)

1. class Student{    
2.  int rollno;    
3.  String name;    
4.  //Creating a method to insert record  
5.  void insertRecord(int r, String n){    
6.   rollno=r;    
7.   name=n;    
8.  }    
9.  //creating a method to display information  
10.  void displayInformation(){System.out.println(rollno+" "+name);}    
11. }    
12. //Creating a Main class to create objects and call methods  
13. public class Main{    
14.  public static void main(String args[]){    
15.   Student s1=new Student();    
16.   Student s2=new Student();    
17.   s1.insertRecord(111,"Karan");    
18.   s2.insertRecord(222,"Aryan");    
19.   s1.displayInformation();    
20.   s2.displayInformation();    
21.  }    
22. }    

**Output:**

111 Karan
222 Aryan

**Explanation**

The provided Java code includes two classes: Student and Main. The Student class includes rollno and name as fields, along with the methods insertRecord() and displayInformation() to initialise and print the respective fields' data. Two Student objects are created in the main() method of the Main class, and their corresponding insertRecord() methods are called to set their rollno and name.

![Object in Java with values](https://d2jdgazzki9vjm.cloudfront.net/core/images/object-in-memory.png)

As we can see in the above figure, the object gets the memory in the heap memory area. The reference variable refers to the object allocated in the heap memory area. Here, s1 and s2 are reference variables that refer to the objects allocated in memory.

### 3) Object Initialization through a Constructor

The concept of object initialization through a constructor is essential to object-oriented programming in Java. Special methods inside a class called constructors are called when an object of that class is created with the new keyword. They initialise the state of objects by entering initial values in their fields or carrying out any required setup procedures. The constructor is automatically invoked upon object instantiation, guaranteeing correct initialization of the object prior to usage.

If you are a beginner, skip this part because we will learn about the constructor later.

Here's an example demonstrating object initialization through a constructor.

### Example

[](https://www.tpointtech.com/java-classes-and-objects#)[](https://www.tpointtech.com/java-classes-and-objects#)[](https://www.tpointtech.com/java-classes-and-objects#)

1. class Student {    
2.     int id;    
3.     String name;    
4.     // Constructor with parameters    
5.     public Student(int id, String name) {    
6.         this.id = id;    
7.         this.name = name;    
8.     }    
9.     // Method to display student information    
10.     public void displayInformation() {    
11.         System.out.println("Student ID: " + id);    
12.         System.out.println("Student Name: " + name);    
13.     }    
14. }    
15. public class Main {    
16.     public static void main(String[] args) {    
17.         // Creating objects of Student class with constructor    
18.         Student student1 = new Student(1, "John Doe");    
19.         Student student2 = new Student(2, "Jane Smith");    
20.         // Displaying information of the objects    
21.         student1.displayInformation();    
22.         student2.displayInformation();    
23.     }    
24. }    

**Output:**

Student ID: 1
Student Name: John Doe
Student ID: 2
Student Name: Jane Smith

**Explanation**

In this example, the id and name fields of a Student object are initialised using a constructor defined by the Student class, which accepts two parameters: id and name. Upon creating objects student1 and student2 using this constructor, the fields of each are initialised with the values supplied. This method ensures that objects are created with the correct starting values, which makes it easier to instantiate and use objects later on in the program.

### Object and Class Example: Employee

Let's see an example where we are maintaining records of employees.

### Example

[](https://www.tpointtech.com/java-classes-and-objects#)[](https://www.tpointtech.com/java-classes-and-objects#)[](https://www.tpointtech.com/java-classes-and-objects#)

1. class Employee{      
2.     int id;      
3.     String name;      
4.     float salary;      
5.     void insert(int i, String n, float s) {      
6.         id=i;      
7.         name=n;      
8.         salary=s;      
9.     }      
10.     void display(){System.out.println(id+" "+name+" "+salary);}      
11. }      
12. public class Main {      
13. public static void main(String[] args) {      
14.     Employee e1=new Employee();      
15.     Employee e2=new Employee();      
16.     Employee e3=new Employee();      
17.     e1.insert(101,"ajeet",45000);      
18.     e2.insert(102,"irfan",25000);      
19.     e3.insert(103,"nakul",55000);      
20.     e1.display();      
21.     e2.display();      
22.     e3.display();      
23. }      
24. }      

**Output:**

101 ajeet 45000.0
102 irfan 25000.0
103 nakul 55000.0

**Explanation**

In the above program, the Employee class has three fields: id, name, and salary. It also has two methods, insert(), which sets the values for these fields, and display(), which prints the values. The main() function of the Main class creates three Employee objects (e1, e2, and e3). It initialises the id, name, and salary fields of each object with precise values, and the insert() method is called on each of the objects. Then, each object's display() method is called, displaying object initialization and information display via method invocation. Each object's id, name, and salary values are printed to the console.

### Object and Class Example: Rectangle

Another example is given that maintains the records of the Rectangle class.

### Example

[](https://www.tpointtech.com/java-classes-and-objects#)[](https://www.tpointtech.com/java-classes-and-objects#)[](https://www.tpointtech.com/java-classes-and-objects#)

1. class Rectangle{    
2.  int length;    
3.  int width;    
4.  void insert(int l, int w){    
5.   length=l;    
6.   width=w;    
7.  }    
8.  void calculateArea(){System.out.println(length*width);}    
9. }    
10. public class Main{    
11.  public static void main(String args[]){    
12.   Rectangle r1=new Rectangle();    
13.   Rectangle r2=new Rectangle();    
14.   r1.insert(11,5);    
15.   r2.insert(3,15);    
16.   r1.calculateArea();    
17.   r2.calculateArea();    
18. }    
19. }    

**Output:**

55
45

**Explanation**

This Java code defines a Rectangle class with fields for length and width, along with methods to insert dimensions and calculate the area. In the Main class's main() method, two Rectangle objects are instantiated, and their dimensions are set using the insert method.

## What are the different ways to create an object in Java?

There are the following ways to create an object in Java.

**1. By new Keyword**

The most common way to create an object in Java is using the new keyword followed by a constructor. For example,

[](https://www.tpointtech.com/java-classes-and-objects#)[](https://www.tpointtech.com/java-classes-and-objects#)[](https://www.tpointtech.com/java-classes-and-objects#)

1. ClassName obj = new ClassName();  

It allocates memory for the object and calls its constructor to initialize it.

**2. By newInstance() Method**

This method is part of the java.lang.Class class and is used to create a new instance of a class dynamically at runtime. It invokes the no-argument constructor of the class. For example,

[](https://www.tpointtech.com/java-classes-and-objects#)[](https://www.tpointtech.com/java-classes-and-objects#)[](https://www.tpointtech.com/java-classes-and-objects#)

1. ClassName obj = (ClassName) Class.forName("ClassName").newInstance();.  

**3. By clone() Method**

The clone() method creates a copy of an existing object by performing a shallow copy. It returns a new object that is a duplicate of the original object. For example,

[](https://www.tpointtech.com/java-classes-and-objects#)[](https://www.tpointtech.com/java-classes-and-objects#)[](https://www.tpointtech.com/java-classes-and-objects#)

1. ClassName obj2 = (ClassName) obj1.clone();.  

**4. By Deserialization**

Objects can be created by deserializing them from a stream of bytes. We can achieve it by using the ObjectInputStream class in Java. The serialized object is read from a file or network, and then the readObject() method is called to recreate the object.

**5. By factory Method**

Factory methods are static methods within a class that return instances of the class. They provide a way to create objects without directly invoking a constructor and can be used to encapsulate object creation logic. For example,

[](https://www.tpointtech.com/java-classes-and-objects#)[](https://www.tpointtech.com/java-classes-and-objects#)[](https://www.tpointtech.com/java-classes-and-objects#)

1. ClassName obj = ClassName.createInstance().  

We will learn these ways to create objects later.

![Different Ways to create an Object in Java](https://d2jdgazzki9vjm.cloudfront.net/core/images/different-ways-to-create-object-in-java1.png)

## Anonymous Object

Anonymous simply means nameless. An object that has no reference is known as an anonymous object. It can be used at the time of object creation only.

If we have to use an object only once, an anonymous object is a good approach. For example:

[](https://www.tpointtech.com/java-classes-and-objects#)[](https://www.tpointtech.com/java-classes-and-objects#)[](https://www.tpointtech.com/java-classes-and-objects#)

1. new Calculation();//anonymous object  

Calling a method through an anonymous object

[](https://www.tpointtech.com/java-classes-and-objects#)[](https://www.tpointtech.com/java-classes-and-objects#)[](https://www.tpointtech.com/java-classes-and-objects#)

1. Calculation c=new Calculation();  
2. c.fact(5);  

Calling method through an anonymous object

[](https://www.tpointtech.com/java-classes-and-objects#)[](https://www.tpointtech.com/java-classes-and-objects#)[](https://www.tpointtech.com/java-classes-and-objects#)

1. new Calculation().fact(5);  

Let's see the full example of an anonymous object in Java.

### Example

[](https://www.tpointtech.com/java-classes-and-objects#)[](https://www.tpointtech.com/java-classes-and-objects#)[](https://www.tpointtech.com/java-classes-and-objects#)

1. class Main{    
2.  void fact(int  n){    
3.   int fact=1;    
4.   for(int i=1;i<=n;i++){    
5.    fact=fact*i;    
6.   }    
7.  System.out.println("factorial is "+fact);    
8. }    
9. public static void main(String args[]){    
10.  new Main().fact(5);//calling method with anonymous object    
11. }    
12. }    

**Output:**

Factorial is 120

**Explanation**

The above Java program calculates the factorial of a given number n. The Main class has a fact() method that computes the factorial. After that, the console prints the outcome. The creation of an anonymous Main class object and the instantaneous invocation of its fact function with parameter 5 in the main() method illustrates how to use anonymous objects in Java for one-time method calls.

## Creating Multiple Objects by One Type Only

We can create multiple objects of one type only, as we do in the case of primitives.

**Initialization of Primitive Variables**

[](https://www.tpointtech.com/java-classes-and-objects#)[](https://www.tpointtech.com/java-classes-and-objects#)[](https://www.tpointtech.com/java-classes-and-objects#)

1. int a=10, b=20;  

**Initialization of Reference Variables**

[](https://www.tpointtech.com/java-classes-and-objects#)[](https://www.tpointtech.com/java-classes-and-objects#)[](https://www.tpointtech.com/java-classes-and-objects#)

1. Rectangle r1=new Rectangle(), r2=new Rectangle();//creating two objects  

Let's see an example.

### Example

[](https://www.tpointtech.com/java-classes-and-objects#)[](https://www.tpointtech.com/java-classes-and-objects#)[](https://www.tpointtech.com/java-classes-and-objects#)

1. //Java Program to illustrate the use of the Rectangle class, which    
2. //has length and width data members    
3. class Rectangle{    
4.  int length;    
5.  int width;    
6.  void insert(int l,int w){    
7.   length=l;    
8.   width=w;    
9.  }    
10.  void calculateArea(){System.out.println(length*width);}    
11. }    
12. class Main{    
13.  public static void main(String args[]){    
14.   Rectangle r1=new Rectangle(),r2=new Rectangle();//creating two objects    
15.   r1.insert(11,5);    
16.   r2.insert(3,15);    
17.   r1.calculateArea();    
18.   r2.calculateArea();    
19. }    
20. }    

**Output:**

55
45

**Explanation**

The usage of a Main class with length and width as its data members is demonstrated in this Java program. There are methods in the class to compute the area of a rectangle and insert dimensions. The main() method of the Main class uses a comma-separated list to generate two Rectangle objects (r1 and r2) in one line, demonstrating the ability to instantiate multiple objects of the same type simultaneously. Each object's dimensions are then specified by calling the insert method, and each rectangle's area is then calculated and printed by calling the calculateArea() method.

### Real World Example: Account

File: TestAccount.java

### Example

[](https://www.tpointtech.com/java-classes-and-objects#)[](https://www.tpointtech.com/java-classes-and-objects#)[](https://www.tpointtech.com/java-classes-and-objects#)

1. //Java Program to demonstrate the working of a banking-system    
2. //where we deposit and withdraw amount from our account.    
3. //Creating an Account class which has deposit() and withdraw() methods    
4. class Account{    
5. int acc_no;    
6. String name;    
7. float amount;    
8. //Method to initialize object    
9. void insert(int a,String n,float amt){    
10. acc_no=a;    
11. name=n;    
12. amount=amt;    
13. }    
14. //deposit method    
15. void deposit(float amt){    
16. amount=amount+amt;    
17. System.out.println(amt+" deposited");    
18. }    
19. //withdraw method    
20. void withdraw(float amt){    
21. if(amount<amt){    
22. System.out.println("Insufficient Balance");    
23. }else{    
24. amount=amount-amt;    
25. System.out.println(amt+" withdrawn");    
26. }    
27. }    
28. //method to check the balance of the account    
29. void checkBalance(){System.out.println("Balance is: "+amount);}    
30. //method to display the values of an object    
31. void display(){System.out.println(acc_no+" "+name+" "+amount);}    
32. }    
33. //Creating a test class to deposit and withdraw amount    
34. class Main{    
35. public static void main(String[] args){    
36. Account a1=new Account();    
37. a1.insert(832345,"Ankit",1000);    
38. a1.display();    
39. a1.checkBalance();    
40. a1.deposit(40000);    
41. a1.checkBalance();    
42. a1.withdraw(15000);    
43. a1.checkBalance();    
44. }}     

**Output:**

832345 Ankit 1000.0
Balance is: 1000.0
40000.0 deposited
Balance is: 41000.0
15000.0 withdrawn
Balance is: 26000.0

**Explanation**

With methods for depositing, withdrawing, checking balance, and showing account details, the Account class in this Java program emulates a simple banking system. Other characteristics include account number, name, and amount. The creation, initialization, and presentation of an Account object a1 with account information take place in the main() method of the Main class. Next, the account is used for deposits and withdrawals, and after each transaction, the balance is checked.

## Difference Between Class and Object in Java

|Feature|Class|Object|
|---|---|---|
|**Definition**|A class is a blueprint or template for creating objects.|It is an instance of a class.|
|**Type**|It is a logical entity.|It is a real-world entity.|
|**Memory Allocation**|Class definition does not occupy memory.|It occupies memory when an object is created.|
|**Keyword**|It is created by using the class keyword.|It is created by using the new keyword and a class constructor.|
|**Contains**|It contains properties and behaviors that an object will have.|It is used to access the properties and behaviors defined in the class.|
|**Existence**|Exists only in source code.|Exists in runtime (in memory).|
|**Usage**|Defines the structure and behavior of objects.|Represents an entity with actual values.|
|**Syntax**|class ClassName{ }|ClassName objectName = new ClassName();|
|**Life**|It exists until the program runs.|It exists as long as the object is referenced in the program.|
|**Inheritance**|The classes can be extended using inheritance.|It cannot be inherited because objects are specific instances.|