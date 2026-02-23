The Java Queue interface belongs to java.util package. It is a fundamental part of the Java Collections Framework designed to handle elements in a specific sequence, typically in a First-In-First-Out (FIFO) manner. As an ordered list of objects, a Queue ensures that elements are inserted at the end and removed from the beginning, making it an ideal data structure for scenarios such as task scheduling, order processing, and managing print jobs.

Being an interface, Queue cannot be instantiated directly. Instead, it requires a concrete implementation. The most common classes that implement the Queue interface in Java are LinkedList and PriorityQueue. The LinkedList class provides a doubly-linked list implementation, while the PriorityQueue class is based on a priority heap, ordering its elements according to their natural ordering or a specified comparator.

However, these standard implementations are not thread-safe, making them unsuitable for concurrent applications where multiple threads may access and modify the queue simultaneously. For such use cases, Java provides the PriorityBlockingQueue class in the java.util.concurrent package, which offers a thread-safe priority queue implementation.

The Queue interface itself extends the Collection interface, inheriting all its methods and adding several specific ones for insertion, removal, and inspection of elements. Key methods include add and offer for insertion, remove and poll for removal, and element and peek for inspection. These methods are designed to handle the unique needs of a queue, such as returning special values or throwing exceptions when operations fail due to capacity restrictions or an empty queue.

### Queue Interface Declaration

