
In C#, a **_do while loop_** is a type of the [while loop](https://www.tpointtech.com/c-sharp-while-loop). It is an exit-control loop, which means that the condition is checked after the loop body executes. It ensures that the loop can be executed at least once if the condition is false. This loop is mainly utilized to iterate the code segment multiple times. It starts with the do keyword.

![C# Do-While Loop](https://images.tpointtech.com/csharp/images/c-sharp-do-while-loop.png)

**Syntax**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-do-while-loop#)[](https://www.tpointtech.com/c-sharp-do-while-loop#)[](https://www.tpointtech.com/c-sharp-do-while-loop#)

1. do  
2. {  
3. // code to be executed  
4. // update expression (if needed)  
5. } while (condition)  

In this syntax,

- **Condition:** It is used to check the condition of the program.
- **Update Expression:** It is used to update the variable value, whether it increments or decrements.
- **Body:** It represents the main block of the code, where we write the code.

### Flow Diagram of do-while Loop in C#

![C# Do-While Loop](https://images.tpointtech.com/csharp/images/c-sharp-do-while-loop2.png)

As we can see in the flowchart, use the following steps to implement the do-while loop in [C#](https://www.tpointtech.com/c-sharp-tutorial).

**Step 1:** First, we have to start the do-while loop

**Step 2:** It executes the loop at least once.

**Step 3:** After that, it checks the condition. If the condition is true, the loop continues to work until the condition is false until it exits the loop.

**Step 4:** Finally, display the output.

### Simple do-while loop Example

Let us take an example to illustrate the do-while loop in C#.

### Example

[](https://www.tpointtech.com/c-sharp-do-while-loop#)[](https://www.tpointtech.com/c-sharp-do-while-loop#)[](https://www.tpointtech.com/c-sharp-do-while-loop#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {  
6.         int q = 1; // Initializing the 'q' variable to the value  
7.         do  
8.         {  
9.             Console.WriteLine("Welcome to Tpointtech!");  
10.             q++; // Update the expression  
11.         } while (q <= 8); // Checking the Condition  
12.     }  
13. }  

**Output:**

Welcome to Tpointtech!
Welcome to Tpointtech!
Welcome to Tpointtech!
Welcome to Tpointtech!
Welcome to Tpointtech!
Welcome to Tpointtech!
Welcome to Tpointtech!
Welcome to Tpointtech!

**Explanation:**

In this example, we use a do-while loop to print "Welcome to Tpointtech!" eight times. The loop starts with q = 1 and increments q after each iteration, which repeats the process while q <= 8. The do-while loop ensures the message is printed at least once, regardless of the condition.

### Factorial Number Program Using Do-While Loop

Let us take an example to calculate the factorial numbers using a do-while loop in C#.

### Example

[](https://www.tpointtech.com/c-sharp-do-while-loop#)[](https://www.tpointtech.com/c-sharp-do-while-loop#)[](https://www.tpointtech.com/c-sharp-do-while-loop#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {  
6.         int n;  
7.         int f = 1;  
8.         int i = 1;  
9.         Console.Write("Enter a number of your choice: ");  
10.         n = Convert.ToInt32(Console.ReadLine());  
11.         do  
12.         {  
13.             f = f * i;  
14.             i++;  
15.         } while (i <= n);  
16.         Console.WriteLine("The factorial of the given number is " + f);  
17.     }  
18. }  

**Output:**

Enter a number of your choice: 5
The factorial of the given number is 120

**Explanation:**

In this example, we calculate the factorial number by using the do-while loop statements. First, we have taken the integer value **num** and **fact**. After that, the user is prompted to enter the integer number to calculate the factorial. Finally, we use the do-while loop and print the output by using the Console.WriteLine() function.

## C# Nested do-while Loop

In C# programming language, a nested do-while loop is a type of loop statement where a do-while loop is inside another do-while loop. Before the outer loop moves to its next iteration, the inner loop must finish all of its iterations. The Nested do-while loop indicates that the inner loop executes completely until it's given condition is false for every iteration of the outer loop.

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-do-while-loop#)[](https://www.tpointtech.com/c-sharp-do-while-loop#)[](https://www.tpointtech.com/c-sharp-do-while-loop#)

1. do{  
2. do{  
3. // statement of inner loop  
4. }  
5. while (condition);  
6. // statement of outer loop  
7. } while (condition)  

### C# Nested do-while loop Example:

Let us take a simple example to illustrate the Nested do-while loop statements.

### Example

[](https://www.tpointtech.com/c-sharp-do-while-loop#)[](https://www.tpointtech.com/c-sharp-do-while-loop#)[](https://www.tpointtech.com/c-sharp-do-while-loop#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {  
6.         int r = 1;  // Outer loop counter  

7.         do  
8.         {  
9.             Console.WriteLine("The outer is: " + r);  

10.             int k = 1;  // Inner loop counter  
11.             do  
12.             {  
13.                 Console.WriteLine("   The inner Loop: " + k);  
14.                 k++;  
15.             } while (k <= 3);  

16.             r++;  
17.         } while (r <= 2);  
18.     }  
19. }  

