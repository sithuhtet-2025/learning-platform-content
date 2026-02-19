
In the C# programming language, a static is a keyword or modifier that belongs to the type, not the instance. However, the instance is not required to access the static members. In C#, static can be a field, method, [constructor](https://www.tpointtech.com/c-sharp-constructor), class, property, [operator](https://www.tpointtech.com/csharp-operators), or event. It means a static member is shared across all objects of the class, and we can access it without creating an object.

In C#, the static keyword is used as a modifier and can be applied to the following members:

![C# static](https://images.tpointtech.com/csharp/images/c-sharp-static.png)

Here, we will discuss these static keywords one by one.

## 1) Static Classes

In the [C# programming language](https://www.tpointtech.com/c-sharp-tutorial), a static class is a class that cannot be instantiated and has only static members. A static class can be declared using the static keyword. It is often used to organize utility or help methods. [Static classes](https://www.tpointtech.com/c-sharp-static-class) are sealed, which means that we cannot inherit a static class from another class.

### Rules of Static Class

There are several rules of a static class in C#. Some of them are as follows:

- It cannot be instantiated or inherited (it is inherently sealed).
- It can only have static members (fields, methods, properties, and many others).
- There are no instance members or constructors allowed.
- Indexers and [destructors](https://www.tpointtech.com/c-sharp-destructor) cannot be static or included.
- The var keyword is not permitted for static members; explicit type is required.
- Members are accessed using their ClassName.MemberName.
- It remains in memory throughout the application domain's lifespan.

### Key features of Static Class

There are several key features of a static class in C#. Some of them are as follows:

- The static keyword is used to declare a static class.
- All of the members must be static.
- This property cannot be inherited or instantiated.

### C# Static Class Example

Let us take an example to illustrate the static class in C#.

### Example

[](https://www.tpointtech.com/c-sharp-static#)[](https://www.tpointtech.com/c-sharp-static#)[](https://www.tpointtech.com/c-sharp-static#)

1. using System;  

2. // Static class  
3. static class Tpoint  
4. {  
5.     public static string App_Name = "Instagram";  
6.     public static string Version = "8.0.0";  

7.     public static void Display()  
8.     {  
9.         Console.WriteLine("The App name is: " + App_Name + " | The app Version is: " + Version);  
10.     }  
11. }  

12. // Separate Test class with Main method  
13. class Test  
14. {  
15.     static void Main()  
16.     {  
17.         Tpoint.Display();  
18.     }  
19. }  

**Output:**

The App name is: Instagram | The app Version is: 8.0.0

**Explanation:**

In this example, we have taken a class Tpoint that contains only static members (App_Name, Version, and Display()), and it cannot be instantiated. After that, the Test class calls the static method directly using the class name, which shows how static classes are useful to collect utility or helper methods.

## 2) Static Fields

In the C# programming language, static fields can be declared within a non-static class by using the static keyword. These fields are shared by all instances of the class, which means that they belong to the class rather than any individual object.

### Key features of Static Field

There are several features of a static field in C#. Some of them are as follows:

- A static field is only initialized once and has a single memory address.
- Any changes made to the static field by one object will be visible to all other instances of the same class.
- Static fields are useful for storing data or configurations that are the same across all instances.

### C# Static Field example

Let us take an example to illustrate a static field in C#.

### Example

[](https://www.tpointtech.com/c-sharp-static#)[](https://www.tpointtech.com/c-sharp-static#)[](https://www.tpointtech.com/c-sharp-static#)

1. using System;  
2. public class Account  
3. {  
4. public int accno;  
5. public String name;  
6. public static float rateOfInterest=8.8f;  
7. public Account(int accno, String name)  
8. {  
9. this.accno = accno;  
10. this.name = name;  
11. }  

12. public void display()  
13. {  
14. Console.WriteLine(accno + " " + name + " " + rateOfInterest);  
15. }  
16. }  
17. class TestAccount  
18. {  
19. public static void Main(string[] args)  
20. {  
21. Account acc1 = new Account(101, "Jhonson");  
22. Account acc2 = new Account(102, "Adam");  
23. acc1.display();  
24. acc2.display();  
25. }  
26. }  

**Output:**

101 Jhonson 8.8
102 Adam 8.8

**Explanation:**

In this example, we have taken an Account class that contains instance variables (accno, name) and a static variable (rateOfInterest) shared across all objects. After that, we create two account objects, and their details, along with the common interest rate, are displayed.

### C# Field Example to Change Static Field

If we change the value of a static field, it will be applied to all the objects.

### Example

[](https://www.tpointtech.com/c-sharp-static#)[](https://www.tpointtech.com/c-sharp-static#)[](https://www.tpointtech.com/c-sharp-static#)

1. using System;    
2.    public class Account    
3.     {    
4.         public int accno;     
5.         public String name;    
6.         public static float rateOfInterest=8.8f;    
7.         public Account(int accno, String name)    
8.         {    
9.             this.accno = accno;    
10.             this.name = name;    
11.         }    

12.         public void display()    
13.         {    
14.             Console.WriteLine(accno + " " + name + " " + rateOfInterest);    
15.         }    
16.    }    
17.    class TestAccount{    
18.        public static void Main(string[] args)    
19.         {    
20.             Account.rateOfInterest = 10.5f;//changing value    
21.             Account acc1 = new Account(101, "Jhonson");    
22.             Account acc2 = new Account(102, "Adam");    
23.             acc1.display();    
24.             acc2.display();    
25.         }    
26.     }  

**Output:**

101 Jhonson 10.5
102 Adam 10.5

**Explanation:**

In this example, we have taken the class Account that has two instance variables (accno, name) and one static variable (rateOfInterest), which is shared by all objects. In the Main() method, the static variable's value is updated to 10.5f before creating two objects. When the display() method is called, both objects show their individual account details along with the same updated interest rate.

## 3) Static Method

In the C# programming language, a static method is a method that can be called on the class itself without creating a new instance. It has direct access to static fields or other static methods. The static method can be declared using the static keyword.

### Rules of Static Method

There are several rules for a static method in C#. Some of them are as follows:

- A static method is defined using the static keyword that was declared before the return type.
- It can be overloaded but cannot be overridden.
- Static members can only be accessed directly using a static method.
- Access to instance members is only possible when they are supplied as parameters.

### Key Features of Static Method

There are several key features of a static method in C#. Some main features are as follows:

- Non-static members cannot be directly accessed.
- It was called with the class name.
- It is useful for functions or actions that are not dependent on object state.

### C# Static Method Example

Let us take an example to illustrate the static method in C#.

### Example

[](https://www.tpointtech.com/c-sharp-static#)[](https://www.tpointtech.com/c-sharp-static#)[](https://www.tpointtech.com/c-sharp-static#)

1. using System;  

2. class Tpoint  
3. {  
4.     public static int SquareNumber(int Num_ber)  
5.     {  
6.         return Num_ber * Num_ber;  
7.     }  
8. }  

9. class Test  
10. {  
11.     static void Main()  
12.     {  
13.         Console.WriteLine("The Square of 10 is: " + Tpoint.SquareNumber(10));  
14.     }  
15. }  

**Output:**

The Square of 10 is: 100

**Explanation:**

In this example, we have taken the SquareNumber method that is declared as static inside the Tpoint class, which can be called directly using the class name without creating an object. After that, the main method calls it to calculate and display the square of 10.

## 4) Static Constructor

In the C# programming language, the static constructor is commonly utilized to initialize a class's static members. It is invoked automatically once before any static members are accessed or the class is created.

### Rules for Static Constructor

There are several rules for a static constructor in C#. Some of them are as follows:

- It is declared using the static keyword. It doesn't take any parameters or access modifiers.
- Each class may only have one static constructor.
- The execution timing is unpredictable.
- It cannot be called directly.
- Once it is executing, the user has no control over C#.
- It is invoked automatically to initialize the class before the creation of the first instance.

### C# Static Constructor Example

Let us take an example to illustrate the static constructor in C#.

### Example

[](https://www.tpointtech.com/c-sharp-static#)[](https://www.tpointtech.com/c-sharp-static#)[](https://www.tpointtech.com/c-sharp-static#)

1. using System;  
2. class Tpoint  
3. {  
4.     public static string LogType;  
5.     static Tpoint()  
6.     {  
7.         LogType = "INFO";  
8.         Console.WriteLine("Static constructor is called.");  
9.     }  
10.     public static void Log(string message)  
11.     {  
12.         Console.WriteLine($"[{LogType}]: {message}");  
13.     }  
14. }  
15. class Program  
16. {  
17.     static void Main()  
18.     {  
19.         Tpoint.Log("Application is started");   
20.         Tpoint.Log("Performing some of the tasks");  
21.     }  
22. }  

**Output:**

Static constructor is called.
[INFO]: Application is started
[INFO]: Performing some of the tasks

**Explanation:**

In this example, we have taken a class Tpoint that initializes the static field LogType, and executes automatically before the first use of the class. After that, the log method uses this initialized value to print the log message in the console.

## Limitations of Static Keyword

There are several limitations of a Static Keyword in C#. Some of them are as follows:

- The "this" keyword is incompatible with the static keyword.
- Static classes are unable to implement interfaces.
- Indexers, destructors, and events cannot be kept static.
- Static members cannot be accessed through an object reference.

## Conclusion

In conclusion, the C# static keyword is mainly used to define members (variables, methods, constructors, or classes) that belong to the class itself rather than to any specific object. Static members are shared across all objects, which means that changes made through one object are reflected in all others. They are useful for common data and utility methods. However, they cannot access non-static (instance) members directly because they are linked to the class.