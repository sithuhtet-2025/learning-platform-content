
In the C# programming language, a constructor is a class-specific method that is called automatically whenever an object of that class is created. It holds the set of instructions that are implemented during object creation. The main work of a constructor is to initialize the class's data members and prepare the object for use.

Constructors have several features in contrast to conventional methods in C#. Some of them are as follows:

- The constructor class name should be the same as the class.
- It has no return type.
- When the new keyword is used to create an object, this function is automatically invoked.
- It cannot be abstract and virtual.

### Syntax of a Constructor

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-constructor#)[](https://www.tpointtech.com/c-sharp-constructor#)[](https://www.tpointtech.com/c-sharp-constructor#)

1. class Demo  
2. {  
3.     //Class name "Demo"  
4.     // Constructor of "Demo" class.  
5.     public Demo()   
6.   {  
7.         // Initialization code write here  
8.     }  
9. }  

## Calling the Constructor

If we want to call the constructor, we can use the following syntax:

[](https://www.tpointtech.com/c-sharp-constructor#)[](https://www.tpointtech.com/c-sharp-constructor#)[](https://www.tpointtech.com/c-sharp-constructor#)

1. Demo d1 = new Demo();  
2. // Demo constructor called and d1 object created.  

**C# Constructor Example**

Let us take an example to illustrate the constructor in C#.

### Example

[](https://www.tpointtech.com/c-sharp-constructor#)[](https://www.tpointtech.com/c-sharp-constructor#)[](https://www.tpointtech.com/c-sharp-constructor#)

1. using System;  

2. class Employee  
3. {  
4.     // Fields  
5.     public string Name;  
6.     public int Age;  
7.     public int Salary;  

8.     // Constructor  
9.     public Employee(string name, int age, int salary)  
10.     {  
11.         Name = name;  
12.         Age = age;  
13.         Salary = salary;  
14.     }  

15.     // Method to display employee details  
16.     public void DisplayInfo()  
17.     {  
18.         Console.WriteLine("Employee Name: " + Name);  
19.         Console.WriteLine("Employee Age: " + Age);  
20.         Console.WriteLine("Employee Salary: " + Salary);  
21.     }  
22. }  

23. class Program  
24. {  
25.     static void Main()  
26.     {  
27.         // Creating object and calling constructor  
28.         Employee emp1 = new Employee("Jhonson", 25, 45000);  
29.         emp1.DisplayInfo();  
30.     }  
31. }  

**Output:**

Employee Name: Jhonson
Employee Age: 25
Employee Salary: 45000

**Explanation:**

In this example, we have taken the constructor Employee(string name, int age, int salary) and initializes it with the fields Name, Age, and Salary when an object is created. After that, the emp1 object is initialized with specific values, and the DisplayInfo() method prints the employee's details.

## Important Points to Remember About Constructors in C#

There are several points to remember about a constructor in C#. Some of them are as follows:

- **Same Name as Class:**The constructor must have the same name as the class where it is defined.
- **Automatic Invocation:** It is called automatically when an object is formed using a new keyword.
- **Overloading is permitted:** A class may have numerous constructors, each contains a different set of parameters.
- **Access Modifiers Allowed:** Constructors can be declared with access modifiers, which control who can construct objects from that class.
- **Static Constructor Rules:** A class can have only one static constructor, which is used to initialize static members. It only runs once during the entire class.
- **If no constructors are defined:** If no constructor is explicitly defined, the C# compiler will create a default parameterless constructor.

## Types of Constructors

There are mainly 5 types of constructors in C#. These are as follows:

![C# Constructor](https://images.tpointtech.com/csharp/images/c-sharp-constructor.png)

Now, we will discuss these constructors one by one.

## Default Constructor

In the [C# programming language](https://www.tpointtech.com/c-sharp-tutorial), a default constructor doesn't require any parameters. If the class does not have any other constructors declared, the compiler will automatically give a default constructor. It is most commonly utilized to set default or fixed values for objects.

### Features of the Default Constructor:

There are several features of the default constructor. Some of them are as follows:

- It doesn't require any parameters.
- When a new object is created, this function is automatically invoked.
- It can be defined explicitly.

### C# Default Constructor Example

Let us take an example to illustrate the default constructor in C#.

### Example

[](https://www.tpointtech.com/c-sharp-constructor#)[](https://www.tpointtech.com/c-sharp-constructor#)[](https://www.tpointtech.com/c-sharp-constructor#)

1. using System;  
2. class Student  
3. {  
4.     public string stu_Name;  
5.     // Default Constructor called.  
6.     public Student()  
7.     {  
8.         stu_Name = "Joseph";  
9.     }  
10.     static void Main()  
11.     {  
12.         Student s = new Student();  
13.         Console.WriteLine("The name of the student is: " + s.stu_Name);  
14.     }  
15. }  

**Output:**

The name of the student is: Joseph

**Explanation:**

In this example, when we create an object, the default constructor Student() is immediately invoked, and the default name is "Joseph". It requires no parameters and helps assign fixed starting values to class members.

## Parameterized Constructor

In the C# programming language, a parameterized constructor is a constructor that takes at least one parameter to initialize an object with definite values during its creation. It accepts arguments and assigns them to class fields.

### Features of Parameterized Constructor:

Several features of parameterized constructor in C# are as follows:

- It allows for greater flexibility when initializing objects.
- Constructor overloading enables the creation of multiple parameterized constructors.

### C# Parameterized Constructor Example

Let us take an example to illustrate the parameterized constructor in C#.

### Example

[](https://www.tpointtech.com/c-sharp-constructor#)[](https://www.tpointtech.com/c-sharp-constructor#)[](https://www.tpointtech.com/c-sharp-constructor#)

1. using System;  
2. class Student  
3. {  
4.     public string name;  
5.     public int age;  
6.     // Parameterized Constructor called.  
7.     public Student(string student_Name, int student_Age)  
8.     {  
9.         name = student_Name;  
10.         age = student_Age;  
11.     }  
12.     static void Main()  
13.     {  
14.         Student stu = new Student("Joseph", 26);  
15.         Console.WriteLine("The name of the student is: " + stu.name);  
16.         Console.WriteLine("The age of the student is: " + stu.age);  
17.     }  
18. }  

**Output:**

The name of the student is: Joseph
The age of the student is: 26

**Explanation:**

In this example, we have taken a constructor of the Student class that accepts names, ages, and fields, which are initialized with values supplied during object creation. It enables the dynamic object initialization using either user-defined or runtime data.

## Copy Constructor

A copy constructor generates a new object by copying the values from another object. C# does not have a built-in copy constructor, such as C++. If we need to duplicate an object, we can manually create a copy constructor.

### Features of the Copy Constructor:

Several features of the copy constructor in C# are as follows:

- It takes an object of the same class as a parameter to copy its data.
- When deep copying is necessary, it is extremely useful.

### C# Copy Constructor Example

Let us take an example to illustrate the copy constructor in C#.

### Example

[](https://www.tpointtech.com/c-sharp-constructor#)[](https://www.tpointtech.com/c-sharp-constructor#)[](https://www.tpointtech.com/c-sharp-constructor#)

1. using System;  
2. class Car  
3. {  
4.     public string name;  
5.     // Parameterized Constructor called.  
6.     public Car(string n)  
7.     {  
8.         name = n;  
9.     }  
10.     // Copy Constructor called.  
11.     public Car(Car c)  
12.     {  
13.         name = c.name;  
14.     }  
15.     static void Main()  
16.     {  
17.         Car car1 = new Car("TATA");  
18.         Car car2 = new Car(car1);  
19.         Console.WriteLine("The Original name of the Car is: " + car1.name);  
20.         Console.WriteLine("The Copy name of the Car is: " + car2.name);  
21.     }  
22. }  

**Output:**

The Original name of the Car is: TATA
The Copy name of the Car is: TATA

**Explanation:**

In this example, we demonstrate a copy constructor, which creates a new object (car2) by copying the values from an existing object (car1). After that, the Car class includes a parameterized constructor to initialize the object and a copy constructor that duplicates the name field.

## Static Constructor

In C#, a [static constructor](https://www.tpointtech.com/c-sharp-static-constructor) is mainly utilized to initialize static data members in a class. It is executed automatically only once, before any instance is created or static members are accessed, which ensures that the static fields are effectively initialized.

### Features of the Static Constructor:

Several features of the static constructor in C# are as follows:

- There are no acceptable parameters.
- It cannot be invoked explicitly.
- There are no access modifiers utilized.

### C# Static Constructor Example

Let us take an example to illustrate the static constructor in C#.

### Example

[](https://www.tpointtech.com/c-sharp-constructor#)[](https://www.tpointtech.com/c-sharp-constructor#)[](https://www.tpointtech.com/c-sharp-constructor#)

1. using System;  
2. class Database  
3. {  
4.     public static string connection;  
5.     // Static Constructor called.  
6.     static Database()  
7.     {  
8.         connection = "Connected to DB";  
9.         Console.WriteLine("Static constructor block executed");  
10.     }  
11.     static void Main()  
12.     {  
13.         Console.WriteLine(Database.connection);  
14.     }  
15. }  

**Output:**

Static constructor block executed
Connected to DB

**Explanation:**

In this example, the static constructor is called automatically before any objects are created or static fields are accessed. The static connection property is initialized here, and a message is printed when the class is initially loaded.

## Private Constructor

In the C# programming language, a [private constructor](https://www.tpointtech.com/private-constructor-in-c-sharp) stops other classes from making instances of that class. It is widely used in [Singleton Design Patterns](https://www.tpointtech.com/singleton-design-pattern-in-c-sharp) and utility classes.

### Features of Private Constructor:

Several features of the private constructor in C# are as follows:

- It is used to limit object creation from the outside.
- It is suitable for static-only classes or singletons.

### C# Private Constructor Example

Let us take an example to illustrate the private constructor in C#.

### Example

[](https://www.tpointtech.com/c-sharp-constructor#)[](https://www.tpointtech.com/c-sharp-constructor#)[](https://www.tpointtech.com/c-sharp-constructor#)

1. using System;  
2. class Logger  
3. {  
4.     private Logger() { }  
5.     public static void Log(string message)  
6.     {  
7.         Console.WriteLine("Log: " + message);  
8.     }  
9.     static void Main()  
10.     {  
11.         Logger.Log("App started");  
12.         Logger obj = new Logger();    //Compile-time error  
13.     }  
14. }  

**Output:**

Log: App started

**Explanation:**

In this example, we have taken the private constructor that prevents objects from being created outside the class, which is important in patterns such as Singleton. While the Logger.Log() method works, direct instantiation (new Logger()) results in a compile-time error.

## Constructor Overloading

In the C# programming language, the constructor overloading enables a class to have many constructors with varying parameter lists. It allows us to create objects in a variety of ways depending on the information available at the moment of instantiation.

### Features of Constructor Overloading:

Several features of constructor overloading in C# are as follows:

- Every constructor must have the same name as the class.
- Constructors differ in terms of the number and kind of parameters.
- The correct constructor is selected automatically based on the inputs supplied.

### Constructor Overloading Example in C#

Let us take an example to illustrate the constructor overloading in C#.

### Example

[](https://www.tpointtech.com/c-sharp-constructor#)[](https://www.tpointtech.com/c-sharp-constructor#)[](https://www.tpointtech.com/c-sharp-constructor#)

1. using System;  
2. namespace ConstructorOverloadExample  
3. {  
4.     class Book  
5.     {  
6.         // Constructor with no parameters.  
7.         public Book()  
8.         {  
9.             Console.WriteLine("The Default constructor is called");  
10.         }  
11.         // Constructor with one parameter.  
12.         public Book(string Book_Title)  
13.         {  
14.             Console.WriteLine("The title of the book is: " + Book_Title);  
15.         }  
16.         // Constructor with two parameters.  
17.         public Book(string Book_Title, string Author_Name)  
18.         {  
19.             Console.WriteLine("The title of the book is: " + Book_Title);  
20.             Console.WriteLine("The name of the Author is: " + Author_Name);  
21.         }  
22.         static void Main(string[] args)  
23.         {  
24.             // Calls default constructor  
25.             Book bk1 = new Book();  
26.             Console.WriteLine();  
27.             // Calls the constructor with one parameter  
28.             Book bk2 = new Book("Python");  
29.             Console.WriteLine();  
30.             // Calls the constructor with two parameters  
31.             Book bk3 = new Book("C# Programming", "Jamie Chan");  
32.             Console.ReadLine();  
33.         }  
34.     }  
35. }  

**Output:**

The Default constructor is called

The title of the book is: Python

The title of the book is: C# Programming
The name of the Author is: Jamie Chan

**Explanation:**

In this example, we have taken a Book class that exhibits several constructors with varying argument sets, which enables more versatile object construction. The matching constructor operates according to the inputs supplied, which demonstrates how overloading improves usability.

## Usage of Constructors in C#

There are several uses of the constructor in C#. Some of them are as follows:

- When an object is created, it is automatically initialized.
- It assigns class fields with default or custom values.
- It allows for constructor overloading for greater flexibility.
- Static constructors are mainly utilized to set up static members.
- Using private constructors, we can restrict object creation.
- Design patterns such as Singleton should be supported.
- Clean initialization helps to improve code readability and maintainability.

## Conclusion

In conclusion, constructors are special methods in C# that are utilized to initialize objects when a class instance is created. They provide versatility by allowing default initialization, supplying custom values, copying data, limiting object formation, and initializing static data. Constructor overloading improves object formation by allowing for numerous initialization pathways. Overall, constructors are essential for managing how objects are set up and behave from the moment they are created.