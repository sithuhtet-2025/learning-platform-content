
In the C# programming language, a struct (known as a structure) is like a class that is used to store data under a single unit. Structs are value types, which means that they are stored on the stack and passed by value rather than by reference. It contains many distinct [data types](https://www.tpointtech.com/csharp-data-types), and it is a user-defined data type. It can include nested types, constants, fields, methods, properties, indexers, [operators](https://www.tpointtech.com/csharp-operators), [events](https://www.tpointtech.com/events-in-c-sharp), and a parameterized or [static constructor](https://www.tpointtech.com/c-sharp-static-constructor). The Struct is defined by the struct keyword.

![C# Structs](https://images.tpointtech.com/csharp/images/c-sharp-structs.png)

## Define a struct in C#

In C#, the structure can be defined using the struct keyword.

**For Example:**

[](https://www.tpointtech.com/c-sharp-structs#)[](https://www.tpointtech.com/c-sharp-structs#)[](https://www.tpointtech.com/c-sharp-structs#)

1. struct master  
2. {  
3. public int id;  
4. }   

## Declare a struct Variable in C#

In [C# programming](https://www.tpointtech.com/c-sharp-tutorial), we must first declare a struct variable before using a struct. It is done by specifying the struct name followed by the variable name.

**For Example:**

[](https://www.tpointtech.com/c-sharp-structs#)[](https://www.tpointtech.com/c-sharp-structs#)[](https://www.tpointtech.com/c-sharp-structs#)

1. struct master {  
2.   public int id;  
3. }  
4. . . .  
5. // declare mst of the struct Employee  
6. master mst;  

## Access the Struct Member in C#

The dot (.) operator is used to access the struct member. The examples are as given below.

**For Example:**

[](https://www.tpointtech.com/c-sharp-structs#)[](https://www.tpointtech.com/c-sharp-structs#)[](https://www.tpointtech.com/c-sharp-structs#)

1. struct Master {  
2.   public int id;  
3. }  
4. ...   
5. // declare mst of struct Master  
6. Master mst;  
7. // accessing the member    
8. mst.id = 1;  

Here, we are using the **mst** variable with the dot (.) operator to access the members of the master.

## Struct Example in C#

Let us take an example to define a struct in C#.

### Example

[](https://www.tpointtech.com/c-sharp-structs#)[](https://www.tpointtech.com/c-sharp-structs#)[](https://www.tpointtech.com/c-sharp-structs#)

1. using System;  
2. struct Person  
3. {  
4.     public string Name;  
5.     public int Age;  
6.     // Method inside struct  
7.     public void DisplayInfo()  
8.     {  
9.         Console.WriteLine("The name is " + Name );  
10.         Console.WriteLine("The age is " + Age );  
11.     }  
12. }  
13. class Program  
14. {  
15.     static void Main()  
16.     {  
17.         // Declare and initialize struct variable  
18.         Person p1;  
19.         p1.Name = "Michael";  
20.         p1.Age = 25;  
21.         // Calling method  
22.         p1.DisplayInfo();  
23.     }  
24. }  

**Output:**

The name is Michael
The age is 25

**Explanation:**

In this example, we create a struct named Person that contains two variables, name (string) and age (integer). After that, it defines the parameterised constructor to initialize these fields and the DisplayInfo() method to print the details. In the main method, we create the object (p1) and call the DisplayInfo() method to display the details.

## struct Constructor in C#

In C#, we can create a [constructor](https://www.tpointtech.com/c-sharp-constructor) for a struct by defining it with the public keyword followed by the struct name.

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-structs#)[](https://www.tpointtech.com/c-sharp-structs#)[](https://www.tpointtech.com/c-sharp-structs#)

1. struct StructName  
2. {  
3.     // Fields  
4.     public int x;  
5.     public int y;  

6.     // Parameterized constructor  
7.     public StructName( int a, int b )  
8.     {  
9.         x = a;  
10.         y = b;  
11.     }  
12. }  

### Constructor in C# struct Example

Let us take an example to illustrate the struct using a Constructor.

### Example

[](https://www.tpointtech.com/c-sharp-structs#)[](https://www.tpointtech.com/c-sharp-structs#)[](https://www.tpointtech.com/c-sharp-structs#)

1. using System;  
2. struct Details  
3. {  
4.     public string name;  
5.     public int age;  
6.     // Constructor  
7.     public Details( string na_me, int a_ge )  
8.     {  
9.         name = na_me;  
10.         age = a_ge;  
11.     }  
12.     public void DisplayInfo()  
13.     {  
14.         Console.WriteLine("The name is: " + name + ", age: " + age );  
15.     }  
16. }  
17. class Program  
18. {  
19.     static void Main()  
20.     {  
21.         // structure object  
22.         Details d1 = new Details("Jhonson", 25);  
23.         d1.DisplayInfo();  
24.     }  
25. }  

**Output:**

The name is: Jhonson, Age: 25

**Explanation:**

In this example, we create a struct named Person that contains two variables, name (string) and age (integer). After that, it defines the parameterised constructor to initialize these fields and the DisplayInfo() method to print the details. In the main method, we create the object (p1) and call the DisplayInfo() method to display the details.

## Immutable Structure (struct)

In the C# programming language, a structure is said to be immutable if its state cannot be changed once it has been created. It means that no fields or properties of the struct can be modified after construction.

### Example of Immutable Structure

Let us take an example to illustrate the immutable structure in C#.

### Example

[](https://www.tpointtech.com/c-sharp-structs#)[](https://www.tpointtech.com/c-sharp-structs#)[](https://www.tpointtech.com/c-sharp-structs#)

1. using System;  
2. struct Details {  
3.     public readonly string name;  
4.     public readonly string contact;  
5.     public readonly string id;  
6.     public Details( string name, string contact, string id ) {  
7.         this.name = name;  
8.         this.contact = contact;  
9.         this.id = id;  
10.     }  
11.     public void ShowDetail() {  
12.         Console.WriteLine($"Name: {name}, Contact: {contact}, ID: {id} ");  
13.     }  
14. }  
15. class Program {  
16.     static void Main() {  
17.         Details d = new Details("Albert", "878283XXXX", "EMPO01");  
18.         d.ShowDetail();  
19.     }  
20. }  

**Output:**

Name: Albert, Contact: 878283XXXX, ID: EMPO01

**Explanation:**

In this example, we define the immutable struct named Details that contains three readonly fields: name, contact, and id. After that, we create a parameterized constructor and set the value. The ShowDetails() method displays these values. In the main method, create the object and call the ShowDetail() method to print the details.

## Array of Structures in C#

In C#, an array of structures allows us to store multiple instances of a structure in a single array. It can access the structure member using an [array](https://www.tpointtech.com/c-sharp-arrays) with a specific index.

**Syntax:**

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-structs#)[](https://www.tpointtech.com/c-sharp-structs#)[](https://www.tpointtech.com/c-sharp-structs#)

1. Array[ index ].Structure( data );  

In this syntax, an index is defined, the particular indexes of an array where the values are inserted or deleted, and the data are the values in the structure.

### Array of Structure Example in C#

Let us take an example to illustrate the array of structure in C#.

### Example

[](https://www.tpointtech.com/c-sharp-structs#)[](https://www.tpointtech.com/c-sharp-structs#)[](https://www.tpointtech.com/c-sharp-structs#)

1. using System;  

2. public struct Emp  
3. {  
4.     // Declare variables  
5.     public int Roll_No;  
6.     public string Name;  
7.     public int Age;  

8.     // Set the employee details  
9.     public void Set_Emp(int RollNo, string name, int age)  
10.     {  
11.         Roll_No = RollNo;  
12.         Name = name;  
13.         Age = age;  
14.     }  

15.     // Display employee details  
16.     public void Display_Emp()  
17.     {  
18.         Console.WriteLine("Employee details: ");  
19.         Console.WriteLine("Id: " + Roll_No);  
20.         Console.WriteLine("Name: " + Name);  
21.         Console.WriteLine("Age: " + Age);  
22.         Console.WriteLine("\n");  
23.     }  
24. }  

25. class TPT  
26. {  
27.     static void Main(string[] args)  
28.     {  
29.         // Create an array of Emp structs  
30.         Emp[] e = {  
31.             new Emp(),  
32.             new Emp(),  
33.             new Emp()  
34.         };  

35.         // Set values for each employee  
36.         e[0].Set_Emp(1, "John", 50);  
37.         e[1].Set_Emp(2, "Thomson", 31);  
38.         e[2].Set_Emp(3, "David", 27);  

39.         // Display employee details  
40.         e[0].Display_Emp();         
41.         e[1].Display_Emp();  
42.         e[2].Display_Emp();  
43.     }  
44. }  

**Output:**

Employee details:
Id: 1
Name: John
Age: 50

Employee details:
Id: 2
Name: Thomson
Age: 31

Employee details:
Id: 3
Name: David
Age: 27

**Explanation:**

In this example, we define the struct named Emp that contains three variables: Roll_No, Name, and Age. We also contain two methods: Set_Emp() to assign values and Display_Emp() to show the details of the employee. In the main method, an array of three Emp structures is created and initialized using the Set_Emp() method. After that, the program shows each employee's details using the Display_Emp() method.

## Properties in C# Struct

In the C# programming language, the [properties](https://www.tpointtech.com/c-sharp-properties) in a struct (structure) are used to encapsulate and manage access to the fields of the struct. Just like in classes, structs can also have properties with get and set accessors, and they can also be read-only.

### Properties Struct Example in C#

Let us take an example to illustrate the Struct property in C#.

### Example

[](https://www.tpointtech.com/c-sharp-structs#)[](https://www.tpointtech.com/c-sharp-structs#)[](https://www.tpointtech.com/c-sharp-structs#)

1. using System;  
2. namespace Struct {  
3.   // declare the struct  
4.   struct Stu_dent {  
5.     public int id;  
6.     // define property  
7.     public int Id {  
8.       get {  
9.         return id;  
10.       }  
11.       // sets the value  
12.       set {  
13.         id = value;  
14.       }  
15.     }  
16.   }  
17.   class Program {  
18.     static void Main(string[] args) {  
19.       // Invoke the Constructor   
20.       Stu_dent std = new Stu_dent();  
21.       std.Id = 1;  
22.       Console.WriteLine("Student Id: " + std.Id);  
23.       Console.ReadLine();  
24.     }  
25.   }  
26. }  

**Output:**

Student Id: 1

**Explanation:**

In this example, we have taken a struct named Stu_dent that is defined with a private field id and a public property Id that provides controlled access to it using get and set accessors. In the main() method, an instance of the struct is created, the Id property is assigned a value, and then the result is displayed.

## Difference between the Structure and Class

There are several differences between the structure and class in C#. Some main differences are as follows:

|Structure|Class|
|---|---|
|Structure is a value type.|Class is a reference type.|
|Inheritance is not supported in the structure.|Inheritance is supported in class.|
|Structure is defined by the struct keyword.|The class is defined by the class keyword.|
|The structure members are public by default.|The class members are private by default.|
|The syntax of the structure is.  <br>Struct StructName {  <br>datatype m1;  <br>datatype m2;  <br>};|The syntax of the class is.  <br>Class ClassName {  <br>// data member  <br>// data method  <br>};|

## Features of C# Structure:

Several features of the C# Structure are as follows.

- The structure can have methods, properties, indexers, fields, operator methods, and events.
- It can also include parameterized constructors, constants, enumerations, and nested types.
- A structure is a value type, which means that it is stored on the stack and passed by value.
- A structure can be implemented with one or more interfaces.
- Struct members cannot be protected, virtual, or abstract.

## Conclusion

In conclusion, C# structure (struct) is an essential concept for any developer creating a software application. It is the main objective of the development. A struct is like a class that is used to store data under a single unit. It is a value type. It contains many distinct data types. It contains several methods, properties, indexers, fields, operator methods, and events.