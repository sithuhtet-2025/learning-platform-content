
In C#, the break statement is used to end/terminate the loop. It breaks the current flow of the program at a user-defined condition. In the case of a nested loop, the break statement will stop/terminate the inner loop wherever the break statement is applied.

In other words, the break statement works as a jump statement in C#, specifically for the early termination of loops and switch statements.

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-break-statement#)[](https://www.tpointtech.com/c-sharp-break-statement#)[](https://www.tpointtech.com/c-sharp-break-statement#)

1. jump-statement;  
2. break;  
3. // block of the code  

Where,

- **Jump statement:** It is the block of code that is used to control the flow of a program(for, while, do while). It helps to use the stop, continue, or go back while running the program.
- **break:** It is used to exit/terminate the loop of program.

### Flow Diagram of Break Statement

![C# break statement flowchart](https://images.tpointtech.com/csharp/images/c-sharp-break-statement.png)

### C# Break Statement Example

- First, we have to initialize the value.
- Next, we go to the loop or switch statements.
- After that, we check the given break condition of the program.
    1. If the break condition of the program becomes true, it exits/terminates the program.
    2. If the break condition of the program becomes false, it executes the program smoothly as expected.
- End of the program.

### Basic Example of C# Break Statement

Let us take a simple example to illustrate the break statement by using [for loop](https://www.tpointtech.com/c-sharp-for-loop) in C#.

### Example

[](https://www.tpointtech.com/c-sharp-break-statement#)[](https://www.tpointtech.com/c-sharp-break-statement#)[](https://www.tpointtech.com/c-sharp-break-statement#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {  
6.         for (int x = 1; x <= 10; x++)  
7.         {  
8.             if (x == 5)  
9.             {  
10.                 break; // Exit the loop when i = 5  
11.             }  
12.             Console.WriteLine(x);  // print the program  
13.         }  
14.         Console.WriteLine("Loop exited using a break statement.");  
15.     }  
16. }  

**Output:**

1
2
3
4
Loop exited using a break statement.

**Explanation:**

In this example, we print the number by using a for loop. We have taken the integer value x and initialized it (x=1). After that, we have to check the conditions. If it matches the condition (x<=10), the condition will be true. Finally, it exits the program when the program matches the given condition x=5.

## Working of Break Statement in C#

Here, we will discuss the usage of break statements by using the different types of loops in C#.

- Simple Loop
- Nested Loop
- Infinite Loop
- Switch-Case statement

## Break Statement using Simple Loops

In [C# programming](https://www.tpointtech.com/c-sharp-tutorial), we can use the break statement with several simple loops. Some of them are as follows:

### Break Statement Using For Loop

In C#, the break statement within the for loop is very essential when the number is in a looping form.

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-break-statement#)[](https://www.tpointtech.com/c-sharp-break-statement#)[](https://www.tpointtech.com/c-sharp-break-statement#)

1. for(initialization; condition; updation)  
2. {  
3. if(condition)  
4. {  
5. // block of code  
6. break;  // exit the code  
7. }  
8. // The remaining character is printed if not match the condition  
9. }  

**C# Break Statement Example using For Loop**

Let us take an example to illustrate the break statement using the for loop in C#.

### Example

[](https://www.tpointtech.com/c-sharp-break-statement#)[](https://www.tpointtech.com/c-sharp-break-statement#)[](https://www.tpointtech.com/c-sharp-break-statement#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {  
6.         string message = "Good morning ! Welcome to Tpoint Tech.";  
7.         for (int s = 0; s < message.Length; s++)  
8.         {  
9.             if (message[s] == '!')  
10.             {  
11.                 Console.WriteLine("\n Exclamation mark found. Exit the loop.");  
12.                 break;  
13.             }  
14.             Console.Write(message[s]);  
15.         }  
16.     }  
17. }  

**Output:**

Good morning
Exclamation mark found. Exit the loop.

**Explanation:**

In this example, we have taken string-type data and assigned the values. After that, we use a for loop to iterate over the value. Now, we have taken the break statement to exit the program. Finally, we print the output by using the Console.WriteLine() function.

### Break Statement Using While Loop

In C#, a break statement within a [while loop](https://www.tpointtech.com/c-sharp-while-loop) is essential, where the number of iterations is unknown but depends on the condition.

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-break-statement#)[](https://www.tpointtech.com/c-sharp-break-statement#)[](https://www.tpointtech.com/c-sharp-break-statement#)

1. While(condition)  
2. {  
3. If(condition)  
4. {  
5. break; // exit the loop   
6. }  
7. }  

**C# Break Statement Example using While Loop**

Let us take an example to illustrate the break statement using a while loop in C#.

### Example

[](https://www.tpointtech.com/c-sharp-break-statement#)[](https://www.tpointtech.com/c-sharp-break-statement#)[](https://www.tpointtech.com/c-sharp-break-statement#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {  
6.         int num, fact = 1;  
7.         Console.Write("Enter a positive number: ");  
8.         num = Convert.ToInt32(Console.ReadLine());  
9.         if (num < 0)  
10.         {  
11.             Console.WriteLine("Factorial is not defined for negative numbers!");  
12.             return; // Exit the program  
13.         }  
14.         int i = num;  
15.         while (true) // Infinite loop  
16.         {  
17.             if (i == 0 || i == 1)  
18.             {  
19.                 break; // Exit the loop when i reach 0 or 1  
20.             }  

21.             fact *= i;  
22.             i--;  
23.         }  
24.         Console.WriteLine("The Factorial of " + num + " is " + fact);  
25.     }  
26. }  

