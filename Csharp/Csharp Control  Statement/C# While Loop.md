
In C# programming language, loops are an important concept to iterate over a group of statements until a specific condition is met. While loop is one of the loops that is known for its simplicity and versatility.

In [C#](https://www.tpointtech.com/c-sharp-tutorial), the while loop is used to execute the block of code repeatedly as long as when the condition remains true. While loop is mainly utilized when the number of iterations are unknown.

### Syntax

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-while-loop#)[](https://www.tpointtech.com/c-sharp-while-loop#)[](https://www.tpointtech.com/c-sharp-while-loop#)

1. while(condition)  
2. {  
3. // code to be executed  
4. }  

In this syntax,

- **Condition:** It is used to check the given condition of the program. If the condition of the program is matched, it executes the block of code. If the condition of the program is not matched, it exits the loops.
- **Update Expression:** It is used to update the loop variable value, whether it increments or decrements.
- **Body:** It represents the main block of the loop where we write the block of code.

### Flow Diagram of While Loop

![C# While Loop](https://images.tpointtech.com/csharp/images/c-sharp-while-loop.png)

- First, we have to initialize the value.
- Next, we go to the while loop.
- After that, we check the given condition of the program.
    1. If the condition of the program becomes true, execute the block of code.
    2. If the condition of the program becomes false, it exits the loop.
- End of the program.

### C# While Loop Example

Let us take an example to demonstrate a while loop to print 1 to 10 numbers.

### Example

[](https://www.tpointtech.com/c-sharp-while-loop#)[](https://www.tpointtech.com/c-sharp-while-loop#)[](https://www.tpointtech.com/c-sharp-while-loop#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {  
6.         int i = 1;   //initialization   
7.         while (i <= 10)  //condition  
8.         {  
9.             Console.WriteLine(i);  
10.             i++;   // updation  
11.         }  
12.     }  
13. }  

**Output:**

1
2
3
4
5
6
7
8
9
10

**Explanation:**

In this example, we print the numbers 1 to 10 by using a while loop. Here, we initialize the integer value i=1. After that, it checks the condition (i<10). If the condition of the program is true, it prints the value. If the condition of the program is not true, it exits the loop. Finally, the output is displayed using the Console.WriteLine() function.

## Factorial Number Program Using While Loop

Here is an example of factorial using the while loop in C#.

### Example

[](https://www.tpointtech.com/c-sharp-while-loop#)[](https://www.tpointtech.com/c-sharp-while-loop#)[](https://www.tpointtech.com/c-sharp-while-loop#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {  
6.         int num, fact = 1;  
7.         Console.WriteLine("Enter the number:");  
8.         num = int.Parse(Console.ReadLine());  
9.         int i = 1; // initializing the value  
10.         while (i <= num)  // condition of value  
11.         {  
12.             fact *= i;  
13.             i++;        // updation of value  
14.         }  
15.     Console.WriteLine($"The factorial of {num} is {fact}");  
16.     }  
17. }  

**Output:**

Enter the number:
5
The factorial of 5 is 120

**Explanation:**

In this example, we print the factorial number by using the while loop statements. We have taken the integer value num and fact. The user prompted the number for calculating the factorial. After that, we use the while loop and print the output by using the Console.WriteLine() function.

## Nested While Loop

In C#, a nested while loop is a type of while loop statement, where a while loop contains another while loop. In nested loop, the inner loop executes completely for each iteration of the outer loop.

**Syntax**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-while-loop#)[](https://www.tpointtech.com/c-sharp-while-loop#)[](https://www.tpointtech.com/c-sharp-while-loop#)

1. while(condition)  
2. {  
3. while(condition)  
4. {  
5. // statements  
6. }  
7. // statements  
8. }  

### Print Pyramid by Using Nested While Loop in C#.

Let us take a simple example to print the triangle by using the while loop in C#.

### Example

[](https://www.tpointtech.com/c-sharp-while-loop#)[](https://www.tpointtech.com/c-sharp-while-loop#)[](https://www.tpointtech.com/c-sharp-while-loop#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {  
6.         int r = 1;  
7.         while (r <= 5)  // outer loop of the program  
8.         {  
9.             int c = 1;  
10.             while (c <= r)  // inner loop of the program   
11.             {  
12.                 Console.Write("* ");  
13.                 c++;  
14.             }  
15.             Console.WriteLine();  
16.             r++;  
17.         }  
18.     }  
19. }  

**Output:**

*
* *
* * *
* * * *
* * * * *

**Explanation:**

In this example, we have taken the integer data type r, c. Here, r represents the outer loop of the program and c represents the inner loop of the program. While the outer loop runs once, the inner loop runs its full iteration. Finally, we used the Console.WriteLine() function to print the output.

### Print Multiplication Table Using Nested While Loop

Let us take an example to print the table using the nested while loop statements.

### Example

[](https://www.tpointtech.com/c-sharp-while-loop#)[](https://www.tpointtech.com/c-sharp-while-loop#)[](https://www.tpointtech.com/c-sharp-while-loop#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {  
6.         int row = 2;  
7.         while (row < 4) // Outer loop   
8.         {  
9.             int col = 1;  

10.             while (col <= 10) // Inner loop   
11.             {  
12.                 Console.WriteLine($"{row} x {col} = {row * col}");  
13.                 col++;  
14.             }  
15.             Console.WriteLine(); // breaking the line  
16.             row++;  
17.         }  
18.     }  
19. }  

