**For loops** in Java are a fundamental control structure used to repeat a block of code a specific number of times or iterate through a sequence of values. They are incredibly useful for tasks that require repetition, such as processing items in an array, generating repetitive output, or executing a block of code a predetermined number of times.

The Java _for loop_ is used to iterate a part of the program several times. If the number of iteration is **fixed**, it is recommended to use for loop.

There are the following three types of for loops in Java.

- Simple for Loop
- [For-each](https://www.tpointtech.com/for-each-loop) or Enhanced for Loop
- Labelled for Loop

## Java Simple for Loop

A simple for loop is the same as [C](https://www.tpointtech.com/c-programming-language-tutorial)/[C++](https://www.tpointtech.com/cpp-tutorial). We can initialize the [variable](https://www.tpointtech.com/java-variables), check condition and increment/decrement value. It consists of four parts:

1. **Initialization:** It is the initial condition which is executed once when the loop starts. Here, we can initialize the variable, or we can use an already initialized variable. It is an optional condition.
2. **Condition:** It is the second condition which is executed each time to test the condition of the loop. It continues execution until the condition is false. It must return boolean value either true or false. It is an optional condition.
3. **Increment/Decrement:** It increments or decrements the variable value. It is an optional condition.
4. **Statement:** The statement of the loop is executed each time until the second condition is false.

### Syntax of the for loop

It has the following syntax:

[](https://www.tpointtech.com/java-for-loop#)[](https://www.tpointtech.com/java-for-loop#)[](https://www.tpointtech.com/java-for-loop#)

1. for(initialization; condition; increment/decrement){    
2. //statement or code to be executed    
3. }    

### Flowchart of the for loop

The following flowchart shows the working of the for loop.

![for loop in java flowchart](https://d2jdgazzki9vjm.cloudfront.net/cpages/images/forloop.png)

### for Loop Example 1: Printing Numbers from 1 to 10

Let us take an example to demonstrate how to print numbers from 1 to 10 using the for loop in Java.

### Example

[](https://www.tpointtech.com/java-for-loop#)[](https://www.tpointtech.com/java-for-loop#)[](https://www.tpointtech.com/java-for-loop#)

1. //Java Program to demonstrate the example of for loop    
2. //which prints table of 1    
3. public class Main {    
4. public static void main(String[] args) {    
5.     //Code of Java for loop    
6.     for(int i=1;i<=10;i++){    
7.         System.out.println(i);    
8.     }    
9. }    
10. }    

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

### for Loop Example 2: Finding Factorial

Let us take another example to demonstrate how to find factorial of a number using the for loop.

### Example

[](https://www.tpointtech.com/java-for-loop#)[](https://www.tpointtech.com/java-for-loop#)[](https://www.tpointtech.com/java-for-loop#)

1. // Java Program to print factorial of 5   
2. public class Main {    
3.     public static void main(String[] args) {    
4.         // Declare an integer variable 'number' and initialize it to 5. This is the number whose factorial is to be calculated.    
5.         int number = 5;    
6.         // Declare an integer variable 'factorial' and initialize it to 1. This variable will hold the result of the factorial calculation.    
7.         int factorial = 1;    
8.         // Start a for loop with the loop variable 'i' initialized to 1.    

9.         for (int i = 1; i <= number; i++) {    
10.             // Multiply the current value of 'factorial' by 'i' and store the result back in 'factorial'.    
11.             factorial *= i; // This is equivalent to factorial = factorial * i;    
12.         }    
13.         // After the loop has completed, print the calculated factorial to the console.    
14.         System.out.println("Factorial of " + number + " is: " + factorial);    
15.     }    
16. }    

**Output:**

Factorial of 5 is: 120

## Java Nested for Loop

If we have a for loop inside the another loop, it is known as nested for loop. The inner loop executes completely whenever outer loop executes.

The structure allows us to perform complex iterations by running a for loop for each iteration of the outer for loop. Nested for loops are particularly useful when working with multi-dimensional data structures like arrays or when we need to perform operations that require multiple levels of looping, such as generating a matrix or table.

### Syntax of the Java Nested for Loop

It has the following syntax:

[](https://www.tpointtech.com/java-for-loop#)[](https://www.tpointtech.com/java-for-loop#)[](https://www.tpointtech.com/java-for-loop#)

1. for (initialization; termination; increment) {  
2.     // Outer loop block  
3.     for (initialization; termination; increment) {  
4.         // Inner loop block  
5.     }  
6. }  

### Nested for Loop Example 1: Demonstrating Loop inside Loop

Here, we are going to take an example to demonstrate the nested for loop in Java.

### Example

[](https://www.tpointtech.com/java-for-loop#)[](https://www.tpointtech.com/java-for-loop#)[](https://www.tpointtech.com/java-for-loop#)

1. //Java program to understand the use of nested for loop  
2. public class Main {    
3. public static void main(String[] args) {    
4.  //loop of i    
5.  for(int i=1;i<=3;i++){    
6.   //loop of j    
7.   for(int j=1;j<=3;j++){    
8.         System.out.println(i+" "+j);    
9.   }//end of i    
10.  }//end of j    
11. }    
12. }    

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

### Nested for Loop Example 2: Printing Left-Aligned Star Triangle

In this example, we are going to print the left-aligned star triangle using the nested for loop.

### Example

[](https://www.tpointtech.com/java-for-loop#)[](https://www.tpointtech.com/java-for-loop#)[](https://www.tpointtech.com/java-for-loop#)

1. //Java program to print pyramid using for loop  
2. public class Main {    
3.  public static void main(String[] args) {    
4.   for(int i=1;i<=5;i++){    
5.    for(int j=1;j<=i;j++){    
6.         System.out.print("* ");    
7.    }    
8.    System.out.println();//new line    
9.   }    
10.  }    
11. }    

**Output:**

*
* *
* * *
* * * *
* * * * *

### Nested for Loop Example 3: Printing Inverted Right-Angled Star Pyramid

In this example, we are going to print the inverted right-aligned star triangle using the nested for loop.

### Example

[](https://www.tpointtech.com/java-for-loop#)[](https://www.tpointtech.com/java-for-loop#)[](https://www.tpointtech.com/java-for-loop#)

1. //Java program to print pyramid or star pattern using for loop  
2. public class Main {    
3.  public static void main(String[] args) {    
4.   int term=6;    
5.   for(int i=1;i<=term;i++){    
6.    for(int j=term;j>=i;j--){    
7.         System.out.print("* ");    
8.    }    
9.   System.out.println();//new line    
10.   }    
11.  }    
12. }    

**Output:**

* * * * * *
* * * * *
* * * *
* * *
* *
*

## Java for-each Loop

The for-each loop is used to traverse array or collection in Java. It is easier to use than simple for loop because we don't need to increment value and use subscript notation.

It works on the basis of elements and not the index. It returns element one by one in the defined variable.

### Syntax of the Java for-each Loop

It has the following syntax:

[](https://www.tpointtech.com/java-for-loop#)[](https://www.tpointtech.com/java-for-loop#)[](https://www.tpointtech.com/java-for-loop#)

1. for(data_type variable : array_name){    
2. //code to be executed    
3. }    

### for each Loop Example: Printing Array Elements

Let us take an example to demonstrate how to print array elements in Java.

### Example

[](https://www.tpointtech.com/java-for-loop#)[](https://www.tpointtech.com/java-for-loop#)[](https://www.tpointtech.com/java-for-loop#)

1. //Java For-each loop example which prints the    
2. //elements of the array    
3. public class Main {    
4. public static void main(String[] args) {    
5.     //Declaring an array    
6.     int arr[]={12,23,44,56,78};    
7.     //Printing array using for-each loop    
8.     for(int i:arr){    
9.         System.out.println(i);    
10.     }    
11. }    
12. }    

**Output:**

12
23
44
56
78

## Java Labelled for Loop

A labelled for loop in Java is a for loop that has been assigned a label. Labels in Java provide a way to identify a block of code, making it possible to break out of or continue an outer loop from within a nested loop. This feature is particularly useful when working with nested loops and we need to control the flow of the outer loop from within an inner loop. Labels enhance the control flow in complex looping structures, allowing for more precise and flexible loop management.

We can have a name of each Java for loop. To do so, we use label before the for loop. It is useful while using the nested for loop as we can break/continue specific for loop.

#### Note: The break and continue keywords breaks or continues the innermost for loop respectively.

### Syntax of the Java Labelled for Loop

It has the following syntax:

[](https://www.tpointtech.com/java-for-loop#)[](https://www.tpointtech.com/java-for-loop#)[](https://www.tpointtech.com/java-for-loop#)

1. labelname:    
2. for(initialization; condition; increment/decrement){    
3. //code to be executed    
4. }    

### Example 1:

Let us take an example to demonstrate the Java labelled for loop.

### Example

[](https://www.tpointtech.com/java-for-loop#)[](https://www.tpointtech.com/java-for-loop#)[](https://www.tpointtech.com/java-for-loop#)

1. //A Java program to demonstrate the use of labeled for loop    
2. public class Main {    
3. public static void main(String[] args) {    
4.     //Using Label for outer and for loop    
5.     aa:    
6.         for(int i=1;i<=3;i++){    
7.             bb:    
8.                 for(int j=1;j<=3;j++){    
9.                     if(i==2&&j==2){    
10.                         break aa;    
11.                     }    
12.                     System.out.println(i+" "+j);    
13.                 }    
14.         }    
15. }    
16. }    

**Output:**

1 1
1 2
1 3
2 1

### Example 2:

If you use **break bb;**, it will break inner loop only which is the default behaviour of any loop.

### Example

[](https://www.tpointtech.com/java-for-loop#)[](https://www.tpointtech.com/java-for-loop#)[](https://www.tpointtech.com/java-for-loop#)

1. public class Main {    
2. public static void main(String[] args) {    
3.     aa:    
4.         for(int i=1;i<=3;i++){    
5.             bb:    
6.                 for(int j=1;j<=3;j++){    
7.                     if(i==2&&j==2){    
8.                         break bb;    
9.                     }    
10.                     System.out.println(i+" "+j);    
11.                 }    
12.         }    
13. }    
14. }    

**Output:**

1 1
1 2
1 3
2 1
3 1
3 2
3 3

## Java Infinitive for Loop

An infinitive for loop in Java is a loop that has no termination condition, or the condition is always true, causing the loop to run indefinitely until the program is manually terminated or interrupted by a break statement or an exception. This type of loop is used when you want to create a continuous loop that keeps running until an external condition or user interaction dictates otherwise.

If we use a pair of semicolons (;;) in the for loop, it will be infinitive for loop.

### Syntax of the Java Infinitive for Loop

It has the following syntax:

[](https://www.tpointtech.com/java-for-loop#)[](https://www.tpointtech.com/java-for-loop#)[](https://www.tpointtech.com/java-for-loop#)

1. for(;;){  
2. //code to be executed  
3. }  

### Example: Java infinitive for Loop

Let us take an example to demonstrate the java infinitive for loop.

[](https://www.tpointtech.com/java-for-loop#)[](https://www.tpointtech.com/java-for-loop#)[](https://www.tpointtech.com/java-for-loop#)

1. //Java program to demonstrate the use of infinite for loop  
2. //which prints an statement  
3. public class ForExample {  
4. public static void main(String[] args) {  
5.     //Using no condition in for loop  
6.     for(;;){  
7.         System.out.println("infinitive loop");  
8.     }  
9. }  
10. }  

**Output:**

infinitive loop
infinitive loop
infinitive loop
infinitive loop
infinitive loop

Now, we need to press Ctrl+C to exit from the program.

## Java for Loop vs while Loop vs do-while Loop

There are several differences between Java for loop, while loop, and do-while loop. Some of them are as follows:

|Comparison|for loop|while loop|do-while loop|
|---|---|---|---|
|Introduction|The Java for loop is a control flow statement that iterates a part of the [programs](https://www.tpointtech.com/java-programs) multiple times.|The Java while loop is a control flow statement that executes a part of the programs repeatedly on the basis of given boolean condition.|The Java do while loop is a control flow statement that executes a part of the programs at least once and the further execution depends upon the given boolean condition.|
|When to use|If the number of iteration is fixed, it is recommended to use for loop.|If the number of iteration is not fixed, it is recommended to use while loop.|If the number of iteration is not fixed and you must have to execute the loop at least once, it is recommended to use the do-while loop.|
|Syntax|for(init;condition;incr/decr){  <br>// code to be executed  <br>}|while(condition){  <br>//code to be executed  <br>}|do{  <br>//code to be executed  <br>}while(condition);|
|Example|//for loop  <br>for(int i=1;i<=10;i++){  <br>System.out.println(i);  <br>}|//while loop  <br>int i=1;  <br>while(i<=10){  <br>System.out.println(i);  <br>i++;  <br>}|//do-while loop  <br>int i=1;  <br>do{  <br>System.out.println(i);  <br>i++;  <br>}while(i<=10);|
|Syntax for infinitive loop|for(;;){  <br>//code to be executed  <br>}|while(true){  <br>//code to be executed  <br>}|do{  <br>//code to be executed  <br>}while(true);|