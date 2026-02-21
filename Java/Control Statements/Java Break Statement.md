
The `break` statement in Java is a powerful tool for controlling the flow of your program. It is used to exit a loop or switch statement prematurely. It allows us to customize the behavior of code based on specific conditions.

## How do break statements work in Loops?

When a break statement is encountered inside a loop, the loop is immediately terminated and the program control resumes at the next statement following the loop.

## Using break with Loops and Switch Statements

The Java _break_ statement is used to break loop or [switch](https://www.tpointtech.com/java-switch) statement. It breaks the current flow of the program at specified condition. In case of inner loop, it breaks only inner loop.

## Practical Example of break Statement

For example, consider a situation if we are searching for a specific value in an array using a for loop. We can use the break statement to exit the loop as soon as we find the value, like this:

[](https://www.tpointtech.com/java-break#)[](https://www.tpointtech.com/java-break#)[](https://www.tpointtech.com/java-break#)

1. int[] array = {1, 2, 3, 4, 5};  
2. int targetValue = 3;  
3. for (int i = 0; i < array.length; i++) {  
4.     if (array[i] == targetValue) {  
5.         System.out.println("Value found at index " + i);  
6.         break;  
7.     }  
8. }  

In this example, as soon as the value 3 is found in the array, the break statement is executed, and the loop is terminated. Without the break statement, the loop would continue iterating through the remaining elements of the array that is unnecessary once the value has been found.

Overall, the break statement is a versatile tool that allows us to customize the flow of Java programs, making them more efficient and easier to read. However, it is important to use break judiciously and understand its impact on the flow of code to avoid unintended consequences.

## Use of break Statement

We can use Java break statement in all types of loops such as [for loop](https://www.tpointtech.com/java-for-loop), [while loop](https://www.tpointtech.com/java-while-loop) and [do-while loop](https://www.tpointtech.com/java-do-while-loop).

### Syntax of the break Statement

[](https://www.tpointtech.com/java-break#)[](https://www.tpointtech.com/java-break#)[](https://www.tpointtech.com/java-break#)

1. jump-statement;    
2. break;   

## Flowchart of break Statement

The flowchart of a break statement starts with the condition check of the loop. If the condition is true, the loop body is executed, and then the condition is checked again. If the condition becomes false, the loop is exited normally, and the program continues with the statement after the loop.

However, if a break statement is encountered inside the loop body, the control jumps to the statement immediately after the loop, bypassing the normal exit condition check. This behavior allows us to prematurely exit a loop based on certain conditions, even if the loop's condition is still true.

It is important to note that a break statement only affects the innermost loop that contains it. If we have nested loops and we use a break statement in the inner loop, only that inner loop will be exited, and the outer loops will continue executing normally unless they also have their own break statements.

![java break statement flowchart](https://d2jdgazzki9vjm.cloudfront.net/core/images/java-break-statement.png)

## Java Break Statement with Loop

The **break statement with loop** is used to immediately terminate the execution of a loop when a specific condition is met and transfer control to the statement that follows the loop.

### Example: Java break statement with Loop

The following example shows the use of the break statement inside a for loop. The loop runs from 1 to 10, but when the value of i becomes 5, the break statement stops the loop. As a result, only the numbers 1 to 4 are printed.

[](https://www.tpointtech.com/java-break#)[](https://www.tpointtech.com/java-break#)[](https://www.tpointtech.com/java-break#)

1. //Java Program to demonstrate the use of break statement    
2. //inside the for loop.  
3. public class BreakExample {  
4. public static void main(String[] args) {  
5.     //using for loop  
6.     for(int i=1;i<=10;i++){  
7.         if(i==5){  
8.             //breaking the loop  
9.             break;  
10.         }  
11.         System.out.println(i);  
12.     }  
13. }  
14. }  

**Output:**

1
2
3
4

## Java Break Statement with Inner Loop

It breaks inner loop only if you use break statement inside the inner loop.

### Example: Java Break Statement with Inner Loop

The following example shows the use of the **break statement inside a for loop**. The loop runs from 1 to 10, but when the value of i becomes 5, the break statement stops the loop. As a result, only the numbers 1 to 4 are printed.

[](https://www.tpointtech.com/java-break#)[](https://www.tpointtech.com/java-break#)[](https://www.tpointtech.com/java-break#)

1. //Java Program to illustrate the use of break statement    
2. //inside an inner loop   
3. public class BreakExample2 {  
4. public static void main(String[] args) {  
5.             //outer loop   
6.             for(int i=1;i<=3;i++){    
7.                     //inner loop  
8.                     for(int j=1;j<=3;j++){    
9.                         if(i==2&&j==2){    
10.                             //using break statement inside the inner loop  
11.                             break;    
12.                         }    
13.                         System.out.println(i+" "+j);    
14.                     }    
15.             }    
16. }  
17. }  

**Output:**

1 1
1 2
1 3
2 1
3 1
3 2
3 3

## Java break Statement with Labelled for Loop

We can use break statement with a label. The feature is introduced since JDK 1.5. So, we can break any loop in Java now whether it is outer or inner loop.

### Example: Java break Statement with Labelled for Loop

The following example demonstrates the use of a **labeled break statement**. Two loops are defined with labels aa (outer loop) and bb (inner loop). When the condition i == 2 and j == 2 becomes true, break aa terminates the **outer loop**, not just the inner loop. As a result, the program stops executing both loops immediately and prints the values generated before the break condition.

[](https://www.tpointtech.com/java-break#)[](https://www.tpointtech.com/java-break#)[](https://www.tpointtech.com/java-break#)

1. //Java Program to illustrate the use of continue statement  
2. //with label inside an inner loop to break outer loop  
3. public class BreakExample3 {  
4. public static void main(String[] args) {  
5.             aa:  
6.             for(int i=1;i<=3;i++){    
7.                     bb:  
8.                     for(int j=1;j<=3;j++){    
9.                         if(i==2&&j==2){    
10.                             //using break statement with label  
11.                             break aa;    
12.                         }    
13.                         System.out.println(i+" "+j);    
14.                     }    
15.             }    
16. }  
17. }  

**Output:**

1 1
1 2
1 3
2 1

## Java break Statement with while loop

The **break statement with a while loop** is used to stop the loop execution immediately when a specified condition becomes true, and control moves to the statement after the loop.

### Example: Java break Statement with while loop

The following example demonstrates the use of the **break statement inside a while loop**. The loop runs while the value of i is less than or equal to 10. When i becomes 5, the break statement is executed, which immediately terminates the loop. As a result, only the values from 1 to 4 are printed.

[](https://www.tpointtech.com/java-break#)[](https://www.tpointtech.com/java-break#)[](https://www.tpointtech.com/java-break#)

1. //Java Program to demonstrate the use of break statement  
2. //inside the while loop.  
3. public class BreakWhileExample {  
4. public static void main(String[] args) {  
5.     //while loop  
6.     int i=1;  
7.     while(i<=10){  
8.         if(i==5){  
9.             //using break statement  
10.             i++;  
11.             break;//it will break the loop  
12.         }  
13.         System.out.println(i);  
14.         i++;  
15.     }  
16. }  
17. }  

**Output:**

1
2
3
4

## Java break Statement with do-while loop

The **break statement with a do-while loop** is used to terminate the loop execution instantly when a specific condition is met, even though the loop executes at least once before the condition is checked.

### Example: Java break Statement with do-while loop

The following example demonstrates the use of the **break statement inside a do-while loop**. The loop starts with i = 1 and executes at least once. When the value of i becomes 5, the break statement stops the loop immediately. As a result, only the numbers from 1 to 4 are printed.

[](https://www.tpointtech.com/java-break#)[](https://www.tpointtech.com/java-break#)[](https://www.tpointtech.com/java-break#)

1. //Java Program to demonstrate the use of break statement  
2. //inside the Java do-while loop.  
3. public class BreakDoWhileExample {  
4. public static void main(String[] args) {  
5.     //declaring variable  
6.     int i=1;  
7.     //do-while loop  
8.     do{  
9.         if(i==5){  
10.            //using break statement  
11.            i++;  
12.            break;//it will break the loop  
13.         }  
14.         System.out.println(i);  
15.         i++;  
16.     }while(i<=10);  
17. }  
18. }  

**Output:**

1
2
3
4

## Java Break Statement with Switch

The break statement can be utilized alongside switch statement in Java for successfully exiting

### Example: Java Break Statement with Switch

The following example shows the use of the **break statement in a switch statement**. The program displays a menu and processes the user’s choice. The break statement exits the switch after each case, while selecting option 4 exits the program.

[](https://www.tpointtech.com/java-break#)[](https://www.tpointtech.com/java-break#)[](https://www.tpointtech.com/java-break#)

1. import java.util.Scanner;  
2. public class JavaBreak1 {  
3.     public static void main(String[] args) {  
4.         Scanner scanner = new Scanner(System.in);  
5.         System.out.println("Choose an option:");  
6.         System.out.println("1. Option 1");  
7.         System.out.println("2. Option 2");  
8.         System.out.println("3. Option 3");  
9.         System.out.println("4. Exit");  
10.         while (true) {  
11.             System.out.print("Enter your choice: ");  
12.             int choice = scanner.nextInt();  
13.             switch (choice) {  
14.                 case 1:  
15.                     System.out.println("You chose Option 1");  
16.                     break; // Exit the switch statement  
17.                 case 2:  
18.                     System.out.println("You chose Option 2");  
19.                     break; // Exit the switch statement  
20.                 case 3:  
21.                     System.out.println("You chose Option 3");  
22.                     break; // Exit the switch statement  
23.                 case 4:  
24.                     System.out.println("Exiting...");  
25.                     scanner.close();  
26.                     return; // Exit the program  
27.                 default:  
28.                     System.out.println("Invalid choice. Please try again.");  
29.                     break; // Exit the switch statement  
30.             }  
31.         }  
32.     }  
33. }  

**Output:**

Choose an option:
1. Option 1
2. Option 2
3. Option 3
4. Exit
Enter your choice: 1
You chose Option 1
Enter your choice: 2
You chose Option 2
Enter your choice: 3
You chose Option 3
Enter your choice: 4
Exiting...

To understand the example of break with switch statement, go with the link: [Java Switch Statement](https://www.tpointtech.com/java-switch).

## Real-World Uses of Java break Statement

The break statement in Java is commonly used in various applications to control the flow of a program and manage loop iterations or switch cases. One common application is in searching algorithms, where break can be used to exit a loop once a desired condition is met. For example, in linear search, the loop can be terminated early if the target element is found, saving unnecessary iterations.

Another application is in error handling, where break can be used to exit a loop if an error condition is encountered. It can prevent the program from continuing to execute potentially faulty code and causing further issues. Additionally, break can be used in switch statements to exit the switch block once a specific case is matched, improving the efficiency of the code.

In user input validation, break can be used to exit a loop that prompts the user for input until a valid input is provided. Once the valid input is received, the loop can be exited using break, and the program can continue with the next steps. It helps in ensuring that the program does not proceed with invalid or unexpected input.

### Example: Real-World Uses of Java break Statement

Let's understand about the break statement of Java with the help of an example program that demonstrates the usage of break statement in all types of scenarios in a program.

[](https://www.tpointtech.com/java-break#)[](https://www.tpointtech.com/java-break#)[](https://www.tpointtech.com/java-break#)

1. import java.util.Scanner;  
2. public class JavaBreak {  
3.     public static void main(String[] args) {  
4.         Scanner scanner = new Scanner(System.in);  
5.         int number;  
6.         // Using break in a for loop  
7.         System.out.println("Using break in a for loop:");  
8.         for (int i = 1; i <= 5; i++) {  
9.             System.out.print("Enter a number (or -1 to exit): ");  
10.             number = scanner.nextInt();  
11.             // Check if the user wants to exit the loop  
12.             if (number == -1) {  
13.                 // If the user wants to exit, break out of the loop  
14.                 break;  
15.             }  
16.             // If the user doesn't want to exit, display the number  
17.             System.out.println("You entered: " + number);  
18.         }  
19.         // Using break in a while loop  
20.         System.out.println("\nUsing break in a while loop:");  
21.         int i = 1;  
22.         while (i <= 5) {  
23.             System.out.print("Enter a number (or -1 to exit): ");  
24.             number = scanner.nextInt();  
25.             // Check if the user wants to exit the loop  
26.             if (number == -1) {  
27.                 // If the user wants to exit, break out of the loop  
28.                 break;  
29.             }  
30.             // If the user doesn't want to exit, display the number  
31.             System.out.println("You entered: " + number);  
32.             i++;  
33.         }  
34.         // Using break in a do-while loop  
35.         System.out.println("\nUsing break in a do-while loop:");  
36.         i = 1;  
37.         do {  
38.             System.out.print("Enter a number (or -1 to exit): ");  
39.             number = scanner.nextInt();  
40.             // Check if the user wants to exit the loop  
41.             if (number == -1) {  
42.                 // If the user wants to exit, break out of the loop  
43.                 break;  
44.             }  
45.             // If the user doesn't want to exit, display the number  
46.             System.out.println("You entered: " + number);  
47.             i++;  
48.         } while (i <= 5);  
49.         // Close the scanner  
50.         scanner.close();  
51.     }  
52. }  

**Output:**

Using break in a for loop:
Enter a number (or -1 to exit): 6
You entered: 6
Enter a number (or -1 to exit): 5
You entered: 5
Enter a number (or -1 to exit): 1
You entered: 1
Enter a number (or -1 to exit): 2
You entered: 2
Enter a number (or -1 to exit): 36
You entered: 36
Using break in a while loop:
Enter a number (or -1 to exit): 5
You entered: 5
Enter a number (or -1 to exit): 2
You entered: 2
Enter a number (or -1 to exit): 2
You entered: 2
Enter a number (or -1 to exit): 2
You entered: 2
Enter a number (or -1 to exit): 2
You entered: 2
Using break in a do-while loop:
Enter a number (or -1 to exit): 2
You entered: 2
Enter a number (or -1 to exit): 2
You entered: 2
Enter a number (or -1 to exit): 2