In [Java](https://www.tpointtech.com/java-tutorial), string is basically an object that represents sequence of char values. An [array](https://www.tpointtech.com/array-in-java) of characters works as a string in Java. For example:

[](https://www.tpointtech.com/java-string#)[](https://www.tpointtech.com/java-string#)[](https://www.tpointtech.com/java-string#)

1. char[] ch={'t','p','o','i','n','t'};    
2. String s=new String(ch);    

is same as:

[](https://www.tpointtech.com/java-string#)[](https://www.tpointtech.com/java-string#)[](https://www.tpointtech.com/java-string#)

1. String s="tpoint";  

**Java String** class provides a lot of methods to perform operations on strings such as compare(), concat(), equals(), split(), length(), replace(), compareTo(), intern(), substring() etc.

The java.lang.String class implements _Serializable_, _Comparable_ and _CharSequence_ [interfaces](https://www.tpointtech.com/interface-in-java).

![String in Java](https://d2jdgazzki9vjm.cloudfront.net/images/core/string-implements.png)

## CharSequence Interface

The CharSequence interface is used to represent the sequence of characters. String, [StringBuffer](https://www.tpointtech.com/StringBuffer-class) and [StringBuilder](https://www.tpointtech.com/StringBuilder-class) classes implement it. It means, we can create strings in Java by using these three classes.

![CharSequence in Java](https://d2jdgazzki9vjm.cloudfront.net/images/core/charsequence.png)

The Java String is immutable which means it cannot be changed. Whenever we change any string, a new instance is created. For mutable strings, you can use StringBuffer and StringBuilder classes.

We will discuss immutable string later. Let's first understand what String in Java is and how to create the String object.

## What is String in Java?

Generally, a **string** is a sequence of characters. However, a string in Java is an object that represents a sequence of characters, and the **java.lang.String** class is used to create string objects. Java Strings are **immutable** that means their values cannot be changed once created.

There are two ways to create String object:

1. By string literal
2. By new keyword

Here, we are going to discuss these objects one by one.

## 1. Creating String Using String Literal

Java String literal is created by using double quotes. For Example:

[](https://www.tpointtech.com/java-string#)[](https://www.tpointtech.com/java-string#)[](https://www.tpointtech.com/java-string#)

1. String s="welcome";  

Each time you create a string literal, the JVM checks the "string constant pool" first. If the string already exists in the pool, a reference to the pooled instance is returned. If the string doesn't exist in the pool, a new string instance is created and placed in the pool. For example:

[](https://www.tpointtech.com/java-string#)[](https://www.tpointtech.com/java-string#)[](https://www.tpointtech.com/java-string#)

1. String s1="Welcome";  
2. String s2="Welcome";//It doesn't create a new instance  

  
![Java String](https://d2jdgazzki9vjm.cloudfront.net/core/images/java-string.png)

In the above example, only one object will be created. Firstly, JVM will not find any string object with the value "Welcome" in string constant pool that is why it will create a new object. After that it will find the string with the value "Welcome" in the pool, it will not create a new object but will return the reference to the same instance.

### Example

The following example demonstrate how to create string using string literals.

[](https://www.tpointtech.com/java-string#)[](https://www.tpointtech.com/java-string#)[](https://www.tpointtech.com/java-string#)

1. //Java Program to create string using string literal    
2. public class Main {    
3.  public static void main(String[] args) {  
4.     String s1="Welcome";    
5.     String s2="Welcome";//It doesn't create a new instance    
6.     System.out.println(s1+" "+s2);  
7.  }    
8. }   

**Output:**

Welcome Welcome

#### Note: String objects are stored in a special memory area known as the "string constant pool".

## 2. Creating String Using new Keyword

A string can be created using the [new keyword](https://www.tpointtech.com/new-keyword-in-java), which explicitly creates a new String object in memory rather than using the string literal pool.

For example:

[](https://www.tpointtech.com/java-string#)[](https://www.tpointtech.com/java-string#)[](https://www.tpointtech.com/java-string#)

1. String s=new String("Welcome");//creates two objects and one reference variable  

Here,

- **"Welcome"** is a string literal, so it is stored in the string pool (one object).
- **new String("Welcome")** creates a new String object in the heap (second object).
- **s** is the reference variable that points to the object in the heap.

In such case, [JVM](https://www.tpointtech.com/jvm-java-virtual-machine) will create a new string object in normal (non-pool) heap memory, and the literal "Welcome" will be placed in the string constant pool. The variable s will refer to the object in a heap (non-pool).

[](https://www.tpointtech.com/java-string#)[](https://www.tpointtech.com/java-string#)[](https://www.tpointtech.com/java-string#)

1. //Java Program to create string using new keyword  
2. public class Main {    
3.  public static void main(String[] args) {  
4.     String s1=new String("Welcome");  
5.     String s2=new String("Welcome");  
6.     System.out.println(s1+" "+s2);  
7.  }    
8. }   

**Output:**

Welcome Welcome

## Finding String Length

You can find the number of characters in a string by calling the length() method on the string object.

### Syntax

It has the following syntax:

[](https://www.tpointtech.com/java-string#)[](https://www.tpointtech.com/java-string#)[](https://www.tpointtech.com/java-string#)

1. int length = str.length();  

### Example

The following example demonstrate how to find string length.

[](https://www.tpointtech.com/java-string#)[](https://www.tpointtech.com/java-string#)[](https://www.tpointtech.com/java-string#)

1. public class StringLengthExample {  
2.     public static void main(String[] args) {  
3.         String str = "Hello World";  
4.         System.out.println("Length of string: " + str.length());  
5.     }  
6. }  

**Output:**

Length of string: 11

## Finding a Character in a String

You can find a character or substring in a string by using the indexOf() method that returns its position.

### Syntax

It has the following syntax:

[](https://www.tpointtech.com/java-string#)[](https://www.tpointtech.com/java-string#)[](https://www.tpointtech.com/java-string#)

1. int index = str.indexOf('a');  

### Example

The following example demonstrate how to find a character in a string.

[](https://www.tpointtech.com/java-string#)[](https://www.tpointtech.com/java-string#)[](https://www.tpointtech.com/java-string#)

1. public class FindCharacterExample {  
2.     public static void main(String[] args) {  
3.         String str = "Hello World";  
4.         System.out.println("Index of 'o': " + str.indexOf('o'));  
5.     }  
6. }  

**Output:**

Index of 'o': 4

## Comparing Strings

You can [compare two strings](https://www.tpointtech.com/string-comparison-in-java) using equals() for equality or compareTo() for lexicographical order.

### Syntax

It has the following syntax:

[](https://www.tpointtech.com/java-string#)[](https://www.tpointtech.com/java-string#)[](https://www.tpointtech.com/java-string#)

1. boolean equal = str1.equals(str2);         
2. int result = str1.compareTo(str2);         

### Example

The following example demonstrate how to compare strings.

[](https://www.tpointtech.com/java-string#)[](https://www.tpointtech.com/java-string#)[](https://www.tpointtech.com/java-string#)

1. public class CompareStringExample {  
2.     public static void main(String[] args) {  
3.         String str1 = "Apple";  
4.         String str2 = "Banana";  

5.         System.out.println("Equal? " + str1.equals(str2));  
6.         System.out.println("CompareTo result: " + str1.compareTo(str2));  
7.     }  
8. }  

**Output:**

Equal? false
CompareTo result: -1

## Concatenating Strings

You can [join two or more strings](https://www.tpointtech.com/string-concatenation-in-java) into one using the concat() method or the + operator.

### Syntax

It has the following syntax:

[](https://www.tpointtech.com/java-string#)[](https://www.tpointtech.com/java-string#)[](https://www.tpointtech.com/java-string#)

1. String result = str1.concat(str2);  

### Example

The following example demonstrate how to concatenate strings.

[](https://www.tpointtech.com/java-string#)[](https://www.tpointtech.com/java-string#)[](https://www.tpointtech.com/java-string#)

1. public class ConcatenateStringExample {  
2.     public static void main(String[] args) {  
3.         String str1 = "Hello";  
4.         String str2 = "World";  
5.         String combined = str1.concat(" ").concat(str2);  

6.         System.out.println("Concatenated String: " + combined);  
7.     }  
8. }  

## Java String Immutability

In Java, strings are immutable. It means that its value cannot be changed once a String object is created. If any operation appears to modify a String, what happens is the creation of a new String object. The original string remains unchanged. This immutable characteristic of strings in Java has several implications for performance, security, and functionality.

### Example

The following example demonstrate the string immutability.

[](https://www.tpointtech.com/java-string#)[](https://www.tpointtech.com/java-string#)[](https://www.tpointtech.com/java-string#)

1. public class ImmutableStringExample {  
2.     public static void main(String[] args) {  
3.         // Original string  
4.         String originalString = "Java";  
5.         System.out.println("Original string: " + originalString);  
6.         // Attempt to modify the original string  
7.         String modifiedString = originalString.concat(" Programming");  
8.         // Showing that the original string remains unchanged  
9.         System.out.println("After modification, original string: " + originalString);  
10.         // The result of the modification attempt is stored in a new string  
11.         System.out.println("Modified string: " + modifiedString);  
12.         // Demonstrating further that the original string is immutable  
13.         originalString.toUpperCase(); // This operation does not change the original string  
14.         System.out.println("After calling toUpperCase on original string: " + originalString);  
15.         // Correct way to use the result of a string operation  
16.         String upperCaseString = originalString.toUpperCase(); // Stores the result in a new string  
17.         System.out.println("Original string in uppercase: " + upperCaseString);  
18.     }  
19. }  

**Output:**

Original string: Java
After modification, original string: Java
Modified string: Java Programming
After calling toUpperCase on original string: Java
Original string in uppercase: JAVA

## Memory Allotment of String

In Java, memory allocation for strings is influenced by **immutability** and the **string pool**.

### String Literal Storage

When a string is created using a literal, Java first checks the **string pool**.

- If the string already exists in the pool, the new reference points to the existing object.
- If it does not exist, a new string object is created in the pool, and the reference points to it.

This mechanism helps **save memory** and improves **performance**, especially when the same strings are used multiple times in a program.

**Syntax**

It has the following syntax:

[](https://www.tpointtech.com/java-string#)[](https://www.tpointtech.com/java-string#)[](https://www.tpointtech.com/java-string#)

1. String s1 = "Hello"; // String literal  
2. String s2 = "Hello"; // Points to the same "Hello" in the Pool as s1  

### new Keyword and String Pool

Strings created with the **new** operator do not use the Pool by default. They are stored in the heap memory outside the Pool, which means each **new** operation results in a new object, even if it contains the same string data

**Syntax:**

It has the following syntax:

[](https://www.tpointtech.com/java-string#)[](https://www.tpointtech.com/java-string#)[](https://www.tpointtech.com/java-string#)

1. String s3 = new String("Hello"); // A new string object is created in the heap  

### Interning

We can manually add a string to the Pool or ensure it uses the Pool by calling the **intern()** method on a string object. If the Pool already contains an equal string, the string from the Pool is returned. Otherwise, the string is added to the Pool.

**Syntax:**

It has the following syntax:

[](https://www.tpointtech.com/java-string#)[](https://www.tpointtech.com/java-string#)[](https://www.tpointtech.com/java-string#)

1. String s4 = new String("Hello").intern(); // Ensures use of the string pool  

### Example Demonstrating Memory Allotment of String

Consider the following example, demonstrating the memory allotment of string.

[](https://www.tpointtech.com/java-string#)[](https://www.tpointtech.com/java-string#)[](https://www.tpointtech.com/java-string#)

1. public class StringMemoryAllotment {  
2.     public static void main(String[] args) {  
3.         // String literals - stored in the string pool  
4.         String str1 = "Java";  
5.         String str2 = "Java";  
6.         // Checking if str1 and str2 point to the same object  
7.         System.out.println("str1 == str2: " + (str1 == str2)); // true, because both refer to the same string literal in the pool  
8.         // Strings created with 'new' - stored in heap memory outside the string pool  
9.         String str3 = new String("Java");  
10.         String str4 = new String("Java");  
11.         // Checking if str3 and str4 point to the same object  
12.         System.out.println("str3 == str4: " + (str3 == str4)); // false, because 'new' creates a new object each time  
13.         // Interning str3  
14.         String str5 = str3.intern();  
15.         // Checking if str1 and str5 point to the same object  
16.         System.out.println("str1 == str5: " + (str1 == str5)); // true, str5 is interned, so it refers to the string in the pool  
17.         // Demonstrating the effect of interning on memory allocation  
18.         String str6 = new String("Java").intern();  
19.         // Checking if str6 is the same as str1  
20.         System.out.println("str1 == str6: " + (str1 == str6)); // true, str6 is interned and points to the pooled instance  
21.     }  
22. }  

**Output:**

str1 == str2: true
str3 == str4: false
str1 == str5: true
str1 == str6: true

## Construct String from a subset of the char array

You can create a string from a part of a character array using a special String constructor. You need to provide three things: the **char array**, the **starting index**, and the **number of characters** to include.

### Syntax

It has the following syntax:

[](https://www.tpointtech.com/java-string#)[](https://www.tpointtech.com/java-string#)[](https://www.tpointtech.com/java-string#)

1. String(char[] value)  
2. String(char[] value, int offset, int count)  

Here,

- **value:** The **char** array.
- **offset:** The initial offset into the array.
- **count:** The number of characters to use from the array.

### Example: Constructing String from Subset of Char Array

The following example demonstrates creating (constructing) a string from the subset of a character array.

[](https://www.tpointtech.com/java-string#)[](https://www.tpointtech.com/java-string#)[](https://www.tpointtech.com/java-string#)

1. public class CharArrayToString {  
2.     public static void main(String[] args) {  
3.         // Define a char array  
4.         char[] charArray = {'H', 'e', 'l', 'l', 'o', ' ', 'W', 'o', 'r', 'l', 'd'};  
5.         // Construct a string from a subset of the char array  
6.         // Here, we start at index 6 (the space character) and use the next 5 characters  
7.         String resultString = new String(charArray, 6, 5);  
8.         // Output the result  
9.         System.out.println(resultString);   
10.     }  
11. }  

**Output:**

World

Let us see another example of Java String which is created using char[] array.

### Example: Creating String Using Char[] Array

The following example demonstrates creating (constructing) a string from a character array (char[] Array).

[](https://www.tpointtech.com/java-string#)[](https://www.tpointtech.com/java-string#)[](https://www.tpointtech.com/java-string#)

1. public class StringExample{    
2. public static void main(String args[]){    
3. String s1="java";//creating string by Java string literal    
4. char ch[]={'s','t','r','i','n','g','s'};    
5. String s2=new String(ch);//converting char array to string    
6. String s3=new String("example");//creating Java string by new keyword    
7. System.out.println(s1);    
8. System.out.println(s2);    
9. System.out.println(s3);    
10. }}    

**Output:**

java
strings
example

The above code, converts a **_char_** array into a **String** object. And displays the String objects **_s1, s2_**, and **_s3_** on console using **_println()_** method.

## String Class Characteristics and Interfaces

Java String class is a part of the **java.lang package** which is used to create and manipulate strings. The **String** class provides many useful methods for operations like comparison, concatenation, and searching.

The **String** class is one of the most fundamental types in Java that is designed to represent **immutable sequences of characters**.

Here are the key characteristics and the interfaces it implements:

- **Immutability:** Once a String object is created, it cannot be modified. This design ensures **thread safety**, consistency, and efficiency, especially when used with the **string pool**.
- **String Pool:** Java maintains a pool of string literals to save memory. When a new string literal is created, Java checks the pool for a matching string. If found, the new reference points to the existing string. Otherwise, a new string is added to the pool.
- **Implemented Interfaces:** The String class implements several interfaces, including:

- - **Serializable:** It allows string objects to be converted into byte streams for storage or transmission.
    - **Comparable<String>:** It enables lexical comparison between strings, supporting natural ordering in collections.
    - **CharSequence:** It provides a read-only interface for different types of character sequences that allows strings to be accessed and manipulated generically.