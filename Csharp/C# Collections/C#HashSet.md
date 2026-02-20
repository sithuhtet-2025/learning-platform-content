C# HashSet class can be used to store, remove or view elements. It does not store duplicate elements. It is suggested to use HashSet class if you have to store only unique elements. It is found in System.Collections.Generic namespace.

### C# HashSet<T> example

Let's see an example of generic HashSet<T> class that stores elements using Add() method and iterates elements using for-each loop.

[](https://www.tpointtech.com/c-sharp-hashset#)[](https://www.tpointtech.com/c-sharp-hashset#)[](https://www.tpointtech.com/c-sharp-hashset#)

1. using System;  
2. using System.Collections.Generic;  

3. public class HashSetExample  
4. {  
5.     public static void Main(string[] args)  
6.     {  
7.         // Create a set of strings  
8.         var names = new HashSet<string>();  
9.         names.Add("Sonoo");  
10.         names.Add("Ankit");  
11.         names.Add("Peter");  
12.         names.Add("Irfan");  
13.         names.Add("Ankit");//will not be added  

14.         // Iterate HashSet elements using foreach loop  
15.         foreach (var name in names)  
16.         {  
17.             Console.WriteLine(name);  
18.         }  
19.     }  
20. }  

Output:

Sonoo
Ankit
Peter
Irfan

### C# HashSet<T> example 2

Let's see another example of generic HashSet<T> class that stores elements using Collection initializer.

[](https://www.tpointtech.com/c-sharp-hashset#)[](https://www.tpointtech.com/c-sharp-hashset#)[](https://www.tpointtech.com/c-sharp-hashset#)

1. using System;  
2. using System.Collections.Generic;  

3. public class HashSetExample  
4. {  
5.     public static void Main(string[] args)  
6.     {  
7.         // Create a set of strings  
8.         var names = new HashSet<string>(){"Sonoo", "Ankit", "Peter", "Irfan"};  

9.         // Iterate HashSet elements using foreach loop  
10.         foreach (var name in names)  
11.         {  
12.             Console.WriteLine(name);  
13.         }  
14.     }  
15. }  

Output:

Sonoo
Ankit
Peter
Irfan