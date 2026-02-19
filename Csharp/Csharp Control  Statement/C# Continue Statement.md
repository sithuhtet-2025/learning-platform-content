
The C# **_continue statement_** is used to continue loop. It continues the current flow of the program and skips the remaining code at specified condition. In the case of inner loop, it continues only inner loop. It forces the program control to run the next loop iteration.

The continue statement is utilized in the loop of the program. In simple words, the code body of any loop following the continue statement would be skipped from the loop, and the next loop iteration would start again.

### Syntax:

It has the followings syntax:

[](https://www.tpointtech.com/c-sharp-continue-statement#)[](https://www.tpointtech.com/c-sharp-continue-statement#)[](https://www.tpointtech.com/c-sharp-continue-statement#)

1. //loop statements  
2. continue; //continue statement  
3. //Code lines, which are to be skipped   

### Flow Diagram of the Continue Statement:

![C# Continue Statement](https://images.tpointtech.com/csharp/images/c-sharp-continue-statement.png)

As we can see in the flowchart, use the following steps to implement the continue statement in C#:

**Step 1:** First, go to the any loop body of the program.

**Step 2:** In the next step, it checks the loop condition to continue the next iteration.

**Step 3:** If the condition is true, it continues to execute the loop body until it is going to be false.

**Step 4:** If the condition is false, it executes the remaining part of the loop body.

**Step 5:** Finally, it prints the output.

## Working of Continue Statement:

In [C#](https://www.tpointtech.com/c-sharp-tutorial) programming, the continue statement works with several loops, including [for loop](https://www.tpointtech.com/c-sharp-for-loop), [while loop](https://www.tpointtech.com/c-sharp-while-loop), [do-while loop](https://www.tpointtech.com/c-sharp-do-while-loop), for-each loop, and nested loop.

### 1. Continue Statement with for Loop in C#:

In C#, if a continue statement is utilized in the [for loop](https://www.tpointtech.com/c-sharp-for-loop), it jumps the current iteration, and the control flow moves to the next iteration of the loop body.

**Syntax:**

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-continue-statement#)[](https://www.tpointtech.com/c-sharp-continue-statement#)[](https://www.tpointtech.com/c-sharp-continue-statement#)

1. for (initialization; condition; update)  
2. {  
3.     if (expression)  
4.     {  
5.         continue; //continue statement  
6.     }  
7.     // Code to be executed if 'continue' is not hit  
8. }  

**Example:**

Let us take an example to illustrate the Continue statement in the for loop in C#.

### Example

[](https://www.tpointtech.com/c-sharp-continue-statement#)[](https://www.tpointtech.com/c-sharp-continue-statement#)[](https://www.tpointtech.com/c-sharp-continue-statement#)

1. using System;    
2. public class ContinueExample    
3.     {    
4.       public static void Main(string[] args)    
5.       {    
6.          for(int i=1;i<=10;i++) //for loop body  
7. {      
8.     //condition to continue statement  
9.             if(i==5){      
10.                 continue;      
11.             }      
12.             Console.WriteLine(i);  //it prints the value of i    
13.         }      
14.       }    
15.    }   

**Output:**

1
2
3
4
6
7
8
9
10

**Explanation:**

In this example, we prints 1 through 10, with the exception of 5. The continue statement skips the printing of the value 5 by proceeding directly to the next iteration. The program shows how to bypass certain iterations with the use of the continue statement.

### 2. Continue Statement with while Loop in C#:

In C# programming, if a continue statement is used in a [while loop](https://www.tpointtech.com/c-sharp-while-loop), it jumps the current iteration, and the control flow starts in the next iteration of the while loop.

**Syntax:**

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-continue-statement#)[](https://www.tpointtech.com/c-sharp-continue-statement#)[](https://www.tpointtech.com/c-sharp-continue-statement#)

1. while (condition)  
2. {  
3.     if (expression)  
4.     {  
5.         continue; // continue statement  
6.     }  
7.     // Code to be executed if 'continue' is not hit  
8. }  

**Example:**

Let us take an example to illustrate the continue statement with a while loop in C#.

### Example

[](https://www.tpointtech.com/c-sharp-continue-statement#)[](https://www.tpointtech.com/c-sharp-continue-statement#)[](https://www.tpointtech.com/c-sharp-continue-statement#)

1. using System;  
2. class Tpointtech  
3. {  
4.     static void Main()  
5.     {  
6.         int i = 0;          
7.         while (i < 6) // start while loop  
8.         {  
9.             i++;              
10.             if (i == 4) //continue condition  
11.             {  
12.                 continue;    
13.             }             
14.             Console.WriteLine(i); //print the value of i  
15.         }  
16.     }  
17. }  

**Output:**

1
2
3
5
6

**Explanation:**

In this example, we have taken an integer value i and initialize value 0. After that, while loop start in the program and check the given condition. When condition (1 ==4) met in the program, continue statement jumps the loop condition to next iteration.

### 3. Continue Statement with do-while Loop in C#:

In C# programming, when a continue statement comes in the [do-while loop](https://www.tpointtech.com/c-sharp-do-while-loop), the control flow jumps directly to the next loop, and skips all the code that is remaining in the loop body.

**Syntax:**

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-continue-statement#)[](https://www.tpointtech.com/c-sharp-continue-statement#)[](https://www.tpointtech.com/c-sharp-continue-statement#)

1. do  
2. {  
3.     if (expression) //condition statement  
4.     {  
5.         continue; // continue statement  
6.     }  
7.     // Code to be executed if 'continue' is not hit  
8. } while (condition);  

**Example:**

Let us take an example to illustrate the continue statement in a [do-while loop](https://www.tpointtech.com/c-sharp-do-while-loop) to find the odd numbers in C#

### Example

[](https://www.tpointtech.com/c-sharp-continue-statement#)[](https://www.tpointtech.com/c-sharp-continue-statement#)[](https://www.tpointtech.com/c-sharp-continue-statement#)

1. using System;  
2. class Tpointtech  
3. {  
4.     static void Main()  
5.     {  
6.         int num = 0;  
7.         Console.WriteLine("Odd numbers from 1 to 10:");  
8.         do  
9.         {  
10.             num++;              
11.             if (num % 2 == 0)  
12.             {  
13.                 continue;  
14.             }  
15.             Console.WriteLine(num);  
16.         } while (num < 10);  
17.     }  
18. }  

**Output:**

Odd numbers from 1 to 10:
1
3
5
7
9

### 4. Continue Statement with for-each loop in C#

In C#, the continue statement can also be utilized with a foreach loop to pass over the current iteration and proceed with the next element of the collection.

**Syntax:**

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-continue-statement#)[](https://www.tpointtech.com/c-sharp-continue-statement#)[](https://www.tpointtech.com/c-sharp-continue-statement#)

1. foreach (var item in collection)  
2. {  
3.     if (expression) //condition statement  
4.     {  
5.         continue; //continue statement  
6.     }  
7.     // Code to be executed if 'continue' is not hit  
8. }  

**Example:**

Let us take an example to illustrate the continue statement with for-each loop in C#.

### Example

[](https://www.tpointtech.com/c-sharp-continue-statement#)[](https://www.tpointtech.com/c-sharp-continue-statement#)[](https://www.tpointtech.com/c-sharp-continue-statement#)

1. using System;  
2. class Tpointtech  
3. {  
4.     static void Main()  
5.     {  
6.         int[] num = { 8, -5, 4, -1, 9, -3, 20 };  
7.         Console.WriteLine("Positive numbers in the array are:");  
8.         foreach (int i in num)  
9.         {  
10.             if (i < 0)  
11.             {  
12.                 continue;   
13.             }  
14.             Console.WriteLine(i);  
15.         }  
16.     }  
17. }  

**Output:**

Positive numbers in the array are:
8
4
9
20

### 5. Continue Statement with Inner Loop in C#

C# Continue Statement continues inner loop only if we use continue statement inside the inner loop.

**Syntax:**

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-continue-statement#)[](https://www.tpointtech.com/c-sharp-continue-statement#)[](https://www.tpointtech.com/c-sharp-continue-statement#)

1. for (int i = 0; i < outerLim; i++)  
2. {  
3.     for (int j = 0; j < innerLim; j++)  
4.     {  
5.         if (expression)  
6.         {  
7.             continue;  // it skips the current iteration  
8.         }  
9.         //Code to be executed  
10.     }  
11. }  

**Example:**

Let us take an example to illustrate the continue statement with for each loop in C#.

### Example

[](https://www.tpointtech.com/c-sharp-continue-statement#)[](https://www.tpointtech.com/c-sharp-continue-statement#)[](https://www.tpointtech.com/c-sharp-continue-statement#)

1. using System;    
2. public class ContinueExample    
3.     {    
4.       public static void Main(string[] args)  //main function  
5.       {    
6.           for(int i=1;i<=3;i++)  //for outer loop  
7. {        
8.                     for(int j=1;j<=3;j++) //for inner loop  
9. {        
10.                         if(i==2&&j==2){        
11.                             continue;        
12.                         }        
13.                         Console.WriteLine(i+" "+j); //print the value of i and j  
14.                     }        
15.             }        
16.       }    
17.  }   

**Output:**

1 1
1 2
1 3
2 1
2 3
3 1
3 2
3 3

## Key differences between Continue and Break Statement:

Several differences between continue and break statement in C#. Some of them are as follows:

|Continue Statement|Break Statement|
|---|---|
|It skips the remaining code in the current iteration and moves to the next iteration.|It exits the loop entirely, regardless of whether the condition is met or not.|
|The loop continues to execute the next iteration.|The loop is terminated immediately.|
|It moves control to the loop's update expression (for for loops) or condition check (for other loops).|It transfers control to the statement immediately after the loop.|
|It is used when we want to skip specific iterations but continue looping.|It is used when we want to terminate the loop early based on a condition.|

## Benefits of using Continue Statement:

Several benefits of using continue statement in C# are as follows:

1. It makes the code neater and faster when avoiding unnecessary operations.
2. It helps in minimizing nested if-else statements, enhancing readability.
3. It is most beneficial when used in filtering operations and data validation situations.