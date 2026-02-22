Java StringBuffer class is thread-safe, i.e., multiple threads cannot access it simultaneously. So, it is safe and will result in an order.

## Constructors of the StringBuffer Class

The StringBuffer class provides multiple constructors to create mutable string objects with different initial states and capacities.

### 1. StringBuffer()

This constructor creates an empty StringBuffer object with a default initial capacity of 16 characters.

**Syntax:**

It has the following syntax:

[](https://www.tpointtech.com/stringbuffer-in-java#)[](https://www.tpointtech.com/stringbuffer-in-java#)[](https://www.tpointtech.com/stringbuffer-in-java#)

1. StringBuffer sb = new StringBuffer();  

### 2. StringBuffer(String str)

This constructor creates a StringBuffer object initialized with the specified string.

**Syntax:**

It has the following syntax:

[](https://www.tpointtech.com/stringbuffer-in-java#)[](https://www.tpointtech.com/stringbuffer-in-java#)[](https://www.tpointtech.com/stringbuffer-in-java#)

1. StringBuffer sb = new StringBuffer("Hello");  

### 3. StringBuffer(int capacity)

This constructor creates an empty StringBuffer object with the specified initial capacity.

**Syntax:**

It has the following syntax:

[](https://www.tpointtech.com/stringbuffer-in-java#)[](https://www.tpointtech.com/stringbuffer-in-java#)[](https://www.tpointtech.com/stringbuffer-in-java#)

1. StringBuffer sb = new StringBuffer(50);  

### Example

The following example demonstrates how to create StringBuffer objects using different constructors:

[](https://www.tpointtech.com/stringbuffer-in-java#)[](https://www.tpointtech.com/stringbuffer-in-java#)[](https://www.tpointtech.com/stringbuffer-in-java#)

1. public class StringBufferConstructorsExample {  
2.     public static void main(String[] args) {  
3.         // Using default constructor  
4.         StringBuffer sb1 = new StringBuffer();  
5.         System.out.println("sb1 (default): \"" + sb1 + "\", Capacity: " + sb1.capacity());  

6.         // Using constructor with initial string  
7.         StringBuffer sb2 = new StringBuffer("Hello");  
8.         System.out.println("sb2 (with string): \"" + sb2 + "\", Capacity: " + sb2.capacity());  

9.         // Using constructor with specified capacity  
10.         StringBuffer sb3 = new StringBuffer(50);  
11.         System.out.println("sb3 (with capacity 50): \"" + sb3 + "\", Capacity: " + sb3.capacity());  
12.     }  
13. }  

**Output:**

sb1 (default): "", Capacity: 16
sb2 (with string): "Hello", Capacity: 21
sb3 (with capacity 50): "", Capacity: 50

**Explanation:**

- **sb1** is created using the default constructor with an initial capacity of 16.
- **sb2** is created with the string "Hello", which adds 5 characters plus the default extra capacity, making a total of 21.
- **sb3** is created with a specified capacity of 50, ready to hold up to 50 characters without resizing.

## Methods of the StringBuffer class

The following tables shows the commonly used methods with their descriptions of the StringBuffer class:

|Modifier and Type|Method|Description|
|---|---|---|
|public synchronized StringBuffer|append(String s)|It is used to append the specified string to this string. The append() method is overloaded like append(char), append(boolean), append(int), append(float), append(double), etc.|
|public synchronized StringBuffer|insert(int offset, String s)|It is used to insert the specified string into this string at the specified position. The insert() method is overloaded like insert(int, char), insert(int, boolean), insert(int, int), insert(int, float), insert(int, double), etc.|
|public synchronized StringBuffer|replace(int startIndex, int endIndex, String str)|It is used to replace the string from the specified startIndex and endIndex.|
|public synchronized StringBuffer|delete(int startIndex, int endIndex)|It is used to delete the string from the specified startIndex and endIndex.|
|public synchronized StringBuffer|reverse()|is used to reverse the string.|
|public int|capacity()|It is used to return the current capacity.|
|public void|ensureCapacity(int minimumCapacity)|It is used to ensure the capacity is at least equal to the given minimum.|
|public char|charAt(int index)|It is used to return the character at the specified position.|
|public int|length()|It is used to return the length of the string, i.e. total number of characters.|
|public String|substring(int beginIndex)|It is used to return the substring from the specified beginIndex.|
|public String|substring(int beginIndex, int endIndex)|It is used to return the substring from the specified beginIndex and endIndex.|

## StringBuffer Class Methods Examples

Here are the StringBuffer class's methods along with appropriate examples.

### 1. StringBuffer Class append() Method

The append() method concatenates the given argument with this String. The following example demonstrates the use of append() method.

[](https://www.tpointtech.com/stringbuffer-in-java#)[](https://www.tpointtech.com/stringbuffer-in-java#)[](https://www.tpointtech.com/stringbuffer-in-java#)

1. class Main {    
2. public static void main(String args[]){    
3. StringBuffer sb=new StringBuffer("Hello ");    
4. sb.append("Java");//now original string is changed    
5. System.out.println(sb);//prints Hello Java    
6. }    
7. }    

**Output:**

Hello Java

### 2. StringBuffer insert() Method

The insert() method inserts the given String into this string at the given position. The following example demonstrates the use of insert() method.

[](https://www.tpointtech.com/stringbuffer-in-java#)[](https://www.tpointtech.com/stringbuffer-in-java#)[](https://www.tpointtech.com/stringbuffer-in-java#)

1. class Main {    
2. public static void main(String args[]){    
3. StringBuffer sb=new StringBuffer("Hello ");    
4. sb.insert(1,"Java");//now original string is changed    
5. System.out.println(sb);//prints HJavaello    
6. }    
7. }    

**Output:**

HJavaello

### 3. StringBuffer replace() Method

The replace() method replaces the given String from the specified beginIndex and endIndex. The following example demonstrates the use of replace() method.

[](https://www.tpointtech.com/stringbuffer-in-java#)[](https://www.tpointtech.com/stringbuffer-in-java#)[](https://www.tpointtech.com/stringbuffer-in-java#)

1. class Main {    
2. public static void main(String args[]){    
3. StringBuffer sb=new StringBuffer("Hello");    
4. sb.replace(1,3,"Java");    
5. System.out.println(sb);//prints HJavalo    
6. }    
7. }    

**Output:**

HJavalo

### 4. StringBuffer delete() Method

The delete() method of the StringBuffer class deletes the String from the specified beginIndex to endIndex. The following example demonstrates the use of delete() method.

[](https://www.tpointtech.com/stringbuffer-in-java#)[](https://www.tpointtech.com/stringbuffer-in-java#)[](https://www.tpointtech.com/stringbuffer-in-java#)

1. class Main {    
2. public static void main(String args[]){    
3. StringBuffer sb=new StringBuffer("Hello");    
4. sb.delete(1,3);    
5. System.out.println(sb);//prints Hlo    
6. }    
7. }    

**Output:**

Hlo

### 5. StringBuffer reverse() Method

The reverse() method of the StringBuffer class reverses the current String. The following example demonstrates the use of reverse() method.

[](https://www.tpointtech.com/stringbuffer-in-java#)[](https://www.tpointtech.com/stringbuffer-in-java#)[](https://www.tpointtech.com/stringbuffer-in-java#)

1. class Main {    
2. public static void main(String args[]){    
3. StringBuffer sb=new StringBuffer("Hello");    
4. sb.reverse();    
5. System.out.println(sb);//prints olleH    
6. }    
7. }    

**Output:**

olleH

### 6. StringBuffer capacity() Method

The capacity() method of the StringBuffer class returns the current capacity of the buffer. The default capacity of the buffer is 16. If the number of characters increases from its current capacity, it increases the capacity by (oldcapacity*2)+2. For example, if your current capacity is 16, it will be (16*2)+2=34.

The following example demonstrates the use of capacity() method.

[](https://www.tpointtech.com/stringbuffer-in-java#)[](https://www.tpointtech.com/stringbuffer-in-java#)[](https://www.tpointtech.com/stringbuffer-in-java#)

1. class Main {    
2. public static void main(String args[]){    
3. StringBuffer sb=new StringBuffer();    
4. System.out.println(sb.capacity());//default 16    
5. sb.append("Hello");    
6. System.out.println(sb.capacity());//now 16    
7. sb.append("java is my favourite language");    
8. System.out.println(sb.capacity());//now (16*2)+2=34 i.e (oldcapacity*2)+2    
9. }    
10. }    

**Output:**

16
16
34

### 7. StringBuffer ensureCapacity() Method

The ensureCapacity() method of the StringBuffer class ensures that the given capacity is the minimum of the current capacity. If it is greater than the current capacity, it increases the capacity by (oldcapacity*2)+2. For example, if your current capacity is 16, it will be (16*2)+2=34. The ensureCapacity() method of the StringBuffer class guarantees that the specified capacity is at least the current capacity. If the specified capacity exceeds the current capacity, it increases the capacity to (oldcapacity* 2) + 2. For instance, if the current capacity is 16, it will be calculated as (16* 2) + 2 = 34.

The following example demonstrates the use of ensureCapacity() method.

[](https://www.tpointtech.com/stringbuffer-in-java#)[](https://www.tpointtech.com/stringbuffer-in-java#)[](https://www.tpointtech.com/stringbuffer-in-java#)

1. class Main {    
2. public static void main(String args[]){    
3. StringBuffer sb=new StringBuffer();    
4. System.out.println(sb.capacity());//default 16    
5. sb.append("Hello");    
6. System.out.println(sb.capacity());//now 16    
7. sb.append("java is my favourite language");    
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