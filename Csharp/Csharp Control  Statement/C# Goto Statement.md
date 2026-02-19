In C#, the **_Goto statement_** is also known jump statement. It is used to transfer control to the other part of the program. It unconditionally jumps to the specified label. The goto statement can be employed to shift control from a deeply nested switch case label or loop.

### Syntax:

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-goto-statement#)[](https://www.tpointtech.com/c-sharp-goto-statement#)[](https://www.tpointtech.com/c-sharp-goto-statement#)

1. goto label;  
2. . . .  
3. label:   
4. // Code to be executed after the jump  

In [C#](https://www.tpointtech.com/c-sharp-tutorial), goto is utilized to jump to a labeled statement using the same method. It is typically employed to jump to a particular location in the code.

### Flowchart of the Goto Statement:

![C# Goto Statement](https://images.tpointtech.com/csharp/images/c-sharp-goto-statement.png)

As we can see in the flowchart, use the following steps to implement the C# Goto Statement:

**Step 1:** The program starts from the Start block.

**Step 2:** It executes the first Statement.

**Step 3:** Subsequently, it tests a condition to determine if it should use a goto Label 2.

**Step 4:** When goto is called, the control skips ahead directly to Label 2, bypassing Statement 1.

**Step 5:** In the alternative case, it jumps sequentially to Statement 1 and next to Statement 2.

**Step 6:** Following the execution of Statement 2, the path continues on to the End.

## C# Goto Statement Example

Let's see the simple example of the goto statement in C#.

### Example

[](https://www.tpointtech.com/c-sharp-goto-statement#)[](https://www.tpointtech.com/c-sharp-goto-statement#)[](https://www.tpointtech.com/c-sharp-goto-statement#)

1. using System;    
2. public class GotoExample    
3.     {    
4.       public static void Main(string[] args)    
5.       {    
6.       ineligible:    
7.           Console.WriteLine("You are not eligible to vote!");    

8.       Console.WriteLine("Enter your age:\n");    
9.       int age = Convert.ToInt32(Console.ReadLine());    
10.       if (age < 18){    
11.               goto ineligible;    
12.       }    
13.       else    
14.       {    
15.               Console.WriteLine("You are eligible to vote!");     
16.       }    
17.       }    
18.    }    

**Output:**

You are not eligible to vote!
Enter your age:
11
You are not eligible to vote!
Enter your age:
5
You are not eligible to vote!
Enter your age:
26
You are eligible to vote!

## C# Goto Statement with for Loop

In C#, the goto statement shifts control to a marked statement within the same method. Although it is seldom advisable because it can make the code less readable, it can be used to break out of nested loops or bypass sections of code in specific situations.

**Syntax:**

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-goto-statement#)[](https://www.tpointtech.com/c-sharp-goto-statement#)[](https://www.tpointtech.com/c-sharp-goto-statement#)

1. for (initialization; condition; updatation)  
2. {  
3.     if (expression)  
4.     {  
5.         goto label;  // Jump to the labeled statement  
6.     }  
7.     // Code to be executed if 'goto' is not hit  
8. }  
9. label:  
10. // Code to be executed after the jump  

### C# Goto Statement Example using for Loop:

Let us take an example to illustrate the Goto statement with for loop in the C#.

### Example

[](https://www.tpointtech.com/c-sharp-goto-statement#)[](https://www.tpointtech.com/c-sharp-goto-statement#)[](https://www.tpointtech.com/c-sharp-goto-statement#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {  
6.         for (int i = 1; i <= 10; i++)  
7.         {  
8.             if (i == 6)  
9.             {  
10.                 goto End;    
11.             }  
12.             Console.WriteLine(i);  
13.         }  
14.     End:  
15.         Console.WriteLine("Loop terminated at 6.");  
16.     }  
17. }  

**Output:**

1
2
3
4
5
Loop Terminated at 6

**Explanation:**

In this example, the for loop iterates through numbers from 1 to 10. When i is 6, the goto End; instruction is carried out, transferring to the End: label. The loop is terminated early, and the message "Loop terminated at 6." is printed.

## C# Goto statement with Switch Statement

In C#, the goto statement can be used inside a switch statement to jump to a particular case label or default label. It is beneficial when you need to transfer control from one case to another.

**Syntax**

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-goto-statement#)[](https://www.tpointtech.com/c-sharp-goto-statement#)[](https://www.tpointtech.com/c-sharp-goto-statement#)

1. switch (expression)  
2. {  
3.     case value1:  
4.         // Code for case 1  
5.         goto case value2;  // Jump to another case  
6.     case value2:  
7.         // Code for case 2  
8.         break;  
9.     default:  
10.         // Default case code  
11.         break;  
12. }  

### C# Goto Statement Example using Switch Statement

Let us take an example to illustrate the goto statement with the switch statement in C#.

### Example

[](https://www.tpointtech.com/c-sharp-goto-statement#)[](https://www.tpointtech.com/c-sharp-goto-statement#)[](https://www.tpointtech.com/c-sharp-goto-statement#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {  
6.         int day = 3;  
7.         Console.WriteLine("Day number: " + day);  
8.         switch (day)  
9.         {  
10.             case 1:  
11.                 Console.WriteLine("Monday");  
12.                 break;  
13.             case 2:  
14.                 Console.WriteLine("Tuesday");  
15.                 break;  
16.             case 3:  
17.                 Console.WriteLine("Wednesday");  
18.                 goto case 5;    
19.             case 4:  
20.                 Console.WriteLine("Thursday");  
21.                 break;  
22.             case 5:  
23.                 Console.WriteLine("Friday");  
24.                 break;  
25.             default:  
26.                 Console.WriteLine("Invalid day");  
27.                 break;  
28.         }  
29.         Console.WriteLine("End of the program.");  
30.     }  
31. }  

**Output:**

Day number: 3
Wednesday
Friday
End of the program.

**Explanation**

In this example, the switch statement checks the value of the day, which is 3. The control belongs to case 3 and outputs "Wednesday". After that, in the goto case 5; instruction goes directly to case 5.

After that, the "Friday" is printed, and the control leaves the switch thereafter. Finally, the program prints "End of the program.".

## C# Goto with Nested Loops

In C#, you can use the goto keyword in nested loops to break more than one loop at the same time or to transfer to a marked statement. You can use it if you want to break all the loops at once under some specific condition.

**Syntax**

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-goto-statement#)[](https://www.tpointtech.com/c-sharp-goto-statement#)[](https://www.tpointtech.com/c-sharp-goto-statement#)

1. for (initialization; condition; update)  
2. {  
3.     for (initialization; condition; update)  
4.     {  
5.         if (expression)  
6.         {  
7.             goto label;  // Jump to the labeled statement  
8.         }  
9.         // Inner loop code  
10.     }  
11.     // Outer loop code  
12. }  
13. label:   
14. // Code to be executed after the jump  

### C# Goto Statement Example using Nested Loop

Let us take an example to illustrate the Goto Statement with the nested loop in C#.

### Example

[](https://www.tpointtech.com/c-sharp-goto-statement#)[](https://www.tpointtech.com/c-sharp-goto-statement#)[](https://www.tpointtech.com/c-sharp-goto-statement#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {  
6.         Console.WriteLine("Checking students marks to find the target:");  
7.         string[] students = { "Alice", "Bob", "Charlie", "David", "Eva" };  
8.         int[] marks = { 85, 90, 78, 92, 88 };  
9.         foreach (string i in students)    
10.         {  
11.             foreach (int j in marks)    
12.             {  
13.                 Console.WriteLine($"Checking marks of {i}: {j}");  
14.                 if (i == "Bob" && j == 90)  
15.                 {  
16.                     Console.WriteLine("Target student found: Bob with 90 marks!");  
17.                     goto End;    
18.                 }  
19.             }  
20.         }  
21.     End:  
22.         Console.WriteLine("Process completed.");  
23.     }  
24. }  

**Output:**

Checking students marks to find the target:
Checking marks of Alice: 85
Checking marks of Alice: 90
Checking marks of Alice: 78
Checking marks of Alice: 92
Checking marks of Alice: 88
Checking marks of Bob: 85
Checking marks of Bob: 90
Target student found: Bob with 90 marks!
Process completed.

**Explanation**

In this example, we iterate over a list of students and cross them out through nested for-each loops. After that, it checks every combination to find student "Bob" with a score of 90.

Once discovered, it displays a message indicating that the target is found and uses the goto statement to break both loops simultaneously. Finally, it shows "Process completed." to signal completion of execution.

## Conclusion

In conclusion, the goto instruction in C# provides a mechanism for passing control directly to a labeled statement in the same procedure. While useful in some specific cases, such as breaking from deeply nested loops or the design of finite state machines. Otherwise, it is considered bad practice because it makes code harder to read and maintain.