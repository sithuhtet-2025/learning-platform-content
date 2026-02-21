In programming, loops play a pivotal role in iterating over a set of statements repeatedly until a specific condition is met. One such loop in [Java](https://www.tpointtech.com/java-tutorial) is the 'while' loop, known for its simplicity and versatility.

## What Is while Loop in Java?

**The Java while loop** is used to iterate a part of the program repeatedly until the specified Boolean condition is true. As soon as the Boolean condition becomes false, the loop automatically stops.

The while loop is considered as a repeating if statement. If the number of iteration is not fixed, it is recommended to use the while loop.

### Syntax pf the Java While Loop

It has the following syntax:

[](https://www.tpointtech.com/java-while-loop#)[](https://www.tpointtech.com/java-while-loop#)[](https://www.tpointtech.com/java-while-loop#)

1. while (condition){      
2. //code to be executed     
3. Increment / decrement statement    
4. }      

Here, condition is a boolean expression that determines whether the loop should continue iterating or not. The statements within the curly braces are executed repeatedly as long as the condition evaluates to true.

### Parts of while Loop

The different parts of while loop are as follows:

**1. Condition:** It is an expression which is tested. If the condition is true, the loop body is executed and control goes to update expression. When the condition becomes false, we exit the while loop.

**Example:**

[](https://www.tpointtech.com/java-while-loop#)[](https://www.tpointtech.com/java-while-loop#)[](https://www.tpointtech.com/java-while-loop#)

1. i <=100  

**2. Update Expression:** Every time the loop body is executed, this expression increments or decrements loop variable.

**Example:**

[](https://www.tpointtech.com/java-while-loop#)[](https://www.tpointtech.com/java-while-loop#)[](https://www.tpointtech.com/java-while-loop#)

1. i++;  

## while Loop Example

This example shows the basic usage of a while loop in Java. Here, we want to print numbers from 1 to 5:

[](https://www.tpointtech.com/java-while-loop#)[](https://www.tpointtech.com/java-while-loop#)[](https://www.tpointtech.com/java-while-loop#)

1. int i = 1;  
2. while (i <= 5) {  
3.     System.out.println(i);  
4.     i++;  
5. }  

**Explanation:**

In this example, the loop starts with the variable i initialized to 1. The condition i <= 5 is checked before each iteration, and the loop continues as long as the condition is true. Inside the loop, the value of i is printed and then increased by 1, which prevents the loop from running infinitely.

## Java While Loop Flowchart

Here, the important thing about while loop is that, sometimes it may not even execute. If the condition to be tested results into false, the loop body is skipped and first statement after the while loop will be executed.

![flowchart of java while loop](https://d2jdgazzki9vjm.cloudfront.net/core/images/java-while-loop.png)

## More Examples on while Loop

Here, we are going to discuss several examples to demonstrate the while loop in Java.

### Example 1: Printing Numbers from 1 to 10

In the following example, we print integer values from 1 to 10. Unlike the for loop, we separately need to initialize and increment the variable used in the condition (here, i). Otherwise, the loop will execute infinitely.

### Example

[](https://www.tpointtech.com/java-while-loop#)[](https://www.tpointtech.com/java-while-loop#)[](https://www.tpointtech.com/java-while-loop#)

1. public class Main {    
2. public static void main(String[] args) {    
3.     int i=1;    
4.     while(i<=10){    
5.         System.out.println(i);    
6.     i++;    
7.     }    
8. }    
9. }    

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

Let us take an example to demonstrate how to find the factorial of a number using while loop in Java.

### Example

[](https://www.tpointtech.com/java-while-loop#)[](https://www.tpointtech.com/java-while-loop#)[](https://www.tpointtech.com/java-while-loop#)

1. // Java Program to print factorial of 5 using while loop  
2. public class Main {    
3.     public static void main(String[] args) {    
4.         // Declare a variable to 5. This is the number whose factorial is to be calculated.    
5.         int number = 5;    
6.         // Declare a variable 'factorial' and initialize it to 1. This variable will hold the result of the factorial calculation.    
7.         int factorial = 1;    
8.         // Declare a variable 'i' and initialize it to 1.    
9.         int i = 1;  
10.         //Start a while loop   
11.         while( i <= number ) {    
12.             // Multiply the current value of 'factorial' by 'i' and store the result back in 'factorial'.    
13.             factorial *= i; // This is equivalent to factorial = factorial * i;   
14.             i++;  
15.         }    
16.         // Print the calculated factorial to the console.    
17.         System.out.println("Factorial of " + number + " is: " + factorial);    
18.     }    
19. }    

**Output:**

Factorial of 5 is: 120

## Java Nested While Loop

A while loop inside the while loop is called nested while loop in Java. The basic syntax of nested while loop is given below:

### Syntax of Java Nested While Loop

It has the following syntax:

[](https://www.tpointtech.com/java-while-loop#)[](https://www.tpointtech.com/java-while-loop#)[](https://www.tpointtech.com/java-while-loop#)

1. while (condition){      
2.  //code to be executed     
3.  while (condition){      
4.   //code to be executed     
5.   Increment / decrement statement    
6.  }  
7.  Increment / decrement statement    
8. }      

### Example 1: Printing Row and Column Values

This example demonstrates the use of a nested while loop in Java, where the inner loop runs completely for each iteration of the outer loop.

### Example

[](https://www.tpointtech.com/java-while-loop#)[](https://www.tpointtech.com/java-while-loop#)[](https://www.tpointtech.com/java-while-loop#)

1. //Java Program to use nested while loop in Java  
2. public class Main {    
3. public static void main(String[] args) {    
4.     int i=1;  
5.     //outer while loop  
6.     while(i<=3){    
7.         //inner while loop  
8.         int j=1;  
9.         while(j<=5){  
10.             System.out.println(i+" "+j);    
11.             j++;    
12.         }    
13.     i++;  
14.     }  
15. }    
16. }    

**Output:**

1 1
1 2
1 3
1 4
1 5
2 1
2 2
2 3
2 4
2 5
3 1
3 2
3 3
3 4
3 5

### Example 2: Printing Multiplication Table

This program uses a nested while loop to print the multiplication table from 1 to 10 in a structured format.

### Example

[](https://www.tpointtech.com/java-while-loop#)[](https://www.tpointtech.com/java-while-loop#)[](https://www.tpointtech.com/java-while-loop#)

1. //Java Program to print multiplication table using while loop in Java  
2. public class Main {    
3. public static void main(String[] args) {    
4.     int i=1;  
5.     //outer while loop  
6.     while(i<=10){    
7.         //inner while loop  
8.         int j=1;  
9.         while(j<=10){  
10.             System.out.print(i*j+" ");    
11.             j++;    
12.         }    
13.         System.out.println();  
14.     i++;  
15.     }  
16. }    
17. }    

**Output:**

1 2 3 4 5 6 7 8 9 10
2 4 6 8 10 12 14 16 18 20
3 6 9 12 15 18 21 24 27 30
4 8 12 16 20 24 28 32 36 40
5 10 15 20 25 30 35 40 45 50
6 12 18 24 30 36 42 48 54 60
7 14 21 28 35 42 49 56 63 70
8 16 24 32 40 48 56 64 72 80
9 18 27 36 45 54 63 72 81 90
10 20 30 40 50 60 70 80 90 100

## Java Infinitive while Loop

While loops can inadvertently become infinite if the condition always evaluates to true. For instance: If we pass true in the while loop, it will be infinitive while loop.

### Syntax of Java infinitive while Loop

It has the following syntax:

[](https://www.tpointtech.com/java-while-loop#)[](https://www.tpointtech.com/java-while-loop#)[](https://www.tpointtech.com/java-while-loop#)

1. while(true){  
2. //code to be executed  
3. }  

This loop will continue indefinitely because the condition true is always true. Therefore, it is crucial to ensure that the condition in a while loop eventually becomes false to exit the loop.

### Example: Java Inifinitive while Loop

Let us take an example to demonstrate the Java infinitive while Loop.

[](https://www.tpointtech.com/java-while-loop#)[](https://www.tpointtech.com/java-while-loop#)[](https://www.tpointtech.com/java-while-loop#)

1. public class WhileExample2 {    
2. public static void main(String[] args) {   
3.  // setting the infinite while loop by passing true to the condition  
4.     while(true){    
5.         System.out.println("infinitive while loop");    
6.     }    
7. }    
8. }    

**Output:**

infinitive while loop
infinitive while loop
infinitive while loop
infinitive while loop
infinitive while loop
ctrl+c

## Preventing Infinite Loops

To prevent infinite loops, it is essential to incorporate mechanisms that modify the loop's condition within the loop block. For instance, using a variable to control the loop:

[](https://www.tpointtech.com/java-while-loop#)[](https://www.tpointtech.com/java-while-loop#)[](https://www.tpointtech.com/java-while-loop#)

1. int count = 0;  
2. while (count < 5) {  
3.     System.out.println("Count: " + count);  
4.     count++;  
5. }  

In this example, the loop will execute five times, incrementing the count variable with each iteration until it reaches 5, satisfying the condition and ending the loop.

### Example: prevent infinite loops with a while loop

The following example demonstrates how to prevent infinite loops with a while loop:

[](https://www.tpointtech.com/java-while-loop#)[](https://www.tpointtech.com/java-while-loop#)[](https://www.tpointtech.com/java-while-loop#)

1. public class PreventingInfiniteLoop {  
2.     public static void main(String[] args) {  
3.         int count = 0;  
4.         while (count < 5) {  
5.             System.out.println("Count: " + count);  
6.             count++;  
7.         }  
8.     }  
9. }  

**Output:**

Count: 0
Count: 1
Count: 2
Count: 3
Count: 4

The while loop in Java offers a versatile mechanism for executing repetitive tasks based on a condition. Its simplicity and flexibility make it a valuable tool for various programming scenarios, from simple iteration to complex input validation. However, care must be taken to prevent infinite loops by ensuring that the loop's condition eventually evaluates to false. Understanding and mastering the while loop is essential for any Java programmer aiming to write efficient and reliable code.