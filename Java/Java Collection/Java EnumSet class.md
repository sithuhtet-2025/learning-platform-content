Java EnumSet class is the specialized Set implementation for use with enum types. It inherits AbstractSet class and implements the Set interface.

### EnumSet class hierarchy

The hierarchy of EnumSet class is given in the figure given below.

![EnumSet class hierarchy](https://www.tpointtech.com/java-enumset)

## EnumSet class declaration

Let's see the declaration for java.util.EnumSet class.

[](https://www.tpointtech.com/java-enumset#)[](https://www.tpointtech.com/java-enumset#)[](https://www.tpointtech.com/java-enumset#)

1. public abstract class EnumSet<E extends Enum<E>> extends AbstractSet<E> implements Cloneable, Serializable  

### Methods of Java EnumSet class

|Method|Description|
|---|---|
|static <E extends Enum<E>> EnumSet<E> allOf(Class<E> elementType)|It is used to create an enum set containing all of the elements in the specified element type.|
|static <E extends Enum<E>> EnumSet<E> copyOf(Collection<E> c)|It is used to create an enum set initialized from the specified collection.|
|static <E extends Enum<E>> EnumSet<E> noneOf(Class<E> elementType)|It is used to create an empty enum set with the specified element type.|
|static <E extends Enum<E>> EnumSet<E> of(E e)|It is used to create an enum set initially containing the specified element.|
|static <E extends Enum<E>> EnumSet<E> range(E from, E to)|It is used to create an enum set initially containing the specified elements.|
|EnumSet<E> clone()|It is used to return a copy of this set.|

## Java EnumSet Example

Java EnumSet

[](https://www.tpointtech.com/java-enumset#)[](https://www.tpointtech.com/java-enumset#)[](https://www.tpointtech.com/java-enumset#)

1. import java.util.*;  
2. enum days {  
3.   SUNDAY, MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY  
4. }  
5. public class Main {  
6.   public static void main(String[] args) {  
7.     Set<days> set = EnumSet.of(days.TUESDAY, days.WEDNESDAY);  
8.     // Traversing elements  
9.     Iterator<days> iter = set.iterator();  
10.     while (iter.hasNext())  
11.       System.out.println(iter.next());  
12.   }  
13. }  

**Output:**

TUESDAY
WEDNESDAY

## Java EnumSet Example: allOf() and noneOf()

Java EnumSet

[](https://www.tpointtech.com/java-enumset#)[](https://www.tpointtech.com/java-enumset#)[](https://www.tpointtech.com/java-enumset#)

1. import java.util.*;  
2. enum days {  
3.   SUNDAY, MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY  
4. }  
5. public class Main {  
6.   public static void main(String[] args) {  
7.     Set<days> set1 = EnumSet.allOf(days.class);  
8.       System.out.println("Week Days:"+set1);  
9.       Set<days> set2 = EnumSet.noneOf(days.class);  
10.       System.out.println("Week Days:"+set2);     
11.   }  
12. }  

**Output:**

Week Days:[SUNDAY, MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY]
Week Days:[]