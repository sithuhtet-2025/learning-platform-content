The **Java Math class** is a fundamental part of the Java language's standard library, offering a wide range of mathematical functions. It provides static methods for performing basic arithmetic operations like min(), max(), random(), round() etc. Additionally, it offers methods for more complex operations such as calculating logarithms and trigonometric functions.

Java Math class provides several methods to work on math calculations like min(), max(), avg(), sin(), cos(), tan(), round(), ceil(), floor(), abs() etc.

Unlike some of the StrictMath class numeric methods, all implementations of the equivalent function of Math class can't define to return the bit-for-bit same results. This relaxation permits implementation with better-performance where strict reproducibility is not required.

## Importing Java Math Class

Math class is part of the **java.lang package**, which is imported automatically, so you can use its methods without explicitly importing it.

### Syntax to use a Math method

The syntax to se a Math class's method is as follows:

[](https://www.tpointtech.com/java-math#)[](https://www.tpointtech.com/java-math#)[](https://www.tpointtech.com/java-math#)

1. Math.methodName(arguments);  

### Example Syntax

The following statements demonstrates how you can use the sqrt() and pow() methods of math class:

[](https://www.tpointtech.com/java-math#)[](https://www.tpointtech.com/java-math#)[](https://www.tpointtech.com/java-math#)

1. // Calculate square root of a number  
2. double result = Math.sqrt(25);  

3. // Calculate power of a number  
4. double power = Math.pow(5, 3);  

## Java Math Class Methods

One of the key features of the Math class is its support for working with floating-point numbers. These methods can handle a variety of mathematical tasks involving decimals, fractions, and very large or very small numbers. For example, the Math.round() method can round a floating-point number to the nearest integer, while Math.random() can generate a random number between 0.0 and 1.0.

The Math class also provides methods for working with angles and trigonometric functions. It includes methods for calculating sine, cosine, and tangent, as well as their inverse functions. These functions are useful for tasks like calculating distances and angles in geometry, or for simulating natural phenomena in physics and engineering.

### Basic Math Methods

The following table shows different basic math methods in Java.

|Method|Description|
|---|---|
|[Math.abs()](https://www.tpointtech.com/java-math-abs-method)|It will return the Absolute value of the given value.|
|[Math.max()](https://www.tpointtech.com/java-math-max-method)|It returns the Largest of two values.|
|[Math.min()](https://www.tpointtech.com/java-math-min-method)|It is used to return the Smallest of two values.|
|[Math.round()](https://www.tpointtech.com/java-math-round-method)|It is used to round of the decimal numbers to the nearest value.|
|[Math.sqrt()](https://www.tpointtech.com/java-math-sqrt-method)|It is used to return the square root of a number.|
|[Math.cbrt()](https://www.tpointtech.com/java-math-cbrt-method)|It is used to return the cube root of a number.|
|[Math.pow()](https://www.tpointtech.com/java-math-pow-method)|It returns the value of first argument raised to the power to second argument.|
|[Math.signum()](https://www.tpointtech.com/java-math-signum-method)|It is used to find the sign of a given value.|
|[Math.ceil()](https://www.tpointtech.com/java-math-ceil-method)|It is used to find the smallest integer value that is greater than or equal to the argument or mathematical integer.|
|[Math.copySign()](https://www.tpointtech.com/java-math-copysign-method)|It is used to find the Absolute value of first argument along with sign specified in second argument.|
|[Math.nextAfter()](https://www.tpointtech.com/java-math-nextafter-method)|It is used to return the floating-point number adjacent to the first argument in the direction of the second argument.|
|[Math.nextUp()](https://www.tpointtech.com/java-math-nextup-method)|It returns the floating-point value adjacent to d in the direction of positive infinity.|
|[Math.nextDown()](https://www.tpointtech.com/java-math-nextdown-method)|It returns the floating-point value adjacent to d in the direction of negative infinity.|
|[Math.floor()](https://www.tpointtech.com/java-math-floor-method)|It is used to find the largest integer value which is less than or equal to the argument and is equal to the mathematical integer of a double value.|
|[Math.floorDiv()](https://www.tpointtech.com/java-math-floordiv-method)|It is used to find the largest integer value that is less than or equal to the algebraic quotient.|
|[Math.random()](https://www.tpointtech.com/java-math-random-method)|It returns a double value with a positive sign, greater than or equal to 0.0 and less than 1.0.|
|[Math.rint()](https://www.tpointtech.com/java-math-rint-method)|It returns the double value that is closest to the given argument and equal to mathematical integer.|
|[Math.hypot()](https://www.tpointtech.com/java-math-hypot-method)|It returns sqrt(x2 +y2) without intermediate overflow or underflow.|
|[Math.ulp()](https://www.tpointtech.com/java-math-ulp-method)|It returns the size of an ulp of the argument.|
|[Math.getExponent()](https://www.tpointtech.com/java-math-getexponent-method)|It is used to return the unbiased exponent used in the representation of a value.|
|[Math.IEEEremainder()](https://www.tpointtech.com/java-math-ieeeremainder-method)|It is used to calculate the remainder operation on two arguments as prescribed by the IEEE 754 standard and returns value.|
|[Math.addExact()](https://www.tpointtech.com/java-math-addexact-method)|It is used to return the sum of its arguments, throwing an exception if the result overflows an int or long.|
|[Math.subtractExact()](https://www.tpointtech.com/java-math-subtractexact-method)|It returns the difference of the arguments, throwing an exception if the result overflows an int.|
|[Math.multiplyExact()](https://www.tpointtech.com/java-math-multiplyexact-method)|It is used to return the product of the arguments, throwing an exception if the result overflows an int or long.|
|[Math.incrementExact()](https://www.tpointtech.com/java-math-incrementexact-method)|It returns the argument incremented by one, throwing an exception if the result overflows an int.|
|[Math.decrementExact()](https://www.tpointtech.com/java-math-decrementexact-method)|It is used to return the argument decremented by one, throwing an exception if the result overflows an int or long.|
|[Math.negateExact()](https://www.tpointtech.com/java-math-negateexact-method)|It is used to return the negation of the argument, throwing an exception if the result overflows an int or long.|
|[Math.toIntExact()](https://www.tpointtech.com/java-math-tointexact-method)|It returns the value of the long argument, throwing an exception if the value overflows an int.|

### Logarithmic Math Methods

The following table shows different Logarithmic math methods in Java.

|Method|Description|
|---|---|
|[Math.log()](https://www.tpointtech.com/java-math-log-method)|It returns the natural logarithm of a double value.|
|[Math.log10()](https://www.tpointtech.com/java-math-log10-method)|It is used to return the base 10 logarithm of a double value.|
|[Math.log1p()](https://www.tpointtech.com/java-math-log1p-method)|It returns the natural logarithm of the sum of the argument and 1.|
|[Math.exp()](https://www.tpointtech.com/java-math-exp-method)|It returns E raised to the power of a double value, where E is Euler's number and it is approximately equal to 2.71828.|
|[Math.expm1()](https://www.tpointtech.com/java-math-expm1-method)|It is used to calculate the power of E and subtract one from it.|

### Trigonometric Math Methods

The following table shows different Trigonometric math methods in Java.

|Method|Description|
|---|---|
|[Math.sin()](https://www.tpointtech.com/java-math-sin-method)|It is used to return the trigonometric Sine value of a Given double value.|
|[Math.cos()](https://www.tpointtech.com/java-math-cos-method)|It is used to return the trigonometric Cosine value of a Given double value.|
|[Math.tan()](https://www.tpointtech.com/java-math-tan-method)|It is used to return the trigonometric Tangent value of a Given double value.|
|[Math.asin()](https://www.tpointtech.com/java-math-asin-method)|It is used to return the trigonometric Arc Sine value of a Given double value|
|[Math.acos()](https://www.tpointtech.com/java-math-acos-method)|It is used to return the trigonometric Arc Cosine value of a Given double value.|
|[Math.atan()](https://www.tpointtech.com/java-math-atan-method)|It is used to return the trigonometric Arc Tangent value of a Given double value.|

### Hyperbolic Math Methods

The following table shows different hyperbolic math methods in Java.

|Method|Description|
|---|---|
|[Math.sinh()](https://www.tpointtech.com/java-math-sinh-method)|It is used to return the trigonometric Hyperbolic Cosine value of a Given double value.|
|[Math.cosh()](https://www.tpointtech.com/java-math-cosh-method)|It is used to return the trigonometric Hyperbolic Sine value of a Given double value.|
|[Math.tanh()](https://www.tpointtech.com/java-math-tanh-method)|It is used to return the trigonometric Hyperbolic Tangent value of a Given double value.|

### Angular Math Methods

The following table shows different angular math methods in Java.

|Method|Description|
|---|---|
|[Math.toDegrees](https://www.tpointtech.com/java-math-todegrees-method)|It is used to convert the specified Radians angle to equivalent angle measured in Degrees.|
|[Math.toRadians](https://www.tpointtech.com/java-math-toradians-method)|It is used to convert the specified Degrees angle to equivalent angle measured in Radians.|

## Examples of Math Class Methods

Some useful methods of the Java Math class with practical examples.

### Example 1: Basic Math Operations

The following example demonstrates basic mathematical operations such as maximum, square root, power, and logarithmic calculations using the Math class.

[](https://www.tpointtech.com/java-math#)[](https://www.tpointtech.com/java-math#)[](https://www.tpointtech.com/java-math#)

1. public class JavaMathExample1    
2. {    
3.     public static void main(String[] args)     
4.     {    
5.         double x = 28;    
6.         double y = 4;    

7.         // return the maximum of two numbers  
8.         System.out.println("Maximum number of x and y is: " +Math.max(x, y));   

9.         // return the square root of y   
10.         System.out.println("Square root of y is: " + Math.sqrt(y));   

11.         //returns 28 power of 4 i.e. 28*28*28*28    
12.         System.out.println("Power of x and y is: " + Math.pow(x, y));      

13.         // return the logarithm of given value       
14.         System.out.println("Logarithm of x is: " + Math.log(x));   
15.         System.out.println("Logarithm of y is: " + Math.log(y));  

16.         // return the logarithm of given value when base is 10      
17.         System.out.println("log10 of x is: " + Math.log10(x));   
18.         System.out.println("log10 of y is: " + Math.log10(y));    

19.         // return the log of x + 1  
20.         System.out.println("log1p of x is: " +Math.log1p(x));    

21.         // return a power of 2    
22.         System.out.println("exp of a is: " +Math.exp(x));    

23.         // return (a power of 2)-1  
24.         System.out.println("expm1 of a is: " +Math.expm1(x));  
25.     }    
26. }    

**Output:**

Maximum number of x and y is: 28.0
Square root of y is: 2.0
Power of x and y is: 614656.0
Logarithm of x is: 3.332204510175204
Logarithm of y is: 1.3862943611198906
log10 of x is: 1.4471580313422192
log10 of y is: 0.6020599913279624
log1p of x is: 3.367295829986474
exp of a is: 1.446257064291475E12
expm1 of a is: 1.446257064290475E12

### Example 2: Trigonometric Methods

The following example demonstrates how to use trigonometric and hyperbolic functions in Java using the Math class.

[](https://www.tpointtech.com/java-math#)[](https://www.tpointtech.com/java-math#)[](https://www.tpointtech.com/java-math#)

1. public class JavaMathExample2    
2. {    
3.     public static void main(String[] args)     
4.     {    
5.         double a = 30;    

6.         // converting values to radian    
7.         double b = Math.toRadians(a);   

8.         // return the trigonometric sine of a      
9.         System.out.println("Sine value of a is: " +Math.sin(a));    

10.         // return the trigonometric cosine value of a  
11.         System.out.println("Cosine value of a is: " +Math.cos(a));  

12.         // return the trigonometric tangent value of a  
13.         System.out.println("Tangent value of a is: " +Math.tan(a));  

14.         // return the trigonometric arc sine of a      
15.         System.out.println("Sine value of a is: " +Math.asin(a));    

16.         // return the trigonometric arc cosine value of a  
17.         System.out.println("Cosine value of a is: " +Math.acos(a));  

18.         // return the trigonometric arc tangent value of a  
19.         System.out.println("Tangent value of a is: " +Math.atan(a));  

20.         // return the hyperbolic sine of a      
21.         System.out.println("Sine value of a is: " +Math.sinh(a));    

22.         // return the hyperbolic cosine value of a  
23.         System.out.println("Cosine value of a is: " +Math.cosh(a));  

24.         // return the hyperbolic tangent value of a  
25.         System.out.println("Tangent value of a is: " +Math.tanh(a));  
26.     }    
27. }    

**Output:**

Sine value of a is: -0.9880316240928618
Cosine value of a is: 0.15425144988758405
Tangent value of a is: -6.405331196646276
Sine value of a is: NaN
Cosine value of a is: NaN
Tangent value of a is: 1.5374753309166493
Sine value of a is: 5.343237290762231E12
Cosine value of a is: 5.343237290762231E12
Tangent value of a is: 1.0

### Example 3: Complete Math Class Reference

The following example demonstrates multiple functionalities of the Math class, including power, logarithms, trigonometric functions, rounding, random numbers, hypotenuse calculation, and constants.

[](https://www.tpointtech.com/java-math#)[](https://www.tpointtech.com/java-math#)[](https://www.tpointtech.com/java-math#)

1. // Java program for demonstrating the features and functionalities of Java Math class with methods.  
2. public class MathDemo {  
3.     public static void main(String[] args) {  
4.         double x = 28;  
5.         double y = 4;  
6.         // Basic arithmetic operations  
7.         System.out.println("Addition: " + (x + y));  
8.         System.out.println("Subtraction: " + (x - y));  
9.         System.out.println("Multiplication: " + (x * y));  
10.         System.out.println("Division: " + (x / y));  
11.         // Square root  
12.         System.out.println("Square root of " + x + ": " + Math.sqrt(x));  
13.         // Cube root  
14.         System.out.println("Cube root of " + x + ": " + Math.cbrt(x));  
15.         // Power  
16.         System.out.println("Power of " + x + " to " + y + ": " + Math.pow(x, y));  
17.         // Trigonometric functions  
18.         double angle = 45.0;  
19.         double radian = Math.toRadians(angle);  
20.         System.out.println("Sine of " + angle + " degrees: " + Math.sin(radian));  
21.         System.out.println("Cosine of " + angle + " degrees: " + Math.cos(radian));  
22.         System.out.println("Tangent of " + angle + " degrees: " + Math.tan(radian));  
23.         // Rounding  
24.         double value = -123.456;  
25.         System.out.println("Absolute value of " + value + ": " + Math.abs(value));  
26.         System.out.println("Ceil value of " + value + ": " + Math.ceil(value));  
27.         System.out.println("Floor value of " + value + ": " + Math.floor(value));  
28.         System.out.println("Round value of " + value + ": " + Math.round(value));  
29.         // Random numbers  
30.         System.out.println("Random number between 0.0 and 1.0: " + Math.random());  
31.         System.out.println("Random number between 0 and 100: " + (int) (Math.random() * 100));  
32.         // Maximum and minimum  
33.         double[] numbers = {10.5, 20.7, 5.2, 30.9};  
34.         System.out.println("Maximum value: " + Math.max(numbers[0], Math.max(numbers[1], Math.max(numbers[2], numbers[3]))));  
35.         System.out.println("Minimum value: " + Math.min(numbers[0], Math.min(numbers[1], Math.min(numbers[2], numbers[3]))));  
36.         // Exponential and logarithmic functions  
37.         System.out.println("e^" + x + ": " + Math.exp(x));  
38.         System.out.println("Logarithm base 10 of " + x + ": " + Math.log10(x));  
39.         System.out.println("Logarithm base e of " + x + ": " + Math.log(x));  
40.         // Hypotenuse  
41.         double side1 = 3.0;  
42.         double side2 = 4.0;  
43.         System.out.println("Hypotenuse of a right triangle with sides " + side1 + " and " + side2 + ": " + Math.hypot(side1, side2));  
44.         // Trigonometric functions (inverse)  
45.         double sinValue = 0.5;  
46.         System.out.println("Arcsine of " + sinValue + ": " + Math.toDegrees(Math.asin(sinValue)));  
47.         System.out.println("Arccosine of " + sinValue + ": " + Math.toDegrees(Math.acos(sinValue)));  
48.         System.out.println("Arctangent of " + sinValue + ": " + Math.toDegrees(Math.atan(sinValue)));  
49.         // Constants  
50.         System.out.println("Value of PI: " + Math.PI);  
51.         System.out.println("Value of E: " + Math.E);  
52.     }  
53. }  

**Output:**

Addition: 32.0
Subtraction: 24.0
Multiplication: 112.0
Division: 7.0
Square root of 28.0: 5.291502622129181
Cube root of 28.0: 3.0365889718756627
Power of 28.0 to 4.0: 614656.0
Sine of 45.0 degrees: 0.7071067811865475
Cosine of 45.0 degrees: 0.7071067811865476
Tangent of 45.0 degrees: 0.9999999999999999
Absolute value of -123.456: 123.456
Ceil value of -123.456: -123.0
Floor value of -123.456: -124.0
Round value of -123.456: -123
Random number between 0.0 and 1.0: 0.40493356810101455
Random number between 0 and 100: 61
Maximum value: 30.9
Minimum value: 5.2
e^28.0: 1.446257064291475E12
Logarithm base 10 of 28.0: 1.4471580313422192
Logarithm base e of 28.0: 3.332204510175204
Hypotenuse of a right triangle with sides 3.0 and 4.0: 5.0
Arcsine of 0.5: 30.000000000000004
Arccosine of 0.5: 60.00000000000001
Arctangent of 0.5: 26.56505117707799
Value of PI: 3.141592653589793
Value of E: 2.718281828459045