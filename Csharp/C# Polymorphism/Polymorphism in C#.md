The word polymorphism is the combination of two words, "poly" + "morphism". The word poly means **many,** and morphism means **form.** It means that one task can be performed in many forms. It is a Greek word. It provides a way to use the same function name with different purposes. In OOPs, it uses the three main concepts: inheritance, encapsulation, and polymorphism. It improves the flexibility, code reusability, and maintainability of code.

### Simple Example of Polymorphism

Let us take an illustrative example to define polymorphism in [C#](https://www.tpointtech.com/c-sharp-tutorial).

### Example

[](https://www.tpointtech.com/c-sharp-polymorphism#)[](https://www.tpointtech.com/c-sharp-polymorphism#)[](https://www.tpointtech.com/c-sharp-polymorphism#)

1. using System;  
2. class Example  
3. {  
4.     static void Main()  
5.     {  
6.         int num1 = 50;   // integer variable  
7.         int num2 = 25;   // integer variable  
8.         string firstWord = "over";   // string variable  
9.         string secondWord = "loading";   
10.         Console.WriteLine("Sum of num1 and num2 = " + (num1 + num2));  
11.         Console.WriteLine("Concatenated string = " + (firstWord + secondWord));  
12.     }  
13. }  

**Output:**

Sum of num1 and num2 = 75
Concatenated string = overloading

**Explanation:**

In this example, we have taken two integer and string data types. After that, we have taken the (+) operators. The first (+) operator is used to add two numbers, and the second (+) operator is used to concatenate two string operands. Finally, we use the Console.WriteLine() function to print the output.

## Types of Polymorphism

There are mainly two types of polymorphism in C#.

![Polymorphism in C#](https://images.tpointtech.com/csharp/images/c-sharp-polymorphism.png)

Here, we will discuss these polymorphisms one by one.

## Compile-time Polymorphism

In the C# programming language, compile-time polymorphism is also known as early binding and static polymorphism. It enables us to define multiple methods that contain the same name but different parameters.

![Polymorphism in C#](https://images.tpointtech.com/csharp/images/c-sharp-polymorphism2.png)

It is achieved by using the method overloading and operator overloading in C#.

#### Note: When a method call decides the actual function during the compilation process of a program, it is known as compile-time polymorphism.

### a) Function Overloading

In C#, function overloading is an important concept of object-oriented programming. It provides a way for a class to have the same name but with several parameters. Function overloading can be implemented by changing the number of arguments or changing the arguments.

**C# Compile-Time Polymorphism Example using Function Overloading**

Let us take a simple example to illustrate compile-time polymorphism using function overloading in C#.

### Example

[](https://www.tpointtech.com/c-sharp-polymorphism#)[](https://www.tpointtech.com/c-sharp-polymorphism#)[](https://www.tpointtech.com/c-sharp-polymorphism#)

1. using System;  

2. class Number  
3. {  
4.     // declaration of method with two int parameters  
5.     public int Add(int a, int b)  
6.     {  
7.         return a + b;  
8.     }  

9.     // method with three int parameters  
10.     public int Add(int a, int b, int c)  
11.     {  
12.         return a + b + c;  
13.     }  

14.     // method with parameters type double  
15.     public double Add(double a, double b)  
16.     {  
17.         return a + b;  
18.     }  
19. }  

20. class Program  
21. {  
22.     static void Main()  
23.     {  
24.         Number num = new Number();  
25.         Console.WriteLine("The Sum of the two numbers is " + num.Add(100, 200));  
26.         Console.WriteLine("The Sum of the three numbers is " + num.Add(100, 200, 300));  
27.         Console.WriteLine("The Sum of two floating numbers is " + num.Add(20.5, 30.7));  
28.     }  
29. }  

**Output:**

The Sum of the two numbers is 300
The Sum of the three numbers is 600
The Sum of two floating numbers is 51.2

**Explanation:**

In this example, we have taken a class named Number that contains three methods with the same name but different parameters. After that, we create an instance of the class (Number) in the main method and call the method (Addition) three times. Finally, we use the Console.WriteLine() function to print the output.

### b) Operator Overloading

In C#, operator overloading allows the same operator to perform different operations. It is a user-defined data type. It can be achieved by using several operators such as +, -, *, = =, <<, >>, etc. If we want to use operator overloading, at least one operand should be a user-defined data type in C#.

**C# Compile-Time Polymorphism Example using Operator Overloading**

Let us take an example to illustrate the compile-time polymorphism using operator overloading in C#.

### Example

[](https://www.tpointtech.com/c-sharp-polymorphism#)[](https://www.tpointtech.com/c-sharp-polymorphism#)[](https://www.tpointtech.com/c-sharp-polymorphism#)

1. using System;  
2. class Comp  
3. {  
4.     public int real, imag;  
5.     public Comp(int r, int i)  
6.     {  
7.         real = r;  
8.         imag = i;  
9.     }  
10.     // Applying the + operator  
11.     public static Comp operator + (Comp a1, Comp a2)  
12.     {  
13.         return new Comp(a1.real + a2.real, a1.imag + a2.imag);  
14.     }  
15.     public void Show()  
16.     {  
17.         Console.WriteLine($"{real} + {imag}i");  
18.     }  
19. }  
20. class Tpoint  
21. {  
22.     static void Main()  
23.     {  
24.         Comp a1 = new Comp(2, 3);  
25.         Comp a2 = new Comp(4, 5);  
26.         Comp sum = a1 + a2;   
27.         sum.Show();   
28.     }  
29. }  

**Output:**

6 + 8i

**Explanation:**

In this example, we have taken a class named Comp that contains two public integer variables (real and imag) and three methods. We use a constructor to set the values of real or imag, and then use the overloaded + operator method to add two Comp objects. After that, a Show() method is used to show the complex number. In the main method, we create two complex numbers and add them using the overloaded + operator, and display the result.

## Runtime Polymorphism

In the C# programming language, the runtime polymorphism is also known as the dynamic polymorphism or late binding. It occurs when the method that gets executed is determined during the run time of the program. It is implemented using method overriding, where a derived class provides its own implementation of a virtual method defined in the base class.

### a) Function Overriding

In C#, function overriding is a key feature of object-oriented programming that enables a derived class to redefine a method that is already defined in its base class. The base method should use the virtual keyword, and the derived classes should use the override keyword to provide their implementation. It enables a child class to give a specific behaviour for a method, which is already defined in the parent class.

**C# Runtime Polymorphism Example using Function Overriding**

Let us take an example to illustrate the run-time polymorphism using function overriding in C#.

### Example

[](https://www.tpointtech.com/c-sharp-polymorphism#)[](https://www.tpointtech.com/c-sharp-polymorphism#)[](https://www.tpointtech.com/c-sharp-polymorphism#)

1. using System;     
2. class Animal  
3. {     
4.     public virtual void Speak()  
5.     {     
6.         Console.WriteLine("The Animal speaks");  
7.     }     
8. }  
9. class Dog : Animal  
10. {  
11.     public override void Speak()  
12.     {  
13.         Console.WriteLine("The dog barks");  
14.     }  
15. }  
16. class Tpoint  
17. {  
18.     static void Main()  
19.     {  
20.         Animal animal = new Dog();  // Base class reference, derived class object  
21.         animal.Speak();  // Calls Dog's Speak() at runtime  
22.     }  
23. }  

**Output:**

The dog barks

**Explanation:**

In this example, we have taken a base class Animal that contains the virtual function Speak(). After that, we create a derived class Dog that inherits from the base class and accesses the features of the base class. In the main method, we create an instance of the derived class (Dog) and call the Speak() method to print the output.

### b) Virtual Method

In the C# programming language, a virtual method is defined inside the base class. The virtual keyword is used to create a virtual method. It is used as a base class member to specify that the base class may be overridden in a derived class. The override keyword is applied in the derived class to give a new implementation of a base class member, which was declared as virtual.

**Virtual Method Example in C#**

Let us take a simple example to define method overriding using the virtual method in C#.

### Example

[](https://www.tpointtech.com/c-sharp-polymorphism#)[](https://www.tpointtech.com/c-sharp-polymorphism#)[](https://www.tpointtech.com/c-sharp-polymorphism#)

1. using System;  
2. class Shape  
3. {  
4.     public virtual void Draw()  
5.     {  
6.         Console.WriteLine("This is the shape Drawing");  
7.     }  
8. }  
9. class Circle : Shape  
10. {  
11.     public override void Draw()  
12.     {  
13.         Console.WriteLine("The is the shape Circle");  
14.     }  
15. }  
16. class Square : Shape  
17. {  
18.     public override void Draw()  
19.     {  
20.         Console.WriteLine("This is the shape square");  
21.     }  
22. }  
23. class Program  
24. {  
25.     static void Main()  
26.     {  
27.         Shape s;  

28.         s = new Circle();  
29.         s.Draw();  

30.         s = new Square();  
31.         s.Draw();  
32.     }  
33. }  

**Output:**

This is the shape Circle
This is the shape square

**Explanation:**

In this example, we have taken a class named Shape that contains the virtual method Draw(). After that, we create a derived class Square that inherits from the base class and accesses the features of the base class. In the main method, we create an instance of the class Shape and call the Draw() method to print the output.

## Use Cases of Polymorphism in C#

There are several use cases of polymorphism in C#. Some of them are as follows:

- It allows us to write generic code in the base class and modify it in the derived classes.
- It is based on the object type that helps us to choose at runtime which method to execute.
- It helps to reduce code duplicity by defining common behavior in a base class and modifying it.
- It allows us to implement multiple classes in the same interface and provide their own functionality.

## Difference between Compile Time and Run-time Polymorphism

There are several differences between compile-time and run-time polymorphism in C#. Some main differences are as follows:

|Compile Time Polymorphism|Run Time Polymorphism|
|---|---|
|It is also known as Early binding.|It is also known as Late binding.|
|The method call is decided during the compilation of the code.|The method call is decided during program execution.|
|It is achieved via method overloading or operator overloading.|It is implemented through method overriding.|
|In Compile-time polymorphism, inheritance is not involved.|Inheritance is involved in run-time polymorphism.|
|It is less flexible.|It is more flexible.|

## Conclusion

In conclusion, C# polymorphism is the key factor for any developer to create a software application. It is one of the main pillars of C# OOP. It provides a way to use the same function name with different purposes. It helps to improve code reusability, flexibility, and maintainability.