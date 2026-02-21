In Java, when you need a loop that executes at least once before checking a condition, the **do-while loop** is used, as it checks the condition after executing the loop body.

## What is do-while Loop in Java?

The Java **do-while loop** is used to iterate a part of the program repeatedly, until the specified condition is true. If the number of iteration is not fixed and you must have to execute the loop at least once, it is recommended to use a do-while loop.

Java do-while loop is called an **exit control loop**. Therefore, unlike while loop and for loop, the do-while check the condition at the end of loop body. The Java _do-while loop_ is executed at least once because condition is checked after loop body.

## Syntax of do-while Loop

It has the following syntax:

[](https://www.tpointtech.com/java-do-while-loop#)[](https://www.tpointtech.com/java-do-while-loop#)[](https://www.tpointtech.com/java-do-while-loop#)

1. do{    
2. //code to be executed / loop body  
3. //update statement   
4. }while (condition);    

**The different parts of do-while loop:**

**1. Condition:** It is an expression which is tested. If the condition is true, the loop body is executed and control goes to update expression. As soon as the condition becomes false, loop breaks automatically.

**i <=100**

**2. Update expression:** Every time the loop body is executed, the this expression increments or decrements loop variable.

**i++;**

#### Note: The do block is executed at least once, even if the condition is false.

## Flow chart of do-while loop

The given diagram demonstrate the working of do-while loop in Java.

![flowchart of do while loop in java](https://d2jdgazzki9vjm.cloudfront.net/core/images/java-do-while-loop.png)

## Examples of do-while Loop

Here, we are going to take several examples to demonstrate the do-while loop in Java.

### Example 1: Printing Numbers from 1 to 10

In the below example, we print integer values from 1 to 10. Unlike the for loop, we separately need to initialize and increment the variable used in the condition (here, i). Otherwise, the loop will execute infinitely.

### Example

[](https://www.tpointtech.com/java-do-while-loop#)[](https://www.tpointtech.com/java-do-while-loop#)[](https://www.tpointtech.com/java-do-while-loop#)

1. //Simple do-while example in Java  
2. public class Main {      
3. public static void main(String[] args) {    
4.     //initialization    
5.     int i=1;      
6.     //do-while loop  
7.     do{      
8.         System.out.println(i);      
9.     i++;      
10.     }while(i<=10);      
11. }      
12. }      

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

### Example 2: Finding Factorial of a Number

Let us take an example to find the factorial of a number using do-while loop in Java.

### Example

[](https://www.tpointtech.com/java-do-while-loop#)[](https://www.tpointtech.com/java-do-while-loop#)[](https://www.tpointtech.com/java-do-while-loop#)

1. // Java Program to print factorial of 5 using do-while loop  
2. public class Main {    
3.     public static void main(String[] args) {    
4.         int number = 5;    
5.         int factorial = 1;    
6.         int i = 1;  
7.         //Start a do-while loop   
8.         do {    
9.             // Multiply the current value of 'factorial' by 'i' and store the result back in 'factorial'.    
10.             factorial *= i; // This is equivalent to factorial = factorial * i;   
11.             i++;  
12.         } while( i <= number );   
13.         // Print the calculated factorial to the console.    
14.         System.out.println("Factorial of " + number + " is: " + factorial);    
15.     }    
16. }    

**Output:**

Factorial of 5 is: 120

## Java Infinitive do-while Loop

If you pass **true** in the do-while loop, it will be infinitive do-while loop.

### Syntax of Infinitive do-while Loop

It has the following syntax:

[](https://www.tpointtech.com/java-do-while-loop#)[](https://www.tpointtech.com/java-do-while-loop#)[](https://www.tpointtech.com/java-do-while-loop#)

1. do{  
2. //code to be executed  
3. }while(true);  

### Example 1: Java Infinitive do-while Loop

Let us take another example to demonstrate the working of infinitive do-while loop in Java.

[](https://www.tpointtech.com/java-do-while-loop#)[](https://www.tpointtech.com/java-do-while-loop#)[](https://www.tpointtech.com/java-do-while-loop#)

1. public class DoWhileExample2 {  
2. public static void main(String[] args) {  
3.     do{  
4.         System.out.println("infinitive do while loop");  
5.     }while(true);  
6. }  
7. }  

**Output:**

infinitive do while loop
infinitive do while loop
infinitive do while loop
ctrl+c

### Example 2: Java Infinitive do-while Loop

Let us take an example to demonstrate the working of infinitive do-while loop in Java.

[](https://www.tpointtech.com/java-do-while-loop#)[](https://www.tpointtech.com/java-do-while-loop#)[](https://www.tpointtech.com/java-do-while-loop#)

1. import java.util.Scanner;  
2. public class DoWhileLoop {  
3.     public static void main(String[] args) {  
4.         // Creating a Scanner object for reading input from the user  
5.         Scanner sc = new Scanner(System.in);  
6.         // Declare variables to store user input and the s of numbers  
7.         int n;  
8.         int s = 0;  
9.         int c = 0; // Variable to c the n of iterations  
10.         // Display a welcome message  
11.         System.out.println("Welcome to the Do-While Loop Program!");  
12.         // Start a do-while loop  
13.         do {  
14.             // Prompt the user to enter a n  
15.             System.out.print("Please enter the value of a and n (or -1 to exit): ");  
16.             // Read the n entered by the user  
17.             n = sc.nextInt();  
18.             // Check if the n is not equal to -1 (exit condition)  
19.             if (n != -1) {  
20.                 // Add the n to the s  
21.                 s += n;  
22.                 // Increment the c of iterations  
23.                 c++;  
24.             }  
25.             // Continue looping until the user enters -1  
26.         } while (n != -1);  
27.         // Display the s of the numbers entered  
28.         System.out.println("Sum of the numbers entered: " + s);  
29.         // Display the n of iterations (excluding the exit condition)  
30.         System.out.println("Number of iterations: " + c);  
31.         // Calculate and display the average of the numbers entered  
32.         double average = (double) s / c;  
33.         System.out.println("Average of the numbers entered: " + average);  
34.         // Close the Scanner object to release system resources  
35.         sc.close();  
36.     }  
37. }  

**Output:**

Welcome to the Do-While Loop Program!
Please enter the value of a and n (or -1 to exit): 5
Please enter a n (or -1 to exit): -1
Sum of the numbers entered: 5
Number of iterations: 1
Average of the numbers entered: 5.0