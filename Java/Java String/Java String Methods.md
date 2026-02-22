In [Java](https://www.tpointtech.com/java-tutorial), the [String](https://www.tpointtech.com/java-string) class represents a sequence of characters. It is a fundamental part of the language that is used extensively for storing and manipulating text data. It has many built-in methods that help us to do string manipulations like, cutting parts of a sentence, joining two pieces of text, changing the format, checking if two texts are the same or replacing one word with another.

## Java String Class Methods

The java.lang.String class provides many useful methods to perform operations on sequence of char values.

|Method|Description|
|---|---|
|[char charAt(int index)](https://www.tpointtech.com/java-string-charat)|It returns char value for the particular index|
|[int length()](https://www.tpointtech.com/java-string-length)|It returns string length|
|[static String format(String format, Object... args)](https://www.tpointtech.com/java-string-format)|It returns a formatted string.|
|[static String format(Locale l, String format, Object... args)](https://www.tpointtech.com/java-string-format)|It returns formatted string with given locale.|
|[String substring(int beginIndex)](https://www.tpointtech.com/java-string-substring)|It returns substring for given begin index.|
|[String substring(int beginIndex, int endIndex)](https://www.tpointtech.com/java-string-substring)|It returns substring for given begin index and end index.|
|[boolean contains(CharSequence s)](https://www.tpointtech.com/java-string-contains)|It returns true or false after matching the sequence of char value.|
|[static String join(CharSequence delimiter, CharSequence... elements)](https://www.tpointtech.com/java-string-join)|It returns a joined string.|
|[static String join(CharSequence delimiter, Iterable<? extends CharSequence> elements)](https://www.tpointtech.com/java-string-join)|It returns a joined string.|
|[boolean equals(Object another)](https://www.tpointtech.com/java-string-equals)|It checks the equality of string with the given object.|
|[boolean isEmpty()](https://www.tpointtech.com/java-string-isempty)|It checks if string is empty.|
|[String concat(String str)](https://www.tpointtech.com/java-string-concat)|It concatenates the specified string.|
|[String replace(char old, char new)](https://www.tpointtech.com/java-string-replace)|It replaces all occurrences of the specified char value.|
|[String replace(CharSequence old, CharSequence new)](https://www.tpointtech.com/java-string-replace)|It replaces all occurrences of the specified CharSequence.|
|[static String equalsIgnoreCase(String another)](https://www.tpointtech.com/java-string-equalsignorecase)|It compares another string. It doesn't check case.|
|[String[] split(String regex)](https://www.tpointtech.com/java-string-split)|It returns a split string-matching regex.|
|[String[] split(String regex, int limit)](https://www.tpointtech.com/java-string-split)|It returns a split string-matching regex and limit.|
|[String intern()](https://www.tpointtech.com/java-string-intern)|It returns an interned string.|
|[int indexOf(int ch)](https://www.tpointtech.com/java-string-indexof)|It returns the specified char value index.|
|[int indexOf(int ch, int fromIndex)](https://www.tpointtech.com/java-string-indexof)|It returns the specified char value index starting with given index.|
|[int indexOf(String substring)](https://www.tpointtech.com/java-string-indexof)|It returns the specified substring index.|
|[int indexOf(String substring, int fromIndex)](https://www.tpointtech.com/java-string-indexof)|It returns the specified substring index starting with given index.|
|[String toLowerCase()](https://www.tpointtech.com/java-string-tolowercase)|It returns a string in lowercase.|
|[String toLowerCase(Locale l)](https://www.tpointtech.com/java-string-tolowercase)|It returns a string in lowercase using specified locale.|
|[String toUpperCase()](https://www.tpointtech.com/java-string-touppercase)|It returns a string in uppercase.|
|[String toUpperCase(Locale l)](https://www.tpointtech.com/java-string-touppercase)|It returns a string in uppercase using specified locale.|
|[String trim()](https://www.tpointtech.com/java-string-trim)|It removes beginning and ending spaces of this string.|
|[static String valueOf(int value)](https://www.tpointtech.com/java-string-valueof)|It converts given type into string. It is an overloaded method.|

## Java String Methods Example

### Java String.toUpperCase() and String.toLowerCase() Method

The String.toUpperCase() method converts the String into uppercase and the String.toLowerCase() method converts the String into lowercase.

### Example

[](https://www.tpointtech.com/java-string-methods#)[](https://www.tpointtech.com/java-string-methods#)[](https://www.tpointtech.com/java-string-methods#)

1. public class Main {  
2.     public static void main(String ar[]) {  
3.         String s = "Computer";  
4.         System.out.println(s.toUpperCase());  
5.         System.out.println(s.toLowerCase());  
6.         System.out.println(s);  
7.     }  
8. }  

**Output:**

COMPUTER
computer
Computer

### Java String.trim() Method

The method eliminates white spaces before and after the String.

### Example

[](https://www.tpointtech.com/java-string-methods#)[](https://www.tpointtech.com/java-string-methods#)[](https://www.tpointtech.com/java-string-methods#)

1. public class Main {  
2.     public static void main(String ar[]) {  
3.         String s = "  computer ";  
4.         System.out.println(s);  
5.         System.out.println(s.trim());  
6.     }  
7. }  

**Output:**

computer
computer

### Java String.startsWith() and String.endsWith() Method

The String.startsWith() method checks whether the String starts with the letters passed as arguments and String.endsWith() method checks whether the String ends with the letters passed as arguments.

### Example

[](https://www.tpointtech.com/java-string-methods#)[](https://www.tpointtech.com/java-string-methods#)[](https://www.tpointtech.com/java-string-methods#)

1. public class Main {  
2.     public static void main(String ar[]) {  
3.         String s = "Computer";  
4.         System.out.println(s.startsWith("C"));// true  
5.         System.out.println(s.endsWith("r"));// true  
6.     }  
7. }  

**Output:**

true
true

### Java String.charAt() Method

The String.charAt() method returns a character at specified index.

### Example

[](https://www.tpointtech.com/java-string-methods#)[](https://www.tpointtech.com/java-string-methods#)[](https://www.tpointtech.com/java-string-methods#)

1. public class Main {  
2.     public static void main(String ar[]) {  
3.         String s = "Laptop";  
4.         System.out.println(s.charAt(2));// S  
5.         System.out.println(s.charAt(1));// h  
6.     }  
7. }  

**Output:**

p
a

### Java String.length() Method

The String.length() method returns length of the specified String.

### Example

[](https://www.tpointtech.com/java-string-methods#)[](https://www.tpointtech.com/java-string-methods#)[](https://www.tpointtech.com/java-string-methods#)

1. public class Main {  
2.     public static void main(String ar[]) {  
3.         String s = "Lamborghini";  
4.         System.out.println(s.length());  
5.     }  
6. }  

**Output:**

11

## Java String.intern() Method

A pool of strings, initially empty, is maintained privately by the class String.

When the intern method is invoked, if the pool already contains a String equal to this String object as determined by the equals(Object) method, then the String from the pool is returned. Otherwise, this String object is added to the pool and a reference to this String object is returned.

### Example

[](https://www.tpointtech.com/java-string-methods#)[](https://www.tpointtech.com/java-string-methods#)[](https://www.tpointtech.com/java-string-methods#)

1. public class Main {  
2.     public static void main(String ar[]) {  
3.         String s = new String("Apple");  
4.         String s2 = s.intern();  
5.         System.out.println(s2);  
6.     }  
7. }  

**Output:**

Apple

### Java String.valueOf() Method

The String.valueOf() method coverts given type such as int, long, float, double, boolean, char and char array into String.

### Example

[](https://www.tpointtech.com/java-string-methods#)[](https://www.tpointtech.com/java-string-methods#)[](https://www.tpointtech.com/java-string-methods#)

1. public class Main {  
2.     public static void main(String ar[]) {  
3.         int a = 10;  
4.         String s = String.valueOf(a);  
5.         System.out.println(s + 10);  
6.     }  
7. }  

**Output:**

1010

### Java String.replace() Method

The String.replace() method replaces all occurrence of first sequence of character with second sequence of character.

### Example

[](https://www.tpointtech.com/java-string-methods#)[](https://www.tpointtech.com/java-string-methods#)[](https://www.tpointtech.com/java-string-methods#)

1. public class Main {  
2.     public static void main(String ar[]) {  
3.         String s1 = "Java is a programming language. Java is a platform. Java is an Island.";  
4.         String replaceString = s1.replace("Java", "Kava");// replaces all occurrences of "Java" to "Kava"  
5.         System.out.println(replaceString);  
6.     }  
7. }  

**Output:**

Kava is a programming language. Kava is a platform. Kava is an Island.