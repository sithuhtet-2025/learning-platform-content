Java HashSet class is used to create a collection that uses a hash table for storage. It inherits the AbstractSet class and implements Set interface.

The important points about Java HashSet class are:

- HashSet stores the elements by using a mechanism called **hashing.**
- HashSet contains unique elements only.
- HashSet allows null value.
- HashSet class is non synchronized.
- HashSet doesn't maintain the insertion order. Here, elements are inserted on the basis of their hashcode.
- HashSet is the best approach for search operations.
- The initial default capacity of HashSet is 16, and the load factor is 0.75.

## Difference Between List and Set

A list can contain duplicate elements whereas Set contains unique elements only.

### Hierarchy of HashSet class

The HashSet class extends AbstractSet class which implements Set interface. The Set interface inherits Collection and Iterable interfaces in hierarchical order.

A HashSet in Java is a collection class that implements the Set interface, which means it stores a collection of unique elements. It does not allow duplicate elements. Internally, a HashSet uses a HashMap to store its elements. Each element in the HashSet is stored as a key in the HashMap, with a dummy value associated with it. HashSet uses the hash code of an element to determine its position in the underlying hash table, which allows for constant-time performance for basic operations like add, remove, and contains, assuming a good hash function.

![Java HashSet class hierarchy](https://d2jdgazzki9vjm.cloudfront.net/images/hashset.png)

One of the key features of a HashSet is its ability to maintain a collection of elements without any specific order. It means that the order in which elements are added to a HashSet is not preserved when iterating over the elements. If we need to maintain the insertion order, we can use a LinkedHashSet, which is another implementation of the Set interface that maintains the insertion order of its elements.

HashSet does not allow null elements, but it can contain a single null value. If we attempt to add a duplicate element to a HashSet, the add method will return false and the HashSet will remain unchanged. HashSet also provides methods for set operations like union, intersection, and difference. However, unlike some other collection classes, HashSet is not synchronized, meaning that it is not thread-safe. If you need a synchronized (thread-safe) version of HashSet, we can use the Collections.synchronizedSet method to wrap your HashSet with a synchronized set.

### HashSet Class Declaration

Let's see the declaration for java.util.HashSet class.

[](https://www.tpointtech.com/java-hashset#)[](https://www.tpointtech.com/java-hashset#)[](https://www.tpointtech.com/java-hashset#)

1. public class HashSet<E> extends AbstractSet<E> implements Set<E>, Cloneable, Serializable  

## Constructors of Java HashSet Class

|SN|Constructor|Description|
|---|---|---|
|1)|HashSet()|It is used to construct a default HashSet.|
|2)|HashSet(int capacity)|It is used to initialize the capacity of the hash set to the given integer value capacity. The capacity grows automatically as elements are added to the HashSet.|
|3)|HashSet(int capacity, float loadFactor)|It is used to initialize the capacity of the hash set to the given integer value capacity and the specified load factor.|
|4)|HashSet(Collection<? extends E> c)|It is used to initialize the hash set by using the elements of the collection c.|

## Methods of Java HashSet Class

