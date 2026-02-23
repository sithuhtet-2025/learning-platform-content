The **Collection in Java** is a framework that provides an architecture to store and manipulate a group of objects.

Java Collections can achieve all the operations that we perform on data, such as searching, sorting, insertion, manipulation, and deletion.

Java Collection means a single unit of objects. Java Collection framework provides many interfaces (Set, List, Queue, Deque) and classes ([ArrayList](https://www.tpointtech.com/java-arraylist), [Vector](https://www.tpointtech.com/java-vector), [LinkedList](https://www.tpointtech.com/java-linkedlist), [PriorityQueue](https://www.tpointtech.com/java-priorityqueue), [HashSet](https://www.tpointtech.com/java-hashset), [LinkedHashSet](https://www.tpointtech.com/java-linkedhashset), [TreeSet](https://www.tpointtech.com/java-treeset)).

## What is Collection?

A Collection represents a single unit of objects, i.e., a group.

## What is a framework?

A framework provides a ready-made structure of classes and interfaces for building software applications efficiently. It simplifies adding new features by offering reusable components that perform similar tasks, eliminating the need to create a framework from scratch for each new project. This approach enhances object-oriented design, making development quicker, more consistent, and reliable.

- It provides readymade architecture.
- It represents a set of classes and interfaces.
- It is optional.

## What is the Collection Framework?

The Collection framework represents a unified architecture for storing and manipulating a group of objects. It enhances code efficiency and readability by offering various data structures, including arrays, linked lists, trees, and hash tables, tailored to different programming needs. It has:

1. Interfaces and its implementations, i.e., classes
2. Algorithm

## Why Collection Framework?

Before the Collection Framework was introduced in JDK 1.2, Java's approach to collections was using Arrays, Vectors, and Hash tables lacked a common interface. This meant each type of collection had its own set of methods, syntax, and constructors, with no standardization or correlation between them.

This made it difficult for users to remember the diverse functionalities of each collection type and hindered code consistency and reusability. The disparate nature of these collections highlighted the need for a unified Collection Framework to simplify and standardize collection operations in Java.

### Hierarchy of Collection Framework

Let's see the hierarchy of Collection framework. The **java.util** package contains all the [classes](https://www.tpointtech.com/object-and-class-in-java) and [interfaces](https://www.tpointtech.com/interface-in-java) for the Collection framework.

The Java Collections Framework is structured around key interfaces-Collection, List, Set, Queue, and Map. Each tailored for specific data management tasks. Implementations like ArrayList, HashSet, and HashMap offer practical solutions for working with these collections, giving Java developers a versatile set of tools for efficient data handling.

![Hierarchy of Java Collection framework](https://d2jdgazzki9vjm.cloudfront.net/images/java-collection-hierarchy.png)

- **Class:** A class is a blueprint from which individual objects are created. It encapsulates data for objects through fields (attributes) and defines behavior via methods. Classes support inheritance, allowing one class to inherit the properties and methods of another, facilitating code reuse and polymorphism.
- **Interface:** An interface is a reference type in Java that can contain constants and abstract methods (methods without a body). Interfaces specify what a class must do but not how it does it, enforcing a set of methods that the class must implement. Interfaces are used to achieve abstraction and multiple inheritance in Java.

### Methods of Collection interface

There are many methods declared in the Collection interface. The Collection interface in Java provides basic methods to work with groups of objects, such as adding, removing, and iterate through each element. They are as follows:

|Method|Description|
|---|---|
|public boolean add(E e)|It is used to insert an element in this collection.|
|public boolean addAll(Collection<? extends E> c)|It is used to insert the specified collection elements in the invoking collection.|
|public boolean remove(Object element)|It is used to delete an element from the collection.|
|public boolean removeAll(Collection<?> c)|It is used to delete all the elements of the specified collection from the invoking collection.|
|default boolean removeIf(Predicate<? super E> filter)|It is used to delete all the elements of the collection that satisfy the specified predicate.|
|public boolean retainAll(Collection<?> c)|It is used to delete all the elements of the invoking collection except the specified collection.|
|public int size()|It returns the total number of elements in the collection.|
|public void clear()|It removes the total number of elements from the collection.|
|public boolean contains(Object element)|It is used to search for an element.|
|public boolean containsAll(Collection<?> c)|It is used to search the specified collection in the collection.|
|public Iterator iterator()|It returns an iterator.|
|public Object[] toArray()|It converts the collection into an array.|
|public <T> T[] toArray(T[] a)|It converts the collection into an array. Here, the runtime type of the returned array is that of the specified array.|
|public boolean isEmpty()|It checks if the collection is empty.|
|default Stream<E> parallelStream()|It returns a possibly parallel Stream with the collection as its source.|
|default Stream<E> stream()|It returns a sequential Stream with the collection as its source.|
|default Spliterator<E> spliterator()|It generates a Spliterator over the specified elements in the collection|
|public boolean equals(Object element)|It matches two collections.|
|public int hashCode()|It returns the hash code number of the collection.|

## Iterator Interface

The iterator interface provides the facility of iterating the elements in a forward direction only.

### Methods of Iterator Interface

There are only three methods in the Iterator interface. They are:

|Method|Description|
|---|---|
|public boolean hasNext()|It returns true if the iterator has more elements; otherwise, it returns false.|
|public Object next()|It returns the element and moves the cursor pointer to the next element.|
|public void remove()|It removes the last elements returned by the iterator. It is less used.|

## Iterable Interface

The Iterable interface is the root interface for all the collection classes. The Collection interface extends the Iterable interface, and therefore, all the subclasses of the Collection interface also implement the Iterable interface.

It contains only one abstract method. i.e.,

[](https://www.tpointtech.com/collections-in-java#)[](https://www.tpointtech.com/collections-in-java#)[](https://www.tpointtech.com/collections-in-java#)

1. Iterator<T> iterator()  

It returns the iterator over the elements of type T.

## Collection Interface

The Collection interface is the interface which is implemented by all the classes in the collection framework. It declares the methods that every collection will have. In other words, we can say that the Collection interface builds the foundation on which the collection framework depends.

Some of the methods of Collection interface are Boolean add (Object obj), Boolean addAll (Collection c), void clear(), etc. that are implemented by all the subclasses of Collection interface.

To read more: [Java Collection Interface](https://www.tpointtech.com/java-collection)

## List Interface

The list interface is the child interface of the Collection interface. It inhibits a list-type data structure in which we can store the ordered collection of objects. It can have duplicate values. The list interface is implemented by the classes ArrayList, LinkedList, Vector, and Stack. To instantiate the List interface, we must use:

[](https://www.tpointtech.com/collections-in-java#)[](https://www.tpointtech.com/collections-in-java#)[](https://www.tpointtech.com/collections-in-java#)

1. List <data-type> list1= new ArrayList();  
2. List <data-type> list2 = new LinkedList();  
3. List <data-type> list3 = new Vector();  
4. List <data-type> list4 = new Stack();  

Various methods in List interface can be used to insert, delete, and access the elements from the list. The classes that implement the List interface are given below:

- ArrayList
- LinkedList
- Vector
- Stack

To read more: [Java List Interface](https://www.tpointtech.com/java-list)

## ArrayList

The ArrayList class implements the List interface. It uses a dynamic array to store the duplicate elements of different data types. The ArrayList class maintains the insertion order and is non-synchronized. The elements stored in the ArrayList class can be randomly accessed. Consider the following example.

To read more: [Java ArrayList](https://www.tpointtech.com/java-arraylist)

### Example of ArrayList

### Example

[](https://www.tpointtech.com/collections-in-java#)[](https://www.tpointtech.com/collections-in-java#)[](https://www.tpointtech.com/collections-in-java#)

1. import java.util.*;    
2. public class Main {    
3.     public static void main(String args[]) {    
4.             ArrayList<String> list=new ArrayList<String>();//Creating arraylist    
5.             list.add("John");//Adding object in arraylist    
6.             list.add("Peter");    
7.             list.add("Lucy");    
8.             list.add("Johnson");    
9.             //Traversing list through Iterator    
10.             Iterator itr=list.iterator();    
11.             while(itr.hasNext()) {    
12.             System.out.println(itr.next());    
13.         }    
14.     }    
15. }    

**Output:**

John
Peter
Lucy
Johnson

## LinkedList

LinkedList implements the Collection interface. It uses a doubly linked list internally to store the elements. It can store the duplicate elements. It maintains the insertion order and is not synchronized. In LinkedList, the manipulation is fast because no shifting is required. Consider the following example.

To read more: [Java LinkedList](https://www.tpointtech.com/java-linkedlist)

### Example of LinkedList

### Example

[](https://www.tpointtech.com/collections-in-java#)[](https://www.tpointtech.com/collections-in-java#)[](https://www.tpointtech.com/collections-in-java#)

1. import java.util.*;    
2. public class Main {    
3.     public static void main(String args[]) {    
4.         LinkedList<String> al=new LinkedList<String>();    
5.         al.add("Lucy");    
6.         al.add("Peter");    
7.         al.add("Lucy");    
8.         al.add("John");    
9.         Iterator<String> itr=al.iterator();    
10.         while(itr.hasNext()) {    
11.             System.out.println(itr.next());    
12.         }    
13.     }    
14. }    

**Output:**

Lucy
Peter
Lucy
John

## Vector

Vector uses a dynamic array to store the data elements. It is similar to ArrayList. However, it is synchronized and contains many methods that are not the part of Collection framework. Consider the following example.

To read more: [Java Vector](https://www.tpointtech.com/java-vector)

### Example

[](https://www.tpointtech.com/collections-in-java#)[](https://www.tpointtech.com/collections-in-java#)[](https://www.tpointtech.com/collections-in-java#)

1. import java.util.*;    
2.     public class Main {    
3.         public static void main(String args[]) {    
4.         Vector<String> v=new Vector<String>();    
5.         v.add("Apple");    
6.         v.add("Banana");    
7.         v.add("Orange");    
8.         v.add("Plum");    
9.         Iterator<String> itr=v.iterator();    
10.         while(itr.hasNext()){    
11.             System.out.println(itr.next());    
12.         }    
13.     }    
14. }   

**Output:**

Apple
Banana
Orange
Plum

## Stack

The stack is the subclass of Vector. It implements the last-in-first-out data structure, i.e., Stack. The stack contains all of the methods of Vector class and also provides its methods like boolean push(), boolean peek(), boolean push(object o), which defines its properties. Consider the following example.

To read more: [Java Stack class](https://www.tpointtech.com/java-stack)

### Example

[](https://www.tpointtech.com/collections-in-java#)[](https://www.tpointtech.com/collections-in-java#)[](https://www.tpointtech.com/collections-in-java#)

1. import java.util.*;    
2.     public class Main {    
3.         public static void main(String args[]) {    
4.         Stack<String> stack = new Stack<String>();    
5.         stack.push("CPU");    
6.         stack.push("Monitor");    
7.         stack.push("Mouse");    
8.         stack.push("Keyboard");    
9.         stack.push("Printer");  
10.         stack.pop();    
11.         Iterator<String> itr=stack.iterator();    
12.         while(itr.hasNext()) {    
13.             System.out.println(itr.next());    
14.         }    
15.     }    
16. }  

**Output:**

CPU
Monitor
Mouse
Keyboard

## Queue Interface

The queue interface maintains the first-in-first-out order. It can be defined as an ordered list that is used to hold the elements that are about to be processed. There are various classes, like PriorityQueue, Deque, and ArrayDeque, which implement the Queue interface.

Queue interface can be instantiated as:

[](https://www.tpointtech.com/collections-in-java#)[](https://www.tpointtech.com/collections-in-java#)[](https://www.tpointtech.com/collections-in-java#)

1. Queue<String> q1 = new PriorityQueue();  
2. Queue<String> q2 = new ArrayDeque();  

Various classes implement the Queue interface; some of them are given below:

- PriorityQueue
- Deque
- ArrayDeque

## PriorityQueue

The PriorityQueue class implements the Queue interface. It holds the elements or objects which are to be processed by their priorities. PriorityQueue does not allow null values to be stored in the queue. Consider the following example.

To read more: [Java Stack class](https://www.tpointtech.com/java-stack)

### Example of PriorityQueue

### Example

[](https://www.tpointtech.com/collections-in-java#)[](https://www.tpointtech.com/collections-in-java#)[](https://www.tpointtech.com/collections-in-java#)

1. import java.util.*;    
2. public class Main {    
3.     public static void main(String args[]) {    
4.         PriorityQueue<String> queue=new PriorityQueue<String>();    
5.         queue.add("Alice");    
6.         queue.add("Daniel");    
7.         queue.add("Jones");    
8.         queue.add("Smith");    
9.         System.out.println("head:"+queue.element());    
10.         System.out.println("head:"+queue.peek());    
11.         System.out.println("iterating the queue elements:");    
12.         Iterator itr=queue.iterator();    
13.         while(itr.hasNext()) {    
14.             System.out.println(itr.next());    
15.         }    
16.         queue.remove();    
17.         queue.poll();    
18.         System.out.println("after removing two elements:");    
19.         Iterator<String> itr2=queue.iterator();    
20.         while(itr2.hasNext()) {    
21.             System.out.println(itr2.next());    
22.         }    
23.     }    
24. }   

**Output:**

head:Alice
head:Alice
iterating the queue elements:
Alice
Daniel
Jones
Smith
after removing two elements:
Jones
Smith

## Deque Interface

The Deque interface extends the Queue interface. In Deque, we can remove and add the elements from both sides. Deque stands for a double-ended queue, which enables us to perform the operations at both ends.

Deque can be instantiated as:

[](https://www.tpointtech.com/collections-in-java#)[](https://www.tpointtech.com/collections-in-java#)[](https://www.tpointtech.com/collections-in-java#)

1. Deque d = new ArrayDeque();  

## ArrayDeque

ArrayDeque class implements the Deque interface. It facilitates us to use the Deque. Unlike queue, we can add or delete the elements from both ends. ArrayDeque is faster than ArrayList and Stack and has no capacity restrictions. Consider the following example.

To read more: [Java Deque Interface](https://www.tpointtech.com/java-deque-arraydeque)

### Example of ArrayDeque

### Example

[](https://www.tpointtech.com/collections-in-java#)[](https://www.tpointtech.com/collections-in-java#)[](https://www.tpointtech.com/collections-in-java#)

1. import java.util.*;    
2. public class Main{    
3.     public static void main(String[] args) {    
4.         //Creating Deque and adding elements    
5.         Deque<String> deque = new ArrayDeque<String>();    
6.         deque.add("Lucy");    
7.         deque.add("Andrew");    
8.         deque.add("Henery");   
9.         //Traversing elements    
10.         for (String str : deque) {    
11.             System.out.println(str);    
12.         }    
13.     }    
14. }    

**Output:**

Lucy
Andrew
Henery

## Set Interface

Set Interface in Java is present in java.util package. It extends the Collection interface. It represents the unordered set of elements which does not allow us to store the duplicate items. We can store at most one null value in Set. HashSet, LinkedHashSet, and TreeSet implement set. The set can be instantiated as:

[](https://www.tpointtech.com/collections-in-java#)[](https://www.tpointtech.com/collections-in-java#)[](https://www.tpointtech.com/collections-in-java#)

1. Set<data-type> s1 = new HashSet<data-type>();  
2. Set<data-type> s2 = new LinkedHashSet<data-type>();  
3. Set<data-type> s3 = new TreeSet<data-type>();  

## HashSet

The HashSet class implements Set Interface. It represents the collection that uses a hash table for storage. Hashing is used to store the elements in the HashSet. It contains unique items. Consider the following example.

To read more: [Java HashSet](https://www.tpointtech.com/java-hashset)

### Example

[](https://www.tpointtech.com/collections-in-java#)[](https://www.tpointtech.com/collections-in-java#)[](https://www.tpointtech.com/collections-in-java#)

1. import java.util.*;    
2. public class Main  {    
3.     public static void main(String args[]) {    
4.         //Creating HashSet and adding elements    
5.         HashSet<String> set=new HashSet<String>();    
6.         set.add("Andrew");    
7.         set.add("Mark");    
8.         set.add("Peter");    
9.         set.add("Johnson");  
10.         //Traversing elements    
11.         Iterator<String> itr=set.iterator();    
12.         while(itr.hasNext()) {    
13.             System.out.println(itr.next());    
14.         }    
15.     }    
16. }    

**Output:**

Johnson
Andrew
Mark
Peter

## LinkedHashSet

The LinkedHashSet class represents the LinkedList implementation of the Set Interface. It extends the HashSet class and implements the Set interface. Like HashSet, it also contains unique elements. It maintains the insertion order and permits null elements. Consider the following example.

To read more: [Java LinkedHashSet Class](https://www.tpointtech.com/java-linkedhashset)

### Example

[](https://www.tpointtech.com/collections-in-java#)[](https://www.tpointtech.com/collections-in-java#)[](https://www.tpointtech.com/collections-in-java#)

1. import java.util.*;    
2. public class Main{    
3.     public static void main(String args[]){    
4.         LinkedHashSet<String> set=new LinkedHashSet<String>();    
5.         set.add("Peter");    
6.         set.add("Jack");    
7.        set.add("Peter");    
8.       set.add("Johnson");   
9.         Iterator<String> itr=set.iterator();    
10.         while(itr.hasNext()){    
11.             System.out.println(itr.next());    
12.         }    
13.     }    
14. }    

**Output:**

Peter
Jack
Johnson

## SortedSet Interface

SortedSet is the alternative to the Set interface that provides a total ordering of its elements. The elements of the SortedSet are arranged in the increasing (ascending) order. The SortedSet provides additional methods that inhibit the natural ordering of the components.

The SortedSet can be instantiated as:

[](https://www.tpointtech.com/collections-in-java#)[](https://www.tpointtech.com/collections-in-java#)[](https://www.tpointtech.com/collections-in-java#)

1. SortedSet<data-type> set = new TreeSet();    

To read more: [Java SortedSet Interface](https://www.tpointtech.com/java-sortedset)

## TreeSet

Java TreeSet class implements the Set interface that uses a tree for storage. Like HashSet, TreeSet also contains unique elements. However, the access and retrieval time of TreeSet is quite fast. The aspects in TreeSet are stored in ascending order. Consider the following example.

To read more: [Java TreeSet Class](https://www.tpointtech.com/java-treeset)

### Example

[](https://www.tpointtech.com/collections-in-java#)[](https://www.tpointtech.com/collections-in-java#)[](https://www.tpointtech.com/collections-in-java#)

1. import java.util.*;    
2. public class Main{    
3.     public static void main(String args[]){    
4.         //Creating and adding elements    
5.         TreeSet<String> set=new TreeSet<String>();    
6.        set.add("Thomas");    
7.         set.add("Davis");    
8.         set.add("Thomas");    
9.         set.add("Donald");   
10.         //traversing elements    
11.         Iterator<String> itr=set.iterator();    
12.         while(itr.hasNext()){    
13.             System.out.println(itr.next());    
14.         }    
15.     }    
16. }    

**Output:**

Davis
Donald
Thomas

### Map Interface

The Map interface in Java is part of the Java Collections Framework. It represents a mapping between a set of keys and their corresponding values. A Map cannot contain duplicate keys; each key can map to at most one value. The Map interface is used to store key-value pairs, where each key is unique, and it provides an efficient way to retrieve, update, and manipulate data based on keys.

**Syntax:**

[](https://www.tpointtech.com/collections-in-java#)[](https://www.tpointtech.com/collections-in-java#)[](https://www.tpointtech.com/collections-in-java#)

1. Map<T, T> hm = new HashMap<>();   
2. Map<T, T> tm = new TreeMap<>();  

To read more: [Java Map Interface](https://www.tpointtech.com/java-map)

### HashMap

HashMap in Java is a key-value data structure offering efficient data access via keys using hashing. Hashing converts large strings or other objects into smaller, consistent values for quick indexing and searching. HashMap implements the Map interface and is used for managing large datasets efficiently. Additionally, HashSet uses HashMap internally to store elements uniquely, demonstrating the utility of hashing in Java's collections framework for fast data retrieval and management.

To read more: [Java HashMap](https://www.tpointtech.com/java-hashmap)

### Example

[](https://www.tpointtech.com/collections-in-java#)[](https://www.tpointtech.com/collections-in-java#)[](https://www.tpointtech.com/collections-in-java#)

1. import java.util.HashMap;  
2. import java.util.Map;  
3. public class Main {  
4.     public static void main(String[] args) {  
5.         // Creating a HashMap  
6.         Map<String, Integer> map = new HashMap<>();  
7.         // Adding key-value pairs to the HashMap  
8.         map.put("Alice", 10);  
9.         map.put("Bob", 20);  
10.         map.put("Charlie", 30);  
11.         // Retrieving a value  
12.         System.out.println("Value for 'Alice': " + map.get("Alice"));  
13.         // Iterating over key-value pairs  
14.         for (Map.Entry<String, Integer> entry : map.entrySet()) {  
15.             String key = entry.getKey();  
16.             Integer value = entry.getValue();  
17.             System.out.println(key + ": " + value);  
18.         }  
19.         // Removing a key-value pair  
20.         map.remove("Charlie");  
21.         // Checking the presence of a key  
22.         if (map.containsKey("Bob")) {  
23.             System.out.println("Map contains key 'Bob'.");  
24.         }  
25.     }  
26. }  

**Output:**

Value for 'Alice': 10Bob: 20
Alice: 10
Charlie: 30
Map contains key 'Bob'.