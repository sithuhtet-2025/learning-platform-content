The C# sealed keyword applies restrictions on the class and method. If we create a sealed class, it cannot be inherited. If we create a sealed method, it cannot be overridden. It is commonly utilized to prevent unwanted extension of classes and to ensure that certain methods are not modified in the derived classes.

#### Note: Structs are implicitly sealed, therefore they can't be inherited.

## C# Sealed class

In the C# programming language, a sealed class is a class that cannot be inherited from by any other class. When we make a sealed class with the sealed keyword, we can effectively lock the class, and no one can inherit new classes from it.

The sealed class is helpful when we know that no other class will ever need to change the behavior of the sealed class, or if we need to optimize performance by eliminating the overhead of runtime checking for inheritance.

### Syntax:

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-sealed#)[](https://www.tpointtech.com/c-sharp-sealed#)[](https://www.tpointtech.com/c-sharp-sealed#)

1. sealed class ClassName  
2. {  
3.     // data members  
4.     // methods  
5. }  

In this syntax,

- **ClassName:** It represents the name of the class.

### C# Sealed Class Example without using sealed class

Let us take an example to illustrate the sealed class without using sealed in C#.

### Example

[](https://www.tpointtech.com/c-sharp-sealed#)[](https://www.tpointtech.com/c-sharp-sealed#)[](https://www.tpointtech.com/c-sharp-sealed#)

1. using System;    
2. sealed public class Animal{    
3.     public void eat() { Console.WriteLine("eating..."); }    
4. }    
5. public class Dog: Animal    
6. {    
7.     public void bark() { Console.WriteLine("barking..."); }    
8. }    
9. public class TestSealed    
10. {    
11.     public static void Main()    
12.     {    
13.         Dog d = new Dog();    
14.         d.eat();    
15.         d.bark();      
16.     }    
17. }    

**Output:**

Compile Time Error: 'Dog': cannot derive from sealed type 'Animal'

**Explanation:**

In this example, we will attempt to declare a sealed class Animal with a method eat, but since sealed classes can't be inherited, Dog: Animal will result in a compiler error. Without the sealed keyword, it would allow Dog to inherit eat() as well as its bark() method, called by Main.

### C# Sealed Example using Sealed Class

Let us take an example to illustrate the sealed class in C#.

### Example

[](https://www.tpointtech.com/c-sharp-sealed#)[](https://www.tpointtech.com/c-sharp-sealed#)[](https://www.tpointtech.com/c-sharp-sealed#)

1. using System;  
2. public class Vehicle  
3. {  
4.     public virtual void Start()  
5.     {  
6.         Console.WriteLine("Vehicle started.");  
7.     }  
8. }  
9. public sealed class Car : Vehicle  
10. {  
11.     public override void Start()  
12.     {  
13.         Console.WriteLine("Car started with a key.");  
14.     }  
15. }  
16. class Program  
17. {  
18.     static void Main()  
19.     {  
20.         Car myCar = new Car();  
21.         myCar.Start();  
22.     }  
23. }  

**Output:**

Car started with a key.

**Explanation:**

In this example, we declare a base class, Vehicle, with a virtual Start method and a sealed class, Car, that overrides the virtual method. In Main , a Car object invokes its Start method, outputting "Car started with a key." As the Car is sealed, no class may inherit from it.

## When to Use Sealed Classes?

We can use sealed classes in different contexts. Some of them are as follows:

- It is used to avoid unwanted inheritance.
- It is used to protect delicate behavior against being overridden.
- It is used to maximize performance in some cases.

## C# Sealed method

In the C# programming language, a sealed method cannot be overridden in derived classes. It is used in conjunction with the override keyword. A method can only be sealed if it overrides a base class method. The sealed keyword cannot be applied to a method unless it has been overridden.

**Syntax:**

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-sealed#)[](https://www.tpointtech.com/c-sharp-sealed#)[](https://www.tpointtech.com/c-sharp-sealed#)

1. sealed override access_modifier return_type MethodName(parameters)  
2. {  
3.     // method body  
4. }  

The sealed method in C# cannot be overridden further. It must be used with the override keyword in a method.

### C# Sealed Example using the sealed Keyword with Methods to Prevent Overriding

Let's see an example to illustrate the sealed method in C#.

### Example

[](https://www.tpointtech.com/c-sharp-sealed#)[](https://www.tpointtech.com/c-sharp-sealed#)[](https://www.tpointtech.com/c-sharp-sealed#)

1. using System;    
2. public class Animal{    
3.     public virtual void eat()   
4. {   
5. Console.WriteLine("eating...");   
6. }    
7.     public virtual void run()   
8. {   
9. Console.WriteLine("running...");   
10. }    

11. }    
12. public class Dog: Animal    
13. {    
14.     public override void eat()   
15. {   
16. Console.WriteLine("eating bread...");   
17. }    
18.     public sealed override void run() {     
19.     Console.WriteLine("running very fast...");     
20.     }    
21. }    
22. public class BabyDog : Dog    
23. {    
24.     public override void eat()   
25. {   
26. Console.WriteLine("eating biscuits...");   
27. }    
28.     public override void run()   
29. {  
30.  Console.WriteLine("running slowly...");   
31. }    
32. }    
33. public class TestSealed    
34. {    
35.     public static void Main()    
36.     {    
37.         BabyDog d = new BabyDog();    
38.         d.eat();    
39.         d.run();    
40.     }    
41. }    

**Output:**

Compile Time Error: 'BabyDog.run()': cannot override inherited member 'Dog.run()' because it is sealed

**Explanation:**

In this example, we will not compile because Dog has sealed the run() method and BabyDog cannot override it. If the run() override in BabyDog is uncommented out, it would inherit Dog's run() method and output "eating biscuits..." followed by "running very fast...".

#### Note: Local variables can't be sealed.

### Invalid Use of sealed with Local Variables in C#

Let us take an example to illustrate the invalid use of sealed with local variables in C#.

### Example

[](https://www.tpointtech.com/c-sharp-sealed#)[](https://www.tpointtech.com/c-sharp-sealed#)[](https://www.tpointtech.com/c-sharp-sealed#)

1. using System;    
2. public class TestSealed    
3. {    
4.     public static void Main()    
5.     {    
6.         sealed int x = 10;    
7.         x++;    
8.         Console.WriteLine(x);    
9.     }    
10. }    

**Output:**

Compile Time Error: Invalid expression term 'sealed'

**Explanation:**

In this example, we will not compile since C# does not support using the sealed keyword with local variables such as int x. sealed is only applicable to classes or method overrides, but not to primitive variables.

### C# Sealed example to Sealing an Overridden Method to Restrict Further Overriding

Let us take an example to illustrate how to seal an overridden method to restrict further overriding in C#.

### Example

[](https://www.tpointtech.com/c-sharp-sealed#)[](https://www.tpointtech.com/c-sharp-sealed#)[](https://www.tpointtech.com/c-sharp-sealed#)

1. using System;  
2. public class Employee  
3. {  
4.     public virtual void Work()  
5.     {  
6.         Console.WriteLine("Employee is working");  
7.     }  
8. }  
9. public class Manager : Employee  
10. {  
11.     public sealed override void Work()  
12.     {  
13.         Console.WriteLine("Manager is managing the team");  
14.     }  
15. }  

16. public class ProjectManager : Manager  
17. {  
18.     public void Plan()  
19.     {  
20.         Console.WriteLine("Project Manager is planning tasks");  
21.     }  
22.     // Cannot override Work() here because it is sealed in Manager  
23. }  

24. class Program  
25. {  
26.     static void Main()  
27.     {  
28.         ProjectManager pm = new ProjectManager();  
29.         pm.Work();   
30.         pm.Plan();   
31.     }  
32. }  

**Output:**

Manager is managing the team
Project Manager is planning tasks

**Explanation:**

In this example, we define an Employee class with a virtual Work method, override it in a sealed Manager class to prevent further modifications, and introduce a Plan method in the ProjectManager class. In the Main() function, a ProjectManager instance invokes Work(from  Manager) and Plan.

## Features of Sealed in C#

There are several features of Sealed in C#. Some of them are as follows:

- Sealed classes cannot be inherited.
- Sealed method cannot be overridden, but it can be declared inside a class that is inheritable.
- All classes are inheritable unless marked as sealed in C#.
- Structures are implicitly sealed, so we cannot inherit from them.
- Sealed helps to enhance the performance because sealed methods are faster due to compiler optimizations.

## Conclusion

In conclusion, C# sealed is used to limit inheritance by disallowing other classes from inheriting from a sealed class or preventing further overriding of a sealed method. It helps to preserve the integrity of a class's design, which prevents its implementation from being modified. It can also provide performance benefits because the runtime knows that the type cannot be extended.

A sealed class is final and cannot be abstracted, whereas a sealed method is a method that is overridden in a derived class but cannot be overridden again in subsequent subclasses.