|SN|Modifier & Type|Method|Description|
|---|---|---|---|
|1)|boolean|[add(E e)](https://www.tpointtech.com/java-hashset-add-method)|It is used to add the specified element to this set if it is not already present.|
|2)|void|[clear()](https://www.tpointtech.com/java-hashset-clear-method)|It is used to remove all of the elements from the set.|
|3)|object|[clone()](https://www.tpointtech.com/java-hashset-clone-method)|It is used to return a shallow copy of this HashSet instance: the elements themselves are not cloned.|
|4)|boolean|[contains(Object o)](https://www.tpointtech.com/java-hashset-contains-method)|It is used to return true if this set contains the specified element.|
|5)|boolean|[isEmpty()](https://www.tpointtech.com/java-hashset-isempty-method)|It is used to return true if this set contains no elements.|
|6)|Iterator<E>|[iterator()](https://www.tpointtech.com/java-hashset-iterator-method)|It is used to return an iterator over the elements in this set.|
|7)|boolean|[remove(Object o)](https://www.tpointtech.com/java-hashset-remove-method)|It is used to remove the specified element from this set if it is present.|
|8)|int|[size()](https://www.tpointtech.com/java-hashset-size-method)|It is used to return the number of elements in the set.|
|9)|Spliterator<E>|[spliterator()](https://www.tpointtech.com/java-hashset-spliterator-method)|It is used to create a late-binding and fail-fast Spliterator over the elements in the set.|

---

### Java HashSet Example

Let's see a simple example of HashSet. Notice, the elements iterate in an unordered collection.

**HashSetExample1.java**

[](https://www.tpointtech.com/java-hashset#)[](https://www.tpointtech.com/java-hashset#)[](https://www.tpointtech.com/java-hashset#)

1. import java.util.*;    
2. class Main{    
3.  public static void main(String args[]){    
4.   //Creating HashSet and adding elements    
5.     HashSet<String> set=new HashSet();    
6.            set.add("One");      
7.            set.add("Two");      
8.            set.add("Three");     
9.            set.add("Four");    
10.            set.add("Five");    
11.            Iterator<String> i=set.iterator();    
12.            while(i.hasNext())    
13.            {    
14.            System.out.println(i.next());    
15.            }    
16.  }    
17. }   

**Output:**

Five
One
Four
Two
Three

### Ignoring Duplicate Elements

In this example, we see that HashSet does not allows duplicate elements.

### Example

[](https://www.tpointtech.com/java-hashset#)[](https://www.tpointtech.com/java-hashset#)[](https://www.tpointtech.com/java-hashset#)

1. import java.util.*;    
2. class Main{    
3.  public static void main(String args[]){    
4.   //Creating HashSet and adding elements    
5.   HashSet<String> set=new HashSet<String>();    
6.   set.add("Ravi");    
7.   set.add("Vijay");    
8.   set.add("Ravi");    
9.   set.add("Ajay");    
10.   //Traversing elements    
11.   Iterator<String> itr=set.iterator();    
12.   while(itr.hasNext()){    
13.    System.out.println(itr.next());    
14.   }    
15.  }    
16. }    

**Output:**

Ajay
Vijay
Ravi

### Removing Elements

Here, we see different ways to remove an element.

### Example

[](https://www.tpointtech.com/java-hashset#)[](https://www.tpointtech.com/java-hashset#)[](https://www.tpointtech.com/java-hashset#)

1. import java.util.*;    
2. class Main{    
3.  public static void main(String args[]){    
4.   HashSet<String> set=new HashSet<String>();    
5.            set.add("Ravi");    
6.            set.add("Vijay");    
7.            set.add("Arun");    
8.            set.add("Sumit");    
9.            System.out.println("An initial list of elements: "+set);    
10.            //Removing specific element from HashSet    
11.            set.remove("Ravi");    
12.            System.out.println("After invoking remove(object) method: "+set);    
13.            HashSet<String> set1=new HashSet<String>();    
14.            set1.add("Ajay");    
15.            set1.add("Gaurav");    
16.            set.addAll(set1);    
17.            System.out.println("Updated List: "+set);    
18.            //Removing all the new elements from HashSet    
19.            set.removeAll(set1);    
20.            System.out.println("After invoking removeAll() method: "+set);    
21.            //Removing elements on the basis of specified condition    
22.            set.removeIf(str->str.contains("Vijay"));      
23.            System.out.println("After invoking removeIf() method: "+set);    
24.            //Removing all the elements available in the set    
25.            set.clear();    
26.            System.out.println("After invoking clear() method: "+set);    
27.  }    
28. }    

**Output:**

An initial list of elements: [Vijay, Ravi, Arun, Sumit]
After invoking remove(object) method: [Vijay, Arun, Sumit]
Updated List: [Vijay, Arun, Gaurav, Sumit, Ajay]
After invoking removeAll() method: [Vijay, Arun, Sumit]
After invoking removeIf() method: [Arun, Sumit]
After invoking clear() method: []

### Java HashSet from another Collection

**HashSetExample4.java**

[](https://www.tpointtech.com/java-hashset#)[](https://www.tpointtech.com/java-hashset#)[](https://www.tpointtech.com/java-hashset#)

1. import java.util.*;    
2. class Main{    
3.  public static void main(String args[]){    
4.    ArrayList<String> list=new ArrayList<String>();    
5.            list.add("Ravi");    
6.            list.add("Vijay");    
7.            list.add("Ajay");    

8.            HashSet<String> set=new HashSet(list);    
9.            set.add("Gaurav");    
10.            Iterator<String> i=set.iterator();    
11.            while(i.hasNext())    
12.            {    
13.            System.out.println(i.next());    
14.            }    
15.  }    
16. }    

**Output:**

Vijay
Ravi
Gaurav
Ajay

### Java HashSet Example: Book

Let's see a HashSet example where we are adding books to set and printing all the books.

### Example

[](https://www.tpointtech.com/java-hashset#)[](https://www.tpointtech.com/java-hashset#)[](https://www.tpointtech.com/java-hashset#)

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
16.     HashSet<Book> set=new HashSet<Book>();  
17.     //Creating Books  
18.     Book b1=new Book(101,"Let us C","Yashwant Kanetkar","BPB",8);  
19.     Book b2=new Book(102,"Data Communications & Networking","Forouzan","Mc Graw Hill",4);  
20.     Book b3=new Book(103,"Operating System","Galvin","Wiley",6);  
21.     //Adding Books to HashSet  
22.     set.add(b1);  
23.     set.add(b2);  
24.     set.add(b3);  
25.     //Traversing HashSet  
26.     for(Book b:set){  
27.     System.out.println(b.id+" "+b.name+" "+b.author+" "+b.publisher+" "+b.quantity);  
28.     }  
29. }  
30. }  

**Output:**

101 Let us C Yashwant Kanetkar BPB 8
102 Data Communications & Networking Forouzan Mc Graw Hill 4
103 Operating System Galvin Wiley 6

Let's understand about Java HashSet in Java with the help of an example program.

### Example 1:

**Filename:** HashSetExample.java

[](https://www.tpointtech.com/java-hashset#)[](https://www.tpointtech.com/java-hashset#)[](https://www.tpointtech.com/java-hashset#)

1. // Java program to demonstrate the features and functionalities of Java HashSet.  
2. import java.util.HashSet;  
3. import java.util.Iterator;  
4. class Person {  
5.     private String name;  
6.     private int age;  
7.     public Person(String name, int age) {  
8.         this.name = name;  
9.         this.age = age;  
10.     }  
11.     @Override  
12.     public boolean equals(Object o) {  
13.         if (this == o) return true;  
14.         if (o == null || getClass() != o.getClass()) return false;  
15.         Person person = (Person) o;  
16.         return age == person.age && name.equals(person.name);  
17.     }  
18.     @Override  
19.     public int hashCode() {  
20.         return name.hashCode() + age;  
21.     }  
22.     @Override  
23.     public String toString() {  
24.         return "Person{" +  
25.                 "name='" + name + '\'' +  
26.                 ", age=" + age +  
27.                 '}';  
28.     }  
29. }  
30. public class HashSetExample {  
31.     public static void main(String[] args) {  
32.         // Create a HashSet  
33.         HashSet<String> hashSet = new HashSet<>();  
34.         // Add elements to the HashSet  
35.         hashSet.add("Apple");  
36.         hashSet.add("Banana");  
37.         hashSet.add("Orange");  
38.         // Display the HashSet  
39.         System.out.println("HashSet: " + hashSet);  
40.         // Iterate over the HashSet using an Iterator  
41.         System.out.print("Iterating over the HashSet using Iterator: ");  
42.         Iterator<String> iterator = hashSet.iterator();  
43.         while (iterator.hasNext()) {  
44.             String element = iterator.next();  
45.             System.out.print(element + " ");  
46.         }  
47.         System.out.println();  
48.         // Convert HashSet to an array  
49.         String[] array = hashSet.toArray(new String[0]);  
50.         System.out.print("HashSet converted to array: ");  
51.         for (String element : array) {  
52.             System.out.print(element + " ");  
53.         }  
54.         System.out.println();  
55.         // Create a HashSet of custom objects  
56.         HashSet<Person> personSet = new HashSet<>();  
57.         personSet.add(new Person("Alice", 30));  
58.         personSet.add(new Person("Bob", 25));  
59.         // Display the HashSet of custom objects  
60.         System.out.println("HashSet of custom objects: " + personSet);  
61.     }  
62. }  

**Output:**

HashSet: [Apple, Orange, Banana]
Iterating over the HashSet using Iterator: Apple Orange Banana
HashSet converted to array: Apple Orange Banana
HashSet of custom objects: [Person{name='Alice', age=30}, Person{name='Bob', age=25}]