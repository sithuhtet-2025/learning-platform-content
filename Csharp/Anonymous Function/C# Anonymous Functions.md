In the C# programming language, an anonymous function is a type of function that does not have a name. It was introduced in C# 2.0, which is very helpful when the user wants to define an inline anonymous method and pass a parameter to it, just like with any regular method. It is created by using the [delegate keyword](https://www.tpointtech.com/c-sharp-delegates) and does not require the name and return type.

![C# Anonymous Functions](https://images.tpointtech.com/csharp/images/c-sharp-anonymous-function.png)

In C#, an anonymous method is a way to write the inline code without giving it a name. It is similar to a lambda expression, but it allows us to skip the parameter when it is not required. Hence, we can say that an anonymous method has only a body without a name, optional parameters, and a return type.

### Syntax:

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-anonymous-function#)[](https://www.tpointtech.com/c-sharp-anonymous-function#)[](https://www.tpointtech.com/c-sharp-anonymous-function#)

1. delegate(parameter_list)  
2. {  
3.     // block of code  
4. };  

In this syntax,

- **delegate:** It defines an anonymous method without a name.
- **parameter_list:** It includes any input parameters.
- **{ }:** It shows the method body of the program.

### C# Anonymous Function Example:

Let us take an example to illustrate the anonymous method in C#.

### Example

[](https://www.tpointtech.com/c-sharp-anonymous-function#)[](https://www.tpointtech.com/c-sharp-anonymous-function#)[](https://www.tpointtech.com/c-sharp-anonymous-function#)

1. using System;  
2. delegate void GreetDelegate(string name);  
3. class Program  
4. {  
5.     static void Main()  
6.     {  
7.         // Defining an anonymous method  
8.         GreetDelegate greet = delegate(string name)  
9.         {  
10.             Console.WriteLine("Hello, " + name + " ! ");  
11.         };  
12.         // Calling the anonymous method  
13.         greet("John");  
14.     }  
15. }  

**Output:**

Hello, John!

**Explanation:**

In this example, we define a delegate GreetDelegate that takes a string parameter. In the main() method, we assign an anonymous method to this delegate using the delegate keyword. After that, it takes a parameter name and prints a greeting message.

## Features of an Anonymous Function

There are several features of an anonymous function in C#. Some main features are as follows:

- In C#, an anonymous method is defined using the delegate keyword or => operator.
- It must be assigned to a delegate instance.
- It can access variables and functions from the outer (enclosing) scope.
- It can be passed as a parameter to methods that accept delegates.
- It can be utilized as an event handler.

## Lambda Expression

In the [C# programming language](https://www.tpointtech.com/c-sharp-tutorial), a lambda expression is an anonymous function that can have expressions and statements. It can be mainly utilized to create delegates or expression tree types and is often passed as an argument to methods. Lambda expressions are commonly utilized in LINQ queries, which helps to make code more concise and readable.

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-anonymous-function#)[](https://www.tpointtech.com/c-sharp-anonymous-function#)[](https://www.tpointtech.com/c-sharp-anonymous-function#)

1. (parameters) => expression_or_statement_block  

In this syntax,

- **parameters:** It represents the inputs to the lambda expression, which is similar to the method parameters.
- **=>:** This symbol is called the lambda operator, which separates the parameters from the body of the expression.

### C# Lambda Expression Example

Let us take an example to illustrate the Lambda expression in C#.

### Example

[](https://www.tpointtech.com/c-sharp-anonymous-function#)[](https://www.tpointtech.com/c-sharp-anonymous-function#)[](https://www.tpointtech.com/c-sharp-anonymous-function#)

1. using System;  
2. class TPoint  
3. {  
4.     static void Main()  
5.     {  
6.         // Lambda expression to add two numbers  
7.         Func<int, int, int> add = (a, b) => a + b;  
8.         int result = add(10, 20);  
9.         Console.WriteLine("The sum of two numbers is " + result);   
10.     }  
11. }  

**Output:**

The sum of two numbers is 30

**Explanation:**

In this example, we define a simple function that adds two integers. The Func<int, int, int> delegate represents a method that takes two parameters and returns an int result. After that, the lambda expression (a, b) => a + b specifies that the function takes two inputs, a and b, and returns their sum.

### C# Example to Check Even or Odd program using Lambda Expression

Let us take an example to check whether the number is even or odd using a lambda expression in C#.

### Example

[](https://www.tpointtech.com/c-sharp-anonymous-function#)[](https://www.tpointtech.com/c-sharp-anonymous-function#)[](https://www.tpointtech.com/c-sharp-anonymous-function#)

1. using System;  
2. using System.Collections.Generic;  
3. using System.Linq;  
4. class Tpoint  
5. {     
6.     static void Main()  
7.     {  
8.         List<int> n = new List<int> {5, 6, 7, 8, 9, 10,12, 12, 13, 14,15};  
9.         // Using a lambda expression   
10.         var en = n.Where(n => n % 2 == 0);  
11.         Console.WriteLine("The even numbers are ");  
12.         foreach (var num in en)  
13.         {  
14.             Console.WriteLine(num);  
15.         }  
16.     }  
17. }  

**Output:**

The even numbers are
6
8
10
12
12
14

**Explanation:**

In this example, we demonstrate the use of a lambda expression to filter even numbers from the list. First, we create a list n containing several integer values. After that, the program uses LINQ where (n => n % 2 == 0) to select even numbers. The result is stored in en variable, and each number is printed using a foreach loop.

### Anonymous Method with Func Delegate in C#

Let us take an example to illustrate the anonymous method with a Func Delegate in C#.

### Example

[](https://www.tpointtech.com/c-sharp-anonymous-function#)[](https://www.tpointtech.com/c-sharp-anonymous-function#)[](https://www.tpointtech.com/c-sharp-anonymous-function#)

1. using System;  
2. class TPoint  
3. {  
4.     static void Main()  
5.     {  
6.         Func<int, string> check = delegate(int n)  
7.         {  
8.             if (n % 2 == 0)  
9.                 return "Even";  
10.             else  
11.                 return "Odd";  
12.         };  
13.         // Call the anonymous method  
14.         Console.WriteLine("The number 10 is " + check(10));   
15.         Console.WriteLine("The number 7 is " + check(7));     
16.     }  
17. }  

**Output:**

The number 10 is Even
The number 7 is Odd

**Explanation:**

In this example, we define the delegate keyword with a Func<int, string> delegate, which takes an integer and returns a string. In the anonymous method, we use an [if-else](https://www.tpointtech.com/c-sharp-if-else) condition to check whether the number is even or odd. If the number is divisible by 2, it returns an even number; otherwise, it returns an odd number. Finally, we call the delegate by passing a number to it and show the result.

### C# Example for Anonymous Method as an Event Handler

Let us take an example to illustrate event handling using an anonymous method in C#.

### Example

[](https://www.tpointtech.com/c-sharp-anonymous-function#)[](https://www.tpointtech.com/c-sharp-anonymous-function#)[](https://www.tpointtech.com/c-sharp-anonymous-function#)

1. using System;  
2. public class Button  
3. {  
4.     public event EventHandler Press;  
5.     public void Click()  
6.     {  
7.         if (Press != null)  
8.             Press(this, EventArgs.Empty);  
9.     }  
10. }  
11. class Program  
12. {  
13.     static void Main()  
14.     {  
15.         Button bb = new Button();  
16.         // Assigning an anonymous method to the Press event  
17.         bb.Press += delegate (object sender, EventArgs e)  
18.         {  
19.             Console.WriteLine("Button was clicked! (Handled by anonymous method)");  
20.         };  
21.         // Simulate button click  
22.         bb.Click();  
23.     }  
24. }  

**Output:**

Button was clicked! (Handled by anonymous method)

**Explanation:**

In this example, we demonstrate how to use an anonymous method as an event handler. First, we create a class named Button with an event called Press and a method named Click() that raises the press event. In the main method, we create an instance bb of the class button and call the Click() method, and print the output.

## Difference between Anonymous method and Lambda Expression

There are several differences between the anonymous method and the lambda expression in the C# programming language. Some main differences are as follows:

|Aspect|Anonymous Method|Lambda Expression|
|---|---|---|
|**Introduced in**|It was introduced in C# 2.0. It was the first way to write the inline and unnamed methods.|It was introduced in C# 3.0. It provides a more modern and expressive way to define inline functions.|
|**Syntax**|The syntax of an Anonymous method is  <br>delegate (parameter) { }.|The syntax of a Lambda expression is  <br>(parameter) = > expression|
|**Type Interface**|It requires explicit parameter types to be declared.|It supports a type interface, which enables the compiler to automatically deduce the type of the parameter.|
|**Usage**|It is less commonly used than a Lambda Expression.|It is commonly utilized in LINQ queries, event handling, and functional programming.|
|**Parameter**|It can access ref and out parameters of the enclosing method.|It cannot access ref or out parameter from the enclosing method.|

## Limitations of an Anonymous Method

There are several limitations of an anonymous method in C#. Some of them are as follows:

- It cannot have jump statements, including goto, break, or continue.
- It cannot access the ref or out parameter of the enclosing method.
- It cannot contain or access an unsafe code block.
- It cannot be utilized on the left-hand side of the is operator.

## Conclusion

In conclusion, anonymous functions in C# give a method to define methods inline without explicitly declaring them. These anonymous function helps to make code more concise, improve readability, and are very useful when working with delegates and LINQ queries. By using anonymous methods or lambda expressions, we can write cleaner and more flexible code.