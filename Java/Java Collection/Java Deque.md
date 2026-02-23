A deque is a linear collection that supports insertion and deletion of elements from both the ends. The name 'deque' is an abbreviation for double-ended queue.

There are no fixed limits on the deque for the number of elements they may contain. However, this interface supports capacity restricted deques as well as the deques with no fixed size limits. There are various methods which are provided to insert, remove and examine the elements.

These methods typically exist in two forms: the one that throws an exception when the particular operation fails and the other returns a special value which can be either null or false depending upon the operations.

## Methods

The java.util.Deque interface provides methods to perform the operations of double-ended queue in Java. Its implementation class is java.util.ArrayDeque.

|Methods|Description|
|---|---|
|[add(E e)](https://www.tpointtech.com/java-deque-add-method)|This method is used to insert a specified element into the queue represented by the deque|
|[addAll(Collection<? Extends E>c)](https://www.tpointtech.com/java-deque-addall-method)|Adds all the elements in the specified collection at the end of the deque.|
|[addFirst(E e)](https://www.tpointtech.com/java-deque-addfirst-method)|Inserts the specified element at the front of the deque.|
|[addLast(E e)](https://www.tpointtech.com/java-deque-addlast-method)|Inserts the specified element at the end of the deque.|
|[contains(object o)](https://www.tpointtech.com/java-deque-contains-method)|Returns true if the deque contains the specified element.|
|[descendingIterator()](https://www.tpointtech.com/java-deque-descendingiterator-method)|Returns an iterator over the elements in reverse sequential order.|
|[element()](https://www.tpointtech.com/java-deque-element-method)|Retrieves the head of the queue represented by the deque.|
|[getFirst()](https://www.tpointtech.com/java-deque-getfirst-method)|Retrieves but does not remove the first element of the deque.|
|[getLast()](https://www.tpointtech.com/java-deque-getlast-method)|Retrieves but does not remove the last element of the deque.|
|[iterator()](https://www.tpointtech.com/java-deque-iterator-method)|Returns an iterator over the element in the deque in a proper sequence.|
|[offer(E e)](https://www.tpointtech.com/java-deque-offer-method)|Inserts the specified element into the deque, returning true upon success and false if no space is available.|
|[offerFirst()](https://www.tpointtech.com/java-deque-offerfirst-method)|Inserts the specified element at the front of the deque unless it violates the capacity restriction.|
|[offerLast()](https://www.tpointtech.com/java-deque-offerlast-method)|Inserts the specified element at the end of the deque unless it violates the capacity restriction.|
|[peek()](https://www.tpointtech.com/java-deque-peek-method)|Retrieves but does not move the head of the queue represented by the deque or may return null if the deque is empty.|
|[peekFirst()](https://www.tpointtech.com/java-deque-peekfirst-method)|Retrieves but does not move the first element of the deque or may return null if the deque is empty.|
|[peekLast()](https://www.tpointtech.com/java-deque-peeklast-method)|Retrieves but does not move the last element of the deque or may return null if the deque is empty.|
|[poll()](https://www.tpointtech.com/java-deque-poll-method)|Retrieves and remove the head of the queue represented by the deque or may return null if the deque is empty.|
|[pollFirst()](https://www.tpointtech.com/java-deque-pollfirst-method)|Retrieves and remove the first element of the deque or may return null if the deque is empty.|
|[pollLast()](https://www.tpointtech.com/java-deque-polllast-method)|Retrieves and remove the last element of the deque or may return null if the deque is empty.|
|pop()|Pops an element from the stack represented by the deque.|
|push()|Pushes an element onto the stack represented by the deque.|
|remove()|Retrieves and remove the head of the queue represented by the deque.|
|remove(Object o)|Removes the first occurrence of the specified element from the deque.|
|removeFirst()|Retrieves and remove the first element from the deque.|
|removeFirstOccurrence(Object o)|Remove the first occurrence of the element from the deque.|
|removeLast()|Retrieve and remove the last element from the deque.|
|removeLastOccurrence(Object o)|Remove the last occurrence of the element from the deque.|
|size()|Returns the total number of elements in the deque.|

---

## Example 1

### Example

[](https://www.tpointtech.com/java-deque#)[](https://www.tpointtech.com/java-deque#)[](https://www.tpointtech.com/java-deque#)

1. import java.util.ArrayDeque;  
2. import java.util.Deque;  

3. public class JavaDequeExample1 {  
4.   public static void main(String[] args) {  
5.     Deque<Integer> deque = new ArrayDeque<Integer>();  
6.     // Inserts the element.  
7.     deque.add(1);  
8.     deque.add(2);  
9.     deque.add(3);  
10.     System.out.println("Inserting three elements : ");  
11.     for (Integer integer : deque) {  
12.     System.out.println(integer);      
13.     }  
14.     // Popping the element.  
15.     deque.pop();  
16.     System.out.println("After popping : ");  
17.     for (Integer integer : deque) {  
18.         System.out.println(integer);  
19.     }  
20.     deque.remove(3);  
21.     System.out.println("Removing the element 3 :"+deque);  
22.   }  
23. }  

**Output:**

Inserting three elements :
1
2
3
After popping :
2
3
Removing the element 3 :[2]

## Example 2

### Example

[](https://www.tpointtech.com/java-deque#)[](https://www.tpointtech.com/java-deque#)[](https://www.tpointtech.com/java-deque#)

1. import java.util.ArrayDeque;  
2. import java.util.Deque;  

3. public class JavaDequeExample2 {  
4. public static void main(String[] args) {  
5.    Deque<String> deque = new ArrayDeque<String>();  
6.    // Adding the element in the front of the deque.  
7.    deque.addFirst("Java");  
8.     System.out.println("The first element is : "+deque);  
9.    // Again adding the element in the front of the deque.  
10.     deque.addFirst("Python");  
11.     System.out.println("After adding the next element in the front of the deque : "+deque);  
12.      deque.add("Ruby");  
13.      System.out.println("The final deque is  : "+deque);  
14.    // Returns the number of elements.  
15.      int size =  deque.size();  
16.      System.out.println("The number of elements are : "+size);  
17.     // Removes the last element.  
18.      deque.removeLast();  
19.  System.out.println("Deque after removing the last element is given as :  "+deque);  
20.    }      
21. }  

**Output:**

The first element is : [Java]
After adding the next element in the front of the deque : [Python, Java]
The final deque is : [Python, Java, Ruby]
The number of elements are : 3
Deque after removing the last element is given as : [Python, Java]