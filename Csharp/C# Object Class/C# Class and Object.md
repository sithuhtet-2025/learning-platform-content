
In the C# programming language, the class and object are the fundamental components of OOP (Object Oriented Programming). They provide the code in a more organized, reusable, and maintainable way. In C#, classes act like a blueprint that defines how objects are structured and behave in the program. On the other hand, objects are instances of classes that are used to hold data and methods to create and manipulate several entities.

![C# Class and Object](https://images.tpointtech.com/csharp/images/c-sharp-object-and-class.png)

## C# Classes

In OOP, a class is a fundamental building block that collects the data members and data methods into a single unit. It is a user-defined reference type that acts as a blueprint to create objects. A class keyword is used to create a class in C#.

A class helps in code reusability and portability, which means the same class can be used across different programs without rewriting the code. It also supports encapsulation, which means it hides the internal implementation details of a class and shows only the necessary features to the outside world. It can also contain fields, properties, methods, [constructors](https://www.tpointtech.com/c-sharp-constructor), and [events](https://www.tpointtech.com/events-in-c-sharp).

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-object-and-class#)[](https://www.tpointtech.com/c-sharp-object-and-class#)[](https://www.tpointtech.com/c-sharp-object-and-class#)

1. class Class_Name  
2. {  
3.     public int data; // Data member  

4.     public void Display()  
5.     {  
6.         // code to be executed  
7.     }  
8. }  

In this syntax,

- **Data Members:** The data members are the variables that are defined inside the class of the program.
- **Data Method:** The data method is the functions that are also defined in the class of the program that operate on the data members.
- **Access Specifiers:** These are utilized to define the visibility and access of a class and its members. These specifiers access the class, field, property, and method.

### C# Class Example

Let us take an example to define a class in C#.

### Example

[](https://www.tpointtech.com/c-sharp-object-and-class#)[](https://www.tpointtech.com/c-sharp-object-and-class#)[](https://www.tpointtech.com/c-sharp-object-and-class#)

1. using System;  
2. namespace Example  
3. {  
4.     class Student  
5.     {  
6.         public string name;  
7.         public int age;  
8.         public void DisplayInfo()  
9.         {  
10.             Console.WriteLine("The student's name is " + name);  
11.             Console.WriteLine("The student's age is " + age);  
12.         }  
13.     }  
14.     class Program  
15.     {  
16.         static void Main(string[] args)  
17.         {  
18.             Student s1 = new Student();  
19.             s1.name = "John";  
20.             s1.age = 20;  
21.             s1.DisplayInfo();  
22.         }  
23.     }  
24. }  

**Output:**

The student's name is John
The student's age is 20

**Explanation:**

In this example, we define the class named Student. Inside this class, we create the methods named DisplayInfo and a member named "name" and "age" that display the details of the student.

After that, we create an object of the class Student and assign the values "John" and 20 to the object's name and age. Finally, we use the Console.WriteLine() function to print the output.

### C# Class Access Specifiers

In the [C# programming language](https://www.tpointtech.com/c-sharp-tutorial), the access specifiers are used to control access to class members. The access specifier is also known as an access modifier in C#.  These are the keywords that are used to limit the accessibility of data members and methods, including protected, private, public, and internal.

There are mainly four types of access specifiers in C#.

- **Public Specifier:** In C#, the public is a more flexible specifier. The public members of a class will be accessible from anywhere in the program.
- **Private Specifier:** The private members are the more restrictive specifiers in C#. The data members of a class will be accessible inside the code block where they were declared.
- **Protected Specifier:** The protected members of the class will be accessible within the same class and also inside its derived classes.
- **Internal Specifier:** The internal specifiers are of assembly-level specifiers. The internal member of the class that can be accessed within the same assembly.

**To Read More:** [Access Modifiers in C#](https://www.tpointtech.com/c-sharp-access-modifiers)

## C# Object

An object is a run-time entity (such as a chair, a car, a pen, etc.) that is used to represent the features of a class. It is also known as an instance of a class, which defines its structure, behaviour, and identity. It is created in the memory when the program is executed. Objects are used to hold data in fields and can access methods and the properties of the class.

![C# Class and Object](https://images.tpointtech.com/csharp/images/c-sharp-object-and-class2.png)

### Creating Objects in C#

In C#, once the class is defined in the program, we can easily create its object in the same manner that we define the [variable](https://www.tpointtech.com/csharp-variables) of any other built-in [data type](https://www.tpointtech.com/csharp-data-types). The object is created using the new keyword, which gives memory to the class and returns a reference to it.

**Syntax:**

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-object-and-class#)[](https://www.tpointtech.com/c-sharp-object-and-class#)[](https://www.tpointtech.com/c-sharp-object-and-class#)

1. ClassName objectName = new ClassName();  

In this syntax,

- **ClassName:** It defines the name of the class.
- **ObjectName:** It refers to the name of the object of a class that can be created.
- **new:** The new keyword is used to make a new object in memory.

### C# Object Example

Let us take an example to define the object in C#.

### Example

[](https://www.tpointtech.com/c-sharp-object-and-class#)[](https://www.tpointtech.com/c-sharp-object-and-class#)[](https://www.tpointtech.com/c-sharp-object-and-class#)

1. using System;  
2. namespace Example  
3. {  
4.     // create a class  
5.     class Car  
6.     {  
7.         // Data members  
8.         public string Brand;  
9.         public int Year;  
10.         // Method  
11.         public void ShowDetails()  
12.         {  
13.             Console.WriteLine("Car Brand: " + Brand);  
14.             Console.WriteLine("Manufacturing Year: " + Year);  
15.         }  
16.     }  
17.     class Program  
18.     {  
19.         static void Main(string[] args)  
20.         {  
21.             // object  
22.             Car myCar = new Car();  
23.             // Assigning values  
24.             myCar.Brand = "Toyota";  
25.             myCar.Year = 2022;  
26.             // Accessing method using object  
27.             myCar.ShowDetails();  
28.         }  
29.     }  
30. }  

**Output:**

Car Brand: Toyota
Manufacturing Year: 2022

**Explanation:**

In this example, we demonstrate how to use the object in C#. First, we create a class named Car. Inside the class, we create the method named ShowDetails().

In the main method, we create an object of the class Car. The brand and year of the item are given the values "Toyota" and 2022. Finally, we use the Console.WriteLine() function to print the output.

### Characteristics of an Object:

The several characteristics of an object are as follows:

- **Identity:** Every object has a unique identity, even if multiple objects have the same values for their properties.
- **State:** Data members of the class can represent the state of the object. It refers to the properties or data stored within the object.
- **Behaviour:** The behaviour of an object is represented as a data method of the class. It defines what operations the object can perform.

### C# Classes and Objects Example

Let us take an instance of the class that contains two fields: id and name. We create an instance of the class and initialize the object, and then print the value.

### Example

[](https://www.tpointtech.com/c-sharp-object-and-class#)[](https://www.tpointtech.com/c-sharp-object-and-class#)[](https://www.tpointtech.com/c-sharp-object-and-class#)

1. using System;  
2. class Worker  // define the class   
3. {  
4.     public int WorkerId;       // variable name  
5.     public string WorkerName;    
6. }  
7. class Program  
8. {  
9.     static void Main(string[] args)  
10.     {  
11.         Worker w1 = new Worker();  // Object   
12.         w1.WorkerId = 501;         // Assigning values  
13.         w1.WorkerName = "Alex Parker";   
14.         Console.WriteLine(w1.WorkerId);      // Display Worker ID  
15.         Console.WriteLine(w1.WorkerName);    // Display Worker Name  
16.     }  
17. }  

**Output:**

501
Alex Parker

**Explanation:**

In this example, we demonstrate how to use the class and object in C#. First, we create a class named Worker that has two variables, WorkerId and WorkerName. After that, we create the object (w1) of the class (Worker) and assign the value 501 and Alex Parker. Finally, we use the Console.WriteLine() function to print the output.

## Pass an Object as an Argument into a Method in C#

In the C# programming language, we can pass an object to a method. The method is a code block that only runs when it is called and carries out a specific task. We can pass the data as arguments, and also pass an object as an argument that is an instance of a class.

When we pass an object to a method, the reference to the object is transmitted, and it doesn't create a copy of the object itself. Therefore, any changes made to the object inside the method will also affect the original object outside the method.

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-object-and-class#)[](https://www.tpointtech.com/c-sharp-object-and-class#)[](https://www.tpointtech.com/c-sharp-object-and-class#)

1. // Creating the testing object  
2. Test t1 = new test(6);  
3. // passing an object as an argument  
4. t1.PassObj(t1);  

### C# pass an object as an argument in a method Example

Let's take another example of a C# program where we store and retrieve employee information.

### Example

[](https://www.tpointtech.com/c-sharp-object-and-class#)[](https://www.tpointtech.com/c-sharp-object-and-class#)[](https://www.tpointtech.com/c-sharp-object-and-class#)

1. using System;  
2. class Staff  
3. {  
4.     public int staff_Id;          // variable name  
5.     public string staff_name;       
6.     public float staff_salary;  
7.     // function name and parameters  
8.     public void SetDetails(int id, string name, float salary)  
9.     {  
10.         staff_Id = id;  
11.         staff_name = name;  
12.         staff_salary = salary;  
13.     }  
14.     // function name  
15.     public void ShowDetails()  
16.     {  
17.         Console.WriteLine(staff_Id + "  " + staff_name + "  " + staff_salary);  
18.     }  
19. }  

20. class Program  
21. {  
22.     static void Main(string[] args)  
23.     {  
24.         Staff staff1 = new Staff();  // object name and class  
25.         Staff staff2 = new Staff();  

26.         staff1.SetDetails(101, "John", 995000);  
27.         staff2.SetDetails(102, "Michael", 29700);  

28.         staff1.ShowDetails();  
29.         staff2.ShowDetails();  
30.     }  
31. }  

**Output:**

101 John 995000
102 Michael 29700

**Explanation:**

In this example, we define the class named Staff that contains the variables name, staff_id, staff_name, staff_salary, along with the method name ShowDetails(). After that, we create the objects (staff1, staff2) of the class (Staff) and assign the value. Finally, we are using the Console.WriteLine() function to print the output.

## Differentiate between the Classes and Objects in C#

Several differences between the classes and objects in C# are as follows.

|Features|Classes|Objects|
|---|---|---|
|**Definition**|Class is a collection of data members and data methods in a single unit.|Objects are instances of the class.|
|**Syntax**|class Class_Name|Class_Name c1 = new Class_Name|
|**Uses**|It is mainly used for concepts and models.|It is mainly used for real-world entities, such as data and functionality.|
|**Representation**|It represents a general concept or type.|It represents a specific instance of the class.|
|**Memory Allocation**|In C# classes, no memory is allocated until an object is created.|Memory for a class is allocated only when an object is created.|

## Important Points about Classes and Objects

Several important points about classes and objects in C# are as follows:

- Classes and Objects are the fundamental concepts of OOP in C#. We can get the different aspects like [inheritance](https://www.tpointtech.com/c-sharp-inheritance), [encapsulation](https://www.tpointtech.com/c-sharp-encapsulation), and abstraction using these classes and objects.
- When we create an object, each object has a different identity that sets it apart from other things.
- We can use the destructor to end the instance in order to reduce the memory usage.
- Classes and Objects are used to implement portability in our program, which means we can use a class easily from one program to another program.

## Conclusion

In C#, classes and objects are the foundation of the object-oriented programming language. These are the fundamental building blocks that are used to create software applications. A class is a user-defined reference type that works as a blueprint to create an object. In contrast, an object is an instance of a class that contains actual values. They enable us to write code in a more organized, reusable, and maintainable way.