
In the C# programming language, a delegate is a reference type variable that holds a reference to a method. It functions similarly to a function pointer in C and C++. It offers a more secure, type-safe, and object-oriented approach. It allows methods to be passed as parameters, assigned to variables, and invoked dynamically at runtime. It is one of the most powerful and common features of the C# programming language that is used for implementing events.

![C# Delegates](https://images.tpointtech.com/csharp/images/c-sharp-delegates.png)

In C#, a delegate can encapsulate both a static method and an instance method. Internally, a delegate declaration defines a class that is the derived class of System.Delegate.

## Declaration of Delegates

Delegate type can be declared using the delegate keyword along with a method signature. If we declare a delegate, the delegate instance will refer to and invoke those methods which has the same return type and parameter list as the delegate declaration.

### Syntax:

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-delegates#)[](https://www.tpointtech.com/c-sharp-delegates#)[](https://www.tpointtech.com/c-sharp-delegates#)

1. [modifier] delegate [return_type] [delegate_name] ([parameter_list]);  

In this syntax,

- **modifier:** It represents an access modifier that defines the delegate's visibility.
- **delegate:** It represents a keyword that defines the delegate.
- **return_type:** It represents the value type that is returned by the methods.
- **delegate_name:** It is used to represent the delegate name.
- **parameter_list:** It represents the parameter list that the method must be assigned to the delegate.

## Instantiating a delegate

Once a delegate is declared in C#, we can instantiate it by assigning a method (using the **_new_** keyword) that matches its signature. It allows us to call that method indirectly through the delegate instance.

### Syntax:

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-delegates#)[](https://www.tpointtech.com/c-sharp-delegates#)[](https://www.tpointtech.com/c-sharp-delegates#)

1. [delegate_name] [instance_name] = new [delegate_name](calling_method_name);  

### C# Delegate Example

Let us take an example to illustrate the delegate in C#.

### Example

[](https://www.tpointtech.com/c-sharp-delegates#)[](https://www.tpointtech.com/c-sharp-delegates#)[](https://www.tpointtech.com/c-sharp-delegates#)

1. using System;  
2. namespace TPoint  
3. {  
4.     // defining a delegate  
5.     public delegate void MyDel(string msg);  
6.     class Program  
7.     {  
8.         public static void Point(string msg)  
9.         {  
10.             Console.WriteLine("Hello, " + msg);  
11.         }  
12.         static void Main(string[] args)  
13.         {  
14.             MyDel del = new MyDel(Point);  
15.             del("Albert"); // calling the delegate  
16.         }  
17.     }  
18. }  

**Output:**

Hello, Albert

**Explanation:**

In this example, we have taken a delegate named MyDel that contains the Point() method, which takes a string parameter. After that, the Point() method matches this signature and prints the message. Inside the main method, the delegate is instantiated with the Point method and calls the Point() method to print the output.

## Passing Delegates as a Parameter

In the C# programming language, we can pass a delegate as a parameter to a method. It allows the method referenced by the delegate to be executed. After doing this, we can define a flexible and reusable method that can accept different functions as arguments.

### C# Passing Delegates as a Parameter Example

Let us take an example to illustrate the delegate using a passing-through parameter in C#.

### Example

[](https://www.tpointtech.com/c-sharp-delegates#)[](https://www.tpointtech.com/c-sharp-delegates#)[](https://www.tpointtech.com/c-sharp-delegates#)

1. using System;  
2. namespace TPoint  
3. {  
4.     // defining the delegate  
5.     public delegate void My_Del(string msg);  
6.     class Program  
7.     {  

8.         public static void Say(string n)  
9.         {  
10.             Console.WriteLine("Welcome to TPointTech, " + n);  
11.         }  

12.         public static void GreetUser(My_Del del, string u)  
13.         {  
14.             del(u);  
15.         }  
16.         static void Main(string[] args)  
17.         {  
18.             // Assign the method   
19.             My_Del my_del = Say;  
20.             // Passing the delegate   
21.             GreetUser(my_del, "David");   
22.         }     
23.     }  
24. }  

**Output:**

Welcome to TPointTech, David

**Explanation:**

In this example, we have taken a delegate named My_Del that contains the Say() method. The Say() method matches this delegate and prints a message. The GreetUser() method accepts a delegate and a string. Inside the main method, we create an instance of the delegate and assign it the Say() method, and then we pass this delegate along with the name "David" to GreetUser(). Finally, we call the Say() method and print the message.

## Multicast Delegate

In the C# programming language, a multicast delegate is a special type of delegate that can hold references to multiple methods at the same time. When the delegate is invoked, it executes all the methods one after another. It is useful for calling many functions using a single delegate. All the methods must have the same signature and return type.

### C# Multicast Delegate Example

Let us take an example to illustrate the multicast delegate in C#.

### Example

[](https://www.tpointtech.com/c-sharp-delegates#)[](https://www.tpointtech.com/c-sharp-delegates#)[](https://www.tpointtech.com/c-sharp-delegates#)

1. using System;  
2. namespace TPoint  
3. {  
4.     // defining a delegate  
5.     public delegate void My_Del(string msg);  
6.     class Program  
7.     {  
8.         // First method  
9.         public static void SayHello(string n)  
10.         {  
11.             Console.WriteLine("Welcome, " + n);  
12.         }  
13.         // Second method  
14.         public static void Say(string n)  
15.         {  
16.             Console.WriteLine("Welcome to TPointTech, " + n);  
17.         }  
18.         static void Main(string[] args)  
19.         {  
20.             // Create delegate instances  
21.             My_Del d1 = Say;  
22.             My_Del d2 = Say;  
23.             // Combining delegates  
24.             My_Del multi = d1 + d2;  
25.             // Call the multicast delegate  
26.             multi("David");  
27.         }  
28.     }  
29. }dc  

**Output:**

Welcome to TPointTech, David
Welcome to TPointTech, David

**Explanation:**

In this example, we have taken a delegate named My_Del that contains the string parameter and two methods, SayHello() and Say(). Inside the main method, we create two instance d1 and d2 that are assigned to the Say method, and then we use the multicast delegate instances to print the output.

## Generic Delegate

A generic delegate in C# is a type of delegate that is defined with a type parameter, which enables it to work with any type of data. We can also define a delegate without fixing the data type, which makes the code more flexible and reusable.

### C# Generic Delegate Example

Let us take an example to illustrate the generic delegate in C#.

### Example

[](https://www.tpointtech.com/c-sharp-delegates#)[](https://www.tpointtech.com/c-sharp-delegates#)[](https://www.tpointtech.com/c-sharp-delegates#)

1. using System;  
2. namespace TPoint  
3. {  
4.     // Generic delegate  
5.     public delegate T MyDel<T>(T value);  
6.     class Program  
7.     {     
8.         public static int Sq(int num)  
9.         {  
10.             return num * num;  
11.         }  
12.         public static string Greet(string name)  
13.         {  
14.             return "Welcome, " + name;  
15.         }  
16.         static void Main(string[] args)  
17.         {  
18.             // create a delegate instance   
19.             MyDel<int> Del = Sq;   
20.             Console.WriteLine("The square of a number is " + Del(5));  
21.             // Delegate instance for string  
22.             MyDel<string> dd = Greet;   
23.             Console.WriteLine(dd("Alice"));   
24.         }  
25.     }  
26. }  

**Output:**

The square of a number is 25
Welcome, Alice

**Explanation:**

In this example, we have taken the generic delegate MyDel<T> that contains one parameter of type T and returns the same type. Inside the main method, we create two instances of delegate: one for int to calculate the square of a number using the Sq method, and another for string to greet a user using the Greet method, which returns a welcome message.

## Build-in Delegate

The following table displays the predefined generic delegates available in C#.

|Delegate|Description|Example|
|---|---|---|
|**Action<T>**|It defines a method that takes parameters but returns void.|Action<string> greet = name => Console.WriteLine("Hello, " +name);|
|**Func<T, TResult>**|It represents a method that takes a parameter with a return type.|Func<int, int, int> add = (m, n) => m + n;|
|**Predicate<T>**|It represents a method that takes a parameter and returns a Boolean type.|Predicate<int> isEven = x => x % 2 == 0;|

## Important Points of Delegate:

There are several important points of C# delegates. Some of them are as follows.

- Delegates provide a convenient way to encapsulate methods and treat them as objects.
- It is defined in the System namespace as a class type.
- They are mainly used to implement callback methods and event handling.
- Delegate can be used to invoke anonymous methods.
- Delegates can call more than one method at the same time by linking them together.

## Conclusion

In conclusion, a delegate is a type that holds a reference to a method. It allows methods to be passed as parameters, assigned to variables, and invoked dynamically at runtime. It is one of the most powerful and common features of delegates that is used to handle events. It enables the code to be modular, reusable, and maintainable.