The Java Collections class belongs to java.util [package](https://www.tpointtech.com/packages-in-java) and provides static utility methods that operate on return collections, such as [List](https://www.tpointtech.com/java-list), [Set](https://www.tpointtech.com/set-in-java), and [Map](https://www.tpointtech.com/java-map). These methods are mostly used to perform common operations such as [sorting](https://www.tpointtech.com/sorting-algorithms), [searching](https://www.tpointtech.com/searching-algorithms), reversing and [synchronization](https://www.tpointtech.com/synchronization-in-java).

The methods of this class all throw a [**NullPointerException**](https://www.tpointtech.com/java-lang-nullpointerexception) if the collections or class objects provided to them are null.

To read more [Collections in Java](https://www.tpointtech.com/collections-in-java)

![Java Collections Class | Java Collections Class Methods](https://images.tpointtech.com/core/images/java-collections-class-1.png)

## Java Collections Class Methods

|Modifier & Type|Methods|Descriptions|
|---|---|---|
|static <T> boolean|[addAll()](https://www.tpointtech.com/java-collections-addall-method)|It is used to adds all of the specified elements to the specified collection.|
|static <T> Queue<T>|[asLifoQueue()](https://www.tpointtech.com/java-collections-aslifoqueue-method)|It returns a view of a Deque as a Last-in-first-out (LIFO) Queue.|
|static <T> int|[binarySearch()](https://www.tpointtech.com/java-collections-binarysearch-method)|It searches the list for the specified object and returns their position in a sorted list.|
|static <E> Collection<E>|[checkedCollection()](https://www.tpointtech.com/java-collections-checkedcollection-method)|It is used to returns a dynamically typesafe view of the specified collection.|
|static <E> List<E>|[checkedList()](https://www.tpointtech.com/java-collections-checkedlist-method)|It is used to returns a dynamically typesafe view of the specified list.|
|static <K,V> Map<K,V>|[checkedMap()](https://www.tpointtech.com/java-collections-checkedmap-method)|It is used to returns a dynamically typesafe view of the specified map.|
|static <K,V> NavigableMap<K,V>|[checkedNavigableMap()](https://www.tpointtech.com/java-collections-checkednavigablemap-method)|It is used to returns a dynamically typesafe view of the specified navigable map.|
|static <E> NavigableSet<E>|[checkedNavigableSet()](https://www.tpointtech.com/java-collections-checkednavigableset-method)|It is used to returns a dynamically typesafe view of the specified navigable set.|
|static <E> Queue<E>|[checkedQueue()](https://www.tpointtech.com/java-collections-checkedqueue-method)|It is used to returns a dynamically typesafe view of the specified queue.|
|static <E> Set<E>|[checkedSet()](https://www.tpointtech.com/java-collections-checkedset-method)|It is used to returns a dynamically typesafe view of the specified set.|
|static <K,V> SortedMap<K,V>|[checkedSortedMap()](https://www.tpointtech.com/java-collections-checkedsortedmap-method)|It is used to returns a dynamically typesafe view of the specified sorted map.|
|static <E> SortedSet<E>|[checkedSortedSet()](https://www.tpointtech.com/java-collections-checkedsortedset-method)|It is used to returns a dynamically typesafe view of the specified sorted set.|
|static <T> void|[copy()](https://www.tpointtech.com/java-collections-copy-method)|It is used to copy all the elements from one list into another list.|
|static boolean|[disjoint()](https://www.tpointtech.com/java-collections-disjoint-method)|It returns true if the two specified collections have no elements in common.|
|static <T> Enumeration<T>|[emptyEnumeration()](https://www.tpointtech.com/java-collections-emptyenumeration-method)|It is used to get an enumeration that has no elements.|
|static <T> Iterator<T>|[emptyIterator()](https://www.tpointtech.com/java-collections-emptyiterator-method)|It is used to get an Iterator that has no elements.|
|static <T> List<T>|[emptyList()](https://www.tpointtech.com/java-collections-emptylist-method)|It is used to get a List that has no elements.|
|static <T> ListIterator<T>|[emptyListIterator()](https://www.tpointtech.com/java-collections-emptylistiterator-method)|It is used to get a List Iterator that has no elements.|
|static <K,V> Map<K,V>|[emptyMap()](https://www.tpointtech.com/java-collections-emptymap-method)|It returns an empty map which is immutable.|
|static <K,V> NavigableMap<K,V>|[emptyNavigableMap()](https://www.tpointtech.com/java-collections-emptynavigablemap-method)|It returns an empty navigable map which is immutable.|
|static <E> NavigableSet<E>|[emptyNavigableSet()](https://www.tpointtech.com/java-collections-emptynavigableset-method)|It is used to get an empty navigable set which is immutable in nature.|
|static <T> Set<T>|[emptySet()](https://www.tpointtech.com/java-collections-emptyset-method)|It is used to get the set that has no elements.|
|static <K,V> SortedMap<K,V>|[emptySortedMap()](https://www.tpointtech.com/java-collections-emptysortedmap-method)|It returns an empty sorted map which is immutable.|
|static <E> SortedSet<E>|[emptySortedSet()](https://www.tpointtech.com/java-collections-emptysortedset-method)|It is used to get the sorted set that has no elements.|
|static <T> Enumeration<T>|[enumeration()](https://www.tpointtech.com/java-collections-enumeration-method)|It is used to get the enumeration over the specified collection.|
|static <T> void|[fill()](https://www.tpointtech.com/java-collections-fill-method)|It is used to replace all of the elements of the specified list with the specified elements.|
|static int|[frequency()](https://www.tpointtech.com/java-collections-frequency-method)|It is used to get the number of elements in the specified collection equal to the specified object.|
|static int|[indexOfSubList()](https://www.tpointtech.com/java-collections-indexofsublist-method)|It is used to get the starting position of the first occurrence of the specified target list within the specified source list. It returns -1 if there is no such occurrence in the specified list.|
|static int|[lastIndexOfSubList()](https://www.tpointtech.com/java-collections-lastindexofsublist-method)|It is used to get the starting position of the last occurrence of the specified target list within the specified source list. It returns -1 if there is no such occurrence in the specified list.|
|static <T> ArrayList<T>|[list()](https://www.tpointtech.com/java-collections-list-method)|It is used to get an array list containing the elements returned by the specified enumeration in the order in which they are returned by the enumeration.|
|static <T extends Object & Comparable<? super T>> T|[max()](https://www.tpointtech.com/java-collections-max-method)|It is used to get the maximum value of the given collection, according to the natural ordering of its elements.|
|static <T extends Object & Comparable<? super T>> T|[min()](https://www.tpointtech.com/java-collections-min-method)|It is used to get the minimum value of the given collection, according to the natural ordering of its elements.|
|static <T> List<T>|[nCopies()](https://www.tpointtech.com/java-collections-ncopies-method)|It is used to get an immutable list consisting of **n** copies of the specified object.|
|static <E> Set<E>|[newSetFromMap()](https://www.tpointtech.com/java-collections-newsetfrommap-method)|It is used to return a set backed by the specified map.|
|static <T> boolean|[replaceAll()](https://www.tpointtech.com/java-collections-replaceall-method)|It is used to replace all occurrences of one specified value in a list with the other specified value.|
|static void|[reverse()](https://www.tpointtech.com/java-collections-reverse-method)|It is used to reverse the order of the elements in the specified list.|
|static <T> Comparator<T>|[reverseOrder()](https://www.tpointtech.com/java-collections-reverseorder-method)|It is used to get the comparator that imposes the reverse of the natural ordering on a collection of objects which implement the Comparable interface.|
|static void|[rotate()](https://www.tpointtech.com/java-collections-rotate-method)|It is used to rotate the elements in the specified list by a given distance.|
|static void|[shuffle()](https://www.tpointtech.com/java-collections-shuffle-method)|It is used to randomly reorders the specified list elements using a default randomness.|
|static <T> Set<T>|[singleton()](https://www.tpointtech.com/java-collections-singleton-method)|It is used to get an immutable set which contains only the specified object.|
|static <T> List<T>|[singletonList()](https://www.tpointtech.com/java-collections-singletonlist-method)|It is used to get an immutable list which contains only the specified object.|
|static <K,V> Map<K,V>|[singletonMap()](https://www.tpointtech.com/java-collections-singletonmap-method)|It is used to get an immutable map, mapping only the specified key to the specified value.|
|static <T extends Comparable<? super T>>void|[sort()](https://www.tpointtech.com/java-collections-sort-method)|It is used to sort the elements presents in the specified list of collection in ascending order.|
|static void|[swap()](https://www.tpointtech.com/java-collections-swap-method)|It is used to swap the elements at the specified positions in the specified list.|
|static <T> Collection<T>|[synchronizedCollection()](https://www.tpointtech.com/java-collections-synchronizedcollection-method)|It is used to get a synchronized (thread-safe) collection backed by the specified collection.|
|static <T> List<T>|[synchronizedList()](https://www.tpointtech.com/java-collections-synchronizedlist-method)|It is used to get a synchronized (thread-safe) collection backed by the specified list.|
|static <K,V> Map<K,V>|[synchronizedMap()](https://www.tpointtech.com/java-collections-synchronizedmap-method)|It is used to get a synchronized (thread-safe) map backed by the specified map.|
|static <K,V> NavigableMap<K,V>|[synchronizedNavigableMap()](https://www.tpointtech.com/java-collections-synchronizednavigablemap-method)|It is used to get a synchronized (thread-safe) navigable map backed by the specified navigable map.|
|static <T> NavigableSet<T>|[synchronizedNavigableSet()](https://www.tpointtech.com/java-collections-synchronizednavigableset-method)|It is used to get a synchronized (thread-safe) navigable set backed by the specified navigable set.|
|static <T> Set<T>|[synchronizedSet()](https://www.tpointtech.com/java-collections-synchronizedset-method)|It is used to get a synchronized (thread-safe) set backed by the specified set.|
|static <K,V> SortedMap<K,V>|[synchronizedSortedMap()](https://www.tpointtech.com/java-collections-synchronizedsortedmap-method)|It is used to get a synchronized (thread-safe) sorted map backed by the specified sorted map.|
|static <T> SortedSet<T>|[synchronizedSortedSet()](https://www.tpointtech.com/java-collections-synchronizedsortedset-method)|It is used to get a synchronized (thread-safe) sorted set backed by the specified sorted set.|
|static <T> Collection<T>|[unmodifiableCollection()](https://www.tpointtech.com/java-collections-unmodifiablecollection-method)|It is used to get an unmodifiable view of the specified collection.|
|static <T> List<T>|[unmodifiableList()](https://www.tpointtech.com/java-collections-unmodifiablelist-method)|It is used to get an unmodifiable view of the specified list.|
|static <K,V> Map<K,V>|[unmodifiableMap()](https://www.tpointtech.com/java-collections-unmodifiablemap-method)|It is used to get an unmodifiable view of the specified map.|
|static <K,V> NavigableMap<K,V>|[unmodifiableNavigableMap()](https://www.tpointtech.com/java-collections-unmodifiablenavigablemap-method)|It is used to get an unmodifiable view of the specified navigable map.|
|static <T> NavigableSet<T>|[unmodifiableNavigableSet()](https://www.tpointtech.com/java-collections-unmodifiablenavigableset-method)|It is used to get an unmodifiable view of the specified navigable set.|
|static <T> Set<T>|[unmodifiableSet()](https://www.tpointtech.com/java-collections-unmodifiableset-method)|It is used to get an unmodifiable view of the specified set.|
|static <K,V> SortedMap<K,V>|[unmodifiableSortedMap()](https://www.tpointtech.com/java-collections-unmodifiablesortedmap-method)|It is used to get an unmodifiable view of the specified sorted map.|
|static <T> SortedSet<T>|[unmodifiableSortedSet()](https://www.tpointtech.com/java-collections-unmodifiablesortedset-method)|It is used to get an unmodifiable view of the specified sorted set.|

Let's use some of the above methods in Java program.

## Java Collections Class Method Examples

### Collections.addAll() Method

The method adds all of the specified elements to the specified collection. Elements to be added may be specified individually or as an array.

**Syntax:**

[](https://www.tpointtech.com/java-collections-class#)[](https://www.tpointtech.com/java-collections-class#)[](https://www.tpointtech.com/java-collections-class#)

1. public static <T> boolean addAll(Collection<? super T> c, T... elements)  

### Example

[](https://www.tpointtech.com/java-collections-class#)[](https://www.tpointtech.com/java-collections-class#)[](https://www.tpointtech.com/java-collections-class#)

1. import java.util.*;    
2. public class Main {    
3.     public static void main(String a[]){        
4.         List<String> list = new ArrayList<String>();    
5.         list.add("C");    
6.         list.add("Core Java");    
7.         list.add("Advance Java");    
8.         System.out.println("Initial collection value:"+list);    
9.         Collections.addAll(list, "Servlet","JSP");    
10.         System.out.println("After adding elements collection value:"+list);    
11.         String[] strArr = {"C#", ".Net"};    
12.         Collections.addAll(list, strArr);    
13.         System.out.println("After adding array collection value:"+list);    
14.     }    
15. }    

**Output:**

Initial collection value:[C, Core Java, Advance Java]
After adding elements collection value:[C, Core Java, Advance Java, Servlet, JSP]
After adding array collection value:[C, Core Java, Advance Java, Servlet, JSP, C#, .Net]

### Collections.max() Method

This method returns the maximum element from the given collection.

**Syntax:**

[](https://www.tpointtech.com/java-collections-class#)[](https://www.tpointtech.com/java-collections-class#)[](https://www.tpointtech.com/java-collections-class#)

1. public static <T extends Comparable<? super T>> T max(Collection<? extends T> coll)  

### Example

[](https://www.tpointtech.com/java-collections-class#)[](https://www.tpointtech.com/java-collections-class#)[](https://www.tpointtech.com/java-collections-class#)

1. import java.util.*;    
2. public class Main {    
3.     public static void main(String a[]){           
4.         List<Integer> list = new ArrayList<Integer>();    
5.         list.add(46);    
6.         list.add(67);    
7.         list.add(24);    
8.         list.add(16);    
9.         list.add(8);    
10.         list.add(12);    
11.         System.out.println("Value of maximum element from the collection: "+Collections.max(list));    
12.     }    
13. }    

**Output:**

Value of maximum element from the collection: 67

**Explanation**

In the above code, we have a list of numbers [46, 67, 24, 16, 8, 12]. The collection.max() method is used to find the largest number in the list which is 67. It works based on the natural order of integers. The method then prints the minimum value. It is the easiest way to find the biggest item in any collection.

### Collections.min() Method

This method returns the minimum element from the given collection.

**Syntax:**

[](https://www.tpointtech.com/java-collections-class#)[](https://www.tpointtech.com/java-collections-class#)[](https://www.tpointtech.com/java-collections-class#)

1. public static <T extends Comparable<? super T>> T min(Collection<? extends T> coll)  

### Example

[](https://www.tpointtech.com/java-collections-class#)[](https://www.tpointtech.com/java-collections-class#)[](https://www.tpointtech.com/java-collections-class#)

1. import java.util.*;    
2. public class Main {    
3.     public static void main(String a[]){           
4.         List<Integer> list = new ArrayList<Integer>();    
5.         list.add(46);    
6.         list.add(67);    
7.         list.add(24);    
8.         list.add(16);    
9.         list.add(8);    
10.         list.add(12);    
11.         System.out.println("Value of minimum element from the collection: "+Collections.min(list));    
12.     }    
13. }    

**Output:**

Value of minimum element from the collection: 8

**Explanation**

In the above code, we have a list of numbers [46, 67, 24, 16, 8, 12]. The collection.min() method finds the smallest number in the list which is 8. It works based on the natural order of integers. The method then prints the minimum value. It is the easiest way to find the smallest item in any collection.

### Collections.sort() Method

The methos is used to sort the given elements. If the elements do not implement Comparable, this method throws a ClassCastException.

[](https://www.tpointtech.com/java-collections-class#)[](https://www.tpointtech.com/java-collections-class#)[](https://www.tpointtech.com/java-collections-class#)

1. <strong>Syntax:</strong></p>  
2. <p>public static <T extends Comparable<? Super T>> void sort(List<T>list)  

### Example

[](https://www.tpointtech.com/java-collections-class#)[](https://www.tpointtech.com/java-collections-class#)[](https://www.tpointtech.com/java-collections-class#)

1. import java.util.Arrays;  
2. import java.util.Collections;  
3. import java.util.List;  
4. public class Main {  
5.     public static void main(String[] args) {  
6.         List<Integer> numbers = Arrays.asList(14, 5, 11, 7);  
7.         Collections.sort(numbers);  
8.         System.out.println(numbers);    
9.     }  
10. }  

**Output:**

[5, 7, 11, 14]

**Explanation**

In the above code, we create a list of integers (14, 5, 11, 7) using Arrays.asList(). The Collections.sort() method is used to sort the list in ascending order based on their natural order (i.e., from smallest to largest). After sorting, the System.out.println() method displays the sorted list: [5, 7, 11, 14].

### Collections.reverse() Method

The method modifies the original list directly which makes it simple way to reverse collection without the need of custom code.

**Syntax:**

[](https://www.tpointtech.com/java-collections-class#)[](https://www.tpointtech.com/java-collections-class#)[](https://www.tpointtech.com/java-collections-class#)

1. public static void reverse(List<?> list)  

### Example

[](https://www.tpointtech.com/java-collections-class#)[](https://www.tpointtech.com/java-collections-class#)[](https://www.tpointtech.com/java-collections-class#)

1. import java.util.*;  
2. public class Main {  
3.     public static void main(String[] args) {  
4.         List<String> fruits = new ArrayList<>(Arrays.asList("Banana", "Pineapple", "Kiwi"));  
5.         Collections.reverse(fruits);  
6.         System.out.println(fruits);    
7.     }  
8. }  

**Output:**

[Kiwi, Pineapple, Banana]

**Explanation**

In the above code, we have created a list of fruits ("Banana", "Pineapple", "Kiwi") using Arrays.asList() and wrap it with an ArrayList. The Collections.reverse() method is then called to reverse the order of elements in the list.

This method modifies the original list directly, so the order changes from [Banana, Pineapple, Kiwi] to [Kiwi, Pineapple, Banana]. Hence, the reversed list is printed to console. This method is simple and efficient to make it easy to reverse collections.

### Collections.shuffle() Method

This method randomly reorders the elements in the given list using default randomness.

**Syntax:**

[](https://www.tpointtech.com/java-collections-class#)[](https://www.tpointtech.com/java-collections-class#)[](https://www.tpointtech.com/java-collections-class#)

1. public static void shuffle(List<?> list)  

### Example

[](https://www.tpointtech.com/java-collections-class#)[](https://www.tpointtech.com/java-collections-class#)[](https://www.tpointtech.com/java-collections-class#)

1. import java.util.*;  
2. public class Main {  
3.     public static void main(String[] aargs){  
4.         List<Integer> numbers = new ArrayList<>(Arrays.asList(5, 6, 7, 8, 9));  
5.         Collections.shuffle(numbers);  
6.         System.out.println(numbers);  
7.     }  
8. }  

**Output:**

[8, 7, 5, 9, 6]

**Explanation**

In the above code we have created a list of integers (5, 6, 7, 8, 9) using ArrayList() and wrap it with an ArrayList. The collection.shuffle() method is then used to randomly shuffle the elements in the list, introducing randomness to their order.

After shuffling, the list might appear as [8, 7, 5, 9, 6] the order will change each time when we run the code. This method is helpful in scenarios like card games or any case where we need to rearrange a collection of items randomly.

### Collections.swap() Method

Swaps the elements at the specified positions in the specified list. (If the specified positions are equal, invoking this method leaves the list unchanged.)

**Syntax:**

[](https://www.tpointtech.com/java-collections-class#)[](https://www.tpointtech.com/java-collections-class#)[](https://www.tpointtech.com/java-collections-class#)

1. public static void swap(List<?> list, int i, int j)  

**Parameters:**

list: The list in which to swap elements.

i: the index of one element to be swapped.

j: the index of the other element to be swapped.

### Example

[](https://www.tpointtech.com/java-collections-class#)[](https://www.tpointtech.com/java-collections-class#)[](https://www.tpointtech.com/java-collections-class#)

1. import java.util.*;  
2. public class Main {  
3.     public static void main(String[] args) {  
4.         List<String> names = new ArrayList<>(Arrays.asList("Daisy", "Ginny",        "Georgia"));  
5.         Collections.swap(names, 0, 2);  
6.         System.out.println(names);    
7.     }  
8. }  

**Output:**

[Georgia, Ginny, Daisy]

**Explanation**

It the above code, we have created a list of names: "Daisy", "Ginny" and "Georgia". The Collections.swap() method is used to swap the elements at position 0 and 2 which means "Daisy" and "Georgia" switch places.

After swapping, the list becomes [Georgia, Ginny, Daisy]. This method is useful when we want to change the order of specific elements quickly in a list without writing extra code.

### Collections.copy() Method

The copy () method copies elements from one list to another. The destination list must be large enough to hold all elements from the source list.

**Syntax:**

[](https://www.tpointtech.com/java-collections-class#)[](https://www.tpointtech.com/java-collections-class#)[](https://www.tpointtech.com/java-collections-class#)

1. public static <T> void copy(List<? super T> dest, List<? extends T> src)  

### Example

[](https://www.tpointtech.com/java-collections-class#)[](https://www.tpointtech.com/java-collections-class#)[](https://www.tpointtech.com/java-collections-class#)

1. import java.util.*;  
2. public class Main {  
3.        public static void main(String[] args) {  
4.                   List<String> source = new ArrayList<>(Arrays.asList("A", "B", "C"));  
5.                    List<String> dest = new ArrayList<>(Arrays.asList("X", "Y", "Z"));  
6.                     Collections.copy(dest, source);  
7.                     System.out.println(dest);           
8.        }  
9. }  

**Output:**

[A, B, C]

**Explanation**

In the above code, we have two lists: one is the source list ("A", "B", "C") and the other is destination list ("X", "Y", "Z"). The collections.copy() method copies all elements from the source list into the destination list, replacing the existing values from each position. After the copy, the destination list becomes [A, B, C].

### Collections.emptyList() Method

The emptyList() method creates a list that has no elements and cannot be changed. This means we cannot add, remove, or update anything in the list.

**Syntax:**

[](https://www.tpointtech.com/java-collections-class#)[](https://www.tpointtech.com/java-collections-class#)[](https://www.tpointtech.com/java-collections-class#)

1. public static <T> List<T> emptyList()  

### Example

[](https://www.tpointtech.com/java-collections-class#)[](https://www.tpointtech.com/java-collections-class#)[](https://www.tpointtech.com/java-collections-class#)

1. import java.util.*;  
2. public class Main {  
3.            public static void main(String[] args) {  
4.             List<String> emptyList = Collections.emptyList();  
5.                   System.out.println(emptyList);   
6.                 }  
7.            }  

**Output:**

[]

**Explanation**

In this example, we used Collection.emptyList() to make an empty list. It is a read only list, so no one can add or remove anything from it. This is useful when we need to return an empty list from a method, and we want to make sure it stays empty and safe from changes.

### Collections.singletonList() Method

The method returns an immutable list containing only the specified object. The returned list is serializable. It returns an immutable list containing only the specified object.

**Syntax:**

[](https://www.tpointtech.com/java-collections-class#)[](https://www.tpointtech.com/java-collections-class#)[](https://www.tpointtech.com/java-collections-class#)

1. public static <T> List<T> singletonList(T o)  

Where,

T: the class of the objects in the list

o: the sole object to be stored in the returned list.

### Example

[](https://www.tpointtech.com/java-collections-class#)[](https://www.tpointtech.com/java-collections-class#)[](https://www.tpointtech.com/java-collections-class#)

1. import java.util.*;  
2. public class Main {  
3.      public static void main(String[] args) {  
4.      List<String> singleton = Collections.singletonList("Hello");  
5.            System.out.println(singleton);    
6.            }   
7. }  

**Output:**

[Hello]

**Explanation**

The above method in Java is used to create a list that contains only one item and that cannot be changed. This means that we cannot add, remove or replace any element in it. It is helpful when we need a fixed, single-value list for quick use. The above example shows the list contains only the word "Hello", and when printed, it shows [Hello]. This method is often used when we want to return a one-item list without worrying that someone might modify it later.

## Conclusion

The Collections class in Java gives us many easy-to-use tools for working with collections like lists, sets, and maps. It has built-in methods to do common tasks such as sorting, reversing, shuffling and copying. These methods help us to write less code and make the program simpler and easier to understand. Working with collections class can save time.