[](https://www.tpointtech.com/java-priorityqueue#)[](https://www.tpointtech.com/java-priorityqueue#)[](https://www.tpointtech.com/java-priorityqueue#)

1. public interface Queue<E> extends Collection<E>  

### Methods of Java Queue Interface

|Method|Description|
|---|---|
|boolean add(object)|It is used to insert the specified element into this queue and return true upon success.|
|boolean offer(object)|It is used to insert the specified element into this queue.|
|Object remove()|It is used to retrieves and removes the head of this queue.|
|Object poll()|It is used to retrieves and removes the head of this queue, or returns null if this queue is empty.|
|Object element()|It is used to retrieves, but does not remove, the head of this queue.|
|Object peek()|It is used to retrieves, but does not remove, the head of this queue, or returns null if this queue is empty.|

## Features of a Queue

The following are some important features of a queue.

- As discussed earlier, FIFO concept is used for insertion and deletion of elements from a queue.
- The Java Queue provides support for all of the methods of the Collection interface including deletion, insertion, etc.
- PriorityQueue, ArrayBlockingQueue and LinkedList are the implementations that are used most frequently.
- The NullPointerException is raised, if any null operation is done on the BlockingQueues.
- Those Queues that are present in the _util_ package are known as Unbounded Queues.
- Those Queues that are present in the _util.concurrent_ package are known as bounded Queues.
- All Queues barring the Deques facilitates removal and insertion at the head and tail of the queue; respectively. In fact, deques support element insertion and removal at both ends.

## PriorityQueue Class

PriorityQueue is also class that is defined in the collection framework that gives us a way for processing the objects on the basis of priority. It is already described that the insertion and deletion of objects follows FIFO pattern in the Java queue. However, sometimes the elements of the queue are needed to be processed according to the priority, that's where a PriorityQueue comes into action.

### PriorityQueue Class Declaration

Let's see the declaration for java.util.PriorityQueue class.

[](https://www.tpointtech.com/java-priorityqueue#)[](https://www.tpointtech.com/java-priorityqueue#)[](https://www.tpointtech.com/java-priorityqueue#)

1. public class PriorityQueue<E> extends AbstractQueue<E> implements Serializable  

### Java PriorityQueue Example

**FileName:** TestCollection12.java

[](https://www.tpointtech.com/java-priorityqueue#)[](https://www.tpointtech.com/java-priorityqueue#)[](https://www.tpointtech.com/java-priorityqueue#)

1. import java.util.*;    
2. class TestCollection12 {    
3.     public static void main(String args[]) {    
4.         // Creating a PriorityQueue of Strings  
5.         PriorityQueue<String> queue = new PriorityQueue<String>();    
6.         // Adding elements to the PriorityQueue  
7.         queue.add("Amit");    
8.         queue.add("Vijay");    
9.         queue.add("Karan");    
10.         queue.add("Jai");    
11.         queue.add("Rahul");    
12.         // Displaying the head of the queue using element() method  
13.         // This method throws an exception if the queue is empty  
14.         System.out.println("head:" + queue.element());    
15.         // Displaying the head of the queue using peek() method  
16.         // This method returns null if the queue is empty  
17.         System.out.println("head:" + queue.peek());    
18.         // Iterating through the queue elements  
19.         System.out.println("iterating the queue elements:");    
20.         Iterator<String> itr = queue.iterator();    
21.         while (itr.hasNext()) {    
22.             System.out.println(itr.next());    
23.         }    
24.         // Removing the head of the queue using remove() method  
25.         // This method throws an exception if the queue is empty  
26.         queue.remove();    
27.         // Removing the head of the queue using poll() method  
28.         // This method returns null if the queue is empty  
29.         queue.poll();    
30.         // Displaying the queue elements after removing two elements  
31.         System.out.println("after removing two elements:");    
32.         Iterator<String> itr2 = queue.iterator();    
33.         while (itr2.hasNext()) {    
34.             System.out.println(itr2.next());    
35.         }    
36.     }    
37. }    

**Output:**

head:Amit
head:Amit
iterating the queue elements:
Amit
Jai
Karan
Vijay
Rahul
after removing two elements:
Karan
Rahul
Vijay

### Java PriorityQueue Example: Book

Let's see a PriorityQueue example where we are adding books to queue and printing all the books. The elements in PriorityQueue must be of Comparable type. String and Wrapper classes are Comparable by default. To add user-defined objects in PriorityQueue, you need to implement Comparable interface.

**FileName:** LinkedListExample.java

[](https://www.tpointtech.com/java-priorityqueue#)[](https://www.tpointtech.com/java-priorityqueue#)[](https://www.tpointtech.com/java-priorityqueue#)

1. import java.util.*;  
2. class Book implements Comparable<Book> {  
3.     int id;  
4.     String name, author, publisher;  
5.     int quantity;  
6.     // Constructor to initialize Book object  
7.     public Book(int id, String name, String author, String publisher, int quantity) {  
8.         this.id = id;  
9.         this.name = name;  
10.         this.author = author;  
11.         this.publisher = publisher;  
12.         this.quantity = quantity;  
13.     }  
14.     // compareTo method to compare Books based on 'id'  
15.     public int compareTo(Book b) {  
16.         if (id > b.id) {  
17.             return 1;  
18.         } else if (id < b.id) {  
19.             return -1;  
20.         } else {  
21.             return 0;  
22.         }  
23.     }  
24. }  
25. public class LinkedListExample {  
26.     public static void main(String[] args) {  
27.         // Creating a PriorityQueue to store Book objects  
28.         Queue<Book> queue = new PriorityQueue<Book>();  
29.         // Creating Book objects  
30.         Book b1 = new Book(121, "Let us C", "Yashwant Kanetkar", "BPB", 8);  
31.         Book b2 = new Book(233, "Operating System", "Galvin", "Wiley", 6);  
32.         Book b3 = new Book(101, "Data Communications & Networking", "Forouzan", "Mc Graw Hill", 4);  
33.         // Adding Book objects to the queue  
34.         queue.add(b1);  
35.         queue.add(b2);  
36.         queue.add(b3);  
37.         // Displaying the elements of the queue  
38.         System.out.println("Traversing the queue elements:");  
39.         for (Book b : queue) {  
40.             System.out.println(b.id + " " + b.name + " " + b.author + " " + b.publisher + " " + b.quantity);  
41.         }  
42.         // Removing the head of the queue  
43.         queue.remove();  
44.         // Displaying the elements of the queue after removing one element  
45.         System.out.println("After removing one book record:");  
46.         for (Book b : queue) {  
47.             System.out.println(b.id + " " + b.name + " " + b.author + " " + b.publisher + " " + b.quantity);  
48.         }  
49.     }  
50. }  

**Output:**

Traversing the queue elements:
101 Data Communications & Networking Forouzan Mc Graw Hill 4
233 Operating System Galvin Wiley 6
121 Let us C Yashwant Kanetkar BPB 8
After removing one book record:
121 Let us C Yashwant Kanetkar BPB 8
233 Operating System Galvin Wiley 6