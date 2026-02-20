C# List<T> class is used to store and fetch elements. It can have duplicate elements. It is found in System.Collections.Generic namespace.

### C# List<T> example

Let's see an example of generic List<T> class that stores elements using Add() method and iterates the list using for-each loop.

[](https://www.tpointtech.com/c-sharp-list#)[](https://www.tpointtech.com/c-sharp-list#)[](https://www.tpointtech.com/c-sharp-list#)

1. using System;  
2. using System.Collections.Generic;  

3. public class ListExample  
4. {  
5.     public static void Main(string[] args)  
6.     {  
7.         // Create a list of strings  
8.         var names = new List<string>();  
9.         names.Add("Sonoo Jaiswal");  
10.         names.Add("Ankit");  
11.         names.Add("Peter");  
12.         names.Add("Irfan");  

13.         // Iterate list element using foreach loop  
14.         foreach (var name in names)  
15.         {  
16.             Console.WriteLine(name);  
17.         }  
18.     }  
19. }  

Output:

Sonoo Jaiswal
Ankit
Peter
Irfan

### C# List<T> example using collection initializer

[](https://www.tpointtech.com/c-sharp-list#)[](https://www.tpointtech.com/c-sharp-list#)[](https://www.tpointtech.com/c-sharp-list#)

1. using System;  
2. using System.Collections.Generic;  

3. public class ListExample  
4. {  
5.     public static void Main(string[] args)  
6.     {  
7.         // Create a list of strings using collection initializer  
8.         var names = new List<string>() {"Sonoo", "Vimal", "Ratan", "Love" };  

9.         // Iterate through the list.  
10.         foreach (var name in names)  
11.         {  
12.             Console.WriteLine(name);  
13.         }  
14.     }  
15. }  

Output:

Sonoo
Vimal
Ratan
Love