Computer systems internally store data in binary representation. A character is stored using a combination of 0's and 1's. The process is called encoding. A character encoding scheme is important because it helps to represent the same information on multiple types of devices.

## Types of Encoding

Following are the different types of encoding used before the Unicode system.

- ASCII (American Standard Code for Information Interchange): used for the United States
- ISO 8859-1 used for the Western European Languages
- KOI-8 used for Russian
- GB18030 and BIG-5 used for Chinese and so on.
- Base64 used for binary to text encoding

## Why does Java use Unicode System?

There were a few limitations to the encoding techniques used before the Unicode system.

1. In every language, different letters are present and the code assigned to every letter is also different which means multiple languages have multiple codes for various letters.
2. Certain languages have many character sets, the code assigned to each character may vary in terms of length. For example, some character can be encoded with a single byte, other might require two or more bytes.

These problems led to finding a better solution for character encoding that is Unicode System.

## What is Unicode System?

- Unicode system is an international character encoding technique that can represent most of the languages around the world.
- Unicode System is established by Unicode Consortium.
- Hexadecimal values are used to represent Unicode characters.
- There are multiple Unicode Transformation Formats:
    1. UTF-8: It represents 8-bits (1 byte) long character encoding.
    2. UTF-16: It represents 16-bits (2 bytes) long character encoding
    3. UTF-32: It represents 32-bits (4 bytes) long character encoding.
- To access a Unicode character the format starts with an escape sequence \u followed by 4 digits hexadecimal value.
- A Unicode character has a range of possible values starting from \u0000 to \uFFFF.
- Some of the Unicode characters are  
    \u00A9 represent the copyright symbol - ©  
    \u0394 represent the capital Greek letter delta - Δ  
    \u0022 represent a double quote - "

## Java Unicode Example

### Example

[](https://www.tpointtech.com/unicode-system-in-java#)[](https://www.tpointtech.com/unicode-system-in-java#)[](https://www.tpointtech.com/unicode-system-in-java#)

1. public class Main {  
2.    public static void main (String[]args) {            
3.       //Unicode characters  
4.       char a = '\u0041';  
5.       char b = '\u0042';  

6.       // printing unicode  
7.       System.out.println("a = " + a);  
8.       System.out.println("b = " + b);  
9.    }  
10. }  

**Output:**

A
B

### Program to convert UTF-8 to Unicode

**UnicodeDemo.java**

[](https://www.tpointtech.com/unicode-system-in-java#)[](https://www.tpointtech.com/unicode-system-in-java#)[](https://www.tpointtech.com/unicode-system-in-java#)

1. public class UnicodeDemo   
2. {  
3.    public static void main(String ar[]) throws Exception   
4.    {  
5.       String str1 = "Unicode Sytem\u00A9";  
6.       byte[] charset = str1.getBytes("UTF-8");  
7.       String newstr = new String(charset, "UTF-8");  
8.       System.out.println(newstr);  
9.    }  
10. }  

**Output:**

Unicode Sytem©

In the above code, a Class **_UnicodeDemo_** is created. At the start, a Unicode String **_str1_** is converted into a UTF-8 form using the **_getBytes()_** method. After that, the byte array is again converted into Unicode and the value of **_newstr_** is displayed on the console.

### Problem Caused by Unicode

The Unicode standard was designed to represent 16-bit character encoding. It was supposed to be capable of representing all the characters in the world using the primitive data type char. But the 16-bits encoding was able to represent only 65,536 characters that were not sufficient for all the characters available around the world.

So, the Unicode system was extended up to 1,112,064 characters. The characters that are larger than 16-bits are called **_Supplementary characters_** and are defined by Java using a pair of _char_ values.

In this article, we have discussed basic methods of encoding, Unicode System in Java, problems caused by Unicode system, and a Java program for demonstrating the use of Unicode system.