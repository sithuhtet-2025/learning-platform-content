In the C# programming language, the access modifiers are the keywords used to define the visibility, scope, and accessibility of classes, methods, variables, properties, and other members in a program. It is an important feature of object-oriented programming (OOP). It helps to implement the principle of encapsulation and data hiding. These are very helpful for encapsulation by restricting unauthorized or unintended access to internal data and implementation details.

## Type of Access Specifier

In the C# programming language, there are mainly six types of access modifiers. These are as follows:

![C# Access Modifiers](https://images.tpointtech.com/csharp/images/c-sharp-access-modifiers.png)

Here, we will discuss these access modifiers one by one.

### 1) C# Public Access Modifier

In C#, the public access modifier is a more flexible modifier. If a class member is declared as public, it can be accessible anywhere from the code inside the same assembly or even outside the assembly. Public class members are commonly utilized to represent the class interface of the class. It may be accessed through the derived class objects. Unlike other access modifiers, it has no access restrictions.

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-access-modifiers#)[](https://www.tpointtech.com/c-sharp-access-modifiers#)[](https://www.tpointtech.com/c-sharp-access-modifiers#)

1. public class ClassName  
2. {  
3.     public dataType variableName;  
4.     public void MethodName()  
5.     {  
6.         // block of code  
7.     }  
8. }  

In this syntax,

- **ClassName:** It declares the public class, which means that it is accessible from anywhere in the program.
- **variableName:** It declares a public member variable of a specified datatype, which means that it can be accessed from any other class or assembly.
- **MethodName():** It declares a public method named MethodName that can be called from anywhere. The method contains the logic or behavior for the class.

**C# Public Access Modifier Example:**

Let us take an example to illustrate the public access specifiers in C#.

### Example

[](https://www.tpointtech.com/c-sharp-access-modifiers#)[](https://www.tpointtech.com/c-sharp-access-modifiers#)[](https://www.tpointtech.com/c-sharp-access-modifiers#)

1. using System;    
2. namespace AccessSpecifiers    
3. {    
4.     class PublicTest    
5.     {    
6.         public string name = "John";    
7.         public void Msg(string msg)    
8.         {     
9.             Console.WriteLine("Hello " + msg);    
10.         }    
11.     }    
12.     class Tpoint    
13.     {    
14.         static void Main(string[] args)    
15.         {    
16.             PublicTest publicTest = new PublicTest();    
17.             // Accessing public variable    
18.             Console.WriteLine("Hello " + publicTest.name);    
19.             // Accessing public function    
20.             publicTest.Msg("Peter Decosta");    
21.         }    
22.     }     
23. }    

**Output:**

Hello John
Hello Peter Decosta

**Explanation:**

In this example, we have taken a public class "PublicTest" that contains a public variable and a public method. Hence, both members are public so that they can be accessed from outside the class. In the main method, we create an instance of the PublicTest class and use the variable and method. Finally, we call the method name Msg() to print the output using Console.WriteLine() method.

### 2) C# Protected Access Modifier

In C#, the protected class members can be accessed inside the same class and in derived classes, even if they are in a different assembly. The accessibility of protected members is restricted outside the derived classes. It means that any function or object outside the class cannot access the protected members of the class. The protected class members are commonly utilized to represent the implementation of a class that must be accessible to its derived classes.

**Syntax:**

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-access-modifiers#)[](https://www.tpointtech.com/c-sharp-access-modifiers#)[](https://www.tpointtech.com/c-sharp-access-modifiers#)

1. class BaseClass  
2. {  
3.     protected dataType variableName;  

4.     protected void MethodName()  
5.     {  
6.         // block of code  
7.     }  
8. }  

In this syntax,

- **BaseClass:** A class that other classes can use to get their features.
- **protected datatype variableName:** It represents the protected variable, which can be accessed inside the same class and its subclasses.
- **protected void MethodName():** It defines the protected method, which is accessible within its own class and any derived subclasses.

**C# Protected Access Modifier Example**

Let us take an example to illustrate the protected access specifiers in C#.

### Example

[](https://www.tpointtech.com/c-sharp-access-modifiers#)[](https://www.tpointtech.com/c-sharp-access-modifiers#)[](https://www.tpointtech.com/c-sharp-access-modifiers#)

1. using System;  
2. class Creature  
3. {  
4.     // using protected specifier  
5.     protected string message = "Creature Sound";  
6.     protected void MakeNoise()  
7.     {  
8.         Console.WriteLine("The creature makes noise: " + message);  
9.     }  
10. }  
11. class Cat : Creature  
12. {  
13.     public void Meow()  
14.     {  
15.         // Accessing protected members of base class  
16.         message = "Meow!";  
17.         MakeNoise();  
18.     }  
19. }  
20. class Tpoint  
21. {  
22.     static void Main()  
23.     {  
24.         Cat cat = new Cat();  
25.         cat.Meow();  
26.     }  
27. }  

**Output:**

The creature makes noise: Meow!

**Explanation:**

In this example, we create a Creature class that contains a protected method named MakeNoise(), which is accessible in the derived class Cat. Inside the Meow() method of the Cat class, the message field is updated to Meow. After that, we create an instance of the cat class and call its Meow() method to print the output using Console.WriteLine() method.

### 3) C# Internal Access Modifier

In C#, the internal access specifier is an assembly-level access modifier. When a class member is declared as internal, it can only be accessed inside the same assembly. It cannot be accessed from another assembly, even if that assembly references it.

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-access-modifiers#)[](https://www.tpointtech.com/c-sharp-access-modifiers#)[](https://www.tpointtech.com/c-sharp-access-modifiers#)

1. internal class ClassName  
2. {  
3.     internal dataType variableName;  

4.     internal void MethodName()  
5.     {  
6.         // block of code  
7.     }  
8. }  

In this syntax,

- **internal:** It defines the specifier that can be accessed only within the same project or assembly.
- **ClassName:** It represents the name of the class.
- **VariableName:** It defines the name of the variable.
- **MethodName:** It defines the name of the method.

**C# Internal Access Modifier Example**

Let us take an example to illustrate the internal access modifier in C#.

### Example

[](https://www.tpointtech.com/c-sharp-access-modifiers#)[](https://www.tpointtech.com/c-sharp-access-modifiers#)[](https://www.tpointtech.com/c-sharp-access-modifiers#)

1. using System;    
2. namespace AccessSpecifiers    
3. {    
4.     class InternalTest    
5.     {    
6.         internal string name = "Michael";    
7.         internal void Msg(string msg)    
8.         {    
9.             Console.WriteLine("Hello " + msg);    
10.         }    
11.     }    
12.     class Program    
13.     {    
14.         static void Main(string[] args)    
15.         {    
16.             InternalTest internalTest = new InternalTest();    
17.             // Accessing internal variable    
18.             Console.WriteLine("Hello " + internalTest.name);    
19.             // Accessing internal function    
20.             internalTest.Msg("Peter Decosta");    
21.         }    
22.     }    
23. }    

**Output:**

Hello Michael
Hello Peter Decosta

**Explanation:**

In this example, we create a class named InternalTest that contains an internal variable and an internal method. Inside the main method, we create an object of the InternalTest class. Since both are in the same assembly, the name variable and Msg() method are accessible. Finally, we call the Msg() method to print the output using Console.WriteLine() method.

### 4) C# Private Access Modifier

In C#, the private Access Specifier is used to specify private accessibility to the variable or function. It is most restrictive and accessible only within the body of the class in which it is declared. It cannot be accessed from outside the class or by the derived class.

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-access-modifiers#)[](https://www.tpointtech.com/c-sharp-access-modifiers#)[](https://www.tpointtech.com/c-sharp-access-modifiers#)

1. class ClassName  
2. {  
3.     private dataType variableName;  

4.     private void MethodName()  
5.     {  
6.         // block of code  
7.     }  
8. }  

In this syntax,

- **ClassName:** It declares the name of the class.
- **variableName:** It represents the name of the private variable inside the class. It is only accessible inside the block where it is defined.
- **MethodName():** It represents the name of a private method. This method can only be called inside the class.

**C# Private Access Modifier Example**

Let us take an example to illustrate the private access specifiers in C#.

### Example

[](https://www.tpointtech.com/c-sharp-access-modifiers#)[](https://www.tpointtech.com/c-sharp-access-modifiers#)[](https://www.tpointtech.com/c-sharp-access-modifiers#)

1. using System;  
2. class Calc    
3. {     
4.     // Public method  
5.     public void start()  
6.     {     
7.         int result = add(100, 200);  // Calling private method inside the same class  
8.         Console.WriteLine("The Result is " + result);  
9.     }  
10.     // Private method  
11.     private int add(int a, int b)  
12.     {  
13.         return a + b;  
14.     }  
15. }  
16. class Tpoint  
17. {  
18.     static void Main()  
19.     {  
20.         Calc c = new Calc();  
21.         c.start();    
22.     }  
23. }  

**Output:**

The Result is 300

**Explanation:**

In this example, we create a class named Calc that contains two methods: the start() method and the add() method. The start() method calls the add() method, which adds two numbers, 100 and 200. The add() method is private, which means that it cannot be accessed directly from outside the Calc class. Inside the main method(), we create an instance of Calc and call the c.start() method, and show the output by using Console.WriteLine() function.

### 5) Protected Internal Modifier

In C#, the protected internal access modifier enables a class member to be accessed:

- Within the same assembly by any class.
- By derived classes, even if those derived classes are in a different assembly.

In other words, this modifier is a combination of protected and internal access levels. It can be accessed inside the same assembly, and from any derived class, even if that class is present in a different assembly.

**C# Protected Internal Modifier Example:**

Let us take an example to illustrate the protected internal specifier in C#.

### Example

[](https://www.tpointtech.com/c-sharp-access-modifiers#)[](https://www.tpointtech.com/c-sharp-access-modifiers#)[](https://www.tpointtech.com/c-sharp-access-modifiers#)

1. using System;  
2. namespace TPoint  
3. {     
4.     public class Car  
5.     {     
6.         protected internal string m;  
7.         public Car(string m)  
8.         {  
9.             this.m = m;  
10.         }  
11.     }  
12.     public class SportCar : Car  
13.     {  
14.         public SportCar(string m) : base(m) { }  
15.         public void Display()  
16.         {  
17.             Console.WriteLine("SportCar m: " + m);  
18.         }  
19.     }  
20.     class Program  
21.     {  
22.         static void Main(string[] args)  
23.         {  
24.             SportCar myCar = new SportCar("Ferrari");  
25.             myCar.Display();  
26.         }  
27.     }  
28. }  

**Output:**

SportsCar m: Ferrari

**Explanation:**

In this example, we create a base class named Car that contains a string variable, which is marked as a protected internal modifier. After that, we create a derived class SportCar that inherits from Car, so it can access the model field. Inside the main method, we take an object of the SportCar class and then call the Display method to print the "SportsCar model: Ferrari".

### 6) Private Protected Access Modifier in C#

In C#, the private protected access modifier is the combination of private and protected access modifiers. It allows class members to be accessed within the same class or inside the derived classes in the same assembly. The private protected class members cannot be accessed from outside the assembly or by derived classes in a different assembly.

**C# Private Protected Access Modifier Example**

Let us take an example to illustrate the private protected modifier in C#.

### Example

[](https://www.tpointtech.com/c-sharp-access-modifiers#)[](https://www.tpointtech.com/c-sharp-access-modifiers#)[](https://www.tpointtech.com/c-sharp-access-modifiers#)

1. using System;  
2. namespace Point  
3. {  
4.     public class Tpoint  
5.     {  
6.         private protected string msg = "Welcome to Tpoint tech";  
7.         private protected void Message()  
8.         {  
9.             Console.WriteLine(msg);  
10.         }  
11.     }  
12.     public class tech : Tpoint  
13.     {  
14.         public void Show()  
15.         {  
16.             Message();  
17.         }  
18.     }  
19.     class Program  
20.     {  
21.         static void Main(string[] args)  
22.         {  
23.             tech tc = new tech();  
24.             tc.Show();  
25.         }  
26.     }  
27. }  

**Output:**

Welcome to Tpoint tech

**Explanation:**

In this example, we create a class named Tpoint that contains a method Message(), which is marked as a private protected modifier. After that, we create a tech class that inherits the TPoint class. Inside the main method, we create an instance of the tech class and call the Show() method to print the output using Console.WriteLine() method.

## Access modifier in C#

Here is a table summarizing the access modifiers in C#.

|Access Specifier|Same Class|Derived Class|Outside Class|
|---|---|---|---|
|**Public Access Modifier**|Yes|Yes|Yes|
|**Private Access Modifier**|Yes|No|No|
|**Protected Access Modifier**|Yes|No|No|
|**Internal Access Modifier**|Yes|Yes(if in the same assembly)|No|
|**Protected Internal Modifier**|Yes|Yes (If in same assembly or derived)|Yes (If in same assembly)|
|**Private protected Modifier**|Yes|Yes (Only if in the same assembly and derived)|No|

## Important Points about Access Modifier in C#

Several important points of access modifiers in C# are as follows:

- Access modifiers are not allowed in a namespace because they do not enforce access control.
- The user can only use one access modifier at a time, except for private, protected, and protected internal.
- In C#, the internal modifier is the default access modifier in a class.

## Conclusion

In conclusion, the C# access modifier is a key feature of the object-oriented programming language that determines the visibility and accessibility of types, members, and methods in a class or structure. These specifiers are very helpful in encapsulation, which helps to ensure data security, modularity, and code maintainability. It has several modifiers, such as public, private, internal, protected, protected internal, and private protected. It is used to maintain the security of the code.