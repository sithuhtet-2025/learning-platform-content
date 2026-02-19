
In the C# programming language, the Params keyword is used to define a parameter that accepts a variable number of arguments. It is an important keyword in C#. It enables calling a method with zero or more arguments without explicitly creating an array and allows a method to accept a variable number of arguments of specific data. It must be used in a Single-dimensional array.

## Params Example in C#

Let us take an example to illustrate the Params keyword in C#.

### Example

[](https://www.tpointtech.com/c-sharp-params#)[](https://www.tpointtech.com/c-sharp-params#)[](https://www.tpointtech.com/c-sharp-params#)

1. using System;  
2. namespace AccessSpecifiers  
3. {  
4.     class Program  
5.     {  
6.         // define a method for integers  
7.         public void Show(params int[] num_bers)  
8.         {  
9.             Console.WriteLine("The integer values are ");  
10.             foreach (int num1 in num_bers)  
11.             {  
12.                 Console.WriteLine(num1);  
13.             }  
14.         }  
15.         // create a method for strings  
16.         public void Show(params string[] messages)  
17.         {  
18.             Console.WriteLine("The String values are ");  
19.             foreach (string msg in messages)  
20.             {  
21.                 Console.WriteLine(msg);  
22.             }  
23.         }  
24.         static void Main(string[] args)  
25.         {  
26.             Program p1 = new Program();  
27.             // Call with integer values  
28.             p1.Show(1, 2, 3, 4, 5);  
29.             // method call with string  
30.             p1.Show("Hello", "World", "C#", "Params");  
31.         }  
32.     }  
33. }   

**Output:**

The integer values are
1
2
3
4
5
The String values are
Hello
World
C#
Params

**Explanation:**

In this example, we demonstrate how to define the Params keyword in C#. First, we create two methods: one takes any number of integers, and the other takes any number of strings. In the main() method, we create an instance of the Program class and call the Show() method. Finally, we use the Console.WriteLine() function to print the output.

### Using the params Keyword for Variable Number of Arguments in C#

Let us take an example to illustrate how to use the params keyword for a variable number of arguments in C#.

### Example

[](https://www.tpointtech.com/c-sharp-params#)[](https://www.tpointtech.com/c-sharp-params#)[](https://www.tpointtech.com/c-sharp-params#)

1. using System;    
2. namespace AccessSpecifiers    
3. {     
4.     class Program    
5.     {    
6.         // define a method for object  
7.         public void DisplayItems(params object[] items)     
8.         {    
9.             for ( int i = 0; i < items.Length; i++ )    
10.             {    
11.                 Console.WriteLine( items[i] );    
12.             }       
13.         }    
14.         // Main function, execution entry point of the program    
15.         static void Main(string[] args)    
16.         {    
17.             Program p = new Program();   
18.             p.DisplayItems("Krishna", "John", 11, 20.5, "Peter", 'X'); // Passing arguments of variable length    
19.         }       
20.     }    
21. }   

**Output:**

Krishna
John
11
20.5
Peter
X

**Explanation:**

In this example, we demonstrate how to use params for a variable number of arguments. First, we define the method named DisplayItems() that accepts a variable number of arguments of any type. After that, we use a for loop to iterate over each item in the array and print it by using the Console.WriteLine() function. In the main() method, we create an object of the program class and call the DisplayItem() method.

### Program to add the element of an array passed to the method in C#

Let us take an example to illustrate how we can add the element of an array that is passed to the method in C#.

### Example

[](https://www.tpointtech.com/c-sharp-params#)[](https://www.tpointtech.com/c-sharp-params#)[](https://www.tpointtech.com/c-sharp-params#)

1. using System;     
2. class tech  
3. {  
4.     // create a method using params   
5.     public static int Sum(params int[] numbers)  
6.     {  
7.         int sum1 = 0;  
8.         // Loop through each number and add to sum  
9.         foreach (int num in numbers)  
10.         {  
11.             sum1 += num;  
12.         }  
13.         return sum1;  
14.     }  
15.     // Main Method  
16.     static void Main(string[] args)  
17.     {  
18.         // Calling the method with different numbers  
19.         int result = Sum(10, 20, 30, 40, 50);  

20.         // Display the outcome  
21.         Console.WriteLine("The total sum of the given numbers is " + result);  
22.     }  
23. }  

**Output:**

The total sum of the given numbers is 150

**Explanation:**

In this example, we create a method named Sum that takes any number of integer arguments. After that, we use the foreach loop to calculate the sum of the given numbers. In the main method, we call the method Sum() with five integer values (10, 20, 30, 40, 50). Finally, it displays the output using the Console.WriteLine() function.

## Why use the params Keyword in C#?

In the C# programming language, a params keyword is mainly utilized to define a parameter that accepts a variable number of arguments. Instead of creating multiple overloaded methods for different parameters, we can define a single method that automatically handles any number of inputs. It helps to improve the code readability and maintainability. It can simply pass an array as an argument.

## Rules for Creating the Params in C#

There are several rules that help to create the params in C#. Some of them are as follows:

1. **Only one params parameter allowed:** We can use only one parameter in a method, and it must appear at the end.
2. **Must be a Single-Dimensional Array:** It must be a single-dimensional array, and all arguments passed to it must match the specified array type.
3. **Empty array:** If no arguments are passed to the parameters, it will be treated as an empty array.

## Benefits of Params in C#

Several benefits of params in C# are as follows:

- **Simplifies Method Overloading:** Without params, we have to create multiple overloaded methods to handle different numbers of arguments. If we are using params, it enables us to write a single method that can accept a variable number of arguments, which makes the code simpler and more maintainable.
- **Support Implicit Array:** When we are using params, the compiler automatically wraps the provided arguments as an array. So, there is no requirement to create it explicitly.
- **Flexibility:** The param keyword provides flexibility in C#. We can pass zero or multiple arguments to the method. It acts as an optional array parameter.
- **Improved Readability:** The params keyword helps us to avoid the many versions of the same methods for different numbers of inputs. Instead of creating multiple methods, we can write only one method using params, which automatically handles any number of arguments passed to it.

## Conclusion

In conclusion, the params keyword is an essential feature in creating functions to create a software application. It enables calling a method with zero or more arguments without explicitly creating an array and allows a method to accept a variable number of arguments of specific data. It helps to improve the code flexibility, readability, and eliminates the requirement to overload methods for different numbers of parameters.