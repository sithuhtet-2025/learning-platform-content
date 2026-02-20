C# SortedDictionary<TKey, TValue> class uses the concept of hashtable. It stores values on the basis of key. It contains unique keys and maintains ascending order on the basis of key. By the help of key, we can easily search or remove elements. It is found in System.Collections.Generic namespace.

### C# SortedDictionary<TKey, TValue> example

Let's see an example of generic SortedDictionary<TKey, TValue> class that stores elements using Add() method and iterates elements using for-each loop. Here, we are using KeyValuePair class to get key and value.

[](https://www.tpointtech.com/c-sharp-sorteddictionary#)[](https://www.tpointtech.com/c-sharp-sorteddictionary#)[](https://www.tpointtech.com/c-sharp-sorteddictionary#)

1. using System;  
2. using System.Collections.Generic;  

3. public class SortedDictionaryExample  
4. {  
5.     public static void Main(string[] args)  
6.     {  
7.         SortedDictionary<string, string> names = new SortedDictionary<string, string>();  
8.         names.Add("1","Sonoo");    
9.         names.Add("4","Peter");    
10.         names.Add("5","James");    
11.         names.Add("3","Ratan");    
12.         names.Add("2","Irfan");    
13.         foreach (KeyValuePair<string, string> kv in names)  
14.         {  
15.             Console.WriteLine(kv.Key+" "+kv.Value);  
16.         }  
17.     }  
18. }  

Output:

1 Sonoo
2 Irfan
3 Ratan
4 Peter
5 James