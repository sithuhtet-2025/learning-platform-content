
In C#, the switch statement is a type of decision-making mechanism by executing several code segments based on the value of a given expression. It is also known as a conditional statement. It is similar to the [if-else](https://www.tpointtech.com/c-sharp-if-else) and ladder if statement, but the switch statement is often more efficient and easy to read.

### Syntax of Switch Statement

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-switch#)[](https://www.tpointtech.com/c-sharp-switch#)[](https://www.tpointtech.com/c-sharp-switch#)

1. switch(expression)  
2. {  
3. case expression_value1:  
4. Statement  
5. break;  
6. case expression_value2:  
7. Statement  
8. break;  
9. case expression_value3:  
10. Statement  
11. break;  
12. default:  
13. Statement   
14. }  

Where,

- **Switch(expression):** The value of the expression is initialized once.
- **expression_value:** It compares the expressions. If they match, the code will be executed and break the program; otherwise, it moves to the next statement.
- **break;:** It is used to exit the program.
- **default:** It is an optional part of the switch statement. It can be executed anywhere inside the switch statement.

### Flowchart of the Switch Statement in C#

![Switch Statement in C#](https://images.tpointtech.com/csharp/images/c-sharp-switch-statement.png)

Let us discuss the flowchart and how to work the switch statement in C#.

**Step 1:** In the first step, we have to evaluate the switch expression.

**Step 2:** After that, the evaluated case checks the given condition.

**Step 3:** In this case, we check the value in each case. If the case is matched, it executes the code block. If the case is not matched, it executes the default statement.

**Step 4:** Finally, the statements are executed with the help of a switch case.

### Simple C# Switch Statement Example

Let us take a simple example to illustrate the switch statement in C#.

### Example

[](https://www.tpointtech.com/c-sharp-switch#)[](https://www.tpointtech.com/c-sharp-switch#)[](https://www.tpointtech.com/c-sharp-switch#)

1. using System;  
2. namespace SwitchExample  
3. {  
4. class Vowel  
5.     {     
6. public static void Main(string[] args)  
7.         {  
8. char l;  // character data type  
9. Console.WriteLine("Enter any Character: ");  
10.     l = Convert.ToChar(Console.ReadLine());  
11. switch(Char.ToLower(l))  
12.             {  
13. case 'a':  
14. Console.WriteLine("The entered character is a Vowel");  
15. break;  
16. case 'e':  
17. Console.WriteLine("The entered character is a Vowel");  
18. break;  
19. case 'i':  
20. Console.WriteLine("The entered character is a Vowel");  
21. break;  
22. case 'o':  
23. Console.WriteLine("The entered character is a Vowel");  
24. break;  
25. case 'u':  
26. Console.WriteLine("The entered character is a Vowel");  
27. break;  
28. default:  
29. Console.WriteLine("The entered character is not a Vowel.");  
30. break;  
31.             }  
32.         }  
33.     }     
34. }  

**Output:**

Enter any Character:
i
The entered character is a Vowel

**Explanation:**

In this example, we have taken a character that is taken as input from the user and converted to lowercase using the ToLower() method. After that, the switch statement checks whether the entered character is a vowel (a, e, i, o, or u). If a match is found, it prints that the character is a vowel; otherwise, the default case displays that it's not a vowel.

### Calculator Program using Switch Statement in C#

Let us take a simple example to calculate the simple arithmetic operation using a switch statement in C#.

### Example

[](https://www.tpointtech.com/c-sharp-switch#)[](https://www.tpointtech.com/c-sharp-switch#)[](https://www.tpointtech.com/c-sharp-switch#)

1. using System;  
2. namespace Calculator  
3. {  
4. class Number  
5.     {  
6. public static void Main(string[] args)  
7.         {  
8. char op;   // use character data type  
9. double fnum, snum, result;   // use double data type  
10. Console.Write("Enter the first number: ");  
11. fnum = Convert.ToDouble(Console.ReadLine());  
12. Console.Write("Enter the second number: ");  
13. snum = Convert.ToDouble(Console.ReadLine());  
14. Console.Write("Enter the operator (+, -, *, /): ");  
15. op = Convert.ToChar(Console.ReadLine());  
16. switch (op)  
17.             {     
18. case '+':  
19. result = fnum + snum;   //addition operation is performed  
20. Console.WriteLine("The sum of the first and second number is " + result);  
21. break;  
22. case '-':  
23. result = fnum - snum;  // subtraction operation is performed  
24. Console.WriteLine("The difference of the first and second number is " + result);  
25. break;  
26. case '*':  
27. result = fnum * snum;  // multiplication operation is performed  
28. Console.WriteLine("The product of the first and second number is " + result);  
29. break;  
30. case '/':  
31. if (snum != 0)  
32.                     {  
33. result = fnum / snum;// division operation is performed  
34. Console.WriteLine("The division of first and second number is " + result);  
35.                     }  
36. break;  
37. default:  
38. Console.WriteLine("Invalid operator.");  
39. break;  
40.             }  
41.         }  
42.     }  
43. }  

**Output:**

Enter the first number: 15
Enter the second number: 20
Enter the operator (+, -, *, /): +
The sum of the first and second numbers is 35

**Explanation:**

In this example, we demonstrate a simple arithmetic operation. After that, we have taken two variables character and double type. Next, the user is prompted to enter any two numbers and choose any operations. After that, the switch statement calculates the numbers and prints the result using the Console.WriteLine() function.

## Rules for Using Switch Statements

There are several rules for using switch statements in C#. Some of them are as follows:

- In [C#](https://www.tpointtech.com/c-sharp-tutorial), we have to use an integral type (such as int and char) inside every switch expression.
- Every switch statement contains multiple cases.
- When a case matches, the code executes until a break statement is reached.
- Every case must end with a break keyword to stop the execution.
- Every case label should be followed by colon ":".
- The outer and inner switch statements can have to use a default case.
- The default case of the switch statement is also optional.

## C# Nested Switch Case

In C#, a nested switch statement is a type of control statement where a switch statement contains another switch statement. It is used when a multi-level decision has to be taken on different conditions.

**Syntax of Nested Switch Case**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-switch#)[](https://www.tpointtech.com/c-sharp-switch#)[](https://www.tpointtech.com/c-sharp-switch#)

1. Switch(ch1)  
2. {  
3. Case 'A':  
4. Console.WriteLine(" first part of the switch statement.");  
5. Switch(ch2)  
6. {  
7. case 'A':  
8. Console.WriteLine("Second part of the switch statement.");  
9. break;  
10. case 'B':    // inner second part of case code.  
11. }  
12. break;  
13. case 'B':  // outer second part of case code.  
14. }  

### C# Nested Switch Case Example

Let us take an example to illustrate the nested switch statement in C#.

### Example

[](https://www.tpointtech.com/c-sharp-switch#)[](https://www.tpointtech.com/c-sharp-switch#)[](https://www.tpointtech.com/c-sharp-switch#)

1. using System;  
2. namespace NestedSwitchCase {  
3. class Program {  
4. static void Main(string[] args) {  
5. int x = 50;  
6. int y = 100;  
7. switch (x) {  //outer switch case  
8. case 50:   
9. Console.WriteLine("This is the first part of the switch statement. ");  
10. switch (y) {   //inner switch case  
11. case 100:  
12. Console.WriteLine("This is the second part of the switch statement. ");  
13. break;  
14.             }  
15. break;  
16.          }  
17. Console.WriteLine("The exact value of x is {0} ", x);  
18. Console.WriteLine("The exact value of y is {0}", y);  
19. Console.ReadLine();  
20.       }  
21.    }  
22. }  

**Output:**

This is the first switch statement.
This is part of the second switch statement.
The exact value of x is 50
The exact value of y is 100

**Explanation:**

In this example, we have taken an integer data type x and y. After that, the program uses nested switch statements to check the values of x and y. Finally, it checks the condition and prints the result using Consle.WriteLine() function.

## Features of Switch Statement

The switch statement has several features in C#. Some of them are as follows:

- In C#, the switch statement is easy to implement as compared if-else statement.
- It makes it easy to execute the complicated problem.
- It handles multiple cases.
- In cases where a variable is compared in many constant values, the switch is usually faster and more efficient than if-else due to compiler optimization.

## Limitations of Switch Statement

In C#, the switch statement has several limitations. Some of them are as follows:

- We cannot use the float value in a switch statement.
- It cannot handle complex case conditions or expressions.
- We cannot compare the non-integer type value.

## Conclusion

In conclusion, the switch statement allows us to solve the critical problem in programming. It is the collection of multiple cases and handling them efficiently. It is beneficial for programmers to handle complicated scenarios.