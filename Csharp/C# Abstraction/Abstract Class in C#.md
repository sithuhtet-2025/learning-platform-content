C# abstract classes provide a strong means of defining a template for other classes, enforcing method implementation by providing the shared code. Abstract classes are employed where we need to create a common template for a class family, which allows derived classes to implement certain methods or properties. They are typically used to specify a general structure or behavior common to several derived classes without precluding those derived classes from presenting their particular implementations.

In C#, an abstract class is a class that is declared abstract. It can have abstract and non-abstract methods. It contains several fields, constructors, and methods. It cannot be instantiated directly. Its implementation must be provided by derived classes. Here, the derived class is forced to provide the implementation of all the abstract methods.

### Syntax

It has the following syntax:

[](https://www.tpointtech.com/abstract-class-in-c-sharp#)[](https://www.tpointtech.com/abstract-class-in-c-sharp#)[](https://www.tpointtech.com/abstract-class-in-c-sharp#)

1. abstract class ClassName  
2. {  
3.     // Abstract method (no body)  
4.     public abstract return_type MethodName(parameters);  
5.     // Normal method (with body)  
6.     public return_type NormalMethod(parameters)  
7.     {  
8.         // implementation  
9.     }  
10. }  

In this syntax,

- **abstract class ClassName:** It represents the name of the abstract class, which means that it cannot be instantiated directly.
- **return_type:** It represents the return type of the abstract method.
- **NormalMethod:** It represents the body that performed the implementation.

### C# Abstract Class Example

Let us take an example to illustrate the abstract class in C#.

### Example

[](https://www.tpointtech.com/abstract-class-in-c-sharp#)[](https://www.tpointtech.com/abstract-class-in-c-sharp#)[](https://www.tpointtech.com/abstract-class-in-c-sharp#)

1. using System;    
2. public abstract class Shape    
3. {    
4.     public abstract void draw();    
5. }    
6. public class Rectangle : Shape    
7. {    
8.     public override void draw()    
9.     {    
10.         Console.WriteLine("drawing rectangle...");    
11.     }    
12. }    
13. public class Circle : Shape    
14. {    
15.     public override void draw()    
16.     {    
17.         Console.WriteLine("drawing circle...");    
18.     }    
19. }    
20. public class TestAbstract    
21. {    
22.     public static void Main()    
23.     {    
24.         Shape s;    
25.         s = new Rectangle();    
26.         s.draw();    
27.         s = new Circle();    
28.         s.draw();    
29.     }    
30. }   

**Output:**

drawing rectangle...
drawing circle...

**Explanation:**

In this example, we declare an abstract class Shape with an abstract method draw(). After that, we take the Rectangle and Circle classes that extend Shape and implement their draw(). In the main() method, a Shape reference is used to call draw() on both Rectangle and Circle objects, which prints out their respective messages.

### C# Abstract Class Example with Constructors for Initialization

Let us take another example to illustrate the abstract classes in C# using Constructors.

### Example

[](https://www.tpointtech.com/abstract-class-in-c-sharp#)[](https://www.tpointtech.com/abstract-class-in-c-sharp#)[](https://www.tpointtech.com/abstract-class-in-c-sharp#)

1. using System;  

2. abstract class Employee  
3. {  
4.     public string Name { get; set; }  
5.     public double Salary { get; set; }  

6.     public abstract void EmpName();  

7.     public void EmpSalary()  
8.     {  
9.         Console.WriteLine($"Salary: {Salary}");  
10.     }  
11. }  

12. class Emp1 : Employee  
13. {  
14.     public Emp1()  
15.     {  
16.         Name = "Johnson";  
17.         Salary = 25000;  
18.     }  

19.     public override void EmpName()  
20.     {  
21.         Console.WriteLine($"Name: {Name}");  
22.     }  
23. }  

24. class Emp2 : Employee  
25. {  
26.     public Emp2()  
27.     {  
28.         Name = "Michael";  
29.         Salary = 30000;  
30.     }  

31.     public override void EmpName()  
32.     {  
33.         Console.WriteLine($"Name: {Name}");  
34.     }  
35. }  

36. class Tpoint  
37. {  
38.     static void Main(string[] args)  
39.     {  
40.         Employee emp1 = new Emp1();  
41.         emp1.EmpName();  
42.         emp1.EmpSalary();  

43.         Employee emp2 = new Emp2();  
44.         emp2.EmpName();  
45.         emp2.EmpSalary();  
46.     }  
47. }  

**Output:**

Name: Johnson
Salary: 25000
Name: Michael
Salary: 30000

**Explanation:**

In this example, we have taken a class Employee that acts as a base class, which contains several common properties and methods. After that, we take two derived classes, Emp1 and Emp2, that set different names and salaries using constructors and override the abstract method EmpName. At runtime, every detail of the employee is displayed, which shows the shared common functionality of abstract classes while enabling specific implementations.

## Abstract Method

A method that is declared abstract and has no body is called an abstract method. It can be declared inside the abstract class only. Its implementation must be provided by derived classes.

**Syntax:**

It has the following syntax:

[](https://www.tpointtech.com/abstract-class-in-c-sharp#)[](https://www.tpointtech.com/abstract-class-in-c-sharp#)[](https://www.tpointtech.com/abstract-class-in-c-sharp#)

1. access-modifier abstract return-type MethodName(parameters);  

In this syntax,

- **Access-modifier:** It represents the visibility of the abstract method.
- **Abstract:** It is used to define the method as abstract.
- **Return-type:** It is used to define the data type that the method should return.
- **MethodName:** It represents the abstract method name.

An abstract method in C# is internally a virtual method, so it can be overridden by the derived class. We cannot use static and virtual modifiers in an abstract method declaration.

### C# Abstract Method Example

Let us take an example to illustrate the abstract method in C#.

### Example

[](https://www.tpointtech.com/abstract-class-in-c-sharp#)[](https://www.tpointtech.com/abstract-class-in-c-sharp#)[](https://www.tpointtech.com/abstract-class-in-c-sharp#)

1. using System;  
2. abstract class Animal  
3. {  
4.     public abstract void Speak();     
5.     public abstract void Drink();       
6. }  
7. class Cat : Animal  
8. {  
9.     public override void Speak()  
10.     {  
11.         Console.WriteLine("Cat says: Meow! Meow!");  
12.     }  
13.     public override void Drink()  
14.     {  
15.         Console.WriteLine("Cat is drinking milk.");  
16.     }  
17. }  
18. class Tpoint  
19. {  
20.     static void Main()  
21.     {  
22.         Animal myCat = new Cat();  
23.         myCat.Speak();  
24.         myCat.Drink();  
25.     }  
26. }  

**Output:**

Cat says: Meow! Meow!
Cat is drinking milk.

**Explanation:**

In this example, we take an abstract class Animal with two abstract methods Speak() and Drink(), which has no body. After that, the Cat class is inherited from Animal and overrides both methods with its implementation. In the main() function, an Animal reference is used to a Cat object, and invoking Speak() and Drink() invokes the overridden methods, which demonstrate the Cat's behavior.

### C# Abstract Method Example for Bank Account Details

Let us take an example to illustrate the abstract method for Bank Account Details in C#.

### Example

[](https://www.tpointtech.com/abstract-class-in-c-sharp#)[](https://www.tpointtech.com/abstract-class-in-c-sharp#)[](https://www.tpointtech.com/abstract-class-in-c-sharp#)

1. using System;  

2. abstract class BankAcc  
3. {  
4.     public string AccHolder { get; set; }  
5.     public double Balance { get; protected set; }  

6.     // using Abstract methods  
7.     public abstract void Deposit(double amount);  
8.     public abstract void Withdraw(double amount);  
9. }  

10. class SavingsAcc : BankAcc  
11. {  
12.     public SavingsAcc(string holder, double initialBal)  
13.     {  
14.         AccHolder = holder;  
15.         Balance = initialBal;  
16.     }  

17.     public override void Deposit(double amount)  
18.     {  
19.         Balance += amount;  
20.         Console.WriteLine($"{amount}Rs deposited in Savings Account.");  
21.     }  

22.     public override void Withdraw(double amount)  
23.     {  
24.         if (Balance >= amount)  
25.         {  
26.             Balance -= amount;  
27.             Console.WriteLine($"{amount}Rs withdrawn from Savings Account.");  
28.         }  
29.         else  
30.         {  
31.             Console.WriteLine("Insufficient balance.");  
32.         }  
33.     }  
34. }  

35. class Tpoint  
36. {  
37.     static void Main(string[] args)  
38.     {  
39.         BankAcc acc = new SavingsAcc("Robert", 1800);  
40.         acc.Deposit(600);   // Calls overridden Deposit  
41.         acc.Withdraw(300);  // Calls overridden Withdraw  

42.         Console.WriteLine($"Total Balance: {acc.Balance}");  
43.     }  
44. }  

**Output:**

600Rs deposited in Savings Account.
300Rs withdrawn from Savings Account.
Total Balance: 2100

**Explanation:**

In this example, we have taken an abstract class that defines the structure for a bank account with two abstract methods, Deposit and Withdraw. After that, we take a derived class SavingsAcc that gives concrete implementations of these methods to handle deposits and withdrawals. In the main method, we create an object of the SavingsAcc class where we make transactions and show the updated balance.

## Usage of Abstract Class in C#

Several uses of abstract class in C# are as follows:

- We can create multiple versions of the component because versioning is not a problem when dealing with abstract classes.
- We can add properties or methods to an abstract class without recompiling, and all the inheriting classes are updated with the change automatically.
- It is required to supply default behaviors along with general behaviors that several derived classes will have in common and be able to override.

## Difference between Abstract Class and Interface

There are several main differences between an Abstract Class and an Interface in C#. Some main differences are as follows:

|Features|Abstract Class|Interface|
|---|---|---|
|**Definition**|Abstract class is a partially implemented class that defines both what and how a class should perform operations.|An interface is a contract that defines only method signatures, properties, events, and indexers, but it has no implementation.|
|**Instantiation**|It cannot be instantiated.|It cannot be instantiated.|
|**Access Modifiers**|It uses all access modifiers.|It doesn't use an access modifier because all classes are public by default.|
|**Members**|It contains several fields, constructors, and methods.|It contains only method signatures, events, properties, and indexers.|
|**Inheritance**|It uses only single inheritance.|It can implement multiple inheritance.|
|**Implementation**|It can provide a default implementation.|It has no implementation.|

## Benefits of Abstract Class in C#

There are several benefits of the abstract class in C#. Some of them are as follows:

- **Promotes code reusability:** Abstract classes enable us to specify common behavior, methods, and properties that may be shared by many derived classes.
- **Acts as a template for derived classes:** These are a template or blueprint for derived classes.
- **Supports inheritance and polymorphism:** Abstract classes allow polymorphism so that derived classes can be viewed as instances of the abstract class.
- **Specifies contracts using abstract methods:** Abstract classes specify contracts using abstract methods, which are implemented by derived classes.
- **Supports code modularization and organization:** Abstract classes allow code to be organized and support modularity.
- **Allows extensibility in the future:** Abstract classes are meant to be extended by derived classes.

## Disadvantages of Abstract Class in C#

There are several disadvantages of the abstract class in C#. Some of them are as follows:

- **Tight coupling:** Abstract classes introduce an element of coupling between the base abstract class and its subclasses. It suggests that changes to the abstract class could impact all subclasses.
- **Incomplete implementation:** Abstract classes usually contain abstract methods, which need to be implemented in their derived classes.
- **Limited flexibility:** When an abstract class is declared, its struct and contracts become more rigid than those of interfaces.
- **Object-oriented design issues:** In certain situations, abstract classes can break some of the principles of object-oriented design, including the Single Responsibility Principle (SRP) or the Interface Segregation Principle (ISP).

## Conclusion

In conclusion, the C# abstract class serves as a base template that can contain both fully implemented members and abstract members that lack a body. Subclasses are required to implement the abstract members. Abstract classes cannot be instantiated directly, which makes them ideal for providing common functionality while ensuring that certain methods are implemented in the subclasses.