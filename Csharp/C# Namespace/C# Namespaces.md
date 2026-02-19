
In C#, namespaces are used to organize classes. It helps to control the scope of methods and classes in a large .NET project, which makes the code more manageable and structured. In a C# program, we use System.Console where the system is the namespace and the Console is the class. A class from a namespace is accessed using the format NamespaceName.ClassName.

In [C#](https://www.tpointtech.com/c-sharp-tutorial), a namespace is defined using the namespace keyword, followed by the namespace name and a pair of curly braces {} that contains its body.

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-namespaces#)[](https://www.tpointtech.com/c-sharp-namespaces#)[](https://www.tpointtech.com/c-sharp-namespaces#)

1. namespacename_of_namespace {  
2. // Namespace ( Nested Namespaces )  
3. // Classes  
4. // Interfaces  
5. // Structures  
6. // Delegates  
7. }  

Where,

- **Namespace name_of_namespace:** It declares the name of the namespace.
- **Nested Namespace:** It specifies the namespace inside another namespace.
- **Classes:** It represent the blueprint for creating objects.
- **Interface:** It defines a contract that contains a method signature without implementation.
- **Structure:** It specifies the light-weighted data type that holds the data.
- **Delegates:** It is a type that holds a reference to a method safely.

### C# Namespace Example

Let us take an example to illustrate the namespace in C#.

### Example

[](https://www.tpointtech.com/c-sharp-namespaces#)[](https://www.tpointtech.com/c-sharp-namespaces#)[](https://www.tpointtech.com/c-sharp-namespaces#)

1. using System;  
2. namespace Name1  // define a namespace  
3. {  
4. class C1  
5.     {  
6. public void Show() =>Console.WriteLine("Hello from Name1");  
7.     }  
8. }  
9. namespace Name2  // define a namespace   
10. {  
11. class C2  
12.     {  
13. public void Show() =>Console.WriteLine("Hello from Name2");  
14.     }  
15. }  
16. class Tpoint  
17. {  
18. static void Main()  
19.     {  
20.         Name1.C1 obj1 = new Name1.C1();  
21.         Name2.C2 obj2 = new Name2.C2();  
22. obj1.Show();  
23. obj2.Show();  
24.     }  
25. }  

**Output:**

Hello from Name1
Hello from Name2

**Explanation:**

In this example, we have taken two namespaces named Name1 and Name2, and each containing a class C1 and C2. In the main method, we create instances (obj1, obj2) of the classes (Name1, Name2) and call the Show() method to print the output.

### Accessing the Members of a Namespace

In C# programming, the members of a namespace are accessed by using the dot (.) operator. It allows access to members defined within that namespace, such as classes or methods.

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-namespaces#)[](https://www.tpointtech.com/c-sharp-namespaces#)[](https://www.tpointtech.com/c-sharp-namespaces#)

1. [Namespace_name].[member_name]  

Here,

- **Namespace_name:** It specifies the name of the namespace.
- **Member_name:** It represents the element inside the namespaces, such as class, method, interface, structure, or delegate.

**C# namespace Example:**

Let us take an illustrative example to demonstrate the namespace in C#.

### Example

[](https://www.tpointtech.com/c-sharp-namespaces#)[](https://www.tpointtech.com/c-sharp-namespaces#)[](https://www.tpointtech.com/c-sharp-namespaces#)

1. using System;  
2. namespace TPointtech  
3. {  
4.     class Message  
5.     {  
6.         public void Show()  
7.         {  
8.             Console.WriteLine("Hello from TPointtech");  
9.         }  
10.     }  
11. }  
12. class Program  
13. {  
14.     static void Main()  
15.     {  
16.         // Creating object using fully qualified namespace  
17.         TPointtech.Message obj = new TPointtech.Message();  
18.         obj.Show();  
19.     }  
20. }  

**Output:**

Hello from TPointtech

**Explanation:**

In this example, we have taken a namespace named TPointtech that contains a class called Message. It defines a Show() method that prints a message using Console.WriteLine() function. In the main function, we create an instance of the class (Message) and call the Show() method to print the outputs.

## Namespace with using keyword

In C#, the using keyword is used to include the namespaces in the program. It allows us to access the classes, methods, and variables from that namespace without writing the full namespace each time.

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-namespaces#)[](https://www.tpointtech.com/c-sharp-namespaces#)[](https://www.tpointtech.com/c-sharp-namespaces#)

1. using namespace_name;  

Here, the using keyword is used to include the namespaces in a program, and the namespace_name represents the collection of classes, interfaces, and methods.

### C# Namespace Example by 'using' keyword

Let's take an example to illustrate the namespace by using the keyword in C#.

### Example

[](https://www.tpointtech.com/c-sharp-namespaces#)[](https://www.tpointtech.com/c-sharp-namespaces#)[](https://www.tpointtech.com/c-sharp-namespaces#)

1. using System;  
2. using Library;  
3. using Student;  
4. namespace Library  
5. {  
6. public class Book  
7.     {  
8. public void ShowBook()  
9.         {  
10. Console.WriteLine("This is the Library Namespace - Book Class");  
11.         }  
12.     }  
13. }  
14. namespace Student  
15. {  
16. public class Info  
17.     {  
18. public void ShowStudent()  
19.         {  
20. Console.WriteLine("This is the Student Namespace - Info Class");  
21.         }  
22.     }  
23. }  

24. public class TestNamespace  
25. {  
26. public static void Main()  
27.     {  
28.         Book b1 = new Book();  
29.         Info s1 = new Info();  

30. b1.ShowBook();  
31. s1.ShowStudent();  
32.     }  
33. }  

**Output:**

This is the Library Namespace - Book Class
This is the Student Namespace - Info Class

**Explanation:**

In this example, we have taken two namespaces, Library and Student. After that, the Library namespace contains a Bool class with the method ShowBook(), and the Student namespace contains an Info class with the method ShowStudent(). We use the "Using" keyword at the top of the program. So, the classes can be accessed directly. In the main method, we are creating an instance and calling its method (ShowBook, ShowStudent) to print the output.

## Nested Namespace

In the C# programming language, nested namespaces allow us to define a namespace inside another namespace. It is useful for organizing code into a hierarchical structure. It avoids the duplicate namespace and enhances the clarity of the code.

### C# Nested Namespace Example

Let us take an example to illustrate the nested namespace in C#.

### Example

[](https://www.tpointtech.com/c-sharp-namespaces#)[](https://www.tpointtech.com/c-sharp-namespaces#)[](https://www.tpointtech.com/c-sharp-namespaces#)

1. using System;  
2. namespace Company  
3. {  
4. namespace HR  
5.     {  
6. class Employee  
7.         {  
8. public void ShowEmployee()  
9.             {  
10. Console.WriteLine("This is the HR namespace - Employee class");  
11.             }  
12.         }  
13.     }  
14. namespace Finance  
15.     {  
16. class Account  
17.         {  
18. public void ShowAccount()  
19.             {  
20. Console.WriteLine("This is the Finance namespace - Account class");  
21.             }  
22.         }  
23.     }  
24. }  
25. class Program  
26. {  
27. static void Main()  
28.     {  
29.         // Access nested namespaces  
30. Company.HR.Employee emp = new Company.HR.Employee();  
31. emp.ShowEmployee();  
32. Company.Finance.Account acc = new Company.Finance.Account();  
33. acc.ShowAccount();  
34.     }  
35. }  

**Output:**

This is the HR namespace - Employee class
This is the Finance namespace - Account class

**Explanation:**

In this program, we have taken the company namespace that contains two sub-namespaces: HR and Finance. Inside the HR namespace, it has an Employee class, and inside Finance, it has an Account class. Each class has the same method names ShowEmployee() and ShowAccount(). In the main method, we are creating the object of both classes and calling their method to print the output.

## C# Built-in Namespace

In the C# programming language, a namespace is a container that holds methods, classes, and interfaces. It provides many built-in namespaces that contain the pre-defined classes and methods, which we can directly use in our program.

### C# Example Built-in Namespace

Let us take a simple example of a built-in namespace in C#.

### Example

[](https://www.tpointtech.com/c-sharp-namespaces#)[](https://www.tpointtech.com/c-sharp-namespaces#)[](https://www.tpointtech.com/c-sharp-namespaces#)

1. using System;   // Built-in namespace  
2. class Program  
3. {  
4. static void Main()  
5.     {  
6.         // Console class   
7. Console.WriteLine("Hello from System Namespace");  

8.         // Apply Math class   
9. int number = 16;  
10. double res = Math.Sqrt(number);   // calculate Square root of number  

11. Console.WriteLine("The square root of " + number + " = " + res);  
12.     }  
13. }  

**Output:**

Hello from System Namespace
The square root of 16 = 4

**Explanation:**

In this example, we have taken the built-in System namespace. The console class is used to print the message, while the math class is used to provide the mathematical operations. We are using the Math.Sqrt() method to calculate its square root. Finally, we are using the Console.WriteLine() function to print the Output.

## # Global Namespace

In the C# programming language, the global namespace is the root namespace that contains all the other namespaces, such as System, MyApp, Library, etc. If you want to point directly to the root namespace, use global(**::).**

### C# Global Namespace Example

Let us take an example to illustrate the global namespace in C#.

### Example

[](https://www.tpointtech.com/c-sharp-namespaces#)[](https://www.tpointtech.com/c-sharp-namespaces#)[](https://www.tpointtech.com/c-sharp-namespaces#)

1. using System;  
2. namespace MyApp  
3. {  
4.     // Custom namespace  
5.     namespace System  
6.     {  
7.         class Console  
8.         {  
9.             public static void WriteLine(string msg)  
10.             {  
11.                 // Use the global System.Console to avoid recursion  
12.                 global::System.Console.WriteLine("Custom message " + msg);  
13.             }  
14.         }  
15.     }  

16.     class Program  
17.     {  
18.         static void Main()  
19.         {  
20.             // Calls our custom Console  
21.             System.Console.WriteLine("Hello");  

22.             // Calls the real System.Console from global namespace  
23.             global::System.Console.WriteLine("Hello TPointtech");  
24.         }  
25.     }  
26. }  

**Output:**

Custom message Hello
Hello TPointtech

**Explanation:**

In this example, we define the custom System.Console class inside the MyApp namespace, when we call System.Console.WriteLine("Hello"), it uses the custom class, which prints using the real console by global::System.Console. The global(::) keyword is used to reach the original .NET Console.

### C# Example to Access Classes using a fully qualified namespace name

Let's take an example of a namespace in C# where one namespace program accesses another namespace program.

### Example

[](https://www.tpointtech.com/c-sharp-namespaces#)[](https://www.tpointtech.com/c-sharp-namespaces#)[](https://www.tpointtech.com/c-sharp-namespaces#)

1. using System;  
2. namespace School  
3. {  
4. public class Student  
5.     {  
6. public void Show()  
7.         {  
8. Console.WriteLine("This is a Student from School Namespace");  
9.         }  
10.     }  
11. }  
12. namespace College  
13. {  
14. public class Student  
15.     {  
16. public void Show()  
17.         {  
18. Console.WriteLine("This is a Student from College Namespace");  
19.         }  
20.     }  
21. }  
22. public class TestNamespace  
23. {  
24. public static void Main()  
25.     {  
26. School.Student s1 = new School.Student();  
27. College.Student s2 = new College.Student();  
28. s1.Show();  
29. s2.Show();  
30.     }  
31. }  

**Output:**

This is a Student from School Namespace
This is a Student from College Namespace

**Explanation:**

In this example, we create two namespaces named School and College, both of which contain the class named Student. In the main method, we create an instance of the class (Student) and call the Show () method to print the output.

## Conclusion

In conclusion, a C# namespace is an important factor in organizing code. It helps to control the scope of methods and classes in a large .NET project, making the code more manageable and structured. It also prevents naming conflicts and improves the clarity of code.