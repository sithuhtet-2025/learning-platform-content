C# Dictionary<TKey, TValue> class uses the concept of hashtable. It stores values on the basis of key. It contains unique keys only. By the help of key, we can easily search or remove elements. It is found in System.Collections.Generic namespace.

### C# Dictionary<TKey, TValue> example

Let's see an example of generic Dictionary<TKey, TValue> class that stores elements using Add() method and iterates elements using for-each loop. Here, we are using KeyValuePair class to get key and value.

[](https://www.tpointtech.com/c-sharp-dictionary#)[](https://www.tpointtech.com/c-sharp-dictionary#)[](https://www.tpointtech.com/c-sharp-dictionary#)

1. using System;  
2. using System.Collections.Generic;  

3. public class DictionaryExample  
4. {  
5.     public static void Main(string[] args)  
6.     {  
7.         Dictionary<string, string> names = new Dictionary<string, string>();  
8.         names.Add("1","Sonoo");  
9.         names.Add("2","Peter");  
10.         names.Add("3","James");  
11.         names.Add("4","Ratan");  
12.         names.Add("5","Irfan");  

13.         foreach (KeyValuePair<string, string> kv in names)  
14.         {  
15.             Console.WriteLine(kv.Key+" "+kv.Value);  
16.         }  
17.     }  
18. }  

Output:

1 Sonoo
2 Peter
3 James
4 Ratan
5 Irfan