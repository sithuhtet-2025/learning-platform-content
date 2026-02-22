In Java, strings can be compared based on their **content** or their **references**. String comparison checks whether two strings have the same sequence of characters, while reference comparison checks whether both variables point to the same object in memory.

Java string comparison is commonly used for authentication using the equals() method, sorting using the compareTo() method, and reference matching using the == operator.

The following are the different ways to compare strings:

- Using equals() Method
- Using == Operator
- Using compareTo() Method
- Using startsWith() and endsWith() Methods

## Comparing Strings Using equals() Method

The String class equals() method compares the original content of the string. It compares values of string for equality. String class provides the following two methods: Additionally, the equalsIgnoreCase() method performs a case-insensitive comparison.

String class provides the following two methods:

- **public boolean equals(Object another)** compares this string to the specified object.
- **public boolean equalsIgnoreCase(String another)** compares this string to another string, ignoring case.

![Java String compare](https://d2jdgazzki9vjm.cloudfront.net/core/images/string-comparison-in-java2.png)

### Example: Comparing Strings Without Ignoring Case

The following example demonstrates string comparison using the equals() method without ignoring case.

[](https://www.tpointtech.com/string-comparison-in-java#)[](https://www.tpointtech.com/string-comparison-in-java#)[](https://www.tpointtech.com/string-comparison-in-java#)

1. class StringComparisonUsingEqualsMethod{  
2.  public static void main(String args[]){  
3.    String s1="Sachin";  
4.    String s2="Sachin";  
5.    String s3=new String("Sachin");  
6.    String s4="Saurav";  
7.    System.out.println(s1.equals(s2));//true  
8.    System.out.println(s1.equals(s3));//true  
9.    System.out.println(s1.equals(s4));//false  
10.  }  
11. }  

**Output:**

true
true
false

**Explanation**

S1 and S2 relate to the same string pool object since they are string literals. As a result, s1.equals(s2) gives true. Despite S3 being developed with the new keyword, S1 and S3 had the same content. Since only the content is compared using the equals() method, s1.equals(s3) is true; however, s1.equals(s4) is false because the contents of s1 and s4 differ.

In the above program, the methods of **String** class are used. The **equals()** method returns true if String objects are matching and both strings are of same case. **equalsIgnoreCase()** returns true regardless of cases of strings.

### Example: Comparing Strings With Ignoring Case

The following example demonstrates string comparison using the equals() method with ignoring case.

[](https://www.tpointtech.com/string-comparison-in-java#)[](https://www.tpointtech.com/string-comparison-in-java#)[](https://www.tpointtech.com/string-comparison-in-java#)

1. class  StringComparisonUsingequalsIgnoreCase {  
2.     public static void main(String[] args) {  
3.         String s1 = "Ram";  
4.         String s2 = "rAm";  
5.         // Using equals() method for case-sensitive comparison  
6.         boolean equalsResult = s1.equals(s2);  
7.         System.out.println("Using equals() method: " + equalsResult); // Output: false  
8.         // Using equalsIgnoreCase() method for case-insensitive comparison  
9.         boolean equalsIgnoreCaseResult = s1.equalsIgnoreCase(s2);  
10.         System.out.println("Using equalsIgnoreCase() method: " + equalsIgnoreCaseResult); // Output: true  
11.     }  
12. }  

**Output:**

false
true

**Explanation**

There are two strings specified, s1 and s2, with distinct cases ("Ram" and "rAm").

Use the equals() function to compare s1 and s2. Because the cases are different, this method compares them in a case-sensitive fashion and returns false.

The comparison between strings s1 and s2 is performed using the equalsIgnoreCase() function. Because it treats the material equally and ignores case distinctions, this function returns true.

## Comparing Strings Using Equal To (==) Operator

In Java, the == operator compares references rather than values.

![Java String compare](https://d2jdgazzki9vjm.cloudfront.net/core/images/string-comparison-in-java3.png)

### Example

The following example demonstrates string comparison using the equal to (==) operator.

[](https://www.tpointtech.com/string-comparison-in-java#)[](https://www.tpointtech.com/string-comparison-in-java#)[](https://www.tpointtech.com/string-comparison-in-java#)

1. class StringCompare {  
2.     public static void main(String[] args) {  
3.         String s1 = "Kohli";  
4.         String s2 = "Kohli";  
5.         String s3 = new String("Kohli");  
6.         System.out.println(s1 == s2);              // true   
7.         System.out.println(s1 == s3);              // false  
8.     }  
9. }  

**Output:**

true
false

## Comparing Strings Using compareTo() Method

The String class compareTo() method compares values lexicographically and returns an integer value that describes if first string is less than, equal to or greater than second string.

Suppose s1 and s2 are two String objects. If:

- **s1 == s2** : The method returns 0.
- **s1 > s2** : The method returns a positive value.
- **s1 < s2** : The method returns a negative value.

### Example

The following example demonstrates string comparison using the compareTo() method.

[](https://www.tpointtech.com/string-comparison-in-java#)[](https://www.tpointtech.com/string-comparison-in-java#)[](https://www.tpointtech.com/string-comparison-in-java#)

1. class StringComparisonUsingComapreto {  
2.     public static void main(String[] args) {  
3.        String str1 = "Sachin";  
4.         String str2 = "Sachin";  
5.         String str3 = "Ratan";  
6.         System.out.println(str1.compareTo(str2));      // 0  
7.         System.out.println(str1.compareTo(str3));      // 1 (str1 > str3)  
8.         System.out.println(str3.compareTo(str1));      // -1 (str3 < str1)  
9.     }  
10. }  

**Output:**

0
1
-1

**Explanation**

The content of str1 and str2 is the same-"Sachin," while str3 has the word "Ratan."

## Comparing Strings Using startsWith() and endsWith() Methods

If a string starts with a prefix and ends with a suffix, respectively, it may be determined using the methods startsWith() and endsWith().

### Example

The following example demonstrates string comparison using startsWith() and endsWith() methods.

[](https://www.tpointtech.com/string-comparison-in-java#)[](https://www.tpointtech.com/string-comparison-in-java#)[](https://www.tpointtech.com/string-comparison-in-java#)

1. class StringCompare {  
2.     public static void main(String[] args) {  
3.         String str = "String Compare";  
4.         System.out.println(str.startsWith("String")); // true  
5.         System.out.println(str.endsWith("Compare"));  // true  
6.     }  
7. }  

**Output:**

true
true

**Explanation**

startsWith("Hello") returns true if the string begins with the given prefix.

endsWith("World!") returns true if the string does, in fact, conclude with the designated suffix.