String concatenation is a basic and commonly used operation in Java that allows you to combine two or more strings into a single string. String concatenation is widely used for creating messages, formatting output, and working with text data.

The following are the different ways to concatenate strings in Java:

1. Using String Concatenation (+=) Operator
2. Using String.concat() Method
3. Using StringBuilder or StringBuffer Class
4. Using String.join() Method
5. Using String.format() Method
6. Using Collector.joining() Method

## String Concatenation Using += Operator

The simplest and most commonly used method for concatenating strings in Java is using the + operator. We can concatenate two or more strings by simply using the + operator between them.

### Example 1

Let us take an example to demonstrate the string concatenation using the += operator.

[](https://www.tpointtech.com/string-concatenation-in-java#)[](https://www.tpointtech.com/string-concatenation-in-java#)[](https://www.tpointtech.com/string-concatenation-in-java#)

1. class TestStringConcatenation1{  
2.  public static void main(String args[]){  
3.    String s="Sachin"+" Tendulkar";  
4.    System.out.println(s);//Sachin Tendulkar  
5.  }  
6. }  

**Output:**

Sachin Tendulkar

The [Java compiler](https://www.tpointtech.com/compiler/java) internally manipulate the string by using the following statement.

[](https://www.tpointtech.com/string-concatenation-in-java#)[](https://www.tpointtech.com/string-concatenation-in-java#)[](https://www.tpointtech.com/string-concatenation-in-java#)

1. String s=(new StringBuilder()).append("Sachin").append(" Tendulkar).toString();  

In Java, String concatenation is implemented through the StringBuilder (or StringBuffer) class and it's append method. String concatenation operator produces a new String by appending the second operand onto the end of the first operand. The String concatenation operator can concatenate not only String but primitive values also. Let's understand it through a Java program.

### Example 2

Let us take another example to demonstrate the string concatenation using the StringBuilder.

[](https://www.tpointtech.com/string-concatenation-in-java#)[](https://www.tpointtech.com/string-concatenation-in-java#)[](https://www.tpointtech.com/string-concatenation-in-java#)

1. class TestStringConcatenation2{  
2.  public static void main(String args[]){  
3.    String s=50+30+"Sachin"+40+40;  
4.    System.out.println(s);//80Sachin4040  
5.  }  
6. }  

**Output:**

80Sachin4040

#### Note: After a string literal, all the + will be treated as string concatenation operator.

## String Concatenation Using String.concat() Method

The concat() method belongs to the Java String class. It is an alternative to the + operator for string concatenation. It appends one string to the end of another.

### Synatx:

It has the following syntax:

[](https://www.tpointtech.com/string-concatenation-in-java#)[](https://www.tpointtech.com/string-concatenation-in-java#)[](https://www.tpointtech.com/string-concatenation-in-java#)

1. public String concat(String another)  

### Example

The following example demonstrates how to concatenate strings using the concat() method.

[](https://www.tpointtech.com/string-concatenation-in-java#)[](https://www.tpointtech.com/string-concatenation-in-java#)[](https://www.tpointtech.com/string-concatenation-in-java#)

1. class TestStringConcatenation3{  
2.  public static void main(String args[]){  
3.    String s1="Sachin ";  
4.    String s2="Tendulkar";  
5.    String s3=s1.concat(s2);  
6.    System.out.println(s3);//Sachin Tendulkar  
7.   }  
8. }  

**Output:**

Sachin Tendulkar

The above Java program, concatenates two String objects **s1** and **s2** using **concat()** method and stores the result into **s3** object.

## String Concatenation Using StringBuilder or StringBuffer Class

In order to address the performance concerns associated with the + operator and concat() method, Java provides two classes, StringBuilder and StringBuffer, that are specifically designed for efficient string manipulation.

StringBuilder is class provides append() method to perform concatenation operation. The append() method accepts arguments of different types like Objects, StringBuilder, int, char, CharSequence, boolean, float, double. StringBuilder is the most popular and fastet way to concatenate strings in Java. It is mutable class which means values stored in StringBuilder objects can be updated or changed.

### Example

The following example demonstrates how to concatenate strings efficiently using the StringBuilder or StringBuffer class.

[](https://www.tpointtech.com/string-concatenation-in-java#)[](https://www.tpointtech.com/string-concatenation-in-java#)[](https://www.tpointtech.com/string-concatenation-in-java#)

1. public class StringBuilderExample {  
2.     public static void main(String[] args) {  
3.         String firstName = "Manoj";  
4.         String lastName = "Mamilla";  
5.         // Using StringBuilder for efficient string concatenation  
6.         StringBuilder stringBuilder = new StringBuilder();  
7.         stringBuilder.append("Hello, ");  
8.         stringBuilder.append(firstName);  
9.         stringBuilder.append(" ");  
10.         stringBuilder.append(lastName);  
11.         String result = stringBuilder.toString();  
12.         System.out.println(result);    
13.     }  
14. }  

**Output:**

Hello, Manoj Mamilla

Both the classes StringBuilder and StringBuffer are mutable. It means that they can be modified without creating new instances for each operation. It makes them more efficient than the + operator or concat() method, especially in scenarios involving repeated concatenation in loops.

## String Concatenation Using String.join() Method

Java 8 introduced the String.join() method, which is a concise and expressive way to concatenate multiple strings with a delimiter:

### Example

The following example demonstrates how to concatenate multiple strings using the String.join() method.

[](https://www.tpointtech.com/string-concatenation-in-java#)[](https://www.tpointtech.com/string-concatenation-in-java#)[](https://www.tpointtech.com/string-concatenation-in-java#)

1. public class StringJoinExample {  
2.     public static void main(String[] args) {  
3.         String firstName = "Manoj";  
4.         String lastName = "Mamilla";  
5.         // Using String.join for concatenation with a delimiter  
6.         String result = String.join(" ", "Hello,", firstName, lastName);  
7.         System.out.println(result);    
8.     }  
9. }  

**Output:**

Hello, Manoj Mamilla

There are some other possible ways to concatenate Strings in Java,

## String Concatenation Using String.format() Method

The String.format() method provides another way to concatenate strings in Java while allowing for more control over the formatting. Here is an example using the format() method.

### Example

The following example demonstrates how to concatenate strings using formatted text with the String.format() method.

[](https://www.tpointtech.com/string-concatenation-in-java#)[](https://www.tpointtech.com/string-concatenation-in-java#)[](https://www.tpointtech.com/string-concatenation-in-java#)

1. public class StringFormatExample {  
2.     public static void main(String[] args) {  
3.         String firstName = "Manoj";  
4.         String lastName = "Mamilla";  
5.         // Using String.format for string concatenation with formatting  
6.         String result = String.format("Hello, %s %s", firstName, lastName);  
7.         System.out.println(result);    
8.     }  
9. }   

**Output:**

Hello, Manoj Mamilla

Here, the String objects result is assigned the concatenated result of Strings firstName and lastName using the String.format() method. The format() accepts parameters as format specifier followed by String objects or values.

## String Concatenation Using Collector.joining() Method

The Collectors class in Java 8 offers joining() method that concatenates the input elements in a similar order as they occur.

### Example

The following example demonstrates how to concatenate strings using the joining() collector from the Stream API.

[](https://www.tpointtech.com/string-concatenation-in-java#)[](https://www.tpointtech.com/string-concatenation-in-java#)[](https://www.tpointtech.com/string-concatenation-in-java#)

1. import java.util.*;  
2. import java.util.stream.Collectors;  
3. public class ColJoining  
4. {  
5.     /* Driver Code */  
6.     public static void main(String args[])  
7.     {  
8.         List<String> liststr = Arrays.asList("abc", "pqr", "xyz"); //List of String array  
9.     String str = liststr.stream().collect(Collectors.joining(", ")); //performs joining operation  
10.         System.out.println(str.toString());  //Displays result  
11.     }  
12. }  

**Output:**

abc, pqr, xyz