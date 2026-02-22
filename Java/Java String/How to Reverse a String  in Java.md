Reversing a string is one of the most common string manipulation tasks in Java. Java provides multiple ways to reverse a string, ranging from built-in classes to manual logic using loops and recursion. In this chapter, we will explore different ways to reverse a string in Java with practical examples.

## Reversing String Using StringBuilder / StringBuffer Class

[StringBuilder](https://www.tpointtech.com/stringbuilder-in-java) and [StringBuffer](https://www.tpointtech.com/stringbuffer-in-java) provide a built-in **reverse()** method that efficiently reverses the characters of a string. This is the simplest and most commonly used approach because it requires minimal code and offers good performance. StringBuilder is preferred in single-threaded environments, while StringBuffer is thread-safe.

### Example

The following example demonstrates reversing string using StringBuilder / StringBuffer class:

[](https://www.tpointtech.com/how-to-reverse-a-string-in-java#)[](https://www.tpointtech.com/how-to-reverse-a-string-in-java#)[](https://www.tpointtech.com/how-to-reverse-a-string-in-java#)

1. public class StringFormatter {  
2.     public static String reverseString(String str) {  
3.         StringBuilder sb = new StringBuilder(str);  
4.         sb.reverse();  
5.         return sb.toString();  
6.     }  
7. }  

8. public class TestStringFormatter {  
9.     public static void main(String[] args) {  
10.         System.out.println(StringFormatter.reverseString("my name is khan"));  
11.         System.out.println(StringFormatter.reverseString("I am sonoo jaiswal"));  
12.     }  
13. }  

**Output:**

nahk si eman ym
lawsiaj oonos ma I

## Reversing String Using Reverse Iteration

In this approach, the string is converted into a character array, and characters are appended in reverse order using a loop. This method helps in understanding how strings work internally and is useful when you want full control over the reversal logic without using built-in methods.

### Example

The following example demonstrates reversing string using reverse iteration:

[](https://www.tpointtech.com/how-to-reverse-a-string-in-java#)[](https://www.tpointtech.com/how-to-reverse-a-string-in-java#)[](https://www.tpointtech.com/how-to-reverse-a-string-in-java#)

1. public class StringFormatter {  
2.     public static String reverseString(String str) {  
3.         char ch[] = str.toCharArray();  
4.         String rev = "";  
5.         for (int i = ch.length - 1; i >= 0; i--) {  
6.             rev += ch[i];  
7.         }  
8.         return rev;  
9.     }  
10. }  

**Output:**

nahk si eman ym
lawsiaj oonos ma I

## Reversing String Using StringBuilder with Manual Iteration

Here, a **StringBuilder** is used, but instead of calling **reverse()**, characters are appended manually from the end of the string to the beginning.

### Example

The following example demonstrates reversing string using StringBuilder with manual iteration:

[](https://www.tpointtech.com/how-to-reverse-a-string-in-java#)[](https://www.tpointtech.com/how-to-reverse-a-string-in-java#)[](https://www.tpointtech.com/how-to-reverse-a-string-in-java#)

1. public static String reverseWithStringBuilder(String str) {  
2.     StringBuilder stringBuilder = new StringBuilder();  
3.     for (int i = str.length() - 1; i >= 0; i--) {  
4.         stringBuilder.append(str.charAt(i));  
5.     }  
6.     return stringBuilder.toString();  
7. }  

**Output:**

!dlrow ,olleH

## Reversing String Using a Character Array

This method reverses a string by swapping characters in a character array using two pointers - one from the start and one from the end. It is memory-efficient and commonly used to demonstrate in-place reversal techniques.

### Example

The following example demonstrates reversing string using a character array:

[](https://www.tpointtech.com/how-to-reverse-a-string-in-java#)[](https://www.tpointtech.com/how-to-reverse-a-string-in-java#)[](https://www.tpointtech.com/how-to-reverse-a-string-in-java#)

1. public static String reverseWithCharArray(String str) {  
2.     char[] charArray = str.toCharArray();  
3.     int start = 0;  
4.     int end = str.length() - 1;  

5.     while (start < end) {  
6.         char temp = charArray[start];  
7.         charArray[start] = charArray[end];  
8.         charArray[end] = temp;  
9.         start++;  
10.         end--;  
11.     }  
12.     return new String(charArray);  
13. }  

**Output:**

gnimmargorP avaJ

## Reversing String Using Recursion

The recursive approach reverses a string by breaking it down into smaller substrings. The method calls itself with a reduced string and appends characters during the return phase.

### Example

The following example demonstrates reversing string using recursion:

[](https://www.tpointtech.com/how-to-reverse-a-string-in-java#)[](https://www.tpointtech.com/how-to-reverse-a-string-in-java#)[](https://www.tpointtech.com/how-to-reverse-a-string-in-java#)

1. public static String reverseWithRecursion(String str) {  
2.     if (str.isEmpty()) {  
3.         return str;  
4.     }  
5.     return reverseWithRecursion(str.substring(1)) + str.charAt(0);  
6. }  

**Output:**

gnimmargorP avaJ