**Output:**

Enter a positive number: 5
The Factorial of 5 is 120

**Explanation:**

In this example, we print the factorial of numbers by using a while loop. The user is prompted to enter the number. If the number is negative or 1, it exits the while loop because the factorial is undefined for negative numbers. If the number is positive, the program performs the factorial calculation. After that, we use the Console.WriteLine() function to print the program.

### Break Statement using do-while loop

In C#, the [do-while loop](https://www.tpointtech.com/c-sharp-do-while-loop) is the part of the loop that executes at least once before checking the condition. The break statement can be used to exit the loop, regarding the condition. It is also known as the exit control loop.

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-break-statement#)[](https://www.tpointtech.com/c-sharp-break-statement#)[](https://www.tpointtech.com/c-sharp-break-statement#)

1. do  
2. {  
3. if(break_condition)  
4. {  
5. break; //break statement  
6. }  
7. // Execute the remaining code  
8. }  
9. while(condition)  

**C Break Statement Example using do-while loop**

Let us take an example to illustrate the break statement within a do-while loop in C#.

### Example

[](https://www.tpointtech.com/c-sharp-break-statement#)[](https://www.tpointtech.com/c-sharp-break-statement#)[](https://www.tpointtech.com/c-sharp-break-statement#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {  
6.         int num = 3;  
7.         do  
8.         {  
9.             Console.WriteLine("Words: " + num);  
10.             if (num == 5) // break the loop  
11.             {  
12.                 Console.WriteLine("Break the loop at number = " + num);  
13.                 break;  
14.             }  
15.             num++; // Incrementation  
16.         }  
17.         while (num <= 7); // Check the while loop condition  
18.         Console.WriteLine("Exit the loop.");  
19.     }  
20. }  

**Output:**

Words: 3
Words: 4
Words: 5
Break the loop at number = 5
Exit the loop.

**Explanation:**

In this example, we have taken the integer data type **num** and assigned the value. The do-while loop executes at least once before checking the condition. We build the break condition (num=5). It means that if the break condition is matched, it exits the program. After that, we print the output by using the Console.WriteLine() function.

## Break Statement with Nested Loop

