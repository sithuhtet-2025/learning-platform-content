In the C# programming language, the checked and unchecked are the keywords that are utilized to handle integral type exceptions. Checked and unchecked keywords specify checked context and unchecked context, respectively. The checked keyword is used to force the run-time to check the arithmetic overflow. On the other hand, the unchecked keyword tells the compiler to ignore overflow.

## C# Checked Keyword

In [C# programming](https://www.tpointtech.com/c-sharp-tutorial), the checked keyword is utilized to explicitly enable overflow checking for integral-type arithmetic operations and conversions. If an overflow occurs during a checked operation, the run-time throws an OverflowException.

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-checked-and-unchecked#)[](https://www.tpointtech.com/c-sharp-checked-and-unchecked#)[](https://www.tpointtech.com/c-sharp-checked-and-unchecked#)

1. checked  
2. {  
3.     // Code inside here will throw an OverflowException on overflow  
4. }  

In this syntax,

- **checked:** It is the keyword that is used to allow overflow checking for arithmetic operations inside the block.

### C# Checked Example without using the checked keyword

Let us take an example to illustrate without using the check keyword in C#.

### Example

[](https://www.tpointtech.com/c-sharp-checked-and-unchecked#)[](https://www.tpointtech.com/c-sharp-checked-and-unchecked#)[](https://www.tpointtech.com/c-sharp-checked-and-unchecked#)

1. using System;    
2. namespace CSharpProgram    
3. {    
4.     class Program    
5.     {    
6.         static void Main(string[] args)     
7.         {    
8.                 int val = int.MaxValue;    
9.                 Console.WriteLine(val + 2);    
10.         }    
11.     }    
12. }    

**Output:**

-2147483647

**Explanation:**

This example generates the wrong result and does not throw any overflow exception.

### C# Checked Example using the checked keyword

Let us take a simple example to illustrate the checked keyword in C#.

### Example

[](https://www.tpointtech.com/c-sharp-checked-and-unchecked#)[](https://www.tpointtech.com/c-sharp-checked-and-unchecked#)[](https://www.tpointtech.com/c-sharp-checked-and-unchecked#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {  
6.         int x = int.MaxValue;   
7.         try  
8.         {  
9.             // checking overflow condition  
10.             checked  
11.             {  
12.                 int result = x + 1;  // OverflowException  
13.                 Console.WriteLine("The Result is " + result);  
14.             }  
15.         }  
16.         catch ( OverflowException m )  
17.         {  
18.             Console.WriteLine("Overflow detected: " + m.Message);  
19.         }  
20.     }  
21. }  

**Output:**

Overflow detected: Arithmetic operation resulted in an overflow.

**Explanation:**

In this example, we demonstrate how to detect an integer overflow using the checked block. First, we initialize a variable x with an int.MaxValue, which is the maximum value. Inside the checked block, the program tries to add 1 to x. Since this operation exceeds the range of an integer value, it causes an overflow. After that, the checked block forces the runtime to throw an OverflowException.

## C# Unchecked Keyword

In C# programming, the unchecked keyword is mainly utilized to ignore overflow-checking context for integral-type arithmetic operations and conversions. If an overflow happens, it will not throw an exception; instead, the result wraps around according to two's complement arithmetic.

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-checked-and-unchecked#)[](https://www.tpointtech.com/c-sharp-checked-and-unchecked#)[](https://www.tpointtech.com/c-sharp-checked-and-unchecked#)

1. unchecked  
2. {  
3.     // Code inside here ignores overflow, values wrap around  
4. }  

In this syntax,

- **unchecked:** It is used to disable overflow checking for arithmetic operations inside the block.

### C# Unchecked Keyword Example

Let us take an example to illustrate the unchecked keyword in C#.

### Example

[](https://www.tpointtech.com/c-sharp-checked-and-unchecked#)[](https://www.tpointtech.com/c-sharp-checked-and-unchecked#)[](https://www.tpointtech.com/c-sharp-checked-and-unchecked#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {  
6.         int y = int.MaxValue;  
7.         // This block ignores overflow  
8.         unchecked  
9.         {  
10.             int result = y + 1;  // No exception, wraps around to a negative value  
11.             Console.WriteLine("The Result is: " + result );  
12.         }  
13.     }  
14. }  

**Output:**

The Result is: -2147483648

**Explanation:**

In this example, we have taken a variable 'y' with int.MaxValue, which is the maximum value an int can hold. Inside the unchecked block, when we add 1 to this value, an overflow occurs. However, since it is inside an unchecked block, the overflow doesn't throw an exception. Instead, the result wraps around to the minimum int value.

## Nested Checked and Unchecked in C#

In C#, nested checked and unchecked blocks allow for placing one inside the other to control overflow behaviour. The outer block sets the default overflow behaviour, and the inner block can override the behaviour temporarily.

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-checked-and-unchecked#)[](https://www.tpointtech.com/c-sharp-checked-and-unchecked#)[](https://www.tpointtech.com/c-sharp-checked-and-unchecked#)

1. checked  
2. {  
3.     // Overflow checking is ON here  
4.     // Some arithmetic operations...  
5.     unchecked  
6.     {  
7.         // Overflow checking is OFF here  
8.         // Values that overflow will wrap around silently  
9.     }  
10.     // Back to checked (overflow checking ON again)  
11. }  

In this syntax,

- **checked block:** It enables overflow checking for all arithmetic operations inside the block.
- **unchecked block:** It ignores the overflow checking for all the arithmetic operations inside the block.

### Simple Example of nested checked and unchecked

Let us take an example to illustrate the nested checked and unchecked keywords in C#.

### Example

[](https://www.tpointtech.com/c-sharp-checked-and-unchecked#)[](https://www.tpointtech.com/c-sharp-checked-and-unchecked#)[](https://www.tpointtech.com/c-sharp-checked-and-unchecked#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {  
6.         int p = int.MaxValue;  
7.         try  
8.         {  
9.             checked  
10.             {  
11.                 Console.WriteLine("Inside checked block:");  
12.                 // It will throw an OverflowException  
13.                 int res1 = p + 1;  
14.                 Console.WriteLine(" The result1 is " + res1 );  
15.                 unchecked  
16.                 {  
17.                     // Inside unchecked  
18.                     int res2 = p + 1;  
19.                     Console.WriteLine(" The result2 is " + res2 );  
20.                 }  
21.             }  
22.         }  
23.         catch (OverflowException m)  
24.         {         
25.             Console.WriteLine("Caught overflow: " + m.Message);  
26.         }  
27.     }  
28. }  

**Output:**

Inside checked block:
Caught overflow: Arithmetic operation resulted in an overflow.

**Explanation:**

In this example, we demonstrate the use of nested checked and unchecked keywords in C#. Inside the checked block, the program tries to add 1 to int.MaxValue, which causes an Overflow, and an OverflowException is thrown. The unchecked block is skipped because the error happens first.

## Difference between Checked and Unchecked keywords

There are several main differences between the checked and unchecked keywords in C#. Some of them are as follows:

|Features|Checked|Unchecked|
|---|---|---|
|**Overflow Check**|It throws an overflow error if the number becomes too large or too small.|It ignores overflow and wraps around the value.|
|**Use**|It is used when we want to catch mistakes with a very large number.|It is used when we expect values to wrap around after getting too big.|
|**Default in debug**|It is enabled by default to help find the error during development.|It is disabled by default.|
|**Default in Release**|It is disabled by default|It is enabled by default.|

## Conclusion

In conclusion, C# checked and unchecked are the powerful keywords to control how arithmetic overflow is handled during the run time of the program. They are important features of C# that help developers manage the overflow behaviour.