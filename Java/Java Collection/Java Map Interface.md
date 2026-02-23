The map interface in Java is a structure that holds a set of key-value pairs where each key is unique and points to one value only. It is a component of the java.util package and is being widely used in Java programming to structure and get data in an ordered manner. A Map is useful if you have to search, update or delete elements on the basis of a key.

## Why Java Map Interface?

Below are some circumstances and reasons where you may find it beneficial to utilize the `Map` interface:

**Efficient Data Retrieval:** Keys are used in maps in order to read values selectively. If you have to connect one set of data with another in a manner that enables you to find the relevant information by typing the key, then the map answers your need very well. For instance, in the case where you have a huge dataset and you want to quickly search for anything that corresponds to specific keys, such as IDs, names, or codes, a map can offer speedy access to such data.

**No Duplicate Keys:** Keys of maps are unique such that a particular key has to be unique. This feature is handy when the goal is to make certain that each key should represent only one value. Also, in a dictionary application, you would have to see that each word has only one definition.

**Flexibility in Key and Value Types:** Java Maps feature the ability to store keys and values of multiple types. You can use any object as a key, which must implement hashCode() and equals() methods, and any object as a value. It provides you with the chance to visualize different relationships between objects.

**Associative Data Structures:** Maps are frequently used for associative arrays, dictionaries, and symbol tables. It offers convenient space for storing and retrieving information, with each item having its own particular index.

**Caching and Memoization:** Maps are very useful for caching and memoization purposes. You can save the results of a costly operation or a consequence of a certain operation in a map, binding them with the inputs or the parameters of the operation. This enables you to go straight to the stored map item if the same input occurs again, rather than having to compute it again from scratch.

