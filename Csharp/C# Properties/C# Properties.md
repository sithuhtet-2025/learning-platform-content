
In the C# programming language, properties are a special type of class member that are used to provide an efficient technique to read, write, and compute the value of a private field. C# Properties are an extension of fields and are accessed like fields. These properties act as a bridge between fields and methods, which provide controlled access to class data.

![C# Properties](https://images.tpointtech.com/csharp/images/c-sharp-properties.png)

Properties are commonly utilized in OOP because they support [encapsulation](https://www.tpointtech.com/c-sharp-encapsulation) and [abstraction](https://www.tpointtech.com/c-sharp-abstraction). Properties have accessors that are used to set, get, or compute their values. These do not contain any storage location.

## Why use Properties in C#?

There are several uses of C# properties. Some of them are as follows:

- C# Properties can have read-only or write-only access.
- Properties can protect class member fields using encapsulation, which is used to hide the implementation details.
- These can be used to access private data members of the class from another using accessors.
- These are used to protect class members so that another class cannot use these members.
- These properties are used to enhance the code readability and maintainability.

### Syntax:

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-properties#)[](https://www.tpointtech.com/c-sharp-properties#)[](https://www.tpointtech.com/c-sharp-properties#)

1. class Class_Name  
2. {  
3.     private datatype field_Name;  // Private field  

4.     public datatype Property_Name  
5.     {  
6.         get {return field_Name;}   // using Getter method  
7.         set {field_Name = value;}  // using Setter method  
8.     }  
9. }  

In this syntax,

- **Class_Name:** It represents the name of the Class.
- **get:** It is only used to access (read) the property value.
- **set:** It is used to assign (write-only) the new value to the property.
- **value:** It is used to hold the value that is assigned by the user.

### Simple Example of Properties

Let us take an example to illustrate the properties in C#.

### Example

[](https://www.tpointtech.com/c-sharp-properties#)[](https://www.tpointtech.com/c-sharp-properties#)[](https://www.tpointtech.com/c-sharp-properties#)

1. using System;  

2. class Employee  
3. {  
4.     private string name;   // using Private field  

5.     // using Property  
6.     public string Name  
7.     {  
8.         get { return name; }  
9.         set { name = value; }  
10.     }  
11. }  

12. class Tpoint  
13. {  
14.     static void Main()  
15.     {  
16.         Employee emp = new Employee();  
17.         emp.Name = "Michael";         // Using property setter  
18.         Console.WriteLine(emp.Name); // Using property getter  
19.     }  
20. }  

**Output:**

Michael

**Explanation:**

In this example, we have taken a property Name that provides controlled access to the private field name. After that, we have taken the set accessor to assign the value "Michael", and the get accessor is used to retrieve this value.

## Accessor in C#

In the [C# programming language](https://www.tpointtech.com/c-sharp-tutorial), an accessor is a block of code inside a property that specifies how a property interacts with a class's private field. Accessors enforce encapsulation by regulating how class fields are read or written from outside the class. It ensures that the internal data remains secure and may be accessed in a controlled manner.

## Types of Accessors

In C#, there are mainly two types of accessors. These are as follows:

![C# Properties](https://images.tpointtech.com/csharp/images/c-sharp-properties2.png)

Here, we will discuss these accessors one by one.

### 1) Get Accessor

In the C# programming language, a get accessor returns the private field's value. It is useful when we want other portions of the application to can read the value without necessarily changing it.

**C# Get Accessor Example**

Let us take an instance to demonstrate the get accessor in C#.

### Example

[](https://www.tpointtech.com/c-sharp-properties#)[](https://www.tpointtech.com/c-sharp-properties#)[](https://www.tpointtech.com/c-sharp-properties#)

1. using System;  
2. class Employee  
3. {  
4.     private int employeeId;  
5.     public Employee(int id)  
6.     {  
7.         employeeId = id;  
8.     }  
9.     public int EmployeeId  
10.     {  
11.         get  
12.         {  
13.             return employeeId;  
14.         }  
15.     }  
16. }  
17. class Tpoint  
18. {  
19.     static void Main()  
20.     {  
21.         Employee emp = new Employee(101);  
22.         Console.WriteLine("The Employee ID is: " + emp.EmployeeId);  
23.     }  
24. }  

**Output:**

The Employee ID is: 101

**Explanation:**

In this example, we have taken a property EmployeeId that enables access to the private field employeeId but does not allow modification from outside the class. After that, the constructor initializes the field with 101, and the get accessor retrieves and prints it

### 2) Set Accessor

In C#, a set accessor specifies a value for a private field. It is called whenever we assign a value to a property. The term value is used within the set block to represent the incoming data.

**C# Set Accessor Example**

Let us take an instance to demonstrate the set accessor in C#.

### Example

[](https://www.tpointtech.com/c-sharp-properties#)[](https://www.tpointtech.com/c-sharp-properties#)[](https://www.tpointtech.com/c-sharp-properties#)

1. using System;  
2. class User  
3. {  
4.     private string password;  
5.     public string Password  
6.     {  
7.         set  
8.         {  
9.             password = value;  
10.         }  
11.     }  
12.     public void ShowMaskedPassword()  
13.     {  
14.         Console.WriteLine("Password is set (hidden for security).");  
15.     }  
16. }  
17. class Program  
18. {  
19.     static void Main()  
20.     {  
21.         User user = new User();  
22.         user.Password = "SecurePass123";    
23.         user.ShowMaskedPassword();  
24.     }  
25. }  

**Output:**

Password is set (hidden for security).

**Explanation:**

In this example, we have taken a Password attribute that allows us to specify a private field, and the program confirms it without revealing the password. It maintains security by restricting external access to sensitive data while allowing input.

## Accessor Accessibility in C#

C# additionally allows [access modifiers](https://www.tpointtech.com/c-sharp-access-modifiers) (such as private, protected) to be applied directly to accessors under certain rules:

- Only properties having both get and set capabilities can have distinct access levels for each.
- [Interfaces](https://www.tpointtech.com/c-sharp-interface) do not allow accessor modifiers.
- The accessor modifier of overridden properties must match that of the base property.

## Types of Properties

C# has six primary types of properties, each serving a distinct access requirement for encapsulated fields.

![C# Properties](https://images.tpointtech.com/csharp/images/c-sharp-properties3.png)

Here, we will discuss these properties one by one.

### 1) Read-Only Property

In C# programming, a Read-Only Property provides controlled access to the value of a private field while preventing alteration from outside the class. It contains only the get accessor.

**Syntax:**

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-properties#)[](https://www.tpointtech.com/c-sharp-properties#)[](https://www.tpointtech.com/c-sharp-properties#)

1. public DataType PropertyName  
2. {  
3.     get  
4.     {  
5.         return _fieldName;  
6.     }  
7. }  

**C# Read-Only Property Example**

Let us take an example to illustrate the Read-only property in C#.

### Example

[](https://www.tpointtech.com/c-sharp-properties#)[](https://www.tpointtech.com/c-sharp-properties#)[](https://www.tpointtech.com/c-sharp-properties#)

1. using System;    
2.        public class Employee    
3.         {    
4.             private static int counter;    

5.             public Employee()    
6.             {    
7.                 counter++;    
8.             }    
9.             public static int Counter    
10.             {    
11.                 get    
12.                 {    
13.                     return counter;    
14.                 }    
15.              }    
16.        }    
17.        class TestEmployee{    
18.            public static void Main(string[] args)    
19.             {    
20.                 Employee e1 = new Employee();    
21.                 Employee e2 = new Employee();    
22.                 Employee e3 = new Employee();    
23.                 //e1.Counter = 10;//Compile Time Error: Can't set value    

24.                 Console.WriteLine("No. of Employees: " + Employee.Counter);    
25.             }    
26.         }    

**Output:**

No. of Employees: 3

**Explanation:**

In the Employee class, the Counter property is read-only and only has a get accessor that returns a static field that counts the number of Employee objects produced.

### 2) Write-Only Property

In C# programming, the Write-Only Property allows us to assign a value to a field but prevents external readers from accessing it. It contains only the set accessor.

**Syntax:**

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-properties#)[](https://www.tpointtech.com/c-sharp-properties#)[](https://www.tpointtech.com/c-sharp-properties#)

1. public DataType PropertyName  
2. {  
3.     set  
4.     {  
5.         _fieldName = value;  
6.     }  
7. }  

**C# Write-Only Property Example**

Let us take an example to illustrate the Write-Only property in C#.

### Example

[](https://www.tpointtech.com/c-sharp-properties#)[](https://www.tpointtech.com/c-sharp-properties#)[](https://www.tpointtech.com/c-sharp-properties#)

1. using System;  
2. class UserAccount  
3. {  
4.     private string passwordHash;  
5.     public string Password  
6.     {  
7.         set  
8.         {  
9.            passwordHash = Convert.ToBase64String(System.Text.Encoding.UTF8.GetBytes(value));  
10.         }  
11.     }  
12.     public void ShowHashedPassword()  
13.     {  
14.         Console.WriteLine("Hashed Password (internal use): " + passwordHash);  
15.     }  
16. }  
17. class Program  
18. {  
19.     static void Main()  
20.     {  
21.         UserAccount user = new UserAccount();  
22.         user.Password = "Secure123";  
23.         user.ShowHashedPassword();  
24.     }  
25. }  

**Output:**

Hashed Password (internal use): U2VjdXJlMTIz

**Explanation:**

In this example, we have taken the UserAccount class that defines a write-only property, Password, with a set accessor that encodes and stores the password internally. It avoids external programs from accessing critical data, which guarantees security while allowing for regulated input.

### 3) Read-Write Property

The Read-Write Property is the most popular type of C# property. It implements both get and set accessors, which allow for both reading and writing.

**Syntax:**

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-properties#)[](https://www.tpointtech.com/c-sharp-properties#)[](https://www.tpointtech.com/c-sharp-properties#)

1. public DataType PropertyName  
2. {  
3.     get  
4.     {  
5.         return _fieldName;  
6.     }  
7.     set  
8.     {  
9.         _fieldName = value;  
10.     }  
11. }  

**C# Read-Only Property Example**

Let us take an example to illustrate the Read-Only property in C#.

### Example

[](https://www.tpointtech.com/c-sharp-properties#)[](https://www.tpointtech.com/c-sharp-properties#)[](https://www.tpointtech.com/c-sharp-properties#)

1. using System;  
2. class Employee  
3. {  
4.     private int salary;  
5.     public string Name   
6.     {  
7.         get; set;  
8.     }  
9.     public int Salary  
10.     {  
11.         get   
12.         {  
13.             return salary;   
14.         }  
15.         set  
16.         {  
17.             if (value >= 30000)  
18.                 salary = value;  
19.             else  
20.                 Console.WriteLine("Salary must be at least 30000.");  
21.         }  
22.     }  
23.     public void Display()  
24.     {  
25.         Console.WriteLine($"Employee Name is: {Name}\nEmployee Salary is: {Salary}");  
26.     }  
27. }  
28. class Tpoint  
29. {  
30.     static void Main()  
31.     {  
32.         Employee emp = new Employee();  
33.         emp.Name = "Alice";  
34.         emp.Salary = 25000;    
35.         emp.Salary = 45000;    
36.         emp.Display();  
37.     }  
38. }  

**Output:**

Salary must be at least 30000.
Employee Name is: Alice
Employee Salary is: 45000

**Explanation:**

In this example, we have taken the Name property, which is an auto-implemented property that allows both reading and writing directly. After that, the Salary property uses a private backing field and get/set accessors; the set accessor enforces a rule that salary must be at least 30,000, otherwise it displays a warning.

### 4) Auto-Implemented property

In C# programming, when the property accessors do not require any additional logic, an Auto-Implemented Property simplifies the syntax. The compiler creates an implicit anonymous backing field.

**Syntax**

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-properties#)[](https://www.tpointtech.com/c-sharp-properties#)[](https://www.tpointtech.com/c-sharp-properties#)

1. public DataType PropertyName   
2. { get; set; }  

**C# Auto-Implemented Property Example**

Let us take an example to illustrate the auto-implemented property in C#.

### Example

[](https://www.tpointtech.com/c-sharp-properties#)[](https://www.tpointtech.com/c-sharp-properties#)[](https://www.tpointtech.com/c-sharp-properties#)

1. using System;  
2. class Book  
3. {  
4.     public string Title { get; set; }  
5.     public string Author { get; set; }  
6.     public int YearPublished { get; set; }  
7.     public void PrintDetails()  
8.     {  
9.         Console.WriteLine($"The title of the book is: {Title}\nThe author's name is: {Author}\nThe year of publication is: {YearPublished}");  
10.     }  
11. }  
12. class Program  
13. {  
14.     static void Main()  
15.     {  
16.         Book book = new Book  
17.         {  
18.             Title = "C# In Depth",  
19.             Author = "Jon Skeet",  
20.             YearPublished = 2023  
21.         };  
22.         book.PrintDetails();  
23.     }  
24. }  

**Output:**

The title of the book is: C# In Depth
The author's name is: Jon Skeet
The year of publication is: 2023

**Explanation:**

In this example, the Title, Author, and YearPublished properties of the Book class are auto-implemented, which provides for straightforward read-write access without the need for explicit backing fields.

### 5) Static Property

In C#, a static property is assigned to the class as a whole, not to any individual instance. It signifies that the static property's value is shared by all objects of the class. If we want to use static properties, we must also make the backing field static, if one is present. Static properties are frequently utilized in utility classes, global settings, and singletons.

**Syntax**

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-properties#)[](https://www.tpointtech.com/c-sharp-properties#)[](https://www.tpointtech.com/c-sharp-properties#)

1. class ClassName  
2. {  
3.     private static DataType fieldName;  
4.     public static DataType PropertyName  
5.     {  
6.         get  
7.         {  
8.             return fieldName;  
9.         }  
10.         set  
11.         {  
12.             fieldName = value;  
13.         }  
14.     }  
15. }  

**C# Static Property Example**

Let us take an example to illustrate the static property in C#.

### Example

[](https://www.tpointtech.com/c-sharp-properties#)[](https://www.tpointtech.com/c-sharp-properties#)[](https://www.tpointtech.com/c-sharp-properties#)

1. using System;  
2. class Bank  
3. {  
4.     public static decimal InterestRate { get; set; }  
5.     public void DisplayInterestRate()  
6.     {  
7.         Console.WriteLine("Current Interest Rate: " + InterestRate + "%");  
8.     }  
9. }  
10. class Program  
11. {  
12.     static void Main()  
13.     {  
14.         Bank.InterestRate = 4.5m;  
15.         Bank bank1 = new Bank();  
16.         Bank bank2 = new Bank();  
17.         bank1.DisplayInterestRate();    
18.         bank2.DisplayInterestRate();     
19.         Bank.InterestRate = 5.0m;  
20.         bank1.DisplayInterestRate();     
21.         bank2.DisplayInterestRate();     
22.     }  
23. }  

**Output:**

Current Interest Rate: 4.5%
Current Interest Rate: 4.5%
Current Interest Rate: 5.0%
Current Interest Rate: 5.0%

**Explanation:**

In this example, we have taken a static property that calls InterestRate in the Bank class, which is shared by all instances of the class. After that, the output shows that changing the static property affects all objects.

### 6) Abstract Property

In the C# programming language, an abstract property is a property that is stated but not implemented in an abstract class or interface. It requires the derived class to override and implement the property accessors. It promotes consistency in structure while allowing subclasses to have unique behavior.

**C# Abstract Property Example**

Let us take an example to demonstrate the abstract property in C#.

### Example

[](https://www.tpointtech.com/c-sharp-properties#)[](https://www.tpointtech.com/c-sharp-properties#)[](https://www.tpointtech.com/c-sharp-properties#)

1. using System;  
2. abstract class Shape  
3. {  
4.     public abstract double Area { get; }  
5.     public abstract double Perimeter { get; }  
6. }  
7. class Circle : Shape  
8. {  
9.     private double rad;  

10.     public Circle(double rad)  
11.     {  
12.         this.rad = rad;  
13.     }  
14.     public override double Area  
15.     {  
16.         get { return Math.PI * rad * rad; }  
17.     }  
18.     public override double Perimeter  
19.     {  
20.         get { return 2 * Math.PI * rad; }  
21.     }  
22. }  
23. class Tpoint  
24. {  
25.     static void Main()  
26.     {  
27.         Circle circle = new Circle(5);  
28.         Console.WriteLine("Circle Area: " + circle.Area);  
29.         Console.WriteLine("Circle Perimeter: " + circle.Perimeter);  
30.     }  
31. }  

**Output:**

Circle Area: 78.5398163397448
Circle Perimeter: 31.4159265358979

**Explanation:**

In this example, we have taken the abstract class Shape, which declares two abstract properties: area and perimeter, but does not implement them. The Circle class derives from Shape and implements concrete logic for these properties, dependent on the radius.

## Conclusion

In conclusion, C# properties provide an efficient method to access and manage class fields while maintaining the principles of encapsulation and abstraction. They allow us to control how data is read, written, or computed without exposing internal implementation details. With the help of different types of properties, C# offers flexibility to handle various scenarios. After understanding C# properties, we can write code that is more secure, maintainable, and easier to understand.