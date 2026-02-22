In Java, an enum is a special data type used to represent a fixed set of constants. In this chapter, we will learn about the enums (enumeration), how to define and use them.

## What is Java Enum?

A Java **enum** is a data type that is used to define a fixed set of constants. Enum constants are implicitly public, static, and final that means they cannot be changed once defined. According to [Java naming conventions](https://www.oracle.com/java/technologies/javase/codeconventions-namingconventions.html), enum constants are written in **uppercase letters**. Enums were introduced in **JDK 1.5** and provide a type-safe way to represent a set of predefined values in your programs.

**Java enum** (Enumeration) is a data type that is used when we need to represent a fixed set of constants. Unlike [C](https://www.tpointtech.com/c-programming-language-tutorial)/[C++](https://www.tpointtech.com/cpp-tutorial), the enum in Java is more powerful. According to the [Java naming conventions](https://www.tpointtech.com/java-naming-conventions), we should have all constants in capital letters. So, we have enum constants in capital letters. The [Java](https://www.tpointtech.com/java-tutorial) enum constants are static and final implicitly. It is available since JDK 1.5.

## Common Examples of Enum

The following examples show scenarios where enums are helpful:

- **Days:** SUNDAY, MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY
- **Directions:** NORTH, SOUTH, EAST, WEST
- **Seasons:** SPRING, SUMMER, AUTUMN (or FALL), WINTER
- **Colors:** RED, YELLOW, BLUE, GREEN, WHITE, BLACK
- **Sizes:** SMALL, MEDIUM, LARGE, EXTRALARGE
- **Planets:** MERCURY, VENUS, EARTH, MARS, JUPITER, SATURN, URANUS, NEPTUNE
- **Months:** JANUARY, FEBRUARY, MARCH, APRIL, MAY, JUNE, JULY, AUGUST, SEPTEMBER, OCTOBER, NOVEMBER, DECEMBER

We observe that all enums have fixed values.

## Defining enum

Java provides the **enum** keyword to define the enum data type. We can define an enum either inside the class or outside the class because it is similar to classes. Java enum internally inherits the Enum class, so it cannot inherit any other class, but it can implement many interfaces. We can have fields, [constructors](https://www.tpointtech.com/java-constructor), methods, and main() methods in a Java enum.

### Syntax

Use the following syntax to define an enum:

[](https://www.tpointtech.com/java-enums#)[](https://www.tpointtech.com/java-enums#)[](https://www.tpointtech.com/java-enums#)

1. enum enumName {  
2. //values  
3. }  

### Syntax Example

The following shows how to define a simple enum:

[](https://www.tpointtech.com/java-enums#)[](https://www.tpointtech.com/java-enums#)[](https://www.tpointtech.com/java-enums#)

1. //defining enum   
2. enum Direction {   
3.    NORTH, SOUTH, EAST, WEST   
4. }  

The semicolon (;) at the end of the enum constants is optional. For example:

[](https://www.tpointtech.com/java-enums#)[](https://www.tpointtech.com/java-enums#)[](https://www.tpointtech.com/java-enums#)

1. //defining enum   
2. enum Direction {   
3.    NORTH, SOUTH, EAST, WEST;  
4. }  

Both the definitions of Java enum are the same. These values inside the braces are called **enum constants**.

## Using an enum as a Variable

We can also create a variable for an enum type. For example,

[](https://www.tpointtech.com/java-enums#)[](https://www.tpointtech.com/java-enums#)[](https://www.tpointtech.com/java-enums#)

1. Size clothSize;  

Here, cloth is a variable of type Size. It has four values.

[](https://www.tpointtech.com/java-enums#)[](https://www.tpointtech.com/java-enums#)[](https://www.tpointtech.com/java-enums#)

1. clothSize = Size.SMALL;  
2. clothSize = Size.MEDIUM;  
3. clothSize = Size.LARGE;  
4. clothSize = Size.EXTRALARGE;  

## Access Values of an Enum

You can access the values of an enum using the **enum variable** or the built-in values() method.

### Syntax

Here is the syntax to access enum values:

[](https://www.tpointtech.com/java-enums#)[](https://www.tpointtech.com/java-enums#)[](https://www.tpointtech.com/java-enums#)

1. EnumType enumVar = EnumType.CONSTANT_NAME;  

### Example

The following example demonstrates how you can access the the values of an enum:

[](https://www.tpointtech.com/java-enums#)[](https://www.tpointtech.com/java-enums#)[](https://www.tpointtech.com/java-enums#)

1. enum Days {  
2.     SUNDAY, MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY  
3. }  

4. public class Main {  
5.     public static void main(String[] args) {  
6.         // Accessing a single enum value  
7.         Days today = Days.WEDNESDAY;  
8.         System.out.println("Today is: " + today);  

9.         // Accessing all enum values  
10.         System.out.println("All days of the week:");  
11.         for (Days d : Days.values()) {  
12.             System.out.println(d);  
13.         }  
14.     }  
15. }  

**Output:**

Today is: WEDNESDAY
All days of the week:
SUNDAY
MONDAY
TUESDAY
WEDNESDAY
THURSDAY
FRIDAY
SATURDAY

## Defining an Enum Outside the Class

You can define an enum outside a class to make it accessible to multiple classes in the same package.

### Example

The following example demonstrates how to define and use an enum outside the class.

[](https://www.tpointtech.com/java-enums#)[](https://www.tpointtech.com/java-enums#)[](https://www.tpointtech.com/java-enums#)

1. enum Direction {  
2.    NORTH, SOUTH, EAST, WEST   
3. }  
4. class Main {  
5.    public static void main(String[] args) {  
6.       System.out.println(Direction.NORTH);  
7.       System.out.println(Direction.WEST);  
8.    }  
9. }  

**Output:**

NORTH
WEST

## Defining an enum Inside the Class

You can define an enum inside a class to keep it encapsulated and limit its usage to that class.

### Example

The following example demonstrates how to define and use an enum inside a class.

[](https://www.tpointtech.com/java-enums#)[](https://www.tpointtech.com/java-enums#)[](https://www.tpointtech.com/java-enums#)

1. class Main {    
2. //defining the enum inside the class    
3. public enum Season { WINTER, SPRING, SUMMER, FALL }    
4. //main method    
5. public static void main(String[] args) {    
6. //traversing the enum    
7. for (Season s : Season.values())    
8. System.out.println(s);    
9. }}    

**Output:**

WINTER
SPRING
SUMMER
FALL

## The main() Method Inside the enum

If we put the main() method inside the enum, we can run the enum directly as we have shown in the following code.

### Example

The following example demonstrates how to include and run a main() method inside an enum.

[](https://www.tpointtech.com/java-enums#)[](https://www.tpointtech.com/java-enums#)[](https://www.tpointtech.com/java-enums#)

1. enum Season {     
2. WINTER, SPRING, SUMMER, FALL;    
3. public static void main(String[] args) {    
4. Season s=Season.WINTER;    
5. System.out.println(s);    
6. }    
7. }    

**Output:**

WINTER

## Using an enum with a switch Statement

You can use enum constants in a switch statement to execute different code based on the enum value.

### Example

The following example demonstrates how to use an enum with a switch statement.

[](https://www.tpointtech.com/java-enums#)[](https://www.tpointtech.com/java-enums#)[](https://www.tpointtech.com/java-enums#)

1. class Main {    
2. enum Day{ SUNDAY, MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY} public static void main(String args[]) {    
3. Day day=Day.MONDAY;    
4. switch(day) {    
5. case SUNDAY:     
6.  System.out.println("Sunday");    
7.  break;    
8. case MONDAY:     
9.  System.out.println("Monday");    
10.  break;    
11. default:    
12. System.out.println("other day");    
13. }    
14. }}    

**Output:**

Monday

## Using an Enum as a Variable

You can declare variables of an enum type to store and work with specific enum constants in your program.

### Example

The following example demonstrates how to use an enum as a variable.

[](https://www.tpointtech.com/java-enums#)[](https://www.tpointtech.com/java-enums#)[](https://www.tpointtech.com/java-enums#)

1. public class Main {  
2.     enum TrafficLight {  
3.         RED, YELLOW, GREEN  
4.     }  
5.     public static void main(String[] args) {  
6.         TrafficLight signal = TrafficLight.YELLOW;  
7.         if (signal == TrafficLight.GREEN) {  
8.             System.out.println("Go!");  
9.         } else if (signal == TrafficLight.RED) {  
10.             System.out.println("Stop!");  
11.         } else if (signal == TrafficLight.YELLOW) {  
12.             System.out.println("Get ready...");  
13.         }  
14.     }  
15. }  

**Output:**

Get ready...

## Initializing Specific Values to the enum Constants

As specified earlier, an Enum can have fields, constructors, and methods. The enum constants have an initial value that starts from 0, 1, 2, 3, and so on. But we can initialize the specific value to the enum constants by defining fields and constructors.

### Example

The following example demonstrates how to initialize and use specific values with enum constants.

[](https://www.tpointtech.com/java-enums#)[](https://www.tpointtech.com/java-enums#)[](https://www.tpointtech.com/java-enums#)

1. class Main {    
2. enum Season {     
3. WINTER(5), SPRING(10), SUMMER(15), FALL(20);     
4. private int value;    
5. //enum type construtor  
6. private Season(int value) {    
7. this.value=value;    
8. }    
9. }    
10. public static void main(String args[]) {    
11. for (Season s : Season.values())    
12. System.out.println(s+" "+s.value);    
13. }}    

**Output:**

WINTER 5
SPRING 10
SUMMER 15
FALL 20

## Enum Constructor and Internal Implementation

The constructor of an enum type is always private. If a private constructor is not explicitly declared, the Java compiler automatically creates one. The compiler adds several built-in methods to every enum, including:

- values(): It returns an array of all enum constants
- valueOf(String name): It returns the enum constant with the specified name
- ordinal(): It returns the position of the constant in the enum declaration (starting from 0)

It internally creates a static and final class for the enum.

### Example: Enum with Constructor and Values

This example demonstrate the enum with constructor and values in Java.

[](https://www.tpointtech.com/java-enums#)[](https://www.tpointtech.com/java-enums#)[](https://www.tpointtech.com/java-enums#)

1. enum Season{    
2. WINTER(10),SUMMER(20);    
3. private int value;    
4. Season(int value){    
5. this.value=value;    
6. }    
7. }     

### Internal Code Generated by Compiler

The Java compiler generates code similar to the following for the above enum:

[](https://www.tpointtech.com/java-enums#)[](https://www.tpointtech.com/java-enums#)[](https://www.tpointtech.com/java-enums#)

1. final class Season extends Enum    
2. {    
3.     public static Season[] values()    
4.     {    
5.         return (Season[])$VALUES.clone();    
6.     }    
7.     public static Season valueOf(String s)    
8.     {    
9.         return (Season)Enum.valueOf(Season, s);    
10.     }    
11.     private Season(String s, int i, int j)    
12.     {    
13.         super(s, i);    
14.         value = j;    
15.     }    
16.     public static final Season WINTER;    
17.     public static final Season SUMMER;    
18.     private int value;    
19.     private static final Season $VALUES[];    
20.     static     
21.     {    
22.         WINTER = new Season("WINTER", 0, 10);    
23.         SUMMER = new Season("SUMMER", 1, 20);    
24.         $VALUES = (new Season[] {    
25.             WINTER, SUMMER    
26.         });    
27.     }    
28. }    

## Using an enum in an if Statement

A variable pointing to an enum constant must frequently be compared to other possible constants in the enum type since Java enum are constants.

### Syntax

It has the following syntax:

[](https://www.tpointtech.com/java-enums#)[](https://www.tpointtech.com/java-enums#)[](https://www.tpointtech.com/java-enums#)

1. if (enumVariable == EnumType.CONSTANT) {  
2.     // logic for the specific enum constant  
3. }  

### Example

RED, YELLOW, and GREEN are the three constants defined by the TrafficLight enum in this example. The if-else statement checks the signal's current value and then performs the proper action.

### Example

[](https://www.tpointtech.com/java-enums#)[](https://www.tpointtech.com/java-enums#)[](https://www.tpointtech.com/java-enums#)

1. public class Main {  
2.     enum TrafficLight {  
3.         RED, YELLOW, GREEN  
4.     }  
5.     public static void main(String[] args) {  
6.         TrafficLight signal = TrafficLight.YELLOW;  
7.         if (signal == TrafficLight.GREEN) {  
8.             System.out.println("Go!");  
9.         } else if (signal == TrafficLight.RED) {  
10.             System.out.println("Stop!");  
11.         } else if (signal == TrafficLight.YELLOW) {  
12.             System.out.println("Get ready...");  
13.         }  
14.     }  
15. }  

**Output:**

Get ready...

## Java enum Iteration

Java's built-in values() [function](https://www.tpointtech.com/java-function) makes it simple to iterate enums by returning an array containing all of the constants defined in the enum. It enables us to use a conventional for loop or an advanced for loop to iterate through all enum values. When we need to display every option that could be selected, execute operations on every value, or check input against specified constants, enum iteration is useful.

### Syntax

It has the following syntax:

[](https://www.tpointtech.com/java-enums#)[](https://www.tpointtech.com/java-enums#)[](https://www.tpointtech.com/java-enums#)

1. for (EnumType variable : EnumType.values()) {  
2.     // logic using variable  
3. }  

### Example

All of the days of the week are listed in this example using the Day enum. Day.values() is used by the for loop for looping through and resulting in each enum constant. When working with menus, drop-down menus, or executing operations on particular enum constants without hardcoding them, this method is extremely useful.

### Example

[](https://www.tpointtech.com/java-enums#)[](https://www.tpointtech.com/java-enums#)[](https://www.tpointtech.com/java-enums#)

1. public class Main {  
2.     enum Day {   
3.         MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY, SUNDAY  
4.     }  
5.     public static void main(String[] args) {  
6.         System.out.println("The Days of the week are:");  
7.         for (Day day : Day.values()) {  
8.             System.out.println(day);  
9.         }  
10.     }  
11. }  

**Output:**

The Days of the week are:
MONDAY
TUESDAY
WEDNESDAY
THURSDAY
FRIDAY
SATURDAY
SUNDAY

## Java Enum Class

An **enum** class is a special type of class used to define a fixed set of constants. Unlike regular classes, each constant in an enum is automatically created as an instance (object) of the **enum** class by the compiler. All enum constants are implicitly public, static, and final, so they cannot be changed once defined.

Every **enum** class implicitly extends the **Enum** class.

### Syntax

It has the following syntax:

[](https://www.tpointtech.com/java-enums#)[](https://www.tpointtech.com/java-enums#)[](https://www.tpointtech.com/java-enums#)

1. public abstract class Enum<E extends Enum<E>> extends Object implements Comparable<E>, Serializable  

### Methods of Enum Class

Enum classes have a few predefined methods that are easily accessible. They are as follows.

|   |   |
|---|---|
|**Method**|**Description**|
|**clone()**|It throws CloneNotSupportedException.|
|**compareTo(E o)**|It compares this enum with the specified object for order.|
|**equals(Object others)**|It returns true if the specified object is equal to this enum constant.|
|**finalize()**|Enum classes cannot have finalize methods.|
|**getDeclaringClass()**|It returns the Class object corresponding to this enum constant's enum type.|
|**hashCode()**|It returns a hash code for this enum constant.|
|**name()**|It returns the name of this enum constant, exactly as declared in its enum declaration.|
|**ordinal()**|It returns the ordinal of this enumeration constant (its position in its enum declaration, where the initial constant is assigned an ordinal of zero).|
|**toString()**|It returns the name of this enum constant, as contained in the declaration.|
|**valueOf(Class<T> enumType, String name)**|It returns the enum constant of the specified enum type with the specified name.|

### Example Using Enum Class Methods

The following example demonstrates creating and using enums using the enum class and its method.

[](https://www.tpointtech.com/java-enums#)[](https://www.tpointtech.com/java-enums#)[](https://www.tpointtech.com/java-enums#)

1. public class Main {  
2.     // Define an enum with a custom description  
3.     enum Day {  
4.         MONDAY("Start of the work week..."),  
5.         TUESDAY("Work in progress..."),  
6.         WEDNESDAY("Mid of the week..."),  
7.         THURSDAY("About to Complete..."),  
8.         FRIDAY("Last day of the work week"),  
9.         SATURDAY("Weekend!"),  
10.         SUNDAY("Rest day");  
11.         private String description;  
12.         //Creating a Constructor  
13.         Day(String description) {  
14.             this.description = description;  
15.         }  
16.         // Method to return custom description  
17.         @Override  
18.         public String toString() {  
19.             return this.description;  
20.         }  
21.     }  
22.     public static void main(String[] args) {  
23.         // ordinal()  method  
24.         System.out.println("The ordinal() values are:");  
25.         for (Day d : Day.values()) {  
26.             System.out.println(d.name() + " -> ordinal: " + d.ordinal());  
27.         }  
28.         // compareTo() method  
29.         System.out.println("\n compareTo() example:");  
30.         System.out.println("MONDAY vs FRIDAY: " + Day.MONDAY.compareTo(Day.FRIDAY));   
31.         System.out.println("SUNDAY vs SUNDAY: " + Day.SUNDAY.compareTo(Day.SUNDAY));    
32.         // toString() method  
33.         System.out.println("\ntoString() example:");  
34.         for (Day d : Day.values()) {  
35.             System.out.println(d.name() + " says: " + d.toString());  
36.         }  
37.         // name() method  
38.         System.out.println("\nname() example:");  
39.         Day today = Day.THURSDAY;  
40.         System.out.println("Enum constant name: " + today.name());  
41.         // valueOf() method  
42.         System.out.println("\nvalueOf() example:");  
43.         String input = "FRIDAY";  
44.         Day dayFromString = Day.valueOf(input);  
45.         System.out.println("\nConverted from string: " + dayFromString.name());  
46.         // values() method  
47.         System.out.println("\nvalues() iteration:");  
48.         for (Day d : Day.values()) {  
49.             System.out.println(d + " (" + d.name() + ")");  
50.         }  
51.     }  
52. }  

**Output:**

The ordinal() values are:
MONDAY -> ordinal: 0
TUESDAY -> ordinal: 1
WEDNESDAY -> ordinal: 2
THURSDAY -> ordinal: 3
FRIDAY -> ordinal: 4
SATURDAY -> ordinal: 5
SUNDAY -> ordinal: 6

compareTo() example:
MONDAY vs FRIDAY: -4
SUNDAY vs SUNDAY: 0

toString() example:
MONDAY says: Start of the work week...
TUESDAY says: Work in progress...
WEDNESDAY says: Mid of the week...
THURSDAY says: About to Complete...
FRIDAY says: Last day of the work week
SATURDAY says: Weekend!
SUNDAY says: Rest day

name() example:
Enum constant name: THURSDAY

valueOf() example:
Converted from string: FRIDAY

values() iteration:
Start of the work week... (MONDAY)
Work in progress... (TUESDAY)
Mid of the week... (WEDNESDAY)
About to Complete... (THURSDAY)
Last day of the work week (FRIDAY)
Weekend! (SATURDAY)
Rest day (SUNDAY)

## Difference Between enum and Enum

The following table shows the difference between enum and Enum in Java.

|enum|Enum|
|---|---|
|It is a keyword.|It is an abstract class that belongs to java.lang package.|
|It allows to create of enumerated types.|It provides functionality for enum types.|
|It automatically extends the Enum class.|It extends the Object class.|
|It does not provide any methods.|It provides methods like, valueOf(), ordinal(), toString(), name(), etc.|