C# Queue<T> class is used to Enqueue and Dequeue elements. It uses the concept of Queue that arranges elements in FIFO (First In First Out) order. It can have duplicate elements. It is found in System.Collections.Generic namespace.

### C# Queue<T> example

Let's see an example of generic Queue<T> class that stores elements using Enqueue() method, removes elements using Dequeue() method and iterates elements using for-each loop.

[](https://www.tpointtech.com/c-sharp-queue#)[](https://www.tpointtech.com/c-sharp-queue#)[](https://www.tpointtech.com/c-sharp-queue#)

1. using System;  
2. using System.Collections.Generic;  

3. public class QueueExample  
4. {  
5.     public static void Main(string[] args)  
6.     {  
7.         Queue<string> names = new Queue<string>();  
8.         names.Enqueue("Sonoo");  
9.         names.Enqueue("Peter");  
10.         names.Enqueue("James");  
11.         names.Enqueue("Ratan");  
12.         names.Enqueue("Irfan");  

13.         foreach (string name in names)  
14.         {  
15.             Console.WriteLine(name);  
16.         }  

17.         Console.WriteLine("Peek element: "+names.Peek());  
18.         Console.WriteLine("Dequeue: "+ names.Dequeue());  
19.         Console.WriteLine("After Dequeue, Peek element: " + names.Peek());  
20.     }  
21. }  

Output:

Sonoo
Peter
James
Ratan
Irfan
Peek element: Sonoo
Dequeue: Sonoo
After Dequeue, Peek element: Peter