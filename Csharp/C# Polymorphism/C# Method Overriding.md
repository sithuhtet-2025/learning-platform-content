
In the C# programming language, method overriding is a process by which a derived class declares a method with the same name, return type, and parameters as a method that is already declared in its base class. It is utilized to obtain runtime polymorphism. It enables us to give a specific implementation of the method that is already given by its base class. It means that the base class defines a general behaviour, but the derived class can extend or completely redefine that behaviour according to the requirement.

### C# Method Overriding Example

Let us take an instance to demonstrate method overriding in C#.

### Example

[](https://www.tpointtech.com/c-sharp-method-overriding#)[](https://www.tpointtech.com/c-sharp-method-overriding#)[](https://www.tpointtech.com/c-sharp-method-overriding#)

1. using System;  

2. class Car  
3. {  
4.     public virtual void Drive()  //using base class  
5.     {  
6.         Console.WriteLine("Car is running");  
7.     }  
8. }  

9. class SpCar : Car  
10. {  
11.     public override void Drive()  //Overriding Drive() method  
12.     {  
13.         Console.WriteLine("Sports Car runs at high speed");  
14.     }  
15. }  

16. class EcCar : Car  
17. {  
18.     public override void Drive() // Overriding Drive() method  
19.     {  
20.         Console.WriteLine("Electric Car runs silently");  
21.     }  
22. }  

23. class MethOverride  
24. {  
25.     static void Main()  
26.     {  
27.         Car myCar;  

28.         myCar = new SpCar();  
29.         myCar.Drive();   // Calls SportsCar version  

30.         myCar = new EcCar();  
31.         myCar.Drive();   // Calls ElectricCar version  
32.     }  
33. }   

**Output:**

Sports Car runs at high speed
Electric Car runs silently

**Explanation:**

In this example, we have taken a base class Car that defines a virtual method Drive(), which is overridden in the derived classes, such as SpCar and EcCar, by using the override keyword. During program execution, the method call is resolved based on the actual object type rather than the reference type. As a result, the corresponding overridden method is invoked, and the specific output is printed.

## Keywords for Method Overriding

If we want to perform method overriding in C#, we have to use the virtual keyword with the base class method and the override keyword with the derived class method. In C#, we can use 3 types of keywords for Method Overriding:

### 1) Virtual keyword

In the [C# programming language](https://www.tpointtech.com/c-sharp-tutorial), a virtual keyword or modifier is mainly used in a base class method. It is applied to modify a base class method to override that specific base class method in the derived class.

**Method Overriding Example in C# using Virtual Keyword**

Let us take an example to illustrate the method overriding using the Virtual Keyword in C#.

### Example

[](https://www.tpointtech.com/c-sharp-method-overriding#)[](https://www.tpointtech.com/c-sharp-method-overriding#)[](https://www.tpointtech.com/c-sharp-method-overriding#)

1. using System;  
2. class Shape  
3. {  
4.     public virtual double Area()  
5.     {  
6.         return 0;  
7.     }  
8. }  
9. class Program  
10. {  
11.     static void Main()  
12.     {  
13.         Shape shape = new Shape();  
14.         Console.WriteLine("Area: " + shape.Area());    
15.     }  
16. }  

**Output:**

Area: 0

**Explanation:**

In this example, we create a Shape class that includes a virtual function Area() returning 0, which indicates that by default, a shape does not have an area. In the main() function, a Shape object is instantiated and the Area() method on it is invoked, which shows the result as Area: 0. Finally, the virtual keyword enables derived classes to override this function in the future.

### 2) Override Keyword

In C# programming, the override keyword is a modifier that is mainly utilized in a derived class method. It provides a specific implementation of a method that is already declared as virtual and abstract in the base class. It enables the derived class to extend or modify the behavior in the base class. During runtime, it ensures that the suitable method is executed based on the actual object type rather than the reference type.

**C# Method Overriding Example using the Override Keyword**

Let us take an example to illustrate the method overriding using the override keyword in C#.

### Example

[](https://www.tpointtech.com/c-sharp-method-overriding#)[](https://www.tpointtech.com/c-sharp-method-overriding#)[](https://www.tpointtech.com/c-sharp-method-overriding#)

1. using System;  
2. class Shape  
3. {  
4.     public virtual double Area()  
5.     {  
6.         return 0;  
7.     }  
8. }  
9. class Rectangle : Shape  
10. {  
11.     public double Width { get; set; }  
12.     public double Height { get; set; }  
13.     public override double Area()  
14.     {  
15.         return Width * Height;  
16.     }  
17. }  
18. class Program  
19. {  
20.     static void Main()  
21.     {  
22.         Rectangle rect = new Rectangle { Width = 5, Height = 3 };  
23.         Console.WriteLine("Rectangle Area: " + rect.Area());    
24.     }  
25. }  

**Output:**

Rectangle Area: 15

**Explanation:**

In this example, we have taken a Shape class with a virtual Area() function that returns 0. After that, the rectangle class inherits from the Shape class and overrides the Area() function to return Width * Height. In the main() function, a rectangle of width 5 and height 3 is instantiated, and calling Area() returns 15.

### 3) Base Keyword

In C#, the base keyword is mainly utilized to access members of the base class in a derived class. Using the base keyword, we can call the methods or functions of the base class from the derived class. It is also utilized to invoke the [constructor](https://www.tpointtech.com/c-sharp-constructor) of the base class internally during [inheritance](https://www.tpointtech.com/c-sharp-inheritance).

**Method Overriding Example in C# using the Base Keyword**

Let us take an example to illustrate the method overriding using the base keyword in C#.

### Example

[](https://www.tpointtech.com/c-sharp-method-overriding#)[](https://www.tpointtech.com/c-sharp-method-overriding#)[](https://www.tpointtech.com/c-sharp-method-overriding#)

1. using System;  
2. class Employee  
3. {  
4.     public virtual void Work()  
5.     {  
6.         Console.WriteLine("Employee is working.");  
7.     }  
8. }  
9. class Manager : Employee  
10. {  
11.     public override void Work()  
12.     {  
13.         base.Work();  
14.         Console.WriteLine("Manager is preparing reports.");  
15.     }  
16. }  
17. class Program  
18. {  
19.     static void Main()  
20.     {  
21.         Manager manager = new Manager();  
22.         manager.Work();  
23.     }  
24. }  

**Output:**

Employee is working.
Manager is preparing reports.

**Explanation:**

In this example, we declare an Employee class with a virtual method Work() that will print a default work message. After that, the Manager class overrides the Work() method to call the base Work(), and then appends its message to the report preparation. In the Main() function, we initiate a Manager object and call the Work() function that will print both messages.

**Method Overriding Example in C# using Devices**

Let us take an example to illustrate the method overriding using several devices in C#.

### Example

[](https://www.tpointtech.com/c-sharp-method-overriding#)[](https://www.tpointtech.com/c-sharp-method-overriding#)[](https://www.tpointtech.com/c-sharp-method-overriding#)

1. using System;  
2. class Device  
3. {  
4.     public virtual void Describe()  
5.     {  
6.         Console.WriteLine("This is a generic device.");  
7.     }  
8. }  
9. class Smartphone : Device  
10. {  
11.     public override void Describe()  
12.     {  
13.         Console.WriteLine("This is a smartphone with a touchscreen.");  
14.     }  
15. }  
16. class Laptop : Device  
17. {  
18.     public override void Describe()  
19.     {  
20.         Console.WriteLine("This is a laptop with a physical keyboard.");  
21.     }  
22. }  
23. class Program  
24. {  
25.     static void Main()  
26.     {  
27.         Device myDevice = new Device();  
28.         myDevice.Describe();   
29.         Device devicePhone = new Smartphone();  
30.         devicePhone.Describe();   
31.         Device deviceLaptop = new Laptop();  
32.         deviceLaptop.Describe();   
33.     }  
34. }  

**Output:**

This is a generic device.
This is a smartphone with a touchscreen.
This is a laptop with a physical keyboard.

**Explanation:**

In this example, we have taken a Device class with a virtual Describe() method. After that, the smartphone and Laptop override it using the override keyword. At runtime, the actual object type (such as Device, Smartphone, or Laptop) determines which version of the Describe() method is executed.

## Rules for Method Overriding

There are several rules for method overriding in C#. Some of them are as follows:

- In C# method overriding, a method, property, indexer, or event may be overridden in the derived class.
- Static methods cannot be overridden in C#.
- We need to utilize the virtual keyword in the methods of the base class so that the methods may be overridden.
- We have to utilize the override keyword in the subclass to override the parent class method.
- The base keyword enables the child class to call the parent version of the method.
- The overridden method should have the same name, return type, and parameters as they are defined in the base class.

## Conclusion

In conclusion, method overriding enables us to extend or modify the inherited method, which promotes runtime polymorphism and dynamic behavior. We can ensure that the correct method is executed based on the actual object type using Virtual and Abstract. It helps to make code flexible, extensible, and easy to use because the base class method can be customized in the derived classes without modifying the actual implementation.