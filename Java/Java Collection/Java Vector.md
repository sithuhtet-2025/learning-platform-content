**Vector** is like the _dynamic array_ which can grow or shrink its size. Unlike array, we can store n-number of elements in it as there is no size limit. It is a part of Java Collection framework since Java 1.2. It is found in the java.util package and implements the _List_ interface, so we can use all the methods of List interface here.

It is recommended to use the Vector class in the thread-safe implementation only. If you don't need to use the thread-safe implementation, you should use the ArrayList, the ArrayList will perform better in such case.

The Iterators returned by the Vector class are _fail-fast_. In case of concurrent modification, it fails and throws the ConcurrentModificationException.

It is similar to the ArrayList, but with two differences-

- Vector is synchronized.
- Java Vector contains many legacy methods that are not the part of a collections framework.

## Java Vector class Declaration

[](https://www.tpointtech.com/java-vector#)[](https://www.tpointtech.com/java-vector#)[](https://www.tpointtech.com/java-vector#)

1. public class Vector<E>  
2. extends Object<E>  
3. implements List<E>, Cloneable, Serializable  

## Java Vector Constructors

Vector class supports four types of constructors. These are given below:

|SN|Constructor|Description|
|---|---|---|
|1)|vector()|It constructs an empty vector with the default size as 10.|
|2)|vector(int initialCapacity)|It constructs an empty vector with the specified initial capacity and with its capacity increment equal to zero.|
|3)|vector(int initialCapacity, int capacityIncrement)|It constructs an empty vector with the specified initial capacity and capacity increment.|
|4)|Vector( Collection<? extends E> c)|It constructs a vector that contains the elements of a collection c.|

### Java Vector Methods

The following are the list of Vector class methods:

