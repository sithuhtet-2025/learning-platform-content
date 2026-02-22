# The ObjectStreamClass in Java is used as a serialization descriptor that contains metadata about a serializable class.

In this chapter, we will learn what the ObjectStreamClass is, why it is used, its fields, important methods, and how it works with an example.

## What is ObjectStreamClass in Java?

The **ObjectStreamClass** is a special class used internally by [Java serialization](https://www.tpointtech.com/serialization-in-java), and it is used to store metadata of a [class](https://www.tpointtech.com/object-and-class-in-java) such as its name, fields, and serialVersionUID.

It acts as a serialization descriptor, which means it describes how a class is represented during the serialization and deserialization process.

## ObjectStreamClass Usage (No Public Constructor)

The ObjectStreamClass does not provide a public constructor. Instead, objects of this class are obtained using static lookup methods provided by the class.

Here is the common way to obtain ObjectStreamClass:

[](https://www.tpointtech.com/java-objectstream-class#)[](https://www.tpointtech.com/java-objectstream-class#)[](https://www.tpointtech.com/java-objectstream-class#)

1. ObjectStreamClass osc = ObjectStreamClass.lookup(ClassName.class);  

## Fields of ObjectStreamClass

The ObjectStreamClass provides fields that describe serializable properties.

| Modifier and Type          | Field     | Description                                         |
| -------------------------- | --------- | --------------------------------------------------- |
| static ObjectStreamField[] | NO_FIELDS | Indicates that the class has no serializable fields |

## Methods of ObjectStreamClass

The ObjectStreamClass class provides methods to access serialization-related information.

| Modifier and Type | Method     | Description                                                          |
| ----------------- | ---------- | -------------------------------------------------------------------- |
| Class<?>          | forClass() | It returns the class in the local VM that this version is mapped to. |
|ObjectStreamField|getField(String name)|It gets the field of this class by name.|
|ObjectStreamField[]|getFields()|It returns an [array](https://www.tpointtech.com/array-in-java) of the fields of this serialization class.|
|String|getName()|It returns the name of the class described by this descriptor.|
|long|getSerialVersionUID()|It returns the serialVersionUID for this class.|
|Static ObjectStreamClass|lookup(Class<?> cl)|It finds the descriptor for a class that can be serialized.|
|Static ObjectStreamClass|lookupAny(Class<?> cl)|It returns the descriptor for any class, regardless of whether it implements Serializable.|
|String|toString()|It returns a string describing this ObjectStreamClass.|

## Example of ObjectStreamClass

This example demonstrates how to retrieve serialization-related information of a class using ObjectStreamClass.

[](https://www.tpointtech.com/java-objectstream-class#)[](https://www.tpointtech.com/java-objectstream-class#)[](https://www.tpointtech.com/java-objectstream-class#)

1. import java.io.ObjectStreamClass;  
2. import java.util.Calendar;  

3. public class ObjectStreamClassExample {  
4.     public static void main(String[] args) {  

5.         // create a new object stream class for Integers  
6.         ObjectStreamClass osc = ObjectStreamClass.lookup(SmartPhone.class);  

7.         // get the value field from ObjectStreamClass for integers  
8.         System.out.println("" + osc.getField("price"));  

9.         // create a new object stream class for Calendar  
10.         ObjectStreamClass osc2 = ObjectStreamClass.lookup(String.class);  

11.         // get the Class instance for osc2  
12.         System.out.println("" + osc2.getField("hash"));  

13.     }  
14. }  

**Output:**

I price
null