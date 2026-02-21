
The Java switch statement executes one statement from multiple conditions. It is like [an if-else-if](https://www.tpointtech.com/java-if-else) ladder statement. The switch statement works with byte, short, int, long, enum types, String, and some wrapper types, such as Byte, Short, Integer, and Long. Since Java 7, we can use [strings](https://www.tpointtech.com/java-string) in the switch statement.

## What Is switch Statement in Java?

The switch statement can be described as a control flow type statement used to manipulate the flow of program execution and invoke various branches of code based on the value of an expression.

In other words, the switch statement tests the equality of a variable against multiple values.

## Rules and Constraints of Java Switch Statement

There are several rules and constraints of Java switch statement. Some of them are as follows:

- There can be one or N case values for a switch expression.
- The case value must be of switch expression type only. The case value must be literal or constant. It doesn't allow [variables](https://www.tpointtech.com/java-variables).
- The case values must be unique. In case of a duplicate value, it renders a compile-time error.
- The Java switch expression must be of byte, short, int, long (with its Wrapper type), [enums](https://www.tpointtech.com/java-switch)and string.
- Each case statement can have a break statement, which is optional. When control reaches the[break statement](https://www.tpointtech.com/java-break), it jumps to the control after the switch expression. If a break statement is not found, the next case is executed.
- The case value can have a default label, which is optional.

In Java, the switch statement provides a more detailed alternative that avoids the use of nested or multiple if-else statements when associated with a single variable.

The syntax of the Java switch statement contains the **switch** keyword, which is followed by the expression that needs to be evaluated using parentheses. The mentioned expression must definitely evaluate to a definite data type, which is primitive such as int, char, or enum.

## Syntax of Switch Statement

Here is the syntax of switch statement:

[](https://www.tpointtech.com/java-switch#)[](https://www.tpointtech.com/java-switch#)[](https://www.tpointtech.com/java-switch#)

1. switch(expression) {      
2. case value1:      
3.  //code to be executed;      
4.  break;  //optional    
5. case value2:      
6.  //code to be executed;      
7.  break;  //optional    
8. ......      
9. default:       
10.   Code to be executed if all cases are not matched.    
11. }      

## Flowchart of Switch Statement

The following images demonstrates the working flow of a switch statement:

![flow of switch statement in java](https://images.tpointtech.com/core/images/java-switch-statement-1.png)

In Java, the switch statement can also contain a default label. The default label will be executed only in the situation when none of the case labels match the expression's value. Declaring a default label is considered optional, but it can be useful in the event of unexpected values or inputs.

Now, we are going to discuss several examples to demonstrate the working of Switch Statement in different aspects.

## Different Examples of switch Statement

Practice the following examples to understand the concept of switch statement in Java:

### Example 1: Simple Switch Statement

Let us take an example to demonstrate the working of the switch statement in Java.

### Example

[](https://www.tpointtech.com/java-switch#)[](https://www.tpointtech.com/java-switch#)[](https://www.tpointtech.com/java-switch#)

1. public class Main {    
2. public static void main(String[] args) {    
3.     //Declaring a variable for switch expression    
4.     int number=20;    
5.     //Switch expression    
6.     switch(number){    
7.     //Case statements    
8.     case 10: System.out.println("10");    
9.     break;    
10.     case 20: System.out.println("20");    
11.     break;    
12.     case 30: System.out.println("30");    
13.     break;    
14.     //Default case statement    
15.     default:System.out.println("Not in 10, 20 or 30");    
16.     }    
17. }    
18. }    

**Output:**

20

### Example 2: Finding Month using switch Statement

Let us take an example to demonstrate how to find months using the switch statement in Java.

### Example

[](https://www.tpointtech.com/java-switch#)[](https://www.tpointtech.com/java-switch#)[](https://www.tpointtech.com/java-switch#)

1. //Java Program to demonstrate the example of the Switch statement, where we are printing the month name for the given number    
2. public class Main {      
3. public static void main(String[] args) {      
4.     //Specifying month number    
5.     int month=7;      
6.     String monthString="";    
7.     //Switch statement    
8.     switch(month){      
9.     //case statements within the switch block    
10.     case 1: monthString="1 - January";    
11.     break;      
12.     case 2: monthString="2 - February";    
13.     break;      
14.     case 3: monthString="3 - March";    
15.     break;      
16.     case 4: monthString="4 - April";    
17.     break;      
18.     case 5: monthString="5 - May";    
19.     break;      
20.     case 6: monthString="6 - June";    
21.     break;      
22.     case 7: monthString="7 - July";    
23.     break;      
24.     case 8: monthString="8 - August";    
25.     break;      
26.     case 9: monthString="9 - September";    
27.     break;      
28.     case 10: monthString="10 - October";    
29.     break;      
30.     case 11: monthString="11 - November";    
31.     break;      
32.     case 12: monthString="12 - December";    
33.     break;      
34.     default:System.out.println("Invalid Month!");      
35.     }      
36.     //Printing the month of the given number    
37.     System.out.println(monthString);    
38. }      
39. }     

**Output:**

7 - July

### Example 3: Checking Vowel or Consonant

If the character is A, E, I, O, or U, it is a vowel; otherwise, consonant. It is not case-sensitive.

### Example

[](https://www.tpointtech.com/java-switch#)[](https://www.tpointtech.com/java-switch#)[](https://www.tpointtech.com/java-switch#)

1. public class Main {      
2. public static void main(String[] args) {      
3.     char ch='O';      
4.     switch(ch)  {    
5.         case 'a':     
6.             System.out.println("Vowel");    
7.             break;    
8.         case 'e':     
9.             System.out.println("Vowel");    
10.             break;    
11.         case 'i':     
12.             System.out.println("Vowel");    
13.             break;    
14.         case 'o':     
15.             System.out.println("Vowel");    
16.             break;    
17.         case 'u':     
18.             System.out.println("Vowel");    
19.             break;    
20.         case 'A':     
21.             System.out.println("Vowel");    
22.             break;    
23.         case 'E':     
24.             System.out.println("Vowel");    
25.             break;    
26.         case 'I':     
27.             System.out.println("Vowel");    
28.             break;    
29.         case 'O':     
30.             System.out.println("Vowel");    
31.             break;    
32.         case 'U':     
33.             System.out.println("Vowel");    
34.             break;    
35.         default:     
36.             System.out.println("Consonant");    
37.     }    
38. }      
39. }     

**Output:**

Vowel

### Java Switch Statement is a fall-through

The Java switch statement is fall-through. It means it executes all statements after the first match if a break statement is not present.

### Example

[](https://www.tpointtech.com/java-switch#)[](https://www.tpointtech.com/java-switch#)[](https://www.tpointtech.com/java-switch#)

1. //Java Switch Example where we are omitting the break statement    
2. public class Main {    
3. public static void main(String[] args) {    
4.     int number=20;    
5.     //switch expression with int value    
6.     switch(number){    
7.     //switch cases without break statements    
8.     case 10: System.out.println("10");    
9.     case 20: System.out.println("20");    
10.     case 30: System.out.println("30");    
11.     default:System.out.println("Not in 10, 20 or 30");    
12.     }    
13. }    
14. }    

**Output:**

20
30
Not in 10, 20 or 30

## Java Switch Statement with String

Since Java 7, Java allows us to use strings in switch expressions. The case statement should be a string literal.

### Example

[](https://www.tpointtech.com/java-switch#)[](https://www.tpointtech.com/java-switch#)[](https://www.tpointtech.com/java-switch#)

1. //Java Program to demonstrate the use of Java Switch statement with String    
2. public class Main {      
3. public static void main(String[] args) {      
4.     //Declaring String variable    
5.     String levelString="Expert";    
6.     int level=0;    
7.     //Using String in Switch expression    
8.     switch(levelString){      
9.     //Using String Literals in Switch Case    
10.     case "Beginner": level=1;    
11.     break;      
12.     case "Intermediate": level=2;    
13.     break;      
14.     case "Expert": level=3;    
15.     break;      
16.     default: level=0;    
17.     break;    
18.     }      
19.     System.out.println("Your Level is: "+level);    
20. }      
21. }  

**Output:**

Your Level is: 3

### Java Nested Switch Statement

We can use a switch statement inside another switch statement in Java. It is known as a nested switch statement.

### Example

[](https://www.tpointtech.com/java-switch#)[](https://www.tpointtech.com/java-switch#)[](https://www.tpointtech.com/java-switch#)

1. //Java Program to demonstrate the use of Java Nested Switch    
2. public class Main {      
3.     public static void main(String args[])  {    
4.       //C - CSE, E - ECE, M - Mechanical    
5.         char branch = 'C';                   
6.         int collegeYear = 4;    
7.         switch( collegeYear )  {    
8.             case 1:    
9.                 System.out.println("English, Maths, Science");    
10.                 break;    
11.             case 2:    
12.                 switch( branch )   {    
13.                     case 'C':    
14.                         System.out.println("Operating System, Java, Data Structure");    
15.                         break;    
16.                     case 'E':    
17.                         System.out.println("Micro processors, Logic switching theory");    
18.                         break;    
19.                     case 'M':    
20.                         System.out.println("Drawing, Manufacturing Machines");    
21.                         break;    
22.                 }    
23.                 break;    
24.             case 3:    
25.                 switch( branch )  {    
26.                     case 'C':    
27.                         System.out.println("Computer Organization, MultiMedia");    
28.                         break;    
29.                     case 'E':    
30.                         System.out.println("Fundamentals of Logic Design, Microelectronics");    
31.                         break;    
32.                     case 'M':    
33.                   System.out.println("Internal Combustion Engines, Mechanical Vibration");    
34.                         break;    
35.                 }    
36.                 break;    
37.             case 4:    
38.                 switch( branch )  {    
39.                     case 'C':    
40.                         System.out.println("Data Communication and Networks, MultiMedia");    
41.                         break;    
42.                     case 'E':    
43.                         System.out.println("Embedded System, Image Processing");    
44.                         break;    
45.                     case 'M':    
46.                         System.out.println("Production Technology, Thermal Engineering");    
47.                         break;    
48.                 }    
49.                 break;    
50.         }    
51.     }    
52. }    

**Output:**

Data Communication and Networks, MultiMedia

## Using enum in Switch Statement

Java allows us to use an enum in a switch statement. A Java enum is a class that represents a group of constants. (immutable, such as final variables). We use the keyword enum and place the constants in curly braces, separated by commas.

### Example

[](https://www.tpointtech.com/java-switch#)[](https://www.tpointtech.com/java-switch#)[](https://www.tpointtech.com/java-switch#)

1. //Java Program to demonstrate the use of Enum in switch statement    
2. public class Main {        
3.        public enum Day {  Sun, Mon, Tue, Wed, Thu, Fri, Sat  }      
4.        public static void main(String args[])  {      
5.          Day[] DayNow = Day.values();      
6.            for (Day Now: DayNow)      {      
7.                 switch (Now)     {      
8.                     case Sun:      
9.                         System.out.println("Sunday");      
10.                         break;      
11.                     case Mon:      
12.                         System.out.println("Monday");      
13.                         break;      
14.                     case Tue:      
15.                         System.out.println("Tuesday");      
16.                         break;           
17.                     case Wed:      
18.                         System.out.println("Wednesday");      
19.                         break;      
20.                     case Thu:      
21.                         System.out.println("Thursday");      
22.                         break;      
23.                     case Fri:      
24.                         System.out.println("Friday");      
25.                         break;      
26.                     case Sat:      
27.                         System.out.println("Saturday");      
28.                         break;      
29.                 }      
30.             }      
31.         }      
32. }      

**Output:**

Sunday
Monday
Tuesday
Wednesday
Thursday
Friday
Saturday

### Java Wrapper in Switch Statement

Java allows us to use four [wrapper classes](https://www.tpointtech.com/wrapper-class-in-java) -Byte, Short, Integer, and Long - in the switch statement.

### Example

[](https://www.tpointtech.com/java-switch#)[](https://www.tpointtech.com/java-switch#)[](https://www.tpointtech.com/java-switch#)

1. //Java Program to demonstrate the use of the Wrapper class in a switch statement    
2. public class Main {         
3.        public static void main(String args[])   {           
4.             Integer age = 18;          
5.             switch (age)    {    
6.                 case (16):              
7.                     System.out.println("You are under 18.");    
8.                     break;    
9.                 case (18):                  
10.                     System.out.println("You are eligible to vote.");    
11.                     break;    
12.                 case (65):                  
13.                     System.out.println("You are senior citizen.");    
14.                     break;    
15.                 default:    
16.                     System.out.println("Please give the valid age.");    
17.                     break;    
18.             }               
19.         }    
20. }    

**Output:**

You are eligible to vote.

## Features and Limitations of Java Switch Statement

There are several features and limitations of the Java Switch Statament. Some of them are as follows:

- One of the major important features of the Java Switch statement is its fall-through behaviour. It means that if a case label does not contain a break statement, execution will be passed directly to the next case label. A switch statement can also include a default label, which is executed if none of the case labels match the expression's value. The default label is optional but can be useful for handling unexpected or unspecified values.
- Switch statements can only match exact values, and they cannot check ranges of values. This means that if you need to check for a range of values, you would need to use multiple case labels or resort to other control flow statements, such as if-else.
- Switch statements can only be used to check for equality between the expression and the case labels. They cannot perform more complex checks, such as checking conditions or using comparison operators.
- The expression in a switch statement must evaluate to a primitive data type (int, char, or enum) or a String (since Java 7). This limitation restricts the types of expressions that can be used with switch statements, making them less flexible in certain situations compared to other control flow statements.
- It's worth noting that starting from Java 12, switch statements have been enhanced to support switch expressions, which allow the switch statement to be used as an expression that returns a value. This feature offers more flexibility and can result in more concise and readable code in certain situations.
- Overall, the switch statement in Java is a powerful tool for controlling the flow of a program based on the value of an expression, offering a clear and efficient way to handle multiple branching scenarios.
- Switch statements can sometimes lead to code duplication, especially when multiple case blocks perform similar actions. It can make the code harder to maintain and debug.
- While switch statements can be used with String objects since Java 7, they cannot be used directly with other object types. This limitation can make switch statements less useful in scenarios where complex objects need to be compared and evaluated.