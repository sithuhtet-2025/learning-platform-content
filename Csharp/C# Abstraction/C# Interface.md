In the C# programming language, an interface is a blueprint for a class or struct. An interface keyword is used to define the interface. It is similar to an abstract class because all the methods that are declared inside the interface are abstract methods. It contains several method groups, properties, events, and indexers.

Interfaces cannot have a method body and cannot be directly instantiated. These are used to achieve abstraction and multiple inheritance that can't be achieved by a class. Its implementation must be provided by a class or a struct. The class or struct that implements the interface should provide the implementation of all the methods declared inside the interface.

Interfaces (Since C# 8.0 version) can also include default implementations and static members, which provide more flexibility in design.

### Syntax of the Interface

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-interface#)[](https://www.tpointtech.com/c-sharp-interface#)[](https://www.tpointtech.com/c-sharp-interface#)

1. interface InterfaceName  
2. {  
3.     // Method signature (no body)  
4.     void MethodName();  
5.     // Property signature  
6.     int PropertyName { get; set; }  
7.     // Event  
8.     event EventHandler EventName;  
9. }  

In this syntax,

- **interface InterfaceName:** It represents the name of the interface.
- **void MethodName():** It represents the name of the method without implementation.
- **PropertyName:** It represents the name of the property with get and set accessors.
- **EventHandler, EventName:** It is used to declare an event inside the interface.

### C# Interface Example

Let us take an example to illustrate the interface in C#.

### Example

[](https://www.tpointtech.com/c-sharp-interface#)[](https://www.tpointtech.com/c-sharp-interface#)[](https://www.tpointtech.com/c-sharp-interface#)

1. using System;    
2. public interface Drawable    
3. {    
4.     void draw();    
5. }    
6. public class Rectangle : Drawable    
7. {    
8.     public void draw()    
9.     {    
10.         Console.WriteLine("drawing rectangle...");    
11.     }    
12. }    
13. public class Circle : Drawable    
14. {    
15.     public void draw()    
16.     {    
17.         Console.WriteLine("drawing circle...");    
18.     }    
19. }    
20. public class TestInterface    
21. {    
22.     public static void Main()    
23.     {    
24.         Drawable d;    
25.         d = new Rectangle();    
26.         d.draw();    
27.         d = new Circle();    
28.         d.draw();    
29.     }    
30. }    

**Output:**

drawing rectangle...
drawing circle...

**Explanation:**

In this example, we have taken a Drawable interface that defines a contract with the draw() method. After that, we take the Rectangle and Circle classes that implement this interface by providing their own versions of the draw() method. In the main() function, a reference of type Drawable is used to invoke the draw() method on both objects, which demonstrates the polymorphism where the same type of interface invokes different implementations.

#### Note: Interface methods are public and abstract by default. You cannot explicitly use public and abstract keywords for an interface method.

**For Example:**

[](https://www.tpointtech.com/c-sharp-interface#)[](https://www.tpointtech.com/c-sharp-interface#)[](https://www.tpointtech.com/c-sharp-interface#)

1. using System;    
2. public interface Drawable    
3. {    
4.     public abstract void draw();//Compile Time Error    
5. }    

## Default Interface Methods

In C# 8.0 and later versions, default interface methods enable us to provide a method implementation directly inside an interface. It helps to include new members in interfaces without breaking the existing classes and structs that implement them.

### C# Default Interface Method Example

Let us take an example to illustrate the default interface method in C#.

### Example

[](https://www.tpointtech.com/c-sharp-interface#)[](https://www.tpointtech.com/c-sharp-interface#)[](https://www.tpointtech.com/c-sharp-interface#)

1. using System;  
2. interface Logger  
3. {  
4.     void Log(string message);   
5.     void LogInfo(string message)  
6.     {  
7.         Console.WriteLine($"INFO: {message}");  
8.     }  
9. }  
10. class ConsoleLogger : Logger  
11. {  
12.     public void Log(string message)  
13.     {  
14.         Console.WriteLine($"LOG: {message}");  
15.     }  
16. }  
17. class Program  
18. {  
19.     static void Main()  
20.     {  
21.         Logger logger = new ConsoleLogger();  
22.         logger.Log("Application started");  
23.         logger.LogInfo("Running smoothly");  
24.     }  
25. }  

**Output:**

LOG: Application started
INFO: Running smoothly

**Explanation:**

In this example, we declare an interface Logger with an abstract method Log and a default method LogInfo that prints an info message. After that, we take a ConsoleLogger class that implements the Log() method, while LogInfo() uses the default implementation that is provided by the interface. In the main() function, when a ConsoleLogger object is called through the Logger reference, both methods execute.

## Interface Inheritance

In C#, interface inheritance is a type of interface that can inherit from a single or multiple interfaces, which merge their contracts into one interface. A class that implements the child interface has to implement all members from all inherited interfaces.

### C# Interface Inheritance Example

Let us take an example to illustrate the interface inheritance in C#.

### Example

[](https://www.tpointtech.com/c-sharp-interface#)[](https://www.tpointtech.com/c-sharp-interface#)[](https://www.tpointtech.com/c-sharp-interface#)

1. using System;  
2. interface Movable  
3. {  
4.     void Move();  
5. }  
6. interface Stoppable  
7. {  
8.     void Stop();  
9. }  
10. interface Vehicle : Movable, Stoppable  
11. {  
12.     void Start();  
13. }  
14. class Car : Vehicle  
15. {  
16.     public void Move()  
17.     {  
18.         Console.WriteLine("Car is moving.");  
19.     }  
20.     public void Stop()  
21.     {  
22.         Console.WriteLine("Car has stopped.");  
23.     }  
24.     public void Start()  
25.     {  
26.         Console.WriteLine("Car has started.");  
27.     }  
28. }  
29. class Tpoint  
30. {  
31.     static void Main()  
32.     {  
33.         Vehicle myCar = new Car();  
34.         myCar.Start();  
35.         myCar.Move();  
36.         myCar.Stop();  
37.     }  
38. }  

**Output:**

Car has started.
Car is moving.
Car has stopped.

**Explanation:**

In this example, we demonstrate the interface inheritance where the Vehicle class inherits from Movable and Stoppable. After that, the Car class implements all the necessary methods. In the main() function, a Vehicle reference calls Start, Move, and Stop, which illustrates multiple interface implementations and polymorphism.

## Explicit Interface Implementation in C#

In the C# programming language, explicit interface implementation is a technique that is used when a class implements two or more interfaces that contain methods with the same name. In this case, the class should explicitly implement the interfaces to fix the ambiguity.

### C# Explicit Interface Example

Let us take an example to illustrate the explicit interface in C# programming.

### Example

[](https://www.tpointtech.com/c-sharp-interface#)[](https://www.tpointtech.com/c-sharp-interface#)[](https://www.tpointtech.com/c-sharp-interface#)

1. using System;  

2. interface Employee  
3. {  
4.     void ShowDetails();  
5. }  

6. interface Project  
7. {  
8.     void ShowDetails();  
9. }  

10. class Employee1 : Employee, Project  
11. {  
12.     // Explicit implementation for Employee  
13.     void Employee.ShowDetails()  
14.     {  
15.         Console.WriteLine("Employee Details: Name- Michael, ID- 101");  
16.     }  

17.     // Explicit implementation for Project  
18.     void Project.ShowDetails()  
19.     {  
20.         Console.WriteLine("Project Details: Project- C# Interfaces, Status- Completed");  
21.     }  
22. }  

23. class Tpoint  
24. {  
25.     static void Main()  
26.     {  
27.         Employee1 emp1 = new Employee1();  

28.         // Access through Employee interface reference  
29.         Employee emp = emp1;  
30.         emp.ShowDetails();  

31.         // Access through Project interface reference  
32.         Project project = emp1;  
33.         project.ShowDetails();  
34.     }  
35. }  

**Output:**

Employee Details: Name- Michael, ID- 101
Project Details: Project- C# Interfaces, Status- Completed

**Explanation:**

In this example, we have taken two Employee and Project interfaces that define the same method ShowDetails(). In the Employee1 class, each interface method is explicitly implemented, and they can only be accessed through their respective interface references, which avoids ambiguity.

## When and Why Use an Interface in C#?

Interfaces in C# are an essential feature that declare contracts or specifications that classes have to comply with. We can use interfaces in the following situations:

- **Defining a Common Contract:** We can define an interface to establish that contract to ensure that several classes share a common group of methods, properties, events, or indexers.
- **Applying Multiple Inheritance:** C# does not enable multiple inheritance for classes, but enables multiple interface implementation. If we need a class to inherit behavior or structure from multiple sources, we can apply interfaces to achieve multiple inheritance. It also enables us to reuse code across different classes without any issue.
- **Imposing a Specific Form:** If we need to execute a specific form or a specific set of methods and properties for classes in the application or library, interfaces can be used to ensure that classes follow that form.
- **Applying Polymorphism:** Interfaces is an important feature to implement polymorphism in C#. When we have multiple classes implementing the same interface, we can handle objects of these classes alike, and it is simpler to work with different objects in a polymorphic manner.

## Key Features of Interfaces

There are several features of Interfaces in C#. Some of them are as follows:

**1) Contract Definition**

An interface is used to define a contract that the implementation class should fulfill by providing implementations for all its declared members.

**2) Polymorphism**

In C# programming, the interface allows runtime polymorphism. It allows different classes to be preserved as instances of the same type of interface.

**3) Multiple Inheritance**

The C# programming language supports multiple interface inheritance, which enables a class to implement multiple inheritances.

**4) Access Modifiers**

By default, all members of an interface are public and abstract; private members are not allowed.

**5) No Fields**

In C#, an interface cannot contain instance fields, constructors, or destructors. Interfaces only declare signatures for members.

**6) Abstraction**

Interface helps to achieve full abstraction in C#. An interface hides the implementation details by defining only what a class should do, not how it should do it.

## Conclusion

In conclusion, the C# interfaces provide a way to define a contract that classes must follow. Interface supports abstraction, multiple inheritance, and polymorphism, which improve the flexibility, reusability, and maintainability of code. With C# 8.0 and later versions, interfaces can also include default methods, which makes them more powerful for creating scalable and modular applications.