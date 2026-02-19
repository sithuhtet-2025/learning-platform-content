
In the C# programming language, the Enum is also known as an enumeration. It is used to store a set of named constants, such as season, days, month, size, etc. The enum constants are also known as enumerators. Enums in C# can be declared within or outside classes and structs using the enum keyword. It enables us to create a group of related symbolic names that represent different states or options inside their code.

Enum constants have default values that start from 0 and are incremented by 1 for each number. However, we can explicitly assign custom values if required.

For example, we can create an enum named Seasons, such as Winter, Spring, Summer, and Fall, instead of using 0, 1, 2, 3, etc., to represent seasons.

### Syntax of Enum

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-enum#)[](https://www.tpointtech.com/c-sharp-enum#)[](https://www.tpointtech.com/c-sharp-enum#)

1. enum EnumName  
2. {  
3.     Value1,  
4.     Value2,  
5.     Value3,  
6.     // ...  
7. }  

In this syntax,

- EnumName: It represents the name of the Enumeration.

### C# Enum Example

Let us take an example to illustrate the enum in C# programming.

### Example

[](https://www.tpointtech.com/c-sharp-enum#)[](https://www.tpointtech.com/c-sharp-enum#)[](https://www.tpointtech.com/c-sharp-enum#)

1. using System;    
2. public class EnumExample    
3. {    
4.     public enum Season   
5. {   
6. WINTER,  
7. SPRING,   
8. SUMMER,   
9. FALL  
10. }       
11.     public static void Main()    
12.     {    
13.         int x = (int)Season.WINTER;    
14.         int y = (int)Season.SUMMER;    
15.         Console.WriteLine("WINTER = {0}", x);    
16.         Console.WriteLine("SUMMER = {0}", y);    
17.     }    
18. }    

**Output:**

WINTER = 0
SUMMER = 2

**Explanation:**

In this example, we declare an enum called Season with four values. In the Main method, it converts two enum members (WINTER and SUMMER) into integers and outputs their respective values. By default, WINTER is 0, SPRING is 1, SUMMER is 2, and FALL is 3, so it prints 0 for WINTER and 2 for SUMMER.

## Features of C# Enum

There are several important features of the C# Enum. Some of them are as follows:

- Enumeration can be declared with the enum keyword within a class, namespace, or structure.
- It is used to define a set of named constants.
- Enum members should be unique inside the same enum.
- It can be utilized to define the custom integrals for the strings.
- By default, the enum base type is int.
- It can be utilized in switch statements.
- Enum members are by default public, static, and constant.

## Enum Inside a Class

In C# programming, an enum can also be defined inside a class. Let us take an example to illustrate the Enum inside the class and changing the index.

### Example

[](https://www.tpointtech.com/c-sharp-enum#)[](https://www.tpointtech.com/c-sharp-enum#)[](https://www.tpointtech.com/c-sharp-enum#)

1. using System;    
2. public class EnumExample    
3. {    
4.     public enum Season {   
5. WINTER=10,   
6. SPRING=11,   
7. SUMMER=12,   
8. FALL=13  
9. }      

10.     public static void Main()    
11.     {    
12.         int x = (int)Season.WINTER;    
13.         int y = (int)Season.SUMMER;    
14.         Console.WriteLine("WINTER = {0}", x);    
15.         Console.WriteLine("SUMMER = {0}", y);    
16.     }    
17. }    

**Output:**

WINTER = 10
SUMMER = 12

**Explanation:**

In this example, we declare an enum Season with WINTER as 10, and hence the subsequent members are auto-incremented. In the main() function, it converts WINTER and SUMMER to integers and prints them. The output will be WINTER = 10 and SUMMER = 12.

### C# Enum Example for Days (Declared Inside a Class)

Let us take an example for weekdays that is declared inside a class in C#.

### Example

[](https://www.tpointtech.com/c-sharp-enum#)[](https://www.tpointtech.com/c-sharp-enum#)[](https://www.tpointtech.com/c-sharp-enum#)

1. using System;    
2. public class EnumExample    
3. {    
4.     public enum Days {   
5. Sun,   
6. Mon,   
7. Tue,   
8. Wed,   
9. Thu,   
10. Fri,   
11. Sat   
12. };      
13.     public static void Main()    
14.     {    
15.         int x = (int)Days.Sun;    
16.         int y = (int)Days.Mon;    
17.         int z = (int)Days.Sat;    
18.         Console.WriteLine("Sun = {0}", x);    
19.         Console.WriteLine("Mon = {0}", y);    
20.         Console.WriteLine("Sat = {0}", z);    
21.     }    
22. }    

**Output:**

Sun = 0
Mon = 1
Sat = 6

**Explanation:**

In this example, we declare an enum Days consisting of days of the week with values from 0 by default. In the main() function, it converts Sun, Mon, and Sat into their integer values and outputs them. The output will be: Sun = 0, Mon = 1, Sat = 6.

## Enum Methods and Properties

There are several methods and properties of Enum in C#. Some of them are as follows:

### 1) GetValues in C#

In C# programming, the Enum.GetValues is utilized to retrieve an array of all values that are defined in an enum type.

**C# Enum Example: Accessing all values using getValues()**

Let us take an example to illustrate the C# enum values to access all values using the getValues() function.

### Example

[](https://www.tpointtech.com/c-sharp-enum#)[](https://www.tpointtech.com/c-sharp-enum#)[](https://www.tpointtech.com/c-sharp-enum#)

1. using System;    
2. public class EnumExample    
3. {    
4.     public enum Days { Sun, Mon, Tue, Wed, Thu, Fri, Sat };      
5.     public static void Main()    
6.     {    
7.         foreach (Days d in Enum.GetValues(typeof(Days)))    
8.         {    
9.             Console.WriteLine(d);    
10.         }    
11.     }    
12. }    

**Output:**

Sun
Mon
Tue
Wed
Thu
Fri
Sat

### 2) GetNames() in C#

In C# programming, the Enum.GetNames() method is utilized to retrieve an array of all the names that are defined in an enum type.

**C# Enum Example: Traversing all values using getNames()**

Let us take an example to illustrate the C# enum values to traverse all values using the getValues() function.

### Example

[](https://www.tpointtech.com/c-sharp-enum#)[](https://www.tpointtech.com/c-sharp-enum#)[](https://www.tpointtech.com/c-sharp-enum#)

1. using System;    
2. public class EnumExample    
3. {    
4.     public enum Days { Sun, Mon, Tue, Wed, Thu, Fri, Sat };      
5.     public static void Main()    
6.     {    
7.         foreach (string s in Enum.GetNames(typeof(Days)))    
8.         {    
9.             Console.WriteLine(s);    
10.         }    
11.     }    
12. }   

**Output:**

Sun
Mon
Tue
Wed
Thu
Fri
Sat

**Explanation:**

In this example, we have taken an enum Days with values ranging from Sun to Sat. In the main() function, it retrieves all the enum names as strings using Enum.GetNames() and prints each one separately with a foreach loop, displaying all the days of the week.

### 3) IsDefined() in C#

In C# programming, this method is used to check whether a given value or name exists in a specified enumeration. It returns a Boolean result.

**C# Enum.IsDefined() Example**

Let us take an example to illustrate the enum.IsDefined() function in C#.

### Example

[](https://www.tpointtech.com/c-sharp-enum#)[](https://www.tpointtech.com/c-sharp-enum#)[](https://www.tpointtech.com/c-sharp-enum#)

1. using System;  

2. public class EnumExample  
3. {  
4.     public enum Colors {   
5.       Red,   
6.       Green,   
7.       Blue,   
8.       Yellow,   
9.       Black,   
10.       Orange   

11.     }  

12.     public static void Main()  
13.     {  
14.         Console.WriteLine(Enum.IsDefined(typeof(Colors), "Black"));     // true  
15.         Console.WriteLine(Enum.IsDefined(typeof(Colors), "Pink"));  // false  
16.     }  
17. }  

**Output:**

True
False

## Converting Enums

In C# programming, Enums are typed constants, but they can be cast explicitly to and from their underlying numeric types like int, byte, etc. We can also convert enums to strings and parse strings to enum values. It is useful when we work with UI, files, or databases where we need to display or store enum names or values.

**C# Example for Converting Enums**

Let us take an example to convert the Enum in C#.

### Example

[](https://www.tpointtech.com/c-sharp-enum#)[](https://www.tpointtech.com/c-sharp-enum#)[](https://www.tpointtech.com/c-sharp-enum#)

1. using System;  
2. public class EnumExample  
3. {  
4.     public enum Status { Off = 0, On = 1 }  
5.     public static void Main()  
6.     {  
7.         int val = (int)Status.On;  
8.         Console.WriteLine("Integer value: " + val);   
9.         Status s = (Status)0;  
10.         Console.WriteLine("Enum value: " + s);    
11.         string name = Status.On.ToString();  
12.         Console.WriteLine("String value: " + name);  
13.         Status parsed = (Status)Enum.Parse(typeof(Status), "Off");  
14.         Console.WriteLine("Parsed enum: " + parsed);   
15.     }  
16. }  

**Output:**

Integer value: 1
Enum value: Off
String value: On
Parsed enum: Off

**Explanation:**

In this example, we define an enum Status with Off=0 and On=1. It converts an enum member to its integer value, casts an integer back to the enum, converts an enum to a string using the ToString() function, and parses a string into the corresponding enum value using the Enum.Parse() function.

## Enums in Switch Statements

In C# programming, Enums work very well with switch statements. Using an enum within a switch statement allows us to perform different operations depending on the enum value. It helps to improve code readability and maintainability with no hardcoded literals.

### Syntax:

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-enum#)[](https://www.tpointtech.com/c-sharp-enum#)[](https://www.tpointtech.com/c-sharp-enum#)

1. enum Enumname { Val1, Val2, Val3 }  
2. Enumname var = EnumName.Val2;  
3. switch (var)  
4. {  
5.     case EnumName.Val1:  
6.         // block of code  
7.         break;  
8.     case EnumName.Val2:  
9.         // block of code  
10.         break;  
11.     default:  
12.         // default code block  
13.         break;  
14. }  

### C# Enum Example using Switch Statement

Let us take an example to illustrate the enum using a switch statement in C#.

### Example

[](https://www.tpointtech.com/c-sharp-enum#)[](https://www.tpointtech.com/c-sharp-enum#)[](https://www.tpointtech.com/c-sharp-enum#)

1. using System;  
2. public class EnumSwitch  
3. {  
4.     public enum Day { Sun, Mon, Tue, Wed, Thu, Fri, Sat }  
5.     public static void Main()  
6.     {  
7.         Day day= Day.Wed;  
8.         switch (day)  
9.         {  
10.             case Day.Sun:  
11.                 Console.WriteLine("It's Sunday");  
12.                 break;  
13.             case Day.Wed:  
14.                 Console.WriteLine("Midweek day");  
15.                 break;  
16.             case Day.Sat:  
17.                 Console.WriteLine("Weekend!");  
18.                 break;  
19.             default:  
20.                 Console.WriteLine("A regular weekday");  
21.                 break;  
22.         }  
23.     }  
24. }  

**Output:**

Midweek day

**Explanation:**

In this example, we declare an enum Day with the days of the week. In the main() function, it initializes today to Wed and uses a switch to test the value. It prints "Midweek day" because the value is Day.Wed.

## Specifying Enum Type in C#

The underlying type of an enum in C# is int, which represents each member as a 32-bit signed integer. We can also specify some other integral type, such as byte, sbyte, short, ushort, uint, long, or ulong, to manage memory consumption or to accommodate external data formats.

**Syntax:**

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-enum#)[](https://www.tpointtech.com/c-sharp-enum#)[](https://www.tpointtech.com/c-sharp-enum#)

1. enum EnumName : underlyingType  
2. {  
3.     Value1,  
4.     Value2,  
5.     Value3  
6. }  

### C# Enum Example to specify Enum Type

Let us take an example to specify an Enum type in C#.

### Example

[](https://www.tpointtech.com/c-sharp-enum#)[](https://www.tpointtech.com/c-sharp-enum#)[](https://www.tpointtech.com/c-sharp-enum#)

1. using System;  
2. enum TemperatureLevel : short     
3. {  
4.     Low = -10,  
5.     Normal = 0,  
6.     Warm = 20,  
7.     Hot = 35,  
8.     Extreme = 50  
9. }  
10. class Tpoint  
11. {  
12.     static void Main()  
13.     {  
14.         TemperatureLevel level = TemperatureLevel.Normal;  
15.         Console.WriteLine($"Temperature Level: {level}");  
16.         Console.WriteLine($"Underlying Value: {(short)level}");  
17.         TemperatureLevel extreme = (TemperatureLevel)50;  
18.         Console.WriteLine($"Casted from number: {extreme}");  
19.     }  
20. }  

**Output:**

Temperature Level: Normal
Underlying Value: 0
Casted from number: Extreme

**Explanation:**

In this example, we define an enum TemperatureLevel with short as the underlying type, assigning specific numeric values to temperature levels. In the main() function, it assigns a level to Normal and prints out both the name of the enum and its value. After that, it casts the number 50 to the enum, which is equivalent to the value Extreme, and prints it out.

## [Flags] Attribute for Bitwise Enums

In C#, using the [Flags] attribute on an enum allows you to represent a collection of bit fields. It allows combining enum values with bitwise operators, which proves useful for situations where there are many choices, permissions, or statuses that can be active simultaneously.

### C# Example to [Flags] Attribute for Bitwise Enum

Let us take an example to illustrate the flag attribute for a bitwise enum in C#.

### Example

[](https://www.tpointtech.com/c-sharp-enum#)[](https://www.tpointtech.com/c-sharp-enum#)[](https://www.tpointtech.com/c-sharp-enum#)

1. using System;  
2. [Flags]  
3. public enum A  
4. {  
5.     None    = 0,     
6.     Read    = 1,     
7.     Write   = 2,     
8.     Execute = 4  
9. }  
10. class Tpoint  
11. {  
12.     static void Main()  
13.     {  
14.         A rights = A.Read | A.Write;  
15.         Console.WriteLine($"Assigned Rights: {rights}");  
16.         bool canWrite = rights.HasFlag(A.Write);  
17.         Console.WriteLine($"Has Write Permission: {canWrite}");  
18.         rights |= A.Execute;  
19.         Console.WriteLine($"Updated Rights: {rights}");  
20.         rights &= ~A.Read;  
21.         Console.WriteLine($"After Removing Read: {rights}");  
22.         if (rights == A.None)  
23.             Console.WriteLine("No permissions assigned.");  
24.     }  
25. }  

**Output:**

Assigned Rights: Read, Write
Has Write Permission: True
Updated Rights: Read, Write, Execute
After Removing Read: Write, Execute

**Explanation:**

In this example, we declare an enum A with the [Flags] attribute so that multiple values can be "combined" using bitwise operations. In the main() function, permissions are assigned as Read | Write, which outputs as Read, Write. It queries if Write is present using HasFlag. After that, execute is added, and eventually, read is excluded using bitwise AND and NOT. Lastly, it queries if there are no permissions left and prints accordingly.

## Conclusion

In conclusion, C# Enums provide a type-safe and beautiful way of representing a fixed number of named constants. They increase readability, remove errors caused by hardcoded values, and fit very well with control statements such as switch. With the help of underlying types, attribute application such as ordinary [Flags], and extension methods, enums can be further enriched to be more flexible and powerful.