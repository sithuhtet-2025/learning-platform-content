
In C#, call by value is the default method for passing arguments to functions in C#. It enables us to copy an original parameter into a formal parameter. The call by value function works on this argument copy, and it cannot modify the original data.

![C# Call by Value](https://images.tpointtech.com/csharp/images/c-sharp-call-by-value.png)

If we want to modify the value of a parameter, it is modified only for the current function. Therefore, any changes inside the parameter do not affect the original value.

### Syntax

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-call-by-value#)[](https://www.tpointtech.com/c-sharp-call-by-value#)[](https://www.tpointtech.com/c-sharp-call-by-value#)

1. Return_type Method_Name (Arguments)  
2. {  
3. // block of code  
4. }  

Where,

- **Return_type:** It specifies the return type that the function returns.
- **Method_Name:** It defines the name of the function.
- **Arguments:** An argument is used to pass the original value in the main method when it is called.

## Call by Value Example in C#

Let us take an example to illustrate the Call by Value in C#.

### Example

[](https://www.tpointtech.com/c-sharp-call-by-value#)[](https://www.tpointtech.com/c-sharp-call-by-value#)[](https://www.tpointtech.com/c-sharp-call-by-value#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {  
6.         int data = 8;  
7.         Change(data);  
8.         Console.WriteLine("The value of the data is: " + data);  
9.     }  
10.     static void Change(int data)  
11.     {  
12.         data = 6;  
13.     }  
14. }  

**Output:**

The value of the data is: 8

**Explanation:**

In this example, the data is initialized with the value 8 in the main function. After that, the change() function is called with data as a parameter, but when this function is passed by value, only a copy is modified inside the change() function. Finally, we print the output by using the Console.WriteLine() function.

## Another Call by Value Example in C#

Let us take another example to illustrate the Call by value method in C#.

### Example

[](https://www.tpointtech.com/c-sharp-call-by-value#)[](https://www.tpointtech.com/c-sharp-call-by-value#)[](https://www.tpointtech.com/c-sharp-call-by-value#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {  
6.         int number = 10;  
7.         Console.WriteLine("Before method call, number = " + number);  
8.         ChangeValue(number);  
9.         Console.WriteLine("After the method call, number = " + number);  
10.     }  
11.     static void ChangeValue(int num)  
12.     {  
13.         num = 20;  
14.         Console.WriteLine("Inside method, num = " + num);  
15.     }  
16. }  

**Output:**

Before method call, number = 10
Inside method, num = 20
After the method call, number = 10

**Explanation:**

In this example, the data is initialized with the value 10 in the main function. After that, the ChangeValue() function is called with data as a parameter, but when this function is passed by value, only a copy is modified inside the change() function. Finally, we print the output by using the Console.WriteLine() function.

## Advantages of Call by Value in C#

Several advantages of call by value in [C#](https://www.tpointtech.com/c-sharp-tutorial) are as follows:

- The call by value does not modify the original variables.
- Whenever this function is called, it does not affect the original value of the actual arguments.
- It requires only those functions that only require to read data because it cannot modify them.
- It has no risk of memory leak.

## Disadvantages of Call by Value in C#

Several disadvantages of call by value in C# are as follows:

- Call by value cannot be utilized when the original variable requires to be modified.
- It requires huge memory space while using large objects such as arrays, strings, structs, etc.
- It does not work efficiently with a dynamic memory location.

## Difference between the Call by Value and Call by Reference in C#

Several differences between Call by Value and [Call by Reference](https://www.tpointtech.com/c-sharp-call-by-reference) in C# are as follows.

|Features|Call by Value|Call by Reference|
|---|---|---|
|**Value Passed**|It is a copy of the value passed to the function.|An address of the value is passed to the function.|
|**Data type**|It is used for basic and simple [data types](https://www.tpointtech.com/csharp-data-types), including int, float, and char.|It is used for complex data types, such as arrays, structs, strings, etc.|
|**Data Safe**|The call by value is considered safer as the original data.|The call by reference is risky because it allows direct modification in original data|
|**Memory Location**|Actual and formal arguments will be created in different memory locations.|Actual and formal arguments will be created in the same memory location|
|**Performance**|It decreases the risk of leaking the data.|It increases the risk as compare the call by value.|

## Conclusion

In conclusion, C# call by value is a key feature that ensures that the data is passed safely without modifying the original variable. It provides better control over leaking the data, especially when the original data must remain unchanged.