In C#, the nested while is a type of loop, where a loop contains another loop. In a Nested loop statement, the inner loop executes completely for each iteration of the outer loop.

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-break-statement#)[](https://www.tpointtech.com/c-sharp-break-statement#)[](https://www.tpointtech.com/c-sharp-break-statement#)

1. for(initialization; condition;  updation)  
2. {  
3. for(initialization; condition; updation)  
4. {  
5. If(condition)  
6. {  
7. break;  // exit the inner loop only  
8. }  
9. }  
10. }  

### C# Break Statement Example using Nested Loop

Let us take an example to illustrate the break statement using the Nested loop.

### Example

[](https://www.tpointtech.com/c-sharp-break-statement#)[](https://www.tpointtech.com/c-sharp-break-statement#)[](https://www.tpointtech.com/c-sharp-break-statement#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {  
6.         for (int i = 1; i <= 3; i++) // Outer loop  
7.         {  
8.             for (int j = 1; j <= 5; j++) // Inner loop  
9.             {  
10.                 if (j == 4)  
11.                 {  
12.                     break; // Exit the inner loop when j == 4  
13.                 }  
14.                 Console.WriteLine($"i = {i}, j = {j}");  
15.             }  
16.         }  
17.     }  
18. }  

**Output:**

i = 1, j = 1
i = 1, j = 2
i = 1, j = 3
i = 2, j = 1
i = 2, j = 2
i = 2, j = 3
i = 3, j = 1
i = 3, j = 2
i = 3, j = 3

**Exaplanation:**

In this example, we used a nested while loop to print the number. The outer loop runs i=1 to i=3. The inner loop runs from j=1 to j=5. After that, we used the break condition on j=4. It means it exits the loop when j is equal to 4. Finally, it prints the output by using the Console.WriteLine() function.

## Break Statement Using Infinite Loop

In C#, we can use the break statement in an infinite loop to terminate the execution process in the infinite loop.

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-break-statement#)[](https://www.tpointtech.com/c-sharp-break-statement#)[](https://www.tpointtech.com/c-sharp-break-statement#)

1. while(true)  
2. {  
3. If(condition)  
4. {  
5. break;  
6. }  
7. }  

### C# Break Statement Example using an Infinite Loop

Let us take an example to illustrate the break statement using an Infinite loop.

### Example

[](https://www.tpointtech.com/c-sharp-break-statement#)[](https://www.tpointtech.com/c-sharp-break-statement#)[](https://www.tpointtech.com/c-sharp-break-statement#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {  
6.         int count = 1;  
7.         while (true) // Infinite loop  
8.         {  
9.             Console.WriteLine("Number: " + count);  
10.             if (count == 4) // exit condition  
11.             {  
12.                 Console.WriteLine("Breaking the loop");  
13.                 break; // terminates the loop  
14.             }  
15.             count++;  
16.         }  
17.         Console.WriteLine("Exit the loop successfully.");  
18.     }  
19. }  

**Output:**

Number: 1
Number: 2
Number: 3
Number: 4
Breaking the loop
Exit the loop successfully.

### Foreach Loop

In C#, the foreach loop is the loop designed to iterate over a collection like an [array](https://www.tpointtech.com/c-sharp-arrays), list, and other enumerable data types. It simplifies the process of accessing each element in the collection without the need for manual testing.

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-break-statement#)[](https://www.tpointtech.com/c-sharp-break-statement#)[](https://www.tpointtech.com/c-sharp-break-statement#)

1. foreach(datatype variable_name in collection)  
2. {  
3. // code to execute the foreach statement  
4. }  

**C# Foreach Loop Example:**

Let us take an example to illustrate the foreach loop using a break statement in C#.

### Example

