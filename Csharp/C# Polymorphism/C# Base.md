In the C# programming language, the base keyword is utilized to access base class members from within the derived class. It helps to invoke the implementation of the parent class when it is overridden or when we need to call the parent constructor during the object creation. A base class keyword can only be used in an instance method, a constructor, or an instance property accessor.

### Syntax:

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-base#)[](https://www.tpointtech.com/c-sharp-base#)[](https://www.tpointtech.com/c-sharp-base#)

1. base.MemberName     
2. :base(parameter_list)   

In this syntax,

- **MemberName:** It is used to access the base class member.
- **:base(parmeter_list):** It is used in the derived class constructor to call the base class constructor.

## C# Base keyword to access the base class field

In [C# programming](https://www.tpointtech.com/c-sharp-tutorial), we can use the base keyword to access the fields of the base class inside the derived class. It can be beneficial if base and derived classes contain the same fields. If the derived class does not define the same field, there is no need to use the base keyword. Base class field can be directly accessed by the derived class.

### C# Base keyword example to access the base class field

Let's see the simple example of a base keyword in C#, which accesses the field of the base class.

### Example

[](https://www.tpointtech.com/c-sharp-base#)[](https://www.tpointtech.com/c-sharp-base#)[](https://www.tpointtech.com/c-sharp-base#)

1. using System;    
2. public class Animal{    
3.     public string color = "white";    
4. }    
5. public class Dog: Animal    
6. {    
7.     string color = "black";    
8.     public void showColor()    
9.     {    
10.         Console.WriteLine(base.color);    
11.         Console.WriteLine(color);    
12.     }    

13. }    
14. public class TestBase    
15. {    
16.     public static void Main()    
17.     {    
18.         Dog d = new Dog();    
19.         d.showColor();    
20.     }    
21. }    

**Output:**

white
black

**Explanation:**

In this example, we demonstrate the field hiding wherein Dog possesses its own color field hiding Animal's color. After that, the base.color is used to reach "white" in Animal, whereas color reaches "black" in Dog.

## C# base keyword to call the base class method

In C#, we can call the base class method using the base keyword. It is useful if base and derived classes define the same cmethod. In other words, if the method is overridden or if the derived class doesn't define the same method, there is no need to use the base keyword. Base class method can be directly called by the derived class method.

### C# base keyword example to call the base class method

Let's see the simple example of a base keyword that calls the method of the base class.

### Example

[](https://www.tpointtech.com/c-sharp-base#)[](https://www.tpointtech.com/c-sharp-base#)[](https://www.tpointtech.com/c-sharp-base#)

1. using System;    
2. public class Animal{    
3.     public virtual void eat(){    
4.         Console.WriteLine("eating...");    
5.     }    
6. }    
7. public class Dog: Animal    
8. {    
9.     public override void eat()    
10.     {    
11.         base.eat();    
12.         Console.WriteLine("eating bread...");    
13.     }    

14. }    
15. public class TestBase    
16. {    
17.     public static void Main()    
18.     {    
19.         Dog d = new Dog();    
20.         d.eat();    
21.     }    
22. }    

**Output:**

eating...
eating bread...

**Explanation:**

In this example, we demonstrate the use of the base keyword to call a base class method from an overridden method in the derived class. Here, the Dog class overrides the eat() method, calling first the base Animal method that prints "eating...", followed by its message "eating bread…".

## C# Base keyword using Constructor Chaining

In the C# programming language, when a class is inherited, the base class [constructor](https://www.tpointtech.com/c-sharp-constructor) is automatically called before the derived class constructor. The base keyword can also be explicitly utilized to call a specific constructor of the base class.

### C# Base keyword example using constructor chaining

Let us take an example to illustrate the base keyword using the constructor chaining in C#.

### Example

[](https://www.tpointtech.com/c-sharp-base#)[](https://www.tpointtech.com/c-sharp-base#)[](https://www.tpointtech.com/c-sharp-base#)

1. using System;    
2. public class Animal{    
3.     public Animal(){    
4.         Console.WriteLine("animal...");    
5.     }    
6. }    
7. public class Dog: Animal    
8. {    
9.     public Dog()    
10.     {    
11.         Console.WriteLine("dog...");    
12.     }    

13. }    
14. public class TestOverriding    
15. {    
16.     public static void Main()    
17.     {    
18.         Dog d = new Dog();              
19.     }    
20. }    

**Output:**

animal...
dog...

**Explanation:**

In this example, we demonstrate the constructor chaining in inheritance where instantiating a Dog object initially invokes the Animal constructor, which prints "animal…", followed by the Dog constructor, which prints "dog…".

## Constructors Chaining with Parameters in C#

In C#, when a base class defines a parameterized constructor, we should explicitly call the derived class to ensure proper initialization. It is accomplished by calling the parameterized base class constructor within the derived class constructor using the base keyword, followed by the respective parameters. It ensures the correct initialization of the base class with the required parameters before the execution of the derived class constructor.

### C# Constructors Chaining with Parameters Example

Let us take an example to illustrate the constructor chaining with parameters in C#.

### Example

[](https://www.tpointtech.com/c-sharp-base#)[](https://www.tpointtech.com/c-sharp-base#)[](https://www.tpointtech.com/c-sharp-base#)

1. using System;  
2. public class Animal  
3. {  
4.     public Animal(string name)  
5.     {  
6.         Console.WriteLine($"Animal constructor: {name}");  
7.     }  
8. }  
9. public class Dog : Animal  
10. {  
11.     public Dog(string name) : base(name)    
12.     {  
13.         Console.WriteLine("Dog constructor");  
14.     }  
15. }  
16. public class Program  
17. {  
18.     public static void Main()  
19.     {  
20.         Dog d = new Dog("Buddy");  
21.     }  
22. }  

**Output:**

Animal constructor: Buddy
Dog constructor

**Explanation:**

In this example, we demonstrate the constructor chaining with parameters wherein initializing Dog("Buddy") makes an initial call to Animal's constructor through base(name) to print "Animal constructor: Buddy", followed by executing the Dog constructor to print "Dog constructor".

## Difference Between base and this keyword in C#

There are several differences between the base and [this keyword](https://www.tpointtech.com/c-sharp-this) in C#. Some main differences are as follows:

### This keyword

- The term "this" refers to the current instance of the class where the code is being executed.
- It allows access to members (fields, properties, and methods) of the immediate class, including any overridden or hidden members from a base class.
- When a method is called using this.Method(), it invokes the most derived override of that method.

### Base Keyword

- The base keyword is a reference to the immediate base class of the current class.
- It refers to members as declared in the base class, overriding any overrides or hiding in the immediate class.
- When calling a method with base.Method(), it invokes the parent class version even if it is overridden in the derived class.

### C# Example using base and this keyword

Let us take an example to illustrate the base and this keyword in C#.

### Example

[](https://www.tpointtech.com/c-sharp-base#)[](https://www.tpointtech.com/c-sharp-base#)[](https://www.tpointtech.com/c-sharp-base#)

1. using System;  
2. public class Shape  
3. {  
4.     public virtual double Area()  
5.     {  
6.         Console.WriteLine("Shape Area: 0");  
7.         return 0;  
8.     }  

9.     public void PrintType()  
10.     {  
11.         Console.WriteLine("This is a Shape");  
12.     }  
13. }  
14. public class Rectangle : Shape  
15. {  
16.     private double width;  
17.     private double height;  
18.     public Rectangle(double w, double h)  
19.     {  
20.         width = w;  
21.         height = h;  
22.     }  
23.     public override double Area()  
24.     {  
25.         base.Area();   
26.         double rectArea = width * height;  
27.         Console.WriteLine($"Rectangle Area (overridden): {rectArea}");  
28.         return rectArea;  
29.     }  
30.     public new void PrintType()  
31.     {  
32.         Console.WriteLine("This is a Rectangle");  
33.     }  
34.     public void ShowInfo()  
35.     {  
36.         Area();              
37.         base.Area();        
38.         base.PrintType();    
39.         this.PrintType();    
40.     }  
41. }  
42. class Program  
43. {  
44.     static void Main()  
45.     {  
46.         Rectangle rect = new Rectangle(5, 4);  
47.         rect.ShowInfo();  
48.     }  
49. }  

**Output:**

Shape Area: 0
Rectangle Area (overridden): 20
Shape Area: 0
This is a Shape
This is a Rectangle

**Explanation:**

In this example, we have taken a Rectangle class that inherits from Shape and overrides the Area() method while hiding the PrintType() method using new. Inside the ShowInfo() method, both base and this are utilized to demonstrate how the base class methods (base.Area(), base.PrintType()) and the derived class methods (this.PrintType(), overridden Area()) can be accessed separately.

## Conclusion

In conclusion, the base keyword is an object-oriented programming requirement of C# that enables a derived class to talk to its immediate base class. The "base" keyword is utilized to invoke base class constructors, access base class members and properties, and eliminate problems concerning derived members that can hide base class members. Its usage in the correct context enables cleaner inheritance hierarchies, reuse of code, and reduced confusion in member accesses in complex class hierarchies.