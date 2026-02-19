Encapsulation is a technique that encapsulates the data and methods into a single unit. It is used to make groups of data members and member functions inside a class. This encapsulated class contains getter and setter properties that are used to read and write data. It includes a feature that restricts direct access to data using the [access modifiers](https://www.tpointtech.com/c-sharp-access-modifiers), which provide controlled access.

![C# Encapsulation](https://images.tpointtech.com/csharp/images/c-sharp-encapsulation.png)

In [C# programming](https://www.tpointtech.com/c-sharp-tutorial), encapsulation enables data hiding, which means it hides the internal details of a class and exposes the essential details through public methods. It allows for preserving data and improving data security, which makes the code easier to maintain and understand.

### Syntax of Encapsulation:

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-encapsulation#)[](https://www.tpointtech.com/c-sharp-encapsulation#)[](https://www.tpointtech.com/c-sharp-encapsulation#)

1. class Classname  
2. {  
3.     private dataType field_name;   // Private field  

4.     public dataType Property_name   // Property (getter & setter)  
5.     {  
6.         get { return fieldName; }  
7.         set { fieldName = value; }  
8.     }  
9. }  

In this syntax,

- **class Classname:** It represents the name of the class.
- **private datatype field_name:** It represents the private field that contains the data type and the field name.
- **public dataType Property_name:** It represents the properties that are declared as public.
- **get:** It is used to read the value of the private field.
- **set:** It is used to assign and modify the value of a private field.

### C# Encapsulation Example:

Let us take an example to illustrate encapsulation in C#.

### Example

[](https://www.tpointtech.com/c-sharp-encapsulation#)[](https://www.tpointtech.com/c-sharp-encapsulation#)[](https://www.tpointtech.com/c-sharp-encapsulation#)

1. using System;  

2. namespace AccessSpecifiers    
3. {    
4.     class Employee    
5.     {    
6.         // Private fields (data hidden from outside)  
7.         private string id;    
8.         private string name;    
9.         private string email;    

10.         // Public properties (controlled access)  
11.         public string ID    
12.         {    
13.             get { return id; }    
14.             set { id = value; }    
15.         }    

16.         public string Name    
17.         {    
18.             get { return name; }    
19.             set { name = value; }    
20.         }    

21.         public string Email    
22.         {    
23.             get { return email; }    
24.             set { email = value; }    
25.         }    
26.     }    

27.     class Tpoint    
28.     {    
29.         static void Main(string[] args)    
30.         {    
31.             Employee emp = new Employee();    

32.             // Set values using properties  
33.             emp.ID = "101";    
34.             emp.Name = "George";    
35.             emp.Email = "George@example.com";    

36.             // Get values using properties  
37.             Console.WriteLine("ID = " + emp.ID);    
38.             Console.WriteLine("Name = " + emp.Name);    
39.             Console.WriteLine("Email = " + emp.Email);    
40.         }    
41.     }    
42. }  

**Output:**

ID = 101
Name = George
Email = George@example.com

**Explanation:**

In this example, we have taken an Employee class that hides its data members (id, name, email) by declaring them private. After that, we provide access to these fields via public properties (ID, Name, Email) that act as getters and setters. It ensures controlled access and protects the internal data while still allowing safe read/write operations from outside the class.

## Why We Need Encapsulation in C#

There are several case that shows the need for encapsulation in C#. Some of them are as follows:

- Encapsulation hides internal details and protects it against unauthorized access.
- It offers data control through validating in properties.
- It makes the code more maintainable because internal modifications do not impact external code.
- It enhances readability and maintains the program well-organized.

## Access Modifiers in C# Encapsulation

In C# programming, access modifiers specify how and where members of a class (fields, methods, properties, etc.) can be accessed. Access modifiers are an essential component of encapsulation, which is one of the four building blocks of Object-Oriented Programming (OOP). C# has mainly five types of access modifiers:

![C# Encapsulation](https://images.tpointtech.com/csharp/images/c-sharp-encapsulation2.png)

Here, we will discuss these access modifiers one by one.

### 1) Public Access Modifier

Public modifier is the most frequently accessed access specifier in C#. It can be accessed from anywhere, from inside and outside the class. Any other code can access the type or member within the same assembly or another assembly that refers to it.

**C# Public Access Modifier Example**

Let us take an example to illustrate the public access modifier in C# encapsulation.

### Example

[](https://www.tpointtech.com/c-sharp-encapsulation#)[](https://www.tpointtech.com/c-sharp-encapsulation#)[](https://www.tpointtech.com/c-sharp-encapsulation#)

1. using System;  
2. namespace CarExample  
3. {  
4.     class Car  
5.     {  
6.         public string Model;    

7.         public void ShowModel()  
8.         {  
9.             Console.WriteLine("Car Model: " + Model);  
10.         }  
11.     }  
12.     class Tpoint  
13.     {  
14.         static void Main()  
15.         {  
16.             Car car = new Car();  
17.             car.Model = "Porsche";     
18.             car.ShowModel();  
19.         }  
20.     }  
21. }  

**Output:**

Car Model: Porsche

**Explanation:**

In this example, we have taken the class Car. After that, we declare a Model field as public that can be accessed and modified directly from outside the Car class. Finally, we use the ShowModel() method that shows the car model that is defined in the main function.

### 2) Private Access Modifier

Private access specifier restricts its accessibility within the classes or structs where they are declared. These are not accessible outside the class, and it is the most restrictive access level.

**Private Access Modifier Example in C#**

Let us take an example to illustrate the private access modifier in C#.

### Example

[](https://www.tpointtech.com/c-sharp-encapsulation#)[](https://www.tpointtech.com/c-sharp-encapsulation#)[](https://www.tpointtech.com/c-sharp-encapsulation#)

1. using System;  
2. class BankAccount  
3. {  
4.     private double balance;    
5.     public void Deposit(double amount)  
6.     {  
7.         if (amount > 0)  
8.         {  
9.             balance += amount;  
10.         }  
11.     }  
12.     public void Withdraw(double amount)  
13.     {  
14.         if (amount > 0 && amount <= balance)  
15.         {  
16.             balance -= amount;  
17.         }  
18.         else  
19.         {  
20.             Console.WriteLine("Invalid withdraw amount!");  
21.         }  
22.     }  
23.     public double GetBalance()  
24.     {  
25.         return balance;  
26.     }  
27. }  
28. class Program  
29. {  
30.     static void Main()  
31.     {  
32.         BankAccount account = new BankAccount();  
33.         account.Deposit(5000);   
34.         Console.WriteLine("Balance: " + account.GetBalance());  
35.         account.Withdraw(1000);   
36.         Console.WriteLine("Balance after withdrawal: " + account.GetBalance());  
37.     }  
38. }  

**Output:**

Balance: 5000
Balance after withdrawal: 4000

**Explanation:**

In this example, we use a BankAccount class with a private balance field to prevent direct access. Public methods allow for depositing, withdrawing, and retrieving the balance. In the Main method, an account instance is created, funds are deposited and withdrawn, and the balance is displayed.

### 3) Protected Access Modifier

The members of a protected access specifier can be accessed within the same class and by the derived classes. It enables a child class to access member variables and member functions of its base class. It is commonly used to implement [inheritance](https://www.tpointtech.com/c-sharp-inheritance) with controlled access.

**Protected Access Modifier Example in C#**

Let us take an example to illustrate the protected access modifier in C#.

### Example

[](https://www.tpointtech.com/c-sharp-encapsulation#)[](https://www.tpointtech.com/c-sharp-encapsulation#)[](https://www.tpointtech.com/c-sharp-encapsulation#)

1. using System;  
2. namespace ProtectedExample  
3. {  
4.     class Person  
5.     {  
6.         protected string name;  
7.         public void SetName(string n)  
8.         {  
9.             name = n;  
10.         }  
11.     }  
12.     class Student : Person  
13.     {  
14.         public void ShowName()  
15.         {  
16.             Console.WriteLine("Student Name: " + name);   
17.         }  
18.     }  
19.     class Program  
20.     {  
21.         static void Main()  
22.         {  
23.             Student s = new Student();  
24.             s.SetName("Michael");  
25.             s.ShowName();  
26.         }  
27.     }  
28. }  

**Output:**

Student Name: Michael

**Explanation:**

In this example, we demonstrate the inheritance as well as encapsulation. We have taken a Person class that includes a protected name field, which cannot be accessed directly but can be used in the derived Student class. After that, the SetName method assigns a value to name, and ShowName displays it. In the Main method, a Student instance sets and displays the name.

### 5) Internal Access Modifier

The internal access modifiers provide access within the program where they are declared and accessed at the same assembly level, but not from another assembly.

**Internal Access Modifier Example in C#**

Let us take an example to illustrate the internal access modifier in C#.

### Example

[](https://www.tpointtech.com/c-sharp-encapsulation#)[](https://www.tpointtech.com/c-sharp-encapsulation#)[](https://www.tpointtech.com/c-sharp-encapsulation#)

1. using System;  
2. namespace Internal  
3. {  
4.     internal class Calculator  
5.     {  
6.         internal int Add(int a, int b)  
7.         {  
8.             return a + b;  
9.         }  
10.         internal int Multiply(int a, int b)  
11.         {  
12.             return a * b;  
13.         }  
14.     }  
15.     class Program  
16.     {  
17.         static void Main()  
18.         {  
19.             Calculator calc = new Calculator();  
20.             Console.WriteLine("Sum: " + calc.Add(6, 27));          
21.             Console.WriteLine("Product: " + calc.Multiply(4, 17));  
22.         }  
23.     }  
24. }  

**Output:**

Sum: 33
Product: 68

**Explanation:**

In this example, we create an internal class Calculator with addition and multiplication methods. As the class is internal, it is visible only within the same assembly. In the Main method, a Calculator object is instantiated and used to print addition and multiplication results.

### 5) Protected Internal Access Modifier

In C# programming, the protected internal access modifier is a combination of both the protected and internal access modifiers. The protected internal access modifier member can be accessed within the same assembly and in derived classes, even if those derived classes are in a different assembly.

**Protected Internal Access Modifier Example in C#**

Let us take an example to illustrate the protected internal access modifier in C#.

### Example

[](https://www.tpointtech.com/c-sharp-encapsulation#)[](https://www.tpointtech.com/c-sharp-encapsulation#)[](https://www.tpointtech.com/c-sharp-encapsulation#)

1. using System;  
2. namespace ProtectedInternal  
3. {  
4.     class Employee  
5.     {  
6.         protected internal string Name;  
7.         protected internal int Salary;  
8.         public void SetDetails(string name, int salary)  
9.         {  
10.             Name = name;  
11.             Salary = salary;  
12.         }  
13.     }  
14.     class Manager : Employee  
15.     {  
16.         public void ShowDetails()  
17.         {  
18.             Console.WriteLine("Manager Name: " + Name);  
19.             Console.WriteLine("Manager Salary: " + Salary);  
20.         }  
21.     }  
22.     class Program  
23.     {  
24.         static void Main()  
25.         {  
26.             Manager mgr = new Manager();  
27.             mgr.Name = "Jhonson";  
28.             mgr.Salary = 80000;  
29.             mgr.ShowDetails();  
30.             Employee emp = new Employee();  
31.             emp.SetDetails("David", 50000);  
32.             Console.WriteLine("Employee Name: " + emp.Name);  
33.             Console.WriteLine("Employee Salary: " + emp.Salary);  
34.         }  
35.     }  
36. }  

**Output:**

Manager Name: Jhonson
Manager Salary: 80000
Employee Name: David
Employee Salary: 50000

**Explanation:**

In this example, we have taken a class Employee and declared two members in it. After that, the Name and Salary members are accessible within the derived class (Manager), and directly from the Program class because they are in the same assembly.

## Comparison Table of Access Specifiers

The following table shows the comparison between these specifiers in C#.

|Specifier|Same Class|Derived Class (Same Assembly)|Other Classes (Same Assembly)|Other Assembly|
|---|---|---|---|---|
|**Public**|Yes|Yes|Yes|Yes|
|**Private**|Yes|No|No|No|
|**Protected**|Yes|Yes|No|No|
|**Internal**|Yes|Yes|Yes|No|
|**Protected Internal**|Yes|Yes|Yes|Yes (Derived only)|
|**Private Protected**|Yes|Yes (Same Assembly only)|No|No|

## C# Encapsulation through Properties

In C#, properties are the preferred method to use encapsulation. Rather than directly exposing fields, we can define them as private and give controlled access via get and set properties.

### C# Encapsulation Example Using Properties

Let us take an example to illustrate the encapsulation using properties in C#.

### Example

[](https://www.tpointtech.com/c-sharp-encapsulation#)[](https://www.tpointtech.com/c-sharp-encapsulation#)[](https://www.tpointtech.com/c-sharp-encapsulation#)

1. using System;  
2. class Employee  
3. {  
4.     private string name;  
5.     private int age;  
6.     public string Name  
7.     {  
8.         get { return name; }  
9.         set  
10.         {  
11.             if (!string.IsNullOrEmpty(value))  
12.                 name = value;  
13.             else  
14.                 Console.WriteLine("Invalid Name!");  
15.         }  
16.     }  
17.     public int Age  
18.     {  
19.         get { return age; }  
20.         set  
21.         {  
22.             if (value > 0 && value <= 60)  
23.                 age = value;  
24.             else  
25.                 Console.WriteLine("Invalid Age! Must be between 1 and 60.");  
26.         }  
27.     }  
28. }  
29. class Tpoint  
30. {  
31.     static void Main()  
32.     {  
33.         Employee emp = new Employee();  
34.         emp.Name = "Jackson";  
35.         emp.Age = 42;  
36.         Console.WriteLine("Name of the Employee : " + emp.Name);  
37.         Console.WriteLine("Age of the Employee : " + emp.Age);  
38.         emp.Name = "";       
39.         emp.Age = 87;       
40.     }  
41. }  

**Output:**

Name of the Employee : Jackson
Age of the Employee : 42
Invalid Name!
Invalid Age! Must be between 1 and 60.

**Explanation:**

In this example, we demonstrate the encapsulation through private members of name and age as fields and revealing them through public properties Name and Age. The properties utilize get to return values and set to verify for valid input before assignment. In the Main() function, values are supplied using properties, valid inputs are accepted and printed, and invalid ones print error messages.

## Advantages of Encapsulation in C#

Several advantages of encapsulation in C# are as follows:

- It stores internal object information securely by restricting direct manipulation and exposing only necessary data through properties or methods.
- It prevents unauthorized use and maintains internal data in a secure manner.
- We can change the internal structure of a class without affecting other sections of the program.
- It is easy to make and change code because internal changes don't interfere with external code that uses the class.
- Encapsulated classes are sealed; therefore, they can be used on different projects.

## Disadvantages of Encapsulation in C#

Several disadvantages of encapsulation in C# are as follows:

- If we add getters and setters for every field, it can lengthen the code and make it complex to read.
- Method/property data access may be slightly less efficient than direct field access.
- Poorly designed encapsulation can reduce its benefits.