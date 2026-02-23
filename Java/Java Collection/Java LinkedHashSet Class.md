
![Java HashSet class hierarchy](https://images.tpointtech.com/images/linkedhashset.png)

Java LinkedHashSet class is a Hashtable and Linked list implementation of the Set interface. It inherits the HashSet class and implements the Set interface.

The important points about the Java LinkedHashSet class are:

- Java LinkedHashSet class contains unique elements only like HashSet.
- Java LinkedHashSet class provides all optional set operations and permits null elements.
- Java LinkedHashSet class is non-synchronized.
- Java LinkedHashSet class maintains insertion order.

#### Note: Keeping the insertion order in the LinkedHashset has some additional costs, both in terms of extra memory and extra CPU cycles. Therefore, if it is not required to maintain the insertion order, go for the lighter-weight HashMap or the HashSet instead.

## Hierarchy of LinkedHashSet class

The LinkedHashSet class extends the HashSet class, which implements the Set interface. The Set interface inherits Collection and Iterable interfaces in hierarchical order.

### LinkedHashSet Class Declaration

Let's see the declaration for java.util.LinkedHashSet class.

[](https://www.tpointtech.com/java-linkedhashset#)[](https://www.tpointtech.com/java-linkedhashset#)[](https://www.tpointtech.com/java-linkedhashset#)

1. public class LinkedHashSet<E> extends HashSet<E> implements Set<E>, Cloneable, Serializable  

### Constructors of Java LinkedHashSet Class

|Constructor|Description|
|---|---|
|HashSet()|It is used to construct a default HashSet.|
|HashSet(Collection c)|It is used to initialize the hash set by using the elements of the collection c.|
|LinkedHashSet(int capacity)|It is used to initialize the capacity of the linked hash set to the given integer value capacity.|
|LinkedHashSet(int capacity, float fillRatio)|It is used to initialize both the capacity and the fill ratio (also called load capacity) of the hash set from its argument.|

### Java LinkedHashSet Example

Let's see a simple example of the Java LinkedHashSet class. Here you can notice that the elements iterate in insertion order.

[](https://www.tpointtech.com/java-linkedhashset#)[](https://www.tpointtech.com/java-linkedhashset#)[](https://www.tpointtech.com/java-linkedhashset#)

1. import java.util.*;  
2. class Main{  
3.  public static void main(String args[]){  
4.  //Creating HashSet and adding elements  
5.         LinkedHashSet<String> set=new LinkedHashSet();  
6.                set.add("One");    
7.                set.add("Two");    
8.                set.add("Three");   
9.                set.add("Four");  
10.                set.add("Five");  
11.                Iterator<String> i=set.iterator();  
12.                while(i.hasNext())  
13.                {  
14.                System.out.println(i.next());  
15.                }  
16.  }  
17. }  

**Output:**

One
Two
Three
Four
Five

#### Note: We can also use the enhanced for loop for displaying the elements.

### Java LinkedHashSet example ignoring duplicate Elements

### Example

[](https://www.tpointtech.com/java-linkedhashset#)[](https://www.tpointtech.com/java-linkedhashset#)[](https://www.tpointtech.com/java-linkedhashset#)

1. import java.util.*;  
2. class Main{  
3.  public static void main(String args[]){  
4.   LinkedHashSet<String> al=new LinkedHashSet<String>();  
5.   al.add("Ravi");  
6.   al.add("Vijay");  
7.   al.add("Ravi");  
8.   al.add("Ajay");  
9.   Iterator<String> itr=al.iterator();  
10.   while(itr.hasNext()){  
11.    System.out.println(itr.next());  
12.   }  
13.  }  
14. }  

**Output:**

Ravi
Vijay
Ajay

### Remove Elements Using LinkeHashSet Class

### Example

[](https://www.tpointtech.com/java-linkedhashset#)[](https://www.tpointtech.com/java-linkedhashset#)[](https://www.tpointtech.com/java-linkedhashset#)

1. import java.util.*;  

2. public class Main  
3. {  

4. // main method  
5. public static void main(String argvs[])  
6. {  

7. // Creating an empty LinekdhashSet of string type  
8. LinkedHashSet<String> lhs = new LinkedHashSet<String>();  

9. // Adding elements to the above Set  
10. // by invoking the add() method  
11. lhs.add("Java");  
12. lhs.add("T");  
13. lhs.add("Point");  
14. lhs.add("Good");  
15. lhs.add("Website");  

16. // displaying all the elements on the console  
17. System.out.println("The hash set is: " + lhs);  

18. // Removing an element from the above linked Set  

19. // since the element "Good" is present, therefore, the method remove()  
20. // returns true  
21. System.out.println(lhs.remove("Good"));  

22. // After removing the element  
23. System.out.println("After removing the element, the hash set is: " + lhs);  

24. // since the element "For" is not present, therefore, the method remove()  
25. // returns false  
26. System.out.println(lhs.remove("For"));  

27. }  
28. }  

**Output:**

The hash set is: [Java, T, Point, Good, Website]
true
After removing the element, the hash set is: [Java, T, Point, Website]
false

### Java LinkedHashSet Example: Book

### Example

[](https://www.tpointtech.com/java-linkedhashset#)[](https://www.tpointtech.com/java-linkedhashset#)[](https://www.tpointtech.com/java-linkedhashset#)

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
16.     LinkedHashSet<Book> hs=new LinkedHashSet<Book>();  
17.     //Creating Books  
18.     Book b1=new Book(101,"Let us C","Yashwant Kanetkar","BPB",8);  
19.     Book b2=new Book(102,"Data Communications & Networking","Forouzan","Mc Graw Hill",4);  
20.     Book b3=new Book(103,"Operating System","Galvin","Wiley",6);  
21.     //Adding Books to hash table  
22.     hs.add(b1);  
23.     hs.add(b2);  
24.     hs.add(b3);  
25.     //Traversing hash table  
26.     for(Book b:hs){  
27.     System.out.println(b.id+" "+b.name+" "+b.author+" "+b.publisher+" "+b.quantity);  
28.     }  
29. }  
30. }  

**Output:**

101 Let us C Yashwant Kanetkar BPB 8
102 Data Communications & Networking Forouzan Mc Graw Hill 4
103 Operating System Galvin Wiley 6