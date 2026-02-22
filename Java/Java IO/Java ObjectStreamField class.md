The ObjectStreamField class in Java is used to describe a serializable field of a serializable class.

In this chapter, we will learn what the ObjectStreamField class is, why it is used, its constructors, important methods, type codes, and how it works with an example.

## Constructors of ObjectStreamField Class

The ObjectStreamField class provides constructors to define a serializable field.

### 1. ObjectStreamField(String name, Class type)

This constructor creates an ObjectStreamField with the specified field name and data type.

**Syntax:**

Here is the syntax of this constructor:

[](https://www.tpointtech.com/java-objectstreamfield-class#)[](https://www.tpointtech.com/java-objectstreamfield-class#)[](https://www.tpointtech.com/java-objectstreamfield-class#)

1. ObjectStreamField(String name, Class<?> type)  

### 2. ObjectStreamField(String name, Class type, boolean unshared)

This constructor creates an ObjectStreamField with the specified name and type and marks it as shared or unshared.

**Syntax:**

Here is the syntax of this constructor:

[](https://www.tpointtech.com/java-objectstreamfield-class#)[](https://www.tpointtech.com/java-objectstreamfield-class#)[](https://www.tpointtech.com/java-objectstreamfield-class#)

1. ObjectStreamField(String name, Class<?> type, boolean unshared)  

## Methods of ObjectStreamField Class

The ObjectStreamField class provides methods to access serialization field details.

|Modifier and Type|Method|Description|
|---|---|---|
|int|compareTo(Object obj)|It compares this field with another ObjectStreamField.|
|String|getName()|It gets the name of this field.|
|int|GetOffset()|Offset of field within instance data.|
|Class<?>|getType()|It get the type of the field.|
|char|getTypeCode()|It returns character encoding of field type.|
|String|getTypeString()|It return the [JVM](https://www.tpointtech.com/internal-details-of-jvm) type signature.|
|boolean|isPrimitive()|It return true if this field has a primitive type.|
|boolean|isUnshared()|It returns boolean value indicating whether or not the serializable field represented by this ObjectStreamField instance is unshared.|
|protected void|setOffset(int offset)|Offset within instance data.|
|String|toString()|It return a [string](https://www.tpointtech.com/java-string) that describes this field.|

### Type Codes Returned by getTypeCode()

The getTypeCode() method returns a character that represents the field data type.

|   |   |
|---|---|
|B|byte|
|C|char|
|D|double|
|F|float|
|I|int|
|J|long|
|L|class or interface|
|S|short|
|Z|boolean|
|[|array|

**Returns:**

the typecode of the serializable field

## Example of ObjectStreamField Class

This example demonstrates how to retrieve serializable field details using the ObjectStreamField class.

[](https://www.tpointtech.com/java-objectstreamfield-class#)[](https://www.tpointtech.com/java-objectstreamfield-class#)[](https://www.tpointtech.com/java-objectstreamfield-class#)

1. import java.io.ObjectStreamClass;  
2. import java.util.Calendar;  

3. public class ObjectStreamClassExample {  
4.      public static void main(String[] args) {  

5.           // create a new object stream class for Integers  
6.           ObjectStreamClass osc = ObjectStreamClass.lookup(String.class);  

7.           // get the value field from ObjectStreamClass for integers  
8.           System.out.println("" + osc.getField("value"));  

9.           // create a new object stream class for Calendar  
10.           ObjectStreamClass osc2 = ObjectStreamClass.lookup(Calendar.class);  

11.           // get the Class instance for osc2  
12.           System.out.println("" + osc2.getField("isTimeSet"));  

13.        }  
14. }  

**Output:**

I value
Z isTimeSet