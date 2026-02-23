

![Java ArrayList class hierarchy](https://d2jdgazzki9vjm.cloudfront.net/images/arraylist.png)

ArrayList in Java is a dynamic array implementation that belongs to the Java Collections Framework. This is a big array that grows on its own as more elements are added to it.

ArrayLists come from the java.util package and are quite commonly used for their ease of use and flexibility. They offer flexibility in that you do not need to determine the size of the ArrayList at the time of its creation, which is similar to standard arrays in Java. So, it is much more flexible than the traditional array. It is like the Vector in C++.

The ArrayList in Java can also have duplicate elements. It implements the List interface so that we can use all the methods of the List interface here. The ArrayList maintains the insertion order internally.

It inherits the AbstractList class and implements [List interface](https://www.tpointtech.com/java-list).

The important points about the Java ArrayList class are:

- **Maintains Insertion Order:** Java ArrayList guarantees the order in which elements are fed into it. When going through the ArrayList with the iterating process, elements are accessed in the same sequence they were added.
- **Non-Synchronized:** Unlike some other Java collection classes (for instance, Vector), ArrayList is not synchronized. This fact implies that ArrayList is not thread-safe; therefore, concurrent modification issues might arise if multiple threads access ArrayList concurrently.
- **Supports Random Access:** ArrayList allows the implementation of fast random access operations using the elements' index positions. This is because an array structure is used for internal implementation, which ensures constant-time access to elements via index.
- **Slower Manipulation compared to LinkedList:** Manipulation operations, such as insertion and deletion, can be slower in ArrayList than in LinkedList. Thus, ArrayList has to perform the shifting of the elements when items are inserted or removed from anywhere except the end of the list. However, it is effortless to add or delete an element in a LinkedList, and no shifting will be needed.
- **Requires Wrapper Classes for Primitive Types:** ArrayList does not have a direct support for primitive data types such as `int`, `float`, and `char`. Instead, it requires the wrapper classes like `Integer`, `Float`, `Character`, etc., to hold for these primitive types. For example:

[](https://www.tpointtech.com/java-arraylist#)[](https://www.tpointtech.com/java-arraylist#)[](https://www.tpointtech.com/java-arraylist#)

1. ArrayList<Integer> integerList = new ArrayList<>();  
2. integerList.add(10); // Here, 10 is automatically boxed into an Integer object  

- **Dynamic Resizing:** ArrayList expands or contracts when adding or removing elements to meet the required new size. Due to adaptive resizing, online collections can be managed without physical resizing.
- **Capacity:** ArrayList has an initial capacity, which is the number of elements it can keep without reallocation. If the number of elements cannot fit into this capacity, the List automatically enlarges the size to accommodate the rest of the elements. Copying all the elements to the new, larger array may be involved.
- **Iterable:** ArrayList implements the `Iterable` interface. Therefore, we can easily iterate the elements using enhanced for loops or iterators.
- **Dynamic Initialization:** Java ArrayList is initialized without specifying its size. Unlike traditional arrays, where you must declare a fixed size, ArrayList dynamically adjusts its size based on the number of elements added or removed. This dynamic sizing eliminates the need to preallocate memory or worry about exceeding array bounds, providing more flexibility in managing collections.

### Hierarchy of ArrayList Class

As shown in the above diagram, the Java ArrayList class extends AbstractList class which implements the List interface. The List interface extends the [Collection](https://www.tpointtech.com/collections-in-java) and Iterable interfaces in hierarchical order.

### ArrayList Class Declaration

Let's see the declaration for java.util.ArrayList class.

[](https://www.tpointtech.com/java-arraylist#)[](https://www.tpointtech.com/java-arraylist#)[](https://www.tpointtech.com/java-arraylist#)

1. public class ArrayList<E> extends AbstractList<E> implements List<E>, RandomAccess, Cloneable, Serializable  

**public class ArrayList<E>:** Introduces the ArrayList class as a generic one with a type parameter E which is the type of the elements stored in the ArrayList. The type paramter E enables the ArrayList to store objects of any reference type.

**extends AbstractList<E>:** Means that the ArrayList class is a subclass of the AbstractList class. AbstractList implements the Skeletal aspect of the List interface, providing almost all of its methods.

**implements List<E>:** Indicates that the ArrayList class implements the List interface. The List interface describes operations for lists and extends the Collection interface.

**implements RandomAccess:** Indicates that the RandomAccess marker interface is implemented by the ArrayList class. This interface is a flag for classes that provide fast (constant time) random access to their elements.

**implements Cloneable:** States that the ArrayList class implements the Cloneable marker interface. This interface signifies that ArrayList instances can be cloned using the clone() method.

**implements Serializable:** This shows that the ArrayList class implements the Serializable marker interface. This interface makes instances of the ArrayList class serializable (converted into a byte stream) for storage or transmission.

### Constructors of the ArrayList Class

|Constructor|Description|
|---|---|
|ArrayList()|It is used to build an empty array list.|
|ArrayList(Collection<? extends E> c)|It is used to build an array list that is initialized with the elements of the collection c.|
|ArrayList(int capacity)|It is used to build an array list that has the specified initial capacity.|

### Methods of the ArrayList Class

|Method|Description|
|---|---|
|void [add](https://www.tpointtech.com/java-arraylist-add-method)(int index, E element)|It is used to insert the specified element at the specified position in a list.|
|boolean [add](https://www.tpointtech.com/java-arraylist-add-method)(E e)|It is used to append the specified element at the end of a list.|
|boolean [addAll](https://www.tpointtech.com/java-arraylist-addall-method)(Collection<? extends E> c)|It is used to append all of the elements in the specified collection to the end of this list, in the order that they are returned by the specified collection's iterator.|
|boolean [addAll](https://www.tpointtech.com/java-arraylist-addall-method)(int index, Collection<? extends E> c)|It is used to append all the elements in the specified collection, starting at the specified position of the list.|
|void [clear](https://www.tpointtech.com/java-arraylist-clear-method)()|It is used to remove all of the elements from this list.|
|void ensureCapacity(int requiredCapacity)|It is used to enhance the capacity of an ArrayList instance.|
|E get(int index)|It is used to fetch the element from the particular position of the list.|
|boolean isEmpty()|It returns true if the list is empty, otherwise false.|
|[Iterator()](https://www.tpointtech.com/java-arraylist-iterator-method)|Returns an iterator over the elements in the ArrayList in proper sequence.  <br>Allows sequential access to the elements in the ArrayList.|
|[listIterator()](https://www.tpointtech.com/java-arraylist-listiterator-method)|Returns a list iterator over the elements in the ArrayList in proper sequence.  <br>Allows bidirectional access to the elements in the ArrayList, including adding, removing, and modifying elements during iteration.|
|int lastIndexOf(Object o)|It is used to return the index in this list of the last occurrence of the specified element, or -1 if the list does not contain this element.|
|Object[] toArray()|It is used to return an array containing all of the elements in this list in the correct order.|
|<T> T[] toArray(T[] a)|It is used to return an array containing all of the elements in this list in the correct order.|
|Object clone()|It is used to return a shallow copy of an ArrayList.|
|boolean contains(Object o)|It returns true if the list contains the specified element.|
|int indexOf(Object o)|It is used to return the index in this list of the first occurrence of the specified element, or -1 if the List does not contain this element.|
|E remove(int index)|It is used to remove the element present at the specified position in the list.|
|boolean [remove](https://www.tpointtech.com/java-arraylist-remove-method)(Object o)|It is used to remove the first occurrence of the specified element.|
|boolean [removeAll](https://www.tpointtech.com/java-arraylist-removeall-method)(Collection<?> c)|It is used to remove all the elements from the list.|
|boolean removeIf(Predicate<? super E> filter)|It is used to remove all the elements from the list that satisfies the given predicate.|
|protected void [removeRange](https://www.tpointtech.com/java-arraylist-removerange-method)(int fromIndex, int toIndex)|It is used to remove all the elements lies within the given range.|
|void replaceAll(UnaryOperator<E> operator)|It is used to replace all the elements from the list with the specified element.|
|void [retainAll](https://www.tpointtech.com/java-arraylist-retainall-method)(Collection<?> c)|It is used to retain all the elements in the list that are present in the specified collection.|
|E set(int index, E element)|It is used to replace the specified element in the list, present at the specified position.|
|void sort(Comparator<? super E> c)|It is used to sort the elements of the list on the basis of the specified comparator.|
|Spliterator<E> spliterator()|It is used to create a spliterator over the elements in a list.|
|List<E> subList(int fromIndex, int toIndex)|It is used to fetch all the elements that lies within the given range.|
|int size()|It is used to return the number of elements present in the list.|
|void trimToSize()|It is used to trim the capacity of this ArrayList instance to be the list's current size.|

### Java Non-generic Vs. Generic Collection

Before JDK 1.5, the Java Collections Framework was a non-generic one, which meant that type safety wasn't guaranteed, and manual type casting was required when retrieving elements from collections.

[](https://www.tpointtech.com/java-arraylist#)[](https://www.tpointtech.com/java-arraylist#)[](https://www.tpointtech.com/java-arraylist#)

1. ArrayList list=new ArrayList();//creating old non-generic arraylist    

In this non-generic ArrayList, you could add elements of any type and the compiler did not enforce type safety. For example, you could add a String followed by an Integer without compile-time checks.

With the introduction of generics in Java 5 (JDK 1.5), the Collections Framework became generic. Generics allow you to specify the type of elements a collection can hold at compile time, providing type safety and eliminating the need for explicit type casting. Here's an example of creating a generic ArrayList:Let's see the new generic example of creating a Java collection.

[](https://www.tpointtech.com/java-arraylist#)[](https://www.tpointtech.com/java-arraylist#)[](https://www.tpointtech.com/java-arraylist#)

1. ArrayList<String> list=new ArrayList<String>();//creating new generic arraylist  

In this generic ArrayList, the type parameterspecifies that the ArrayList can only contain elements of type String. If you try to add an element of any other type, the compiler will give a compile-time error, ensuring type safety. For example, attempting to add an Integer to this ArrayList would result in a compile-time error.

### Java ArrayList Example

### Example

[](https://www.tpointtech.com/java-arraylist#)[](https://www.tpointtech.com/java-arraylist#)[](https://www.tpointtech.com/java-arraylist#)

1. import java.util.*;  
2.  public class Main{  
3.  public static void main(String args[]){  
4.   ArrayList<String> list=new ArrayList<String>();//Creating arraylist    
5.       list.add("Mango");//Adding object in arraylist    
6.       list.add("Apple");    
7.       list.add("Banana");    
8.       list.add("Grapes");    
9.       //Printing the arraylist object   
10.       System.out.println(list);  
11.  }  
12. }  

**Output:**

[Mango, Apple, Banana, Grapes]

### Iterating ArrayList using Iterator

Iterating through an ArrayList using an Iterator in Java is a common operation that allows you to traverse the list's elements sequentially. Iterators provide a safe and efficient way to access elements in a collection, especially when you want to perform operations like removing elements during iteration. Let's see an example of traversing ArrayList elements using the Iterator interface.

### Example

[](https://www.tpointtech.com/java-arraylist#)[](https://www.tpointtech.com/java-arraylist#)[](https://www.tpointtech.com/java-arraylist#)

1. import java.util.*;  
2. public class Main{  
3.  public static void main(String args[]){  
4.   ArrayList<String> list=new ArrayList<String>();//Creating arraylist  
5.   list.add("Mango");//Adding object in arraylist    
6.   list.add("Apple");    
7.   list.add("Banana");    
8.   list.add("Grapes");    
9.   //Traversing list through Iterator  
10.   Iterator itr=list.iterator();//getting the Iterator  
11.   while(itr.hasNext()){//check if iterator has the elements  
12.    System.out.println(itr.next());//printing the element and move to next  
13.   }  
14.  }  
15. }  

**Output:**

Mango
Apple
Banana
Grapes

### Iterating ArrayList using For-each loop

Iterating through an ArrayList using a for-each loop, also known as an enhanced for loop, provides a concise and readable way to access elements in the list sequentially. This approach simplifies the code and is especially useful when you only need to iterate through the elements without requiring the index or performing complex operations. Let's see an example to traverse the ArrayList elements using the for-each loop.

### Example

[](https://www.tpointtech.com/java-arraylist#)[](https://www.tpointtech.com/java-arraylist#)[](https://www.tpointtech.com/java-arraylist#)

1. import java.util.*;  
2. public class Main{  
3.  public static void main(String args[]){  
4.   ArrayList<String> list=new ArrayList<String>();//Creating arraylist  
5.   list.add("Mango");//Adding object in arraylist    
6.   list.add("Apple");    
7.   list.add("Banana");    
8.   list.add("Grapes");    
9.   //Traversing list through for-each loop  
10.   for(String fruit:list)    
11.     System.out.println(fruit);    

12.  }  
13. }  

**Output:**

Mango
Apple
Banana
Grapes

### Get and Set ArrayList

You can retrieve and modify an ArrayList using the get() and set() methods.

**Using get() method:**

- The get( ) method is used to retrieve the element at a certain index in the ArrayList.
- It takes an integer argument which specifies the element index to be brought back.
- The indexing begins with 0, which represents the initial element, and ends with size() - 1 for the last element in the ArrayList.

**Using set() method:**

- The set() method is used to replace the element at a specific index in the ArrayList with a new element.
- It takes two parameters: the index of the element to replace and the new element to be placed at that index.
- The previous element at the specified index will be overwritten by the new element.

### Example

[](https://www.tpointtech.com/java-arraylist#)[](https://www.tpointtech.com/java-arraylist#)[](https://www.tpointtech.com/java-arraylist#)

1. import java.util.*;  
2. public class Main{  
3.  public static void main(String args[]){  
4.   ArrayList<String> al=new ArrayList<String>();  
5.   al.add("Mango");  
6.   al.add("Apple");  
7.   al.add("Banana");  
8.   al.add("Grapes");  
9.   //accessing the element    
10.   System.out.println("Returning element: "+al.get(1));//it will return the 2nd element, because index starts from 0  
11.   //changing the element  
12.   al.set(1,"Dates");  
13.   //Traversing list  
14.   for(String fruit:al)    
15.     System.out.println(fruit);    

16.  }  
17. }  

**Output:**

Returning element: Apple
Mango
Dates
Banana
Grapes

### How to Sort ArrayList?

The _java.util_ package provides a utility class **Collections**, which has the static method sort(). Using the **Collections.sort()** method, we can easily sort the ArrayList.

### Example

[](https://www.tpointtech.com/java-arraylist#)[](https://www.tpointtech.com/java-arraylist#)[](https://www.tpointtech.com/java-arraylist#)

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

### Ways to iterate the elements of the collection in Java

There are various ways to traverse the collection elements:

1. By Iterator interface.
2. By for-each loop.
3. By ListIterator interface.
4. By for loop.
5. By forEach() method.
6. By forEachRemaining() method.

### Iterating Collection through remaining ways

Let's see an example to traverse the ArrayList elements through other ways

### Example

[](https://www.tpointtech.com/java-arraylist#)[](https://www.tpointtech.com/java-arraylist#)[](https://www.tpointtech.com/java-arraylist#)

1. import java.util.*;  
2. class Main{  
3.  public static void main(String args[]){  
4.     ArrayList<String> list=new ArrayList<String>();//Creating arraylist  
5.            list.add("Ravi");//Adding object in arraylist  
6.            list.add("Vijay");  
7.            list.add("Ravi");  
8.            list.add("Ajay");  

9.            System.out.println("Traversing list through List Iterator:");  
10.            //Here, element iterates in reverse order  
11.               ListIterator<String> list1=list.listIterator(list.size());  
12.               while(list1.hasPrevious())  
13.               {  
14.                   String str=list1.previous();  
15.                   System.out.println(str);  
16.               }  
17.         System.out.println("Traversing list through for loop:");  
18.            for(int i=0;i<list.size();i++)  
19.            {  
20.             System.out.println(list.get(i));     
21.            }  

22.         System.out.println("Traversing list through forEach() method:");  
23.         //The forEach() method is a new feature, introduced in Java 8.  
24.             list.forEach(a->{ //Here, we are using lambda expression  
25.                 System.out.println(a);  
26.               });  

27.             System.out.println("Traversing list through forEachRemaining() method:");  
28.               Iterator<String> itr=list.iterator();  
29.               itr.forEachRemaining(a-> //Here, we are using lambda expression  
30.               {  
31.             System.out.println(a);  
32.               });  
33.  }  
34. }  

**Output:**

Traversing list through List Iterator:
Ajay
Ravi
Vijay
Ravi
Traversing list through for loop:
Ravi
Vijay
Ravi
Ajay
Traversing list through forEach() method:
Ravi
Vijay
Ravi
Ajay
Traversing list through forEachRemaining() method:
Ravi
Vijay
Ravi
Ajay

### User-defined class objects in Java ArrayList

ArrayLists can store objects of user-defined classes, providing flexibility and scalability in managing collections of custom data types. This capability allows developers to create collections tailored to their specific application requirements.

When using user-defined class objects in ArrayLists, each element in the ArrayList represents an instance of the user-defined class. For example, consider a scenario where a Student class represents individuals with attributes such as name, age, and rollno. We can create an ArrayList to store instances of the Sudent class:

Let's see an example where we store Student class objects in an array list.

### Example

[](https://www.tpointtech.com/java-arraylist#)[](https://www.tpointtech.com/java-arraylist#)[](https://www.tpointtech.com/java-arraylist#)

1. class Student{    
2.   int rollno;    
3.   String name;    
4.   int age;    
5.   Student(int rollno,String name,int age){    
6.    this.rollno=rollno;    
7.    this.name=name;    
8.    this.age=age;    
9.   }    
10. }    

11. import java.util.*;    
12.  class ArrayList5{    
13.  public static void main(String args[]){    
14.   //Creating user-defined class objects    
15.   Student s1=new Student(101,"Sonoo",23);    
16.   Student s2=new Student(102,"Ravi",21);    
17.   Student s3=new Student(103,"Hanumat",25);    
18.   //creating arraylist    
19.   ArrayList<Student> al=new ArrayList<Student>();    
20.   al.add(s1);//adding Student class object    
21.   al.add(s2);    
22.   al.add(s3);    
23.   //Getting Iterator    
24.   Iterator itr=al.iterator();    
25.   //traversing elements of ArrayList object    
26.   while(itr.hasNext()){    
27.     Student st=(Student)itr.next();    
28.     System.out.println(st.rollno+" "+st.name+" "+st.age);    
29.   }    
30.  }    
31. }    

**Output:**

101 Sonoo 23
102 Ravi 21
103 Hanumat 25

### Java ArrayList Serialization and Deserialization Example

Serialization and deserialization in Java are processes used to convert objects into byte streams for storage or transmission and then reconstruct the objects from those byte streams, respectively. This mechanism allows objects to be saved to files, sent over networks, or stored in databases.

Let's see an example of serialising an ArrayList object and then deserialising it.

### Example

[](https://www.tpointtech.com/java-arraylist#)[](https://www.tpointtech.com/java-arraylist#)[](https://www.tpointtech.com/java-arraylist#)

1. import java.util.*;  
2. class ArrayList6 {  
3.     public static void main(String[] args) {  
4.         // Create an ArrayList and add elements to it  
5.         ArrayList<String> al = new ArrayList<String>();  
6.         al.add("Ravi");  
7.         al.add("Vijay");  
8.         al.add("Ajay");  
9.         try {  
10.             // Serialization  
11.             FileOutputStream fos = new FileOutputStream("file");  
12.             ObjectOutputStream oos = new ObjectOutputStream(fos);  
13.             oos.writeObject(al); // Write the ArrayList object to the file  
14.             fos.close();  
15.             oos.close();  
16.             // Deserialization  
17.             FileInputStream fis = new FileInputStream("file");  
18.             ObjectInputStream ois = new ObjectInputStream(fis);  
19.             // Read the ArrayList object from the file and cast it to ArrayList<String>  
20.             ArrayList list = (ArrayList) ois.readObject();  
21.             System.out.println(list); // Print the deserialized ArrayList  
22.             ois.close();  
23.             fis.close();  
24.         } catch (Exception e) {  
25.             System.out.println(e);  
26.         }  
27.     }  
28. }  

**Output:**

[Ravi, Vijay, Ajay]

### Java ArrayList example to add elements

Here, we see different ways to add an element.

### Example

[](https://www.tpointtech.com/java-arraylist#)[](https://www.tpointtech.com/java-arraylist#)[](https://www.tpointtech.com/java-arraylist#)

1. import java.util.*;  
2.  class ArrayList7{  
3.  public static void main(String args[]){  
4.   ArrayList<String> al=new ArrayList<String>();  
5.            System.out.println("Initial list of elements: "+al);  
6.            //Adding elements to the end of the list  
7.            al.add("Ravi");  
8.            al.add("Vijay");  
9.            al.add("Ajay");  
10.            System.out.println("After invoking add(E e) method: "+al);  
11.            //Adding an element at the specific position  
12.            al.add(1, "Gaurav");  
13.            System.out.println("After invoking add(int index, E element) method: "+al);  
14.            ArrayList<String> al2=new ArrayList<String>();  
15.            al2.add("Sonoo");  
16.            al2.add("Hanumat");  
17.            //Adding second list elements to the first list  
18.            al.addAll(al2);  
19.            System.out.println("After invoking addAll(Collection<? extends E> c) method: "+al);  
20.            ArrayList<String> al3=new ArrayList<String>();  
21.            al3.add("John");  
22.            al3.add("Rahul");  
23.            //Adding second list elements to the first list at specific position  
24.            al.addAll(1, al3);  
25.            System.out.println("After invoking addAll(int index, Collection<? extends E> c) method: "+al);  

26.  }  
27. }  

**Output:**

Initial list of elements: []
After invoking add(E e) method: [Ravi, Vijay, Ajay]
After invoking add(int index, E element) method: [Ravi, Gaurav, Vijay, Ajay]
After invoking addAll(Collection<? extends E> c) method:
[Ravi, Gaurav, Vijay, Ajay, Sonoo, Hanumat]
After invoking addAll(int index, Collection<? extends E> c) method:
[Ravi, John, Rahul, Gaurav, Vijay, Ajay, Sonoo, Hanumat]

### Java ArrayList example to remove elements

Here, we see different ways to remove an element.

### Example

[](https://www.tpointtech.com/java-arraylist#)[](https://www.tpointtech.com/java-arraylist#)[](https://www.tpointtech.com/java-arraylist#)

1. import java.util.*;  
2.  class ArrayList8 {  

3.         public static void main(String [] args)  
4.         {  
5.           ArrayList<String> al=new ArrayList<String>();  
6.           al.add("Ravi");    
7.           al.add("Vijay");    
8.           al.add("Ajay");   
9.           al.add("Anuj");  
10.           al.add("Gaurav");  
11.           System.out.println("An initial list of elements: "+al);   
12.           //Removing specific element from arraylist  
13.           al.remove("Vijay");  
14.           System.out.println("After invoking remove(object) method: "+al);   
15.           //Removing element on the basis of specific position  
16.           al.remove(0);  
17.           System.out.println("After invoking remove(index) method: "+al);   

18.           //Creating another arraylist  
19.           ArrayList<String> al2=new ArrayList<String>();    
20.           al2.add("Ravi");    
21.           al2.add("Hanumat");    
22.           //Adding new elements to arraylist  
23.           al.addAll(al2);  
24.           System.out.println("Updated list : "+al);   
25.           //Removing all the new elements from arraylist  
26.           al.removeAll(al2);  
27.           System.out.println("After invoking removeAll() method: "+al);   
28.           //Removing elements on the basis of specified condition  
29.           al.removeIf(str -> str.contains("Ajay"));   //Here, we are using Lambda expression   
30.           System.out.println("After invoking removeIf() method: "+al);  
31.           //Removing all the elements available in the list  
32.           al.clear();  
33.           System.out.println("After invoking clear() method: "+al);   
34.        }  
35.     }                   

**Output:**

An initial list of elements: [Ravi, Vijay, Ajay, Anuj, Gaurav]
After invoking remove(object) method: [Ravi, Ajay, Anuj, Gaurav]
After invoking remove(index) method: [Ajay, Anuj, Gaurav]
Updated list : [Ajay, Anuj, Gaurav, Ravi, Hanumat]
After invoking removeAll() method: [Ajay, Anuj, Gaurav]
After invoking removeIf() method: [Anuj, Gaurav]
After invoking clear() method: []

### Java ArrayList example of retainAll() method

retainAll() method in Java ArrayList is used to retain only the elements in the ArrayList that are also present in another collection, typically another ArrayList. In other words, it removes all elements from the current ArrayList that are not contained in the specified collection.

### Example

[](https://www.tpointtech.com/java-arraylist#)[](https://www.tpointtech.com/java-arraylist#)[](https://www.tpointtech.com/java-arraylist#)

1. import java.util.*;  
2. class Main {  
3.     public static void main(String args[]) {  
4.         // Create the first ArrayList (al) and add elements to it  
5.         ArrayList<String> al = new ArrayList<String>();  
6.         al.add("Ravi");  
7.         al.add("Vijay");  
8.         al.add("Ajay");  
9.         // Create the second ArrayList (al2) and add elements to it  
10.         ArrayList<String> al2 = new ArrayList<String>();  
11.         al2.add("Ravi");  
12.         al2.add("Hanumat");  
13.         // Retain only the elements that are present in both al and al2  
14.         al.retainAll(al2);  
15.         // Print the elements of al after retaining the elements of al2  
16.         System.out.println("Iterating the elements after retaining the elements of al2:");  
17.         Iterator itr = al.iterator();  
18.         while (itr.hasNext()) {  
19.             System.out.println(itr.next());  
20.         }  
21.     }  
22. }  

**Output:**

iterating the elements after retaining the elements of al2
Ravi

### Java ArrayList example of isEmpty() method

isEmpty() method in Java ArrayList is used to check if the ArrayList is empty, i.e., it returns true if the ArrayList contains no elements and false otherwise.

### Example

[](https://www.tpointtech.com/java-arraylist#)[](https://www.tpointtech.com/java-arraylist#)[](https://www.tpointtech.com/java-arraylist#)

1. import java.util.*;  
2. class Main {  
3.     public static void main(String[] args) {  
4.         // Create an ArrayList  
5.         ArrayList<String> al = new ArrayList<String>();  
6.         // Check if the ArrayList is empty  
7.         System.out.println("Is ArrayList Empty: " + al.isEmpty());  
8.         // Add elements to the ArrayList  
9.         al.add("Ravi");  
10.         al.add("Vijay");  
11.         al.add("Ajay");  
12.         // Display a message after insertion  
13.         System.out.println("After Insertion");  
14.         // Check if the ArrayList is empty after insertion  
15.         System.out.println("Is ArrayList Empty: " + al.isEmpty());  
16.     }  
17. }  

**Output:**

Is ArrayList Empty: true
After Insertion
Is ArrayList Empty: false

### Java ArrayList Example: Book

Let's see an ArrayList example where we are adding books to the list and printing all the books.

### Example

[](https://www.tpointtech.com/java-arraylist#)[](https://www.tpointtech.com/java-arraylist#)[](https://www.tpointtech.com/java-arraylist#)

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
28.         System.out.println(b.id+" "+b.name+" "+b.author+" "+b.publisher+" "+b.quantity);  
29.     }  
30. }  
31. }  

**Output:**

101 Let us C Yashwant Kanetkar BPB 8
102 Data Communications and Networking Forouzan Mc Graw Hill 4
103 Operating System Galvin Wiley 6

### Size and Capacity of an ArrayList

Size and capacity of an array list are the two terms that beginners find confusing. ArrayList handles a variable size of elements through elements being added or removed, making it flexible on collections. The length of an ArrayList refers to the number of elements to be stored in it, which you can obtain by calling the size() method. This size is automatically adjusted when elements are added or removed.

An Array List capacity means the maximum number of elements it can keep before having to be resized. Initially, an ArrayList's capacity is defined by the constructor used to create it, or by the default capacity in the event no constructor is defined. When the total numbers of objects in ArrayList exceed the current capacity, the ArrayList automatically reallocates and increases its capacity to carry more objects, hence efficient storage and whimpering. The size of the ArrayList can be retrieved using the capacity() method.

Let's understand it in this section with the help of some examples. Consider the following code snippet.

### Example

[](https://www.tpointtech.com/java-arraylist#)[](https://www.tpointtech.com/java-arraylist#)[](https://www.tpointtech.com/java-arraylist#)

1. import java.util.*;  
2. public class Main {     
3.     public static void main(String[] args) throws Exception {       
4.         // Create an ArrayList of Integer type  
5.         ArrayList<Integer> al = new ArrayList<Integer>();            
6.         // Print the size of the ArrayList using the size() method  
7.         System.out.println("The size of the array is: " + al.size());    
8.     }    
9. }  

**Output:**

The size of the array is: 0

**Explanation:** The output makes sense as we have not done anything with the array list. Now observe the following program.

### Example

[](https://www.tpointtech.com/java-arraylist#)[](https://www.tpointtech.com/java-arraylist#)[](https://www.tpointtech.com/java-arraylist#)

1. import java.util.*;  
2. public class Main {     
3.     public static void main(String[] args) throws Exception {          
4.         // Create an ArrayList of Integer type with an initial capacity of 10  
5.         ArrayList<Integer> al = new ArrayList<Integer>(10);         
6.         // Print the size of the ArrayList using the size() method  
7.         System.out.println("The size of the array is: " + al.size());    
8.     }    
9. }  

**Output:**

The size of the array is: 0

**Explanation:** We see that the size is still 0, and the reason behind this is the number 10 represents the capacity no the size. In fact, the size represents the total number of elements present in the array. As we have not added any element, therefore, the size of the array list is zero in both programs.

Imagine you have a box called an ArrayList. This box has a special property called capacity, which tells you how many items it can hold. Let's say the capacity of this box is 10.

Now, you start putting items into this box, like toys. Every time you put a toy inside, you check if the number of toys in the box (that's called the size) is equal to the capacity. If it is, it means the box is full, and you need a bigger box to put more toys in.

So, until you've put 10 toys in the box, the capacity stays at 10. But as soon as you try to put an 11th toy inside, you realize the box is full, and you need a bigger box. In our case, since the box can only hold 10 toys, you need to get a new box with a bigger capacity.

Now, remember, there are two scenarios:

In the first scenario, you start with a default box that can hold 10 toys. You don't specify the capacity; it's just the default.

In the second scenario, you explicitly say, "I want a box with a capacity of 10 toys." So, right from the start, you get a box that can hold exactly 10 toys.

But the process is the same in both cases: you keep adding toys, and if the box gets full, you get a bigger one.

Note: There is no standard method to tell how the capacity increases in the array list. In fact, the way the capacity increases varies from one GDK version to the other version. Therefore, it is required to check how capacity increases code is implemented in the GDK. There is no pre-defined method in the ArrayList class that returns the capacity of the array list. Therefore, for better understanding, use the capacity() method of the Vector class. The logic of the size and capacity are the same in the ArrayList and Vector classes.