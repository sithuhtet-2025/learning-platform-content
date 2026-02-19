
In C# programming, the for loop is a type of loop that is used to execute a block of code repeatedly as long as the condition remains true. In [C#](https://www.tpointtech.com/c-sharp-tutorial), a for loop is also known as an exit-controlled loop because it checks the condition before the loop body executes. It is used to loop part of the program several times.

![C# for Loop](https://images.tpointtech.com/csharp/images/c-sharp-for-loop.png)

**Syntax**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-for-loop#)[](https://www.tpointtech.com/c-sharp-for-loop#)[](https://www.tpointtech.com/c-sharp-for-loop#)

1. for (initialization; condition; updation)  
2. {  
3. // code to be executed  
4. }    

In this syntax,

- **Initialization:** It is used to initialize the variable at once.
- **Condition:** This block is used to check the condition of the program. If the program condition is matched, the block of code is executed. If the program condition doesn't match, it exits the loops.
- **Updation:** This block is used for updating the loop variable value, whether it increments or decrements.

### Flow Diagram for a for Loop

![C# for Loop](https://images.tpointtech.com/csharp/images/c-sharp-for-loop2.png)

As we can see in the flow chart, use the following steps to implement a for loop in C#.

- First, we have to initialize the value.
- Next, we proceed to the while loop.
- After that, we check the given condition of the program.
    1. If the given condition becomes true, it executes the block of code.
    2. If the given condition becomes false, it does not execute the block of the loop and terminates the loop.
- End of the program.

**C# for Loop Example**

Let us take an example to illustrate the for loop in C#.

### Example

[](https://www.tpointtech.com/c-sharp-for-loop#)[](https://www.tpointtech.com/c-sharp-for-loop#)[](https://www.tpointtech.com/c-sharp-for-loop#)

1. using System;  
2. class Program  
3. {     
4.     static void Main()  
5.     {     
6.         for (int i = 1; i <= 10; i++) // C# for loop  
7.         {  
8.             Console.WriteLine(i);  
9.         }  
10.     }  
11. }   

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

In this example, we print the numbers 1 to 10 by using a for loop. Here, we initialize the integer value i=1. After that, it checks the given condition (i<10). If the given condition is true, it prints the value of i. If the given condition is false, it terminates the loop.

### Factorial Number Program Using a for Loop

Let us take an example to find the factorial of a given number using a for loop in C#.

### Example

[](https://www.tpointtech.com/c-sharp-for-loop#)[](https://www.tpointtech.com/c-sharp-for-loop#)[](https://www.tpointtech.com/c-sharp-for-loop#)

1. using System;   
2. class Program  
3. {  
4.     static void Main()  
5.     {  
6.         int num_ber, factorial = 1;  
7.         Console.WriteLine("Please input the number:");  
8.         num_ber = int.Parse(Console.ReadLine());  
9.         for (int i = 1; i <= num_ber; i++) // using for loop  
10.         {  
11.             factorial *= i;  
12.         }  
13.         Console.WriteLine($"The factorial of {num_ber} is {factorial}");  
14.     }  
15. }   

**Output:**

Please input the number:
6
The factorial of 6 is 720

**Explanation:**

In this example, we are using a for loop to print the factorial number. First, we have taken the integer value num and fact. The user entered the number to calculate the factorial. After that, we use the for loop and print the output by using the Console.WriteLine() function.

### Multiplication Table Using a for loop in C#

Let us take an example to print the table by using the for loop statements.

### Example

[](https://www.tpointtech.com/c-sharp-for-loop#)[](https://www.tpointtech.com/c-sharp-for-loop#)[](https://www.tpointtech.com/c-sharp-for-loop#)

1. using System;  
2. class Program  
3. {     
4.     static void Main()  
5.     {  
6.         int num_ber;  
7.         Console.Write("Enter a Number: ");  
8.         num_ber = int.Parse(Console.ReadLine());  

9.         for (int i = 1; i <= 10; i++) // for loop  
10.         {  
11.             Console.WriteLine($"{num_ber} * {i} = {num_ber * i}");  
12.         }  
13.     }  
14. }   

**Output:**

Enter a Number: 6
6 * 1 = 6
6 * 2 = 12
6 * 3 = 18
6 * 4 = 24
6 * 5 = 30
6 * 6 = 36
6 * 7 = 42
6 * 8 = 48
6 * 9 = 54
6 * 10 = 60

**Explanation:**

In this example, we have taken the integer data type num_ber. After that, we assign the value n=1. The user entered the number to perform the multiplication table. After that, we use a for loop and create the logic to multiply numbers. Finally, we use the Console.WriteLine() function to print the output.

## C# Nested for Loop

In C# programming, the nested for loop is a type of loop statement where one for loop is inside another for loop. The inner loop finishes all of its iterations each time the outer loop runs at least once. In other words, the inner loop completes all its steps before the outer loop runs at least once.

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-for-loop#)[](https://www.tpointtech.com/c-sharp-for-loop#)[](https://www.tpointtech.com/c-sharp-for-loop#)

1. for(initialization; condition; increment)  
2. {  
3. for(initialization; condition; increment)  
4. {  
5. // statement of inner loop  
6. }  
7. // statement of outer loop  
8. }     

### Flow Diagram of Nested for Loop

![C# for Loop](https://images.tpointtech.com/csharp/images/c-sharp-for-loop3.png)

**C# Nested for Loop Example**

Let us take an example to illustrate the Nested for loop in C#.

### Example

[](https://www.tpointtech.com/c-sharp-for-loop#)[](https://www.tpointtech.com/c-sharp-for-loop#)[](https://www.tpointtech.com/c-sharp-for-loop#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {  
6.         for (int i = 1; i <= 3; i++) // outer for loop  
7.         {  
8.             for (int j = 1; j <= 3; j++) // inner for loop  
9.             {  
10.                 Console.WriteLine($"{i} {j}"); // display the value  
11.             }  
12.         }  
13.     }  
14. }   

**Output:**

1 1
1 2
1 3
2 1
2 2
2 3
3 1
3 2
3 3

**Explanation:**

In this example, we are using a nested for loop to print the numbers. First, we have taken the two integer variables i and j. Here, i represents the outer loop that controls the rows, and the inner loop represents the inner loop that controls the columns. After that, it prints the output in 9 lines that shows each pair of values.

### C# Pyramid Program Using Nested for Loops

Let us take an example to print the pyramid pattern using nested for loops in C#.

### Example

[](https://www.tpointtech.com/c-sharp-for-loop#)[](https://www.tpointtech.com/c-sharp-for-loop#)[](https://www.tpointtech.com/c-sharp-for-loop#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {  
6.         Console.Write("Enter the Number of rows: ");  
7.         int n = int.Parse(Console.ReadLine());  
8.         // Outer loop   
9.         for (int i = 0; i < n; i++)  
10.         {  
11.             // Inner loop   
12.             for (int j = 0; j <= i; j++)  
13.             {  
14.                 Console.Write("* "); // stars Printing  
15.             }  
16.             Console.WriteLine(); // moves to the new line after every row  
17.         }  
18.     }  
19. }   

**Output:**

Enter the Number of rows: 6
*
* *
* * *
* * * *
* * * * *
* * * * * *

**Explanation:**

In this example, we have created the pyramid program using a nested for loop statement. First, we have taken the two integer variables i and j. After that, it prompts the user to input the number of rows and uses a nested loop. The outer loop is used to control the number of rows, whereas the inner loop is used to print the stars in increasing order each time.

### C# Inverted Pyramid Program Using Nested for Loops

Let us take an example to print the pyramid pattern using a nested for loop in C#.

### Example

[](https://www.tpointtech.com/c-sharp-for-loop#)[](https://www.tpointtech.com/c-sharp-for-loop#)[](https://www.tpointtech.com/c-sharp-for-loop#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {  
6.         Console.Write("Enter the Number of rows: ");  
7.         int n = int.Parse(Console.ReadLine());  
8.         // Outer loop  
9.         for (int i = 0; i < n; i++)  
10.         {  
11.             // Inner loop  
12.             for (int j = n; j > i; j--)  
13.             {  
14.                 Console.Write("* "); // stars printing  
15.             }  
16.             Console.WriteLine(); // moves to the new line after every row  
17.         }  
18.     }  
19. }   

**Output:**

Enter the Number of rows: 8
* * * * * * * *
* * * * * * *
* * * * * *
* * * * *
* * * *
* * *
* *
*

**Explanation:**

In this example, we have created the inverted pyramid program using a nested for loop statement. First, it prompts the user to input the number of rows and uses a nested loop. The outer loop is used to control the number of rows, whereas the inner loop is used to print the stars in decreasing order each time.

## C# Infinite for Loop

In C#, if we remove the initialization, condition, and update expression, it will result in an infinite loop. In other words, if we use a double semicolon in the for loop, it will be executed infinite times.

**Syntax**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-for-loop#)[](https://www.tpointtech.com/c-sharp-for-loop#)[](https://www.tpointtech.com/c-sharp-for-loop#)

1. for( ; ; )    
2. {  
3. //  code to be executed  
4. }  

**C# Infinite for Loop Example**

Let us take an example to illustrate an infinite for loop in C#.

### Example

[](https://www.tpointtech.com/c-sharp-for-loop#)[](https://www.tpointtech.com/c-sharp-for-loop#)[](https://www.tpointtech.com/c-sharp-for-loop#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {  
6.         for (;;) // infinite for loop  
7.         {  
8.             Console.Write("Hello! Tpointtech"); // prints without newline  
9.         }  
10.     }  
11. }    

**Output:**

Hello! Tpointtech
Hello! Tpointtech
Hello! Tpointtech
Hello! Tpointtech

**Explanation:**

In this example, we have built the program using an infinite 'for' loop. The loop is defined as 'for (;;)', which runs endlessly because it has no condition. Inside the loop, we repeatedly print "Hello Tpointtech" to the console.

## C# foreach Loop

In C# programming, the foreach loop is a loop that is used to work with collections like [strings](https://www.tpointtech.com/c-sharp-strings), [arrays](https://www.tpointtech.com/c-sharp-arrays) and arrays of objects, etc. It works on the basis of items. The foreach loop is an element-based loop, which means to fetches each element from the collection one by one.

**Syntax**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-for-loop#)[](https://www.tpointtech.com/c-sharp-for-loop#)[](https://www.tpointtech.com/c-sharp-for-loop#)

1. foreach (datatype variable in collection)  
2. {  
3.     // Code to be executed  
4. }   

In this syntax,

- **Datatype:** It represents the type of elements in the collection (such as int, string, etc).
- **Datatype:** It represents the type of elements in the collection (such as int, string, etc).
- **Collection:** It represents the collection of an array.

**C# for each loop Example:**

Let us take an example to illustrate the for each loop in C#.

### Example

[](https://www.tpointtech.com/c-sharp-for-loop#)[](https://www.tpointtech.com/c-sharp-for-loop#)[](https://www.tpointtech.com/c-sharp-for-loop#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {  
6.         // Define an array of fruits  
7.         string[] fruits = { "Apple", "Banana", "Orange", "Mango" };  

8.         // Use a foreach loop to iterate through the array  
9.         foreach (string fruit in fruits)  
10.         {  
11.             Console.WriteLine("Fruit: " + fruit);  
12.         }  
13.     }  
14. }   

**Output:**

Fruit: Apple
Fruit: Banana
Fruit: Orange
Fruit: Mango

**Explanation:**

In this example, we use the foreach loop to iterate over items in the collection. First, we have created an array named fruits and stored some fruits. After that, we have used the for loop to iterate the items from the array. Finally, we are using the Console.WriteLine() function to print the output.

## Conclusion

In conclusion, the C# for Loop statement allows us to solve the critical problem in programming. It is essential for performing the repeat action in programs. It is beneficial for programmers to perform dynamic calculations.