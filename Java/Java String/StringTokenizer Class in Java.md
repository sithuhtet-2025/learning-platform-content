Java StringTokenizer class is useful when a string needs to be broken into smaller tokens based on delimiters. In this chapter, we will learn what the StringTokenizer class is, along with its constructors, methods, and usage through examples.

## What is StringTokenizer class in Java?

The **StringTokenizer** class is used to **break a string into tokens** based on **specified delimiters**. It belongs to the **java.util** package and provides a simple way to split a string into smaller parts. The delimiters can be defined at the time of object creation or applied while retrieving tokens.

**StringTokenizer** is considered a **legacy class**, and it does not provide advanced features such as distinguishing between numbers, identifiers, or quoted strings. For more flexible and modern string processing, classes like String.split() or StreamTokenizer are generally preferred.

For example, consider the string **"hello welcome to TpointTech"**. As shown in the image, the StringTokenizer breaks this string into separate tokens based on the specified delimiter (such as a space), resulting in individual words like **hello**, **welcome**, **to**, and **TpointTech**.

![StringTokenizer in Java](https://d2jdgazzki9vjm.cloudfront.net/core/images/string-tokenizer-in-java.png)

## Constructors of StringTokenizer Class

There are three constructors defined in the StringTokenizer class, which are:

### 1. StringTokenizer(String str)

It creates a StringTokenizer for the specified string using the default delimiter (space, tab, newline, etc.).

**Syntax:**

It has the following syntax:

[](https://www.tpointtech.com/string-tokenizer-in-java#)[](https://www.tpointtech.com/string-tokenizer-in-java#)[](https://www.tpointtech.com/string-tokenizer-in-java#)

1. StringTokenizer st = new StringTokenizer(str);  

### 2. StringTokenizer(String str, String delim)

It creates a StringTokenizer for the specified string using the provided delimiter(s).

**Syntax:**

It has the following syntax:

[](https://www.tpointtech.com/string-tokenizer-in-java#)[](https://www.tpointtech.com/string-tokenizer-in-java#)[](https://www.tpointtech.com/string-tokenizer-in-java#)

1. StringTokenizer st = new StringTokenizer(str, delim);  

### 3. StringTokenizer(String str, String delim, boolean returnDelims)

It creates a StringTokenizer for the specified string and delimiter(s). If returnDelims is true, the delimiters are also returned as tokens. If false, delimiters are only used to separate tokens.

**Syntax:**

It has the following syntax:

[](https://www.tpointtech.com/string-tokenizer-in-java#)[](https://www.tpointtech.com/string-tokenizer-in-java#)[](https://www.tpointtech.com/string-tokenizer-in-java#)

1. StringTokenizer st = new StringTokenizer(str, delim, true); // delimiters included as tokens  
2. StringTokenizer st2 = new StringTokenizer(str, delim, false); // delimiters not included  

You can choose any of the constructors, how to split your string and whether to consider delimiters as tokens, depending on your parsing needs.

### Example of StringTokenizer Constructors

The following example demonstrates all three constructors of the StringTokenizer class:

[](https://www.tpointtech.com/string-tokenizer-in-java#)[](https://www.tpointtech.com/string-tokenizer-in-java#)[](https://www.tpointtech.com/string-tokenizer-in-java#)

1. import java.util.StringTokenizer;  

2. public class TestStringTokenizer {  
3.     public static void main(String[] args) {  
4.         String str = "Hello,Welcome,To,TpointTech";  

5.         // Constructor 1: Default delimiter (space)  
6.         StringTokenizer st1 = new StringTokenizer("Hello Welcome To TpointTech");  
7.         System.out.println("Tokens using default delimiter:");  
8.         while (st1.hasMoreTokens()) {  
9.             System.out.println(st1.nextToken());  
10.         }  

11.         // Constructor 2: Custom delimiter (,)  
12.         StringTokenizer st2 = new StringTokenizer(str, ",");  
13.         System.out.println("\nTokens using comma as delimiter:");  
14.         while (st2.hasMoreTokens()) {  
15.             System.out.println(st2.nextToken());  
16.         }  

17.         // Constructor 3: Custom delimiter with returnDelims = true  
18.         StringTokenizer st3 = new StringTokenizer(str, ",", true);  
19.         System.out.println("\nTokens including delimiters:");  
20.         while (st3.hasMoreTokens()) {  
21.             System.out.println(st3.nextToken());  
22.         }  
23.     }  
24. }  

**Output:**

Tokens using default delimiter:
Hello
Welcome
To
TpointTech

Tokens using comma as delimiter:
Hello
Welcome
To
TpointTech

Tokens including delimiters:
Hello
,
Welcome
,
To
,
TpointTech

**Explanation:**

- The first constructor uses the **default space delimiter**.
- The second constructor uses a **custom delimiter (comma)** to split the string.
- The third constructor also uses a **comma**, but with returnDelims = true, so the delimiters themselves are returned as tokens.

## Methods of the StringTokenizer Class

The following table shows the commonly used method of StringTokenizer class:

![StringTokenizer in Java](https://d2jdgazzki9vjm.cloudfront.net/core/images/string-tokenizer-in-java2.png "Java - StringTokenizer")

|Methods|Description|
|---|---|
|boolean hasMoreTokens()|It checks if there is more tokens available.|
|String nextToken()|It returns the next token from the StringTokenizer object.|
|String nextToken(String delim)|It returns the next token based on the delimiter.|
|boolean hasMoreElements()|It is the same as hasMoreTokens() method.|
|Object nextElement()|It is the same as nextToken() but its return type is Object.|
|int countTokens()|It returns the total number of tokens.|

## Example of StringTokenizer Class Methods

These examples demonstrate how to use the various methods of the StringTokenizer class.

### Example 1: StringTokenizer.nextToken(String delim) Method

The following example demonstrates how to get the next token from a string using a specified delimiter.

[](https://www.tpointtech.com/string-tokenizer-in-java#)[](https://www.tpointtech.com/string-tokenizer-in-java#)[](https://www.tpointtech.com/string-tokenizer-in-java#)

1. import java.util.*;  

2. public class Test {  
3.    public static void main(String[] args) {  
4.        StringTokenizer st = new StringTokenizer("my,name,is,khan");  

5.       // printing next token  
6.       System.out.println("Next token is : " + st.nextToken(","));  
7.    }      
8. }  

**Output:**

Next token is : my

#### Note: The StringTokenizer class is deprecated now. It is recommended to use the split() method of the String class or the Pattern class from java.util.regex.

### Example 2: StringTokenizer.hasMoreTokens() Method

The following example demonstrates how to check if more tokens are available and iterate through them.

[](https://www.tpointtech.com/string-tokenizer-in-java#)[](https://www.tpointtech.com/string-tokenizer-in-java#)[](https://www.tpointtech.com/string-tokenizer-in-java#)

1. import java.util.StringTokenizer;    
2. public class StringTokenizer1  
3. {    
4.  /* Driver Code */  
5.  public static void main(String args[])  
6.  {    
7.    /* StringTokenizer object */  
8.    StringTokenizer st = new StringTokenizer("Demonstrating methods from StringTokenizer class"," ");    
9.      /* Checks if the String has any more tokens */  
10.      while (st.hasMoreTokens())   
11.      {    
12.          System.out.println(st.nextToken());    
13.      }    
14.  }    
15. }  

**Output:**

Demonstrating
methods
from
StringTokenizer
class

### Example 3: StringTokenizer.hasMoreElements() Method

This method works similarly to hasMoreTokens() but is useful when using the Enumeration interface. Consider the following code:

[](https://www.tpointtech.com/string-tokenizer-in-java#)[](https://www.tpointtech.com/string-tokenizer-in-java#)[](https://www.tpointtech.com/string-tokenizer-in-java#)

1. import java.util.StringTokenizer;    
2. public class StringTokenizer2  
3. {    
4.  public static void main(String args[])  
5.  {    
6.    StringTokenizer st = new StringTokenizer("Hello everyone I am a Java developer"," ");    
7.      while (st.hasMoreElements())   
8.      {    
9.          System.out.println(st.nextToken());    
10.      }    
11.  }    
12. }  

**Output:**

Hello
everyone
I
am
a
Java
developer

### Example 4: StringTokenizer.nextElement() Method

The nextElement() method returns the next token as an Object and can be used with Enumeration. Here is the example code:

[](https://www.tpointtech.com/string-tokenizer-in-java#)[](https://www.tpointtech.com/string-tokenizer-in-java#)[](https://www.tpointtech.com/string-tokenizer-in-java#)

1. import java.util.StringTokenizer;    
2. public class StringTokenizer3  
3. {    
4.  /* Driver Code */  
5.  public static void main(String args[])  
6.  {    
7.    /* StringTokenizer object */  
8.    StringTokenizer st = new StringTokenizer("Hello Everyone Have a nice day"," ");    
9.      /* Checks if the String has any more tokens */  
10.      while (st.hasMoreTokens())   
11.      {    
12.          /* Prints the elements from the String */  
13.          System.out.println(st.nextElement());    
14.      }    
15.  }    
16. }  

**Output:**

Hello
Everyone
Have
a
nice
day

### Example 5: StringTokenizer.countTokens() Method

This method counts the total number of tokens in the string. The following example demonstrates the same:

[](https://www.tpointtech.com/string-tokenizer-in-java#)[](https://www.tpointtech.com/string-tokenizer-in-java#)[](https://www.tpointtech.com/string-tokenizer-in-java#)

1. import java.util.StringTokenizer;    
2. public class StringTokenizer3  
3. {    
4.  /* Driver Code */  
5.  public static void main(String args[])  
6.  {    
7.    /* StringTokenizer object */  
8.    StringTokenizer st = new StringTokenizer("Hello Everyone Have a nice day"," ");    
9.          /* Prints the number of tokens present in the String */  
10.          System.out.println("Total number of Tokens: "+st.countTokens());    
11.  }    
12. }  

**Output:**

Total number of Tokens: 6