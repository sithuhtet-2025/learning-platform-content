

In the C# programming language, this keyword refers to the current instance of the class. It is mainly utilized to access instance members, such as fields, methods, and properties. It is very essential when there is a naming conflict with numbers. This keyword is also utilized to track the instance that is called to perform extra processing or calculations associated with that instance.

### Syntax of this keyword

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-this#)[](https://www.tpointtech.com/c-sharp-this#)[](https://www.tpointtech.com/c-sharp-this#)

1. this.memberName = parameterName;  

In this syntax,

- **this:** It represents a keyword that defines the current instance of the class.
- **memberName:** It represents the name of the class's variables.
- **parameterName:** It represents the local variable or parameter that is passed into the methods or a constructor.

## Basic Example of C# this keyword

Let's take an illustrative example of this keyword that refers to the fields of the current class in [C# programming](https://www.tpointtech.com/c-sharp-tutorial).

### Example

[](https://www.tpointtech.com/c-sharp-this#)[](https://www.tpointtech.com/c-sharp-this#)[](https://www.tpointtech.com/c-sharp-this#)

1. using System;  
2. class Student  
3. {  
4.     private string na_me;  
5.     private int age;  
6.     // using Constructor   
7.     public Student(string na_me, int age)  
8.     {  
9.         this.na_me = na_me;   
10.         this.age = age;  
11.     }  
12.     public void ShowDetails()  
13.     {  
14.         Console.WriteLine("The name is " + this.na_me);  
15.         Console.WriteLine("The age is " + this.age);  
16.     }  
17. }  
18. class Program  
19. {  
20.     static void Main()  
21.     {  
22.         Student student1 = new Student("John", 20);  
23.         student1.ShowDetails();  
24.     }  
25. }  

**Output:**

The name is John
The age is 20

**Explanation:**

In this example, we create a class named Student that contains two fields: name and age, and then we create a constructor which accepts two parameters. After that, we create the method ShowDetails() that displays the student's name and age. In the main() method, we create an object student1 and initialize it with values. After that, the ShowDetails() method is called and displays the students details.

### Initialize Class Fields and Constructors using the this keyword

Let us take an example to illustrate this keyword that is used to initialized class fields and the [constructor](https://www.tpointtech.com/c-sharp-constructor).

### Example

[](https://www.tpointtech.com/c-sharp-this#)[](https://www.tpointtech.com/c-sharp-this#)[](https://www.tpointtech.com/c-sharp-this#)

1. using System;  
2. class Staff  
3. {  
4.     private int staff_Id;      // variable  
5.     private string staff_Name;         
6.     private float staff_Salary;  
7.     public Staff(int id, string name, float salary)  
8.     {  
9.         this.staff_Id = id;  
10.         this.staff_Name = name;  
11.         this.staff_Salary = salary;  
12.     }  
13.     public void ShowInfo()  
14.     {  
15.         Console.WriteLine($"{staff_Id}  {staff_Name}  {staff_Salary}");  
16.     }  
17. }  
18. class Program  
19. {  
20.     static void Main(string[] args)  
21.     {  
22.         Staff staff1 = new Staff(101, "Michael", 890000);  
23.         Staff staff2 = new Staff(102, "Stuart", 59000);  
24.         staff1.ShowInfo();  
25.         staff2.ShowInfo();  
26.     }  
27. }  

**Output:**

101 Michael 890000
102 Stuart 59000

**Explanation:**

In this example, we create the class named Staff that contains three fields: StaffId, StaffName and StaffSalary, and then we create a constructor which accepts three parameters. After that, we create the method ShowInfo() that displays the StaffId's, Staff Name's, and Staff Salary's. In the main() method, we create object staff1 and staff2, and then initialize them with values. After that, the ShowInfo() method is called and displays the staff details.

## Uses of this keyword in C#

There are several uses of this keyword in C#. Some of them are as follows.

- It is used to pass the reference of the current object to another method.
- It is used to access the members of the current class.
- It is used to invoke the constructor.
- It is used to define and apply the extension methods.

## Characteristics of this keyword in C#

In C#, several characteristics of this keyword are as follows:

- This keyword is automatically created during the execution of a member function.
- Static functions do not allow this keyword in C#.
- The **_'this'_** keyword is not allowed in static functions because static members belong to the class itself, not to any instance.

## Different ways to use this keyword

There are several ways to use this keyword in C#. Some of them are as follows:

### 1) Accessing Data Members

In C#, this keyword is used to resolve the naming conflicts when a method parameter has the same name as an object's member variable.

**Accessing Data Members Example using this keyword**

Let us take an example to demonstrate how we can access data members using this keyword in C#.

### Example

[](https://www.tpointtech.com/c-sharp-this#)[](https://www.tpointtech.com/c-sharp-this#)[](https://www.tpointtech.com/c-sharp-this#)

1. using System;  
2. class Sample  
3. {  
4.     private int number;  
5.     public void AssignValue(int number)  
6.     {  
7.         this.number = number; // Resolves naming conflict  
8.     }  
9.     public void Display()  
10.     {  
11.         Console.WriteLine("Value of number: " + number);  
12.     }  
13.     static void Main()  
14.     {  
15.         Sample obj = new Sample();  
16.         obj.AssignValue(10);  
17.         obj.Display();  
18.     }  
19. }  

**Output:**

Value of number: 10

**Explanation:**

In this example, we create a Sample class that contains a private integer data member and two methods, AssignValue and Display. The AssignValue method sets the value of a number using the 'this' keyword. In the main method, we create an object and assign the values and then call the Display() method to show the result.

### 2) Returning the Object (Method Chaining)

In the C# programming language, the technique of calling multiple methods in the same object in a single statement is known as method chaining. The this keyword is necessary to enable method chaining because it returns the current instance of the class.

**Returning the Object** **Example using this keyword**

Let us take an example to illustrate the method chaining in C#.

### Example

[](https://www.tpointtech.com/c-sharp-this#)[](https://www.tpointtech.com/c-sharp-this#)[](https://www.tpointtech.com/c-sharp-this#)

1. using System;  
2. class point  
3. {  
4.     private int val;  
5.     public point Set_Val(int x)  
6.     {  
7.         this.val = x;  
8.         return this; // Return the current object  
9.     }  
10.     public void Display()  
11.     {  
12.        Console.WriteLine("The value is " + val);  
13.     }  
14. }  
15. class Program  
16. {  
17.     static void Main()  
18.     {  
19.         point obj = new point(); // creating an object  
20.         obj.Set_Val(25).Display();   
21.     }  
22. }  

**Output:**

The value is 25

**Explanation:**

In this example, we create a Chain class that contains a private integer data member and two methods, SetValue() and Display(). After that, the SetValue() method uses the this keyword to return the current object, which allows method chaining. Finally, it allows us to call multiple methods on the same object in a single statement, which improves the code readability and fluency.

### 3) Passing the Current Object in C#

In C#, the this keyword is used to refer to the current instance of the class. It can be used to pass the current object as an argument to a method or constructor.

**Passing the Current Object Example using this keyword**

Let's see an example to illustrate how we can pass the current objects using this keyword in C#.

### Example

[](https://www.tpointtech.com/c-sharp-this#)[](https://www.tpointtech.com/c-sharp-this#)[](https://www.tpointtech.com/c-sharp-this#)

1. using System;  
2. class Simple  
3. {  
4.     public void Show()  
5.     {  
6.         Console.WriteLine("Inside show method");  
7.     }  
8.     public void Called(Simple obj)  
9.     {  
10.         obj.Show(); // Calling Show() method  
11.     }  
12.     public void Exec()  
13.     {  
14.         Called(this); // Passing the current object  
15.     }  
16.     static void Main()  
17.     {  
18.         Simple s = new Simple();  
19.         s.Exec();   
20.     }  
21. }  

**Output:**

Inside Show method

**Explanation:**

In this example, we define the Sample class that contains three methods: Show(), Call(), and Execute(). The Show() method uses the Console.WriteLine() function to display the value. The Call() method takes an object of the class as a parameter and calls its Show() method. In the Execute() method, this method is used to pass the current object to the Call() method. After that, we create the object of the Sample class and call the execute function.

## Using this keyword in a Constructor in C#

In C#, the this keyword is used inside a constructor to make reference to the class's current instance. It can be used to invoke a different constructor within the same class.

### Constructor Example using this keyword

Let us take an example to solve the naming conflict in the constructor using this keyword in C#.

### Example

[](https://www.tpointtech.com/c-sharp-this#)[](https://www.tpointtech.com/c-sharp-this#)[](https://www.tpointtech.com/c-sharp-this#)

1. using System;  
2. class Sample  
3. {  
4.     private int number;  
5.     // Constructor using 'this' keyword to resolve name conflict  
6.     public Sample(int number)  
7.     {  
8.         this.number = number;  
9.         Console.WriteLine("Constructor executed. Initial number: " + this.number);  
10.     }  
11.     // Method chaining using 'this' keyword  
12.     public Sample UpdateNumber(int value)  
13.     {  
14.         this.number = value;  
15.         return this;  
16.     }  
17.     public void Show()  
18.     {  
19.         Console.WriteLine("Updated Number: " + number);  
20.     }  
21.     static void Main()  
22.     {  
23.         Sample obj = new Sample(10);     // object  
24.         obj.UpdateNumber(20).Show();     //updates number   
25.     }  
26. }  

**Output:**

Constructor executed. Initial number: 10
Updated Number: 20

**Explanation:**

In this example, we create a Sample class that contains a private integer data member and two methods: UpdateNumber() and Show(). The Sample() constructor sets the initial value of the number using the this keyword to resolve a naming conflict. The UpdateNumber() method is used to update the value of the number, and the Show() method is used to display the updated value of the number. In the Main() method, we create an object, set its value, and display it using method chaining.

## Conclusion

In conclusion, the 'this' keyword refers to the current instance of the class in the C# programming language. It is mainly utilized to retrieve members from accesses, instance members, and the constructor. It is used to pass the current object as a parameter to another function. It improves code readability and allows method chaining by returning the current object.