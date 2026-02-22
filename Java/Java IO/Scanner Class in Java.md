Java provides various ways to read input from the user, and the Scanner class is one of the simplest and most commonly used approaches.

In this chapter, we will learn what the Scanner class is, why it is used, its declaration, constructors, important methods, and examples to understand how it works for reading input and parsing data.

## What is Scanner Class in Java?

The Scanner class is used to read input data from different sources such as keyboard input, files, strings, or streams.

It breaks the input into tokens using a delimiter, which is whitespace by default, and allows us to read data in different primitive types like int, long, double, float, byte, boolean, and String.

The Scanner class belongs to the java.util package. It extends the Object class and implements the Iterator<String> and Closeable interfaces.

Scanner is widely used because it provides easy-to-use methods like nextInt(), nextLine(), nextDouble(), and nextBoolean() to parse input efficiently.

## Scanner Class Declaration

The Scanner class is defined in the java.util package.

[](https://www.tpointtech.com/scanner-class-in-java#)[](https://www.tpointtech.com/scanner-class-in-java#)[](https://www.tpointtech.com/scanner-class-in-java#)

1. public final class Scanner extends Object implements Iterator<String>  

## How to Get a Scanner Object?

### Reading Input from Keyboard

To read input from the user, we pass System.in to the Scanner constructor.

[](https://www.tpointtech.com/scanner-class-in-java#)[](https://www.tpointtech.com/scanner-class-in-java#)[](https://www.tpointtech.com/scanner-class-in-java#)

1. Scanner sc = new Scanner(System.in);  

### Reading Input from a String

To parse data from a string, we pass the string to the Scanner constructor.

[](https://www.tpointtech.com/scanner-class-in-java#)[](https://www.tpointtech.com/scanner-class-in-java#)[](https://www.tpointtech.com/scanner-class-in-java#)

1. Scanner sc = new Scanner("Hello TpointTech");  

## Constructors of Scanner Class

The Scanner class provides multiple constructors to read input from different sources.

### 1. Scanner(InputStream source)

This constructor creates a Scanner that reads input from an input stream such as System.in.

**Syntax:**

Here is the syntax:

[](https://www.tpointtech.com/scanner-class-in-java#)[](https://www.tpointtech.com/scanner-class-in-java#)[](https://www.tpointtech.com/scanner-class-in-java#)

1. Scanner Scanner sc = new Scanner(System.in);  

### 2. Scanner(InputStream source, String charsetName)

This constructor creates a Scanner that reads input from an input stream using the specified character encoding.

**Syntax:**

Here is the syntax:

[](https://www.tpointtech.com/scanner-class-in-java#)[](https://www.tpointtech.com/scanner-class-in-java#)[](https://www.tpointtech.com/scanner-class-in-java#)

1. Scanner sc = new Scanner(System.in, "UTF-8");  

### 3. Scanner(String source)

This constructor creates a Scanner that reads input from the specified string.

**Syntax:**

Here is the syntax:

[](https://www.tpointtech.com/scanner-class-in-java#)[](https://www.tpointtech.com/scanner-class-in-java#)[](https://www.tpointtech.com/scanner-class-in-java#)

1. Scanner sc = new Scanner("Hello TpointTech");  

### 4. Scanner(File source)

This constructor creates a Scanner that reads input from a file.

**Syntax:**

Here is the syntax:

[](https://www.tpointtech.com/scanner-class-in-java#)[](https://www.tpointtech.com/scanner-class-in-java#)[](https://www.tpointtech.com/scanner-class-in-java#)

1. Scanner sc = new Scanner(new File("data.txt"));  

### 5. Scanner(File source, String charsetName)

This constructor creates a Scanner that reads input from a file using the specified character encoding.

**Syntax:**

Here is the syntax:

[](https://www.tpointtech.com/scanner-class-in-java#)[](https://www.tpointtech.com/scanner-class-in-java#)[](https://www.tpointtech.com/scanner-class-in-java#)

1. Scanner sc = new Scanner(new File("data.txt"), "UTF-8");  

### 6. Scanner(Readable source)

This constructor creates a Scanner that reads input from any object implementing the Readable interface.

**Syntax:**

Here is the syntax:

[](https://www.tpointtech.com/scanner-class-in-java#)[](https://www.tpointtech.com/scanner-class-in-java#)[](https://www.tpointtech.com/scanner-class-in-java#)

1. Readable readable = new StringReader("Java Scanner");  
2. Scanner sc = new Scanner(readable);  

### 7. Scanner(ReadableByteChannel source)

This constructor creates a Scanner that reads input from a readable byte channel.

**Syntax:**

Here is the syntax:

[](https://www.tpointtech.com/scanner-class-in-java#)[](https://www.tpointtech.com/scanner-class-in-java#)[](https://www.tpointtech.com/scanner-class-in-java#)

1. ReadableByteChannel channel = Files.newByteChannel(Paths.get("data.txt"));  
2. Scanner sc = new Scanner(channel);  

### 8. Scanner(ReadableByteChannel source, String charsetName)

This constructor creates a Scanner that reads input from a readable byte channel using the specified character encoding.

**Syntax:**

Here is the syntax:

[](https://www.tpointtech.com/scanner-class-in-java#)[](https://www.tpointtech.com/scanner-class-in-java#)[](https://www.tpointtech.com/scanner-class-in-java#)

1. ReadableByteChannel channel = Files.newByteChannel(Paths.get("data.txt"));  
2. Scanner sc = new Scanner(channel, "UTF-8");  

### 9. Scanner(Path source)

This constructor creates a Scanner that reads input from a file path.

**Syntax:**

Here is the syntax:

[](https://www.tpointtech.com/scanner-class-in-java#)[](https://www.tpointtech.com/scanner-class-in-java#)[](https://www.tpointtech.com/scanner-class-in-java#)

1. Scanner sc = new Scanner(Paths.get("data.txt"));  

### 10. Scanner(Path source, String charsetName)

This constructor creates a Scanner that reads input from a file path using the specified character encoding.

**Syntax:**

Here is the syntax:

[](https://www.tpointtech.com/scanner-class-in-java#)[](https://www.tpointtech.com/scanner-class-in-java#)[](https://www.tpointtech.com/scanner-class-in-java#)

1. Scanner sc = new Scanner(Paths.get("data.txt"), "UTF-8");  

## Methods of Scanner Class

The Scanner class provides many useful methods to read and parse input.

|Modifier & Type|Method|Description|
|---|---|---|
|void|[close()](https://www.tpointtech.com/java-scanner-close-method)|It is used to close this scanner.|
|pattern|[delimiter()](https://www.tpointtech.com/java-scanner-delimiter-method)|It is used to get the Pattern which the Scanner class is currently using to match delimiters.|
|Stream<MatchResult>|findAll()|It is used to find a stream of match results that match the provided pattern string.|
|String|[findInLine()](https://www.tpointtech.com/java-scanner-findinline-method)|It is used to find the next occurrence of a pattern constructed from the specified string, ignoring delimiters.|
|string|[findWithinHorizon()](https://www.tpointtech.com/java-scanner-findwithinhorizon-method)|It is used to find the next occurrence of a pattern constructed from the specified string, ignoring delimiters.|
|boolean|[hasNext()](https://www.tpointtech.com/java-scanner-hasnext-method)|It returns true if this scanner has another token in its input.|
|boolean|[hasNextBigDecimal()](https://www.tpointtech.com/java-scanner-hasnextbigdecimal-method)|It is used to check if the next token in this scanner's input can be interpreted as a BigDecimal using the nextBigDecimal() method or not.|
|boolean|[hasNextBigInteger()](https://www.tpointtech.com/java-scanner-hasnextbiginteger-method)|It is used to check if the next token in this scanner's input can be interpreted as a BigDecimal using the nextBigDecimal() method or not.|
|boolean|[hasNextBoolean()](https://www.tpointtech.com/java-scanner-hasnextboolean-method)|It is used to check if the next token in this scanner's input can be interpreted as a Boolean using the nextBoolean() method or not.|
|boolean|[hasNextByte()](https://www.tpointtech.com/java-scanner-hasnextbyte-method)|It is used to check if the next token in this scanner's input can be interpreted as a Byte using the nextBigDecimal() method or not.|
|boolean|[hasNextDouble()](https://www.tpointtech.com/java-scanner-hasnextdouble-method)|It is used to check if the next token in this scanner's input can be interpreted as a BigDecimal using the nextByte() method or not.|
|boolean|[hasNextFloat()](https://www.tpointtech.com/java-scanner-hasnextfloat-method)|It is used to check if the next token in this scanner's input can be interpreted as a Float using the nextFloat() method or not.|
|boolean|[hasNextInt()](https://www.tpointtech.com/java-scanner-hasnextint-method)|It is used to check if the next token in this scanner's input can be interpreted as an int using the nextInt() method or not.|
|boolean|[hasNextLine()](https://www.tpointtech.com/java-scanner-hasnextline-method)|It is used to check if there is another line in the input of this scanner or not.|
|boolean|[hasNextLong()](https://www.tpointtech.com/java-scanner-hasnextlong-method)|It is used to check if the next token in this scanner's input can be interpreted as a Long using the nextLong() method or not.|
|boolean|[hasNextShort()](https://www.tpointtech.com/java-scanner-hasnextshort-method)|It is used to check if the next token in this scanner's input can be interpreted as a Short using the nextShort() method or not.|
|IOException|[ioException()](https://www.tpointtech.com/java-scanner-ioexception-method)|It is used to get the IOException last thrown by this Scanner's readable.|
|Locale|[locale()](https://www.tpointtech.com/java-scanner-locale-method)|It is used to get a Locale of the Scanner class.|
|MatchResult|[match()](https://www.tpointtech.com/java-scanner-match-method)|It is used to get the match result of the last scanning operation performed by this scanner.|
|String|[next()](https://www.tpointtech.com/java-scanner-next-method)|It is used to get the next complete token from the scanner which is in use.|
|BigDecimal|[nextBigDecimal()](https://www.tpointtech.com/java-scanner-nextbigdecimal-method)|It scans the next token of the input as a BigDecimal.|
|BigInteger|[nextBigInteger()](https://www.tpointtech.com/java-scanner-nextbiginteger-method)|It scans the next token of the input as a BigInteger.|
|boolean|[nextBoolean()](https://www.tpointtech.com/java-scanner-nextboolean-method)|It scans the next token of the input into a boolean value and returns that value.|
|byte|[nextByte()](https://www.tpointtech.com/java-scanner-nextbyte-method)|It scans the next token of the input as a byte.|
|double|[nextDouble()](https://www.tpointtech.com/java-scanner-nextdouble-method)|It scans the next token of the input as a double.|
|float|[nextFloat()](https://www.tpointtech.com/java-scanner-nextfloat-method)|It scans the next token of the input as a float.|
|int|[nextInt()](https://www.tpointtech.com/java-scanner-nextint-method)|It scans the next token of the input as an Int.|
|String|[nextLine()](https://www.tpointtech.com/java-scanner-nextline-method)|It is used to get the input string that was skipped by the Scanner object.|
|long|[nextLong()](https://www.tpointtech.com/java-scanner-nextlong-method)|It scans the next token of the input as a long.|
|short|[nextShort()](https://www.tpointtech.com/java-scanner-nextshort-method)|It scans the next token of the input as a short.|
|int|[radix()](https://www.tpointtech.com/java-scanner-radix-method)|It is used to get the default radix of the Scanner use.|
|void|[remove()](https://www.tpointtech.com/java-scanner-remove-method)|It is used when this implementation of the Iterator does not support the remove operation.|
|Scanner|[reset()](https://www.tpointtech.com/java-scanner-reset-method)|It is used to reset the Scanner which is in use.|
|Scanner|[skip()](https://www.tpointtech.com/java-scanner-skip-method)|It skips input that matches the specified pattern, ignoring delimiters|
|Stream<String>|[tokens()](https://www.tpointtech.com/java-scanner-tokens-method)|It is used to get a stream of delimiter-separated tokens from the Scanner object which is in use.|
|String|[toString()](https://www.tpointtech.com/java-scanner-tostring-method)|It is used to get the string representation of a Scanner.|
|Scanner|[useDelimiter()](https://www.tpointtech.com/java-scanner-usedelimiter-method)|It is used to set the delimiting pattern of the Scanner which is in use to the specified pattern.|
|Scanner|[useLocale()](https://www.tpointtech.com/java-scanner-uselocale-method)|It is used to sets this scanner's locale object to the specified locale.|
|Scanner|[useRadix()](https://www.tpointtech.com/java-scanner-useradix-method)|It is used to set the default radix of the Scanner which is in use to the specified radix.|

## Examples of Java Scanner Class

Practice the following examples to understand different uses of the Scanner class.

### Example 1: Reading a String from User

The following example demonstrates how to read a string input from the user using the nextLine() method.

[](https://www.tpointtech.com/scanner-class-in-java#)[](https://www.tpointtech.com/scanner-class-in-java#)[](https://www.tpointtech.com/scanner-class-in-java#)

1. import java.util.Scanner;  

2. public class ScannerExample1 {  
3.     public static void main(String args[]) {  
4.         Scanner sc = new Scanner(System.in);  

5.         System.out.print("Enter your name: ");  
6.         String name = sc.nextLine();  

7.         System.out.println("Name is: " + name);  
8.         sc.close();  
9.     }  
10. }   

**Output:**

Enter your name: Jack
Name is: Jack

### Example 2: Reading Multiple Data Types

The following example demonstrates how to read different data types such as String, int, and double using Scanner.

[](https://www.tpointtech.com/scanner-class-in-java#)[](https://www.tpointtech.com/scanner-class-in-java#)[](https://www.tpointtech.com/scanner-class-in-java#)

1. import java.util.Scanner;  

2. public class ScannerExample2 {  
3.     public static void main(String args[]) {  

4.         Scanner sc = new Scanner(System.in);  

5.         System.out.print("Enter your name: ");  
6.         String name = sc.next();  

7.         System.out.print("Enter your age: ");  
8.         int age = sc.nextInt();  

9.         System.out.print("Enter your salary: ");  
10.         double salary = sc.nextDouble();  

11.         System.out.println("Name: " + name);  
12.         System.out.println("Age: " + age);  
13.         System.out.println("Salary: " + salary);  

14.         sc.close();  
15.     }  
16. }    

**Output:**

Enter your name: Andrew
Enter your age: 23
Enter your salary: 25000
Name: Andrew
Age: 23
Salary: 25000.0

### Example 3: Using Scanner with Delimiter

The following example demonstrates how to change the delimiter and tokenize a string using the Scanner class.

[](https://www.tpointtech.com/scanner-class-in-java#)[](https://www.tpointtech.com/scanner-class-in-java#)[](https://www.tpointtech.com/scanner-class-in-java#)

1. import java.util.Scanner;  

2. public class ScannerExample3 {  
3.     public static void main(String args[]) {  

4.         String str = "Hello/This is TpointTech/My name is Jack.";  
5.         Scanner scanner = new Scanner(str);  

6.         scanner.useDelimiter("/");  

7.         System.out.println("--- Tokenized Output ---");  
8.         while (scanner.hasNext()) {  
9.             System.out.println(scanner.next());  
10.         }  

11.         System.out.println("Delimiter used: " + scanner.delimiter());  
12.         scanner.close();  
13.     }  
14. }  

**Output:**

--- Tokenized Output ---
Hello
This is TpointTech
My name is Jack.
Delimiter used: /