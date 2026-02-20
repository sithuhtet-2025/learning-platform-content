C# SortedSet class can be used to store, remove or view elements. It maintains ascending order and does not store duplicate elements. It is suggested to use SortedSet class if you have to store unique elements and maintain ascending order. It is found in System.Collections.Generic namespace.

### C# SortedSet<T> example

Let's see an example of generic SortedSet<T> class that stores elements using Add() method and iterates elements using for-each loop.

[](https://www.tpointtech.com/c-sharp-sortedset#)[](https://www.tpointtech.com/c-sharp-sortedset#)[](https://www.tpointtech.com/c-sharp-sortedset#)

1. using System;  
2. using System.Collections.Generic;  

3. public class SortedSetExample  
4. {  
5.     public static void Main(string[] args)  
6.     {  
7.         // Create a set of strings  
8.         var names = new SortedSet<string>();  
9.         names.Add("Sonoo");  
10.         names.Add("Ankit");  
11.         names.Add("Peter");  
12.         names.Add("Irfan");  
13.         names.Add("Ankit");//will not be added  

14.         // Iterate SortedSet elements using foreach loop  
15.         foreach (var name in names)  
16.         {  
17.             Console.WriteLine(name);  
18.         }  
19.     }  
20. }  

Output:

Ankit
Irfan
Peter
Sonoo

### C# SortedSet<T> example 2

Let's see another example of generic SortedSet<T> class that stores elements using Collection initializer.

[](https://www.tpointtech.com/c-sharp-sortedset#)[](https://www.tpointtech.com/c-sharp-sortedset#)[](https://www.tpointtech.com/c-sharp-sortedset#)

1. using System;  
2. using System.Collections.Generic;  

3. public class SortedSetExample  
4. {  
5.     public static void Main(string[] args)  
6.     {  
7.         // Create a set of strings  
8.         var names = new SortedSet<string>(){"Sonoo", "Ankit", "Peter", "Irfan"};  

9.         // Iterate SortedSet elements using foreach loop  
10.         foreach (var name in names)  
11.         {  
12.             Console.WriteLine(name);  
13.         }  
14.     }  
15. }  

Output:

Ankit
Irfan
Peter
Sonoo