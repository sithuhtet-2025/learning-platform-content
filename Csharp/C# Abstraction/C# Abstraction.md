In C#, an abstraction is an essential feature of object-oriented programming (OOP). It hides unnecessary implementation details and shows only the necessary details of an object. It simplifies the development process by reducing programming complexity and efforts. It also helps in securing code by exposing only relevant data and methods. Abstraction can be implemented through the use of abstract classes and interfaces.

## Why use Abstraction in C#?

Several main uses of abstraction in object-oriented programming in C# are as follows:

- It helps to enhance the ease of maintaining the code.
- It is used to improve code complexity.
- It enhances code security by exposing only the relevant data and methods.
- It helps to provide a clear interface while hiding the internal data.

## Types of Abstraction in C#

In the C# programming language, abstraction can be categorized into two types. These are as follows.

![C# Abstraction](https://images.tpointtech.com/csharp/images/csharp-abstraction-1.png)

Here, we will discuss these abstractions one by one.

### 1) Data Abstraction:

In the [C# programming language](https://www.tpointtech.com/c-sharp-tutorial), data abstraction refers to hiding the details of how data is stored or maintained and only showing the important information that the user needs.

**Simple Example of Data Abstraction in C#:**

Let us take a simple example to illustrate the data abstraction in C#.

### Example

[](https://www.tpointtech.com/c-sharp-abstraction#)[](https://www.tpointtech.com/c-sharp-abstraction#)[](https://www.tpointtech.com/c-sharp-abstraction#)

1. using System;     
2. class Account  
3. {  
4.     private double bal;   
5.     public void deposit(double amt)  
6.     {  
7.         bal += amt;  
8.     }  
9.     public double GetBal()  
10.     {  
11.         return bal;  
12.     }  
13. }  
14. class Tpoint  
15. {  
16.     static void Main(string[] args)  
17.     {  
18.         Account myAct = new Account();  
19.         myAct.deposit(500);   
20.         Console.WriteLine("Balance after deposit: " + myAct.GetBal() );  
21.         myAct.deposit(200);   
22.         Console.WriteLine("Balance after second deposit: " + myAct.GetBal());  
23.     }  
24. }  

**Output:**

Balance after deposit: 500
Balance after second deposit: 700

**Explanation:**

In this example, we define the class named Account that keeps track of a bank balance. The balance is private, so it cannot be changed directly. After that, we create the deposit() method to add the money, and the GetBal() method is used to show the current balance. In the main method, we are creating an object of class (Account) and calling the deposit() method.

### 2) Control Abstraction:

In C#, control abstraction refers to the process of hiding the control flow or logic of the program and showing only the necessary operations to the user. It shows only what the code does, instead of focusing on how the control flow works internally.

**Simple Example of Control Abstraction in C#**

Let us take an example to illustrate the control abstraction in C#.

### Example

[](https://www.tpointtech.com/c-sharp-abstraction#)[](https://www.tpointtech.com/c-sharp-abstraction#)[](https://www.tpointtech.com/c-sharp-abstraction#)

1. using System;  
2. class Tpoint  
3. {  
4.     static void PrintReport()  
5.     {  
6.         Console.WriteLine("Report Printed");  
7.     }  
8.     static void Main(string[] args)  
9.     {  
10.         PrintReport();  
11.     }  
12. }  

**Output:**

Report Printed

**Explanation:**

In this example, we have taken the PrintReport() method, which represents a task that could involve complex operations, such as retrieving and formatting data for a report. However, all that complexity is hidden from the user. In the Main() method, we are simply calling the PrintReport() method and printing the output.

## Ways to implement Abstraction in C#

Abstraction in C# can be implemented through two main approaches.

- Abstract Class
- Interface

Here, we will discuss these ways of abstraction one by one.

### 1) Abstract Class

In the C# programming language, an [abstract class](https://www.tpointtech.com/abstract-class-in-c-sharp) is a class that cannot be instantiated on its own. It is declared using the abstract keyword. It is mainly used for [inheritance](https://www.tpointtech.com/c-sharp-inheritance) to access the features of the base class.

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-abstraction#)[](https://www.tpointtech.com/c-sharp-abstraction#)[](https://www.tpointtech.com/c-sharp-abstraction#)

1. public abstract class MyAbstractClass  
2. {  
3.     // Abstract method  
4.     public abstract void MyAbstractMethod();  
5.     // Non-abstract method  
6.     public void ConcreteMethod()  
7.     {  
8.         // block of code  
9.     }  
10.     // Abstract property  
11.     public abstract string AbstractProperty {get; set;}  
12. }  

In this syntax,

- **MyAbstractClass:** It defines the base class that cannot be used to create objects directly.
- **MyAbstractMethod():** It is an abstract method. It has no implementation here and must be overridden in any subclasses.
- **ConcreteMethod:** It is a non-abstract method with a defined implementation.
- **AbstractProperty:** It defines an abstract property, so any class that inherits must write its own get and set code.

**C# Abstract Class Example**

Let us take an example to illustrate the abstract class in C#.

### Example

[](https://www.tpointtech.com/c-sharp-abstraction#)[](https://www.tpointtech.com/c-sharp-abstraction#)[](https://www.tpointtech.com/c-sharp-abstraction#)

1. using System;     
2. // Abstract class  
3. abstract class animal  
4. {  
5.     // Abstract method  
6.     public abstract void sound();  
7.     // Normal method  
8.     public void sleep()  
9.     {  
10.         Console.WriteLine("sleeping now");  
11.     }  
12. }  
13. // Derived class  
14. class dog : animal  
15. {  
16.     // Implementing abstract method  
17.     public override void sound()  
18.     {  
19.         Console.WriteLine("Woof! Woof!");  
20.     }  
21. }  
22. class Tpoint  
23. {     
24.     static void Main()  
25.     {  
26.         dog d = new dog();  
27.         d.sound();   
28.         d.sleep();     
29.     }  
30. }  

**Output:**

Woof! Woof!
sleeping now

**Explanation:**

In this program, we define the abstract class named Animal that contains an abstract method sound() and a normal method sleep(). The Animal is an abstract class, hence it cannot be instantiated directly. The class dog is derived from an animal and accesses the features of the method sound () using the override keyword. In the main() method, we create an object of the dog class and call both the sound() method and the sleep() method to show the output using Console.WriteLine() function.

### 2) Interface

In the C# programming language, an [interface](https://www.tpointtech.com/c-sharp-interface) is like a contract that specifies the methods, properties, events, or indexer without providing their implementation. The interface keyword is used to define an interface. By default, all members of an interface are public, and access modifiers are not allowed on individual members.

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-abstraction#)[](https://www.tpointtech.com/c-sharp-abstraction#)[](https://www.tpointtech.com/c-sharp-abstraction#)

1. interface interface_name  
2. {  
3.     void method_name();  // method signature only  
4. }  

In this syntax,

- **Interface_name:** It represents the name of the interface.
- **Method_name:** It represents the name of the method.

**C# Example of Interface**

Let us take an example to define and use an interface in C#.

### Example

[](https://www.tpointtech.com/c-sharp-abstraction#)[](https://www.tpointtech.com/c-sharp-abstraction#)[](https://www.tpointtech.com/c-sharp-abstraction#)

1. using System;  
2. // Create an interface  
3. interface ISound  
4. {  
5.     void Sound(); // Method declaration  
6. }  
7. // Implement the interface in a class  
8. class Cat : ISound  
9. {  
10.     public void Sound()  
11.     {  
12.         Console.WriteLine("The cat meows.");  
13.     }  
14. }  
15. class App  
16. {  
17.     static void Main(string[] args)  
18.     {  
19.         ISound myPet = new Cat(); // Interface reference  
20.         myPet.Sound();          
21.     }  
22. }  

**Output:**

The cat meows.

**Explanation:**

In this example, we declare the ISound interface that contains the Sound() method, which is implemented by the cat class to print "The cat meows" using an ISound interface reference. In the main method, we are creating an object of the cat class, but we reference it using an ISound interface type and call the Sound () method to print the output.

## Difference between the Abstract Class and Interface

The main difference between the abstract class and interface in C# is as follows.

|Features|Abstract Class|Interface|
|---|---|---|
|**Definition**|A class that cannot be instantiated and may contain both abstract and concrete members.|A contract that defines only method signatures without implementation.|
|**Inheritance**|A class is allowed to inherit from only one abstract class.|A class can implement multiple interfaces at the same time.|
|**Access modifier**|It can have an access modifier like public, private, and protected.|The members are always public by default. It doesn't allow the access modifier.|
|**Constructor**|It is allowed to have a constructor.|It is not allowed to have a constructor.|

## Advantages of Abstraction in C#

Several advantages of data abstraction in C# are as follows.

**1) Hides Complex internal details**

Abstraction hides the complex inner workings of a program and only shows the parts that are needed. It ensures the internal code stays stable and secure.

**2) Allows internal Changes without affecting users**

Abstraction allows the developer to change the internal code or logic without affecting the users. It means the outer code remains the same if the internal code is updated or improved.

**3) Strengthen Security and Data Protection**

Abstraction shows only the important parts of the program and hides the sensitive or complex details. It helps in securing code by exposing only relevant data and methods.

**4) Simplifies Maintenance**

Abstraction shows only the important parts of the code, so it becomes easier to change or fix things without confusion.

## Conclusion

In conclusion, abstraction is a core principle of object-oriented programming in C#. It enables developers to manage complexity, hides unnecessary implementation details, and shows only the necessary details of an object. It helps in securing code by exposing only relevant data and methods.

## C# Abstraction FAQs

**1) What is abstraction in C#?**

In C#, an abstraction is the fundamental principle of object-oriented programming (OOP). It hides unnecessary implementation details and shows only the relevant functionality of an object. It simplifies the development process by reducing programming complexity and efforts. It also helps in securing code by exposing only relevant data and methods.

**2) Define an abstract Class in C#?**

In the C# programming language, an abstract class is a class that cannot be instantiated on its own. It is declared using the abstract keyword. It is mainly used for inheritance to access the features of the base class.

**3) Define an interface in C#?**

In C#, an interface is like a contract that specifies the methods, properties, events, or indexer without providing their implementation. The interface keyword is used to define an interface.

**4) How is abstraction achieved in C#?**

Abstract can be achieved through two main approaches.

- Abstract Class
- Interface

**5) Can we create an object of an abstract class?**

No, an abstract class cannot create the object directly in C#.