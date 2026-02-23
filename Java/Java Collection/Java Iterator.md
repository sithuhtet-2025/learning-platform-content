In Java, an **Iterator** is one of the Java cursors. **Java Iterator** is an interface that is practiced in order to iterate over a collection of Java object components entirety one by one. It is free to use in the Java programming language since the Java 1.2 Collection framework. It belongs to java.util package.

Though Java Iterator was introduced in Java 1.2, however, it is still not the oldest tool available to traverse through the elements of the Collection object. The oldest Iterator in the Java programming language is the Enumerator predated Iterator. Java Iterator interface succeeds the enumerator iterator that was practiced in the beginning to traverse over some accessible collections like the ArrayLists.

The Java Iterator is also known as the **universal cursor** of Java as it is appropriate for all the classes of the Collection framework. The Java Iterator also helps in the operations like READ and REMOVE. When we compare the Java Iterator interface with the enumeration iterator interface, we can say that the names of the methods available in Java Iterator are more precise and straightforward to use.

## How to use Java Iterator?

When a user needs to use the Java Iterator, then it's compulsory for them to make an instance of the Iterator interface from the collection of objects they desire to traverse over. After that, the received Iterator maintains the trail of the components in the underlying collection to make sure that the user will traverse over each of the elements of the collection of objects.

If the user modifies the underlying collection while traversing over an Iterator leading to that collection, then the Iterator will typically acknowledge it and will throw an exception in the next time when the user will attempt to get the next component from the Iterator.

## Java Iterator Methods

The following figure perfectly displays the class diagram of the Java Iterator interface. It contains a total of four methods that are:

- hasNext()
- next()
- remove()
- forEachRemaining()

The **forEachRemaining()** method was added in the Java 8. Let's discuss each method in detail.

- **boolean hasNext()**: The method does not accept any parameter. It returns true if there are more elements left in the iteration. If there are no more elements left, then it will return false.  
    If there are no more elements left in the iteration, then there is no need to call the next() method. In simple words, we can say that the method is used to determine whether the next() method is to be called or not.
- **E next():** It is similar to hasNext() method. It also does not accept any parameter. It returns E, i.e., the next element in the traversal. If the iteration or collection of objects has no more elements left to iterate, then it throws the NoSuchElementException.
- **default void remove():** This method also does not require any parameters. There is no return type of this method. The main function of this method is to remove the last element returned by the iterator traversing through the underlying collection. The remove () method can be requested hardly once per the next () method call. If the iterator does not support the remove operation, then it throws the UnSupportedOperationException. It also throws the IllegalStateException if the next method is not yet called.
- **default void forEachRemaining(Consumer action):** It is the only method of Java Iterator that takes a parameter. It accepts action as a parameter. Action is nothing but that is to be performed. There is no return type of the method. This method performs the particularized operation on all of the left components of the collection until all the components are consumed or the action throws an exception. Exceptions thrown by action are delivered to the caller. If the action is null, then it throws a NullPointerException.

## Example of Java Iterator

Now it's time to execute a Java program to illustrate the advantage of the Java Iterator interface. The below code produces an ArrayList of city names. Then we initialize an iterator applying the iterator () method of the ArrayList. After that, the list is traversed to represent each element.

### Example

[](https://www.tpointtech.com/java-iterator#)[](https://www.tpointtech.com/java-iterator#)[](https://www.tpointtech.com/java-iterator#)

1. import java.io.*;  
2. import java.util.*;  

3. public class Main {  
4.     public static void main(String[] args)  
5.     {  
6.         ArrayList<String> cityNames = new ArrayList<String>();  

7.         cityNames.add("Delhi");  
8.         cityNames.add("Mumbai");  
9.         cityNames.add("Kolkata");  
10.         cityNames.add("Chandigarh");  
11.         cityNames.add("Noida");  

12.         // Iterator to iterate the cityNames  
13.         Iterator iterator = cityNames.iterator();  

14.         System.out.println("CityNames elements : ");  

15.         while (iterator.hasNext())  
16.             System.out.print(iterator.next() + " ");  

17.         System.out.println();  
18.     }  
19. }  

**Output:**

CityNames elements:
Delhi Mumbai Kolkata Chandigarh Noida