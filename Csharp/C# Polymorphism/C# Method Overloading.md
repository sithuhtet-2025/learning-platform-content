In the C# programming language, method overloading is an object-oriented programming concept that allows us to define several methods with the same name in a class with different parameters. It allows us to execute the same operation in multiple ways, depending on the type or amount of inputs given. The compiler chooses the appropriate method to execute based on the arguments provided in the call, which makes the code adaptable to different input scenarios without the need for separate method names.

### Syntax:

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-member-overloading#)[](https://www.tpointtech.com/c-sharp-member-overloading#)[](https://www.tpointtech.com/c-sharp-member-overloading#)

1. class Class_Name  
2. {  
3.     // Method 1  
4.     return_Type MethodName(parameter_list1) {  
5.         // method body  
6.     }  
7.     //method 2  
8.     return_Type MethodName(parameter_list2) {  
9.         // method body  
10.     }  
11. }  

In this syntax, we have taken two function declarations that have the same name but different parameters.

**For Example:**

[](https://www.tpointtech.com/c-sharp-member-overloading#)[](https://www.tpointtech.com/c-sharp-member-overloading#)[](https://www.tpointtech.com/c-sharp-member-overloading#)

1. int method(int a)  
2. float method (float a)  
3. double method (double a, double b)  

### Method Overloading Example in C#

Let us take an example to illustrate method overloading in C#.

### Example

[](https://www.tpointtech.com/c-sharp-member-overloading#)[](https://www.tpointtech.com/c-sharp-member-overloading#)[](https://www.tpointtech.com/c-sharp-member-overloading#)

1. using System;  

2. class Calculator  
3. {  
4.     // Method 1 - multiply two integers  
5.     public int Mul(int x, int y)  
6.     {  
7.         return x * y;  
8.     }  

9.     // Method 2 - multiply three integers  
10.     public int Mul(int x, int y, int z)  
11.     {  
12.         return x * y * z;  
13.     }  

14.     // Method 3 - multiply two double numbers  
15.     public double Mul(double x, double y)  
16.     {  
17.         return x * y;  
18.     }  
19. }  

20. class TpointTech  
21. {  
22.     static void Main()  
23.     {  
24.         Calculator calc = new Calculator();  

25.         Console.WriteLine("Multiplications of 2 ints: " + calc.Mul(15, 10));  
26.         Console.WriteLine("Multiplications of 3 ints: " + calc.Mul(4, 6, 5));  
27.         Console.WriteLine("Multiplications of 2 doubles: " + calc.Mul(6.5, 4.8));  
28.     }  
29. }  

**Output:**

Multiplications of 2 ints: 150
Multiplications of 3 ints: 120
Multiplications of 2 doubles: 31.2

**Explanation:**

In this example, we have taken a Mul() method that is defined with the name but different parameter lists to handle two integers, three integers, and two doubles. At compilation time, it selects the appropriate method that is based on the arguments passed.

## Important points for Method Overloading

There are several important points for method overloading in C#. Some of them are as follows:

- Overloaded methods are distinguished based on the number and parameter types that are passed as arguments to the methods.
- If we have taken multiple methods with the same parameter but different return types, it will throw a compile-time error.
- We cannot define multiple methods with the same name, and the type of the arguments, it will throw a compile-time error.
- It can have different [access modifiers](https://www.tpointtech.com/c-sharp-access-modifiers), such as public and private.
- All overloaded methods should have the same name within the same class.

## Different ways to perform Method Overloading in C#

In the [C# programming language](https://www.tpointtech.com/c-sharp-tutorial), method overloading improves code readability by combining related operations into a single and descriptive label. It encourages reusability by reducing duplication and avoiding several names for similar functionality. It enables flexibility by allowing the same method name to handle a variety of input types or numbers.

We can perform method overloading in C# in three ways:

- By changing the number of parameters
- By changing the data type of the arguments
- Using different data types for parameters

Here, we will discuss these different ways that can help to perform method overloading in C#.

### 1. By changing the number of Parameters

In the C# programming language, method overloading can be achieved by defining multiple methods with the same name but different numbers of parameters. The compiler selects the appropriate method to call based on the number of arguments provided during the method call.

**Syntax:**

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-member-overloading#)[](https://www.tpointtech.com/c-sharp-member-overloading#)[](https://www.tpointtech.com/c-sharp-member-overloading#)

1. returnType MethodName(type1 param1, type2 param2)  // Overloaded Method with 2 parameters  
2. returnType MethodName(type1 param1, type2 param2, type3 param3)  // Overloaded method with 3 parameters  

**C# Method Overloading Example by Changing the Number of Parameters**

Let us take an example to illustrate method overloading by changing the number of parameters in C#.

### Example

[](https://www.tpointtech.com/c-sharp-member-overloading#)[](https://www.tpointtech.com/c-sharp-member-overloading#)[](https://www.tpointtech.com/c-sharp-member-overloading#)

1. using System;    
2.     public class Cal  
3.      {      
4.         public static int add(int x, int y)  
5.      {    
6.             return x + y;    
7.         }    
8.         public static int add(int x, int y, int z)    
9.         {    
10.             return x + y + z;    
11.         }    
12.     }    
13.     public class TestMemberOverloading    
14.     {    
15.         public static void Main()    
16.         {    
17.             Console.WriteLine(Cal.add(12, 23));    
18.             Console.WriteLine(Cal.add(12, 23, 25));    
19.         }    
20.     }    

**Output:**

35
60

**Explanation:**

In this example, we have taken the Cal class that defines two add() methods: one with two integer parameters and one with three integer parameters. After that, the compiler uses the number of arguments passed to determine which method to call.

### 2) By Changing the Data Type of the Arguments

In C#, method overloading can happen by defining multiple methods with the same name but contain different parameter data types. This distinction might be made in terms of the number of parameters or the [data types](https://www.tpointtech.com/csharp-data-types) of those parameters.

**Syntax:**

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-member-overloading#)[](https://www.tpointtech.com/c-sharp-member-overloading#)[](https://www.tpointtech.com/c-sharp-member-overloading#)

1. returnType MethodName(int param1, int param2)    // Method with int parameters  
2. returnType MethodName(double param1, double param2) // Overloaded method with double parameters  

**C# Method Overloading Example by Changing the Data Type of the Arguments**

Let us take an example to illustrate method overloading by changing the data type of the arguments in C#.

### Example

[](https://www.tpointtech.com/c-sharp-member-overloading#)[](https://www.tpointtech.com/c-sharp-member-overloading#)[](https://www.tpointtech.com/c-sharp-member-overloading#)

1. using System;    
2.     public class Cal  
3. {    
4.         public static int add(int a, int b)  
5. {    
6.             return a + b;    
7.         }    
8.         public static float add(float a, float b)    
9.         {    
10.             return a + b;    
11.         }    
12.     }    
13.     public class TestMemberOverloading    
14.     {    
15.         public static void Main()    
16.         {    
17.             Console.WriteLine(Cal.add(12, 23));    
18.             Console.WriteLine(Cal.add(12.4f,21.3f));    
19.         }    
20.     }   

**Output:**

35
33.7

**Explanation:**

In this example, we have taken a Cal class that contains two add() methods, one for integers and another for floating-point numbers. After that, the data types of the parameters provided are used to select the method.

### 3) Using Different Data Types for Parameters

Method overloading can be achieved by defining multiple methods with the same name but with parameters in a different order.

**Syntax:**

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-member-overloading#)[](https://www.tpointtech.com/c-sharp-member-overloading#)[](https://www.tpointtech.com/c-sharp-member-overloading#)

1. // Method with int and double parameters  
2.     returnType MethodName(int parameter1, double parameter2)  
3.     // Overloaded method with double and string parameters  
4.     returnType MethodName(double parameter1, string parameter2)  
5.     // Overloaded method with string and int parameters  
6.     returnType MethodName(string parameter1, int parameter2)  

**C# Method Overloading Example by using different data types for parameters**

Let us take an example to illustrate the method overloading by using different data types for parameters in C#.

### Example

[](https://www.tpointtech.com/c-sharp-member-overloading#)[](https://www.tpointtech.com/c-sharp-member-overloading#)[](https://www.tpointtech.com/c-sharp-member-overloading#)

1. using System;  
2. class ProductDetails   
3. {  
4.     public void Print(string productName, double price)  
5.     {  
6.         Console.WriteLine("The Product Name is: " + productName + "\nThe Price is: " + price);  
7.     }  
8.     public void Print(double price, string productName)  
9.     {  
10.         Console.WriteLine("The Product Name is: " + productName + "\nThe Price is: " + price);  
11.     }  
12.     public static void Main(string[] args)  
13.     {  
14.         ProductDetails p = new ProductDetails();  
15.         p.Print("Laptop", 58000.75);  
16.         p.Print(1500.50, "Headphones");  
17.     }  
18. }  

**Output:**

The Product Name is: Laptop
The Price is: 58000.75
The Product Name is: Headphones
The Price is: 1500.5

**Explanation:**

In this example, we have taken the ProductDetails() class that contains two Print() methods: one accepts a string followed by a double, and another accepts a double followed by a string. The method chosen is determined by the order and type of inputs provided.

## Constructor Method Overloading

In C#, constructor overloading allows us to define multiple constructors in the same class with the same name, but with different parameters. It allows us to initialize the class objects in a different method, which is based on the provided arguments.

**Syntax:**

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-member-overloading#)[](https://www.tpointtech.com/c-sharp-member-overloading#)[](https://www.tpointtech.com/c-sharp-member-overloading#)

1. class ClassName  
2. {  
3.     // Default constructor (no parameters)  
4.     public ClassName()  
5.     {  
6.         // body of the code  
7.     }  

8.     // Parameterized constructor (with parameters  
9.     public ClassName(type1 par1, type2 par2)  
10.     {  
11.         // body of the code  
12.     }  
13. }  

### Constructor Method Overloading Example in C#

Let us take an example to illustrate the constructor overloading in C#.

### Example

[](https://www.tpointtech.com/c-sharp-member-overloading#)[](https://www.tpointtech.com/c-sharp-member-overloading#)[](https://www.tpointtech.com/c-sharp-member-overloading#)

1. using System;  

2. class Employee  
3. {  
4.     private int empId;  
5.     private string name;  
6.     private string depart;  

7.     // Constructor 1 - Default  
8.     public Employee()  
9.     {  
10.         empId = 0;  
11.         name = "None";  
12.         depart = "General";  
13.     }  

14.     // Constructor 2 - Initialize with ID and Name  
15.     public Employee(int id, string empName)  
16.     {  
17.         empId = id;  
18.         name = empName;  
19.         depart = "General";  
20.     }  

21.     // Constructor 3 - Initialize with ID, Name, and Department  
22.     public Employee(int id, string empName, string dept)  
23.     {  
24.         empId = id;  
25.         name = empName;  
26.         depart = dept;  
27.     }  

28.     public void Show()  
29.     {  
30.         Console.WriteLine($"Employee ID: {empId}, Employee Name: {name}, Employee Department: {depart}");  
31.     }  
32. }  

33. class consOverloading  
34. {  
35.     static void Main()  
36.     {  
37.         // Using different constructors  
38.         Employee emp1 = new Employee();  // default constructor  
39.         Employee emp2 = new Employee(101, "Michael");  // constructor with 2 params  
40.         Employee emp3 = new Employee(102, "Johnson", "HR");  // constructor with 3 params  

41.         emp1.Show();  
42.         emp2.Show();  
43.         emp3.Show();  
44.     }  
45. }  

**Output:**

Employee ID: 0, Employee Name: None, Employee Department: General
Employee ID: 101, Employee Name: Michael, Employee Department: General
Employee ID: 102, Employee Name: Johnson, Employee Department: HR

**Explanation:**

In this example, we have taken an Employee class that contains 3 parameters, such as a default constructor, a second parameter that initializes the empid and employee name, and a third parameter that initializes all the fields. After that, the suitable constructor is called to create the employee objects that are depend on the passed arguments.

## Conclusion

In conclusion, C# method overloading enables multiple methods with the same name with different parameter lists. It is a type of compile-time polymorphism that enhances code readability, reusability, and flexibility. If we use method overloading, we may handle similar operations with a single method name, which makes the code cleaner and easier to maintain.