![Java Map Hierarchy](https://d2jdgazzki9vjm.cloudfront.net/images/core/java-map-hierarchy.png)

A Map doesn't allow duplicate keys, but you can have duplicate values. HashMap and LinkedHashMap allow null keys and values, but TreeMap doesn't allow any null key or value.

A Map can't be traversed, so you need to convert it into Set using _keySet()_ or _entrySet()_ method.

|Class|Description|
|---|---|
|[HashMap](https://www.tpointtech.com/java-hashmap)|HashMap is the implementation of Map, but it doesn't maintain any order.|
|[LinkedHashMap](https://www.tpointtech.com/java-linkedhashmap)|LinkedHashMap is the implementation of Map. It inherits HashMap class. It maintains insertion order.|
|[TreeMap](https://www.tpointtech.com/java-treemap)|TreeMap is the implementation of Map and SortedMap. It maintains ascending order.|

### Useful methods of Map interface

|Method|Description|
|---|---|
|V put(Object key, Object value)|It is used to insert an entry in the map.|
|void putAll(Map map)|It is used to insert the specified map in the map.|
|V putIfAbsent(K key, V value)|It inserts the specified value with the specified key in the map only if it is not already specified.|
|V remove(Object key)|It is used to delete an entry for the specified key.|
|boolean remove(Object key, Object value)|It removes the specified values with the associated specified keys from the map.|
|Set keySet()|It returns the Set view containing all the keys.|
|Set<Map.Entry<K,V>> entrySet()|It returns the Set view containing all the keys and values.|
|void clear()|It is used to reset the map.|
|V compute(K key, BiFunction<? super K,? super V,? extends V> remappingFunction)|It is used to compute a mapping for the specified key and its current mapped value (or null if there is no current mapping).|
|V computeIfAbsent(K key, Function<? super K,? extends V> mappingFunction)|It is used to compute its value using the given mapping function, if the specified key is not already associated with a value (or is mapped to null), and enters it into this map unless null.|
|V computeIfPresent(K key, BiFunction<? super K,? super V,? extends V> remappingFunction)|It is used to compute a new mapping given the key and its current mapped value if the value for the specified key is present and non-null.|
|boolean containsValue(Object value)|This method returns true if some value equal to the value exists within the map, else return false.|
|boolean containsKey(Object key)|This method returns true if some key equal to the key exists within the map, else return false.|
|boolean equals(Object o)|It is used to compare the specified Object with the Map.|
|void forEach(BiConsumer<? super K,? super V> action)|It performs the given action for each entry in the map until all entries have been processed or the action throws an exception.|
|V get(Object key)|This method returns the object that contains the value associated with the key.|
|V getOrDefault(Object key, V defaultValue)|It returns the value to which the specified key is mapped, or defaultValue if the map contains no mapping for the key.|
|int hashCode()|It returns the hash code value for the Map|
|boolean isEmpty()|This method returns true if the map is empty; returns false if it contains at least one key.|
|V merge(K key, V value, BiFunction<? super V,? super V,? extends V> remappingFunction)|If the specified key is not already associated with a value or is associated with null, associates it with the given non-null value.|
|V replace(K key, V value)|It replaces the specified value for a specified key.|
|boolean replace(K key, V oldValue, V newValue)|It replaces the old value with the new value for a specified key.|
|void replaceAll(BiFunction<? super K,? super V,? extends V> function)|It replaces each entry's value with the result of invoking the given function on that entry until all entries have been processed or the function throws an exception.|
|Collectionvalues()|It returns a collection view of the values contained in the map.|
|int size()|This method returns the number of entries in the map.|

## Map.Entry Interface

Map.Entry is an inner interface of the Map interface which represents a single pair of key-value in a map. It additionally allows one to get a map and to iterate over its entries, convert the map to a set of keys/values, etc. It returns a collection-view of the map, whose elements are of this class. It provides methods to get keys and values.

### Methods of Map.Entry interface

|Method|Description|
|---|---|
|K getKey()|It is used to obtain a key.|
|V getValue()|It is used to obtain value.|
|int hashCode()|It is used to obtain hashCode.|
|V setValue(V value)|It is used to replace the value corresponding to this entry with the specified value.|
|boolean equals(Object o)|It is used to compare the specified object with the other existing objects.|
|static <K extends Comparable<? super K>,V> Comparator<Map.Entry<K,V>> comparingByKey()|It returns a comparator that compare the objects in natural order on key.|
|static <K,V> Comparator<Map.Entry<K,V>> comparingByKey(Comparator<? super K> cmp)|It returns a comparator that compare the objects by key using the given Comparator.|
|static <K,V extends Comparable<? super V>> Comparator<Map.Entry<K,V>> comparingByValue()|It returns a comparator that compare the objects in natural order on value.|
|static <K,V> Comparator<Map.Entry<K,V>> comparingByValue(Comparator<? super V> cmp)|It returns a comparator that compare the objects by value using the given Comparator.|

### Java Map Example: Non-Generic (Old Style)

### Example

[](https://www.tpointtech.com/java-map#)[](https://www.tpointtech.com/java-map#)[](https://www.tpointtech.com/java-map#)

1. //Non-generic  
2. import java.util.*;  
3. public class Main {  
4. public static void main(String[] args) {  
5.     Map map=new HashMap();  
6.     //Adding elements to map  
7.     map.put(1,"Amit");  
8.     map.put(5,"Rahul");  
9.     map.put(2,"Jai");  
10.     map.put(6,"Amit");  
11.     //Traversing Map  
12.     Set set=map.entrySet();//Converting to Set so that we can traverse  
13.     Iterator itr=set.iterator();  
14.     while(itr.hasNext()){  
15.         //Converting to Map.Entry so that we can get key and value separately  
16.         Map.Entry entry=(Map.Entry)itr.next();  
17.         System.out.println(entry.getKey()+" "+entry.getValue());  
18.     }  
19. }  
20. }  

**Output:**

1 Amit
2 Jai
5 Rahul
6 Amit

 

### Example

[](https://www.tpointtech.com/java-map#)[](https://www.tpointtech.com/java-map#)[](https://www.tpointtech.com/java-map#)

1. import java.util.*;  
2. class Main{  
3.    public static void main(String args[]){  
4.       // Creating a HashMap instance  
5.       Map<Integer,String> map=new HashMap<Integer,String>();     
6.       // Adding key-value pairs to the map  
7.       map.put(100,"Amit");  
8.       map.put(101,"Vijay");  
9.       map.put(102,"Rahul");    
10.       // Elements can traverse in any order  
11.       // Iterating over the entries of the map  
12.       for(Map.Entry m:map.entrySet()){  
13.          // Printing the key-value pairs  
14.          System.out.println(m.getKey()+" "+m.getValue());  
15.       }  
16.    }  
17. }  

**Output:**

100 Amit
101 Vijay
102 Rahul

### Java Map Example: comparingByKey()

### Example

[](https://www.tpointtech.com/java-map#)[](https://www.tpointtech.com/java-map#)[](https://www.tpointtech.com/java-map#)

1. import java.util.*;  
2. class Main {  
3.     public static void main(String args[]) {  
4.         // Creating a HashMap instance to store key-value pairs  
5.         Map<Integer, String> map = new HashMap<Integer, String>();  
6.         // Adding key-value pairs to the map  
7.         map.put(100, "Amit");  
8.         map.put(101, "Vijay");  
9.         map.put(102, "Rahul");  
10.         // Returns a Set view of the mappings contained in this map  
11.         map.entrySet() // Returns a Set view of the mappings contained in this map  
12.             .stream() // Returns a sequential Stream with this collection as its source  
13.             .sorted(Map.Entry.comparingByKey()) // Sorted according to the provided Comparator  
14.             .forEach(System.out::println); // Performs an action for each element of this stream  
15.     }  
16. }  

**Output:**

100=Amit
101=Vijay
102=Rahul

### Java Map Example: comparingByKey() in Descending Order

### Example

[](https://www.tpointtech.com/java-map#)[](https://www.tpointtech.com/java-map#)[](https://www.tpointtech.com/java-map#)

1. import java.util.*;  
2. class main {  
3.     public static void main(String args[]) {  
4.         // Creating a HashMap instance to store key-value pairs  
5.         Map<Integer, String> map = new HashMap<Integer, String>();  
6.         // Adding key-value pairs to the map  
7.         map.put(100, "Amit");  
8.         map.put(101, "Vijay");  
9.         map.put(102, "Rahul");  
10.         // Returns a Set view of the mappings contained in this map  
11.         map.entrySet() // Returns a Set view of the mappings contained in this map  
12.             .stream() // Returns a sequential Stream with this collection as its source  
13.             .sorted(Map.Entry.comparingByKey(Comparator.reverseOrder())) // Sorted according to the provided Comparator  
14.             .forEach(System.out::println); // Performs an action for each element of this stream  
15.     }  
16. }  

**Output:**

102=Rahul
101=Vijay
100=Amit

The Map interface is implemented by several classes. Some of the commonly used classes that implement the Map interface include:

## HashMap

HashMap is an important data structure in Java which implements the Map interface. In this way, it provides a scheme for storing of key-value pairs. A HashMap has each key unique and only has one value for each key. This enables the lookup of values by their keys that are paired with them.

One of the most important features of HashMap is its underlying implementation as a hash table that allows constant-time performance for basic operations such as insertion, deletion, and retrieval on average, providing a good hash function and proper capacity management.

### Example:

### Example

[](https://www.tpointtech.com/java-map#)[](https://www.tpointtech.com/java-map#)[](https://www.tpointtech.com/java-map#)

1. import java.util.HashMap;  
2. import java.util.Map;  
3. public class Main {  
4.     public static void main(String[] args) {  
5.         // Creating a HashMap to store student IDs and their corresponding names  
6.         Map<Integer, String> studentMap = new HashMap<>();  
7.         // Adding some student records to the HashMap  
8.         studentMap.put(1001, "John Smith");  
9.         studentMap.put(1002, "Emily Brown");  
10.         studentMap.put(1003, "Michael Johnson");  
11.         // Retrieving and printing a student's name based on their ID  
12.         int studentIdToFind = 1002;  
13.         String studentName = studentMap.get(studentIdToFind);  
14.         if (studentName != null) {  
15.             System.out.println("Student with ID " + studentIdToFind + " is: " + studentName);  
16.         } else {  
17.             System.out.println("Student with ID " + studentIdToFind + " not found.");  
18.         }  
19.         // Iterating over the entries of the HashMap and printing each key-value pair  
20.         System.out.println("Student Records:");  
21.         for (Map.Entry<Integer, String> entry : studentMap.entrySet()) {  
22.             System.out.println("ID: " + entry.getKey() + ", Name: " + entry.getValue());  
23.         }  
24.         // Checking if a student ID exists in the HashMap  
25.         int idToCheck = 1004;  
26.         boolean exists = studentMap.containsKey(idToCheck);  
27.         System.out.println("Student with ID " + idToCheck + " exists in records: " + exists);  
28.     }  
29. }  

**Output:**

Student with ID 1002 is: Emily BrownStudent Records:
ID: 1001, Name: John Smith
ID: 1002, Name: Emily Brown
ID: 1003, Name: Michael Johnson
Student with ID 1004 exists in records: false

## LinkedHashMap

LinkedHashMap is a class in Java that extends HashMap and implements the Map interface. It resembles Hashmap in functionality but maintains a predictable iteration order, that is, the order in which keys were inserted into the map (insertion-order). This in turn makes LinkedHashMap a good candidate for cases when the order of insertion needs to be preserved.

LinkedHashMap has one of the special features of its keeping a doubly linked list of its entries, which enables you to go through the entries in either insertion or access order (the order in which entries were last accessed).

### Example:

### Example

[](https://www.tpointtech.com/java-map#)[](https://www.tpointtech.com/java-map#)[](https://www.tpointtech.com/java-map#)

1. import java.util.LinkedHashMap;  
2. import java.util.Map;  
3. public class Main {  
4.     public static void main(String[] args) {  
5.         // Creating a LinkedHashMap to store student IDs and their corresponding names  
6.         Map<Integer, String> studentMap = new LinkedHashMap<>();  
7.         // Adding some student records to the LinkedHashMap  
8.         studentMap.put(1001, "John Smith");  
9.         studentMap.put(1002, "Emily Brown");  
10.         studentMap.put(1003, "Michael Johnson");  
11.         // Iterating over the entries of the LinkedHashMap and printing each key-value pair  
12.         System.out.println("Student Records:");  
13.         for (Map.Entry<Integer, String> entry : studentMap.entrySet()) {  
14.             System.out.println("ID: " + entry.getKey() + ", Name: " + entry.getValue());  
15.         }  
16.     }  
17. }  

**Output:**

Student Records:
ID: 1001, Name: John Smith
ID: 1002, Name: Emily Brown
ID: 1003, Name: Michael Johnson

## TreeHashMap

TreeMap in Java is a sorted map implementation that stores key-value pairing in a Red-Black tree structure. It guarantees that the elements are arranged in relation to their keys, either naturally or by a user-defined comparator. This data structure offers operations of O(log n) time-efficiency for insertion, deletion, and retrieval. TreeMap implements the NavigableMap interface, providing navigation and range-based operation methods. Several usage examples include keeping the dictionaries in sorted order, implementing range search, and running the data in a sorted manner.

### Example:

### Example

[](https://www.tpointtech.com/java-map#)[](https://www.tpointtech.com/java-map#)[](https://www.tpointtech.com/java-map#)

1. import java.util.*;  
2. public class Main {  
3.     public static void main(String[] args) {  
4.         // Creating a TreeMap to store student IDs and their corresponding names  
5.         TreeMap<Integer, String> studentMap = new TreeMap<>();  
6.         // Adding some student records to the TreeMap  
7.         studentMap.put(1003, "Michael Johnson");  
8.         studentMap.put(1001, "John Smith");  
9.         studentMap.put(1002, "Emily Brown");  
10.         // Iterating over the entries of the TreeMap and printing each key-value pair  
11.         System.out.println("Student Records:");  
12.         for (Map.Entry<Integer, String> entry : studentMap.entrySet()) {  
13.             System.out.println("ID: " + entry.getKey() + ", Name: " + entry.getValue());  
14.         }  
15.     }  
16. }  

**Output:**

Student Records:
ID: 1001, Name: John Smith
ID: 1002, Name: Emily Brown
ID: 1003, Name: Michael Johnson