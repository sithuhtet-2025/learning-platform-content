 
Last Updated : 21 Jan 2026

In C# programming language, the out keyword is mainly used to pass arguments by reference. It is like a reference-type, except it does not require a variable to initialize before passing. We must use the out keyword to pass arguments as an out type. It is useful when we want a function to return multiple values.

**Syntax**

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-out-parameter#)[](https://www.tpointtech.com/c-sharp-out-parameter#)[](https://www.tpointtech.com/c-sharp-out-parameter#)

1. void MethodName (out DataType parameter1, out DataType parameter2)  
2. {  
3.     // Assigning the value  
4.     parameter1 = value1;  
5.     parameter2 = value2;  
6. }  

In this syntax,

- **void:** It is the void type method, which means the method does not return a value directly.
- **DataType:** It defines the type of data that has been passed to the method.
- **Parameter:** It is used for holding the value that has been passed to the variable.

### C# Out Parameter Example

Let us take an example to illustrate the out parameter in C#.

### Example

[](https://www.tpointtech.com/c-sharp-out-parameter#)[](https://www.tpointtech.com/c-sharp-out-parameter#)[](https://www.tpointtech.com/c-sharp-out-parameter#)

1. using System;  
2. class Program  
3. {  
4.     static void GetSquare(int num_ber, out int square)  
5.     {  
6.         square = num_ber * num_ber;  
7.     }  
8.     static void Main()  
9.     {  
10.         int input = 6;  
11.         int result;  
12.         GetSquare(input, out result);  
13.         Console.WriteLine("The Square of " + input + " is: " + result);  
14.     }  
15. }  

**Output:**

The Square of 6 is: 36

**Explanation:**

In this example, we have taken the out parameter to calculate the square of a number. After that, we define a method named GetSquare that takes an integer input and uses an out parameter to return its square. In the main method, we define the number and call the GetSquare method. Finally, we print the square of a number using Console.WriteLine() function.

### Important Points of Out parameter

Several important points of out parameter in C# are as follows:

- It is similar to the ref keyword.
- The data is passed in a unidirectional (out) manner.
- Method overloading can also be done using an out parameter.
- We cannot use properties as an out parameter because they are not actual variables that can be changed directly.

### C# Out Parameter Example

Let us take an example to illustrate an out parameter in C#.

### Example

[](https://www.tpointtech.com/c-sharp-out-parameter#)[](https://www.tpointtech.com/c-sharp-out-parameter#)[](https://www.tpointtech.com/c-sharp-out-parameter#)

1. using System;  
2. namespace OutParameterSimple  
3. {  
4.     class Program  
5.     {  
6.         // Create method using out parameter  
7.         public void Value(out int number)  
8.         {  
9.             number = 10; // Assigning the value  
10.         }  
11.         static void Main(string[] args)  
12.         {  
13.             int result;  
14.             Program program = new Program();  
15.             program.Value(out result); // Calling method  
16.             Console.WriteLine("The Value set by the method: " + result);  
17.         }  
18.     }  
19. }  

**Output:**

The Value set by the method: 10

**Explanation:**

In this example, we create a method named SetValue that accepts one out parameter called number. Inside the method, we assign the value 10 to this parameter. In the Main method, we declare a variable result without initializing it. After that, we create an object of the program class and call the SetValue method using the out keyword. This allows the method to set the value of the result.

## When to use an out parameter in C#?

In [C# programming](https://www.tpointtech.com/c-sharp-tutorial), the out parameter is used when we need to return more than one value from the method. Let's take an example of two numbers from a single method call.

### Example

[](https://www.tpointtech.com/c-sharp-out-parameter#)[](https://www.tpointtech.com/c-sharp-out-parameter#)[](https://www.tpointtech.com/c-sharp-out-parameter#)

1. using System;  
2. class Program  
3. {  
4.     static void SumAndProduct(int p, int q, out int sum, out int product)  
5.     {  
6.         sum = p + q;  
7.         product = p * q;  
8.     }  
9.     static void Main()  
10.     {  
11.         int number1 = 5, number2 = 10;  
12.         int Sum, Product;  
13.         SumAndProduct(number1, number2, out Sum, out Product);  
14.         // Output the results  
15.         Console.WriteLine($"Sum: {Sum}, Product: {Product}");  
16.     }  
17. }  

**Output:**

Sum: 15, Product: 50

**Explanation:**

In this example, we create a method named **SumAndProduct** that accepts two out parameters. Inside this method, we calculate the sum and product of the numbers. In the main method, we declare that the (5 and 10) values are passed to the method and return their sum and product of the number.

### C# Multiple Out Parameters

In C#, the multiple out parameter allows passing multiple out parameters to the method, and the method returns multiple values.

**Syntax**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-out-parameter#)[](https://www.tpointtech.com/c-sharp-out-parameter#)[](https://www.tpointtech.com/c-sharp-out-parameter#)

1. return_type MethodName (datatype1 param1, datatype2 param2, ..., datatypeN paramN)  
2. {  
3.     // Method   
4. }  

In this syntax,

- **return_type:** It specifies the type of method.
- **datatype:** It defines the type of data that has been passed to the method.

**C# Multiple Out Parameter Example:**

Let us take an example to illustrate the multiple parameters in C#.

### Example

[](https://www.tpointtech.com/c-sharp-out-parameter#)[](https://www.tpointtech.com/c-sharp-out-parameter#)[](https://www.tpointtech.com/c-sharp-out-parameter#)

1. using System;  
2. class Program  
3. {  
4.     // Method  
5.     static void Details(string name, int age, string city)  
6.     {  
7.         Console.WriteLine($"Name: {name}");  
8.         Console.WriteLine($"Age: {age}");  
9.         Console.WriteLine($"City: {city}");  
10.     }  
11.     static void Main()  
12.     {  
13.         // Calling method   
14.         Details("Alice", 25, "New York");  
15.     }  
16. }  

**Output:**

Name: Alice
Age: 25
City: New York

**Explanation:**

In this example, we create a method named PrintDetails that accepts three parameters: a name, an age, and a city. Next, we use the Console.WriteLine() function to print these values. After that, we have call the methods(PrintDetails) in the main method by passing the values "Alice", 25, and "New York".

## Difference between ref and out keyword

Several differences between the ref and out keywords are as follows:

|ref|out|
|---|---|
|It is mandatory to initialize the parameter before it is passed to the ref.|It is not necessary to initialize the parameter before it is passed to out.|
|It does not need to initialize the value of the parameter.|It is necessary to initialize the value of the parameter.|
|The data is passed in a bi-directional(in/out).|The data is passed in unidirectional(out).|
|It is used for modifying the existing value.|It is used for returning a new value.|

## Conclusion

In conclusion, the out keyword in C# allows methods to return multiple values, which makes it very useful when a return statement alone is insufficient. Unlike ref, it does not require the variable to be initialized beforehand."