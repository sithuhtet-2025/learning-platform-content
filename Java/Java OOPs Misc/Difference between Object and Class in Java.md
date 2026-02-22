Java **objects** are instances of a class that exist in memory, whereas **classes** are blueprints or templates that define the structure and behavior of objects. In this chapter, we will discuss the key differences between objects and classes, along with examples.

## What is an Object in Java?

An object is an instance of a class. It is a real-world entity that holds actual values in memory and can invoke methods defined in the class.

### Characteristics of an Object

The following are the characteristics of an object:

- **Instance of a Class**: An object is a concrete implementation of a class.
- **Physical Entity**: It occupies memory in the heap at runtime.
- **State and Behavior**:
    - **State** is stored in fields (variables).
    - **Behavior** is exhibited through methods.
- **Object Creation**: Objects are typically created using the new keyword.

## What is a Class in Java?

A class in Java is a blueprint or template that defines the structure and behavior (data and methods) of objects. It acts as a logical entity that groups similar types of data and functions. A Java class contains fields, methods, blocks, constructors, etc.

### Characteristics of a Class

The following are the characteristics of a class:

- **Blueprint**: A class is a blueprint or prototype from which objects are created.
- **Logical Entity**: It doesn't consume memory until an object is created.
- **Defined with class keyword**: Every class in Java is declared using the class keyword.
- **Abstraction**: It abstracts the implementation details and shows only the structure.
- **Encapsulation**: It can group data (fields) and code (methods) into a single unit.

To read more [Java Classes and Objects](https://www.tpointtech.com/java-classes-and-objects)

## Differences Between Objects and Classes

There are many differences between an object and a class. A list of differences between object and class is given below:

|Object|Class|
|---|---|
|An object is an **instance** of a class.|Class is a **blueprint or template** from which objects are created.|
|The object is a real-world entity such as a pen, a laptop, a mobile, a bed, a keyboard, a mouse, a chair, etc.|A class is a **group of similar objects**.|
|An object is a **physical** entity.|Class is a **logical** entity.|
|Object is created through **new keyword** mainly e.g.  <br>Student s1=new Student();|Class is declared using the **class keyword**. For example,  <br>class Student{}|
|The object is created many times as per the requirement.|Class is declared **once**.|
|An object **allocates memory when it is created**.|A class does not allocate **memory when it is created**.|
|There are **many ways to create objects in Java, such as the new keyword, the newInstance() method, the clone() method, the** factory method and deserialisation.|There is only **one way to define a class in Java using the** class keyword.|
|Objects represent individual instances with specific states and behaviors.|A class defines the state (fields) and behavior (methods) that its objects will have.|
|Each object has its copy of instance variables.|The class contains the definition of variables but doesn't hold values until instantiated.|
|Objects can access both instance and static members of the class.|Class can have static members that are shared across all objects.|
|Objects are stored in heap memory.|Class definitions (metadata) are stored in the method area of the JVM.|
|Objects are created during runtime.|The JVM loads a class during the class loading phase.|
|Objects can be serialized (converted into a byte stream).|Class itself cannot be serialised, but it must implement the Serializable interface to allow its objects to be serialized.|
|Objects can interact with each other through method calls.|Class defines the methods used for object interaction but does not perform actions on its own.|
|Object lifecycle is managed by the garbage collector once it's no longer referenced.|Class lifecycle is managed by the JVM, and it is unloaded when the application ends or the classloader is garbage collected.|

## Real-Life Examples of Classes and Objects

To better understand the difference between **classes** and **objects**, let's look at some real-life examples:

|Object|Class|
|---|---|
|**Class**|**Objects (Instances)**|
|**Human**|Man, Woman|
|**Fruit**|Apple, Banana, Mango, Guava|
|**Mobile Phone**|iPhone, Samsung, Moto|
|**Vehicle**|Car, Bike, Truck, Bus|
|**Shape**|Circle, Rectangle, Triangle, Square|
|**Computer**|Laptop, Desktop, Tablet, Server|

## Understanding Classes Vs Objects with a Java Program

Let's understand how classes and objects work in Java using a simple **bank account program** that can deposit, withdraw, and check balances.

In the following example, we create an **Account class** and use its **object a1** to perform operations like deposit, withdraw, and check balance.

### Example

[](https://www.tpointtech.com/difference-between-object-and-class#)[](https://www.tpointtech.com/difference-between-object-and-class#)[](https://www.tpointtech.com/difference-between-object-and-class#)

1. //Java Program to understand the use of class and object in Java    
2. //Creating an Account class which has deposit() and withdraw() methods    
3. class Account{    
4. int acc_no;    
5. String name;    
6. float amount;    
7. //Method to initialize object    
8. void insert(int a,String n,float amt){    
9. acc_no=a;    
10. name=n;    
11. amount=amt;    
12. }    
13. //deposit method    
14. void deposit(float amt){    
15. amount=amount+amt;    
16. System.out.println(amt+" deposited");    
17. }    
18. //withdraw method    
19. void withdraw(float amt){    
20. if(amount<amt){    
21. System.out.println("Insufficient Balance");    
22. }else{    
23. amount=amount-amt;    
24. System.out.println(amt+" withdrawn");    
25. }    
26. }    
27. //method to check the balance of the account    
28. void checkBalance(){System.out.println("Balance is: "+amount);}    
29. //method to display the values of an object    
30. void display(){System.out.println(acc_no+" "+name+" "+amount);}    
31. }    
32. //Creating a test class to deposit and withdraw amounts    
33. public class Main {    
34. public static void main(String[] args){    
35. Account a1=new Account();    
36. a1.insert(832345,"Ankit",1000);    
37. a1.display();    
38. a1.checkBalance();    
39. a1.deposit(40000);    
40. a1.checkBalance();    
41. a1.withdraw(15000);    
42. a1.checkBalance();    
43. }}  

**Output:**

832345 Ankit 1000.0
Balance is: 1000.0
40000.0 deposited
Balance is: 41000.0
15000.0 withdrawn
Balance is: 26000.0