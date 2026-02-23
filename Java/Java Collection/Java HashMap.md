Java **HashMap** class implements the Map interface which allows us _to store key and value pair_, where keys should be unique. If you try to insert the duplicate key, it will replace the element of the corresponding key. It is easy to perform operations using the key index like updation, deletion, etc. HashMap class is found in the java.util package.

HashMap in Java is like the legacy Hashtable class, but it is not synchronized. It allows us to store the null elements as well, but there should be only one null key. Since Java 5, it is denoted as HashMap<K,V>, where K stands for key and V for value. It inherits the AbstractMap class and implements the Map interface.

## Hierarchy of HashMap Class

![Java HashMap](https://d2jdgazzki9vjm.cloudfront.net/core/images/java-hashmap.png)

As shown in the above figure, the HashMap class extends the AbstractMap class and implements the Map interface.

### HashMap Class Declaration

Let's see the declaration for java.util.HashMap class.

[](https://www.tpointtech.com/java-hashmap#)[](https://www.tpointtech.com/java-hashmap#)[](https://www.tpointtech.com/java-hashmap#)

1. public class HashMap<K,V> extends AbstractMap<K,V> implements Map<K,V>, Cloneable, Serializable  

### HashMap Class Parameters

Let's see the Parameters for java.util.HashMap class.

- **K:** It is the type of keys maintained by this map.
- **V:** It is the type of mapped values.

### Constructors of Java HashMap Class

|Constructor|Description|
|---|---|
|HashMap()|It is used to construct a default HashMap.|
|HashMap(Map<? extends K,? extends V> m)|It is used to initialize the hash map by using the elements of the given Map object m.|
|HashMap(int capacity)|It is used to initializes the capacity of the hash map to the given integer value, capacity.|
|HashMap(int capacity, float loadFactor)|It is used to initialize both the capacity and load factor of the hash map by using its arguments.|
|HashMap(int capacity, float loadFactor, boolean accessOrder)|It is used to specify the ordering mode and initialize the hash map's capacity and load factor using its inputs.|

### Methods of Java HashMap Class

|Method|Description|
|---|---|
|void clear()|It is used to remove all of the mappings from this map.|
|boolean isEmpty()|It is used to return true if this map contains no key-value mappings.|
|Object clone()|It is used to return a shallow copy of this HashMap instance: the keys and values themselves are not cloned.|
|Set entrySet()|It is used to return a collection view of the mappings contained in this map.|
|Set keySet()|It is used to return a set view of the keys contained in this map.|
|V put(Object key, Object value)|It is used to insert an entry in the map.|
|void putAll(Map map)|It is used to insert the specified map in the map.|
|V putIfAbsent(K key, V value)|It inserts the specified value with the specified key in the map only if it is not already specified.|
|V remove(Object key)|It is used to delete an entry for the specified key.|
|boolean remove(Object key, Object value)|It removes the specified values with the associated specified keys from the map.|
|V compute(K key, BiFunction<? super K,? super V,? extends V> remappingFunction)|It is used to compute a mapping for the specified key and its current mapped value (or null if there is no current mapping).|
|V computeIfAbsent(K key, Function<? super K,? extends V> mappingFunction)|It is used to compute its value using the given mapping function, if the specified key is not already associated with a value (or is mapped to null), and enters it into this map unless null.|
|V computeIfPresent(K key, BiFunction<? super K,? super V,? extends V> remappingFunction)|It is used to compute a new mapping given the key and its current mapped value if the value for the specified key is present and non-null.|
|boolean containsValue(Object value)|This method returns true if some value equal to the value exists within the map, else return false.|
|boolean containsKey(Object key)|This method returns true if some key equal to the key exists within the map, else return false.|
|boolean equals(Object o)|It is used to compare the specified Object with the Map.|
|void forEach(BiConsumer<? super K,? super V> action)|It performs the given action for each entry in the map until all entries have been processed or the action throws an exception.|
|V get(Object key)|This method returns the object that contains the value associated with the key.|
|V getOrDefault(Object key, V defaultValue)|It returns the value to which the specified key is mapped, or defaultValue if the map contains no mapping for the key.|
|boolean isEmpty()|This method returns true if the map is empty; returns false if it contains at least one key.|
|V merge(K key, V value, BiFunction<? super V,? super V,? extends V> remappingFunction)|If the specified key is not already associated with a value or is associated with null, associates it with the given non-null value.|
|V replace(K key, V value)|It replaces the specified value for a specified key.|
|boolean replace(K key, V oldValue, V newValue)|It replaces the old value with the new value for a specified key.|
|void replaceAll(BiFunction<? super K,? super V,? extends V> function)|It replaces each entry's value with the result of invoking the given function on that entry until all entries have been processed or the function throws an exception.|
|Collection<V> values()|It returns a collection view of the values contained in the map.|
|int size()|This method returns the number of entries in the map.|

### Java HashMap Example

Let's see a simple example of HashMap to store key and value pair.

### Example

[](https://www.tpointtech.com/java-hashmap#)[](https://www.tpointtech.com/java-hashmap#)[](https://www.tpointtech.com/java-hashmap#)

1. import java.util.*;  
2. public class Main{  
3.  public static void main(String args[]){  
4.    HashMap<Integer,String> map=new HashMap<Integer,String>();//Creating HashMap    
5.    map.put(1,"Mango");  //Put elements in Map  
6.    map.put(2,"Apple");    
7.    map.put(3,"Banana");   
8.    map.put(4,"Grapes");   

9.    System.out.println("Iterating Hashmap...");  
10.    for(Map.Entry m : map.entrySet()){    
11.     System.out.println(m.getKey()+" "+m.getValue());    
12.    }  
13. }  
14. }  

**Output:**

Iterating Hashmap...
1 Mango
2 Apple
3 Banana
4 Grapes

**Explanation**

The provided Java code initializes a HashMap named map, which is parameterized to accept Integer keys and String values. Four key-value pairs are then added to the HashMap using the put method, associating integers 1 to 4 with corresponding fruit names ('Mango', 'Apple', 'Banana', and 'Grapes'). Subsequently, a loop iterates over the entries of the HashMap using the entrySet() method, printing each key-value pair to the console.

## No Duplicate Key on HashMap

We cannot store duplicate keys in HashMap. However, if we try to store a duplicate key with another value, it will replace the value.

Because of this behavior, HashMaps are guaranteed to retain a one-to-one mapping between keys and values, where each key and value is uniquely identified. It's also important to remember that HashMaps permit null values, but only one null key may exist. Within the HashMap data structure, fast key-value pair retrieval and manipulation are made possible by this unique restriction on keys.

### Example

[](https://www.tpointtech.com/java-hashmap#)[](https://www.tpointtech.com/java-hashmap#)[](https://www.tpointtech.com/java-hashmap#)

1. import java.util.*;  
2. public class Main{  
3.  public static void main(String args[]){  
4.    HashMap<Integer,String> map=new HashMap<Integer,String>();//Creating HashMap    
5.    map.put(1,"Mango");  //Put elements in Map  
6.    map.put(2,"Apple");    
7.    map.put(3,"Banana");   
8.    map.put(1,"Grapes"); //trying duplicate key  

9.    System.out.println("Iterating Hashmap...");  
10.    for(Map.Entry m : map.entrySet()){    
11.     System.out.println(m.getKey()+" "+m.getValue());    
12.    }  
13. }  
14. }  

**Output:**

Iterating Hashmap...
1 Grapes
2 Apple
3 Banana

**Explanation**

The Java code that is provided initializes a hash map with the name map, mapping String values to Integer keys. Using the put method, four key-value pairs-each representing a fruit and its matching identifier-are added to the HashMap. Interestingly, the code replaces the value ("Mango") associated with key 1 by attempting to introduce a duplicate key (1) with a different value ("Grapes").

## Java HashMap Example to Add Elements

There are the following ways to add elements in HashMap:

**1. Using put() Method:**

A key-value pair is inserted into the HashMap using the put() method. The new value is overwritten in the related value if the specified key already exists.

**2. Using putIfAbsent() Method:**

The putIfAbsent() method only adds a key-value pair to the HashMap in the event that the given key isn't already there.

**3. Using putAll() Method:**

Copy every key-value pair from one HashMap to another using the putAll() method. All of the components from the designated map are added to the active map.

These techniques give programmers in Java the ability to add entries to HashMaps with flexibility, facilitating the effective manipulation and arrangement of key-value data structures.

Let's implement all the above methods in a Java program.

### Example

[](https://www.tpointtech.com/java-hashmap#)[](https://www.tpointtech.com/java-hashmap#)[](https://www.tpointtech.com/java-hashmap#)

1. import java.util.*;  
2. class Main{  
3.  public static void main(String args[]){  
4.    HashMap<Integer,String> hm=new HashMap<Integer,String>();    
5.     System.out.println("Initial list of elements: "+hm);  
6.       hm.put(100,"Amit");    
7.       hm.put(101,"Vijay");    
8.       hm.put(102,"Rahul");   

9.       System.out.println("After invoking put() method ");  
10.       for(Map.Entry m:hm.entrySet()){    
11.        System.out.println(m.getKey()+" "+m.getValue());    
12.       }  

13.       hm.putIfAbsent(103, "Gaurav");  
14.       System.out.println("After invoking putIfAbsent() method ");  
15.       for(Map.Entry m:hm.entrySet()){    
16.            System.out.println(m.getKey()+" "+m.getValue());    
17.           }  
18.       HashMap<Integer,String> map=new HashMap<Integer,String>();  
19.       map.put(104,"Ravi");  
20.       map.putAll(hm);  
21.       System.out.println("After invoking putAll() method ");  
22.       for(Map.Entry m:map.entrySet()){    
23.            System.out.println(m.getKey()+" "+m.getValue());    
24.           }  
25.  }  
26. }  

**Output:**

Initial list of elements: {}
After invoking put() method
100 Amit
101 Vijay
102 Rahul
After invoking putIfAbsent() method
100 Amit
101 Vijay
102 Rahul
103 Gaurav
After invoking putAll() method
100 Amit
101 Vijay
102 Rahul
103 Gaurav
104 Ravi

**Explanation**

The Java code that is provided creates a hash map called hm with key-value pairs of String and Integer, respectively. This HashMap is expanded with new elements by utilising the put() method. Then, if the given key is not already linked to a value, the putIfAbsent() function is used to add a key-value pair. Next, all of the components from hm are added to map using the putAll() method, which creates a new HashMap with the name map.

## Java HashMap Example to Remove Elements

**1. remove(Object key):**

If the mapping for the given key exists in the HashMap, it is removed. gives back the value that corresponds to the key, or null if the key is absent.

**2. remove(Object key, Object value):**

If the supplied key is currently mapped to the specified value, only then is the entry for that key removed. Returns false otherwise and true if the removal was successful.

**3. clear():**

Empties the HashMap by removing all key-value pairs.

### Example

[](https://www.tpointtech.com/java-hashmap#)[](https://www.tpointtech.com/java-hashmap#)[](https://www.tpointtech.com/java-hashmap#)

1. import java.util.*;  
2. public class Main {  
3.    public static void main(String args[]) {  
4.     HashMap<Integer,String> map=new HashMap<Integer,String>();          
5.       map.put(100,"Amit");    
6.       map.put(101,"Vijay");    
7.       map.put(102,"Rahul");  
8.       map.put(103, "Gaurav");  
9.     System.out.println("Initial list of elements: "+map);  
10.     //key-based removal  
11.     map.remove(100);  
12.     System.out.println("Updated list of elements: "+map);  
13.     //value-based removal  
14.     map.remove(101);  
15.     System.out.println("Updated list of elements: "+map);  
16.     //key-value pair based removal  
17.     map.remove(102, "Rahul");  
18.     System.out.println("Updated list of elements: "+map);  
19.    }      
20. }  

**Output:**

Initial list of elements: {100=Amit, 101=Vijay, 102=Rahul, 103=Gaurav}
Updated list of elements: {101=Vijay, 102=Rahul, 103=Gaurav}
Updated list of elements: {102=Rahul, 103=Gaurav}
Updated list of elements: {103=Gaurav}

**Explanation**

The Java code that is provided initialises a hash map called "map" with integer keys and string values. It then uses the put() function to fill the map with many key-value pairs. The remove() function is then used to demonstrate various removal scenarios: initially, an item is removed based on a specific key (map.remove(100)), then a value-based entry is removed (map.remove(101)), and lastly, an entry is removed based on both a key and a value (map.remove(102, "Rahul")). The updated list of entries in the hash map is produced to reflect the modifications made following each removal operation.

## Java HashMap Example to Replace Elements

1. **replace(K key, V value):** If the given key is mapped to a value at present, only then does this method replace the entry for that key. If there was no mapping for the key, it returns null. Otherwise, it returns the previous value connected to the given key.
2. **replace(K key, V oldValue, V newValue):** This function replaces the key entry only if it is mapped to the supplied oldValue at the moment. If the replacement happened, it returns true; if not, it returns false.

### Example

[](https://www.tpointtech.com/java-hashmap#)[](https://www.tpointtech.com/java-hashmap#)[](https://www.tpointtech.com/java-hashmap#)

1. import java.util.*;  
2. class Main{  
3.  public static void main(String args[]){  
4.    HashMap<Integer,String> hm=new HashMap<Integer,String>();    
5.       hm.put(100,"Amit");    
6.       hm.put(101,"Vijay");    
7.       hm.put(102,"Rahul");   
8.       System.out.println("Initial list of elements:");  
9.      for(Map.Entry m:hm.entrySet())  
10.      {  
11.         System.out.println(m.getKey()+" "+m.getValue());   
12.      }  
13.      System.out.println("Updated list of elements:");  
14.      hm.replace(102, "Gaurav");  
15.      for(Map.Entry m:hm.entrySet())  
16.      {  
17.         System.out.println(m.getKey()+" "+m.getValue());   
18.      }  
19.      System.out.println("Updated list of elements:");  
20.      hm.replace(101, "Vijay", "Ravi");  
21.      for(Map.Entry m:hm.entrySet())  
22.      {  
23.         System.out.println(m.getKey()+" "+m.getValue());   
24.      }   
25.      System.out.println("Updated list of elements:");  
26.      hm.replaceAll((k,v) -> "Ajay");  
27.      for(Map.Entry m:hm.entrySet())  
28.      {  
29.         System.out.println(m.getKey()+" "+m.getValue());   
30.      }  
31.  }  
32. }  

**Output:**

Initial list of elements:
100 Amit
101 Vijay
102 Rahul
Updated list of elements:
100 Amit
101 Vijay
102 Gaurav
Updated list of elements:
100 Amit
101 Ravi
102 Gaurav
Updated list of elements:
100 Ajay
101 Ajay
102 Ajay

**Explanation**

The Java code that is provided initialises a hash map called "hm" with multiple key-value pairs and, integer keys and String values. After that, various techniques for swapping out elements in the hash map are shown. First, it substitutes "Gaurav" for the value linked to key 102 using the replace(K key, V value) method. The value associated with key 101 is then changed from "Vijay" to "Ravi" using the replace(K key, V oldValue, V newValue) method. Lastly, it replaces every value in the HashMap with "Ajay" by using the replaceAll(BiFunction<K, V, V> function) method. Following every replacement operation, the HashMap's updated element list is printed.

## Difference Between HashSet and HashMap

HashSet contains only values, whereas HashMap contains an entry(key and value).

|Feature|HashSet|HashMap|
|---|---|---|
|**Contains**|Only values|Key-value pairs (entries)|
|**Data Structure**|Implements Set interface|Implements Map interface|
|**Usage**|Used for storing unique elements|Used for storing key-value pairs|
|**Null Elements**|Allows one null element|Allows one null key and multiple null values|
|**Ordering**|Unordered|Unordered|
|**Retrieval**|Direct access by value|Access by key|
|**Implementation**|Implemented using HashMap internally|Implemented using HashTable internally|
|**Performance**|Typically offers better performance|It might have a slightly lower performance|
|**Memory Overhead**|Lower due to storing only values|>Higher due to storing both keys and values|
|**Iteration**|Iterating over elements is straightforward|Iterating over entries is less intuitive|
|**Use Cases**|Checking for presence, maintaining uniqueness|Associating values with keys, efficient value retrieval|
|**Concurrency**|Not synchronised, not suitable for concurrent access without external synchronisation|Can be synchronised or use ConcurrentHashMap for concurrent access|
|**API Differences**|Methods for adding, removing, and checking containment|Methods for getting/setting values based on keys, additional operations for managing key-value pairs|

Let's see Java HashMap program.

### Example

[](https://www.tpointtech.com/java-hashmap#)[](https://www.tpointtech.com/java-hashmap#)[](https://www.tpointtech.com/java-hashmap#)

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
16.     //Creating map of Books    
17.     Map<Integer,Book> map=new HashMap<Integer,Book>();    
18.     //Creating Books    
19.     Book b1=new Book(101,"Let us C","Yashwant Kanetkar","BPB",8);    
20.     Book b2=new Book(102,"Data Communications & Networking","Forouzan","Mc Graw Hill",4);    
21.     Book b3=new Book(103,"Operating System","Galvin","Wiley",6);    
22.     //Adding Books to map   
23.     map.put(1,b1);  
24.     map.put(2,b2);  
25.     map.put(3,b3);  

26.     //Traversing map  
27.     for(Map.Entry<Integer, Book> entry:map.entrySet()){    
28.         int key=entry.getKey();  
29.         Book b=entry.getValue();  
30.         System.out.println(key+" Details:");  
31.         System.out.println(b.id+" "+b.name+" "+b.author+" "+b.publisher+" "+b.quantity);   
32.     }    
33. }    
34. }    

**Output:**

1 Details:
101 Let us C Yashwant Kanetkar BPB 8
2 Details:
102 Data Communications and Networking Forouzan Mc Graw Hill 4
3 Details:
103 Operating System Galvin Wiley 6

**Explanation**

The Java code that is provided shows how to store and retrieve instances of the class Book using a hash map. It begins with defining the Book class, which has a constructor to initialise the attributes id, name, author, publisher, and quantity. A hash map with integer keys and book values is built in the MapExample class. Using distinct integer keys, multiple Book objects are constructed and appended to the hash map. Next, a for-each loop over the entry set is used by the code to iterate through the HashMap. Each entry's key and matching Book object are retrieved, and the details of each Book-including its id, name, author, publisher, and quantity-are printed out.