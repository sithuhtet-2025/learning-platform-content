
Conditional statements are essential in programming as they provide a way to make decisions in code. In [C#](https://www.tpointtech.com/c-sharp-tutorial), if, else if, and else provide ways for developers to run various blocks of code based on particular conditions. These constructs are needed for developing dynamic and logical programs.

C# includes multiple iterations of the if statement to manage different program requirements efficiently. In C# programming, the if statement is used to test the condition. There are various types of if statements in C#.

- if statement
- if-else statement
- if-else-if ladder
- nested if statement

Each decision-making structure within C++ provides unique functionalities that boost programming flexibility because they perform distinct tasks.

## C# if Statement

The C# if statement tests the condition. If the condition is true, it executes the code inside the if block. If the condition is false, it exits the if block.

### Syntax:

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-if-else#)[](https://www.tpointtech.com/c-sharp-if-else#)[](https://www.tpointtech.com/c-sharp-if-else#)

1. if(condition){    
2. //code to be executed    
3. }    

Here, if the condition is true, it execute the code inside the if block. On the other, if condition is false, it execute the code of else block.

### Flow Diagram of If Statement in C#

![C# If-else Statement](https://images.tpointtech.com/csharp/images/c-sharp-if-else.png)

This flowchart illustrates the implementation of an if condition within a programming context. The following is a step-by-step description of each element of the flowchart:

**1. Start Point**

- The flowchart starts with a start symbol (a small filled circle).
- This symbolizes the beginning of the process.

**2. Condition Evaluation**

The diamond symbol is used to represent a decision-making point. Here, a condition is evaluated. The decision block can result in two possible outcomes:

- **True:** If the condition is True, the flow goes down.
- **False:** If the condition is False, the flow skips the if block and goes straight to the next step.

**3. If Code Execution (True Condition)**

- If the condition is True, the flowchart goes to a rectangular box named "If code".
- It indicates the execution of a collection of instructions within the if block.

**4. After If Block**

- Once the execution of the if block, control goes to the "After If" block.
- This is the continuation of the program after passing the if statement.
- If the condition was not True, execution directly proceeds to this block, bypassing the if code.

**5. End of Execution**

The flowchart terminates in another small circle, indicating that the process ends.

### C# If Example:

Let us take an example to illustrate the if statement in C#.

### Example

[](https://www.tpointtech.com/c-sharp-if-else#)[](https://www.tpointtech.com/c-sharp-if-else#)[](https://www.tpointtech.com/c-sharp-if-else#)

2. using System;        
3. public class IfExample    
4.     {    
5.        public static void Main(string[] args)    
6.         {    
7.             int num = 10;    
8.             if (num % 2 == 0)    
9.             {    
10.                 Console.WriteLine("It is even number");    
11.             }    

12.         }    
13.     }    

Output:

It is even number

**Explanation:**

- Defines a class (IfExample) that serves as the program's container.
- The program's entry point is the Main Method (Main).
- After that, declares a variable that is an integer (num) and gives it the value 10.
- **Checks if num is Even:** In order to determine whether num is divisible by 2, an if condition is used.
- **Prints Output:** "It is even number" is displayed if the condition is true.
- **Expected Output:** "It is even number" is printed because 10 is even.

## C# IF-else Statement

The C# **_if-else_** statement also tests the condition. It executes if block if the condition is true; otherwise else block is executed.

### Syntax:

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-if-else#)[](https://www.tpointtech.com/c-sharp-if-else#)[](https://www.tpointtech.com/c-sharp-if-else#)

1. if(condition){    
2. //code if condition is true    
3. }else{    
4. //code if condition is false    
5. }    

### Flow Diagram of the If-else Statement:

![C# If-else Statement](https://images.tpointtech.com/csharp/images/c-sharp-if-else2.png)

### C# If-else Example:

Let us take an example to illustrate the if-else statement in C#.

### Example

[](https://www.tpointtech.com/c-sharp-if-else#)[](https://www.tpointtech.com/c-sharp-if-else#)[](https://www.tpointtech.com/c-sharp-if-else#)

1. using System;        
2. public class IfExample    
3.     {    
4.         public static void Main(string[] args)    
5.         {    
6.             int num = 11;    
7.             if (num % 2 == 0)    
8.             {    
9.                 Console.WriteLine("It is even number");    
10.             }    
11.             else    
12.             {    
13.                 Console.WriteLine("It is odd number");    
14.             }    

15.         }    
16.     }    

Output:

It is odd number

**Explanation:**

- This example, specifies a class (IfExample) that houses the logic of the program.
- The Main Method (Main) serves as the executioner's starting point.
- An integer variable (num) is declared, and its value is set to 11.
- It verifies whether num is even by using an if condition to determine whether it is divisible by two.
- It carries out if "It is even number" is printed by Block if True if the criteria is satisfied.
- It carries out else "It is odd number" is printed by Block if False if num is not divisible by 2.
- **Expected Output:** "It is an odd number" is printed because 11 is an odd number.

### C# If-else Example: with input from user

In this example, we are getting input from the user using Console.ReadLine() method. It returns a string. For numeric value, you need to convert it into int using Convert.ToInt32() method.

### Example

[](https://www.tpointtech.com/c-sharp-if-else#)[](https://www.tpointtech.com/c-sharp-if-else#)[](https://www.tpointtech.com/c-sharp-if-else#)

1. using System;        
2. public class IfExample    
3.     {    
4.        public static void Main(string[] args)    
5.         {    
6.             Console.WriteLine("Enter a number:");    
7.             int num = Convert.ToInt32(Console.ReadLine());    

8.             if (num % 2 == 0)    
9.             {    
10.                 Console.WriteLine("It is even number");    
11.             }    
12.             else    
13.             {    
14.                 Console.WriteLine("It is odd number");    
15.             }    

16.         }    
17.     }    

Output:

Enter a number:11
It is odd number

Output:

Enter a number:12
It is even number

**Explanation:**

- In this example, we defines a Class (IfExample) that contains the logic of the program.
- The program's entry point is the Main Method (Main).
- "Enter a number:" appears on the console when the user is prompted for input.
- **Reading User Input:** This function takes a string input and uses Convert to change it to an integer.ToInt32().
- **Verifies whether the integer Is Even:** An if condition is used to ascertain whether the integer is divisible by two.
- Carries out if Prints "It is even number" if the condition is true. Block if True.
- **Carries out else Block if False:** If the condition is not met, it prints "It is an odd number".
- **Dynamic Output:** Using the user's input, the program decides if something is even or odd.

## C# IF-else-if ladder Statement

The C# if-else-if ladder statement executes one condition from multiple statements. Multiple cases can be handled through an if-else if conditional sequence in this structure.

### Syntax:

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-if-else#)[](https://www.tpointtech.com/c-sharp-if-else#)[](https://www.tpointtech.com/c-sharp-if-else#)

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

### Flow Diagram of the If-else-if ladder Statement:

![C# If-else Statement](https://images.tpointtech.com/csharp/images/c-sharp-if-else3.png)

### C# If-else-if ladder Example:

Let us take an example to illustrate the if-else-if ladder statement in C#.

### Example

[](https://www.tpointtech.com/c-sharp-if-else#)[](https://www.tpointtech.com/c-sharp-if-else#)[](https://www.tpointtech.com/c-sharp-if-else#)

1. using System;        
2. public class IfExample    
3.     {    
4.         public static void Main(string[] args)    
5.         {    
6.             Console.WriteLine("Enter a number to check grade:");    
7.             int num = Convert.ToInt32(Console.ReadLine());    

8.             if (num <0 || num >100)    
9.             {    
10.                 Console.WriteLine("wrong number");    
11.             }    
12.             else if(num >= 0 && num < 50){    
13.                 Console.WriteLine("Fail");    
14.             }    
15.             else if (num >= 50 && num < 60)    
16.             {    
17.                 Console.WriteLine("D Grade");    
18.             }    
19.             else if (num >= 60 && num < 70)    
20.             {    
21.                 Console.WriteLine("C Grade");    
22.             }    
23.             else if (num >= 70 && num < 80)    
24.             {    
25.                 Console.WriteLine("B Grade");    
26.             }    
27.             else if (num >= 80 && num < 90)    
28.             {    
29.                 Console.WriteLine("A Grade");    
30.             }    
31.             else if (num >= 90 && num <= 100)    
32.             {    
33.                 Console.WriteLine("A+ Grade");    
34.             }    
35.         }    
36.     }   

Output:

Enter a number to check grade:66
C Grade

Output:

Enter a number to check grade:-2
wrong number

**Explanation**

- In this example, we defines a Class (IfExample) - Encapsulates the program logic.
- **Main Method (Main):** It serves as the entry point for program execution.
- **Prompts the User for Input:** Displays "Enter a number to check grade:".
- **Reads and Converts User Input:** Takes input as a string and converts it into an integer using Convert.ToInt32().
- **Validates Input Range:** Checks if the number is outside 0-100; if true, prints "wrong number".
- Checks Grade Conditions Using if-else Statements:
    1. Below 50 → Prints "Fail".
    2. 50-59 → Prints "D Grade".
    3. 60-69 → Prints "C Grade".
    4. 70-79 → Prints "B Grade".
    5. 80-89 → Prints "A Grade".
    6. 90-100 → Prints "A+ Grade".
- **Dynamic Output:** The grade varies based on the number entered by the user.

## Nested-if statement:

A nested if statement in C# is an if statement placed inside another if statement. It is used when multiple conditions need to be checked sequentially, allowing for more refined decision-making.

### Syntax:

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-if-else#)[](https://www.tpointtech.com/c-sharp-if-else#)[](https://www.tpointtech.com/c-sharp-if-else#)

1. if (condition1)  
2. {  
3.     // Code block for condition1  
4.     if (condition2)  
5.     {  
6.         // Code block for condition2 (executed if both conditions are true)  
7.     }  
8. }  

- The outer if checks condition1.
- If condition1 is true, the inner if checks condition2.
- The inner block runs only if both conditions are true.

Example of Nested if Statement in C#

### Example

[](https://www.tpointtech.com/c-sharp-if-else#)[](https://www.tpointtech.com/c-sharp-if-else#)[](https://www.tpointtech.com/c-sharp-if-else#)

1. using System;  

2. public class NestedIfExample  
3. {  
4.     public static void Main(string[] args)  
5.     {  
6.         int number = 25;  

7.         if (number > 0)  // Outer if statement  
8.         {  
9.             Console.WriteLine("The number is positive.");  

10.             if (number % 2 == 0)  // Inner if statement  
11.             {  
12.                 Console.WriteLine("It is an even number.");  
13.             }  
14.             else  
15.             {  
16.                 Console.WriteLine("It is an odd number.");  
17.             }  
18.         }  
19.     }  
20. }  

**Output:**

The number is positive.
It is an odd number.

**Explanation:**

1. Outer if checks number > 0
    - Since number = 25 (positive), "The number is positive." is printed.
2. Inner if checks number % 2 == 0
    - Since 25 is not even, the else block executes, printing "It is an odd number."