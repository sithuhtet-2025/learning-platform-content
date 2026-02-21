In programming, decision-making plays a pivotal role in determining the flow of execution. Whether it's directing traffic in a complex intersection or navigating through various scenarios in a program, making decisions is essential. In Java, one of the fundamental constructs for decision-making is the 'if-else' statement. Let's delve into what 'if-else' statements are, how they work, and how they can be effectively utilised in [Java programming](https://www.tpointtech.com/java-tutorial).

The Java if statement is used to test the condition. It checks the Boolean condition: true or false. There are mainly four types of if statements in Java.

1. if statement
2. if-else statement
3. if-else-if ladder
4. [nested if statement](https://www.tpointtech.com/nested-if-statements-in-java)

## Java if Statement

The simplest type of control structure for decision-making in Java is the if statement. It executes the if block if the condition is true. It checks a Boolean condition and executes the code block inside the if statement if the condition is true. This statement merely bypasses the block if the condition is false. Using specific criteria helps regulate the program's flow. It is frequently employed in real-world applications for conditional executions, checks, and validation.

### Syntax:

It has the following syntax:

[](https://www.tpointtech.com/java-if-else#)[](https://www.tpointtech.com/java-if-else#)[](https://www.tpointtech.com/java-if-else#)

1. if(condition){  
2. //code to be executed  
3. }  

  
![if statement in java](https://d2jdgazzki9vjm.cloudfront.net/images/core/if1.png)

### Example: Checking Age

Here, we are going to take an example to demonstrate how to find the age using the if statement in Java.

### Example

[](https://www.tpointtech.com/java-if-else#)[](https://www.tpointtech.com/java-if-else#)[](https://www.tpointtech.com/java-if-else#)

1. //Java Program to demonstate the use of if statement.  
2. public class Main {  
3. public static void main(String[] args) {  
4.     //defining an 'age' variable  
5.     int age=20;  
6.     //checking the age  
7.     if(age>18){  
8.         System.out.print("Age is greater than 18");  
9.     }  
10. }  
11. }  

**Output:**

Age is greater than 18

## Java if-else Statement

The Java if-else statement is a basic control structure that allows us to run multiple code blocks depending on whether a condition is true or false. It executes the if block if the condition is true; otherwise, the else block is executed. It enables decision-making within a program and permits the execution flow to alter based on different circumstances. In real-time situations like error handling, branching logic, and validation, it is frequently utilized.

### Syntax:

It has the following syntax:

[](https://www.tpointtech.com/java-if-else#)[](https://www.tpointtech.com/java-if-else#)[](https://www.tpointtech.com/java-if-else#)

1. if(condition){  
2. //code if condition is true  
3. }else{  
4. //code if condition is false  
5. }  

  
![if-else statement in java](https://d2jdgazzki9vjm.cloudfront.net/images/core/if2.png)

### Example: Checking EVEN or ODD

Let us take a program to find odd and even number using the Java if-else statement.

### Example

[](https://www.tpointtech.com/java-if-else#)[](https://www.tpointtech.com/java-if-else#)[](https://www.tpointtech.com/java-if-else#)

1. public class Main {  
2. public static void main(String[] args) {  
3.     //defining a variable  
4.     int number=13;  
5.     //Check if the number is divisible by 2 or not  
6.     if(number%2==0){  
7.         System.out.println("even number");  
8.     }else{  
9.         System.out.println("odd number");  
10.     }  
11. }  
12. }  

**Output:**

odd number

### Example: Checking Leap Year

A year is a leap, if it is divisible by 4 and 400. But, not by 100.

### Example

[](https://www.tpointtech.com/java-if-else#)[](https://www.tpointtech.com/java-if-else#)[](https://www.tpointtech.com/java-if-else#)

1. public class Main {    
2. public static void main(String[] args) {    
3.     int year=2020;    
4.     if(((year % 4 ==0) && (year % 100 !=0)) || (year % 400==0)){  
5.         System.out.println("LEAP YEAR");  
6.     }  
7.     else{  
8.         System.out.println("COMMON YEAR");  
9.     }  
10. }    
11. }    

**Output:**

LEAP YEAR

## Java if-else-if ladder Statement

The if-else-if ladder statement executes one condition from multiple statements. An optional else block comes at the end of the code after an if condition and one or more else if blocks. Every condition is checked from top to bottom as the program runs, and the block corresponding to the first true condition is run. The else block is run if none of the conditions are met. Many possible paths can be handled clearly and understandably with the help of this statement.

### Syntax:

It has the following syntax:

[](https://www.tpointtech.com/java-if-else#)[](https://www.tpointtech.com/java-if-else#)[](https://www.tpointtech.com/java-if-else#)

1. if(condition1){  
2. //code to be executed if condition1 is true  
3. }else if(condition2){  
4. //code to be executed if condition2 is true  
5. }  
6. else if(condition3){  
7. //code to be executed if condition3 is true  
8. }  
9. ...  
10. else{  
11. //code to be executed if all the conditions are false  
12. }  

  
![if-else-if ladder statement in java](https://d2jdgazzki9vjm.cloudfront.net/cpages/images/elseifladder.png)

### Example: Checking Grading System

Let us take an example to demonstrate how to check grading system using if-else-if ladder statement in Java.

### Example

[](https://www.tpointtech.com/java-if-else#)[](https://www.tpointtech.com/java-if-else#)[](https://www.tpointtech.com/java-if-else#)

1. //Java Program to demonstrate the use of If else-if ladder.  
2. //It is a program of grading system for fail, D grade, C grade, B grade, A grade and A+.  
3. public class Main {  
4. public static void main(String[] args) {  
5.     int marks=65;  

6.     if(marks<50){  
7.         System.out.println("fail");  
8.     }  
9.     else if(marks>=50 && marks<60){  
10.         System.out.println("D grade");  
11.     }  
12.     else if(marks>=60 && marks<70){  
13.         System.out.println("C grade");  
14.     }  
15.     else if(marks>=70 && marks<80){  
16.         System.out.println("B grade");  
17.     }  
18.     else if(marks>=80 && marks<90){  
19.         System.out.println("A grade");  
20.     }else if(marks>=90 && marks<100){  
21.         System.out.println("A+ grade");  
22.     }else{  
23.         System.out.println("Invalid!");  
24.     }  
25. }  
26. }  

**Output:**

C grade

### Example: Checking Positive, Negative, or Zero

Let us take an example to demonstrate how to check positive, negative, and zero using the if else-if ladder statement in Java.

### Example

[](https://www.tpointtech.com/java-if-else#)[](https://www.tpointtech.com/java-if-else#)[](https://www.tpointtech.com/java-if-else#)

1. public class Main {    
2. public static void main(String[] args) {    
3.     int number=-13;    
4.     if(number>0){  
5.     System.out.println("POSITIVE");  
6.     }else if(number<0){  
7.     System.out.println("NEGATIVE");  
8.     }else{  
9.     System.out.println("ZERO");  
10.    }  
11. }    
12. }    

**Output:**

NEGATIVE

## Java Nested if statement

In Java, putting one if statement inside another is known as a "nested if statement." In this way, a hierarchical decision-making framework is created, allowing you to check for a secondary condition only if the first condition is true. It is helpful for testing several linked circumstances that are interdependent. Nested if statements are strong, but they should be used sparingly to prevent making the code difficult to read and update.

### Syntax:

It has the following syntax:

[](https://www.tpointtech.com/java-if-else#)[](https://www.tpointtech.com/java-if-else#)[](https://www.tpointtech.com/java-if-else#)

1. if(condition){    
2.      //code to be executed    
3.           if(condition){  
4.              //code to be executed    
5.     }    
6. }  

  
![Java Nested If Statement](https://d2jdgazzki9vjm.cloudfront.net/corebasic/images/nestedif.png)

### Example: Checking Elegibility for Blood Donation

### Example

[](https://www.tpointtech.com/java-if-else#)[](https://www.tpointtech.com/java-if-else#)[](https://www.tpointtech.com/java-if-else#)

1. //Java Program to demonstrate the use of Nested If Statement.  
2. public class Main {    
3. public static void main(String[] args) {    
4.     //Creating two variables for age and weight  
5.     int age=20;  
6.     int weight=80;    
7.     //applying condition on age and weight  
8.     if(age>=18){    
9.         if(weight>50){  
10.             System.out.println("You are eligible to donate blood");  
11.         }    
12.     }    
13. }}  

**Output:**

You are eligible to donate blood

### Example: Checking Elegibility for Blood Donation

### Example

[](https://www.tpointtech.com/java-if-else#)[](https://www.tpointtech.com/java-if-else#)[](https://www.tpointtech.com/java-if-else#)

1. //Java Program to demonstrate the use of Nested If Statement.    
2. public class Main {      
3. public static void main(String[] args) {      
4.     //Creating two variables for age and weight    
5.     int age=25;    
6.     int weight=48;      
7.     //applying condition on age and weight    
8.     if(age>=18){      
9.         if(weight>50){    
10.             System.out.println("You are eligible to donate blood");    
11.         } else{  
12.             System.out.println("You are not eligible to donate blood");    
13.         }  
14.     } else{  
15.       System.out.println("Age must be greater than 18");  
16.     }  
17. }    
18. }  

**Output:**

You are not eligible to donate blood

## Ternary Operator

We can also use ternary operator (? :) to perform the task of if...else statement. It is a shorthand way to check the condition. If the condition is true, the result of ? is returned. But, if the condition is false, the result of : is returned.

### Example

[](https://www.tpointtech.com/java-if-else#)[](https://www.tpointtech.com/java-if-else#)[](https://www.tpointtech.com/java-if-else#)

1. public class Main {    
2. public static void main(String[] args) {    
3.     int number=13;    
4.     //Using ternary operator  
5.     String output=(number%2==0)?"even number":"odd number";    
6.     System.out.println(output);  
7. }    
8. }    

**Output:**

odd number