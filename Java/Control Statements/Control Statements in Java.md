
[Java compiler](https://www.tpointtech.com/compiler/java) executes the code from top to bottom. The statements in the code are executed according to the order in which they appear. However, [Java](https://www.tpointtech.com/java-tutorial) provides statements that can be used to control the flow of Java code. Such statements are called control flow statements. It is one of the fundamental features of Java, which provides a smooth flow of program.

## Types of Control Flow Statements

Java provides three types of control flow statements.

1. Decision Making statements
    - if statements
    - switch statement
2. Loop statements
    - do while loop
    - while loop
    - for loop
    - for-each loop
3. Jump statements
    - break statement
    - continue statement

## Java Decision-Making statements

As the name suggests, decision-making statements decide which statement to execute and when. Decision-making statements evaluate the Boolean expression and control the program flow depending upon the result of the condition provided. There are two types of decision-making statements in Java, i.e., If statement and switch statement.

### 1) If Statement

In Java, the "if" statement is used to evaluate a condition. The control of the program is diverted depending upon the specific condition. The condition of the If statement gives a Boolean value, either true or false. In Java, there are four types of if-statements given below.

1. Simple if statement
2. if-else statement
3. if-else-if ladder
4. Nested if-statement

Let's understand the if-statements one by one.

### 1.1) Simple if statement

It is the most basic statement among all control flow statements in Java. It evaluates a Boolean expression and enables the program to enter a block of code if the expression evaluates to true.

**Syntax:**

Syntax of if statement is given below.

[](https://www.tpointtech.com/control-statements-in-java#)[](https://www.tpointtech.com/control-statements-in-java#)[](https://www.tpointtech.com/control-statements-in-java#)

1. if(condition) {    
2. statement 1; //executes when condition is true   
3. }    

Consider the following example in which we have used the **if** statement in the java code.

### Example

[](https://www.tpointtech.com/control-statements-in-java#)[](https://www.tpointtech.com/control-statements-in-java#)[](https://www.tpointtech.com/control-statements-in-java#)

1. public class Main {      
2.     public static void main(String[] args) {      
3.         int x = 10;      
4.         int y = 12;      
5.         if(x+y > 20) {      
6.             System.out.println("x + y is greater than 20");      
7.         }      
8.     }        
9. }       

**Output:**

x + y is greater than 20

### 1.2) if-else statement

The [if-else statement](https://www.tpointtech.com/java-if-else) is an extension to the if-statement, which uses another block of code, i.e., else block. The else block is executed if the condition of the if-block is evaluated as false.

**Syntax:**

It has the following syntax:

[](https://www.tpointtech.com/control-statements-in-java#)[](https://www.tpointtech.com/control-statements-in-java#)[](https://www.tpointtech.com/control-statements-in-java#)

1. if(condition) {    
2. statement 1; //executes when condition is true   
3. }  
4. else{  
5. statement 2; //executes when condition is false   
6. }  

Consider the following example.

### Example

[](https://www.tpointtech.com/control-statements-in-java#)[](https://www.tpointtech.com/control-statements-in-java#)[](https://www.tpointtech.com/control-statements-in-java#)

1. public class Main {    
2.     public static void main(String[] args) {    
3.         int x = 10;    
4.         int y = 12;    
5.         if(x+y < 10) {    
6.             System.out.println("x + y is less than 10");    
7.         }   else {    
8.             System.out.println("x + y is greater than 20");    
9.         }    
10.     }    
11. }    

**Output:**

x + y is greater than 20

### 1.3) if-else-if ladder

The if-else-if statement contains the if-statement followed by multiple else-if statements. In other words, we can say that it is the chain of if-else statements that create a decision tree where the program may enter in the block of code where the condition is true. We can also define an else statement at the end of the chain.

**Syntax:**

Syntax of if-else-if statement is given below.

[](https://www.tpointtech.com/control-statements-in-java#)[](https://www.tpointtech.com/control-statements-in-java#)[](https://www.tpointtech.com/control-statements-in-java#)

1. if(condition 1) {    
2. statement 1; //executes when condition 1 is true   
3. }  
4. else if(condition 2) {  
5. statement 2; //executes when condition 2 is true   
6. }  
7. else {  
8. statement 2; //executes when all the conditions are false   
9. }  

Consider the following example.

### Example

[](https://www.tpointtech.com/control-statements-in-java#)[](https://www.tpointtech.com/control-statements-in-java#)[](https://www.tpointtech.com/control-statements-in-java#)

1. public class Main {    
2.     public static void main(String[] args) {    
3.         String city = "Delhi";    
4.         if(city == "Meerut") {    
5.         System.out.println("city is meerut");    
6.         }else if (city == "Noida") {    
7.         System.out.println("city is noida");    
8.         }else if(city == "Agra") {    
9.         System.out.println("city is agra");    
10.         }else {    
11.         System.out.println(city);    
12.         }    
13.     }    
14. }    

**Output:**

Delhi

### 1.4) Nested if-statement

In nested if-statements, the if statement can contain a **if** or **if-else** statement inside another if or else-if statement.

**Syntax:**

Syntax of Nested if-statement is given below.

[](https://www.tpointtech.com/control-statements-in-java#)[](https://www.tpointtech.com/control-statements-in-java#)[](https://www.tpointtech.com/control-statements-in-java#)

1. if(condition 1) {    
2. statement 1; //executes when condition 1 is true   
3. if(condition 2) {  
4. statement 2; //executes when condition 2 is true   
5. }  
6. else{  
7. statement 2; //executes when condition 2 is false   
8. }  
9. }  

Consider the following example.

### Example

[](https://www.tpointtech.com/control-statements-in-java#)[](https://www.tpointtech.com/control-statements-in-java#)[](https://www.tpointtech.com/control-statements-in-java#)

1. public class Main {      
2.     public static void main(String[] args) {      
3.         String address = "Delhi, India";      

4.         if(address.endsWith("India")) {      
5.             if(address.contains("Meerut")) {      
6.             System.out.println("Your city is Meerut");      
7.             }else if(address.contains("Noida")) {      
8.             System.out.println("Your city is Noida");      
9.             }else {      
10.             System.out.println(address.split(",")[0]);      
11.         }      
12.         }else {      
13.             System.out.println("You are not living in India");      
14.         }      
15.     }      
16. }   

**Output:**

Delhi

### 2) Switch Statement

In Java, [Switch statements](https://www.tpointtech.com/java-switch) are similar to if-else-if statements. The switch statement contains multiple blocks of code called cases and a single case is executed based on the variable which is being switched. The switch statement is easier to use instead of if-else-if statements. It also enhances the readability of the program.

Points to be noted about switch statement:

- The case variables can be int, short, byte, char, or enumeration. String type is also supported since version 7 of Java
- Cases cannot be duplicate
- Default statement is executed when any of the case doesn't match the value of expression. It is optional.
- Break statement terminates the switch block when the condition is satisfied.  
    It is optional, if not used, next case is executed.
- While using switch statements, we must notice that the case expression will be of the same type as the variable. However, it will also be a constant value.

**Syntax:**

The syntax to use the switch statement is given below.

[](https://www.tpointtech.com/control-statements-in-java#)[](https://www.tpointtech.com/control-statements-in-java#)[](https://www.tpointtech.com/control-statements-in-java#)

1. switch (expression){  
2.     case value1:  
3.      statement1;  
4.      break;  
5.     .  
6.     .  
7.     .  
8.     case valueN:  
9.      statementN;  
10.      break;  
11.     default:  
12.      default statement;  
13. }  

Consider the following example to understand the flow of the switch statement.

### Example

[](https://www.tpointtech.com/control-statements-in-java#)[](https://www.tpointtech.com/control-statements-in-java#)[](https://www.tpointtech.com/control-statements-in-java#)

1. public class Main {    
2.     public static void main(String[] args) {    
3.         int num = 2;    
4.         switch (num){    
5.             case 0:    
6.             System.out.println("number is 0");    
7.             break;    
8.             case 1:    
9.             System.out.println("number is 1");    
10.             break;    
11.             default:    
12.             System.out.println(num);    
13.         }    
14.     }    
15. }    

**Output:**

2

While using switch statements, we must notice that the case expression will be of the same type as the variable. However, it will also be a constant value. The switch permits only int, string, and Enum type variables to be used.

## Java Loop Statements

In programming, sometimes we need to execute the block of code repeatedly while some condition evaluates to true. However, loop statements are used to execute the set of instructions in a repeated order. The execution of the set of instructions depends upon a particular condition.

In Java, we have three types of loops that execute similarly. However, there are differences in their syntax and condition checking time.

1. Java for loop
2. Java for-each loop
3. Java while loop
4. Java do-while loop

Let's understand the loop statements one by one.

### Java for loop

In Java, [for loop](https://www.tpointtech.com/java-for-loop) is similar to [C](https://www.tpointtech.com/c-programming-language-tutorial) and [C++](https://www.tpointtech.com/cpp-tutorial). It enables us to initialize the loop variable, check the condition, and increment/decrement in a single line of code. We use the for loop only when we exactly know the number of times, we want to execute the block of code.

**Syntax:**

It has the following syntax:

[](https://www.tpointtech.com/control-statements-in-java#)[](https://www.tpointtech.com/control-statements-in-java#)[](https://www.tpointtech.com/control-statements-in-java#)

1. for(initialization, condition, increment/decrement) {    
2. //block of statements    
3. }    

The flow chart for the for-loop is given below.

![Control Flow in Java](https://images.tpointtech.com/core/images/control-flow-in-java.png)

Consider the following example to understand the proper functioning of the for loop in java.

### Example

[](https://www.tpointtech.com/control-statements-in-java#)[](https://www.tpointtech.com/control-statements-in-java#)[](https://www.tpointtech.com/control-statements-in-java#)

1. public class Main {    
2.     public static void main(String[] args) {    
3.         // TODO Auto-generated method stub    
4.         int sum = 0;    
5.         for(int j = 1; j<=10; j++) {    
6.             sum = sum + j;    
7.         }    
8.         System.out.println("The sum of first 10 natural numbers is " + sum);    
9.     }    
10. }    

**Output:**

The sum of first 10 natural numbers is 55

### Java for-each loop

Java provides an enhanced for loop to traverse the data structures like array or collection. In the for-each loop, we don't need to update the loop variable.

**Syntax:**

The syntax to use the for-each loop in java is given below.

[](https://www.tpointtech.com/control-statements-in-java#)[](https://www.tpointtech.com/control-statements-in-java#)[](https://www.tpointtech.com/control-statements-in-java#)

1. for(data_type var : array_name/collection_name){    
2. //statements    
3. }    

Consider the following example to understand the functioning of the for-each loop in Java.

### Example

[](https://www.tpointtech.com/control-statements-in-java#)[](https://www.tpointtech.com/control-statements-in-java#)[](https://www.tpointtech.com/control-statements-in-java#)

1. public class Main {      
2.     public static void main(String[] args) {      
3.         String[] names = {"Java","C","C++","Python","JavaScript"};      
4.         System.out.println("Printing the content of the array names:");      
5.         for(String name:names) {      
6.             System.out.println(name);      
7.         }      
8.     }      
9. }      

**Output:**

Printing the content of the array names:

Java
C
C++
Python
JavaScript

### Java while loop

The [while loop](https://www.tpointtech.com/java-while-loop) is also used to iterate over the number of statements multiple times. However, if we don't know the number of iterations in advance, it is recommended to use a while loop. Unlike for loop, the initialization and increment/decrement doesn't take place inside the loop statement in while loop.

It is also known as the entry-controlled loop since the condition is checked at the start of the loop. If the condition is true, then the loop body will be executed; otherwise, the statements after the loop will be executed.

**Syntax:**

The syntax of the while loop is given below.

[](https://www.tpointtech.com/control-statements-in-java#)[](https://www.tpointtech.com/control-statements-in-java#)[](https://www.tpointtech.com/control-statements-in-java#)

1. while(condition){    
2. //looping statements    
3. }    

The flow chart for the while loop is given in the following image.

![Control Flow in Java](https://images.tpointtech.com/core/images/control-flow-in-java2.png)

Consider the following example.

### Example

[](https://www.tpointtech.com/control-statements-in-java#)[](https://www.tpointtech.com/control-statements-in-java#)[](https://www.tpointtech.com/control-statements-in-java#)

1. public class Main {      
2.     public static void main(String[] args) {      
3.         int i = 0;      
4.         System.out.println("Printing the list of first 10 even numbers");      
5.         while(i<=10) {      
6.             System.out.println(i);      
7.             i = i + 2;      
8.         }      
9.     }      
10. }      

**Output:**

Printing the list of first 10 even numbers

0
2
4
6
8
10

### Java do-while loop

The [do-while loop](https://www.tpointtech.com/java-do-while-loop) checks the condition at the end of the loop after executing the loop statements. When the number of iteration is not known and we have to execute the loop at least once, we can use do-while loop.

It is also known as the exit-controlled loop since the condition is not checked in advance. The syntax of the do-while loop is given below.

[](https://www.tpointtech.com/control-statements-in-java#)[](https://www.tpointtech.com/control-statements-in-java#)[](https://www.tpointtech.com/control-statements-in-java#)

1. do     
2. {    
3. //statements    
4. } while (condition);    

The flow chart of the do-while loop is given in the following image.

![Control Flow in Java](https://images.tpointtech.com/core/images/control-flow-in-java3.png)

Consider the following example to understand the functioning of the do-while loop in Java.

### Example

[](https://www.tpointtech.com/control-statements-in-java#)[](https://www.tpointtech.com/control-statements-in-java#)[](https://www.tpointtech.com/control-statements-in-java#)

1. public class Main {      
2.     public static void main(String[] args) {      
3.         int i = 0;      
4.         System.out.println("Printing the list of first 10 even numbers ");      
5.         do {      
6.             System.out.println(i);      
7.             i = i + 2;      
8.         }while(i<=10);      
9.     }      
10. }    

**Output:**

Printing the list of first 10 even numbers
0
2
4
6
8
10

## Java Jump Statements

Jump statements are used to transfer the control of the program to the specific statements. In other words, jump statements transfer the execution control to the other part of the program. There are two types of jump statements in Java. These are as listed below:

1. Java break statement
2. Java continue statement

### Java break statement

As the name suggests, the [break statement](https://www.tpointtech.com/java-break) is used to break the current flow of the program and transfer the control to the next statement outside a loop or switch statement. However, it breaks only the inner loop in the case of the nested loop.

The break statement cannot be used independently in the Java program, i.e., it can only be written inside the loop or switch statement.

**The break statement example with for loop**

Consider the following example in which we have used the break statement with the for loop.

### Example

[](https://www.tpointtech.com/control-statements-in-java#)[](https://www.tpointtech.com/control-statements-in-java#)[](https://www.tpointtech.com/control-statements-in-java#)

1. public class Main {    
2.     public static void main(String[] args) {    
3.         for(int i = 0; i<= 10; i++) {    
4.             System.out.println(i);    
5.             if(i==6) {    
6.             break;    
7.             }    
8.         }    
9.     }    
10. }    

**Output:**

0
1
2
3
4
5
6

**break statement example with labeled for loop**

### Example

[](https://www.tpointtech.com/control-statements-in-java#)[](https://www.tpointtech.com/control-statements-in-java#)[](https://www.tpointtech.com/control-statements-in-java#)

1. public class Main {      
2. public static void main(String[] args) {      
3.     a:      
4.     for(int i = 0; i<= 10; i++) {      
5.         b:      
6.         for(int j = 0; j<=15;j++) {      
7.             c:      
8.             for (int k = 0; k<=20; k++) {      
9.                 System.out.println(k);      
10.                 if(k==5) {      
11.                 break a;      
12.                 }      
13.             }      
14.         }      

15.     }      
16. }      
17. }      

**Output:**

0
1
2
3
4
5

### Java continue statement

Unlike break statement, the [continue statement](https://www.tpointtech.com/java-continue) doesn't break the loop, whereas, it skips the specific part of the loop and jumps to the next iteration of the loop immediately.

Consider the following example to understand the functioning of the continue statement in Java.

### Example

[](https://www.tpointtech.com/control-statements-in-java#)[](https://www.tpointtech.com/control-statements-in-java#)[](https://www.tpointtech.com/control-statements-in-java#)

1. public class Main {    
2. public static void main(String[] args) {      
3.     for(int i = 0; i<= 2; i++) {    

4.         for (int j = i; j<=5; j++) {    

5.             if(j == 4) {    
6.             continue;    
7.             }    
8.             System.out.println(j);    
9.         }    
10.     }    
11. }      
12. }  

**Output:**

0
1
2
3
5
1
2
3
5
2
3
5