[](https://www.tpointtech.com/c-sharp-break-statement#)[](https://www.tpointtech.com/c-sharp-break-statement#)[](https://www.tpointtech.com/c-sharp-break-statement#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {  
6. int[] number = { 5, 10, 15, 20, 25 };  
7.         Console.WriteLine("Searching for number 15...");  
8.         foreach (int num in number)  
9.         {  
10.             if (num == 15)  
11.             {  
12.                 Console.WriteLine("Number 15 found!");  
13.                 break; // Exit the loop when 15 is found  
14.             }  
15.             Console.WriteLine($"Checked number: {num}");  
16.         }  
17.         Console.WriteLine("Loop finished.");  
18.     }  
19. }  

**Output:**

Searching for number 15...
Checked number: 5
Checked number: 10
Number 15 found!
Loop finished.

**Explanation:**

In this example, we are searching for the number 15. We have taken the integer array and assigned the static value. We use each loop to iterate over the number. After that, we use the break condition. If the break condition becomes true, it exits the program and then uses the Console.WriteLine() function to print the output.

## Break Statement using Switch-case Statement

In C#, the [switch statement](https://www.tpointtech.com/c-sharp-switch) is a type of decision-making mechanism that allows us to run several code segments based on the value of a given condition. It is also known as a Conditional statement.

The break statement in a switch case is utilized to exit the block of code until the break condition is matched. If the break condition is not matched, the execution will continue to the next case.

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-break-statement#)[](https://www.tpointtech.com/c-sharp-break-statement#)[](https://www.tpointtech.com/c-sharp-break-statement#)

1. switch(expression)  
2. {  
3. case expression_value1;  
4. // statement  
5. break;  
6. case expression_value1;  
7. // statement  
8. break;  
9. case expression_value1;  
10. // statement  
11. break;  
12. default:  
13. // statement  
14. }  

Where,

- **Switch(expression):** The value of the expression is initialised once.
- **expression_value:** It checks the given expressions. If they match, the code will be executed and break the program; otherwise, it moves to the next statement.
- **break;:** It is used to exit the program.
- **default:** It is the optional part of the switch statement; if no expression matches, this
- block executes.

### C# Break Statement Example using Switch Case Statement

Let us take an example to illustrate the break statement in a switch case statement in C#.

### Example

[](https://www.tpointtech.com/c-sharp-break-statement#)[](https://www.tpointtech.com/c-sharp-break-statement#)[](https://www.tpointtech.com/c-sharp-break-statement#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {  
6.         Console.Write("Enter a number (1-3): ");  
7.         string input = Console.ReadLine();  
8.         if (int.TryParse(input, out int number))  
9.         {  
10.             switch (number)  
11.             {  
12.                 case 1:  
13.                     Console.WriteLine("You choose One.");  
14.                     break;  
15.                 case 2:  
16.                     Console.WriteLine("You choose Two.");  
17.                     break;  
18.                 case 3:  
19.                     Console.WriteLine("You choose Three.");  
20.                     break;  
21.                 default:  
22.                     Console.WriteLine("Invalid choice. Please enter 1, 2, or 3.");  
23.                     break;  
24.             }  
25.         }  
26.         else  
27.         {  
28.             Console.WriteLine("Invalid input. Please enter a number.");  
29.         }  
30.         Console.WriteLine("Switch statement complete.");  
31.     }  
32. }  

**Output:**

Enter a number(1-3):
You choose One.
Switch Statement complete.

**Explanation:**

In this example, the user is prompted to enter a number between 1 and 3. After that, we use the switch statement to ensure the valid input. Finally, we use the Console.WriteLine() function to print the output.

### Advantages of the break Statement:

Several advantages of the break statement in C# are as follows.

- The programs are efficient while using the break statement because the break statement stops the unnecessary iteration.
- The termination indicates how to terminate execution to improve readability.

## Conclusion:

In C#, the break statement is the mechanism to exit the code when the break condition becomes true. The code works very efficiently while using the break statement because the break statement stops the unnecessary iteration. It requires attentive usage to preserve code readability and prevent confusion in programming.