|SN|Method|Description|
|---|---|---|
|1)|[add()](https://www.tpointtech.com/java-vector-add-method)|It is used to append the specified element in the given vector.|
|2)|[addAll()](https://www.tpointtech.com/java-vector-addall-method)|It is used to append all of the elements in the specified collection to the end of this Vector.|
|3)|[addElement()](https://www.tpointtech.com/java-vector-addelement-method)|It is used to append the specified component to the end of this vector. It increases the vector size by one.|
|4)|[capacity()](https://www.tpointtech.com/java-vector-capacity-method)|It is used to get the current capacity of this vector.|
|5)|[clear()](https://www.tpointtech.com/java-vector-clear-method)|It is used to delete all of the elements from this vector.|
|6)|[clone()](https://www.tpointtech.com/java-vector-clone-method)|It returns a clone of this vector.|
|7)|[contains()](https://www.tpointtech.com/java-vector-contains-method)|It returns true if the vector contains the specified element.|
|8)|[containsAll()](https://www.tpointtech.com/java-vector-containsall-method)|It returns true if the vector contains all of the elements in the specified collection.|
|9)|[copyInto()](https://www.tpointtech.com/java-vector-copyinto-method)|It is used to copy the components of the vector into the specified array.|
|10)|[elementAt()](https://www.tpointtech.com/java-vector-elementat-method)|It is used to get the component at the specified index.|
|11)|[elements()](https://www.tpointtech.com/java-vector-elements-method)|It returns an enumeration of the components of a vector.|
|12)|[ensureCapacity()](https://www.tpointtech.com/java-vector-ensurecapacity-method)|It is used to increase the capacity of the vector which is in use, if necessary. It ensures that the vector can hold at least the number of components specified by the minimum capacity argument.|
|13)|[equals()](https://www.tpointtech.com/java-vector-equals-method)|It is used to compare the specified object with the vector for equality.|
|14)|[firstElement()](https://www.tpointtech.com/java-vector-firstelement-method)|It is used to get the first component of the vector.|
|15)|[forEach()](https://www.tpointtech.com/java-vector-foreach-method)|It is used to perform the given action for each element of the Iterable until all elements have been processed or the action throws an exception.|
|16)|[get()](https://www.tpointtech.com/java-vector-get-method)|It is used to get an element at the specified position in the vector.|
|17)|[hashCode()](https://www.tpointtech.com/java-vector-hashcode-method)|It is used to get the hash code value of a vector.|
|18)|[indexOf()](https://www.tpointtech.com/java-vector-indexof-method)|It is used to get the index of the first occurrence of the specified element in the vector. It returns -1 if the vector does not contain the element.|
|19)|[insertElementAt()](https://www.tpointtech.com/java-vector-insertelementat-method)|It is used to insert the specified object as a component in the given vector at the specified index.|
|20)|[isEmpty()](https://www.tpointtech.com/java-vector-isempty-method)|It is used to check if this vector has no components.|
|21)|[iterator()](https://www.tpointtech.com/java-vector-iterator-method)|It is used to get an iterator over the elements in the list in proper sequence.|
|22)|[lastElement()](https://www.tpointtech.com/java-vector-lastelement-method)|It is used to get the last component of the vector.|
|23)|[lastIndexOf()](https://www.tpointtech.com/java-vector-lastindexof-method)|It is used to get the index of the last occurrence of the specified element in the vector. It returns -1 if the vector does not contain the element.|
|24)|listIterator()|It is used to get a list iterator over the elements in the list in proper sequence.|
|25)|[remove()](https://www.tpointtech.com/java-vector-remove-method)|It is used to remove the specified element from the vector. If the vector does not contain the element, it is unchanged.|
|26)|[removeAll()](https://www.tpointtech.com/java-vector-removeall-method)|It is used to delete all the elements from the vector that are present in the specified collection.|
|27)|[removeAllElements()](https://www.tpointtech.com/java-vector-removeallelements-method)|It is used to remove all elements from the vector and set the size of the vector to zero.|
|28)|[removeElement()](https://www.tpointtech.com/java-vector-removeelement-method)|It is used to remove the first (lowest-indexed) occurrence of the argument from the vector.|
|29)|[removeElementAt()](https://www.tpointtech.com/java-vector-removeelementat-method)|It is used to delete the component at the specified index.|
|30)|removeIf()|It is used to remove all of the elements of the collection that satisfy the given predicate.|
|31)|removeRange()|It is used to delete all of the elements from the vector whose index is between fromIndex, inclusive and toIndex, exclusive.|
|32)|[replaceAll()](https://www.tpointtech.com/java-vector-replaceall-method)|It is used to replace each element of the list with the result of applying the operator to that element.|
|33)|[retainAll()](https://www.tpointtech.com/java-vector-retainall-method)|It is used to retain only that element in the vector which is contained in the specified collection.|
|34)|set()|It is used to replace the element at the specified position in the vector with the specified element.|
|35)|setElementAt()|It is used to set the component at the specified index of the vector to the specified object.|
|36)|setSize()|It is used to set the size of the given vector.|
|37)|size()|It is used to get the number of components in the given vector.|
|38)|sort()|It is used to sort the list according to the order induced by the specified Comparator.|
|39)|spliterator()|It is used to create a late-binding and fail-fast Spliterator over the elements in the list.|
|40)|subList()|It is used to get a view of the portion of the list between fromIndex, inclusive, and toIndex, exclusive.|
|41)|toArray()|It is used to get an array containing all of the elements in this vector in correct order.|
|42)|toString()|It is used to get a string representation of the vector.|
|43)|trimToSize()|It is used to trim the capacity of the vector to the vector's current size.|

## Java Vector Example

### Example

