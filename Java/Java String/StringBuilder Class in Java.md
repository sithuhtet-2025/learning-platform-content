Java StringBuilder class is used to create mutable (modifiable) String. The Java StringBuilder class is same as [StringBuffer class](https://www.tpointtech.com/stringbuffer-in-java) except that it is non-synchronized. It is available since JDK 1.5.

## Import Statement for StringBuilder Class

The StringBuilder class belongs to the **java.lang** package that is automatically imported in every Java program. Therefore, no explicit import statement is required to use StringBuilder.

### Syntax

The below syntax demonstrating directly use of StringBuilder in your program without adding any import statement:

[](https://www.tpointtech.com/stringbuilder-in-java#)[](https://www.tpointtech.com/stringbuilder-in-java#)[](https://www.tpointtech.com/stringbuilder-in-java#)

1. StringBuilder sb = new StringBuilder();  

## Constructors of StringBuilder Class

The StringBuilder class provides multiple constructors to create mutable string objects with different initial capacities or values.

### 1. StringBuilder() Constructor

This constructor creates an empty StringBuilder object with a default initial capacity of 16 characters.

**Syntax:**

It has the following syntax:

[](https://www.tpointtech.com/stringbuilder-in-java#)[](https://www.tpointtech.com/stringbuilder-in-java#)[](https://www.tpointtech.com/stringbuilder-in-java#)

1. StringBuilder sb = new StringBuilder();  

It is useful when you do not know the initial content size and want a flexible buffer.

### 2. StringBuilder(String str) Constructor

This constructor creates a StringBuilder object initialized with the specified string.

**Syntax:**

It has the following syntax:

[](https://www.tpointtech.com/stringbuilder-in-java#)[](https://www.tpointtech.com/stringbuilder-in-java#)[](https://www.tpointtech.com/stringbuilder-in-java#)

1. StringBuilder sb = new StringBuilder(String str);  

### 3. StringBuilder(int length) Constructor

This constructor creates an empty StringBuilder object with the specified initial capacity.

**Syntax:**

It has the following syntax:

[](https://www.tpointtech.com/stringbuilder-in-java#)[](https://www.tpointtech.com/stringbuilder-in-java#)[](https://www.tpointtech.com/stringbuilder-in-java#)

1. StringBuilder sb = new StringBuilder(int length);  

It is helpful when the required capacity is known in advance to improve performance.

## Methods of StringBuilder Class

The following table shows the commonly used method of StringBuilder class:

|Method|Description|
|---|---|
|public StringBuilder append(String s)|It is used to append the specified string with this string. The append() method is overloaded like append(char), append(boolean), append(int), append(float), append(double) etc.|
|public StringBuilder insert(int offset, String s)|It is used to insert the specified string with this string at the specified position. The insert() method is overloaded like insert(int, char), insert(int, boolean), insert(int, int), insert(int, float), insert(int, double) etc.|
|public StringBuilder replace(int startIndex, int endIndex, String str)|It is used to replace the string from specified startIndex and endIndex.|
|public StringBuilder delete(int startIndex, int endIndex)|It is used to delete the string from specified startIndex and endIndex.|
|public StringBuilder reverse()|It is used to reverse the string.|
|public int capacity()|It is used to return the current capacity.|
|public void ensureCapacity(int minimumCapacity)|It is used to ensure the capacity at least equal to the given minimum.|
|public char charAt(int index)|It is used to return the character at the specified position.|
|public int length()|It is used to return the length of the string i.e. total number of characters.|
|public String substring(int beginIndex)|It is used to return the substring from the specified beginIndex.|
|public String substring(int beginIndex, int endIndex)|It is used to return the substring from the specified beginIndex and endIndex.|

## Java StringBuilder Examples

Let's see the examples of different methods of StringBuilder class.

### 1. StringBuilder append() method

The StringBuilder append() method concatenates the given argument with this String.

The following example demonstrates the use of append() method.

[](https://www.tpointtech.com/stringbuilder-in-java#)[](https://www.tpointtech.com/stringbuilder-in-java#)[](https://www.tpointtech.com/stringbuilder-in-java#)

1. class StringBuilderExample{  
2. public static void main(String args[]){  
3. StringBuilder sb=new StringBuilder("Hello ");  
4. sb.append("Java");//now original string is changed  
5. System.out.println(sb);//prints Hello Java  
6. }  
7. }  

**Output:**

Hello Java

### 2. StringBuilder insert() method

The StringBuilder insert() method inserts the given string with this string at the given position.

The following example demonstrates the use of insert() method.

[](https://www.tpointtech.com/stringbuilder-in-java#)[](https://www.tpointtech.com/stringbuilder-in-java#)[](https://www.tpointtech.com/stringbuilder-in-java#)

1. class StringBuilderExample2{  
2. public static void main(String args[]){  
3. StringBuilder sb=new StringBuilder("Hello ");  
4. sb.insert(1,"Java");//now original string is changed  
5. System.out.println(sb);//prints HJavaello  
6. }  
7. }  

**Output:**

HJavaello

### 3. StringBuilder replace() method

The StringBuilder replace() method replaces the given string from the specified beginIndex and endIndex.

The following example demonstrates the use of replace() method.

[](https://www.tpointtech.com/stringbuilder-in-java#)[](https://www.tpointtech.com/stringbuilder-in-java#)[](https://www.tpointtech.com/stringbuilder-in-java#)

1. class StringBuilderExample3{  
2. public static void main(String args[]){  
3. StringBuilder sb=new StringBuilder("Hello");  
4. sb.replace(1,3,"Java");  
5. System.out.println(sb);//prints HJavalo  
6. }  
7. }  

**Output:**

HJavalo

### 4. StringBuilder delete() method

The delete() method of StringBuilder class deletes the string from the specified beginIndex to endIndex.

The following example demonstrates the use of delete() method.

[](https://www.tpointtech.com/stringbuilder-in-java#)[](https://www.tpointtech.com/stringbuilder-in-java#)[](https://www.tpointtech.com/stringbuilder-in-java#)

1. class StringBuilderExample4{  
2. public static void main(String args[]){  
3. StringBuilder sb=new StringBuilder("Hello");  
4. sb.delete(1,3);  
5. System.out.println(sb);//prints Hlo  
6. }  
7. }  

**Output:**

Hlo

### 5. StringBuilder reverse() method

The reverse() method of StringBuilder class reverses the current string.

The following example demonstrates the use of reverse() method.

[](https://www.tpointtech.com/stringbuilder-in-java#)[](https://www.tpointtech.com/stringbuilder-in-java#)[](https://www.tpointtech.com/stringbuilder-in-java#)

1. class StringBuilderExample5{  
2. public static void main(String args[]){  
3. StringBuilder sb=new StringBuilder("Hello");  
4. sb.reverse();  
5. System.out.println(sb);//prints olleH  
6. }  
7. }  

**Output:**

olleH

### 6. StringBuilder capacity() method

The capacity() method of StringBuilder class returns the current capacity of the Builder. The default capacity of the Builder is 16. If the number of character increases from its current capacity, it increases the capacity by (oldcapacity*2)+2. For example if your current capacity is 16, it will be (16*2)+2=34.

The following example demonstrates the use of capacity() method.

[](https://www.tpointtech.com/stringbuilder-in-java#)[](https://www.tpointtech.com/stringbuilder-in-java#)[](https://www.tpointtech.com/stringbuilder-in-java#)

1. class StringBuilderExample6{    
2. public static void main(String args[]){    
3. StringBuilder sb=new StringBuilder();    
4. System.out.println(sb.capacity());//default 16    
5. sb.append("Hello");    
6. System.out.println(sb.capacity());//now 16    
7. sb.append("Java is my favourite language");    
8. System.out.println(sb.capacity());//now (16*2)+2=34 i.e (oldcapacity*2)+2    
9. }    
10. }    

**Output:**

16
16
34

### 7. StringBuilder ensureCapacity() method

The ensureCapacity() method of StringBuilder class ensures that the given capacity is the minimum to the current capacity. If it is greater than the current capacity, it increases the capacity by (oldcapacity*2)+2. For example if your current capacity is 16, it will be (16*2)+2=34.

The following example demonstrates the use of ensureCapacity() method.

[](https://www.tpointtech.com/stringbuilder-in-java#)[](https://www.tpointtech.com/stringbuilder-in-java#)[](https://www.tpointtech.com/stringbuilder-in-java#)

1. class StringBuilderExample7{    
2. public static void main(String args[]){    
3. StringBuilder sb=new StringBuilder();    
4. System.out.println(sb.capacity());//default 16    
5. sb.append("Hello");    
6. System.out.println(sb.capacity());//now 16    
7. sb.append("Java is my favourite language");    
8. System.out.println(sb.capacity());//now (16*2)+2=34 i.e (oldcapacity*2)+2    
9. sb.ensureCapacity(10);//now no change    
10. System.out.println(sb.capacity());//now 34    
11. sb.ensureCapacity(50);//now (34*2)+2    
12. System.out.println(sb.capacity());//now 70    
13. }    
14. }    

**Output:**

16
16
34
34
70