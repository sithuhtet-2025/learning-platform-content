
In the C# programming language, a static constructor is a special type of constructor that is used to initialize static fields of a class. It can also be used to perform any action that is to be performed only once. It is invoked automatically before the first instance is created or any static member is referenced. It also ensures that the class-level data is completely initialized before it is used.

![C# Static Constructor](https://images.tpointtech.com/csharp/images/c-sharp-static-constructor.png)

### Syntax:

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-static-constructor#)[](https://www.tpointtech.com/c-sharp-static-constructor#)[](https://www.tpointtech.com/c-sharp-static-constructor#)

1. class ClassName  
2. {  
3.     //static constructor  
4.     static ClassName()  
5.     {  
6.         // Initialization code here  
7.     }  
8. }  

In this syntax;

- **ClassName:** It represents the name of the class.
- **Static ClassName:** It represents the static constructor of the class.

### C# Static Constructor Example

Let us take an example to illustrate the static constructor in C#.

### Example

[](https://www.tpointtech.com/c-sharp-static-constructor#)[](https://www.tpointtech.com/c-sharp-static-constructor#)[](https://www.tpointtech.com/c-sharp-static-constructor#)

1. using System;  

2. class Tpoint  
3. {  
4.     public static string message;  

5.     // Static constructor  
6.     static Tpoint()  
7.     {  
8.         message = "Hello! this is a static constructor.";  
9.         Console.WriteLine("Static constructor executed.");  
10.     }  

11.     public static void ShowMessage()  
12.     {  
13.         Console.WriteLine(message);  
14.     }  
15. }  

16. class Program  
17. {  
18.     static void Main()  
19.     {  
20.         // Calling static method  
21.         Tpoint.ShowMessage();  
22.     }  
23. }  

**Output:**

Static constructor executed.
Hello! this is a static constructor.

**Explanation:**

In this example, we have taken a class Tpoint that has a static field (message) and a static constructor that initializes it. After that, the static constructor is called automatically only once, before any member of the class is accessed. When the ShowMessage() method is called in the Main() method, it first triggers the static constructor, prints the initialization message, and then displays the static field value.

### Remember the following key points:

There are several points to remember about a static constructor in C#. Some of them are as follows:

- Static constructor executes automatically before accessing static members or creating the initial object.
- It doesn't have any parameters or [access modifiers](https://www.tpointtech.com/c-sharp-access-modifiers).
- The user cannot specifically invoke it.
- The execution is handled by the runtime. Therefore, we have no influence over the timing.
- Static data is only initialized once, which makes it ideal for single-use.
- If any static field initializers are present, they execute before the static constructor.
- It only runs once during the program's lifetime, regardless of how many times the class is accessed.
- A class can contain only one static constructor.
- It is mainly utilized to initialize static fields of a class.
- It cannot be inherited or overloaded.

## How Static Constructors Work in C#?

In the [C# programming language](https://www.tpointtech.com/c-sharp-tutorial), a static constructor is a type of [constructor](https://www.tpointtech.com/c-sharp-constructor) that is commonly utilized to initialize the static members of a class. It is automatically executed only once by the [CLR (Common Language Runtime)](https://www.tpointtech.com/net-common-language-runtime), before the class is accessed for the first time, either via creating an object or calling a static member. There are several steps that can help us understand the working of a static constructor in C#.

1. **Static Member Initialization:** Runtime activates static constructors for member initialization. They run before any static members are used to ensure that they have been properly initialized and are ready to be used.
2. **Execution Timing:** The static constructor is only called once, when the class is first used, either by accessing a static member or creating an object. However, because the exact timing of execution is not guaranteed, we should avoid writing code that is dependent on a specific order.
3. **Exception Handling:** The runtime does not handle [exception handling](https://www.tpointtech.com/c-sharp-exception-handling) if it throws an exception. As a result, the type is rendered unusable for the rest of the application's existence.

### C# Static Constructor Example using Object Creation

Let us take an example to illustrate the static constructor using object creation in C#.

### Example

[](https://www.tpointtech.com/c-sharp-static-constructor#)[](https://www.tpointtech.com/c-sharp-static-constructor#)[](https://www.tpointtech.com/c-sharp-static-constructor#)

1. using System;    
2.  public class Account     
3. {    
4. public int id;     
5. public String name;    
6. public static float rateOfInterest;    
7. public Account(int id, String name)    
8. {    
9. this.id = id;    
10. this.name = name;  
11. }  
12. static Account()    
13. {    
14. rateOfInterest = 9.5f;    
15. }    
16. public void display()    
17. {    
18. Console.WriteLine(id + " " + name+" "+rateOfInterest);    
19. }    
20. }    
21. class Tpoint  
22. {    
23. public static void Main(string[] args)    
24. {    
25. Account acc1 = new Account(101, "Jhonson");   
26. Account acc2 = new Account(102, "Smith");    
27. acc1.display();    
28. acc2.display();      
29. }   
30. }    

**Output:**

101 Jhonson 9.5
102 Smith 9.5

**Explanation:**

In this example, we have taken an Account class, which has a static constructor that initializes the static field rateOfInterest to 9.5f. After that, the static constructor is executed only once automatically before the first object of the class is created. When we create two objects (acc1 and acc2), they share the same rateOfInterest value, and their details are displayed with the common interest rate.

### C# Static Constructor Example with Single Execution

Let us take an example to illustrate the static constructor with single execution in C#.

### Example

[](https://www.tpointtech.com/c-sharp-static-constructor#)[](https://www.tpointtech.com/c-sharp-static-constructor#)[](https://www.tpointtech.com/c-sharp-static-constructor#)

1. using System;  

2. class Login  
3. {  
4.     public static string logType;  

5.     static Login()  
6.     {  
7.         logType = "INFO";  
8.         Console.WriteLine("Static constructor is successfully executed.");  
9.     }  

10.     public static void Log(string message)  
11.     {  
12.         Console.WriteLine($"[{logType}]: {message}");  
13.     }  
14. }  

15. class Tpoint  
16. {  
17.     static void Main()  
18.     {  
19.         Login.Log("Application has started");  
20.         Login.Log("Performing tasks");  
21.         Login.Log("Application has ended");  
22.     }  
23. }  

**Output:**

Static constructor is successfully executed.
[INFO]: Application has started
[INFO]: Performing tasks
[INFO]: Application has ended

**Explanation:**

In this example, we have taken a Login class, which has a static constructor that initializes the static field logType with "INFO". After that, a static constructor is executed only once, before the class is used for the first time. When the Log method is called multiple times, it uses the same initialized value of logType. Finally, it prints the result in the console.

## Conclusion

In conclusion, C# static constructors are required to initialize static members and conduct one-time setup activities before accessing any class instance or static member. Their automatic and single-time execution assures consistent initialization while relieving the developer of manual invocation.