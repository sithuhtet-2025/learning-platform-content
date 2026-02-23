
![Java TreeSet Class](https://d2jdgazzki9vjm.cloudfront.net/images/treeset.png)

Java TreeSet class implements the Set interface that uses a tree for storage. It inherits AbstractSet class and implements the NavigableSet interface. The objects of the TreeSet class are stored in ascending order.

The important points about the Java TreeSet class are:

- Java TreeSet class contains unique elements only like HashSet.
- Java TreeSet class access and retrieval times are quite fast.
- Java TreeSet class doesn't allow null elements.
- Java TreeSet class is non-synchronized.
- Java TreeSet class maintains ascending order.
- The TreeSet can only allow those generic types that are comparable. For example, the Comparable interface is being implemented by the StringBuffer class.

### Internal Working of The TreeSet Class

TreeSet is being implemented using a binary search tree, which is self-balancing just like a Red-Black Tree. Therefore, operations such as a search, remove, and add consume O(log(N)) time. The reason behind this is there in the self-balancing tree. It is there to ensure that the tree height never exceeds O(log(N)) for all of the mentioned operations. Therefore, it is one of the efficient data structures in order to keep the large data that is sorted and also to do operations on it.

### Key Aspects of TreeSet's Functionality

- **Red-Black Tree Structure:** Each node in this tree is assigned a color-either red or black-which plays a crucial role in maintaining the tree's balance. This strategic coloring helps prevent the tree from becoming lopsided, which enhances performance and ensures that operations are processed quickly and efficiently.
- **Dynamic Rebalancing:** Whenever elements are added or removed, **TreeSet** dynamically adjusts its internal structure. It ensures that the set's elements are always in ascending order, making it highly reliable for applications that require well-ordered data.
- **Handling Duplicates:** TreeSet is designed to store only unique elements. Attempts to add duplicates are gracefully handled by the set, ensuring that only distinct elements are maintained. It is crucial for data integrity and simplifies management of collections where uniqueness is a priority.
- **Order Determination:** The sorting of elements within TreeSet can follow the natural ordering of the elements or be defined by a custom comparator. This flexibility allows developers to control how elements are compared and ordered within the set.

### Synchronization of The TreeSet Class

As already mentioned above, the TreeSet class is not synchronized. It means, if more than one thread concurrently accesses a tree set, and one of them accessing thread to modify it, then the synchronization must be done manually. It is usually done by doing some object synchronization techniques that encapsulates the set. However, in the case where no such object is found, then the set must be wrapped with the help of the Collections.synchronizedSet() method. It is advised to use the method during creation time in order to avoid the unsynchronized access of the set. The following code snippet shows the same.

### Synchronization of The TreeSet Class

As already mentioned above, the TreeSet class is not synchronized. It means if more than one thread concurrently accesses a tree set, and one of the accessing threads modify it, then the synchronization must be done manually. It is usually done by doing some object synchronization that encapsulates the set. However, in the case where no such object is found, then the set must be wrapped with the help of the Collections.synchronizedSet() method. It is advised to use the method during creation time in order to avoid the unsynchronized access of the set. The following code snippet shows the same.

[](https://www.tpointtech.com/java-treeset#)[](https://www.tpointtech.com/java-treeset#)[](https://www.tpointtech.com/java-treeset#)

1. TreeSet treeSet = new TreeSet();   
2. Set syncrSet = Collections.synchronziedSet(treeSet);  

### Hierarchy of theTreeSet Class

As shown in the above diagram, the Java TreeSet class implements the NavigableSet interface. The NavigableSet interface extends SortedSet, Set, Collection and Iterable interfaces in hierarchical order.

The TreeSet class in Java is a crucial part of the Java Collections Framework, designed to store elements in a sorted and unique manner, ensuring no duplicates. Here are the key points about its hierarchical structure:

**SortedSet Interface:** TreeSet directly implements the SortedSet interface, which extends the basic Set interface. This interface introduces methods for operations that maintain an order among the elements and support range-view functionalities, essential for ordered data manipulation.

**NavigableSet Interface:** Positioned below the SortedSet, the NavigableSet interface adds advanced navigation capabilities. It allows TreeSet to retrieve elements based on their precise relation to others in the set, enhancing its functionality for efficient data querying and manipulation.

**Efficiency:** Backed by a TreeMap using a red-black tree structure, TreeSet performs fundamental operations like adding, removing, and checking the presence of elements with logarithmic time complexity, making it ideal for high-performance applications that require quick data processing.

### TreeSet Class Declaration

Let's see the declaration for java.util.TreeSet class.

[](https://www.tpointtech.com/java-treeset#)[](https://www.tpointtech.com/java-treeset#)[](https://www.tpointtech.com/java-treeset#)

1. public class TreeSet<E> extends AbstractSet<E> implements NavigableSet<E>, Cloneable, Serializable    

### Components of the Declaration

1. **TreeSet<E> Class:** The TreeSet class is declared as public, meaning it can be accessed from anywhere class within any package.  
    The <E> denotes that TreeSet is a generic class, capable of storing objects of any type, as specified by the user.
2. **AbstractSet<E>:** TreeSet class extends the AbstractSet interface that provides a skeletal implementation of the Set interface. It means that the TreeSet class inherits all the abstract methods from the AbstractSet interface.
3. **NavigableSet<E>:** By implementing NavigableSet, TreeSet gains() methods to navigate the set in relation to a given target element, such as higher, lower, ceiling, and floor. The interface extends SortedSet, which in turn extends Set, ensuring that TreeSet has all functionalities of a sorted and navigable set.
4. **Cloneable:** It indicates that TreeSet supports cloning, allowing it to be copied safely without affecting the original set.
5. **Serializable:** It ensures that a TreeSet can be serialized, meaning its state can be converted into a byte stream that can be reverted back into a copy of the TreeSet. Serialization is essential for saving the state of an object for later retrieval or transmission to a different processing environment.

### Constructors of Java TreeSet Class

|Constructor|Description|
|---|---|
|TreeSet()|It is used to construct an empty tree set that will be sorted in ascending order according to the natural order of the tree set.|
|TreeSet(Collection<? extends E> c)|It is used to build a new tree set that contains the elements of the collection c.|
|TreeSet(Comparator<? super E> comparator)|It is used to construct an empty tree set that will be sorted according to given comparator.|
|TreeSet(SortedSet<E> s)|It is used to build a TreeSet that contains the elements of the given SortedSet.|

### Methods of Java TreeSet Class

|Method|Description|
|---|---|
|boolean add(E e)|It is used to add the specified element to this set if it is not already present.|
|boolean addAll(Collection<? extends E> c)|It is used to add all of the elements in the specified collection to this set.|
|E ceiling(E e)|It returns the equal or closest greatest element of the specified element from the set, or null there is no such element.|
|Comparator<? super E> comparator()|It returns a comparator that arranges elements in order.|
|IteratordescendingIterator()|It is used to iterate the elements in descending order.|
|NavigableSetdescendingSet()|It returns the elements in reverse order.|
|E floor(E e)|It returns the equal or closest least element of the specified element from the set, or null there is no such element.|
|SortedSetheadSet(E toElement)|It returns the group of elements that are less than the specified element.|
|NavigableSetheadSet(E toElement, boolean inclusive)|It returns the group of elements that are less than or equal to (if, inclusive is true) the specified element.|
|E higher(E e)|It returns the closest greatest element of the specified element from the set, or null there is no such element.|
|Iteratoriterator()|It is used to iterate the elements in ascending order.|
|E lower(E e)|It returns the closest least element of the specified element from the set, or null there is no such element.|
|E pollFirst()|It is used to retrieve and remove the lowest(first) element.|
|E pollLast()|It is used to retrieve and remove the highest(last) element.|
|Spliteratorspliterator()|It is used to create a late-binding and fail-fast spliterator over the elements.|
|NavigableSetsubSet(E fromElement, boolean fromInclusive, E toElement, boolean toInclusive)|It returns a set of elements that lie between the given range.|
|SortedSetsubSet(E fromElement, E toElement))|It returns a set of elements that lie between the given range which includes fromElement and excludes toElement.|
|SortedSettailSet(E fromElement)|It returns a set of elements that are greater than or equal to the specified element.|
|NavigableSettailSet(E fromElement, boolean inclusive)|It returns a set of elements that are greater than or equal to (if, inclusive is true) the specified element.|
|boolean contains(Object o)|It returns true if this set contains the specified element.|
|boolean isEmpty()|It returns true if this set contains no elements.|
|boolean remove(Object o)|It is used to remove the specified element from this set if it is present.|
|void clear()|It is used to remove all of the elements from this set.|
|Object clone()|It returns a shallow copy of this TreeSet instance.|
|E first()|It returns the first (lowest) element currently in this sorted set.|
|E last()|It returns the last (highest) element currently in this sorted set.|
|int size()|It returns the number of elements in this set.|

### Java TreeSet Examples

### Java TreeSet Example 1:

Let's see a simple example of Java TreeSet.

**FileName:** TreeSet1.java

[](https://www.tpointtech.com/java-treeset#)[](https://www.tpointtech.com/java-treeset#)[](https://www.tpointtech.com/java-treeset#)

1. import java.util.*;  
2. class TreeSet1{  
3.  public static void main(String args[]){  
4.   //Creating and adding elements  
5.   TreeSet<String> al=new TreeSet<String>();  
6.   al.add("Ravi");  
7.   al.add("Vijay");  
8.   al.add("Ravi");  
9.   al.add("Ajay");  
10.   //Traversing elements  
11.   Iterator<String> itr=al.iterator();  
12.   while(itr.hasNext()){  
13.    System.out.println(itr.next());  
14.   }  
15.  }  
16. }  

**Output:**

Ajay
Ravi
Vijay

### Java TreeSet Example 2:

Let's see an example of traversing elements in descending order.

**FileName:** TreeSet2.java

[](https://www.tpointtech.com/java-treeset#)[](https://www.tpointtech.com/java-treeset#)[](https://www.tpointtech.com/java-treeset#)

1. import java.util.*;  
2. class TreeSet2{  
3.  public static void main(String args[]){  
4.  TreeSet<String> set=new TreeSet<String>();  
5.          set.add("Ravi");  
6.          set.add("Vijay");  
7.          set.add("Ajay");  
8.          System.out.println("Traversing element through Iterator in descending order");  
9.          Iterator i=set.descendingIterator();  
10.          while(i.hasNext())  
11.          {  
12.              System.out.println(i.next());  
13.          }  

14.  }  
15. }  

**Output:**

Traversing element through Iterator in descending order
Vijay
Ravi
Ajay
Traversing element through NavigableSet in descending order
Vijay
Ravi
Ajay

### Java TreeSet Example 3:

Let's see an example to retrieve and remove the highest and lowest Value.

**FileName:** TreeSet3.java

[](https://www.tpointtech.com/java-treeset#)[](https://www.tpointtech.com/java-treeset#)[](https://www.tpointtech.com/java-treeset#)

1. import java.util.*;    
2. class TreeSet3{    
3.  public static void main(String args[]){    
4.  TreeSet<Integer> set=new TreeSet<Integer>();    
5.          set.add(24);    
6.          set.add(66);    
7.          set.add(12);    
8.          set.add(15);    
9.          System.out.println("Lowest Value: "+set.pollFirst());    
10.          System.out.println("Highest Value: "+set.pollLast());    
11.  }    
12. }    

**Output:**

Lowest Value: 12
Highest Value: 66

### Java TreeSet Example 4:

In this example, we perform various NavigableSet operations.

**FileName:** TreeSet4.java

[](https://www.tpointtech.com/java-treeset#)[](https://www.tpointtech.com/java-treeset#)[](https://www.tpointtech.com/java-treeset#)

1. import java.util.*;  
2. class TreeSet4{  
3.  public static void main(String args[]){  
4.   TreeSet<String> set=new TreeSet<String>();  
5.          set.add("A");  
6.          set.add("B");  
7.          set.add("C");  
8.          set.add("D");  
9.          set.add("E");  
10.          System.out.println("Initial Set: "+set);  

11.          System.out.println("Reverse Set: "+set.descendingSet());  

12.          System.out.println("Head Set: "+set.headSet("C", true));  

13.          System.out.println("SubSet: "+set.subSet("A", false, "E", true));  

14.          System.out.println("TailSet: "+set.tailSet("C", false));  
15.  }  
16. }  

**Output:**

Initial Set: [A, B, C, D, E]
Reverse Set: [E, D, C, B, A]
Head Set: [A, B, C]
SubSet: [B, C, D, E]
TailSet: [D, E]

### Java TreeSet Example 5:

In this example, we perform various SortedSetSet operations.

**FileName:** TreeSet5.java

[](https://www.tpointtech.com/java-treeset#)[](https://www.tpointtech.com/java-treeset#)[](https://www.tpointtech.com/java-treeset#)

1. import java.util.*;  
2. class TreeSet5{  
3.  public static void main(String args[]){  
4.   TreeSet<String> set=new TreeSet<String>();  
5.          set.add("A");  
6.          set.add("B");  
7.          set.add("C");  
8.          set.add("D");  
9.          set.add("E");  

10.          System.out.println("Intial Set: "+set);  

11.          System.out.println("Head Set: "+set.headSet("C"));  

12.          System.out.println("SubSet: "+set.subSet("A", "E"));  

13.          System.out.println("TailSet: "+set.tailSet("C"));  
14.  }  
15. }  

**Output:**

Intial Set: [A, B, C, D, E]
Head Set: [A, B]
SubSet: [A, B, C, D]
TailSet: [C, D, E]

### Java TreeSet Example: Book

Let's see a TreeSet example where we are adding books to the set and printing all the books. The elements in TreeSet must be of a Comparable type. String and Wrapper classes are Comparable by default. To add user-defined objects in TreeSet, you need to implement the Comparable interface.

**FileName:** TreeSetExample.java

[](https://www.tpointtech.com/java-treeset#)[](https://www.tpointtech.com/java-treeset#)[](https://www.tpointtech.com/java-treeset#)

1. import java.util.*;    
2. class Book implements Comparable<Book>{    
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
13. // implementing the abstract method  
14. public int compareTo(Book b) {    
15.     if(id>b.id){    
16.         return 1;    
17.     }else if(id<b.id){    
18.         return -1;    
19.     }else{    
20.     return 0;    
21.     }    
22. }    
23. }    
24. public class TreeSetExample {    
25. public static void main(String[] args) {    
26.     Set<Book> set=new TreeSet<Book>();    
27.     //Creating Books    
28.     Book b1=new Book(121,"Let us C","Yashwant Kanetkar","BPB",8);    
29.     Book b2=new Book(233,"Operating System","Galvin","Wiley",6);    
30.     Book b3=new Book(101,"Data Communications & Networking","Forouzan","Mc Graw Hill",4);    
31.     //Adding Books to TreeSet    
32.     set.add(b1);    
33.     set.add(b2);    
34.     set.add(b3);    
35.     //Traversing TreeSet    
36.     for(Book b:set){    
37.     System.out.println(b.id+" "+b.name+" "+b.author+" "+b.publisher+" "+b.quantity);    
38.     }    
39. }    
40. }    

**Output:**

101 Data Communications & Networking Forouzan Mc Graw Hill 4
121 Let us C Yashwant Kanetkar BPB 8
233 Operating System Galvin Wiley 6

### ClassCast Exception in TreeSet

If we add an object of the class that is not implementing the Comparable interface, the ClassCast Exception is raised. Observe the following program.

**FileName:** ClassCastExceptionTreeSet.java

[](https://www.tpointtech.com/java-treeset#)[](https://www.tpointtech.com/java-treeset#)[](https://www.tpointtech.com/java-treeset#)

1. // important import statement  
2. import java.util.*;  

3. class Employee  
4. {  

5. int empId;  
6. String name;  

7. // getting the name of the employee  
8. String getName()  
9. {  
10.     return this.name;  
11. }  

12. // setting the name of the employee  
13. void setName(String name)  
14. {  
15. this.name = name;  
16. }  

17. // setting the employee id   
18. // of the employee  
19. void setId(int a)  
20. {  
21. this.empId = a;  
22. }  

23. // retrieving the employee id of  
24. // the employee  
25. int getId()  
26. {  
27. return this.empId;  
28. }  

29. }  

30. public class ClassCastExceptionTreeSet  
31. {  

32. // main method  
33. public static void main(String[] argvs)  
34. {  
35. // creating objects of the class Employee  
36. Employee obj1 = new Employee();  

37. Employee obj2 = new Employee();  

38. TreeSet<Employee> ts =  new TreeSet<Employee>();  

39. // adding the employee objects to   
40. // the TreeSet class  
41. ts.add(obj1);  
42. ts.add(obj2);  

43. System.out.println("The program has been executed successfully.");  

44. }  
45. }  

**Output:**

Exception in thread "main" java.lang.ClassCastException: class Employee cannot be cast to class java.lang.Comparable (Employee is in unnamed module of loader 'app'; java.lang.Comparable is in module java.base of loader 'bootstrap')
at java.base/java.util.TreeMap.compare(TreeMap.java:1569)
at java.base/java.util.TreeMap.addEntryToEmptyMap(TreeMap.java:776)
at java.base/java.util.TreeMap.put(TreeMap.java:785)
at java.base/java.util.TreeMap.put(TreeMap.java:534)
at java.base/java.util.TreeSet.add(TreeSet.java:255)
at ClassCastExceptionTreeSet.main(ClassCastExceptionTreeSet.java:52)

**Explanation:** In the above program, it is required to implement a Comparable interface. It is because the TreeSet maintains the sorting order, and for doing the sorting the comparison of different objects that are being inserted in the TreeSet is must, which is accomplished by implementing the Comparable interface.

## TreeSet Vs. HashSet

|Feature|TreeSet|HashSet|
|---|---|---|
|**Underlying Data Structure**|Red-Black Tree|Hash Table|
|**Ordering of Elements**|Keeps elements sorted, which facilitates ordered traversal and quick-range searches.|Does not maintain any order; element arrangement is determined by the hash function.|
|**Performance for Basic Operations**|Somewhat increased temporal complexity; operations like add, delete, and contain are ?(log⁡?)_O_(log_N_).|Constant-time complexity ?(1)_O_(1) for basic operations like add, delete, and contain, making it highly efficient.|
|**Best Use Case**|Better suited for applications requiring ordered data management, such as range queries or sequential access.|Ideal for scenarios where quick retrieval and manipulation are more important than element order.|
|**Sorting**|Automatically sorts elements according to their natural ordering or a specified comparator.|No sorting of elements; storage is hash-based.|
|**Application Suitability**|Preferred for applications where elements need to be maintained in a sorted manner.|More suitable for applications requiring fast access and where element order is not a concern.|