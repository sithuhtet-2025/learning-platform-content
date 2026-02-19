

In the C# programming language, the static class is like a normal class, but it cannot be instantiated or inherited. It can have only static members, such as methods, fields, [properties](https://www.tpointtech.com/c-sharp-properties), and [constructors](https://www.tpointtech.com/c-sharp-constructor). As a static class is automatically [sealed](https://www.tpointtech.com/c-sharp-sealed) and abstract, it is suitable to represent the utility or helper classes in which objects are not required.

![C# Static Class](https://images.tpointtech.com/csharp/images/c-sharp-static-class.png)

The Common Language Runtime (CLR) makes sure that the static members of the class are loaded and can be used during the lifetime of the application.

### Syntax:

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-static-class#)[](https://www.tpointtech.com/c-sharp-static-class#)[](https://www.tpointtech.com/c-sharp-static-class#)

1. static class ClassName  
2. {  
3.     // static fields  
4.     // static properties  
5.     // static methods  
6. }  

In this syntax,

- **ClassName:** It represents the name of the class.
- **static class ClassName:** It represents the static class.

### Static Class Example in C#

Let us take an example to illustrate the static class that contains a static field and a static method in C#.

### Example

[](https://www.tpointtech.com/c-sharp-static-class#)[](https://www.tpointtech.com/c-sharp-static-class#)[](https://www.tpointtech.com/c-sharp-static-class#)

1. using System;    
2.    public static class MyMath    
3.     {    
4.         public static float PI=3.14f;     
5.         public static int cube(int n){return n*n*n;}    
6.     }    
7.    class TestMyMath{    
8.        public static void Main(string[] args)    
9.         {    
10.             Console.WriteLine("Value of PI is: "+MyMath.PI);    
11.             Console.WriteLine("Cube of 3 is: " + MyMath.cube(3));    
12.         }    
13.     }    

**Output:**

Value of PI is: 3.14
Cube of 3 is: 27

**Explanation**

In this example, we declare a static class MyMath with a static field PI and a static method cube() that returns the cube of a figure. In the Main() method of TestMyMath, both members are accessed directly through the class name without object creation. After that, it prints the value of PI and the cube of 3.

### Points to remember for C# static class

Several important points for static class in C# are as follows:

- A C# static class contains only static members.
- A C# static class cannot be instantiated.
- A C# static class is sealed.
- A C# static class cannot contain instance constructors.
- Static class members can be accessed u the class name.
- Static classes can be created once and remain for the lifetime of the application.

## When to Use Static Classes in C#?

In C#, static classes are very useful when we need to group methods, properties, or fields. These classes are common to the entire application and do not depend on objects. These classes are suitable for utility or helper functionality, including configuration handling, performing mathematical operations, logging, or string manipulation, in which the behavior always remains the same and does not need to maintain a state.

As static classes cannot be instantiated or inherited, they ensure a single and globally accessible group of members. These classes are suitable for those situations where there should only exist a single version of the data or logic during the program.

### C# Static Class Example for Application Configuration

Let us take another example to illustrate the static class for application configuration in C#.

### Example

[](https://www.tpointtech.com/c-sharp-static-class#)[](https://www.tpointtech.com/c-sharp-static-class#)[](https://www.tpointtech.com/c-sharp-static-class#)

1. using System;  
2. public static class AppConfig  
3. {  
4.     public static string AppName = "MyCoolApp";  
5.     public static string Version = "1.0.0";  
6.     public static bool IsDebugMode = true;  
7.     public static void ShowConfig()  
8.     {  
9.         Console.WriteLine("App Name: " + AppName);  
10.         Console.WriteLine("Version: " + Version);  
11.         Console.WriteLine("Debug Mode: " + (IsDebugMode ? "ON" : "OFF"));  
12.     }  
13. }  
14. class Program  
15. {  
16.     static void Main()  
17.     {  
18.         AppConfig.ShowConfig();  
19.         AppConfig.IsDebugMode = false;  
20.         Console.WriteLine("\n-- After Updating Debug Mode --\n");  
21.         AppConfig.ShowConfig();  
22.     }  
23. }  

**Output:**

App Name: MyCoolApp
Version: 1.0.0
Debug Mode: ON

-- After Updating Debug Mode --
App Name: MyCoolApp
Version: 1.0.0
Debug Mode: OFF

**Explanation:**

In this example, we have taken the AppConfig class that is declared as a static class, which means that it cannot be instantiated or inherited, and its members are accessed directly using the class name. It can store the global configuration values, such as AppName, Version, and IsDebugMode. After that, the ShowConfig() method is used to display these values, and changes made to the static fields are reflected during the program.

## Difference between Static Class and Non-Static Class

There are several differences between a static class and a Non-static class in C#. Some main differences are as follows:

|Static Class|Non-Static Class|
|---|---|
|The static keyword declares a static class.|The static keyword does not declare a non-static class.|
|The members of a static class can be accessed directly by its class name.|The members of a non-static class are not accessed directly by its class name.|
|A static class cannot be inherited from another class.|A non-static class can be inherited from another class.|
|A static class has no instance constructor.|A non-static class has an instance constructor.|
|A static class always holds static members.|A non-static class can hold both static and non-static methods.|

## Advantages of Static Class

Several advantages of Static Class in C# are as follows:

- **Global Accessibility:** We can access the static classes directly using the class name, which can help to make them effective and reliable during the program without creating objects of the classes.
- **One-Time Initialization:** If we initialize static fields and data only once, it ensures the reliability across the entire program.
- **Improved Performance:** As static members remain the same in the memory for the entire program, there is no need to create repeated objects or garbage collection overhead, which helps to improve the performance of the program.
- **Thread Safety with CLR Initialization:** The .NET Framework runtime makes sure that static constructors and initializations are controlled in a thread-safe manner.

## Disadvantages of Static Class

Several disadvantages of a Static Class in C# are as follows:

- **No Inheritance:** Static classes cannot be inherited in the program, which can restrict the code flexibility and reusability.
- **Memory Usage:** Static members will stay unchanged in the memory during the program's lifetime, which can help to increase the memory consumption if they hold a large amount of data.
- **Tight Coupling:** The utilization of static classes for a long time can increase the coupling between different code segments, which can make it harder to test or refactor.
- **No Instantiation:** Static classes cannot be instantiated in the program, which means we cannot create any object to store different states of the program.

## Conclusion

In conclusion, a static class in C# is a type of class that can collect methods, properties, or constants without the requirement for object creation. It provides a single or shared definition throughout the application, which is suitable for utility functions, configuration settings, or helper logic. Since it cannot be inherited or instantiated, it can give better control, memory usage, and easy access by using the class name. Static classes can lead to cleaner and more organized code if they are used properly.