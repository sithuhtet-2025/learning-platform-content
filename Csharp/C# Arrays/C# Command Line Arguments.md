
In the C# programming language, the command line arguments are used to pass the value from the user or programmer to the program at the time of execution. It is a straightforward method for passing a message between the user and the main() method of the program. The values are passed through the command line, known as the command line arguments.

### Syntax of Command Line Arguments

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-command-line-arguments#)[](https://www.tpointtech.com/c-sharp-command-line-arguments#)[](https://www.tpointtech.com/c-sharp-command-line-arguments#)

1. Static void main (string[] args)  
2. {     
3. // block of code  
4. }  

In the above syntax,

- **Static:** It represents that the Main() method can execute without any object.
- **string []:** It is the type of arguments that is passed to the method.
- **Args:** It represents the arguments which is defined by the user.

### Command-Line Arguments Example in C#

Let us take an example that sums two numbers passed through arguments.

### Example

[](https://www.tpointtech.com/c-sharp-command-line-arguments#)[](https://www.tpointtech.com/c-sharp-command-line-arguments#)[](https://www.tpointtech.com/c-sharp-command-line-arguments#)

1. using System;    
2. namespace CSharpProgram    
3. {  
4.     class Program    
5.     {    
6.         // Main Method  
7.         static void Main( string[] args ) // string type parameters    
8.         {     
9.             Console.WriteLine(" The number of input is "+args.Length );    
10.             Console.WriteLine(" The Supplied Arguments are: ");    
11.             foreach (object o in args )    
12.             {    
13.                 Console.WriteLine(obj);         
14.             }    
15.         }    
16.     }    
17. }   

Compile and execute this program by using the following commands.

**Compile:** csc program.cs

**Execute:** Program.exe Hi there, how are you?

**Output:**

Argument length: 5
Supplied Arguments are:
Hi
there,
how
are
you.

**Explanation:**

In this example, we print the number of arguments using args.Length and then using the foreach loop to iterate over each argument one by one. Finally, we are using the Console.WriteLine() function to display the output.

## How do Command Line Arguments Work in C#?

In the [C# programming language](https://www.tpointtech.com/c-sharp-tutorial), the command line arguments are passed to the program through the main() method when it is executed from the command line. These command-line arguments can be accessed inside the main() method.

## Passing Arguments to the Main Method

In C#, the arguments are passed to the main method through command-line arguments at the time of program execution. The Main() method serves as the entry point of a C# application and can accept an array of strings (string[] args) as a parameter to receive these arguments in the C# program.

### Passing Arguments Example in C#

Let's take an illustrate example to pass the arguments in the main method.

### Example

[](https://www.tpointtech.com/c-sharp-command-line-arguments#)[](https://www.tpointtech.com/c-sharp-command-line-arguments#)[](https://www.tpointtech.com/c-sharp-command-line-arguments#)

1. using System;  
2. class Program  
3. {  
4.     static void Main( string[] args )  
5.     {  
6.         Console.WriteLine(" The number of arguments passed: " + args.Length );  
7.         for ( int i = 0; i < args.Length; i++ )  
8.         {  
9.             Console.WriteLine(" The Argument " + (i + 1) + ": " + args[i] );  
10.         }  
11.     }  
12. }  

**Output:**

The number of arguments passed: 0

**Explanation:**

In this example, we are demonstrating how to use the command line arguments. In the main() method, we take a string[] args, which stores all the values passed when executing the program. After that, we are printing the total number of arguments, and then we use a for loop to print each argument using the Console.WriteLine() function.

### Factorial Program using Command Line Arguments in C#

Let's take an illustrate example to calculate the factorial numbers using the C# command line arguments.

### Example

[](https://www.tpointtech.com/c-sharp-command-line-arguments#)[](https://www.tpointtech.com/c-sharp-command-line-arguments#)[](https://www.tpointtech.com/c-sharp-command-line-arguments#)

1. using System;  
2. using System.IO;  
3. using System.Collections.Generic;  
4. namespace ConsoleApp4  
5. {  
6. class Program  
7. {  
8. public static void Main(string[] args)  
9. {  
10. int num;  
11. int fact;  
12. try  
13. {  
14. if (args.Length == 0)  
15. {  
16. Console.WriteLine("Enter a number to calculate its factorial " + "its fact");  
17. return;  
18. }  
19. if(args.Length > 1)  
20. {  
21. Console.WriteLine("Enter a number for your choice");  
22. return;  
23. }  
24. Console.WriteLine("The number entered is: " + args[0]);  
25. num = Convert.ToInt32(args[0]);  
26. fact = num;  
27. //determine factorial  
28. for( int i = num - 1; i >= 1; i-- )  
29. {  
30. fact = fact * i;  
31. }  
32. Console.WriteLine("The factorial of {0} is {1}", args[0], fact);  
33. Console.ReadLine();  
34. }  
35. catch(Exception ex)  
36. {  
37. Console.WriteLine(ex.Message);  
38. }  
39. }  
40. }  
41. }  

**Output:**

Enter a number to calculate its factorial: 5
The factorial of 5 is: 120

**Explanation:**

In the above example, first, it verifies that the input is provided. If not, it asks for a number. If the input is valid, the program converts it into an integer and calculates the factorial using a loop. The result is shown using Console.WriteLine() function.

### Program: Check Even or Odd Number via C# Command Line Arguments.

Let's take an illustrate example to check whether the number is even or odd using C# command line arguments.

### Example

[](https://www.tpointtech.com/c-sharp-command-line-arguments#)[](https://www.tpointtech.com/c-sharp-command-line-arguments#)[](https://www.tpointtech.com/c-sharp-command-line-arguments#)

1. using System;  
2. using System.IO;  
3. using System.Collections.Generic;  
4. namespace Console  
5. {  
6. class Program  
7. {  
8. public static void Main( string [] args )  
9. {  
10. List<int> even_Array = new List<int>();  
11. List<int> odd_Array = new List<int>();  
12. try  
13. {  
14. if ( args.Length == 0 )  
15. {  
16. Console.WriteLine("Enter numbers your choice ");  
17. return;  
18. }  
19. for ( int i = 0; i < args.Length; i++ )  
20. {  
21. if ((Convert.ToInt32(args[i]) % 2) == 0)  
22. {  
23. even_Array.Add(Convert.ToInt32(args[i]));  
24. }  
25. else  
26. {  
27. odd_Array.Add(Convert.ToInt32(args[i]));  
28. }  
29. }  
30. // printing all the numbers entered  
31. Console.WriteLine("The entered number is ");  
32. for (int i = 0; i < args.Length; i++)  
33. {  
34. Console.WriteLine(args[i]);  
35. }  
36. Console.WriteLine("\n The Even numbers are ");  
37. for (int i = 0; i < even_Array.Count; i++)  
38. {  
39. Console.WriteLine(even_Array[i]);  
40. }  
41. Console.WriteLine("\n The Odd numbers are ");  
42. for ( int i = 0; i < odd_Array.Count; i++ )  
43. {  
44. Console.WriteLine(odd_Array[i]);  
45. }  
46. Console.ReadLine();  
47. }  
48. catch(Exception ex)  
49. {  
50. Console.WriteLine( ex.Message );  
51. }  
52. }  
53. }  
54. }  

**Output:**

10 7 4 3 12 9
Numbers entered:
10
7
4
3
12
9
Even numbers:
10
4
12
Odd numbers:
7
3
9

**Explanation:**

In this example, we take multiple numbers from the command line and separate them into even and odd numbers. First, we check if any arguments are provided. If the arguments are not provided, it shows a message to enter a number. After that, we use a [for loop](https://www.tpointtech.com/c-sharp-for-loop) to access the arguments and convert them into an integer, and then it checks whether the number is even or odd. Finally, we are using the Console.WriteLine() function to print the output.

## Conclusion

The command line arguments are used to pass the value from the user or programmer to the program. It is a simple method for message passing between the user and the main method. The values are passed by the command line, known as the command line arguments.