In the C# programming language, a collection represents a group of objects. It includes a set of classes to hold elements in a generalized way. The collections are commonly used to store, update, delete, retrieve, search, and sort objects. Instead of working with single variables, a collection enables us to handle several items in an efficient and structured manner. These are part of the System.Collections, System.Collection.Generic, and System.Collections.Concurrent namespaces in .NET Framework.

In C#, collections provide several features, including dynamic resizing, searching, sorting, and easy data access, which makes them very useful in real-world application development. In short, all the data structure work can be performed by C# collections.

We can store objects in an array or collection. A collection has an advantage over an array. An array has a size limit. On the other hand, the collection can grow or shrink dynamically when we store objects.

## Types of Collections in C#

There are mainly 3 ways to work with collections. The three namespaces of the collections are as follows:

![C# Collections](https://images.tpointtech.com/csharp/images/c-sharp-collections.png)

Here, we will discuss these collections one by one.

## System.Collections.Generic Classes

In the C# programming language, the Generic Collection is defined in the System.Collection.Generic namespace. These collections offer a generic implementation of standard data structures, including stacks, queues, linked lists, dictionaries, and many others.

The Generic collections are type-safe because they are generic, which means they can only store those collections that are type-compatible with the type of collection in the generic collection. It removes accidental type mismatches and prevents the requirement for boxing and unboxing, which enhances the performance, flexibility, and efficiency of the program.

The System.Collections.Generic namespace has several classes in C#. Some of them are as follows:

|Classes|Description|
|---|---|
|**List<T>**|It is a generic list that keeps elements in a sequence that has an order and supports access by index. It can automatically increase or decrease in size, has duplicate elements, and offers helpful methods, such as Add, Remove, and Sort.|
|**Stack<T>**|It is used to represent a LIFO collection in which elements are added with Push and removed with Pop. The Peek provides a view of the top element without its removal, which is helpful for applications such as undo operations.|
|**Queue<T>**|It is used to represent an instance based on the First-In-First-Out (FIFO) concept, where an item is added at the tail by Enqueue and an item is taken from the head by Dequeue. Peek is applicable to look at the front element without removing it, which is an apt application for scheduling tasks.|
|**LinkedList<T>**|It is used to represent a doubly linked list in which every element holds references to the next and previous node. It is optimal for constant insertions and removals towards both ends or in the middle, and contains methods such as AddFirst, AddLast, and Remove.|
|**HashSet<T>**|It is used to represent a data structure that only contains unique elements and no duplicates. It is hashing-based, so search and lookups are extremely quick, but the elements' order is not kept. It also supports set operations, such as Union and Intersection.|
|**SortedSet<T>**|It is comparable to HashSet, but maintains elements in sorted order. It enforces uniqueness and supports efficient search while being particularly useful when dealing with sorted data ranges.|
|**Dictionary<TKey, TValue>**|It is used to represent a list of key-value pairs, with each key requiring uniqueness. It supports fast lookups and value retrieval using keys and includes methods such as Add, Remove, and TryGetValue for safe access.|
|**SortedDictionary<TKey, TValue>**|This is a function like a Dictionary, but keeps its elements sorted by key. It is useful where fast lookups are required along with sorted traversal of the key-value pairs.|
|**SortedList<TKey, TValue>**|It is used to store the elements in sorted order by key. It takes less memory than SortedDictionary and grants access by both key and index, although insertion and deletion can be slower for bigger collections.|

### C# System.Collections.Generic classes Example

Let us take an example to illustrate the System.Collections.Generic classes in C#.

### Example

[](https://www.tpointtech.com/c-sharp-collections#)[](https://www.tpointtech.com/c-sharp-collections#)[](https://www.tpointtech.com/c-sharp-collections#)

1. using System;  
2. using System.Collections.Generic;  

3. class Tpoint  
4. {  
5.     static void Main()  
6.     {  
7.         // using List<T> function  
8.         List<int> numbers = new List<int>() { 5, 10, 15 };  
9.         numbers.Add(20);  
10.         Console.WriteLine("List: " + string.Join(", ", numbers));  

11.         // Using Dictionary<TKey, TValue> function  
12.         Dictionary<string, int> ages = new Dictionary<string, int>();  
13.         ages["Brendon"] = 27;  
14.         ages["James"] = 32;  
15.         Console.WriteLine("Dictionary:");  
16.         foreach (var kvp in ages)  
17.             Console.WriteLine($"{kvp.Key}: {kvp.Value}");  

18.         // Using Queue<T> function  
19.         Queue<string> queue = new Queue<string>();  
20.         queue.Enqueue("First");  
21.         queue.Enqueue("Second");  
22.         Console.WriteLine("Queue Dequeue: " + queue.Dequeue());  

23.         // using Stack<T> function  
24.         Stack<string> stack = new Stack<string>();  
25.         stack.Push("Bottom");  
26.         stack.Push("Top");  
27.         Console.WriteLine("Stack Pop: " + stack.Pop());  

28.         // using LinkedList<T> function  
29.         LinkedList<int> linkedList = new LinkedList<int>();  
30.         linkedList.AddLast(14);  
31.         linkedList.AddLast(26);  
32.         linkedList.AddFirst(13);  
33.         Console.WriteLine("LinkedList: ");  
34.         foreach (var item in linkedList)  
35.             Console.Write(item + " ");  
36.         Console.WriteLine();  

37.     }  
38. }  

**Output:**

List: 5, 10, 15, 20
Dictionary:
Brendon: 27
James: 32
Queue Dequeue: First
Stack Pop: Top
LinkedList:
13 14 26

**Explanation:**

In this example, we use various generic collection classes from the System.Collections.Generic namespace. First, it displays a List<T> for dynamic arrays, a Dictionary<TKey, TValue> for key-value pairs, Queue<T> for FIFO operations, Stack<T> for LIFO operations, and LinkedList<T> for a doubly linked list, which performs basic operations like adding, removing, and iterating elements.

## System.Collections classes

In the C# programming language, the System.Collections namespace offers non-generic collection classes. It is represented as a general-purpose data structure that performs operations on object references. These non-generic classes can store any type of object. These collections are not type-safe. Non-generic collections can be defined by a group of interfaces and classes.

The System.Collections namespace has several classes in C#. Some of them are as follows:

|Classes|Description|
|---|---|
|**ArrayList**|ArrayList holds elements of any class in a dynamic indexed list and can increase or decrease in size as necessary. However, it is not type-safe and is primarily utilized for backward compatibility.|
|**Stack**|Stack is a last-in, first-out (LIFO) data structure, which pushes items in with the Push() function, pops them out with the Pop() function, and accesses the latest one first, which is better for reversing orders or dealing with recursive calls.|
|**Queue**|A queue is a FIFO collection, including insert with Enqueue(), remove with Dequeue(), items accessed in order of entry, with applications in scheduling and buffer operations.|
|**Hashtable**|It is used to store key-value pairs for quick lookups, where each key has to be unique, and values may be any object, which makes it effective for mapping and associative storage.|

### C# System.Collections Classes Example

Let us take an example to illustrate the System.Collections classes in C#.

### Example

[](https://www.tpointtech.com/c-sharp-collections#)[](https://www.tpointtech.com/c-sharp-collections#)[](https://www.tpointtech.com/c-sharp-collections#)

1. using System;  
2. using System.Collections;  

3. class Tpoint  
4. {  
5.     static void Main()  
6.     {  
7.         // using ArrayList function  
8.         ArrayList arrayList = new ArrayList() { 1, "Hello TpointTech", 3.14 };  
9.         arrayList.Add(100);  
10.         Console.WriteLine("ArrayList: ");  
11.         foreach (var item in arrayList)  
12.             Console.Write(item + " ");  
13.         Console.WriteLine("\n");  

14.         // using Hashtable function  
15.         Hashtable hashtable = new Hashtable();  
16.         hashtable["id"] = 101;  
17.         hashtable["name"] = "Jhonson";  
18.         Console.WriteLine("Hashtable: ");  
19.         foreach (DictionaryEntry entry in hashtable)  
20.             Console.WriteLine($"{entry.Key}: {entry.Value}");  
21.         Console.WriteLine();  

22.         // using Queue function  
23.         Queue queue = new Queue();  
24.         queue.Enqueue("First");  
25.         queue.Enqueue("Second");  
26.         Console.WriteLine("Queue Dequeue: " + queue.Dequeue());  
27.         Console.WriteLine();  

28.         // using Stack function  
29.         Stack stack = new Stack();  
30.         stack.Push("Bottom");  
31.         stack.Push("Top");  
32.         Console.WriteLine("Stack Pop: " + stack.Pop());  
33.         Console.WriteLine();  

34.     }  
35. }  

**Output:**

ArrayList:
1 Hello TpointTech 3.14 100

Hashtable:
id: 101
name: Jhonson

Queue Dequeue: First

Stack Pop: Top

**Explanation:**

In this example, we demonstrate the use of non-generic collection classes from the System.Collections namespace. First, it shows how ArrayList stores the mixed-type elements dynamically, Hashtable manages key-value pairs, Queue works on a FIFO basis, and Stack applies the LIFO principle. After that, it performs the simple add, remove, and iteration operations.

## System.Collections.Concurrent Classes

In the C# programming language, the System.Collections.Concurrent namespace provides classes for thread-safe operations. It came into existence in .NET Framework 4 and onwards. It was mainly designed for multi-threaded programming. These collections enable multiple threads to effectively add, remove, and update data without explicit locks, which makes them efficient and safer than using System.Collections or System.Collectios.Generic.

The System.Collections.Concurrent namespace has several classes in C#. Some of them are as follows:

|Classes|Description|
|---|---|
|BlockingCollection|It offers a thread-safe collection with blocking and bounding features for producers and consumers to wait if the collection is empty or full, which is applicable in producer-consumer situations.|
|ConcurrentBag|It is a thread-safe, unordered collection and is most efficient when many threads are inserting and deleting items continuously, but the order does not matter.|
|ConcurrentStack|It is a thread-safe LIFO-based stack and is appropriate for use in undo actions or backtracking in a multithreading environment.|
|ConcurrentQueue|It is a first-in, first-out (FIFO) thread-safe data structure suitable for processing jobs or tasks in sequence by many threads simultaneously.|
|ConcurrentDirectory|It is a thread-safe key-value pair dictionary for storing and supporting concurrent write and read operations, which enable efficient multi-threading access to dictionary values.|
|Partitioner|It helps to split a data source into multiple partitions in order to distribute work equally between threads in parallel processing and improve performance in data-parallel operations.|
|OrderablePartitioner|It extends Partitioner with the added functionality to maintain element order while partitioning, useful when parallel jobs process ordered data.|

### C# System.Collections.Concurrent Example

Let us take an example to illustrate the System.Collections.Concurrent in C#.

### Example

[](https://www.tpointtech.com/c-sharp-collections#)[](https://www.tpointtech.com/c-sharp-collections#)[](https://www.tpointtech.com/c-sharp-collections#)

1. using System;  
2. using System.Collections.Concurrent;  
3. using System.Threading.Tasks;  
4. class Tpoint  
5. {  
6.     static void Main()  
7.     {  
8.         var dict = new ConcurrentDictionary<int, string>();  
9.         dict.TryAdd(1, "One");  
10.         dict[2] = "Two";  
11.         dict.AddOrUpdate(2, "Second", (key, oldValue) => oldValue + " Updated");  
12.         if (dict.TryGetValue(1, out string value))  
13.         {  
14.             Console.WriteLine($"Key 1 = {value}");  
15.         }  
16.         Parallel.For(3, 6, i =>  
17.         {  
18.             dict[i] = $"Number {i}";  
19.         });  
20.         Console.WriteLine("Final dictionary:");  
21.         foreach (var a in dict)  
22.         {  
23.             Console.WriteLine($"{a.Key} : {a.Value}");  
24.         }  
25.     }  
26. }  

**Output:**

Key 1 = One
Final dictionary:
1 : One
2 : Two Updated
3 : Number 3
4 : Number 4
5 : Number 5

**Explanation:**

In this example, we demonstrate how ConcurrentDictionary operates thread-safely. Here, we are performing several operations, including inserting items, modifying a value, looking up a key, and inserting several entries. Finally, it displays all key-value pairs of the dictionary.

## General Categories of Collections

C# collections are categorized into four main categories, including Indexed-Based, Key-Value Pair, Prioritized Collection, and Specialized Collections.

![C# Collections](https://images.tpointtech.com/csharp/images/c-sharp-collections2.png)

Here, we will discuss these collection categories one by one.

### Indexed-Based Collections

Indexed-based collections hold elements that are accessed through an internal index position. It also includes several examples, such as Array, List, and ArrayList, where every location of the item is checked by its index for quick access and modification.

### Key-Value Pair Collections

The key-value pair collections keep data in pairs for easy access by key. It includes several classes, such as Hashtable, Dictionary, and SortedList. They are utilized when items have to be retrieved or modified by a unique key instead of position.

### Prioritized Collection

Prioritized collections process elements according to order or priority, including Queue, Stack, and SortedList, where order or priority dictates the way items are handled.

### Specialized Collections

Specialized collections are optimized for particular use scenarios, including thread-safe operations or special structures. Some examples include LinkedList and the collections from the System.Collections.Concurrent, and others for parallel or specialized processing needs.

## Features of C# Collections

There are several features of C# collections. Some of them are as follows:

- In C#, collections can grow or shrink in size during runtime.
- Generic collections offer compile-time type checking, which helps to reduce runtime errors.
- Collections can store data as lists, queues, stacks, dictionaries, sets, and linked lists, depending on the requirement.
- In C#, System.Collections.Concurrent offer built-in thread-safe classes for parallel and multi-threaded programming.
- It can be optimized for several operations, including sorting, searching, inserting, and deleting.
- Collections can support non-generic, generic, and thread-safe concurrent collections.

## Conclusion

In conclusion, C# collections are a group of objects that facilitate the effective handling and processing of associated data in collections as a unit. Dynamic sizing and type safety ensure flexible, maintainable, and stable code, and support for concurrency and rich built-in operations make collections an integral part of scalable modern C# software.