[](https://www.tpointtech.com/java-vector#)[](https://www.tpointtech.com/java-vector#)[](https://www.tpointtech.com/java-vector#)

1. import java.util.*;  
2. public class Main {  
3.        public static void main(String args[]) {  
4.           //Create a vector  
5.           Vector<String> vec = new Vector<String>();  
6.           //Adding elements using add() method of List  
7.           vec.add("Tiger");  
8.           vec.add("Lion");  
9.           vec.add("Dog");  
10.           vec.add("Elephant");  
11.           //Adding elements using addElement() method of Vector  
12.           vec.addElement("Rat");  
13.           vec.addElement("Cat");  
14.           vec.addElement("Deer");  

15.           System.out.println("Elements are: "+vec);  
16.        }  
17. }  

**Output:**

Elements are: [Tiger, Lion, Dog, Elephant, Rat, Cat, Deer]

## Java Vector Example 2

### Example

[](https://www.tpointtech.com/java-vector#)[](https://www.tpointtech.com/java-vector#)[](https://www.tpointtech.com/java-vector#)

1. import java.util.*;  
2. public class Main {  
3.        public static void main(String args[]) {  
4.           //Create an empty vector with initial capacity 4  
5.           Vector<String> vec = new Vector<String>(4);  
6.           //Adding elements to a vector  
7.           vec.add("Tiger");  
8.           vec.add("Lion");  
9.           vec.add("Dog");  
10.           vec.add("Elephant");  
11.           //Check size and capacity  
12.           System.out.println("Size is: "+vec.size());  
13.           System.out.println("Default capacity is: "+vec.capacity());  
14.           //Display Vector elements  
15.           System.out.println("Vector element is: "+vec);  
16.           vec.addElement("Rat");  
17.           vec.addElement("Cat");  
18.           vec.addElement("Deer");  
19.           //Again check size and capacity after two insertions  
20.           System.out.println("Size after addition: "+vec.size());  
21.           System.out.println("Capacity after addition is: "+vec.capacity());  
22.           //Display Vector elements again  
23.           System.out.println("Elements are: "+vec);  
24.           //Checking if Tiger is present or not in this vector         
25.             if(vec.contains("Tiger"))  
26.             {  
27.                System.out.println("Tiger is present at the index " +vec.indexOf("Tiger"));  
28.             }  
29.             else  
30.             {  
31.                System.out.println("Tiger is not present in the list.");  
32.             }  
33.             //Get the first element  
34.           System.out.println("The first animal of the vector is = "+vec.firstElement());   
35.           //Get the last element  
36.           System.out.println("The last animal of the vector is = "+vec.lastElement());   
37.        }  
38. }  

**Output:**

Size is: 4
Default capacity is: 4
Vector element is: [Tiger, Lion, Dog, Elephant]
Size after addition: 7
Capacity after addition is: 8
Elements are: [Tiger, Lion, Dog, Elephant, Rat, Cat, Deer]
Tiger is present at the index 0
The first animal of the vector is = Tiger
The last animal of the vector is = Deer

## Java Vector Example 3

### Example

[](https://www.tpointtech.com/java-vector#)[](https://www.tpointtech.com/java-vector#)[](https://www.tpointtech.com/java-vector#)

1. import java.util.*;  
2. public class Main {  
3.        public static void main(String args[]) {  
4.         //Create an empty Vector        
5.         Vector<Integer> in = new Vector<>();  
6.         //Add elements in the vector  
7.         in.add(100);  
8.         in.add(200);  
9.         in.add(300);  
10.         in.add(200);  
11.         in.add(400);  
12.         in.add(500);  
13.         in.add(600);  
14.         in.add(700);  
15.         //Display the vector elements  
16.         System.out.println("Values in vector: " +in);  
17.         //use remove() method to delete the first occurence of an element  
18.         System.out.println("Remove first occourence of element 200: "+in.remove((Integer)200));  
19.         //Display the vector elements afre remove() method  
20.         System.out.println("Values in vector: " +in);  
21.         //Remove the element at index 4  
22.         System.out.println("Remove element at index 4: " +in.remove(4));  
23.         System.out.println("New Value list in vector: " +in);  
24.         //Remove an element  
25.         in.removeElementAt(5);        
26.         //Checking vector and displays the element  
27.         System.out.println("Vector element after removal: " +in);  
28.         //Get the hashcode for this vector  
29.         System.out.println("Hash code of this vector = "+in.hashCode());  
30.         //Get the element at specified index  
31.         System.out.println("Element at index 1 is = "+in.get(1));  
32.           }  
33. }  

**Output:**

Values in vector: [100, 200, 300, 200, 400, 500, 600, 700]
Remove first occourence of element 200: true
Values in vector: [100, 300, 200, 400, 500, 600, 700]
Remove element at index 4: 500
New Value list in vector: [100, 300, 200, 400, 600, 700]
Vector element after removal: [100, 300, 200, 400, 600]
Hash code of this vector = 130123751
Element at index 1 is = 300