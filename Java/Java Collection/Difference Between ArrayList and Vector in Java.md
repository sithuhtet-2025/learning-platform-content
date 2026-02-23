## ArrayList

ArrayList in Java is a dynamic array implementation that belongs to the Java Collections Framework. This is a big array that grows on its own as more elements are added to it.

ArrayList class is defined in java.util package is quite commonly used for its ease of use and flexibility. They offer flexibility in that you do not need to determine the size of the ArrayList at the time of its creation, which is similar to standard arrays in Java. So, it is much more flexible than the traditional array.

The ArrayList in Java can also have duplicate elements. It implements the List interface so that we can use all the methods of the List interface here. The ArrayList maintains the insertion order internally.

To read more [Java ArrayList](https://www.tpointtech.com/java-arraylist)

## Vector

A **Vector** is like a dynamic array that can grow or shrink its size. Unlike an array, we can store n-number of elements in it as there is no size limit. It is a part of the Java Collection framework since Java 1.2. It belongs to java.util package and implements the _List_ interface so that we can use all the methods of the List interface here.

It is recommended to use the Vector class in the thread-safe implementation only. If you do not need to use the thread-safe implementation, you should use the ArrayList; the ArrayList will perform better in such a case.

It is similar to the ArrayList, but with two differences-

- Vector is synchronized.
- Java Vector contains many legacy methods that are not part of the Collections framework.

To read more [Java Vector](https://www.tpointtech.com/java-vector)

## ArrayList Vs. Vector

|Feature|ArrayList|Vector|
|---|---|---|
|**Thread Safety**|ArrayList is not synchronized, which means multiple threads can access it at the same time. In a multithreaded setup, one thread can add elements while another might remove them.|The vector is synchronized, so only one thread can access it at a time. If one thread is working on it, others must wait their turn. It's safer but also slower in multithreaded environments.|
|**Growth**|ArrayList grows dynamically. When it runs out of space, it increases its size by 50% of its current capacity.|Vector also resizes automatically, but it grows by doubling its size, which can lead to more memory being used than necessary.|
|**Performance**|ArrayList performs faster for most operations, like adding, searching, or deleting elements. Since it does not have built-in synchronization, there's no delay from locking, which means better speed.|Vector is slower in comparison. Because it locks the whole structure during operations, other threads have to wait. The thread-safety comes at the cost of performance.|
|**Legacy Status**|ArrayList is modern, introduced in Java 1.2, and is part of the Collections Framework. It's commonly used in new Java programs.|Vector is an older class, around since Java 1.0. It's considered a legacy class and is rarely used in modern applications.|
|**Element Traversal**|ArrayList uses an iterator to loop through elements, which is how most modern Java collections work.|Vector supports both iterator and Enumeration, which is an older way of looping through elements in Java.|

  
![ArrayList vs Vector](https://images.tpointtech.com/images/arraylist-vs-vector.jpg)

## ArrayList Example

Let's see a simple example where we are using ArrayList to store and traverse the elements.

### Example

[](https://www.tpointtech.com/difference-between-arraylist-and-vector#)[](https://www.tpointtech.com/difference-between-arraylist-and-vector#)[](https://www.tpointtech.com/difference-between-arraylist-and-vector#)

1. import java.util.*;    
2. class Main{    
3.  public static void main(String args[]){    

4.   List<String> al=new ArrayList<String>();//creating an ArrayList  
5.   al.add("Sonoo");//adding object in ArrayList  
6.   al.add("Michael");    
7.   al.add("James");    
8.   al.add("Andy");    
9.   //traversing elements using Iterator  
10.   Iterator itr=al.iterator();  
11.   while(itr.hasNext()){  
12.    System.out.println(itr.next());  
13.   }    
14.  }    
15. }    

**Output:**

Sonoo
Michael
James
Andy

## Vector Example

Let's see a simple example of a Java Vector class that uses the Enumeration interface.

### Example

[](https://www.tpointtech.com/difference-between-arraylist-and-vector#)[](https://www.tpointtech.com/difference-between-arraylist-and-vector#)[](https://www.tpointtech.com/difference-between-arraylist-and-vector#)

1. import java.util.*;        
2. public class Main   {        
3.  public static void main(String args[]){        
4.   Vector<String> v=new Vector<String>();//creating vector    
5. v.add("Andrew");//method of Collection    
6.   v.addElement("Peter");//method of Vector    
7.   v.addElement("Jack");    
8.   //traversing elements using Enumeration    
9.   Enumeration e=v.elements();    
10.   while(e.hasMoreElements()){    
11.    System.out.println(e.nextElement());    
12.   }    
13.  }        
14. }            

**Output:**

Andrew
Peter
Jack