**Output:**

The outer is: 1
The inner Loop: 1
The inner Loop: 2
The inner Loop: 3
The outer is: 2
The inner Loop: 1
The inner Loop: 2
The inner Loop: 3

**Explanation:**

In this example, we use do-while loops to demonstrate nested iteration. Here, we have taken two loop, an outer and inner loop. The outer loop executes two times during iteration the inner loop executes three times. Finally, we use the Console.WriteLine() function and print the output.

## Infinite do-while Loop:

In C#, an infinite do-while loop occurs when the condition is always true. In other words, the loop will continue to run indefinitely because do while loop runs at least once before verifying the condition.

**Syntax**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-do-while-loop#)[](https://www.tpointtech.com/c-sharp-do-while-loop#)[](https://www.tpointtech.com/c-sharp-do-while-loop#)

1. do  
2. {  
3. // block of code   
4. } while (true);  

### Infinite do-while loop Example:

Let us take an example to illustrate an infinite do-while loop in C#.

### Example

[](https://www.tpointtech.com/c-sharp-do-while-loop#)[](https://www.tpointtech.com/c-sharp-do-while-loop#)[](https://www.tpointtech.com/c-sharp-do-while-loop#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {  
6.         do  
7.         {  
8.             Console.WriteLine("This loop will run indefinitely.");  
9.         } while (true); // The condition always evaluates to true.  
10.     }  
11. }  

**Output:**

This loop will run indefinitely.
This loop will run indefinitely.
This loop will run indefinitely.
This loop will run indefinitely.
This loop will run indefinitely.
This loop will run indefinitely.

**Explanation:**

In this example, we use infinite do-while loops to demonstrate nested iteration, where the condition remains always true. After at least one execution, the do block prints to the console, "This loop will run indefinitely". Finally, we use the Console.WriteLine() function to display the output.

## Examples of the do-while loop in C#

There are several examples of the do-while loop in C#. Some of them are as follows:

### Program of Pyramid Pattern Using do-while Loop

Let us take an example to illustrate and print the pyramid pattern using a do-while loop.

### Example

[](https://www.tpointtech.com/c-sharp-do-while-loop#)[](https://www.tpointtech.com/c-sharp-do-while-loop#)[](https://www.tpointtech.com/c-sharp-do-while-loop#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {  
6.         int rows, q = 1, k;  
7.         // Prompt user for input  
8.         Console.Write("Enter the number of rows: ");  
9.         rows = Convert.ToInt32(Console.ReadLine());  
10.         // Outer do-while loop  
11.         do  
12.         {  
13.             k = 1;  
14.             // Inner do-while loop  
15.             do  
16.             {  
17.                 Console.Write("* ");  
18.                 k++;  
19.             } while (k <= q);  
20.             Console.WriteLine();  
21.             q++;  
22.         } while (q <= rows);  
23.     }  
24. }  

**Output:**

Enter the number of rows: 7
*
* *
* * *
* * * *
* * * * *
* * * * * *
* * * * * * *

**Explanation:**

In this example, we demonstrate the do-while loop to display a pyramid pattern at a right angle. The number of rows is prompted by the user. After that, the inner loop iterates completely for each iteration of the outer loop. Every time the inner loop iterates from k=1, it prints *. Finally, we use the Console.WriteLine() function to print the ***** pattern**.**

### Program of Multiplication table using do-while loop.

Let us take an example to illustrate and print the table using a do-while loop in C#.

### Example

[](https://www.tpointtech.com/c-sharp-do-while-loop#)[](https://www.tpointtech.com/c-sharp-do-while-loop#)[](https://www.tpointtech.com/c-sharp-do-while-loop#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {  
6.         int num_ber, q = 1;  
7.         // Initializing the variable num_ber and 'q'.  
8.         Console.Write("Enter a number: ");  
9.         num_ber = Convert.ToInt32(Console.ReadLine());  
10.         // do-while loop to print multiplication table  
11.         do  
12.         {  
13.             Console.WriteLine($"{num_ber} * {q} = {num_ber * q}");  
14.             q++;  
15.         } while (q <= 10);  
16.     }  
17. }  

**Output:**

Enter a number: 7
7 * 1 = 7
7 * 2 = 14
7 * 3 = 21
7 * 4 = 28
7 * 5 = 35
7 * 6 = 42
7 * 7 = 49
7 * 8 = 56
7 * 9 = 63
7 * 10 = 70

**Explanation:**

In this example, we demonstrate the do-while loop to print the table in C#. First, we have taken the two integer variables num_ber and q and q is initialized (q=1). The user prompts to enter the number. After that, we build the logic to print the table. Finally, we use the Console.WriteLine() function to print the output.

## Conclusion

In conclusion, the do-while Loop statement allows us to solve the critical problem in programming. It is essential for performing the repeat action in programs. It is beneficial for programmers to perform dynamic calculations. It ensures that the loop can be executed at least once, if the condition is false.