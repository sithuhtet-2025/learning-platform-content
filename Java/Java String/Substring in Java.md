A substring is a part of a string, or in other words, a subset of another string. In Java, extracting substrings is a common operation used for text processing, data validation, and string manipulation. Java provides built-in methods that make it easy to extract substrings using index values or delimiters.

For example, if the string is "**computer**", possible substrings include "**com**", "compu", "ter", and more.

#### Note: String index positions start from 0.

You can find a substring from a given string in Java using the following methods:

- Using substring(int startIndex)
- Using String.split() method
- Using String.indexOf() along with substring()

## Finding Substring Using substring() Method

The **substring()** method of the String class is used to extract a part of a string based on index positions. In this method:

- startIndex is **inclusive**
- endIndex is **exclusive**

### Syntax

It has the following syntax:

[](https://www.tpointtech.com/substring-in-java#)[](https://www.tpointtech.com/substring-in-java#)[](https://www.tpointtech.com/substring-in-java#)

1. public String substring(int startIndex)  

This method returns a new string starting from the specified startIndex to the end of the string. It throws an IndexOutOfBoundsException if startIndex is less than 0 or greater than the string length.

[](https://www.tpointtech.com/substring-in-java#)[](https://www.tpointtech.com/substring-in-java#)[](https://www.tpointtech.com/substring-in-java#)

1. public String substring(int startIndex, int endIndex)  

This method returns a new string starting from startIndex and ending at endIndex. It throws an IndexOutOfBoundsException if startIndex is less than 0, greater than endIndex, or if endIndex exceeds the string length.

### Understanding startIndex and endIndex

Let's understand the startIndex and endIndex by the code given below.

[](https://www.tpointtech.com/substring-in-java#)[](https://www.tpointtech.com/substring-in-java#)[](https://www.tpointtech.com/substring-in-java#)

1. String s = "hello";  
2. System.out.println(s.substring(0, 2)); // returns "he"  

Here, 0 points to the first character and 2 points to the character e. Since the end index is exclusive, only characters at index 0 and 1 are included.

### Example

The following example demonstrates finding substrings using substring() method.

[](https://www.tpointtech.com/substring-in-java#)[](https://www.tpointtech.com/substring-in-java#)[](https://www.tpointtech.com/substring-in-java#)

1. public class TestSubstring {  
2.     public static void main(String args[]) {  
3.         String s = "SachinTendulkar";  

4.         System.out.println("Original String: " + s);  
5.         System.out.println("Substring starting from index 6: " + s.substring(6));  
6.         System.out.println("Substring starting from index 0 to 6: " + s.substring(0, 6));  
7.     }  
8. }  

**Output:**

Original String: SachinTendulkar
Substring starting from index 6: Tendulkar
Substring starting from index 0 to 6: Sachin

The above program demonstrates both variants of the substring() method, where the start index is inclusive and the end index is exclusive.

## Finding Substring Using String.split() Method

The **split()** method of the String class can also be used to extract substrings by dividing a string based on a delimiter or regular expression. It returns an array of strings.

### Syntax

Here is the syntax to use String.split() method for finding substring:

[](https://www.tpointtech.com/substring-in-java#)[](https://www.tpointtech.com/substring-in-java#)[](https://www.tpointtech.com/substring-in-java#)

1. public String[] split(String regex)  

This method splits the given string around matches of the specified regular expression and returns an array of substrings.

[](https://www.tpointtech.com/substring-in-java#)[](https://www.tpointtech.com/substring-in-java#)[](https://www.tpointtech.com/substring-in-java#)

1. public String[] split(String regex, int limit)  

This overloaded version splits the string based on the given regular expression and limits the number of resulting substrings.

### Example

The following example demonstrates finding substring using the split() method.

[](https://www.tpointtech.com/substring-in-java#)[](https://www.tpointtech.com/substring-in-java#)[](https://www.tpointtech.com/substring-in-java#)

1. import java.util.*;  

2. public class TestSubstring2 {  
3.     public static void main(String args[]) {  
4.         String text = "Hello, My name is Sachin";  
5.         String[] sentences = text.split(",");  

6.         System.out.println(Arrays.toString(sentences));  
7.     }  
8. }  

**Output:**

[Hello, My name is Sachin]

In this example, the split() method separates the string based on the comma delimiter and stores the resulting substrings in an array.

## Finding Substring Using String.indexOf() along with substring()

This approach can also be used to find the position of a specific character or word in a string using the **indexOf()** method and then extracts the required part using the **substring()** method. It is useful when you know what text you want to start or end the substring with, rather than fixed index values.

### Syntax

It has the following syntax:

[](https://www.tpointtech.com/substring-in-java#)[](https://www.tpointtech.com/substring-in-java#)[](https://www.tpointtech.com/substring-in-java#)

1. int index = str.indexOf(searchValue);  
2. String sub = str.substring(startIndex, endIndex);  

### Example

The following example demonstrates finding substring using String.indexOf() along with substring() method.

[](https://www.tpointtech.com/substring-in-java#)[](https://www.tpointtech.com/substring-in-java#)[](https://www.tpointtech.com/substring-in-java#)

1. public class TestSubstring {  
2.     public static void main(String[] args) {  
3.         String s = "Java Programming Language";  

4.         int index = s.indexOf("Programming");  
5.         String result = s.substring(index);  

6.         System.out.println(result);  
7.     }  
8. }  

**Output:**

Programming Language

In this example, indexOf() locates the starting position of the word "Programming", and substring() extracts the string from that position to the end.