## What is Hashing

It is the process of converting an object into an integer value. The integer value helps in indexing and faster searches.

In other words, hashing is a technique used to uniquely identify a specific object from a group of similar objects.

## What is HashMap

HashMap is a part of the Java collection framework. It uses a technique called Hashing. It implements the map interface. It stores the data in the pair of Key and Value. HashMap contains an array of the nodes, and the node is represented as a class. It uses an array and LinkedList data structure internally for storing Key and Value. There are four fields in HashMap.

![Working of HashMap in Java](https://d2jdgazzki9vjm.cloudfront.net/images/core/working-of-hashmap-in-java.png)

Before understanding the internal workings of HashMap, we must be aware of hashCode() and equals() methods.

- **equals():** It checks the equality of two objects. It compares the Key, whether they are equal or not. It is a method of the Object class. It can be overridden. If you override the equals() method, then it is mandatory to override the hashCode() method.
- **hashCode():** This is the method of the object class. It returns the memory reference of the object in integer form. The value received from the method is used as the bucket number. The bucket number is the address of the element inside the map. Hash code of null Key is 0.
- **Buckets:** Array of the node is called buckets. Each node has a data structure like a LinkedList. More than one node can share the same bucket. It may be different in capacity.

![Working of HashMap in Java](https://d2jdgazzki9vjm.cloudfront.net/images/core/working-of-hashmap-in-java2.png)

## Hash Function

When given an input (or key), a hash function outputs a fixed-length string or number, which is usually a hash code. To index a hash table, use this hash code (similar to the array in HashMap). A hash function's primary goal is to minimise collisions and evenly distribute inputs throughout the hash table.

### Insert Key, Value Pair in HashMap

We use the put() method to insert the Key and Value pair into the HashMap, which has a default size of 16 (0 to 15).

**Example**

In the following example, we want to insert three (Key, Value) pair in the HashMap.

[](https://www.tpointtech.com/working-of-hashmap-in-java#)[](https://www.tpointtech.com/working-of-hashmap-in-java#)[](https://www.tpointtech.com/working-of-hashmap-in-java#)

1. HashMap<String, Integer> map = new HashMap<>();  
2. map.put("Aman", 19);  
3. map.put("Sunny", 29);  
4. map.put("Ritesh", 39);  

Let's see at which index the key-value pair will be saved into the Hash Map. When we call the put() method, it calculates the hash code of the Key "Aman." Suppose, the hash code of "Aman" is 2657860. To store the Key in memory, we have to calculate the index.

### Calculating Index

Index minimizes the size of the array. The Formula for calculating the index is:

[](https://www.tpointtech.com/working-of-hashmap-in-java#)[](https://www.tpointtech.com/working-of-hashmap-in-java#)[](https://www.tpointtech.com/working-of-hashmap-in-java#)

1. Index = hashcode(Key) & (n-1)  

Where n is the size of the array. Hence, the index value for "Aman" is:

[](https://www.tpointtech.com/working-of-hashmap-in-java#)[](https://www.tpointtech.com/working-of-hashmap-in-java#)[](https://www.tpointtech.com/working-of-hashmap-in-java#)

1. Index = 2657860 & (16-1) = 4  

The value 4 is the computed index value where the Key and value will store in HashMap.

![Working of HashMap in Java](https://d2jdgazzki9vjm.cloudfront.net/images/core/working-of-hashmap-in-java3.png)

## Hash Collision

This is the case when the calculated index value is the same for two or more Keys. Let's calculate the hash code for another Key, "Sunny." Suppose, the hash code for "Sunny" is 63281940. To store the Key in the memory, we have to calculate the index by using the index formula.

[](https://www.tpointtech.com/working-of-hashmap-in-java#)[](https://www.tpointtech.com/working-of-hashmap-in-java#)[](https://www.tpointtech.com/working-of-hashmap-in-java#)

1. Index=63281940 & (16-1) = 4  

The value 4 is the computed index value where the Key will be stored in HashMap. In this case, equals() method check that both Keys are equal or not. If Keys are same, replace the value with the current value. Otherwise, connect this node object to the existing node object through the LinkedList. Hence both Keys will be stored at index 4.

![Working of HashMap in Java](https://d2jdgazzki9vjm.cloudfront.net/images/core/working-of-hashmap-in-java4.png)

Similarly, we will store the Key "Ritesh." Suppose, hash code for the Key is 2349873. The index value will be 1. Hence, this Key will be stored at index 1.

![Working of HashMap in Java](https://d2jdgazzki9vjm.cloudfront.net/images/core/working-of-hashmap-in-java5.png)

## Handling Collisions

Despite efforts to minimize them, collisions are inevitable. Two main strategies to handle collisions are:

- **Chaining:** Storing all elements that hash to the same index in a linked list or tree at that
- **Open Addressing:** Finding another open slot within the hash table by probing (for example, linear probing, quadratic probing) when a collision occurs.

## HashMap.get() Method

The get() method is used to get the value by its Key. It will not fetch the value if we do not know the Key. When the get(K Key) method is called, it calculates the hash code of the Key.

Suppose, we have to fetch the Key "Aman." The following method will be called.

[](https://www.tpointtech.com/working-of-hashmap-in-java#)[](https://www.tpointtech.com/working-of-hashmap-in-java#)[](https://www.tpointtech.com/working-of-hashmap-in-java#)

1. map.get(new Key("Aman"));  

It generates the hash code as 2657860. Now calculate the index value of 2657860 by using index formula. The index value will be 4, as we have calculated above. The get() method search for the index value 4. It compares the first element Key with the given Key. If both keys are equal, then it returns the value else check for the next element in the node if it exists. In our scenario, it is found as the first element of the node and return the value 19.

Let's fetch another Key "Sunny."

The hash code of the Key "Sunny" is 63281940. The calculated index value of 63281940 is 4, as we have calculated for put() method. Go to index 4 of the array and compare the first element's Key with the given Key. It also compares Keys. In our scenario, the given Key is the second element, and the next of the node is null. It compares the second element Key with the specified Key and returns the value 29. It returns null if the next of the node is null.

### HashMap Traversal

Java provides various methods such as entrySet(), keySet(), and values() to traverse over hash map. These methods allow us to iterate over the keys, values, or key-value pairs of the HashMap. Consider the following code snippet.

[](https://www.tpointtech.com/working-of-hashmap-in-java#)[](https://www.tpointtech.com/working-of-hashmap-in-java#)[](https://www.tpointtech.com/working-of-hashmap-in-java#)

1. for (Map.Entry<String, Integer> entry : map.entrySet()) {  
2.     System.out.println("Key: " + entry.getKey() + ", Value: " + entry.getValue());  
3. }  

## Rehashing and Load Factor

To maintain performance, a HashMap needs to resize itself (rehash) when the number of elements grows significantly. It is controlled by the load factor that is a measure of how full the hash table is allowed to get before its capacity is automatically increased.

- **Load Factor:** HashMap's default load factor is 0.75. It means that when the hash table is 75% full, it will resize by doubling its current capacity.
- **Rehashing:** When rehashing occurs, a new, larger array is created, and all the existing entries are rehashed to new indices in the new array. It ensures that the hash table maintains a good balance between time and space complexity.