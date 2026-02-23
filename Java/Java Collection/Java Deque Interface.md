
Java Deque interface belongs to java.util package. It is the subtype of the Queue interface. Deque, short for double-ended queue. The Deque supports the addition as well as the removal of elements from both ends of the data structure.

Therefore, a deque can be used as a stack or a queue. We know that the stack supports the Last-In-First-Out (LIFO) operation, and the operation First-In-First-Out is supported by a queue. As a deque supports both, either of the mentioned operations can be performed on it. Dequeue provides a powerful abstraction for managing elements in a collection where both ends are accessible for insertion and removal operations.

### Deque Interface Declaration

[](https://www.tpointtech.com/java-deque-arraydeque#)[](https://www.tpointtech.com/java-deque-arraydeque#)[](https://www.tpointtech.com/java-deque-arraydeque#)

1. public interface Deque<E> extends Queue<E>  

### Methods of Java Deque Interface

|Method|Description|
|---|---|
|boolean add(object)|It is used to insert the specified element into this deque and return true upon success.|
|boolean offer(object)|It is used to insert the specified element into this deque.|
|Object remove()|It is used to retrieve and removes the head of this deque.|
|Object poll()|It is used to retrieve and removes the head of this deque, or returns null if this deque is empty.|
|Object element()|It is used to retrieve, but does not remove, the head of this deque.|
|Object peek()|It is used to retrieve, but does not remove, the head of this deque, or returns null if this deque is empty.|
|Object peekFirst()|The method returns the head element of the deque. The method does not remove any element from the deque. Null is returned by this method, when the deque is empty.|
|Object peekLast()|The method returns the last element of the deque. The method does not remove any element from the deque. Null is returned by this method, when the deque is empty.|
|Boolean offerFirst(e)|Inserts the element e at the front of the queue. If the insertion is successful, true is returned; otherwise, false.|
|Object offerLast(e)|Inserts the element e at the tail of the queue. If the insertion is successful, true is returned; otherwise, false.|

![java arraydeque hierarchy](https://d2jdgazzki9vjm.cloudfront.net/java/collection/images/arraydeque.png)

### Key Features of Deque Interface:

**Double-Ended Operations:** Deque supports operations that allow elements to be added or removed from both the front and rear of the queue. These operations include addFirst(E e), addLast(E e), removeFirst(), and removeLast().

**Accessors:** Deque provides methods to access elements from both ends without removing them. These methods include getFirst() and getLast().

**Special Insertion and Removal Operations:** Apart from regular insertion and removal operations, Deque offers specialized operations such as offerFirst(E e) and offerLast(E e) for inserting elements, and pollFirst() and pollLast() for removing elements.

## ArrayDeque Class

We know that it is not possible to create an object of an interface in Java. Therefore, for instantiation, we need a class that implements the Deque interface, and that class is ArrayDeque. It grows and shrinks as per usage. It also inherits the AbstractCollection class.

The important points about ArrayDeque class are:

- Unlike Queue, we can add or remove elements from both sides.
- Null elements are not allowed in the ArrayDeque.
- ArrayDeque is not thread safe, in the absence of external synchronization.
- ArrayDeque has no capacity restrictions.
- ArrayDeque is faster than LinkedList and Stack.

### ArrayDeque Hierarchy

The hierarchy of ArrayDeque class is given in the figure displayed at the right side of the page.

### ArrayDeque Class Declaration

Let's see the declaration for java.util.ArrayDeque class.

[](https://www.tpointtech.com/java-deque-arraydeque#)[](https://www.tpointtech.com/java-deque-arraydeque#)[](https://www.tpointtech.com/java-deque-arraydeque#)

1. public class ArrayDeque<E> extends AbstractCollection<E> implements Deque<E>, Cloneable, Serializable  

## Java ArrayDeque Example

### Example

[](https://www.tpointtech.com/java-deque-arraydeque#)[](https://www.tpointtech.com/java-deque-arraydeque#)[](https://www.tpointtech.com/java-deque-arraydeque#)

1. import java.util.*;  
2. public class Main {  
3.    public static void main(String[] args) {  
4.    //Creating Deque and adding elements  
5.    Deque<String> deque = new ArrayDeque<String>();  
6.    deque.add("Ravi");    
7.    deque.add("Vijay");     
8.    deque.add("Ajay");    
9.    //Traversing elements  
10.    for (String str : deque) {  
11.    System.out.println(str);  
12.    }  
13.    }  
14. }  

**Output:**

Ravi
Vijay
Ajay

## Java ArrayDeque Example: offerFirst() and pollLast()

**FileName:** DequeExample.java

[](https://www.tpointtech.com/java-deque-arraydeque#)[](https://www.tpointtech.com/java-deque-arraydeque#)[](https://www.tpointtech.com/java-deque-arraydeque#)

1. import java.util.*;  
2. public class Main {  
3. public static void main(String[] args) {  
4.     Deque<String> deque=new ArrayDeque<String>();  
5.     deque.offer("arvind");  
6.     deque.offer("vimal");  
7.     deque.add("mukul");  
8.     deque.offerFirst("jai");  
9.     System.out.println("After offerFirst Traversal...");  
10.     for(String s:deque){  
11.         System.out.println(s);  
12.     }  
13.     //deque.poll();  
14.     //deque.pollFirst();//it is same as poll()  
15.     deque.pollLast();  
16.     System.out.println("After pollLast() Traversal...");  
17.     for(String s:deque){  
18.         System.out.println(s);  
19.     }  
20. }  
21. }  

**Output:**

After offerFirst Traversal...
jai
arvind
vimal
mukul
After pollLast() Traversal...
jai
arvind
vimal

## Java ArrayDeque Example: Book

### Example

[](https://www.tpointtech.com/java-deque-arraydeque#)[](https://www.tpointtech.com/java-deque-arraydeque#)[](https://www.tpointtech.com/java-deque-arraydeque#)

1. import java.util.*;    
2. class Book {    
3. int id;    
4. String name,author,publisher;    
5. int quantity;    
6. public Book(int id, String name, String author, String publisher, int quantity) {    
7.     this.id = id;    
8.     this.name = name;    
9.     this.author = author;    
10.     this.publisher = publisher;    
11.     this.quantity = quantity;    
12. }    
13. }    
14. public class Main {    
15. public static void main(String[] args) {    
16.     Deque<Book> set=new ArrayDeque<Book>();    
17.     //Creating Books    
18.     Book b1=new Book(101,"Let us C","Yashwant Kanetkar","BPB",8);    
19.     Book b2=new Book(102,"Data Communications & Networking","Forouzan","Mc Graw Hill",4);    
20.     Book b3=new Book(103,"Operating System","Galvin","Wiley",6);    
21.     //Adding Books to Deque   
22.     set.add(b1);    
23.     set.add(b2);    
24.     set.add(b3);    
25.     //Traversing ArrayDeque  
26.     for(Book b:set){    
27.     System.out.println(b.id+" "+b.name+" "+b.author+" "+b.publisher+" "+b.quantity);    
28.     }    
29. }    
30. }    

**Output:**

101 Let us C Yashwant Kanetkar BPB 8
102 Data Communications & Networking Forouzan Mc Graw Hill 4
103 Operating System Galvin Wiley 6

The Java Deque interface offers a versatile and efficient abstraction for managing collections of elements where insertion and removal operations are required at both ends. Its rich set of methods facilitates various operations, making it suitable for a wide range of applications. Whether we are implementing double-ended queues, stack data structures, or solving complex algorithmic problems, the Deque interface provides the necessary tools to streamline your development process.