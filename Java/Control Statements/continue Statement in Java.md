
The continue statement is used in loop control structure when you need to jump to the next iteration of the loop immediately. It can be used with for loop or while loop.

## How to continue Statement Works?

The Java continue statement is used to continue the loop. It continues the current flow of the program and skips the remaining code at the specified condition. In case of an inner loop, it continues the inner loop only. Unlike the break statement, continue only interrupts the ongoing iteration and resumes control at the beginning of the next iteration.

## Loops Supported by the continue Statement

We can use Java continue statements in all types of loops, such as [for loops](https://www.tpointtech.com/java-for-loop), [while loops](https://www.tpointtech.com/java-while-loop), and [do-while loops](https://www.tpointtech.com/java-do-while-loop).

## Syntax of continue Statement

It has the following syntax:

[](https://www.tpointtech.com/java-continue#)[](https://www.tpointtech.com/java-continue#)[](https://www.tpointtech.com/java-continue#)

1. jump-statement;      
2. continue;     

When executed, continue causes the loop to skip the remaining code in the current iteration and immediately proceed to the next iteration. In the case of nested loops, continue affects only the innermost loop.

## Example of continue Statement

The following example demonstrates the use of the continue statement inside a for loop. When the value of i becomes 5, the continue statement skips the current iteration. As a result, all numbers from 1 to 10 are printed except 5.

### Example

[](https://www.tpointtech.com/java-continue#)[](https://www.tpointtech.com/java-continue#)[](https://www.tpointtech.com/java-continue#)

1. public class Main {  
2.     public static void main(String[] args) {  
3.         // for loop  
4.         for (int i = 1; i <= 10; i++) {  
5.             if (i == 5) {  
6.                 // using continue statement  
7.                 continue;// it will skip the rest statement  
8.             }  
9.             System.out.println(i);  
10.         }  
11.     }  
12. }  

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

## Java continue Statement with Inner Loop

It continues the inner loop only if we use the continue statement inside the inner loop.

The following example illustrates the use of the **continue statement inside an inner loop**. When the condition i == 2 and j == 2 is met, the continue statement skips that iteration of the inner loop. The remaining iterations continue normally, so all pairs are printed except 2 2.

### Example

[](https://www.tpointtech.com/java-continue#)[](https://www.tpointtech.com/java-continue#)[](https://www.tpointtech.com/java-continue#)

1. public class Main {  
2.     public static void main(String[] args) {  
3.         // outer loop  
4.         for (int i = 1; i <= 3; i++) {  
5.             // inner loop  
6.             for (int j = 1; j <= 3; j++) {  
7.                 if (i == 2 && j == 2) {  
8.                     // using continue statement inside inner loop  
9.                     continue;  
10.                 }  
11.                 System.out.println(i + " " + j);  
12.             }  
13.         }  
14.     }  
15. }  

**Output:**

1 1
1 2
1 3
2 1
2 3
3 1
3 2
3 3

## Java continue Statement with Labelled for Loop

We can use a continue statement with a label. This feature was introduced in JDK 1.5. Therefore, we can now continue any loop in Java, whether it is an outer loop or an inner loop.

The following example demonstrates the use of a labeled continue statement. When the condition i == 2 and j == 2 is true, continue aa skips the remaining iterations of the current outer loop and moves to the next iteration of the outer loop. All other pairs are printed normally.

### Example

[](https://www.tpointtech.com/java-continue#)[](https://www.tpointtech.com/java-continue#)[](https://www.tpointtech.com/java-continue#)

1. //Java Program to illustrate the use of continue statement with a label inside an inner loop to continue the outer loop    
2. public class Main {  
3.     public static void main(String[] args) {  
4.         aa: for (int i = 1; i <= 3; i++) {  
5.             bb: for (int j = 1; j <= 3; j++) {  
6.                 if (i == 2 && j == 2) {  
7.                     // using continue statement with label  
8.                     continue aa;  
9.                 }  
10.                 System.out.println(i + " " + j);  
11.             }  
12.         }  
13.     }  
14. }  

**Output:**

1 1
1 2
1 3
2 1
3 1
3 2
3 3

## Java continue Statement with While Loop

The **continue statement with a while loop** is used to skip the remaining code in the current iteration and immediately move to the next iteration of the loop when a specified condition is met.

The following example demonstrates the use of the **continue statement inside a while loop**. When i becomes 5, the continue statement skips that iteration, so 5 is not printed. All other numbers from 1 to 10 are displayed.

### Example

[](https://www.tpointtech.com/java-continue#)[](https://www.tpointtech.com/java-continue#)[](https://www.tpointtech.com/java-continue#)

1. //Java Program to demonstrate the use of continue statement inside the while loop.    
2. public class Main {  
3.     public static void main(String[] args) {  
4.         // while loop  
5.         int i = 1;  
6.         while (i <= 10) {  
7.             if (i == 5) {  
8.                 // using continue statement  
9.                 i++;  
10.                 continue;// it will skip the rest statement  
11.             }  
12.             System.out.println(i);  
13.             i++;  
14.         }  
15.     }  
16. }  

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

## Java continue Statement with do-while Loop

The **continue statement with a do-while loop** is used to skip the rest of the code in the current iteration and proceed directly to the next iteration, even though the loop executes at least once before checking the condition.

The following example demonstrates the use of the continue statement inside a do-while loop. When i becomes 5, the continue statement skips that iteration, so 5 is not printed. All other numbers from 1 to 10 are displayed.

### Example

[](https://www.tpointtech.com/java-continue#)[](https://www.tpointtech.com/java-continue#)[](https://www.tpointtech.com/java-continue#)

1. //Java Program to demonstrate the use of continue statement inside the Java do-while loop.    
2. public class Main {    
3.     public static void main(String[] args) {    
4.         //declaring variable    
5.         int i=1;    
6.         //do-while loop    
7.         do {    
8.             if(i==5) {    
9.                     //using continue statement    
10.                      i++;    
11.                 continue;//it will skip the rest statement    
12.             }    
13.             System.out.println(i);    
14.             i++;    
15.         } while(i<=10);    
16.     }    
17. }    

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

## Practical Applications of Continue Statement

There are several practical applications of the continue statement. Some of them are as follows:

### Filtering Data

One common use case for the continue statement is filtering data. Suppose we have a list of numbers, and we want to print only the odd numbers. Using the continue statement, we can easily skip the even numbers.

### Example

[](https://www.tpointtech.com/java-continue#)[](https://www.tpointtech.com/java-continue#)[](https://www.tpointtech.com/java-continue#)

1. import java.util.Arrays;  
2. import java.util.List;  
3. public class Main {  
4.     public static void main(String[] args) {  
5.         List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5, 6, 7, 8, 9, 10);  
6.         for (int number : numbers) {  
7.             if (number % 2 == 0) {  
8.                 continue; // Skip even numbers  
9.             }  
10.             System.out.println(number);  
11.         }  
12.     }  
13. }  

**Output:**

1
3
5
7
9

## Advantages of Continue Statement

There are several advantages of the continue statement in Java. Some of them are as follows:

**Improves Readability:** It helps you avoid deeply nested if-else structures. The logic becomes more direct and easier to follow.

**Flexible Control Flow:** It enables the efficient handling of unusual instances within loops without altering the primary logic.

**Example:**

[](https://www.tpointtech.com/java-continue#)[](https://www.tpointtech.com/java-continue#)[](https://www.tpointtech.com/java-continue#)

1. String[] names = { "Alice", null, "Bob", "Charlie", null, "Dave" };  
2. for (String name : names) {  
3.     if (name == null) {  
4.         continue; // Skip null values  
5.     }  
6.     System.out.println(name);  
7. }  
8. // Output: Alice, Bob, Charlie, Dave  

**Explanation:**

The following example demonstrates using the **continue statement in a for-each loop**. The array contains some null values. When a null element is encountered, continue skips that iteration, so only non-null names (Alice, Bob, Charlie, Dave) are printed.

**Useful for Filtering:** We can filter unwanted data items during iteration without extra flags or lists.

## Disadvantages of Continue Statement

There are several disadvantages of the continue statement in Java. Some of them are as follows:

**Reduce Clarity if Overused:** The loop logic may become difficult to understand if continue is used excessively or with complicated conditions, particularly when there are multiple continue statements.

**Example:**

[](https://www.tpointtech.com/java-continue#)[](https://www.tpointtech.com/java-continue#)[](https://www.tpointtech.com/java-continue#)

1. for (int i = 1; i <= 10; i++) {  
2.     if (i % 2 == 0) continue;  
3.     if (i % 3 == 0) continue;  
4.     if (i % 5 == 0) continue;  
5.     System.out.println(i);  
6. }  
7. // Output: 1, 7  

**Explanation:**

The following example demonstrates using multiple **continue statements** in a for loop. The loop skips numbers divisible by 2, 3, or 5. Only numbers that are **not divisible** by 2, 3, or 5 (1 and 7) are printed