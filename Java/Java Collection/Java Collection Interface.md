Collection is a group of objects, which are known as elements. It is the root interface in the collection hierarchy. This interface is basically used to pass around the collections and manipulate them where the maximum generality is desired.

There are many methods defined in the Collection interface. These are as follows:

|Method|Description|
|---|---|
|[add()](https://www.tpointtech.com/java-collection-add-method)|This method returns a Boolean value true if it inserts the specified element in this collection.|
|[addAll()](https://www.tpointtech.com/java-collection-addall-method)|This method returns a Boolean value true if it adds all the elements of specified collection in the invoking collection.|
|[clear()](https://www.tpointtech.com/java-collection-clear-method)|It removes all the elements automatically from this collection.|
|[contains()](https://www.tpointtech.com/java-collection-contains-method)|It returns a Boolean value true if this queue contains the specified element.|
|[containsAll()](https://www.tpointtech.com/java-collection-containsall-method)|It returns a Boolean value true if this collection contains all the elements in the specified collection.|
|[equals()](https://www.tpointtech.com/java-collection-equals-method)|This method returns a boolean value true if the specified object is equal with this collection.|
|[hashCode()](https://www.tpointtech.com/java-collection-hashcode-method)|It returns a hash code value for this collection.|
|[isEmpty()](https://www.tpointtech.com/java-collection-isempty-method)|This method returns true if this collection contains no elements or is empty.|
|[iterator()](https://www.tpointtech.com/java-collection-iterator-method)|It returns an iterator over the elements in proper sequence.|
|[remove()](https://www.tpointtech.com/java-collection-remove-method)|It removes the specified element from this queue, if it is present in the collection.|
|[removeAll()](https://www.tpointtech.com/java-collection-removeall-method)|It removes all the elements of this collection which are also present in the specified collection.|
|[removeIf()](https://www.tpointtech.com/java-collection-removeif-method)|It removes all the elements of this collection that satisfy the given predicate filter.|
|[retainAll()](https://www.tpointtech.com/java-collection-retainall-method)|This method retains only those elements in this collection that are present in the specified collection.|
|[size()](https://www.tpointtech.com/java-collection-size-method)|It returns the total number of the elements in this collection.|
|[spliterator()](https://www.tpointtech.com/java-collection-spliterator-method)|It returns a spliterator over the elements in this collection.|
|[toArray()](https://www.tpointtech.com/java-collection-toarray-method)|It returns an array containing all the elements of this collection which are in proper sequence.|

---

## Example 1

### Example

[](https://www.tpointtech.com/java-collection#)[](https://www.tpointtech.com/java-collection#)[](https://www.tpointtech.com/java-collection#)

1. import java.util.Collections;  
2. import java.util.HashSet;  
3. import java.util.Set;  
4. public class Main {  
5.     public static void main(String[] args) {  
6.         Set<Integer> set = new HashSet<>();  
7.         // inserts the specified element in this collection  
8.         set.add(2);  
9.         set.add(5);  
10.         System.out.println("Initial collection :"+set);  
11.         //it adds all the elements of specified collection in the invoking collection.  
12.         Collections.addAll(set, 11, 12, 13, 14, 15);  
13.         System.out.println("Final Collection : "+set);  
14.         //returns the total size of the collection  
15.         int size =set.size();  
16.         System.out.println("Size of Collection : "+size);  
17.         //It returns a Boolean value true if this queue contains the specified element.  
18.         Boolean val=set.contains(5);  
19.         if (val){  
20.             System.out.println("5 is present in the collection");  
21.         }  
22.         else{  
23.             System.out.println("5 is not present in the collection");  
24.         }  
25.         //It removes all the elements automatically from this collection.  
26.         set.clear();  
27.         System.out.println("Elements in collection : "+set);  
28.     }  
29. }  

**Output:**

Initial collection :[2, 5]
Final Collection : [2, 5, 11, 12, 13, 14, 15]
Size of Collection : 7
5 is present in the collection
Elements in collection : []

## Example 2

### Example

[](https://www.tpointtech.com/java-collection#)[](https://www.tpointtech.com/java-collection#)[](https://www.tpointtech.com/java-collection#)

1. import java.util.Collections;  
2. import java.util.HashSet;  
3. import java.util.Iterator;  
4. import java.util.Set;  
5. import java.util.concurrent.ConcurrentLinkedQueue;  
6. public class Main {  
7.     public static void main(String[] args) {  
8.         ConcurrentLinkedQueue<Integer> queue = new ConcurrentLinkedQueue<Integer>();  
9.         Set<Integer> set = new HashSet<>();  
10.         //it adds all the elements of specified collection in the invoking collection.  
11.         Collections.addAll(set, 11, 12, 13, 14, 15);  
12.         System.out.println("Collection : "+set);  
13.         //It returns an iterator over the elements in proper sequence.  
14.         Iterator<Integer> iterator = set.iterator();  
15.         while(iterator.hasNext()){  
16.             System.out.println(iterator.next());  
17.         }  
18.        set.clear();  
19.         //checks whether the set is empty or not  
20.         Boolean b1= set.isEmpty();  
21.         if (b1){  
22.             System.out.println("Queue is empty");  
23.         }  
24.         else{  
25.             System.out.println("Queue is not empty");  
26.         }  
27.         for (int i=1;i<21;i++){  
28.             queue.add(i);  
29.         }  
30.         System.out.println(" Elements in the set : " + queue);  
31.         for (int i = 1; i < 11; i++) {  
32.             int j = i *5;  
33.             set.add(j);  
34.         }  
35.         //will give the elements in the queue which are present in set  
36.         queue.retainAll(set);  
37.         System.out.println(" Multiple of 5 : " + queue);  
38.     }  
39. }  

**Output:**

Collection : [11, 12, 13, 14, 15]
11
12
13
14
15
Queue is empty
Elements in the set : [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20]
Multiple of 5 : [5, 10, 15, 20]