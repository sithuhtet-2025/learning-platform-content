In the C# programming language, a string is an object of System.String class that represents a sequence of characters. A string variable holds a sequence of characters enclosed by double quotes. It is defined by using the string keyword. It can perform many operations on strings, such as concatenation, comparison, getting a substring, search, trimming, replacement, etc. It is also commonly utilized in applications that involve text processing, user input, file I/O, and data formatting.

![C# Strings](https://images.tpointtech.com/cpp/images/c-sharp-strings.png)

For example, when we write a message on our smartphone, such as "Hello, John", the phone internally stores this message as a string. Similarly, an email address like john@gmail.com is also a string because it is a series of characters.

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-strings#)[](https://www.tpointtech.com/c-sharp-strings#)[](https://www.tpointtech.com/c-sharp-strings#)

1. string variableName = "Your text here";  

In this syntax,

- **String:** It is the keyword that is used to define the string variable.
- **VariableName:** It is defined by the name of the variable.

## Declaring and Initializing a String in C#

Several ways to declare and initialize a string in [C#](https://www.tpointtech.com/c-sharp-tutorial).

### Declaration without initialization

If we want to declare a string using simple and System.String, we can use the following syntax:

[](https://www.tpointtech.com/c-sharp-strings#)[](https://www.tpointtech.com/c-sharp-strings#)[](https://www.tpointtech.com/c-sharp-strings#)

1. string myString1;  

2. // Declaration using System.String.  
3. System.String myString2;  

**Initializing with a string literal**

If we want to initialize a string with a string literal, we can use the following syntax:

[](https://www.tpointtech.com/c-sharp-strings#)[](https://www.tpointtech.com/c-sharp-strings#)[](https://www.tpointtech.com/c-sharp-strings#)

1. string myString3 = "Welcome to Tpoint tech";  

**String Initialization using Local Variables**

Using var, we can create a string with implicit typing:

[](https://www.tpointtech.com/c-sharp-strings#)[](https://www.tpointtech.com/c-sharp-strings#)[](https://www.tpointtech.com/c-sharp-strings#)

1. var localString = "Still a strongly-typed string.";  

**String Initialization using a Constructor**

In C#, a string constructor may create a string from a char*, char[], or sbyte*.

[](https://www.tpointtech.com/c-sharp-strings#)[](https://www.tpointtech.com/c-sharp-strings#)[](https://www.tpointtech.com/c-sharp-strings#)

1. char [] source = {'X', 'Y', 'Z'};  
2. string myString4 = new string (source);  

### C# Simple String Example

Let us take an example to illustrate the string in C#.

### Example

[](https://www.tpointtech.com/c-sharp-strings#)[](https://www.tpointtech.com/c-sharp-strings#)[](https://www.tpointtech.com/c-sharp-strings#)

1. using System;    
2. public class StringExample    
3. {    
4.     public static void Main(string[] args)    
5.     {    
6.         string s1 = "hello";    

7.         char[] ch = { 'c', 's', 'h', 'a', 'r', 'p' };    
8.         string s2 = new string(ch);    

9.         Console.WriteLine(s1);    
10.         Console.WriteLine(s2);    
11.     }    
12. }   

**Output:**

hello
csharp

**Explanation:**

In this example, we have taken two ways to create strings in C#. Here, the first string s1 is created using a string literal, while the second string s2 is created from a character array using the new string() constructor. Finally, it shows the result of both strings: hello and csharp.

## Characteristics of Strings

There are several characteristics of strings in C#. Some of them are as follows.

- **Immutable:** In the C# programming language, strings are immutable, which means that they can't be modified after creation.
- **Reference Type:** Strings are a reference type, but they act as a value type in some scenarios.
- **Unicode Support:** Strings have Unicode characters, which allows support for multiple languages.
- **Null and Embedded Null:** Strings can be null, which means that it doesn't represent any value, or they can contain an embedded null character (\0).
- **Operator Overloading:** Strings support the operator overloading, such as (+) for concatenation and (==) for comparison.

## C# String Class

In the C# programming language, the string class is a built-in class that represents a string of characters. It is part of the System.namespace and is a reference type. The String class provides various properties and methods for creating, manipulating, and comparing strings efficiently.

## C# String Methods

The following table represents several types of methods in the C# programming language.

|Method Name|Description|
|---|---|
|[Clone()](https://www.tpointtech.com/csharp-string-clone)|It is used to return a reference to the instance of String.|
|[Compare(String, String)](https://www.tpointtech.com/csharp-string-compare)|It is used to compare two specified String objects. It returns an integer that indicates their relative position in the sort order.|
|[CompareOrdinal(String, String)](https://www.tpointtech.com/csharp-string-compareordinal)|It is used to compare two specified String objects by evaluating the numeric values of the corresponding Char objects in each string..|
|[CompareTo(String)](https://www.tpointtech.com/csharp-string-compareto)|It is used to compare the instance with a specified String object. It indicates whether this instance precedes, follows, or appears in the same position in the sort order as the specified string.|
|[Concat(String, String)](https://www.tpointtech.com/csharp-string-concat)|It is used to concatenate two specified instances of String.|
|[Contains(String)](https://www.tpointtech.com/csharp-string-contains)|It is used to return a value, which indicates whether a specified substring occurs within this string.|
|[Copy(String)](https://www.tpointtech.com/csharp-string-copy)|It is used to create a new instance of String with the same value as a specified String.|
|[CopyTo(Int32, Char[], Int32, Int32)](https://www.tpointtech.com/csharp-string-copyto)|It is used to copy a specified number of characters from a specified position in the instance to a specified position in an array of Unicode characters.|
|[EndsWith(String)](https://www.tpointtech.com/csharp-string-endswith)|It is used to check that the end of the string instance matches the specified string.|
|[Equals(String, String)](https://www.tpointtech.com/csharp-string-equals)|It is used to determine that two specified String objects have the same value.|
|[Format(String, Object)](https://www.tpointtech.com/csharp-string-format)|It is used to replace one or more format items in a specified string with the string representation of a specified object.|
|[GetEnumerator()](https://www.tpointtech.com/csharp-string-getenumerator)|It is used to retrieve an object that can iterate through the individual characters in this string.|
|[GetHashCode()](https://www.tpointtech.com/csharp-string-gethashcode)|It returns the hash code for the string.|
|[GetType()](https://www.tpointtech.com/csharp-string-gettype)|It is used to get the Type of the current instance.|
|[GetTypeCode()](https://www.tpointtech.com/csharp-string-gettypecode)|It is used to return the TypeCode for the class String.|
|[IndexOf(String)](https://www.tpointtech.com/csharp-string-indexof)|It is used to report the zero-based index of the first occurrence of the specified string in the instance.|
|[Insert(Int32, String)](https://www.tpointtech.com/csharp-string-insert)|It is used to return a new string in which a specified string is inserted at a specified index position.|
|[Intern(String)](https://www.tpointtech.com/csharp-string-intern)|It is used to retrieve the system's reference to the specified String.|
|[IsInterned(String)](https://www.tpointtech.com/csharp-string-isinterned)|It is used to retrieve a reference to a specified String.|
|[IsNormalized()](https://www.tpointtech.com/csharp-string-isnormallize)|It is used to indicate that the string is in Unicode normalization form C.|
|[IsNullOrEmpty(String)](https://www.tpointtech.com/csharp-string-isnullorempty)|It is used to indicate that the specified string is **null** or an Empty string.|
|[IsNullOrWhiteSpace(String)](https://www.tpointtech.com/csharp-string-isnullorwhitespace)|It is used to indicate whether a specified string is **null**, empty, or consists only of white-space characters.|
|[Join(String, String[])](https://www.tpointtech.com/csharp-string-join)|It is used to concatenate all the elements of a string array, using the specified separator between each element.|
|[LastIndexOf(Char)](https://www.tpointtech.com/csharp-string-lastindexof)|It is used to report the zero-based index position of the last occurrence of a specified character within a String.|
|[LastIndexOfAny(Char[])](https://www.tpointtech.com/csharp-string-lastindexofany)|It is commonly utilized to return the zero-based index of the last occurrence of any character from the specified character array within the string. If none of the characters are found, it returns -1.|
|[Normalize()](https://www.tpointtech.com/csharp-string-normalize)|It is commonly utilized to return a new string with the same textual content, but its binary representation is normalized according to a specified Unicode normalization form.|
|[PadLeft(Int32)](https://www.tpointtech.com/csharp-string-padleft)|It is used to return a new string that right-aligns the characters of the original string by padding them with spaces on the left.|
|[PadRight(Int32)](https://www.tpointtech.com/csharp-string-padright)|It is used to return a new string that left-aligns the characters of the original string by padding them with spaces on the right.|
|[Remove(Int32)](https://www.tpointtech.com/csharp-string-remove)|It is used to return a new string in which all the characters in the current instance, beginning at a specified position and continuing through the last position, have been deleted.|
|[Replace(String, String)](https://www.tpointtech.com/csharp-string-replace)|It is used to return a new string in which all occurrences of a specified string in the current instance are replaced with another specified string.|
|[Split(Char[])](https://www.tpointtech.com/csharp-string-split)|It is used to split a string into substrings based on the characters in an array.|
|[StartsWith(String)](https://www.tpointtech.com/csharp-string-startswith)|It is used to check whether the beginning of the current string matches the specified string.|
|[Substring(Int32)](https://www.tpointtech.com/csharp-string-substring)|It is used to retrieve a substring from the current string instance. The substring starts at a specified character position and continues to the end of the string.|
|[ToCharArray()](https://www.tpointtech.com/csharp-string-tochararray)|It is used to copy the characters of the current string to a Unicode character array.|
|[ToLower()](https://www.tpointtech.com/csharp-string-tolower)|It is used to convert a String into lowercase.|
|[ToLowerInvariant()](https://www.tpointtech.com/csharp-string-tolowerinvariant)|It is used to convert a String into lowercase using the casing rules of the invariant culture.|
|[ToString()](https://www.tpointtech.com/csharp-string-tostring)|It is used to return an instance of String.|
|[ToUpper()](https://www.tpointtech.com/csharp-string-toupper)|It is used to convert a String into uppercase.|
|[Trim()](https://www.tpointtech.com/csharp-string-trim)|It is used to remove all leading and trailing white-space characters from the current String object.|
|[TrimEnd(Char[])](https://www.tpointtech.com/csharp-string-trimend)|It is used to remove all trailing occurrences of a set of characters specified in an array from the current String object.|
|[TrimStart(Char[])](https://www.tpointtech.com/csharp-string-trimstart)|It is used to remove all leading occurrences of a set of characters, which is specified in an array, from the current String object.|

### C# String Method Example

Let us take an example to illustrate the string method in the C# programming language.

### Example

[](https://www.tpointtech.com/c-sharp-strings#)[](https://www.tpointtech.com/c-sharp-strings#)[](https://www.tpointtech.com/c-sharp-strings#)

1. using System;  
2. class Tpoint {  
3.     public static void Main() {  
4.         // Creating strings  
5.         string city = "Delhi";  
6.         string country = "India";  
7.         // Using ToUpper and ToLower methods  
8.         Console.WriteLine("Uppercase: " + city.ToUpper());  
9.         Console.WriteLine("Lowercase: " + city.ToLower());  
10.         // Using the Trim method  
11.         string sp = "Welcome to Tpoint tech";  
12.         Console.WriteLine("Trimmed: " + sp.Trim() );  
13.         // Using the Replace method  
14.         string rep = country.Replace("India", "Bharat");  
15.         Console.WriteLine("Replaced String: " + rep);   
16.         // Using the Split method  
17.         string fruits ="Apple,Banana,Cherry";  
18.         string [] fruitArray = fruits.Split(',');  
19.         Console.WriteLine("Fruits after split: ");  
20.         foreach (string f in fruitArray) {  
21.             Console.WriteLine(f);  
22.         }  
23.         // Using StartsWith and EndsWith methods  
24.        Console.WriteLine("Does the city start with 'Del'?" + city.StartsWith("Del"));  
25.    Console.WriteLine("Does the country end with 'dia'?" + country.EndsWith("dia"));  
26.         // Using the IndexOf method  
27.         int index = fruits.IndexOf("Banana");  
28.         Console.WriteLine("Index of Banana: " + index);  
29.         // Using String Copy method  
30.         string copyCity = String.Copy(city);  
31.         Console.WriteLine("Copied String: " + copyCity);  
32.         // Using Null or Empty Check method  
33.         string emptyStr = "";  
34.         Console.WriteLine("Is emptyStr null or empty?" + String.IsNullOrEmpty(emptyStr));  
35.     }  
36. }  

**Output:**

Uppercase: DELHI
Lowercase: delhi
Trimmed: Welcome to Tpoint tech
Replaced String: Bharat
Fruits after split:
Apple
Banana
Cherry
Does the city start with 'Del'?True
Does the country end with 'dia'?True
Index of Banana: 6
Copied String: Delhi
Is emptyStr null or empty?True

**Explanation:**

In this example, we demonstrate the use of various string methods in C#. First, we use the conversion case using the ToUpper() and ToLower() methods. The trim() method is used to remove extra spaces, while the Replace() method is used to replace a part of a string. The split() method is used to break the string into an array.

After that, the StartsWith() and EndWith() check prefixes and suffixes. The IndexOf() method finds the position of a substring. The String.Copy() method is used to create a copy of an existing string, and String.IsNullorEmpty() method is used to check whether a string is either null or empty.

## String Literals

C# has three different types of string literals. These are as follows:

- Quoted String Literals
- Verbatim Literals
- Raw String Literals

Now, we will discuss these string literals one by one in C#.

### 1) Quoted String Literals

In the C# programming language, a quoted string literals are enclosed in a double quote character (") on a single line. It supports escape sequences for special characters like newline (\n), tab (\t), double quote (\"), and backslash (\\).

[](https://www.tpointtech.com/c-sharp-strings#)[](https://www.tpointtech.com/c-sharp-strings#)[](https://www.tpointtech.com/c-sharp-strings#)

1. string text1 = " Learning C# is fun and interesting. ";  
2. string text2 = " This sentence\r\n has a line break. ";  
3. /* The resulting string: 
4. This sentence 
5. has a line break. 
6. */  

Several escape sequences are used in string literals.

|Escape sequence|Character Name|
|---|---|
|\'|It represents a single quote|
|\"|It indicates a double Quote|
|\\|It represents a backslash|
|\0|It shows the null|
|\n|It defines the new line|
|\t|It is a Horizontal tab|
|\uNNNN|It is a UTF -16 Unicode Character|
|\U00NNNNNN|It is a UTF -32 Unicode Character|

### 2) Verbatim String Literals

In C#, a verbatim string literal is used to create multi-line strings. Verbatim string allows special characters and breaks the line. A verbatim string can be created by prefixing the string with @symbol before double quotes.

**For Example:**

[](https://www.tpointtech.com/c-sharp-strings#)[](https://www.tpointtech.com/c-sharp-strings#)[](https://www.tpointtech.com/c-sharp-strings#)

1. string str1 = @" spdf  
2. abc ";  
3. string str2 = @" \mypcsharedproject ";  
4. string str3 = @" xyz@gmail.com ";  

**3) Raw String Literals**

In C#, a raw string literal keeps whitespaces, line breaks, and special characters, which allows us to break the embedded line. It used three quotes (""") to represent the string literals. They can include any characters without requiring escape sequences. It allows the string to appear in code exactly as it will be stored or displayed.

## String Concatenation

In the C# programming language, a String is concatenated using the (+) operator. It allows us to join the two string values in a single format. We can also use methods like String.Concat() or String.Join() for concatenation.

### C# String Concatenation Example

Let us take an example to illustrate the concatenation of strings in C#.

### Example

[](https://www.tpointtech.com/c-sharp-strings#)[](https://www.tpointtech.com/c-sharp-strings#)[](https://www.tpointtech.com/c-sharp-strings#)

1. using System;  
2. class TPT {  
3.     public static void Main() {  
4.         // Declaration of string variables  
5.         string fname = "Tpoint";  
6.         string lname = " Tech";  
7.         // using + operator  
8.         string fullName = fname + " " + lname;  
9.         // Displaying the result  
10.         Console.WriteLine("Full Name: " + fullName);  
11.     }  
12. }  

**Output:**

Full Name: Tpoint Tech

**Explanation:**

In this example, we create a class TPT and declare the string variables. After initializing the value, we use the (+) operator to concatenate the string values. In the end, we use the Console.WriteLine() function to print the output.

## String Interpolation

In C#, string interpolation is an effective way to concatenate strings. It allows us to embed variables directly inside a string, which helps to make the code more readable.

### C# String Interpolation Example

Let us take an example to illustrate the string interpolation in C#.

### Example

[](https://www.tpointtech.com/c-sharp-strings#)[](https://www.tpointtech.com/c-sharp-strings#)[](https://www.tpointtech.com/c-sharp-strings#)

1. using System;  
2. class TPT  
3. {  
4.     public static void Main()  
5.     {  
6.         string fName = "Welcome to";  
7.         string lName = "Tpoint tech";  
8.         int age = 24;  
9.         // Using string interpolation  
10.         string msg = $"Hello, {fName}{lName} and I am {age} years old.";  
11.         Console.WriteLine(msg);  
12.     }  
13. }  

**Output:**

Hello, Welcome to Tpoint tech and I am 24 years old.

**Explanation:**

In this example, we demonstrate the use of string interpolation in C#. First, we define three variables: fName, lName, and age, which store parts of a message and a number. After that, we use the interpolation by prefixing the string with a $ symbol. It allows us to create a readable and concise message in the msg variable.

## Finding the length of a string in C#

Let us take an example to find the length of a string using the length property in C#.

### Example

[](https://www.tpointtech.com/c-sharp-strings#)[](https://www.tpointtech.com/c-sharp-strings#)[](https://www.tpointtech.com/c-sharp-strings#)

1. using System;  
2. class TPT  
3. {  
4.     public static void Main()  
5.     {  
6.         // Declaration of a string  
7.         string msg = "Welcome to Tpoint tech";  
8.         // using the length property  
9.         int l = msg.Length;  
10.         Console.WriteLine($"The string is: {msg}");  
11.         Console.WriteLine($"The length of the string: {l}");  
12.     }  
13. }  

**Output:**

The string is: Welcome to Tpoint tech
The length of the string: 22

**Explanation:**

In this example, we create a class named TPT and declare the string variable msg. After initializing the value, we use the Length property to find the length of the string..

## Comparing String

In the C# programming language, the string can be compared using the String.Compare(), Equals(), and == method. This method returns an integer value that represents whether one string is less than, equal to, or greater than another string.

### C# String Example to Compare Two Strings

Let us take an example to illustrate how to compare two strings using the different methods in C#.

### Example

[](https://www.tpointtech.com/c-sharp-strings#)[](https://www.tpointtech.com/c-sharp-strings#)[](https://www.tpointtech.com/c-sharp-strings#)

1. using System;  

2. public class StringCompareExample  
3. {  
4.     public static void Main()  
5.     {  
6.         string str1 = "Csharp";  
7.         string str2 = "Java";  

8.         // Using String.Compare()  
9.         int result = String.Compare(str1, str2);  

10.         // Using Equals()  
11.         bool isEqual = str1.Equals(str2);  

12.         // Using ==  
13.         bool equalOperator = (str1 == str2);  

14.         Console.WriteLine("String.Compare() Result: " + result);  
15.         Console.WriteLine("Equals() Result: " + isEqual);  
16.         Console.WriteLine("== Operator Result: " + equalOperator);  
17.     }  
18. }  

**Output:**

String.Compare() Result: -1
Equals() Result: False
== Operator Result: False

**Explanation:**

In this example, we demonstrate how to compare strings using different methods in C#. Here, the string.Compare() function returns -1 because "Csharp" comes before "Java" alphabetically. Both Equals() and == return False because the two strings are not the same.

## Conclusion

In conclusion, a C# string is a sequence of characters that is used to represent text. Strings are widely used in programming to store and manipulate words, sentences, and other text-based data. They have many built-in methods that make coding easier, such as concatenating, manipulating, comparing, trimming, and searching. Strings are very important for writing clear, efficient, and easy-to-understand programs.