**Output:**

2 x 1 = 2
2 x 2 = 4
2 x 3 = 6
2 x 4 = 8
2 x 5 = 10
2 x 6 = 12
2 x 7 = 14
2 x 8 = 16
2 x 9 = 18
2 x 10 = 20

3 x 1 = 3
3 x 2 = 6
3 x 3 = 9
3 x 4 = 12
3 x 5 = 15
3 x 6 = 18
3 x 7 = 21
3 x 8 = 24
3 x 9 = 27
3 x 10 = 30

**Explanation:**

In this example, we have taken the integer data type row and col. After that, assigns the value row=2 and col=1. Here, row represents the outer loop of the program, and col represents the inner loop of the program, where it creates the logic to multiply numbers. When the outer loop runs once, the inner loop runs its full iteration. Finally, we use the Console.WriteLine() function to print the output.

## C# Infinitive while Loop

In C#, infinite loop is a loop that never terminates and repeats indefinitely. In other words, an infinite loop is a loop in which the test condition has always true.

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-while-loop#)[](https://www.tpointtech.com/c-sharp-while-loop#)[](https://www.tpointtech.com/c-sharp-while-loop#)

1. While(true)  
2. {  
3. // block of the code  
4. }  

### Simple Example of Infinite While Loop:

Let us take a simple example of the infinite while loop.

### Example

[](https://www.tpointtech.com/c-sharp-while-loop#)[](https://www.tpointtech.com/c-sharp-while-loop#)[](https://www.tpointtech.com/c-sharp-while-loop#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {  
6.         while (true)  
7.         {  
8.             Console.WriteLine("Infinitive While Loop");  
9.         }  
10.     }  
11. }  

**Output:**

Infinitive While Loop
Infinitive While Loop

**Explanation:**

In this example, we have created the infinite while loop, where the condition becomes always true. After that, we have taken the Console.WriteLine() function to display the output.

## Controlling While Loop Statement

In C#, there are two types of controlling while loop statements.

- Using break statement
- Using Continue Statement

### Using break statement

In C#, the [break statement](https://www.tpointtech.com/c-sharp-break-statement) is used to exit the condition of the while loop.

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-while-loop#)[](https://www.tpointtech.com/c-sharp-while-loop#)[](https://www.tpointtech.com/c-sharp-while-loop#)

1. break;  

**C# Example Break Statement using While Loop**

Let us take a simple example that uses the break statement to stop the execution.

### Example

[](https://www.tpointtech.com/c-sharp-while-loop#)[](https://www.tpointtech.com/c-sharp-while-loop#)[](https://www.tpointtech.com/c-sharp-while-loop#)

1. using System;     
2. public class Program  
3. {  
4.     public static void Main(string[] args)  
5.     {  
6.         int s = 1;  
7.         while (s < 10)  
8.         {  
9.             if (s == 6)  
10.             {  
11.                 break;  // exit the code when s equal to 5.  
12.             }  
13.             Console.WriteLine(s);  
14.             s++;  
15.         }  
16.         Console.WriteLine("Exit the loop = " + s);  
17.     }  
18. }  

**Output:**

1
2
3
4
5
Exit the loop = 6

**Explanation:**

In this example, we print the numbers 1 to 5. We have taken the integer data type s=1. After that, we check the given condition. If the value of s =6, exit the code by using the break keyword. Finally, we use the Console.WriteLine() function to print the output.

### Using Continue Statement:

In C#, the [continue statement](https://www.tpointtech.com/c-sharp-continue-statement) is used to skip the current iteration and move to the next iteration.

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-while-loop#)[](https://www.tpointtech.com/c-sharp-while-loop#)[](https://www.tpointtech.com/c-sharp-while-loop#)

1. while (condition)  
2. {  
3.     if (condition)  
4.     {  
5.         continue; // skips to the next iteration  
6.     }  
7.     // More code // continue execute the code  
8. }  

**C# Example of Switch Statement using While Loop**

Let us take a simple example that uses the continue statement to skip the execution.

### Example

[](https://www.tpointtech.com/c-sharp-while-loop#)[](https://www.tpointtech.com/c-sharp-while-loop#)[](https://www.tpointtech.com/c-sharp-while-loop#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {  
6.         int s = 0;  // initializing the value  
7.         while (s < 10)  // condition of value  
8.         {  
9.             s++; // increment of value  
10.             if (s == 6)  
11.             {  
12.                 continue; // skip the 6 number  
13.             }  
14.             Console.WriteLine(s); // print the number  
15.         }  
16.     }  
17. }  

**Output:**

1
2
3
4
5
7
8
9
10

**Explanation:**

In this example, we use the continue statement to skip the execution. We have taken the integer data type **s** and initialized the value(**s=0**). After that check the condition(**s<10**). This block of code executes when the condition remains true. After that, we use the continue keyword to skip the value and print the output by using the Console.WriteLine() function.

## Conclusion

In C#, the while loop statement allows us to solve the critical problem in programming. It is essential for performing the repeat action in programs. It is beneficial for programmers to perform dynamic calculations.