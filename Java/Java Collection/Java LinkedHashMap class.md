

![Java LinkedHashMap class hierarchy](https://images.tpointtech.com/images/linkedhashmap.png)

Java LinkedHashMap class is Hashtable and Linked list implementation of the Map interface, with predictable iteration order. It inherits HashMap class and implements the Map interface.

### Points to remember

- Java LinkedHashMap contains values based on the key.
- Java LinkedHashMap contains unique elements.
- Java LinkedHashMap may have one null key and multiple null values.
- Java LinkedHashMap is non synchronized.
- Java LinkedHashMap maintains insertion order.
- The initial default capacity of Java HashMap class is 16 with a load factor of 0.75.

### LinkedHashMap class declaration

Let's see the declaration for java.util.LinkedHashMap class.

[](https://www.tpointtech.com/java-linkedhashmap#)[](https://www.tpointtech.com/java-linkedhashmap#)[](https://www.tpointtech.com/java-linkedhashmap#)

1. public class LinkedHashMap<K,V> extends HashMap<K,V> implements Map<K,V>  

### LinkedHashMap class Parameters

Let's see the Parameters for java.util.LinkedHashMap class.

- **K**: It is the type of keys maintained by this map.
- **V**: It is the type of mapped values.

### Constructors of Java LinkedHashMap class

|Constructor|Description|
|---|---|
|LinkedHashMap()|It is used to construct a default LinkedHashMap.|
|LinkedHashMap(int capacity)|It is used to initialize a LinkedHashMap with the given capacity.|
|LinkedHashMap(int capacity, float loadFactor)|It is used to initialize both the capacity and the load factor.|
|LinkedHashMap(int capacity, float loadFactor, boolean accessOrder)|It is used to initialize both the capacity and the load factor with specified ordering mode.|
|LinkedHashMap(Map<? extends K,? extends V> m)|It is used to initialize the LinkedHashMap with the elements from the given Map class m.|

### Methods of Java LinkedHashMap class

|Method|Description|
|---|---|
|V get(Object key)|It returns the value to which the specified key is mapped.|
|void clear()|It removes all the key-value pairs from a map.|
|boolean containsValue(Object value)|It returns true if the map maps one or more keys to the specified value.|
|Set<Map.Entry<K,V>> entrySet()|It returns a Set view of the mappings contained in the map.|
|void forEach(BiConsumer<? super K,? super V> action)|It performs the given action for each entry in the map until all entries have been processed or the action throws an exception.|
|V getOrDefault(Object key, V defaultValue)|It returns the value to which the specified key is mapped or defaultValue if this map contains no mapping for the key.|
|Set<K> keySet()|It returns a Set view of the keys contained in the map|
|protected boolean removeEldestEntry(Map.Entry<K,V> eldest)|It returns true on removing its eldest entry.|
|void replaceAll(BiFunction<? super K,? super V,? extends V> function)|It replaces each entry's value with the result of invoking the given function on that entry until all entries have been processed or the function throws an exception.|
|Collection<V> values()|It returns a Collection view of the values contained in this map.|

  

### Java LinkedHashMap Example

### Example

[](https://www.tpointtech.com/java-linkedhashmap#)[](https://www.tpointtech.com/java-linkedhashmap#)[](https://www.tpointtech.com/java-linkedhashmap#)

1. import java.util.*;  
2. class Main{  
3.  public static void main(String args[]){  

4.   LinkedHashMap<Integer,String> hm=new LinkedHashMap<Integer,String>();  

5.   hm.put(100,"Amit");  
6.   hm.put(101,"Vijay");  
7.   hm.put(102,"Rahul");  

8. for(Map.Entry m:hm.entrySet()){  
9.    System.out.println(m.getKey()+" "+m.getValue());  
10.   }  
11.  }  
12. }  

**Output:**

100 Amit
101 Vijay
102 Rahul

### Java LinkedHashMap Example: Key-Value pair

### Example

[](https://www.tpointtech.com/java-linkedhashmap#)[](https://www.tpointtech.com/java-linkedhashmap#)[](https://www.tpointtech.com/java-linkedhashmap#)

1. import java.util.*;  
2. class Main{  
3.  public static void main(String args[]){  
4.    LinkedHashMap<Integer, String> map = new LinkedHashMap<Integer, String>();           
5.       map.put(100,"Amit");    
6.      map.put(101,"Vijay");    
7.      map.put(102,"Rahul");    
8.        //Fetching key  
9.        System.out.println("Keys: "+map.keySet());  
10.        //Fetching value  
11.        System.out.println("Values: "+map.values());  
12.        //Fetching key-value pair  
13.        System.out.println("Key-Value pairs: "+map.entrySet());  
14.  }  
15. }  

**Output:**

Keys: [100, 101, 102]
Values: [Amit, Vijay, Rahul]
Key-Value pairs: [100=Amit, 101=Vijay, 102=Rahul]

### Java LinkedHashMap Example:remove()

### Example

[](https://www.tpointtech.com/java-linkedhashmap#)[](https://www.tpointtech.com/java-linkedhashmap#)[](https://www.tpointtech.com/java-linkedhashmap#)

1. import java.util.*;  
2. public class Main {  
3.    public static void main(String args[]) {  
4.     Map<Integer,String> map=new LinkedHashMap<Integer,String>();        
5.      map.put(101,"Amit");    
6.      map.put(102,"Vijay");    
7.      map.put(103,"Rahul");    
8.      System.out.println("Before invoking remove() method: "+map);     
9.     map.remove(102);  
10.     System.out.println("After invoking remove() method: "+map);    
11.    }      
12. }  

**Output:**

Before invoking remove() method: {101=Amit, 102=Vijay, 103=Rahul}
After invoking remove() method: {101=Amit, 103=Rahul}

### Java LinkedHashMap Example: Book

### Example

[](https://www.tpointtech.com/java-linkedhashmap#)[](https://www.tpointtech.com/java-linkedhashmap#)[](https://www.tpointtech.com/java-linkedhashmap#)

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
17.     Map<Integer,Book> map=new LinkedHashMap<Integer,Book>();    
18.     //Creating Books    
19.     Book b1=new Book(101,"Let us C","Yashwant Kanetkar","BPB",8);    
20.     Book b2=new Book(102,"Data Communications & Networking","Forouzan","Mc Graw Hill",4);    
21.     Book b3=new Book(103,"Operating System","Galvin","Wiley",6);    
22.     //Adding Books to map   
23.     map.put(2,b2);  
24.     map.put(1,b1);  
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

2 Details:
102 Data Communications & Networking Forouzan Mc Graw Hill 4
1 Details:
101 Let us C Yashwant Kanetkar BPB 8
3 Details:
103 Operating System Galvin Wiley 6