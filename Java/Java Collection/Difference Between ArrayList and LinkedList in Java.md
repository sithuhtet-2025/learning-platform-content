## ArrayList

In Java, an ArrayList is a **resizable array.** It belongs to java.util package. Unlike regular arrays, which have a fixed size, an ArrayList can grow or shrink dynamically as elements are added or removed.

### Key Features of ArrayList

- **Dynamic resizing**: No need to specify size upfront.
- **Allows duplicate elements**: Unlike sets, it permits duplicates.
- **Maintains insertion order**: Elements are stored in the order they were added.
- **Random access**: Uses an index-based approach for fast retrieval.
- **Not synchronized**: Unlike Vector, ArrayList is not thread-safe.

To read More [Java ArrayList](https://www.tpointtech.com/java-arraylist)

## LinkedList

A **LinkedList** is a **doubly linked list** implementation of the List and Deque interfaces. It also uses a dynamic array, like ArrayList. Each element in the LinkedList is stored as a node. Each node contains: **Data** (the actual element), **Reference to the next node**, **Reference to the previous node** (in a doubly linked list).

### Key Features of LinkedList

- Efficient insertions/deletions
- Maintains insertion order
- Implements both List and Deque
- Not synchronized

To read more [Java LinkedList](https://www.tpointtech.com/java-linkedlist)

## Example of ArrayList and LinkedList in Java

Let's see a simple example where we are using ArrayList and LinkedList.

### Example

[](https://www.tpointtech.com/difference-between-arraylist-and-linkedlist#)[](https://www.tpointtech.com/difference-between-arraylist-and-linkedlist#)[](https://www.tpointtech.com/difference-between-arraylist-and-linkedlist#)

1. import java.util.*;      
2. public class Main {      
3.  public static void main(String args[]){      
4.   List<String> al=new ArrayList<String>();//creating arraylist      
5.   al.add("Andrew");//adding object in arraylist      
6.   al.add("John");      
7.   al.add("Lucy");      
8.   al.add("Peter");      
9.   List<String> al2=new LinkedList<String>();//creating linkedlist      
10.   al2.add("Akshat");//adding object in linkedlist      
11.   al2.add("Satwik");      
12.   al2.add("Aryan");      
13.   al2.add("Hrithik");    
14.   System.out.println("arraylist: "+al);    
15.   System.out.println("linkedlist: "+al2);    
16.  }      
17. }     

**Output:**

arraylist: [Andrew, John, Lucy, Peter]
linkedlist: [Akshat, Satwik, Aryan, Hrithik]

Therefore, ArrayList and LinkedList both implements the List interface and maintain insertion order. Both are non-synchronized classes.

## ArrayList Vs. LinkedList

|ArrayList|LinkedList|
|---|---|
|ArrayList internally uses a **dynamic array** to store the elements.|LinkedList internally uses a **doubly linked list** to store the elements.|
|Manipulation with ArrayList is **slow** because it internally uses an array. If any element is removed from the array, all the other elements are shifted in memory.|Manipulation with LinkedList is **faster** than ArrayList because it uses a doubly linked list, so no bit shifting is required in memory.|
|An ArrayList class can **act as a list** only because it implements the List only.|The LinkedList class can **act as both a list and a queue because it implements the** List and Deque interfaces.|
|ArrayList is **better for storing and accessing** data.|LinkedList is **better for manipulating** data.|
|The memory location of the elements of an ArrayList is contiguous.|The location of the elements of a linked list is not contagious.|
|Generally, when an ArrayList is initialized, a default capacity of 10 is assigned to the ArrayList.|There is no case of default capacity in a LinkedList. In LinkedList, an empty list is created when a LinkedList is initialized.|
|To be precise, an ArrayList is a resizable array.|LinkedList implements the doubly linked list of list interface.|
|Less memory is used.|More memory is used.|

## Points to Remember

The following are some important points to remember regarding an ArrayList and a LinkedList.

- When the rate of addition or removal rate is more than the read scenarios, then go for the LinkedList. On the other hand, when the frequency of the read scenarios is more than the addition or removal rate, then ArrayList takes precedence over LinkedList.
- Since the elements of an ArrayList are stored more compactly as compared to a LinkedList; therefore, the ArrayList is more cache-friendly as compared to the LinkedList. Thus, the chances of a cache miss are less in an ArrayList as compared to a LinkedList. Generally, it is considered that a LinkedList is poor in cache locality.
- Memory overhead in the LinkedList is more than compared of the ArrayList. It is because, in a LinkedList, we have two extra links (next and previous) as it is required to store the address of the previous and the next nodes, and these links consume additional Such links are not present in an ArrayList.