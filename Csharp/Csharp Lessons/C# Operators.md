

In C#, **_operators_** are special symbols that are to perform operations on variables and values on operands. Operators are important concepts in any programming language. Operators may take one or multiple operands to perform operations and produce a result. There can be perform multiple operations, such as arithmetic, value [assignment](https://www.tpointtech.com/assignment-operator-in-c), bitwise, and [logical](https://www.tpointtech.com/logical-operator-in-c) computations.

### Simple C# Operator Example:

Let us take a simple example to illustrate operators in [C#](https://www.tpointtech.com/c-sharp-tutorial).

### Example

[](https://www.tpointtech.com/csharp-operators#)[](https://www.tpointtech.com/csharp-operators#)[](https://www.tpointtech.com/csharp-operators#)

1. using System;  

2. class BasicExample {  
3.     static void Main() {  
4.         int a = 10, b = 20;  
5.         int c = a + b;  

6.         Console.WriteLine("The value of a + b is " + (c)); // Addition  
7. }  
8. }  

**Output:**

The value of a + b is 30.

## Types of Operators:

There are several types of operators that may perform different types of operations in C#. Important C# operators are as follows:

1. Arithmetic Operators
2. Relational Operators
3. Logical Operators
4. Bitwise Operators
5. Assignment Operators
6. Unary Operators
7. Ternary or Conditional Operators
8. Null-Coalescing Operators
9. Operator Associativity and Precedence

Here, we will discuss these operators one by one with their types and examples.

## 1. Arithmetic Operators

In [C#](https://www.tpointtech.com/c-sharp-tutorial), arithmetic operators are mainly used to perform basic mathematical operations (including addition, subtraction, multiplication, division, etc.) on the operands.

|Operator Name|Symbol|Description|
|---|---|---|
|**Addition**|+|It is commonly utilized to add two numbers together.|
|**Subtraction**|-|It is commonly utilized to subtract one number from another.|
|**Multiplication**|*|It is commonly utilized to multiply two numbers.|
|**Division**|/|It is commonly utilized to divide one number by another.|
|**Modulus**|%|It returns the remainder of division.|

### C# Arithmetic Operators Example:

Let us take an example to illustrate the arithmetic operators in C#.

### Example

[](https://www.tpointtech.com/csharp-operators#)[](https://www.tpointtech.com/csharp-operators#)[](https://www.tpointtech.com/csharp-operators#)

1. using System;  

2. class Arithmetic {  
3.     static void Main() //main method  
4.        {  
5.         int a = 10, b = 3; //initializing variables and values  

6.         Console.WriteLine("The value of a + b is " + (a + b)); // Addition  
7.         Console.WriteLine("The value of a - b is " + (a - b)); // Subtraction  
8.         Console.WriteLine("The value of a * b is " + (a * b)); // Multiplication  
9.         Console.WriteLine("The value of a / b is " + (a / b)); // Division  
10.         Console.WriteLine("The value of a % b is " + (a % b)); // Modulus  
11.     }  
12. }  

**Output:**

The value of a + b is 13
The value of a - b is 7
The value of a * b is 30
The value of a / b is 3
The value of a % b is 1

## 2. Relational (Comparison) Operators

In C#, a relational operator is mainly utilized to compare two values and returns a boolean value (true or false).

|Operator Name|Symbol|Description|
|---|---|---|
|**Equal to**|==|It checks both operands are equal to one another. If both operands are equal, it returns true; else return false.|
|**Not equal to**|!=|It checks if the values of two operands are equal or not. If the values are not equal, the condition becomes true. If values are equal, the condition becomes false.|
|**Greater than**|>|It is utilized to compare two values and returns true if the first operand is greater than the second. If the first operand is not greater than the second, it returns false.|
|**Less than**|<|It is also utilized to compare two values and returns true if the first operand is less than the second operand. Otherwise, it returns false.|
|**Greater than or equal to**|>=|It returns true if the first operand is greater than or equal to the second operand. Otherwise, it returns false.|
|**Less than or equal to**|<=|It returns true if the first operand is less than or equal to the second. Otherwise, it returns false.|

### C# Relational Operators Example:

Let us take an example to illustrate the relational operator's example in C#.

### Example

[](https://www.tpointtech.com/csharp-operators#)[](https://www.tpointtech.com/csharp-operators#)[](https://www.tpointtech.com/csharp-operators#)

1. using System;  

2. class Relational   
3. {  
4.     static void Main() //main method  
5.     {  
6.         int a = 15, b = 30; //initializing variables and values  

7.         Console.WriteLine("The value of a == b is " + (a == b)); // Equal to operator  
8.         Console.WriteLine("The value of a != b is " + (a != b)); // Not equal to operator  
9.         Console.WriteLine("The value of a > b is " + (a > b));   // Greater than operator  
10.         Console.WriteLine("The value of a < b is " + (a < b));   // Less than operator  
11.         Console.WriteLine("The value of a >= b is " + (a >= b)); // Greater than or equal to  
12.         Console.WriteLine("The value of a <= b is " + (a <= b)); // Less than or equal to operator  
13.     }  
14. }   

**Output:**

The value of a == b is False
The value of a != b is True
The value of a > b is False
The value of a < b is True
The value of a >= b is False
The value of a <= b is True

## 3. Logical Operators

In C#, logical operators are utilized to combine more than one condition and return a boolean result.

|Operator Name|Symbol|Description|
|---|---|---|
|**Logical AND**|&&|It returns true only if both the operands are non-zero. Otherwise, it will give false if either or both conditions given are false.|
|**Logical OR**|\||It returns true only if one of the conditions is true. If both conditions are false, it returns false only.|
|**Logical NOT**|!|It inverts the Boolean value of a condition. If a condition is true, it returns false. If a operand value is false, it returns true only.|

### C# Logical Operators Example:

Let us take an example to illustrate the logical operator in C#.

### Example

[](https://www.tpointtech.com/csharp-operators#)[](https://www.tpointtech.com/csharp-operators#)[](https://www.tpointtech.com/csharp-operators#)

1. using System;  

2. class Logical   
3. {  
4.     static void Main() //main method  
5.     {  
6.         bool x = true, y = false; //initializing Boolean variable and value  

7.         Console.WriteLine("The value of x && y is " + (x && y)); // Logical AND  
8.         Console.WriteLine("The value of x || y is " + (x || y)); // Logical OR  
9.         Console.WriteLine("The value of !x is " + (!x)); // Logical NOT  
10.     }  
11. }  

**Output:**

The value of x && y is False
The value of x || y is True
The value of !x is False

## 4. Bitwise Operators

In C#, bitwise operators operate at the binary level to modify bits of a number.

|Operator Name|Symbol|Description|
|---|---|---|
|**Bitwise AND**|&|If this operator exists in both operands, it copies a bit to the result.|
|**Bitwise OR**|\||If it is available in any of the operands, it copies a bit to the calculated result.|
|**Bitwise XOR**|^|If it is available in any of the operands, it copies a bit to the calculated result.|
|**Bitwise Complement**|~|It is unary and has the effect of flipping bits. It reverses the binary values 1 to 0 and 0 to 1|
|**Left Shift**|<<|It shifts all bits in a number a specified number of positions to the left and fills the empty position with 0. It multiplies the number by 2n.|
|**Right Shift**|>>|It shifts all bits of a number to the right by a defined number of positions. In order to positive numbers, empty bits are filled with 0. In order to negative numbers, the behaviour depends on the implementation.|

### C# Bitwise Operators Example:

Let us take an example to illustrate the bitwise operators in C#.

### Example

[](https://www.tpointtech.com/csharp-operators#)[](https://www.tpointtech.com/csharp-operators#)[](https://www.tpointtech.com/csharp-operators#)

1. using System;  

2. class Bitwise   
3. {  
4.     static void Main() //main function  
5.     {  
6.         int a = 10, b = 15; //initializing variables and values  

7.         Console.WriteLine("The value of a & b is " + (a & b)); // Bitwise AND  
8.         Console.WriteLine("The value of a | b is " + (a | b)); // Bitwise OR  
9.         Console.WriteLine("The value of a ^ b is " + (a ^ b)); // Bitwise XOR  
10.         Console.WriteLine("The value of ~a is " + (~a)); // Bitwise Complement  
11.         Console.WriteLine("The value of a << b is " + (a << 1)); //Bitwise Left Shift  
12.         Console.WriteLine("The value of a >> b is " + (a >> 1)); //Bitwise Right Shift  
13.     }  
14. }  

**Output:**

The value of a & b is 10
The value of a | b is 15
The value of a ^ b is 5
The value of ~a is -11
The value of a << b is 20
The value of a >> b is 5

## 5. Assignment Operators

In C#, the [assignment](https://www.tpointtech.com/assignment-operator-in-c) operators are mainly used to assign values to a variable and perform operations simultaneously. The most commonly used operator is the assignment operator (=). It allows us to modify the value stored in the variable.

|Operator Name|Symbol|Description|
|---|---|---|
|**Assign**|=|It is commonly utilized to assign the value of the right operand to the left operand.|
|**Add and assign**|+=|It allows us to add the right operand to the left operand and assign the result value to the left operand.|
|**Subtract and assign**|-=|It allows us to subtract the right operand from the left operand and assign the result value to the left operand.|
|**Multiply and assign**|*=|It allows us to multiply the left operand by the right operand and assign the result number to the left operand.|
|**Divide and assign**|/=|It allows us to divide the left operand by the right operand and assign the result value to the left operand.|
|**Modulus and assign**|%=|It allows us to compute the remainder when the left operand is divided by the right operand and assign the result number to the left operand.|

### C# Assignment Operators Example:

Let us take an example to illustrate the assignment operator in C#.

### Example

[](https://www.tpointtech.com/csharp-operators#)[](https://www.tpointtech.com/csharp-operators#)[](https://www.tpointtech.com/csharp-operators#)

1. using System;  

2. class Program   
3. {  
4.     static void Main() //main function  
5.     {  
6.         int a = 10, b = 6; //initializing variables and values  

7.         Console.WriteLine("The value of a is " + (a)); //using Assignment Operator   

8.         Console.WriteLine("The value of a+=b is " + (a += b));  //using Add and Assignment Operator  

9.         Console.WriteLine("The value of a-=b is " + (a -= b)); //using Subtract and Assignment Operator  

10.         Console.WriteLine("The value of a*=b is " + (a *= b)); //using Multiply and Assignment Operator  

11.         Console.WriteLine("The value of a/=b is " + (a /= b)); //using Divide and Assignment Operator  

12.         Console.WriteLine("The value of a%=b is " + (a %= b)); //using Modulus and Assignment Operator  

13.     }  
14. }  

**Output:**

The value of a is 10
The value of a+=b is 16
The value of a-=b is 10
The value of a*=b is 60
The value of a/=b is 10
The value of a%=b is 4

## 6. Unary Operators

In C#, unary operators perform operations on a single operand.

|Operator Name|Symbol|Description|
|---|---|---|
|**Unary Plus**|+|It represents a positive value. It is usually optional because numbers are positive by default.|
|**Unary Minus**|-|It neglects the value of a variable, which transform a positive number to a negative and vice versa.|
|**Increment**|++|It increases the value of a variable by 1  <br>**Prefix (++x):** It increments the value first, and then it is utilized in the program.  <br>**Postfix (x++):** It uses the value first and then increments it.|
|**Decrement**|--|It decreases the value of a variable by 1  <br>**Prefix (--x):** It decreases the value first, and then it is utilized in the program.  <br>**Postfix (x--):** It uses the value first and then decreases it.|

### C# Unary Operators Example:

Let us take an example to illustrate the unary operator in C#.

### Example

[](https://www.tpointtech.com/csharp-operators#)[](https://www.tpointtech.com/csharp-operators#)[](https://www.tpointtech.com/csharp-operators#)

1. using System;  

2. class Unary   
3. {  
4.     static void Main() //main method  
5.     {  
6.         int a = 10; //initialize variable and value  

7.         Console.WriteLine("The value of +a is " + (+a)); // Unary plus  
8.         Console.WriteLine("The value of -a is " + (-a)); // Unary minus  

9.         Console.WriteLine("The value of a after a++ is " + (a++)); // Increment  

10.         Console.WriteLine("The value of a after a-- is " + (--a)); // Decrement  
11.     }  
12. }  

**Output:**

The value of +a is 10
The value of -a is -10
The value of a after a++ is 10
The value of a after a-- is 10

## 7. Ternary or Conditional Operator

In C#, the ternary operator is an alternative to if-else statements. It mainly performs the operations on three operands. It is conditional-based operator.

### Syntax:

It has the following syntax:

[](https://www.tpointtech.com/csharp-operators#)[](https://www.tpointtech.com/csharp-operators#)[](https://www.tpointtech.com/csharp-operators#)

1. (Condition) ? Expression_a : Expression_b;  

Here, two conditions are occurred:

- If the given condition is true, Expression_a is executed and provides the appropriate result.
- If the given condition is false, Expression_b is executed and provides the appropriate result.

### C# Ternary or Conditional Operator Example:

Let us take an example to illustrate the ternary and conditional operator in C#.

### Example

[](https://www.tpointtech.com/csharp-operators#)[](https://www.tpointtech.com/csharp-operators#)[](https://www.tpointtech.com/csharp-operators#)

1. using System;  

2. class Ternary   
3. {  
4.     static void Main() //main method  
5.     {  
6.         int a = 15, b = 20;  
7.         int min = (a < b) ? a : b;  // If a < b, min = a, otherwise min = b  

8.         Console.WriteLine("The minimum value is " + min);  
9.     }  
10. }  

**Output:**

The minimum value is 15

## 8. Null Coalescing Operators

In C#, null coalescing operators provide a default value when dealing with null values.

|Operator Name|Symbol|Description|
|---|---|---|
|**Null Coalescing**|??|It checks whether or not the left side operand is null. It returns the left operand if it is not null. If it is null, it returns the right operand. It enables us to provide default values.|
|**Null Coalescing Assignment**|??=|It sets the left operand to the right operand only if the left operand is null.|

### C# Null Coalescing Operators Example:

Let us take an example to illustrate the null and coalescing operator in C#.

### Example

[](https://www.tpointtech.com/csharp-operators#)[](https://www.tpointtech.com/csharp-operators#)[](https://www.tpointtech.com/csharp-operators#)

1. using System;  

2. class Program {  
3.     static void Main() {  
4.         int? num = null;  
5.         int result = num ?? 100;  // If num is null, assign 100  

6.         Console.WriteLine("The result is " + result);  

7.         int? x = null;  
8.         x ??= 50;  // Assigns 50 to x if it is null  

9.         Console.WriteLine("The value of x is " + x);  
10.     }  
11. }  

**Output:**

The result is 100
The value of x is 50

## 9. Operator Associativity and Precedence

In C#, operator precedence is the rule which define the evaluation order of different operators in an expression. Operator precedence determines the order of evaluation for different operators, while associativity describes the order between operators of the same precedence, telling whether to evaluate from the left or right.

### 1. Operator Precedence

Operators with higher precedence are evaluated first. For example, in the expression:

### Example

[](https://www.tpointtech.com/csharp-operators#)[](https://www.tpointtech.com/csharp-operators#)[](https://www.tpointtech.com/csharp-operators#)

1. int result = 10 + 5 * 2;  
2. Console.WriteLine(result);  

**Output:**

20

Here, multiplication (*) has higher precedence than addition (+), so 5 * 2 is calculated first, and then 10 is added.

### 2. Operator Associativity

If operators are at the same precedence level, their associativity defines evaluation order:

- **Left-to-Right Associativity:** Operators like +, -, *, /, %, &&, ||, ==, etc., are evaluated from left to right.
- **Right-to-Left Associativity:** Operators like = (assignment), +=, -=, ??=, and the ternary operator (?:) are evaluated from right to left.

**Example of Operator Precedence and Associativity**

### Example

[](https://www.tpointtech.com/csharp-operators#)[](https://www.tpointtech.com/csharp-operators#)[](https://www.tpointtech.com/csharp-operators#)

1. int result = 10 - 2 * 3 + 4;  
2. Console.WriteLine(result);  

**Output:**

8

Since * has higher precedence than - and +, it is evaluated first.

**Example of Right-to-Left Associativity**

### Example

[](https://www.tpointtech.com/csharp-operators#)[](https://www.tpointtech.com/csharp-operators#)[](https://www.tpointtech.com/csharp-operators#)

1. int a = 5;  
2. int b = 10;  
3. int result = a = b = 20; // Right to Left evaluation  
4. Console.WriteLine(result);  

**Output:**

20

Here, b = 20 is evaluated first, then a = 20, and finally result = 20.