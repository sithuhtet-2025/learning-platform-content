# 

Last Updated : 12 Feb 2026

**Java**, a versatile and widely-used programming language, offers a robust set of data structures to handle **collections** of objects efficiently. One of the fundamental data structures in Java is the List interface that provides an ordered collection of elements with dynamic sizing. It is a part of **Java Collections Framework,** provides a versatile and ordered way to handle collections of elements. In this section, we will explore the **features, implementations**, and best practices associated with **Java Lists**.

**List** in Java provides the facility to maintain the _ordered collection_. It contains the index-based methods to insert, update, delete and search the elements. It can have the duplicate elements also. We can also store the null elements in the list.

The List interface is found in the java.util package and inherits the Collection interface. It is a factory of ListIterator interface. Through the ListIterator, we can iterate the list in forward and backward directions. The implementation classes of List interface are **ArrayList, LinkedList, Stack**, and Vector. The ArrayList and LinkedList are widely used in Java programming. The Vector class is deprecated since Java 5.

### List Interface Declaration

[](https://www.tpointtech.com/java-list#)[](https://www.tpointtech.com/java-list#)[](https://www.tpointtech.com/java-list#)

1. public interface List<E> extends Collection<E>  

### Java List Class Methods

|Method|Description|
|---|---|
|void add(int index, E element)|It is used to insert the specified element at the specified position in a list.|
|boolean add(E e)|It is used to append the specified element at the end of a list.|
|boolean addAll(Collection<? extends E> c)|It is used to append all of the elements in the specified collection to the end of a list.|
|boolean addAll(int index, Collection<? extends E> c)|It is used to append all the elements in the specified collection, starting at the specified position of the list.|
|void clear()|It is used to remove all of the elements from this list.|
|boolean equals(Object o)|It is used to compare the specified object with the elements of a list.|
|int hashcode()|It is used to return the hash code value for a list.|
|E get(int index)|It is used to fetch the element from the particular position of the list.|
|boolean isEmpty()|It returns true if the list is empty, otherwise false.|
|int lastIndexOf(Object o)|It is used to return the index in this list of the last occurrence of the specified element, or -1 if the list does not contain this element.|
|Object[] toArray()|It is used to return an array containing all of the elements in this list in the correct order.|
|<T> T[] toArray(T[] a)|It is used to return an array containing all of the elements in this list in the correct order.|
|boolean contains(Object o)|It returns true if the list contains the specified element|
|boolean containsAll(Collection<?> c)|It returns true if the list contains all the specified element|
|int indexOf(Object o)|It is used to return the index in this list of the first occurrence of the specified element, or -1 if the List does not contain this element.|
|E remove(int index)|It is used to remove the element present at the specified position in the list.|
|boolean remove(Object o)|It is used to remove the first occurrence of the specified element.|
|boolean removeAll(Collection<?> c)|It is used to remove all the elements from the list.|
|void replaceAll(UnaryOperator<E> operator)|It is used to replace all the elements from the list with the specified element.|
|void retainAll(Collection<?> c)|It is used to retain all the elements in the list that are present in the specified collection.|
|E set(int index, E element)|It is used to replace the specified element in the list, present at the specified position.|
|void sort(Comparator<? super E> c)|It is used to sort the elements of the list on the basis of specified comparator.|
|Spliterator<E> spliterator()|It is used to create spliterator over the elements in a list.|
|List<E> subList(int fromIndex, int toIndex)|It is used to fetch all the elements lies within the given range.|
|int size()|It is used to return the number of elements present in the list.|

### How to create List?

The ArrayList and LinkedList classes provide the implementation of List interface. Let's see the examples to create the List:

[](https://www.tpointtech.com/java-list#)[](https://www.tpointtech.com/java-list#)[](https://www.tpointtech.com/java-list#)

1. //Creating a List of type String using ArrayList  
2. List<String> list=new ArrayList<String>();  

3. //Creating a List of type Integer using ArrayList  
4. List<Integer> list=new ArrayList<Integer>();  

5. //Creating a List of type Book using ArrayList  
6. List<Book> list=new ArrayList<Book>();  

7. //Creating a List of type String using LinkedList  
8. List<String> list=new LinkedList<String>();  

In short, we can create the List of any type. The ArrayList<T> and LinkedList<T> classes are used to specify the type. Here, T denotes the type.

## Common List Operations

Here are some essential operations we can perform on Java Lists.

**1. Adding Elements:**

[](https://www.tpointtech.com/java-list#)[](https://www.tpointtech.com/java-list#)[](https://www.tpointtech.com/java-list#)

1. list.add("Java");  
2. list.add(1, "JavaScript");  

**2. Removing Elements:**

[](https://www.tpointtech.com/java-list#)[](https://www.tpointtech.com/java-list#)[](https://www.tpointtech.com/java-list#)

1. list.remove("Java");  
2. list.remove(0);  

**3. Accessing Elements:**

[](https://www.tpointtech.com/java-list#)[](https://www.tpointtech.com/java-list#)[](https://www.tpointtech.com/java-list#)

1. String firstElement = list.get(0);  
2. int index = list.indexOf("JavaScript");  

**4. Iterate Over List:**

[](https://www.tpointtech.com/java-list#)[](https://www.tpointtech.com/java-list#)[](https://www.tpointtech.com/java-list#)

1. for (String element : list)   
2. {  
3.     System.out.println(element);  
4. }  

## Java List Example

Let's see a simple example of List where we are using the ArrayList class as the implementation.

### Example

[](https://www.tpointtech.com/java-list#)[](https://www.tpointtech.com/java-list#)[](https://www.tpointtech.com/java-list#)

1. import java.util.*;  
2. public class Main{  
3. public static void main(String args[]){  
4.  //Creating a List  
5.  List<String> list=new ArrayList<String>();  
6.  //Adding elements in the List  
7.  list.add("Mango");  
8.  list.add("Apple");  
9.  list.add("Banana");  
10.  list.add("Grapes");  
11.  //Iterating the List element using for-each loop  
12.  for(String fruit:list)  
13.   System.out.println(fruit);  

14. }  
15. }  

**Output:**

Mango
Apple
Banana
Grapes

### How to convert Array to List

Converting an array to a list in Java is a common operation. We can convert the Array to List by traversing the array and adding the element in list one by one using the List.add() method. It is a common approach that we use. Beside this there are some other approaches we can use as follows:

**Method 1:** Using Arrays.asList()

**Method 2:** Using ArrayList Constructor

### Example

[](https://www.tpointtech.com/java-list#)[](https://www.tpointtech.com/java-list#)[](https://www.tpointtech.com/java-list#)

1. import java.util.*;  
2. public class Main{  
3. public static void main(String args[]){  
4. //Creating Array  
5. String[] array={"Java","Python","PHP","C++"};  
6. System.out.println("Printing Array: "+Arrays.toString(array));  
7. //Converting Array to List  
8. List<String> list=new ArrayList<String>();  
9. for(String lang:array){  
10. list.add(lang);  
11. }  
12. System.out.println("Printing List: "+list);  

13. }  
14. }  

**Output:**

Printing Array: [Java, Python, PHP, C++]
Printing List: [Java, Python, PHP, C++]

### How to convert List to Array

We can convert the List to Array by calling the List.toArray() method. Let's see a simple example to convert list elements into array.

### Example

[](https://www.tpointtech.com/java-list#)[](https://www.tpointtech.com/java-list#)[](https://www.tpointtech.com/java-list#)

1. import java.util.*;  
2. public class Main{  
3. public static void main(String args[]){  
4.  List<String> fruitList = new ArrayList<>();    
5.  fruitList.add("Mango");    
6.  fruitList.add("Banana");    
7.  fruitList.add("Apple");    
8.  fruitList.add("Strawberry");    
9.  //Converting ArrayList to Array  
10.  String[] array = fruitList.toArray(new String[fruitList.size()]);    
11.  System.out.println("Printing Array: "+Arrays.toString(array));  
12.  System.out.println("Printing List: "+fruitList);  
13. }  
14. }  

**Output:**

Printing Array: [Mango, Banana, Apple, Strawberry]
Printing List: [Mango, Banana, Apple, Strawberry]

### Get and Set Element in List

The _get() method_ returns the element at the given index, whereas the _set() method_ changes or replaces the element.

### Example

[](https://www.tpointtech.com/java-list#)[](https://www.tpointtech.com/java-list#)[](https://www.tpointtech.com/java-list#)

1. import java.util.*;  
2. public class Main{  
3.  public static void main(String args[]){  
4.  //Creating a List  
5.  List<String> list=new ArrayList<String>();  
6.  //Adding elements in the List  
7.  list.add("Mango");  
8.  list.add("Apple");  
9.  list.add("Banana");  
10.  list.add("Grapes");  
11.  //accessing the element    
12.  System.out.println("Returning element: "+list.get(1));//it will return the 2nd element, because index starts from 0  
13.  //changing the element  
14.  list.set(1,"Dates");  
15.  //Iterating the List element using for-each loop  
16.  for(String fruit:list)  
17.   System.out.println(fruit);  

18.  }  
19. }  

**Output:**

Returning element: Apple
Mango
Dates
Banana
Grapes

## How to Sort a List?

Sorting a list in Java can be done using the Collections.sort() method or by using the List.sort() method introduced in Java 8. Here are examples for both approaches:

### Example

[](https://www.tpointtech.com/java-list#)[](https://www.tpointtech.com/java-list#)[](https://www.tpointtech.com/java-list#)

1. import java.util.*;  
2. class Main{  
3.  public static void main(String args[]){  
4.   //Creating a list of fruits  
5.   List<String> list1=new ArrayList<String>();  
6.   list1.add("Mango");  
7.   list1.add("Apple");  
8.   list1.add("Banana");  
9.   list1.add("Grapes");  
10.   //Sorting the list  
11.   Collections.sort(list1);  
12.    //Traversing list through the for-each loop  
13.   for(String fruit:list1)  
14.     System.out.println(fruit);  

15.  System.out.println("Sorting numbers...");  
16.   //Creating a list of numbers  
17.   List<Integer> list2=new ArrayList<Integer>();  
18.   list2.add(21);  
19.   list2.add(11);  
20.   list2.add(51);  
21.   list2.add(1);  
22.   //Sorting the list  
23.   Collections.sort(list2);  
24.    //Traversing list through the for-each loop  
25.   for(Integer number:list2)  
26.     System.out.println(number);  
27.  }  

28. }  

**Output:**

Apple
Banana
Grapes
Mango
Sorting numbers...
1
11
21
51

## Java ListIterator Interface

ListIterator Interface is used to traverse the element in a backward and forward direction.

### ListIterator Interface declaration

[](https://www.tpointtech.com/java-list#)[](https://www.tpointtech.com/java-list#)[](https://www.tpointtech.com/java-list#)

1. public interface ListIterator<E> extends Iterator<E>  

### Methods of Java ListIterator Interface

|Method|Description|
|---|---|
|**void add(E e)**|The method inserts the specified element into the list.|
|**boolean hasNext()**|The method returns true if the list iterator has more elements while traversing the list in the forward direction.|
|**E next()**|The method returns the next element in the list and advances the cursor position.|
|**int nextIndex()**|The method returns the index of the element that would be returned by a subsequent call to next()|
|**boolean hasPrevious()**|The method returns true if this list iterator has more elements while traversing the list in the reverse direction.|
|**E previous()**|The method returns the previous element in the list and moves the cursor position backward.|
|**E previousIndex()**|The method returns the index of the element that would be returned by a subsequent call to previous().|
|**void remove()**|The method removes the last element from the list that was returned by next() or previous() methods|
|**void set(E e)**|The method replaces the last element returned by next() or previous() methods with the specified element.|

### Example of ListIterator Interface

### Example

[](https://www.tpointtech.com/java-list#)[](https://www.tpointtech.com/java-list#)[](https://www.tpointtech.com/java-list#)

1. import java.util.*;  
2. public class Main{  
3. public static void main(String args[]){  
4. List<String> al=new ArrayList<String>();    
5.         al.add("Amit");    
6.         al.add("Vijay");    
7.         al.add("Kumar");    
8.         al.add(1,"Sachin");    
9.         ListIterator<String> itr=al.listIterator();    
10.         System.out.println("Traversing elements in forward direction");    
11.         while(itr.hasNext()){    

12.         System.out.println("index:"+itr.nextIndex()+" value:"+itr.next());    
13.         }    
14.         System.out.println("Traversing elements in backward direction");    
15.         while(itr.hasPrevious()){    

16.         System.out.println("index:"+itr.previousIndex()+" value:"+itr.previous());    
17.         }    
18. }  
19. }  

**Output:**

Traversing elements in forward direction
index:0 value:Amit
index:1 value:Sachin
index:2 value:Vijay
index:3 value:Kumar
Traversing elements in backward direction
index:3 value:Kumar
index:2 value:Vijay
index:1 value:Sachin
index:0 value:Amit

### Example of List: Book

Let's see an example of List where we are adding the Books.

### Example

[](https://www.tpointtech.com/java-list#)[](https://www.tpointtech.com/java-list#)[](https://www.tpointtech.com/java-list#)

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
16.     //Creating list of Books  
17.     List<Book> list=new ArrayList<Book>();  
18.     //Creating Books  
19.     Book b1=new Book(101,"Let us C","Yashwant Kanetkar","BPB",8);  
20.     Book b2=new Book(102,"Data Communications and Networking","Forouzan","Mc Graw Hill",4);  
21.     Book b3=new Book(103,"Operating System","Galvin","Wiley",6);  
22.     //Adding Books to list  
23.     list.add(b1);  
24.     list.add(b2);  
25.     list.add(b3);  
26.     //Traversing list  
27.     for(Book b:list){  
28.     System.out.println(b.id+" "+b.name+" "+b.author+" "+b.publisher+" "+b.quantity);  
29.     }  
30. }  
31. }  

**Output:**

101 Let us C Yashwant Kanetkar BPB 8
102 Data Communications and Networking Forouzan Mc Graw Hill 4
103 Operating System Galvin Wiley 6