# 
In C#, the Call by Reference is the systematic way to pass values to the function arguments. It enables the function to directly modify the actual variable values because both actual and formal parameters refer to the same variable. If we change in parameter with in the function it might be affect the original arguments. It is also known as Call by Address.

![C# Call by Reference](https://images.tpointtech.com/csharp/images/c-sharp-call-by-reference.png)

### Syntax:

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-call-by-reference#)[](https://www.tpointtech.com/c-sharp-call-by-reference#)[](https://www.tpointtech.com/c-sharp-call-by-reference#)

1. return_type Method_Name(ref dataType param_Name)  
2. {  
3.     // Code to be Executed  
4. }  

Here, we need to use the ref keyword when calling the method.

### Example:

Let's take an instance to demonstrate the Call by Reference in C#.

### Example

[](https://www.tpointtech.com/c-sharp-call-by-reference#)[](https://www.tpointtech.com/c-sharp-call-by-reference#)[](https://www.tpointtech.com/c-sharp-call-by-reference#)

1. using System;  
2. class Tpointtech  
3. {  
4.     static void ModifyValues(ref int num1, ref int num2) // Method to modify values using ref  
5.     {  
6.         num1 *= 3;    
7.         num2 += 7;  // double the first number.  
8.             }  
9.     static void Main(string[] args)  
10.     {  
11.         Console.Write("Enter the First Number: "); //takes user input  
12.         int x = int.Parse(Console.ReadLine());  
13.         Console.Write("Enter the Second Number: ");  
14.         int y = int.Parse(Console.ReadLine());  
15.         Console.WriteLine("\nBefore modification, the values are:");  
16.         Console.WriteLine($"x = {x}, y = {y}");  

17.         ModifyValues(ref x, ref y); // Call the method with ref parameters  
18.         Console.WriteLine("\nAfter modification, the values are:");  
19.         Console.WriteLine($"x = {x}, y = {y}");  
20.     }  
21. }  

**Output:**

Enter the first number: 5
Enter the second number: 2

Before modification, the values are:
x = 5, y = 2

After modification, the values are:
x = 15, y = 9

**Explanation:**

In this example, we use the ref keyword to demonstrate the Call-by-reference function. After that, two integer parameters by reference are modified via the ModifyValues() function, which triples the first value and increases the second by 7.

In the main() [function](https://www.tpointtech.com/c-sharp-function), it first asks the user to input two integer numbers and shows their values before making any modifications. After that, it calls ModifyValues(ref x, ref y), which uses reference passing to update the original values directly.

## Methods in C# Call by Reference:

Several methods of Call by Reference in C# are as follows:

### 1. Using ref in C# (Pass by Reference):

In C#, a [variable](https://www.tpointtech.com/csharp-variables) can be passed by reference using the ref [keyword](https://www.tpointtech.com/csharp-keywords). It means that any changes made to the variable inside the method directly affect the original value in the caller's scope. The ref enables the method to work with the actual variable itself.

### Example for Using Ref Keyword in C#:

### Example

[](https://www.tpointtech.com/c-sharp-call-by-reference#)[](https://www.tpointtech.com/c-sharp-call-by-reference#)[](https://www.tpointtech.com/c-sharp-call-by-reference#)

1. using System;  
2. class Tpointtech  
3. {  
4.     static void DoubleValue(ref int num_ber)  
5.     {  
6.         num_ber *= 3;  // Modifying the original value  
7.     }  
8.     static void Main()  
9.     {  
10.         int value = 14;  
11.         Console.WriteLine("Before modifying the value is: " + value);  
12.         DoubleValue(ref value);  // Passing the variable by reference  
13.         Console.WriteLine("After modifying the value is: " + value);  
14.     }  
15. }  

**Output:**

Before modifying the value is: 14
After modifying the value is: 42

**Explanation:**

In this example, an integer variable is passed by reference using the ref keyword, which enables the method to change the variable's initial value. Using num_ber as a reference parameter, the DoubleValue method updates the original value variable by multiplying it by 3. As a result, when DoubleValue(ref value) is called in the main() function, the modification continues, which changes the value from 14 to 42.

### 2. Using Out in C# (Pass by Reference Without Initialization):

In C#, a method can return multiple values by passing arguments by reference using the out keyword. The Out keyword enables an uninitialized variable to be passed as an argument. But before the method ends, it needs to provide the variable a value.

### Why use Out Keyword in C#?

The out keyword is especially helpful when a method has to return multiple values but does not want to use complex data structures like tuples or objects. It gives a method the ability to change several variables at once without requiring explicit [return statements](https://www.tpointtech.com/return-statement-in-c).

### Example for Using Out Keyword in C#:

### Example

[](https://www.tpointtech.com/c-sharp-call-by-reference#)[](https://www.tpointtech.com/c-sharp-call-by-reference#)[](https://www.tpointtech.com/c-sharp-call-by-reference#)

1. using System;  
2. class Tpointtech  
3. {  
4.     static void GetNumbers(out int num1, out int num2)  
5.     {  
6.         num1 = 10; // Assign value inside the method  
7.         num2 = 20;  
8.     }  
9.     static void Main()  
10.     {  
11.         int x, y;  
12.         GetNumbers(out x, out y);  
13.         Console.WriteLine("The First number is: " + x);  
14.         Console.WriteLine("The Second number is: " + y);  
15.     }  
16. }  

**Output:**

The First number is: 10
The Second number is: 20

**Explanation:**

This C# program allows a method to return several values by passing variables by reference using the out keyword.

### 3. Using In keyword in C# (Pass by Read-Only Reference):

A variable can be passed as a read-only [reference](https://www.tpointtech.com/cpp-references) to a method in [C#](https://www.tpointtech.com/c-sharp-tutorial) using the in [keyword](https://www.tpointtech.com/csharp-keywords). This ensures that the method cannot modify the original value. It is helpful when we work with big structures or objects because it does not allow memory to be copied unnecessarily while maintaining the integrity of the original data.

### Example for Using In keyword in C#:

Let's take an example to demonstrate the In keyword in C#.

### Example

[](https://www.tpointtech.com/c-sharp-call-by-reference#)[](https://www.tpointtech.com/c-sharp-call-by-reference#)[](https://www.tpointtech.com/c-sharp-call-by-reference#)

1. using System;  
2. struct LargeData  
3. {  
4.     public int Number;  
5.     public string Text;  
6. }  
7. class Tpointtech //defining a class  
8. {  
9.     static void DisplayData(in LargeData data)  
10.     {  
11.         Console.WriteLine("Number: " + data.Number); //Shows the Number  
12.         Console.WriteLine("Text: " + data.Text); //Shows the Text  
13.         // data.Number = 115;   
14.     }  
15.     static void Main()  
16.     {  
17.         LargeData obj = new LargeData { Number = 70, Text = "Hello Tpointtech" };  
18.         DisplayData(in obj);  // using read-only reference  
19.     }  
20. }  

**Output:**

Number: 70
Text: Hello Tpointtech

**Explanation:**

This example shows how to pass a read-only reference to a method in the in keyword. An int (Num) and a string (Text) from the LargeData struct are passed to the DisplayData method, which allows only read access and avoids unnecessary memory copying.

## When to Use Call by Reference in C#?

1. **Modifying Original Variables:** It is useful when a method requires to modify a variable's original value instead of creating a copy.
2. **Working with Complex Data Types:** It is suitable for modifying the state of large data structures, arrays, or objects.
3. **Returning Multiple Values:** It can be useful when a method wants to return more values without depending on return values.
4. **Enhancing Code Flexibility:** Functions can interact with variables, which makes code flexible and reusable.

## Advantages of Call by Reference

Several advantages of Call by Reference are as follows:

- It helps to modify the original value.
- It is useful for a large data structure to modify the actual data.
- It doesn't make duplicate data to store values in memory space.

## Disadvantages of Call by Reference:

Several disadvantages of Call by Reference are as follows:

- When several references refer to the same data, changing one reference affects all of them.
- The debugging becomes more challenging.
- As the function is passed by reference, it is no longer theoretically pure.

## Conclusion

In C# language, Call by Reference is a key feature that allows controlled access to the original data, which enables modification when required or ensuring safety through mechanisms like read-only access.