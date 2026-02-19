

In the C# programming language, inheritance is a process in which one object acquires all the properties and behaviors of its parent object automatically. In such a way, we can reuse, extend, or modify the attributes and behaviors which is defined in another class.

In [C#](https://www.tpointtech.com/c-sharp-tutorial), the class that inherits the members of another class is called the derived class, and the class whose members are inherited is called the base class. The derived class is the specialized class for the base class.

### Syntax

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-inheritance#)[](https://www.tpointtech.com/c-sharp-inheritance#)[](https://www.tpointtech.com/c-sharp-inheritance#)

1. class BaseClass  
2. {  
3.     // base class members  
4. }  
5. class DerivedClass : BaseClass  
6. {  
7.     // derived class members  
8. }  

In this syntax;

- **Derived Class:** It represents a class that inherits from the other class, which is also known as a subclass. It can add fields and methods to the other class.
- **Base Class:** It is also known as the parent class. It is a class whose features are inherited by the other class.

### C# Inheritance Example

Let us take an example to illustrate the inheritance in C#.

### Example

[](https://www.tpointtech.com/c-sharp-inheritance#)[](https://www.tpointtech.com/c-sharp-inheritance#)[](https://www.tpointtech.com/c-sharp-inheritance#)

1. using System;    
2.    public class Animal    //base class  
3.     {    
4.        public void eat() {   
5. Console.WriteLine("Eating...");   
6. }    
7.    }    
8.    public class Dog: Animal    //derived class  
9.    {    
10.        public void bark() {   
11. Console.WriteLine("Barking...");   
12. }    
13.    }    
14.    class TestInheritance2{    
15.        public static void Main(string[] args)    
16.         {    
17.             Dog d1 = new Dog();    
18.             d1.eat();    
19.             d1.bark();    
20.         }    
21.     }    

**Output:**

Eating...
Barking...

**Explanation:**

In this example, we have taken a base class Animal that defines a method eat(), while the derived class Dog inherits from Animal and adds its own method bark(). In the main() function, a Dog object is created, which can call both eat() and bark() functions. Finally, it shows the output.

## Types of Inheritance

There are several types of inheritance in the C# programming language. These are as follows:

![C# Inheritance](https://images.tpointtech.com/csharp/images/c-sharp-inheritance.png)

Now, we will discuss these inheritances one by one.

### Single Inheritance in C#

In the C# programming language, single inheritance is defined as the inheritance in which a derived class is inherited from only a base class.

![C# Inheritance](https://images.tpointtech.com/csharp/images/c-sharp-inheritance1.png)

**Single Inheritance Example**

Let's take an example of single inheritance in C#.

### Example

[](https://www.tpointtech.com/c-sharp-inheritance#)[](https://www.tpointtech.com/c-sharp-inheritance#)[](https://www.tpointtech.com/c-sharp-inheritance#)

1. using System;    
2.    public class Employee    
3.     {    
4.        public float salary = 40000;    
5.    }    
6.    public class Programmer: Employee    
7.    {    
8.        public float bonus = 10000;    
9.    }    
10.    class SingleInheritance{    
11.        public static void Main(string[] args)    
12.         {    
13.             Programmer p1 = new Programmer();      
14.             Console.WriteLine("Salary: " + p1.salary);    
15.             Console.WriteLine("Bonus: " + p1.bonus);    
16.         }    
17.     }  

**Output:**

Salary: 40000
Bonus: 10000

**Explanation:**

In this example, we have taken a base class Employee, and Programmer is the derived class. After that, the Programmer class inherits the salary field from the Employee class. It has its own field bonus. When we create an object of programmer, we can access both Salary and bonus.

### Multi-Level Inheritance

In the C# programming language, multi-level inheritance is the process by which one class inherits another class, which is further inherited by another class. Inheritance is transitive, so the last derived class acquires all the members of all its base classes.

![C# Inheritance](https://images.tpointtech.com/csharp/images/c-sharp-inheritance2.png)

Let's consider three classes, such as Class A, Class B, and Class C, where Class A represents the base class, Class B represents the intermediary class, and Class C represents the derived class. It shows that one class inherits another class, which is further inherited by another class.

**Syntax:**

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-inheritance#)[](https://www.tpointtech.com/c-sharp-inheritance#)[](https://www.tpointtech.com/c-sharp-inheritance#)

1. class Base    
2. {    
3.     // body of Base class    
4. };    
5.  class Intermediate : public Base     
6. {    
7.     //Body of intermediate class     
8. };    
9. class Derived : public Intermediate     
10. {    
11.     // Body of derived class     
12. };   

**Multi-Level Inheritance Example**

Let us take an example to illustrate the multi-level inheritance in C#.

### Example

[](https://www.tpointtech.com/c-sharp-inheritance#)[](https://www.tpointtech.com/c-sharp-inheritance#)[](https://www.tpointtech.com/c-sharp-inheritance#)

1. using System;    
2.    public class Animal    
3.     {    
4.        public void eat() { Console.WriteLine("Eating..."); }    
5.    }    
6.    public class Dog: Animal    
7.    {    
8.        public void bark() { Console.WriteLine("Barking..."); }    
9.    }    
10.    public class BabyDog : Dog    
11.    {    
12.        public void weep() { Console.WriteLine("Weeping..."); }    
13.    }    
14.    class Mul_level_inheritance{    
15.        public static void Main(string[] args)    
16.         {    
17.             BabyDog d1 = new BabyDog();    
18.             d1.eat();    
19.             d1.bark();    
20.             d1.weep();    
21.         }    
22.     }    

**Output:**

Eating...
Barking...
Weeping...

**Explanation:**

In this example, we have taken a Dog class that inherits from Animal, and the BabyDog class inherits from Dog. Therefore, an object of BabyDog can access methods from all three classes eat(), bark(), and weep().

### Hierarchical Inheritance

In the C# programming language, hierarchical inheritance is a process by which more than one derived class inherits from a single base class. In this inheritance, we can include all features in the base class that are common to child classes.

![C# Inheritance](https://images.tpointtech.com/csharp/images/c-sharp-inheritance3.png)

**Syntax:**

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-inheritance#)[](https://www.tpointtech.com/c-sharp-inheritance#)[](https://www.tpointtech.com/c-sharp-inheritance#)

1. class A      
2. {      
3.     // body of the class A.      
4. }        
5. class B : public A       
6. {      
7.     // body of class B.      
8. }      
9. class C : public A      
10. {      
11.     // body of class C.      
12. }       
13. class D : public A      
14. {      
15.     // body of class D.      
16. }   

**C# Hierarchical Inheritance Example**

Let us take an example to illustrate the Hierarchical inheritance in C#.

### Example

[](https://www.tpointtech.com/c-sharp-inheritance#)[](https://www.tpointtech.com/c-sharp-inheritance#)[](https://www.tpointtech.com/c-sharp-inheritance#)

1. using System;  
2. class Vehicle  
3. {  
4.     public void Start()  
5.     {  
6.         Console.WriteLine("Vehicle has started");  
7.     }  
8. }  
9. class Car : Vehicle  
10. {  
11.     public void Drive()  
12.     {  
13.         Console.WriteLine("Driving the car");  
14.     }  
15. }  
16. class Bike : Vehicle  
17. {  
18.     public void Ride()  
19.     {  
20.         Console.WriteLine("Riding the bike");  
21.     }  
22. }  
23. class Program  
24. {  
25.     static void Main()  
26.     {  
27.         Car car = new Car();  
28.         car.Start();    
29.         car.Drive();    
30.         Bike bike = new Bike();  
31.         bike.Start();   
32.         bike.Ride();    
33.     }  
34. }  

**Output:**

Vehicle has started
Driving the car
Vehicle has started
Riding the bike

**Explanation:**

In this example, we have taken a base class Vehicle with a Start() method, and two derived classes Car and Bike, each having its own methods Drive() and Ride(). In the Main() function, instances of Car and Bike are declared, and both utilize the overridden Start() method as well as their class-specific methods to illustrate hierarchical inheritance.

### Multiple Inheritance

In C#, multiple inheritance is a process by which a class inherits from more than one interface. C# doesn't support inheriting multiple base classes. Use interfaces for multiple inheritance.

![C# Inheritance](https://images.tpointtech.com/csharp/images/c-sharp-inheritance4.png)

**Syntax:**

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-inheritance#)[](https://www.tpointtech.com/c-sharp-inheritance#)[](https://www.tpointtech.com/c-sharp-inheritance#)

1. interface A  
2. {  
3.     void Method1();  
4. }  

5. interface B  
6. {  
7.     void Method2();  
8. }  

9. class MyClass : A, B  
10. {  
11.     public void Method1() { }  
12.     public void Method2() { }  
13. }  

**C# Multiple Inheritance Example**

Let us take an example to illustrate multiple inheritance in C#.

### Example

[](https://www.tpointtech.com/c-sharp-inheritance#)[](https://www.tpointtech.com/c-sharp-inheritance#)[](https://www.tpointtech.com/c-sharp-inheritance#)

1. using System;  
2. interface IWriter  
3. {  
4.     void Write();  
5. }  
6. interface IReader  
7. {  
8.     void Read();  
9. }  
10. class Document : IWriter, IReader  
11. {  
12.     public void Write()  
13.     {  
14.         Console.WriteLine("Writing to the document.");  
15.     }  
16.     public void Read()  
17.     {  
18.         Console.WriteLine("Reading from the document.");  
19.     }  
20. }  
21. class Program  
22. {  
23.     static void Main()  
24.     {  
25.         Document doc = new Document();  
26.         doc.Read();     
27.         doc.Write();   
28.     }  
29. }  

**Output:**

Reading from the document.
Writing to the document.

**Explanation:**

In this example, we have taken two interfaces, IWriter and IReader, each of which declares methods Write() and Read(). Class Document inherits both interfaces, so Document provides an implementation for both methods. In the Main method, a document object is created and used to call the Read() and Write() methods. It demonstrates how C# allows a class to derive functionality from more than one location using interfaces, even though it doesn't directly allow multiple class inheritance.

### Hybrid Inheritance

The C# programming language does not directly support multiple inheritance using classes (to prevent ambiguity). Hybrid inheritance is a mix of multilevel inheritance and hierarchical inheritance.

![C# Inheritance](https://images.tpointtech.com/csharp/images/c-sharp-inheritance5.png)

**Syntax:**

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-inheritance#)[](https://www.tpointtech.com/c-sharp-inheritance#)[](https://www.tpointtech.com/c-sharp-inheritance#)

1. // Base class  
2. class BaseClass  
3. {  
4.     public void DisplayBase() { }  
5. }  

6. // Interface 1  
7. interface A  
8. {  
9.     void Method1();  
10. }  

11. // Interface 2  
12. interface B  
13. {  
14.     void Method2();  
15. }  

16. // Derived class inherits from BaseClass and implements multiple interfaces  
17. class DerivedClass : BaseClass, A, B  
18. {  
19.     public void Method1() { }  
20.     public void Method2() { }  
21. }  

**C# Hybrid Inheritance Example**

Let us take an example to illustrate the Hybrid Inheritance in C#.

### Example

[](https://www.tpointtech.com/c-sharp-inheritance#)[](https://www.tpointtech.com/c-sharp-inheritance#)[](https://www.tpointtech.com/c-sharp-inheritance#)

1. using System;  
2. interface Employee  
3. {  
4.     void Work();  
5. }  
6. class Person  
7. {  
8.     public void ShowDetails()  
9.     {  
10.         Console.WriteLine("Person details displayed");  
11.     }  
12. }  
13. class Manager : Person, Employee  
14. {  
15.     public void ManageTeam()  
16.     {  
17.         Console.WriteLine("Managing the team");  
18.     }  
19.     public void Work()  
20.     {  
21.         Console.WriteLine("Manager is working");  
22.     }  
23. }  
24. class Developer : Person, Employee  
25. {  
26.     public void WriteCode()  
27.     {  
28.         Console.WriteLine("Writing code");  
29.     }  

30.     public void Work()  
31.     {  
32.         Console.WriteLine("Developer is working");  
33.     }  
34. }  
35. class Program  
36. {  
37.     static void Main()  
38.     {  
39.         Manager m = new Manager();  
40.         m.ShowDetails();    
41.         m.ManageTeam();     
42.         m.Work();           
43.         Developer d = new Developer();  
44.         d.ShowDetails();    
45.         d.WriteCode();      
46.         d.Work();           
47.     }  
48. }  

**Output:**

Person details displayed
Managing the team
Manager is working
Person details displayed
Writing code
Developer is working

**Explanation:**

In this example, we have taken a parent class Person, from which Student is inherited, and CollegeStudent is further inherited from Student. CollegeStudent implements the interface IExaminable. In the main() function, an object of CollegeStudent calls methods of Person, Student, its methods, and the interface method, thus demonstrating hybrid inheritance with both class and interface relationships.

## Access Modifiers in C# Inheritance

In the C# programming language, access modifiers help to control the visibility of class members through inheritance. There are mainly five types of access modifiers in C# inheritance. These are as follows:

**1) Public Access Modifiers**

In C#, the public access modifier is mainly used to specify that base class members can be accessed anywhere in the class, derived class, and outside the class. It is also a part of the derived class object. It does not restrict data to the declared block.

**2) Private Access Modifiers**

The private members of the base class can be accessed only inside the same class. The accessibility of private members is restricted outside the derived classes.

**3) Protected Access Modifiers**

The protected members of the base class can be accessed inside the same class and in derived classes. It is not accessible outside the class hierarchy in the case of inheritance.

**4) Internal Access Modifiers**

The internal members can be accessed in the same assembly. It cannot be accessed outside the class. The internal keyword is used to define the internal access modifier in C#. It is useful in large applications with multiple files.

**5) Protected Internal Access Modifiers**

The protected internal members can be accessed in the same assembly (like internal) in which it is declared. It can also be accessed inside the derived classes (like protected). The protected internal keyword is used to specify the protected internal access modifiers.

## Method Overriding in C# Inheritance

In C# inheritance, method overriding enables a derived class to give a specific execution for a method that is already defined in the base class. If a similar method of the class is available in both the base class and the derived class, the derived class method overrides the base class method.

### Method Overriding Example in C# Inheritance

Let us take an example to illustrate the Method overriding in C# inheritance.

### Example

[](https://www.tpointtech.com/c-sharp-inheritance#)[](https://www.tpointtech.com/c-sharp-inheritance#)[](https://www.tpointtech.com/c-sharp-inheritance#)

1. using System;  

2. class Student   // Base class  
3. {  
4.     public string Name;  
5.     public int RollNo;  

6.     public Student(string std_name, int std_rollNo)  
7.     {  
8.         Name = std_name;  
9.         RollNo = std_rollNo;  
10.     }  

11.     // Virtual method  
12.     public virtual void ShowInfo()  
13.     {  
14.         Console.WriteLine($"Student: {Name}, Roll No: {RollNo}");  
15.     }  
16. }  

17. class CollegeStudent : Student   // Derived class  
18. {  
19.     public string Course;  

20.     public CollegeStudent(string std_name, int std_rollNo, string std_course)   
21.         : base(std_name, std_rollNo)  
22.     {  
23.         Course = std_course;  
24.     }  

25.     // Overriding the base method  
26.     public override void ShowInfo()  
27.     {  
28.         Console.WriteLine($"College Student: {Name}, Roll No: {RollNo}, Course: {Course}");  
29.     }  
30. }  

31. class SchoolStudent : Student   // Another derived class  
32. {  
33.     public int ClassGrade;  

34.     public SchoolStudent(string std_name, int std_rollNo, int std_grade)  
35.         : base(std_name, std_rollNo)  
36.     {  
37.         ClassGrade = std_grade;  
38.     }  

39.     // Overriding the base method  
40.     public override void ShowInfo()  
41.     {  
42.         Console.WriteLine($"School Student: {Name}, Roll No: {RollNo}, Grade: {ClassGrade}");  
43.     }  
44. }  

45. class Program  
46. {  
47.     static void Main()  
48.     {  
49.         Student s1 = new CollegeStudent("Michael", 101, "Computer Science");  
50.         Student s2 = new SchoolStudent("Richard", 202, 10);  

51.         // Calls overridden methods  
52.         s1.ShowInfo();  
53.         s2.ShowInfo();  
54.     }  
55. }  

**Output:**

College Student: Michael, Roll No: 101, Course: Computer Science
School Student: Richard, Roll No: 202, Grade: 10

**Explanation:**

In this example, we demonstrate method overriding in C# inheritance. Here, we have taken a student-based class that defines a virtual method ShowInfo that is overridden in the derived classes CollegeStudent and SchoolStudent to give more specific details. When we create objects using the base class references, the overridden methods in the derived classes are executed.

## Type Conversion in C# Inheritance

In C# inheritance, type conversion refers to converting between a base class and its derived class. A derived class object may be implicitly treated as a base class object (upcasting), while converting a base class object back to a derived class requires explicit casting (downcasting). It is very helpful when we want to handle derived objects via base class references.

### Type Conversion Example in C# Inheritance

Let us take an example to illustrate the type conversion in C# inheritance.

### Example

[](https://www.tpointtech.com/c-sharp-inheritance#)[](https://www.tpointtech.com/c-sharp-inheritance#)[](https://www.tpointtech.com/c-sharp-inheritance#)

1. using System;  
2. class Animal  //base class  
3. {  
4.     public void Speak()  
5.     {  
6.         Console.WriteLine("Animal speaks");  
7.     }  
8. }  
9. class Dog : Animal  
10. {  
11.     public void Bark()  
12.     {  
13.         Console.WriteLine("Dog barks");  
14.     }  
15. }  
16. class Program  
17. {  
18.     static void Main()  
19.     {  
20.         // Upcasting  
21.         Animal a = new Dog();  
22.         a.Speak();   
23.         // Downcasting   
24.         if (a is Dog)  
25.         {  
26.             Dog d = (Dog)a;  
27.             d.Bark();    
28.         // Downcasting using 'as'  
29.         Dog d2 = a as Dog;  
30.         if (d2 != null)  
31.         {  
32.             d2.Bark();    
33.         }  
34.         }  
35.     }  
36. }  

**Output:**

Animal speaks
Dog barks
Dog barks

**Explanation:**

In this example, we have taken a Person class that defines a constructor and a virtual method ShowInfo(). The derived class Employee inherits from Person, which calls the base class constructor using the base(emp_name) method, and overrides ShowInfo() while also calling the base method using the base.ShowInfo() method. It ensures that both the base class information (Name) and the derived class information (EmpID) are displayed together.

## Base Keyword in C# Inheritance

In C# inheritance, the base keyword is mainly utilized inside a derived class to access the base class members, and is used to call the base class constructor from the derived class constructor. It can also access the base class methods, properties, and fields that are hidden or overridden in the derived class.

**Syntax:**

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-inheritance#)[](https://www.tpointtech.com/c-sharp-inheritance#)[](https://www.tpointtech.com/c-sharp-inheritance#)

1. base.MemberName  
2. base (...)  

In this syntax,

- **MemberName:** It helps to access the base class members.
- **base (…):** It calls the base class constructor from the derived class constructor.

### Base Keyword Example in C# Inheritance

Let us take an example to illustrate the base keyword in C# inheritance.

### Example

[](https://www.tpointtech.com/c-sharp-inheritance#)[](https://www.tpointtech.com/c-sharp-inheritance#)[](https://www.tpointtech.com/c-sharp-inheritance#)

1. using System;  

2. class Person   // Base class  
3. {  
4.     public string Name;  

5.     public Person(string emp_name)  
6.     {  
7.         Name = emp_name;  
8.     }  

9.     public virtual void ShowInfo()  
10.     {  
11.         Console.WriteLine($"Employee Name: {Name}");  
12.     }  
13. }  

14. class Employee : Person   // Derived class  
15. {  
16.     public int EmpID;  

17.     // Calling base constructor  
18.     public Employee(string emp_name, int emp_id) : base(emp_name)  
19.     {  
20.         EmpID = emp_id;  
21.     }  

22.     // Overriding method  
23.     public override void ShowInfo()  
24.     {  
25.         // Calling base class method using base keyword  
26.         base.ShowInfo();  
27.         Console.WriteLine($"Employee ID: {EmpID}");  
28.     }  
29. }  

30. class Program  
31. {  
32.     static void Main()  
33.     {  
34.         Employee emp = new Employee("Johnson", 201);  
35.         emp.ShowInfo();  
36.     }  
37. }  

**Output:**

Employee Name: Johnson
Employee ID: 201

**Explanation:**

In this example, we have taken a base class Person that defines a constructor and a virtual method ShowInfo(). After that, we have taken the derived class Employee inherits from Person, which calls the base class constructor using the base method, and overrides ShowInfo() method. Finally, we use the base.ShowInfo() method to ensure that both the base class information and the derived class information are displayed together.

## Advantages of Inheritance in C#

There are several advantages of inheritance in C#. Some of them are as follows:

- Inheritance allows us to reuse the methods and properties of a base class in the derived class, which helps to reduce code duplication.
- It allows method overriding, which allows us to use different classes to provide specific implementations while sharing the same interface.
- It makes a hierarchical class structure, which helps to make the code more structured and easier to understand.
- If we make some changes in the base class, it is automatically applied in all derived classes.

## Disadvantages of Inheritance in C#

There are several disadvantages of inheritance in C#. Some of them are as follows:

- In C# inheritance, derived classes are tightly coupled with the base class because they inherit methods and properties of the base class. If we make any change in the base class, it may affect all the derived classes.
- It can increase the code complexity by introducing additional abstraction levels.
- If we create dependencies between the base class and the derived class, inheritance may make the code weaker.
- Deep inheritance hierarchies may make the code harder to understand, debug, and maintain.

## Conclusion

In conclusion, C# inheritance is an essential object-oriented programming method by which a class inherits the properties and behaviors from another class. In C#, the class that inherits the members of another class is called the derived class, and the class whose members are inherited is called the base class. It helps to promote code reusability, extensibility, and polymorphism, which makes applications more maintainable and organized.