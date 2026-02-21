In programming languages, data types specify the different sizes and values that can be stored in the variable or constants. Each data type is predefined, which makes Java a statically and strongly typed language. There are the following two types of data types in Java.

1. **Primitive Data Types:** The primitive data types include boolean, char, byte, short, int, long, float and double.
2. **Non-Primitive Data Types:** The non-primitive data types include Classes, Interfaces, String, and Arrays.

![Java Data Types](https://images.tpointtech.com/core/images/java-data-types1.png)

Let's understand in detail.

## Java Primitive Data Types

In Java, primitive data types are the building blocks of data manipulation. These are the basic data types.

In Java, there are mainly eight primitive data types which are as follows.

1. [boolean data type](https://www.tpointtech.com/java-data-types#boolean)
2. [char data type](https://www.tpointtech.com/java-data-types#char)
3. [byte data type](https://www.tpointtech.com/java-data-types#byte)
4. [short data type](https://www.tpointtech.com/java-data-types#short)
5. [int data type](https://www.tpointtech.com/java-data-types#int)
6. [long data type](https://www.tpointtech.com/java-data-types#long)
7. [float data type](https://www.tpointtech.com/java-data-types#float)
8. [double data type](https://www.tpointtech.com/java-data-types#double)

---

Java is a statically typed programming language. It means all variables must be declared before their use. That is why we need to declare the variable's type and name. Let's discuss each data type one by one.

### 1. Boolean Data Type

In Java, the boolean data type represents a single bit of information with two possible states: **true** or **false**. The size of the Boolean data type is 1 byte (8 bits).

It is used to store the result of logical expressions or conditions. Unlike other primitive data types like int or double, boolean does not have a specific size or range. It is typically implemented as a single bit, although the exact implementation may vary across platforms.

**Syntax:**

[](https://www.tpointtech.com/java-data-types#)[](https://www.tpointtech.com/java-data-types#)[](https://www.tpointtech.com/java-data-types#)

1. boolean flag;  

### Example

[](https://www.tpointtech.com/java-data-types#)[](https://www.tpointtech.com/java-data-types#)[](https://www.tpointtech.com/java-data-types#)

1. Boolean a = false;  
2. Boolean b = true;    

### 2. Byte Data Type

The byte data type in Java is a primitive data type that represents an 8-bits signed two's complement integer. It has a range of values from **-128 to 127**. Its default value is 0.

The byte data type is commonly used when working with raw binary data or when memory conservation is a concern, as it occupies less memory than larger integer types like int or long.

**Syntax:**

[](https://www.tpointtech.com/java-data-types#)[](https://www.tpointtech.com/java-data-types#)[](https://www.tpointtech.com/java-data-types#)

1. byte size;  

### Example

[](https://www.tpointtech.com/java-data-types#)[](https://www.tpointtech.com/java-data-types#)[](https://www.tpointtech.com/java-data-types#)

1. byte a = 10;  
2. byte b = -20;  

### 3. Short Data Type

The short data type in Java is a primitive data type that represents a **16-bits** signed two-complement integer. Its range of values is **-32,768 to 32,767**.

Similar to the byte data type, short is used when memory conservation is a concern, but more precision than byte is required. Its default value is 0.

**Syntax:**

[](https://www.tpointtech.com/java-data-types#)[](https://www.tpointtech.com/java-data-types#)[](https://www.tpointtech.com/java-data-types#)

1. short var;  

### Example

[](https://www.tpointtech.com/java-data-types#)[](https://www.tpointtech.com/java-data-types#)[](https://www.tpointtech.com/java-data-types#)

1. short a = 10000;    
2. short b = -5000;  

### 4. int Data Type

The int data type in Java is a primitive data type that represents a **32-bits** signed two's complement integer. It has a range of values from **-2,147,483,648 to 2,147,483,647**.

The int data type is one of the most commonly used data types. It is typically used to store whole numbers without decimal points. Its default value is 0.

**Syntax:**

[](https://www.tpointtech.com/java-data-types#)[](https://www.tpointtech.com/java-data-types#)[](https://www.tpointtech.com/java-data-types#)

1. int myInt = 54;  

In Java, int variables are declared using the int keyword. For example, int myInt = 54 ; declares an int variable named myInt and initializes it with the value 54. int variables can be used in mathematical expressions, assigned to other int variables, and used in conditional statements.

**Remember:** In Java SE 8 and later versions, we can use the int data type to represent an unsigned 32-bit integer. It has a value in the range [0, 232-1]. Use the Integer class to use the int data type as an unsigned integer.

### Example

[](https://www.tpointtech.com/java-data-types#)[](https://www.tpointtech.com/java-data-types#)[](https://www.tpointtech.com/java-data-types#)

1. int a = 100000;    
2. int b = -200000;  

### 5. long Data Type

The long data type in Java is a primitive data type that represents a **64-bits** signed two's complement integer. It has a wider range of values than int, ranging from **- 9,223,372,036,854,775,808 to 9,223,372,036,854,775,807.** Its default value is 0.0L or 0.0l.

The long data type is used when the int data type is not large enough to hold the desired value or when a larger range of integer values is needed.

**Syntax:**

[](https://www.tpointtech.com/java-data-types#)[](https://www.tpointtech.com/java-data-types#)[](https://www.tpointtech.com/java-data-types#)

1. long num = 15000000000L;  
2. long num = 9,223,372,036,854,775l  

The long data type is commonly used in applications where large integer values are required, such as in scientific computations, financial applications, and systems programming. It provides greater precision and a larger range than int, making it suitable for scenarios where int is insufficient.

### Example

[](https://www.tpointtech.com/java-data-types#)[](https://www.tpointtech.com/java-data-types#)[](https://www.tpointtech.com/java-data-types#)

1. long a = 5000000L;    
2. long b = -6000000L;  

#### Note: In Java SE 8 and later versions, we can use the long data type to represent an unsigned 64-bit long number. It has a minimum value of 0 and a maximum value of 264-1.

### 6. float Data Type

The float data type in Java is a primitive data type that represents single-precision **32-bits** IEEE 754 floating-point numbers. It can represent a wide range of decimal values, but it is not suitable for precise values such as currency. Its default value is 0.0f or 0.0F.

The float data type is useful for applications where a higher range of values is needed and precision is not critical.

**Syntax:**

[](https://www.tpointtech.com/java-data-types#)[](https://www.tpointtech.com/java-data-types#)[](https://www.tpointtech.com/java-data-types#)

1. float num = 67;  

One of the key characteristics of the float data type is its ability to represent a wide range of values, both positive and negative, including very small and very large values. However, due to its limited precision (approximately 6-7 significant decimal digits), it is not suitable for applications where exact decimal values are required.

### Example

[](https://www.tpointtech.com/java-data-types#)[](https://www.tpointtech.com/java-data-types#)[](https://www.tpointtech.com/java-data-types#)

1. float f = 234.5f;   

### 7. double Data Type

The double data type in Java is a primitive data type that represents double-precision 64-bits IEEE 754 floating-point numbers. Its default value is 0.0. It provides a wider range of values and greater precision compared to the float data type, which makes it suitable for applications where accurate representation of decimal values is required.

**Syntax:**

[](https://www.tpointtech.com/java-data-types#)[](https://www.tpointtech.com/java-data-types#)[](https://www.tpointtech.com/java-data-types#)

1. double num = 75.658d;  

One of the key advantages of the double data type is its ability to represent a wider range of values with greater precision compared to float. It can accurately represent values with up to approximately 15-16 significant decimal digits, making it suitable for applications that require high precision, such as financial calculations, scientific computations, and graphics programming.

### Example

[](https://www.tpointtech.com/java-data-types#)[](https://www.tpointtech.com/java-data-types#)[](https://www.tpointtech.com/java-data-types#)

1. double d = 12.3;   

#### Note: If accuracy is the most important concern, it is suggested not to use float and double data types; use the BigDecimal class instead.

### 8. char Data Type

The char data type in Java is a primitive data type that represents a single **16-bits** Unicode character. It can store any character from the Unicode character set, which allows Java to support the internationalisation and representation of characters from various languages and writing systems.

**Syntax:**

[](https://www.tpointtech.com/java-data-types#)[](https://www.tpointtech.com/java-data-types#)[](https://www.tpointtech.com/java-data-types#)

1. char alphabets = 'J';  
2. char a = 60, b = 61, c = 62;  

The char data type is commonly used to represent characters, such as letters, digits, and symbols. It can also be used to perform arithmetic operations, as the Unicode values of characters can be treated as integers.

### Example

[](https://www.tpointtech.com/java-data-types#)[](https://www.tpointtech.com/java-data-types#)[](https://www.tpointtech.com/java-data-types#)

1. char c = 'A';  

For example, we can perform addition or subtraction operations on char variables to manipulate their Unicode values.

|Type|Default Values|Size|Range of Values|Example|
|---|---|---|---|---|
|**boolean**|false|8 bits|true, false|true, false, 0, 1|
|**byte**|0|8 bits|-128 to 127|-|
|**char**|\u0000|16 bits|Characters Representation of ASCII values  <br>0 to 255|'z', '\u0041', '\11', '\\', '\', '\n'|
|**short**|0|16 bits|-32,768 to 32,767|-|
|**int**|0|32 bits|-2,147,483,648  <br>to  <br>2,147,483,647|-5,-1,0,6,8|
|**long**|0|64 bits|-9,223,372,036,854,775,808  <br>to  <br>9,223,372,036,854,775,807|-7L,-2L,0L,1L,2L|
|**float**|0.0f|32 bits|up to 7 decimal digits|3.14f, 89.09F, -9.3F|
|**double**|0.0|64 bits|up to 16 decimal digits|6.98765e300d , -567899e-600d , 2e2d|

## Java Primitive Data Type Example

**File Name: Main.java**

### Example

[](https://www.tpointtech.com/java-data-types#)[](https://www.tpointtech.com/java-data-types#)[](https://www.tpointtech.com/java-data-types#)

1. public class Main  
2. {  
3.     public static void main(String args[])  
4.     {  
5.         boolean flag = true;  
6.         char ch = 'z';  
7.         int num = 1234;  
8.         byte size = 2;  
9.         short srt = 78;  
10.         double value = 2.4546778;  
11.         float temp = 3.8f;  
12.         long val = 1888889;  
13.         System.out.println("boolean: " + flag);  
14.         System.out.println("char: " + ch);  
15.         System.out.println("integer: " + num);  
16.         System.out.println("byte: " + size);  
17.         System.out.println("short: " + srt);  
18.         System.out.println("float: " + value);  
19.         System.out.println("double: " + temp);  
20.         System.out.println("long: " + val);  
21.     }  
22. }  

**Output:**

boolean: true
char: z
integer: 1234
byte: 2
short: 78
float: 2.4546778
double: 3.8
long: 1888889

## Non-Primitive Data Types in Java

In Java, non-primitive data types are also known as reference data types. It is used to store complex objects rather than simple values. Reference data types store references or memory addresses that point to the location of the object in memory. This distinction is important because it affects how these data types are stored, passed, and manipulated in Java programs.

### 1. Class

One common non-primitive data type in Java is the class. Classes are used to create objects, which are instances of the class. A class defines the properties and behaviours of objects, including [variables](https://www.tpointtech.com/java-variables) (fields) and [methods](https://www.tpointtech.com/method-in-java).

For example, you might create a Person class to represent a person, with variables for the person's name, age, and address, and methods to set and get these values.

**Syntax:**

[](https://www.tpointtech.com/java-data-types#)[](https://www.tpointtech.com/java-data-types#)[](https://www.tpointtech.com/java-data-types#)

1. class Main  
2. {  
3. //code  
4. }  

### 2. Interface

[Interfaces](https://www.tpointtech.com/interface-in-java) are another important non-primitive data type in Java. An interface defines a contract for what a class implementing the interface must provide without specifying how it should be implemented. Interfaces are used to [achieve abstraction](https://www.tpointtech.com/abstraction-in-java) and multiple inheritance.

**Syntax:**

[](https://www.tpointtech.com/java-data-types#)[](https://www.tpointtech.com/java-data-types#)[](https://www.tpointtech.com/java-data-types#)

1. // interface  
2. interface Shape {  
3.   public void draw(); // interface method (does not have a body)  
4.   public void color(); // interface method (does not have a body)  
5. }  

### 3. Arrays

[Arrays](https://www.tpointtech.com/java-arrays) are a fundamental non-primitive data type in Java that allows you to store multiple values of the same type in a single variable. Arrays have a fixed size, which is specified when the array is created and can be accessed using an index. Arrays are commonly used to store lists of values or to represent matrices and other multi-dimensional data structures.

**Syntax:**

[](https://www.tpointtech.com/java-data-types#)[](https://www.tpointtech.com/java-data-types#)[](https://www.tpointtech.com/java-data-types#)

1. int[] arr = { 1, 2, 3, 4, 5 };  

### 4. String

In Java, a [string](https://www.tpointtech.com/java-string) is a sequence of characters. In simple words, we can define a string as an array of characters. The difference between a character array and a string in Java is that the string is designed to hold a sequence of characters in a single variable, whereas a character array is a collection of separate char-type entities. Note that, unlike C/C++, Java strings are not terminated with a null character.

**Syntax:**

[](https://www.tpointtech.com/java-data-types#)[](https://www.tpointtech.com/java-data-types#)[](https://www.tpointtech.com/java-data-types#)

1. // string without using new operator   
2. String s = "tpointtech";   
3. // String using new operator   
4. String str = new String("Austria");  

### 5. enum

Java also includes other non-primitive data types, such as enums and collections. [Enums](https://www.tpointtech.com/java-enums) are used to define a set of named constants, providing a way to represent a fixed set of values. Collections are a framework of classes and interfaces that provide dynamic data structures such as lists, sets, and maps, which can grow or shrink in size as needed.

**Syntax:**

[](https://www.tpointtech.com/java-data-types#)[](https://www.tpointtech.com/java-data-types#)[](https://www.tpointtech.com/java-data-types#)

1. enum Grade {  
2.   FIRST,  
3.   SECOND,  
4.   THIRD  
5. }  

Overall, non-primitive data types in Java are essential for creating complex and flexible programs. They allow us to create and manipulate objects, define relationships between objects, and represent complex data structures.

## Java Non-Primitive Data Type Example

**File Name: Main.java**

### Example

[](https://www.tpointtech.com/java-data-types#)[](https://www.tpointtech.com/java-data-types#)[](https://www.tpointtech.com/java-data-types#)

1. enum Color {  
2.     RED,  
3.     GREEN,  
4.     BLUE;  
5. }  
6. public class Main {  
7.     public static void main(String[] args) {  
8.         String str = "Hello";  
9.         int[] arr = { 1, 2, 3, 4, 5 };  
10.         Color clr = Color.BLUE;  
11.         System.out.println(clr);  
12.         System.out.println(str);  
13.         for (int member: arr) {  
14.         System.out.print(member+", ");  
15.         }  
16.     }  
17. }  

**Output:**

BLUE
Hello
1, 2, 3, 4, 5

## Why char uses 2 bytes in Java, and what is \u0000 ?

It is because Java uses the Unicode system, not the ASCII code system. The \u0000 is the lowest range of the Unicode system. To get a detailed explanation of a Unicode, visit the next page