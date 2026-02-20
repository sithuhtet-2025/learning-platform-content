C# LinkedList<T> class uses the concept of linked list. It allows us to insert and delete elements fastly. It can have duplicate elements. It is found in System.Collections.Generic namespace.

It allows us to add and remove element at before or last index.

### C# LinkedList<T> example

Let's see an example of generic LinkedList<T> class that stores elements using AddLast() and AddFirst() methods and iterates elements using for-each loop.

[](https://www.tpointtech.com/c-sharp-linkedlist#)[](https://www.tpointtech.com/c-sharp-linkedlist#)[](https://www.tpointtech.com/c-sharp-linkedlist#)

1. using System;  
2. using System.Collections.Generic;  

3. public class LinkedListExample  
4. {  
5.     public static void Main(string[] args)  
6.     {  
7.         // Create a list of strings  
8.         var names = new LinkedList<string>();  
9.         names.AddLast("Sonoo Jaiswal");  
10.         names.AddLast("Ankit");  
11.         names.AddLast("Peter");  
12.         names.AddLast("Irfan");  
13.         names.AddFirst("John");//added to first index  

14.         // Iterate list element using foreach loop  
15.         foreach (var name in names)  
16.         {  
17.             Console.WriteLine(name);  
18.         }  
19.     }  
20. }  

Output:

John
Sonoo Jaiswal
Ankit
Peter
Irfan

#### Note: Unlike List, you cannot create LinkedList using Collection initializer.

### C# LinkedList<T> example 2

Let's see another example of generic LinkedList<T> class that stores elements before and after specific node. To get the specific node, we are calling Find() method.

[](https://www.tpointtech.com/c-sharp-linkedlist#)[](https://www.tpointtech.com/c-sharp-linkedlist#)[](https://www.tpointtech.com/c-sharp-linkedlist#)

1. using System;  
2. using System.Collections.Generic;  

3. public class LinkedListExample  
4. {  
5.     public static void Main(string[] args)  
6.     {  
7.         // Create a list of strings  
8.         var names = new LinkedList<string>();  
9.         names.AddLast("Sonoo");  
10.         names.AddLast("Ankit");  
11.         names.AddLast("Peter");  
12.         names.AddLast("Irfan");  

13.         //insert new element before "Peter"  
14.         LinkedListNode<String> node=names.Find("Peter");  
15.         names.AddBefore(node, "John");  
16.         names.AddAfter(node, "Lucy");  

17.         // Iterate list element using foreach loop  
18.         foreach (var name in names)  
19.         {  
20.             Console.WriteLine(name);  
21.         }  
22.     }  
23. }  

Output:

Sonoo
Ankit
John
Peter
Lucy
Irfan

As you can see in the above output "John" and "Lucy" are added before and after "Peter".