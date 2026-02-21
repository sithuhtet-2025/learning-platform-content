Java wrapper class provides a mechanism to convert primitive data types into objects and objects into primitive data types. In this chapter, we will learn about wrapper classes and how they work.

## What are Wrapper classes in Java?

**Wrapper classes** are predefined classes in the **java.lang** package that convert [primitive data types](https://www.tpointtech.com/java-data-types) into objects. They allow primitives to be used in object-oriented features such as [collections](https://www.tpointtech.com/collections-in-java) and [methods](https://www.tpointtech.com/java-data-types) that require objects.

## Autoboxing and Unboxing

Since J2SE 5.0, Java supports **autoboxing** and **unboxing**, which automatically convert primitive data types into their corresponding object types and vice versa.

The automatic conversion of a primitive type into its wrapper object is called **autoboxing**, while the conversion of a wrapper object back into its primitive type is known as **unboxing**.

## Use of Wrapper Classes in Java

Java is an object-oriented programming language, so we need to deal with objects many times like in Collections, Serialization, Synchronization, etc. Let us see the different scenarios, where we need to use the wrapper classes.

- **Change the value in Method:** Java supports only call by value. So, if we pass a primitive value, it will not change the original value. But, if we convert the primitive value in an object, it will change the original value.
- **Serialization:** We need to convert the objects into streams to perform the serialization. If we have a primitive value, we can convert it in objects through the wrapper classes.
- **Synchronization:** Java synchronization works with objects in Multithreading.
- **java.util package:** The java.util package provides the utility classes to deal with objects.
- **Collection Framework:** Java collection framework works with objects only. All classes of the collection framework (ArrayList, LinkedList, Vector, HashSet, LinkedHashSet, TreeSet, PriorityQueue, ArrayDeque, etc.) deal with objects only.

## Wrapper Classes in the java.lang Package

The eight classes of the java.lang package are known as wrapper classes in Java. The list of eight wrapper classes is given below:

|Primitive Type|Wrapper class|
|---|---|
|boolean|[Boolean](https://www.tpointtech.com/java-boolean)|
|char|[Character](https://www.tpointtech.com/post/java-character)|
|byte|[Byte](https://www.tpointtech.com/java-byte)|
|short|[Short](https://www.tpointtech.com/java-short)|
|int|[Integer](https://www.tpointtech.com/java-integer)|
|long|[Long](https://www.tpointtech.com/java-long)|
|float|[Float](https://www.tpointtech.com/java-float)|
|double|[Double](https://www.tpointtech.com/java-double)|

## Primitive to Wrapper Conversion (Autoboxing)

The automatic conversion of primitive data type into its corresponding wrapper class is known as autoboxing, for example, byte to Byte, char to Character, int to Integer, long to Long, float to Float, boolean to Boolean, double to Double, and short to Short.

Since Java 5, we do not need to use the valueOf() method of wrapper classes to convert the primitive into objects.

### Example

The following example demonstrates the primitive to wrapper class conversion using autoboxing.

[](https://www.tpointtech.com/wrapper-class-in-java#)[](https://www.tpointtech.com/wrapper-class-in-java#)[](https://www.tpointtech.com/wrapper-class-in-java#)

1. //Java program to convert primitive into objects  
2. //Autoboxing example of int to Integer  
3. public class WrapperExample1{  
4. public static void main(String args[]){  
5. //Converting int into Integer  
6. int a=20;  
7. Integer i=Integer.valueOf(a);//converting int into Integer explicitly  
8. Integer j=a;//autoboxing, now compiler will write Integer.valueOf(a) internally  

9. System.out.println(a+" "+i+" "+j);  
10. }}  

**Output:**

20 20 20

## Wrapper to Primitive Conversion (Unboxing)

The automatic conversion of wrapper type into its corresponding primitive type is known as unboxing. It is the reverse process of autoboxing. Since Java 5, we do not need to use the intValue() method of wrapper classes to convert the wrapper type into primitives.

### Example

The following example demonstrates the wrapper to primitive type conversion using unboxing:

[](https://www.tpointtech.com/wrapper-class-in-java#)[](https://www.tpointtech.com/wrapper-class-in-java#)[](https://www.tpointtech.com/wrapper-class-in-java#)

1. //Java program to convert object into primitives  
2. //Unboxing example of Integer to int  
3. public class WrapperExample2{    
4. public static void main(String args[]){    
5. //Converting Integer to int    
6. Integer a=new Integer(3);    
7. int i=a.intValue();//converting Integer to int explicitly  
8. int j=a;//unboxing, now compiler will write a.intValue() internally    

9. System.out.println(a+" "+i+" "+j);    
10. }}    

**Output:**

3 3 3

## Wrapper Classes (Autoboxing and Unboxing) Example

In this example, we are converting all primitive data types into their corresponding wrapper class objects using autoboxing. After that, the wrapper objects are converted back into primitive data types using unboxing. Finally, both object values and primitive values are printed to verify the conversion process.

[](https://www.tpointtech.com/wrapper-class-in-java#)[](https://www.tpointtech.com/wrapper-class-in-java#)[](https://www.tpointtech.com/wrapper-class-in-java#)

1. //Java Program to convert all primitives into its corresponding   
2. //wrapper objects and vice-versa  
3. public class WrapperExample3{  
4. public static void main(String args[]){  
5. byte b=10;  
6. short s=20;  
7. int i=30;  
8. long l=40;  
9. float f=50.0F;  
10. double d=60.0D;  
11. char c='a';  
12. boolean b2=true;  

13. //Autoboxing: Converting primitives into objects  
14. Byte byteobj=b;  
15. Short shortobj=s;  
16. Integer intobj=i;  
17. Long longobj=l;  
18. Float floatobj=f;  
19. Double doubleobj=d;  
20. Character charobj=c;  
21. Boolean boolobj=b2;  

22. //Printing objects  
23. System.out.println("---Printing object values---");  
24. System.out.println("Byte object: "+byteobj);  
25. System.out.println("Short object: "+shortobj);  
26. System.out.println("Integer object: "+intobj);  
27. System.out.println("Long object: "+longobj);  
28. System.out.println("Float object: "+floatobj);  
29. System.out.println("Double object: "+doubleobj);  
30. System.out.println("Character object: "+charobj);  
31. System.out.println("Boolean object: "+boolobj);  

32. //Unboxing: Converting Objects to Primitives  
33. byte bytevalue=byteobj;  
34. short shortvalue=shortobj;  
35. int intvalue=intobj;  
36. long longvalue=longobj;  
37. float floatvalue=floatobj;  
38. double doublevalue=doubleobj;  
39. char charvalue=charobj;  
40. boolean boolvalue=boolobj;  

41. //Printing primitives  
42. System.out.println("---Printing primitive values---");  
43. System.out.println("byte value: "+bytevalue);  
44. System.out.println("short value: "+shortvalue);  
45. System.out.println("int value: "+intvalue);  
46. System.out.println("long value: "+longvalue);  
47. System.out.println("float value: "+floatvalue);  
48. System.out.println("double value: "+doublevalue);  
49. System.out.println("char value: "+charvalue);  
50. System.out.println("boolean value: "+boolvalue);  
51. }}  

**Output:**

---Printing object values---
Byte object: 10
Short object: 20
Integer object: 30
Long object: 40
Float object: 50.0
Double object: 60.0
Character object: a
Boolean object: true
---Printing primitive values---
byte value: 10
short value: 20
int value: 30
long value: 40
float value: 50.0
double value: 60.0
char value: a
boolean value: true

## Custom Wrapper Class

Wrapper classes wrap primitive data types; that is why they are called wrapper classes. Similarly, we can also create our own class that wraps a primitive data type. Such a user-defined class is known as a **custom wrapper class**.

### Example

The following example demonstrates creating and using a custom wrapper class.

[](https://www.tpointtech.com/wrapper-class-in-java#)[](https://www.tpointtech.com/wrapper-class-in-java#)[](https://www.tpointtech.com/wrapper-class-in-java#)

1. //Creating the custom wrapper class  
2. class Javatpoint{  
3. private int i;  
4. Javatpoint(){}  
5. Javatpoint(int i){  
6. this.i=i;  
7. }  
8. public int getValue(){  
9. return i;  
10. }  
11. public void setValue(int i){  
12. this.i=i;  
13. }  
14. @Override  
15. public String toString() {  
16.   return Integer.toString(i);  
17. }  
18. }  
19. //Testing the custom wrapper class  
20. public class TestJavatpoint{  
21. public static void main(String[] args){  
22. Javatpoint j=new Javatpoint(10);  
23. System.out.println(j);  
24. }}  

**Output:**

10