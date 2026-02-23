
## Java Set Interface

A Java Set interface represents a group of elements arranged like an array. It does not allow duplicate elements. When we try to pass the same element that is already available in the Set, then it will not store into the Set. It is used to model the mathematical set abstraction.

## Java HashSet class

A Java HashSet class represents a set of elements (objects). It does not guarantee the order of elements. It constructs a collection that uses a hash table for storing elements. It contains unique elements. It inherits the AbstractSet class. It also implements the Set interface. It uses a technique to store elements is called hashing. HashSet uses HashMap internally in Java.

Suppose, we want to create a HashSet to store a group of Strings, then create the object as:

[](https://www.tpointtech.com/working-of-hashset-in-java#)[](https://www.tpointtech.com/working-of-hashset-in-java#)[](https://www.tpointtech.com/working-of-hashset-in-java#)

1. HashSet<String> hs=new HashSet<>();  

Where <String> is the generic type parameter. It represents the type of element storing in the HashSet.

HashSet implements Set interface. It guarantees uniqueness. It is achieved by storing elements as keys with the same value always. HashSet does not have any method to retrieve the object from the HashSet. There is only a way to get objects from the HashSet via Iterator. When we create an object of HashSet, it internally creates an instance of HashMap with default initial capacity 16.

HashSet uses a constructor HashSet(int capacity) that represents how many elements can be stored in the HashSet. The capacity may increase automatically when more elements to be store.

HashSet uses another constructor HashSet(int capacity, float loadfactor). Here, loadfactor demines the point where the capacity of HashSet would be increased internally. For example, the product of capacity and loadfactor is 101*0.5=50.5. It means that after storing 50th element into the HashSet; its capacity will be internally increased to store more elements. The initial default capacity of HashSet is 16. The default load factor is 0.75.

## HashSet Implementation

In the following, we are implementing add() method which adds element into HashSet.

### Example

[](https://www.tpointtech.com/working-of-hashset-in-java#)[](https://www.tpointtech.com/working-of-hashset-in-java#)[](https://www.tpointtech.com/working-of-hashset-in-java#)

1. import java.util.*;  
2. public class HashsetDemo  
3. {  
4. public static void main(String[] args)  
5. {  
6. HashSet<String> hs= new HashSet<String>();  
7. hs.add(?India?);  
8. hs.add(?America?);  
9. hs.add(?Russia?);  
10. System.out.println(?Set is ?+hs);      //view HashSet  
11. Iterator it=hs.iterator();               //add an iterator to hs  
12. System.out.println("Elements using iterator:");  
13. while(it.hasNext())                             //display elements by using iterator  
14. {  
15. String s=(String)it.next();  
16. System.out.println(s);  
17. }  
18. }  
19. }  

**Output:**

Set is [America, India, Russia]
Elements using iterator:
America
India
Russia

In the following example we are trying to add some duplicate values.

### Example

[](https://www.tpointtech.com/working-of-hashset-in-java#)[](https://www.tpointtech.com/working-of-hashset-in-java#)[](https://www.tpointtech.com/working-of-hashset-in-java#)

1. import java.util.*;  
2. public class Main  
3. {  
4. public static void main(String[] args)  
5. {  
6. HashSet<String> hs= new HashSet<String>();  
7. hs.add("India");  
8. hs.add("America");  
9. hs.add("Russia");  
10. hs.add("China");  
11. hs.add("India");                          //duplicate value  
12. hs.add("Russia");                                //duplicate value  
13. System.out.println("Set is "+hs);           //view HashSet  
14. Iterator it=hs.iterator();                    //add an iterator to hs  
15. System.out.println("Elements using iterator:");  
16. while(it.hasNext())                          //display elements by using iterator  
17. {  
18. String s=(String)it.next();  
19. System.out.println(s);  
20. }  
21. }  
22. }  

**Output:**

Set is [China, America, India, Russia]
Elements using iterator:
China
America
India
Russia

In the above example we have added some duplicate values. We can observe that duplicate values are not stored in the HashSet. When we pass duplicate elements in the add() method of the Set object, it internally returns false.

Here, a question arises that how it returns false. When we open the HashSet implementation of the add() method in Java APIs i.e. rt.jar, we find the following code in it:

[](https://www.tpointtech.com/working-of-hashset-in-java#)[](https://www.tpointtech.com/working-of-hashset-in-java#)[](https://www.tpointtech.com/working-of-hashset-in-java#)

1. public class HashSet<E> extends AbstractSet<E>  
2. {  
3. private transient HashMap<E,Object> map;  
4. // Dummy value to associate with an Object in the backing Map  
5. private static final Object PRESENT = new Object();  
6. public HashSet()  
7. {  
8. map = new HashMap<>();  
9. }  
10. public boolean add(E e)   
11. {  
12. return map.put(e, PRESENT)==null;  
13. }  
14. }  

In the above code a call to add(object) is delegated to put(key, value) internally. Where key is the object we have passed and the value is another object, called PRESENT. It is a constant in java.util.HashSet.

We are achieving uniqueness in Set internally through HashMap. When we create an object of HashSet, it will create an object of HashMap. We know that each key is unique in the HashMap. So, we pass the argument in the add(E e) method. Here, we need to associate some value to the key. It will associate with Dummy value that is (new Object()) which is referred by Object reference PRESENT.

When we add an element in HashSet like hs.add("India"), Java does internally is that it will put that element E here "India" as a key into the HashMap (generated during HashSet object creation). It will also put some dummy value that is Object's object is passed as a value to the key.

**put method of HashMap**

[](https://www.tpointtech.com/working-of-hashset-in-java#)[](https://www.tpointtech.com/working-of-hashset-in-java#)[](https://www.tpointtech.com/working-of-hashset-in-java#)

1. put(Key k, Value v)  
2. {  
3. //some code  
4. }  

The important points about put(key, value) method is that:

- If the Key is unique and added to the map, then it will return null
- If the Key is duplicate, then it will return the old value of the key.

When we invoke add() method in HashSet, Java internally checks the return value of map.put(key, value) method with the null value.

[](https://www.tpointtech.com/working-of-hashset-in-java#)[](https://www.tpointtech.com/working-of-hashset-in-java#)[](https://www.tpointtech.com/working-of-hashset-in-java#)

1. public boolean add(E e)  
2. {  
3. return map.put(e, PRESENT==null);  
4. }  

- If the method map.put(key, value) returns null, then the method map.put(e, PRESENT)==null will return true internally, and the element added to the HashSet.
- If the method map.put(key, value) returns the old value of the key, then the method map.put(e, PRESENT)==null will return false internally, and the element will not add to the HashSet.

**Retrieving Object from the HashSet**

We use iterator() method to retrieve object from the HashSet. It is a method of **java.util.HashSet** class. It returns iterator for backup Map returned by map.keySet().iterator() method.

[](https://www.tpointtech.com/working-of-hashset-in-java#)[](https://www.tpointtech.com/working-of-hashset-in-java#)[](https://www.tpointtech.com/working-of-hashset-in-java#)

1. public Iterator<E> iterator()  
2. {  
3. return map.keySet().iterator();  
4. }