# 

C# variables are the containers that are used to store data during the program execution. It represents memory location and is used to reserve the memory space so that we can store data during the run-time of the program on that reserved space. We can also change the values of a variable during the run-time of the program.

**Syntax:**

It has the following syntax:

[](https://www.tpointtech.com/csharp-variables#)[](https://www.tpointtech.com/csharp-variables#)[](https://www.tpointtech.com/csharp-variables#)

1. type variableName = value;  

Where,

- **type:** It represents the data type, such as int, float, and char.
- **VariableName:** It defines the variable name.
- **Value:** It represents the value of the variable.

## Simple Example of C# Variables:

Let us take a simple example to illustrate the variables in C#.

### Example

[](https://www.tpointtech.com/csharp-variables#)[](https://www.tpointtech.com/csharp-variables#)[](https://www.tpointtech.com/csharp-variables#)

1. using System;  
2. public class Variables_Declaration  
3. {  
4. public static void Main(string[] args)  
5. {  
6. int num = 5; // Integer value  
7. string name = "John"; //string value  
8. Console.WriteLine("The number is " +num);  
9. Console.WriteLine("Name is " +name);  
10. }  
11. }   

**Output:**

The number is 5
Name is John

**Explanation:**

In this example, we have taken two variables are declared num as an integer with the value 5, and name as a string with the value "John". After that, the program prints both values using the Console.WriteLine() method.

Now, we will discuss how to create a variable, initialize a variable, access a variable, and update a variable one by one.

### 1) Creating a Variable

In [C#](https://www.tpointtech.com/c-sharp-tutorial), when we create or declare a variable, we need to specify the [data type](https://www.tpointtech.com/csharp-data-types) and assign it a value.

**Syntax**

It has the following syntax:

[](https://www.tpointtech.com/csharp-variables#)[](https://www.tpointtech.com/csharp-variables#)[](https://www.tpointtech.com/csharp-variables#)

1. type VariableName;  

Where,

- **type:** It identifies the type of data that a variable can store.
- **VariableName:** It identifies the name that is assigned to the variable.

**Example:**

[](https://www.tpointtech.com/csharp-variables#)[](https://www.tpointtech.com/csharp-variables#)[](https://www.tpointtech.com/csharp-variables#)

1. int sum;  

In this example, we use the int data type to store the integer number.

### 2) Variable Initialization

In C#, the term initialization means to assign some value to the variable. It is the main objective of the variable. It is performed using an assignment operator(=). Let us see the initialization of a variable in the following syntax:

[](https://www.tpointtech.com/csharp-variables#)[](https://www.tpointtech.com/csharp-variables#)[](https://www.tpointtech.com/csharp-variables#)

1. type variable_name;  
2. variable_name = value;  

**Example:**

[](https://www.tpointtech.com/csharp-variables#)[](https://www.tpointtech.com/csharp-variables#)[](https://www.tpointtech.com/csharp-variables#)

1. int num;  // declaring variable num  
2. num=20;  // Initializing num with value 20  

In this example, we use the integer data type and assign the 20 values.

### 3) Variable Accessing

In C#, variable accessing means retrieving or modifying the value that is stored in a variable. For example, a container where we can store multiple things and retrieve them when needed.

**C# Variable Accessing Example**

Let us take an example to illustrate how to access a variable in C#.

### Example

[](https://www.tpointtech.com/csharp-variables#)[](https://www.tpointtech.com/csharp-variables#)[](https://www.tpointtech.com/csharp-variables#)

1. using System;  
2. public class AccessingValues  
3. {  
4.     public static void Main(string[] args)  
5.     {  
6.         int roll_no = 10;    
7.         string name = "John";  
8.         float total_marks = 123f;  
9.         Console.WriteLine("Roll Number is \n" + roll_no + "\nName is \n" + name + "\nTotal Marks are:\n" + total_marks);  
10.     }  
11. }  

**Output:**

Roll Number is
10
Name is
John
Total Marks are
123

**Explanation:**

In this example, we have taken three variables (roll_no, name, and total_marks) that are declared and initialized with student details. After that, the Console.WriteLine() method is utilized to print each value with descriptive text on a new line.

### 4) Updating a Variable:

Let us take an example to illustrate how to update the variable in C#.

### Example

[](https://www.tpointtech.com/csharp-variables#)[](https://www.tpointtech.com/csharp-variables#)[](https://www.tpointtech.com/csharp-variables#)

1. using System;  
2. public class Updates  
3. {  
4.     public static void Main(string[] args)  
5.     {  
6.         int value= 15;   
7.         Console.WriteLine("The entered the value is " +value);  
8.         value= 25;  
9.         Console.WriteLine("The updated value is " + value);  
10.     }  
11. }  

**Output:**

The entered the value is 15
The updated value is 25

**Explanation:**

In this example, we have taken an integer variable value that is first initialized with 15 and displayed. After that, this value is updated to 25, and the new value is printed.

## Rules for Creating a Variable

In C#, if we want to create a variable, we have to follow the following rules. These are as follows:

- Variable names should be case-sensitive.
- Variable names must start with an alphabet. It can be alpha-numeric.
- We cannot write the special symbol. Only underscore (_) is allowed.
- We can't use a keyword name as a variable.
- We have used a limited number of characters in a variable name. Usually, variable names are sufficient between 10 to 12 characters.
- We used the comma (,) symbol to create more than one variable.
- Wide space is not allowed between variable names.

## Types of Variable in C#

In C#, there are five types of Variables. These are as follows:

![C# Variables](https://images.tpointtech.com/csharp/images/csharp-variables.png)

Here, we will discuss these variables one by one.

### 1) Local Variables

In C#, local variables are those variables that are defined within a block method or [constructor](https://www.tpointtech.com/c-sharp-constructor). The scope of these variables exists only within the block and outside the constructor.

**C# Local Variables Example**

Let us take an example to illustrate local variable in C#.

### Example

[](https://www.tpointtech.com/csharp-variables#)[](https://www.tpointtech.com/csharp-variables#)[](https://www.tpointtech.com/csharp-variables#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {  
6.         int number = 100; // Local variable  
7.         Console.WriteLine("The entered number is " +number);  
8.     }  
9. }  

**Output:**

The entered number is 100

**Explanation:**

In this example, we have taken an integer number that shows the local variable. After that, we use the Console.WriteLine() to print the output.

### 2) Instance Variable or Non-Static Variables:

In C#, instance variables are also known as non-static variables that are declared in a class but outside any method, constructor, or block. These variables execute when we create an object of the class. We can use the [access specifiers](https://www.tpointtech.com/c-sharp-access-modifiers) to create an instance variable.

**C# Instance Variable Example**

Let us take an example to illustrate the instance variable in C#.

### Example

[](https://www.tpointtech.com/csharp-variables#)[](https://www.tpointtech.com/csharp-variables#)[](https://www.tpointtech.com/csharp-variables#)

1. using System;     
2. class Records {  
3.     string name;  // Instance Variable  
4.     int Marks;   
5.     string performance;    
6.     // Main Method  
7.     public static void Main(String[] args)  
8.     {     
9.         Records obj = new Records(); // create the object of the class  
10.         obj.name = "John";  
11.         obj.Marks = 95;  
12.         obj.performance = "Excellent";  
13.         // showing the records of student   
14.         Console.WriteLine("Record of Students is ");  
15.         Console.WriteLine("The name of the student is " + obj.name);  
16.         Console.WriteLine("The mark of student is " +obj.Marks);  
17.         Console.WriteLine("The performance of the student is " +obj.performance);  
18.     }  
19. }  

**Output:**

Record of Students is
The name of Student is John
The mark of Student is 95
The performance of the student is Excellent

**Explanation:**

In this example, we create integer and string-type variables inside the class. After that, we create the object of the class to build the program.

### 3) Static Variable or Class Variables:

In C#, static variables are also known as class variables that are declared inside a class but outside any method, constructor, or block. These variables are generally like instance variables. We can create the static variable by using the static keyword. In static variables, objects cannot be created during the execution of programs.

**C# Static Variables Example**

Let us take an example to illustrate the static variable in C#.

### Example

[](https://www.tpointtech.com/csharp-variables#)[](https://www.tpointtech.com/csharp-variables#)[](https://www.tpointtech.com/csharp-variables#)

1. using System;  
2. class Employee {  
3.     static int num;    // integer variable  
4.     static string name = "John";      
5.     public static void Main(String[] args)       
6.     {  
7.         Employee.num = 950;   // Accessing the variable  
8.         Console.WriteLine(Employee.name + "'s total marks is " + Employee.num);  
9.     }  
10. }  

**Output:**

John's total marks is 950

**Explanation:**

In this example, we create integer and string-type static variables inside the class. After that, we access the static variables in the main method.

### 5) Constant Variable:

In C#, Constant variables are declared by using the **const** keyword. These variables cannot be changed once initialized.

**C# Constant Variable Example**

Let us take an example to illustrate the constant variable in C#.

### Example

[](https://www.tpointtech.com/csharp-variables#)[](https://www.tpointtech.com/csharp-variables#)[](https://www.tpointtech.com/csharp-variables#)

1. using System;  
2. class Program  
3. {  
4.     const int number = 100;  // constant variable   
5.     static void Main()  
6.     {  
7.         Console.WriteLine("The number is " + number);  
8.     }  
9. }  

**Output:**

The number is: 100

**Explanation:**

In this example, we create a constant variable and access the value in the main method.

## Readonly Variables:

In C#, readonly variables are declared by using the **readonly** keyword. This variable cannot change the value, once initialized. The readonly variable is not compulsory to initialize at the time of declaration, and it can also initialize in the constructor.

### C# Readonly Variables Example

Let us take an example to illustrate the readonly variable in C#.

### Example

[](https://www.tpointtech.com/csharp-variables#)[](https://www.tpointtech.com/csharp-variables#)[](https://www.tpointtech.com/csharp-variables#)

1. using System;  
2. class Program {  
3.     static int number = 400;   
4.     readonly int num1;  
5.     public static void Main()  
6.     {  
7.         Program obj = new Program();  
8.         Console.WriteLine("The value of b is = " + Program.number);  
9.         Console.WriteLine("The value of k is = " + obj.num1);  
10.     }  
11. }  

**Output:**

The value of b is = 400
The value of k is = 0

**Explanation:**

In this example, we have taken a static variable that is shared across all instances and initialized with 400. After that, the readonly num1 variable gets the default value 0 because it's not explicitly assigned.

## Scope of Variables

In C#, the scope of variables specifies the variable accessibility to a specific section of the applications. There are mainly three types of scopes of variables in C#.

![C# Variables](https://images.tpointtech.com/csharp/images/csharp-variables2.png)

Here, we will discuss the scope of variables in C# one by one.

### Class Level Scope

In C#, class-level scope refers to the variable that is declared within the class, outside of methods and constructors. It makes them accessible anywhere in the class of the program. We can access the variables using the non-static methods of the class where these variables are declared.

**C# Class Level Scope Variable Example**

Let us take an example to illustrate the class-level scope variable in C#.

### Example

[](https://www.tpointtech.com/csharp-variables#)[](https://www.tpointtech.com/csharp-variables#)[](https://www.tpointtech.com/csharp-variables#)

1. using System;  
2. public class Example  
3. {  
4.     int number = 50;  // class-level variable   
5.     public void show()  
6.     {  
7.         Console.WriteLine("Number is " + number);  // accessing class-level variable  
8.     }  
9. }  
10. public class Program  
11. {  
12.     public static void Main()  
13.     {  
14.         Example s = new Example();  
15.         s.show();  
16.     }  
17. }  

**Output:**

Number is 50

**Explanation:**

In this example, we have taken the class-level variable (number=50). After that, we create the Show() function, where the variable is being accessed.

### Method-Level Scope

In C#, method-level scope is variables that are declared inside the method (function). It is also known as a local variable, and these variables can't be accessed outside the method.

**C# Method-Level Scope Example**

Let us take an example to illustrate the method-level scope variable in C#.

### Example

[](https://www.tpointtech.com/csharp-variables#)[](https://www.tpointtech.com/csharp-variables#)[](https://www.tpointtech.com/csharp-variables#)

1. using System;  
2. class Example  
3. {  
4.     static void Main()  
5.     {  
6.         int num = 1000; // Method-level variable  
7.         Console.WriteLine("The number is " + num);  
8.     }  
9. }  

**Output:**

The number is 1000

**Explanation:**

In this example, we represent the method level variable using the int num=1000. After that, the output is print using the Console.WriteLine() method.

### Code-Block Level Scope:

In C#, code-block level scope means the variable works only within the class. A variable cannot be accessed outside of the block of code.

**C# Code-Block Level Scope Example**

Let us take an example to illustrate the Code-Block level scope variable in C#.

### Example

[](https://www.tpointtech.com/csharp-variables#)[](https://www.tpointtech.com/csharp-variables#)[](https://www.tpointtech.com/csharp-variables#)

1. using System;  
2. public class Num  
3. {  
4.     public static void Main() {  
5.         Num obj = new Num();  
6.         obj.showNum();  
7.     }  
8.     void showNum() {  
9.         for (int i = 0; i < 5; i++) {  
10.             Console.WriteLine(i);  // 'i' is exist here  
11.         }  
12.         // Console.WriteLine(i); // Error: 'i' does not exist here  
13.     }  
14. }  

**Output:**

0
1
2
3
4

**Explanation:**

In this example, we have taken the code-block level scope 'i', where the variable is declared in the 'for' loop. After that, we will create the instance to invoke the function.

## Conclusion

In C#, variables are a key factor for any developer creating a software application. It is the main objective for development. Variables are containers that represent the location of memory. It has five types: local, instance, static, constant, and read-only. These are very crucial roles in programming.