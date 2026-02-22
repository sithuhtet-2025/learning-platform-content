
## What is Recursion in Java?

Recursion is a process in which a method calls itself to solve a problem. The method that calls itself is known as a **recursive method**.

A **recursive method** works by dividing a problem into smaller parts and solving each part using the same method logic. Every recursive method must have a **base condition**, which stops the recursive calls and prevents infinite execution.

## Syntax of Recursion

Here is the syntax to write a recursive method:

[](https://www.tpointtech.com/recursion-in-java#)[](https://www.tpointtech.com/recursion-in-java#)[](https://www.tpointtech.com/recursion-in-java#)

1. returnType methodName(parameters) {  
2.     // Base condition  
3.     if (condition) {  
4.         return value;  
5.     }  

6.     // Recursive call  
7.     return methodName(modifiedParameters);  
8. }  

> **Note:** Without a base condition, recursion can cause a StackOverflowError.

## How Recursion Works?

Recursion works using two main cases: the **base case** and the **recursive case**, which are explained below:

### 1. Base Case

The **base case** acts as the stopping condition for recursion. It is important because, without a base case, the recursive method would continue calling itself indefinitely that will lead to a **StackOverflowError**. The base case specifies the condition under which the recursion terminates.

### 2. Recursive Case

The **recursive case** is the part of the method where it calls itself with modified arguments. These arguments move the problem closer to the base case. With each recursive call, the problem size is reduced until the base case is reached.

## Examples of Recursion

Practice the following programs to understand the concept of recursion in Java.

### Example 1: Sum of First N Natural Numbers Using Recursion

The following program demonstrates how recursion is used to calculate the sum of the first N natural numbers.

[](https://www.tpointtech.com/recursion-in-java#)[](https://www.tpointtech.com/recursion-in-java#)[](https://www.tpointtech.com/recursion-in-java#)

1. class SumExample {    
2.     // Recursive function to calculate the sum of first 'n' natural numbers    
3.     public static int sum(int n) {    
4.         // Base case: If n is 0, return 0 (base case)    
5.         if (n == 0)    
6.             return 0;    
7.         else    
8.  return n + sum(n - 1);   
9. // Recursive case: If n is not 0, recursively call the sum function with n-1 and add it to n   
10.     }    
11. }  
12. public class Main{  
13.  public static void main(String[] args) {    
14.     int num = 5; // Number of natural numbers to sum    
15.     // Calculate sum of first 'num' natural numbers using recursive sum function    
16.     int result = SumExample.sum(num);  
17.     // Print the result    
18.     System.out.println("Sum of first " + num + " natural numbers is: " + result);    
19.  }    
20. }    

**Output:**

Sum of first 5 natural numbers is: 15

In this example, if (n == 0) is the base case. When n becomes 0, the recursion stops.

### Example 2: Recursive Method Calling Itself Infinite Times

The following program demonstrates a recursive method that calls itself without a base case, resulting in infinite recursion.

[](https://www.tpointtech.com/recursion-in-java#)[](https://www.tpointtech.com/recursion-in-java#)[](https://www.tpointtech.com/recursion-in-java#)

1. class RecursionExample {  
2.     // Recursive function p() which prints "hello" and calls itself indefinitely  
3.     static void p() {  
4.         System.out.println("hello"); // Print "hello"  
5.         p(); // Recursive call to itself  
6.     }  
7. }  
8. public class Main{  
9.     public static void main(String[] args) {  
10.         RecursionExample.p(); // Initial call to p() from the main method  
11.     }  
12. }  

**Output:**

hello
hello
...
java.lang.StackOverflowError

### Example 3: Recursive Method Executed Finite Times

The following program demonstrates recursion that runs a finite number of times using a base condition.

[](https://www.tpointtech.com/recursion-in-java#)[](https://www.tpointtech.com/recursion-in-java#)[](https://www.tpointtech.com/recursion-in-java#)

1. class RecursionExample {    
2.     static int count = 0; // Static variable to keep track of the count    
3.     // Recursive method p() which increments count, prints "hello" along with the count, and calls itself recursively    
4.     static void p() {    
5.         count++; // Increment the count    
6.         // Check if count is less than or equal to 5    
7.         if (count <= 5) {    
8.             System.out.println("hello " + count); // Print "hello" along with the current count    
9.             p(); // Recursive call to itself    
10.         }    
11.     }    
12. }  
13. public class Main{  
14.     public static void main(String[] args) {    
15.         RecursionExample.p(); // Initial call to the p() method from the main method    
16.     }    
17. }  

**Output:**

hello 1
hello 2
hello 3
hello 4
hello 5

### Example 4: Factorial of a Number Using Recursion

The following program demonstrates how recursion is used to calculate the factorial of a number.

[](https://www.tpointtech.com/recursion-in-java#)[](https://www.tpointtech.com/recursion-in-java#)[](https://www.tpointtech.com/recursion-in-java#)

1. class FactorialExample {    
2.     // Recursive function to calculate the factorial of a non-negative integer 'n'    
3.     public static int factorial(int n) {    
4.         // Base case: If n is 0 or 1, factorial is 1    
5.         if (n == 0 || n == 1)    
6.             return 1;    
7.         // Recursive case: If n is greater than 1, recursively call factorial function with n-1 and multiply it with n    
8.         else    
9.             return n * factorial(n - 1);    
10.     }    
11. }  
12. public class Main{  
13.     public static void main(String[] args) {    
14.         int num = 5; // Number for which factorial is to be calculated    
15.         // Calculate factorial of 'num' using recursive factorial function    
16.         int result = FactorialExample.factorial(num);    
17.         // Print the result    
18.         System.out.println("Factorial of " + num + " is: " + result);    
19.     }    
20. }    

**Output:**

Factorial of 5 is: 120

**Working of above program:**

factorial(5)
factorial(4)
factorial(3)
factorial(2)
factorial(1)
return 1
return 2*1 = 2
return 3*2 = 6
return 4*6 = 24
return 5*24 = 120

### Example 5: Fibonacci Series Using Recursion

The following program demonstrates how to generate a Fibonacci series using recursion.

[](https://www.tpointtech.com/recursion-in-java#)[](https://www.tpointtech.com/recursion-in-java#)[](https://www.tpointtech.com/recursion-in-java#)

1. class F{    
2.     static int n1=0,n2=1,n3=0;        
3.      static void printFibo(int count){        
4.         if(count>0){        
5.              n3 = n1 + n2;        
6.              n1 = n2;        
7.              n2 = n3;        
8.              System.out.print(" "+n3);       
9.              printFibo(count-1);        
10.          }        
11.      }          
12. }  
13. public class Main{  
14.  public static void main(String[] args) {    
15.     int count=15;        
16.     System.out.print(F.n1+" "+F.n2);//printing 0 and 1        
17.     F.printFibo(count-2);//n-2 because 2 numbers are already printed       
18.  }    
19. }    

**Output:**

0 1 1 2 3 5 8 13 21 34 55 89 144 233 377

## Stack Overflow Error in Recursion

A **Stack Overflow Error** is a runtime error that occurs when a program exceeds the size of the call stack due to excessive recursive method calls. This usually happens when a recursive function does not have a proper termination condition or when the recursion depth becomes too large.

For example, if you try to calculate the factorial of a very large number, the program may throw a stack overflow error because each recursive call consumes stack memory. Similarly, calculating the factorial of a negative number without proper validation can also lead to infinite recursion and cause a stack overflow error.

## How to Avoid Stack Overflow Error in Recursion?

To prevent a stack overflow error, follow the guidelines given below:

- **Ensure a Proper Base Case**  
    Always define a correct base case that eventually stops the recursion. In the factorial example, the base case occurs when n is 0 or 1.
- **Limit Recursion Depth**  
    Avoid deep recursion when possible. For problems that require a large number of recursive calls, consider using an iterative approach instead.
- **Optimize Recursion**  
    Recursive logic can sometimes be optimized to reduce stack usage. Techniques such as tail recursion help minimize the number of stack frames, and some compilers can optimize tail-recursive calls into iterative forms.

For example, here is the factorial function with an additional check to prevent negative numbers:

### Example

[](https://www.tpointtech.com/recursion-in-java#)[](https://www.tpointtech.com/recursion-in-java#)[](https://www.tpointtech.com/recursion-in-java#)

1. class FactorialExample {    
2.     // Recursive function to calculate the factorial of a non-negative integer 'n'    
3.     public static int factorial(int n) {    
4.         // Base case: if n is negative, return an error code    
5.         if (n < 0)    
6.             return -1; // Error code for invalid input    
7.         // Base case: if n is 0 or 1, factorial is 1    
8.         else if (n == 0 || n == 1)    
9.             return 1;    
10.         // Recursive case: if n is greater than 1, recursively call factorial function with n-1 and multiply it with n    
11.         else    
12.             return n * factorial(n - 1);    
13.     }    
14. }  
15. public class Main{  
16.     public static void main(String[] args) {    
17.         int num = 5; // Number for which factorial is to be calculated    
18.         // Calculate factorial of 'num' using recursive factorial function    
19.         int result = FactorialExample.factorial(num);    
20.         // Print the result    
21.         System.out.println("Factorial of " + num + " is: " + result);    
22.     }    
23. }    

**Output:**

Factorial of 5 is: 120

## Memory Allocation During Recursion

In recursion, memory is allocated to function calls on the program's call stack. Each time a function is called, a new stack frame is created and pushed onto the call stack. This stack frame contains information such as function parameters, local variables, return address, and other necessary data for executing the function.

When a function returns, its stack frame is popped off the call stack, releasing the memory allocated to it. This process continues until the initial function call (usually main() in Java) completes, at which point the call stack becomes empty.

Let's break down how memory allocation works during recursion:

**Initial Function Call:**

- When a function is called for the first time, its parameters and local variables are allocated memory within a stack frame.
- The return address, which indicates where to return after the function completes, is also stored in the stack frame.
- If the function calls itself recursively, a new stack frame is created for each recursive call.

**Recursive Calls:**

- Each recursive call results in the creation of a new stack frame.
- The parameters and local variables of each recursive call are stored in their respective stack frames.
- As the recursion progresses, the call stack grows deeper, with each function call adding a new stack frame on top of the previous one.

**Base Case and Returning:**

- When the base case (i.e., the termination condition of the recursion) is reached, the function begins to return.
- As each function returns, its stack frame is popped off the call stack, freeing up the memory allocated to it.
- The return value of each function call is typically used in the calculation of the previous function call's result, until the initial function call returns the final result.

**Stack Overflow:**

- If the depth of recursion becomes too large, the call stack may run out of memory, leading to a stack overflow error.
- This typically happens when there are too many nested function calls and the call stack exceeds its maximum size.

### Example

Let’s consider the following example and understand the concept of memory allocation during recursion:

[](https://www.tpointtech.com/recursion-in-java#)[](https://www.tpointtech.com/recursion-in-java#)[](https://www.tpointtech.com/recursion-in-java#)

1. public class FactorialExample {  
2.     public static int factorial(int n) {  
3.         // Base case  
4.         if (n == 0 || n == 1)  
5.             return 1;  
6.         // Recursive case  
7.         else  
8.             return n * factorial(n - 1);  
9.     }  
10.     public static void main(String[] args) {  
11.         int result = factorial(5);  
12.         System.out.println("Factorial of 5 is: " + result);  
13.     }  
14. }  

**Output:**

Factorial of 5 is: 120

**Explanation:**

In this example, when factorial(5) is called:

**Initial Call (factorial(5)):**

- A stack frame is created for the initial call to factorial(5).
- Inside this stack frame, the value of n is set to 5, and other necessary information, such as the return address, is stored.

**First Recursive Call (factorial(4)):**

- Upon encountering the recursive call factorial(n - 1), a new stack frame is created for factorial(4).
- This stack frame contains its own copy of the parameter n, which is set to 4.
- The call stack now contains two stack frames: one for factorial(5) and one for factorial(4).

**Subsequent Recursive Calls:**

- The process repeats as more recursive calls are made, each resulting in the creation of a new stack frame with its own copy of the parameter n.
- Each stack frame remains on the call stack until its corresponding function call completes.

**Base Case and Returning:**

- Eventually, the base case (n == 0 or n == 1) is reached, and the recursion starts to unwind.
- As each function call returns, its stack frame is removed from the call stack, freeing up memory.
- The return values of the recursive calls are used to calculate the final result.

**Final Result:**

- After all recursive calls have returned, the initial call to factorial(5) obtains the final result.
- Once the main function completes, the call stack becomes empty, and all memory allocated to the function calls is released.

### Advantages of Recursion

Recursion makes code simpler, more readable, and closely matches the natural structure of problems. It promotes modularity, reusability, and works well for mathematical computations and tree-like data structures binary trees, graphs, and linked lists.

### Disadvantages of Recursion

Recursion can be slower and memory-intensive due to multiple function calls that may cause stack overflow if too deep. It is harder to debug, and may not scale well for very large inputs.