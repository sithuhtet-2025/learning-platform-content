Method overriding and overloading are the two major concepts of object-oriented programming. Both are the ways of implementing polymorphism.

## Java Method Overloading

[Method overloading](https://www.tpointtech.com/method-overloading-in-java) is a feature in Java that allows a class to have more than one method with the same name, provided their parameter lists are different. Itenables methods to perform similar but distinct tasks.

Method overloading is a form of compile-time polymorphism, which means that the compiler determines which method to call based on the method signature (name and parameter list).

### Example: Method Overloading

The following example demonstrates method overloading.

[](https://www.tpointtech.com/method-overloading-vs-method-overriding-in-java#)[](https://www.tpointtech.com/method-overloading-vs-method-overriding-in-java#)[](https://www.tpointtech.com/method-overloading-vs-method-overriding-in-java#)

1. public class Main{     
2.     // Method to add two integers    
3.     public int add(int a, int b) { // Method named 'add' that takes two integer parameters    
4.         return a + b; // Returns the sum of the two integers    
5.     }    
6.     // Method to add three integers    
7.     public int add(int a, int b, int c) { // Overloaded method named 'add' that takes three integer parameters    
8.         return a + b + c; // Returns the sum of the three integers    
9.     }    
10.     // Method to add two double values    
11.     public double add(double a, double b) { // Overloaded method named 'add' that takes two double parameters    
12.         return a + b; // Returns the sum of the two double values    
13.     }    
14.     // Method to add three double values    
15.     public double add(double a, double b, double c) { // Overloaded method named 'add' that takes three double parameters    
16.         return a + b + c; // Returns the sum of the three double values    
17.     }    
18.     // Method to add an array of integers    
19.     public int add(int[] numbers) { // Overloaded method named 'add' that takes an array of integers as parameter    
20.         int sum = 0; // Initializes sum to 0    
21.         for (int number : numbers) { // Iterates through each element in the array    
22.             sum += number; // Adds each element to the sum    
23.         }    
24.         return sum; // Returns the total sum of the elements in the array    
25.     }    
26.     // Main method to test the overloaded methods    
27.     public static void main(String[] args) { // Main method, the entry point of the program    
28.         Main calc = new Main(); // Creates an instance of the Main class    
29.         // Test add methods    
30.         System.out.println("Sum of 2 and 3 (int): " + calc.add(2, 3)); // Calls the add method with two integers and prints the result    
31.         System.out.println("Sum of 1, 2, and 3 (int): " + calc.add(1, 2, 3)); // Calls the add method with three integers and prints the result    
32.         System.out.println("Sum of 2.5 and 3.5 (double): " + calc.add(2.5, 3.5)); // Calls the add method with two doubles and prints the result    
33.         System.out.println("Sum of 1.1, 2.2, and 3.3 (double): " + calc.add(1.1, 2.2, 3.3)); // Calls the add method with three doubles and prints the result    
34.         System.out.println("Sum of array {1, 2, 3, 4, 5}: " + calc.add(new int[]{1, 2, 3, 4, 5})); // Calls the add method with an array of integers and prints the result    
35.     }    
36. }    

**Output:**

Sum of 2 and 3 (int): 5
Sum of 1, 2, and 3 (int): 6
Sum of 2.5 and 3.5 (double): 6.0
Sum of 1.1, 2.2, and 3.3 (double): 6.6
Sum of array {1, 2, 3, 4, 5}: 15

## Java Method Overriding

[Method overriding](https://www.tpointtech.com/method-overriding-in-java) is a fundamental concept in object-oriented programming (OOP) that allows a subclass to provide a specific implementation for a method that is already defined in its superclass. It enables a subclass to inherit the method from the superclass but override it to perform a different task. Method overriding is essential for achieving runtime polymorphism, where the method that gets called is determined by the actual object type at runtime, not the reference type.

### Example: Method Overriding

The following example demonstrates method overriding.

[](https://www.tpointtech.com/method-overloading-vs-method-overriding-in-java#)[](https://www.tpointtech.com/method-overloading-vs-method-overriding-in-java#)[](https://www.tpointtech.com/method-overloading-vs-method-overriding-in-java#)

1. // Superclass Animal    
2. class Animal {    
3.     // Method to be overridden in subclass    
4.     public void makeSound() {    
5.         System.out.println("Animal makes a sound");   
6.     }    
7. }    
8. // Subclass Dog that extends Animal    
9. class Dog extends Animal {    
10.     // Overriding the makeSound() method in the superclass    
11.     @Override    
12.     public void makeSound() {    
13.         System.out.println("Dog barks");   
14.     }    
15. }    
16. public class Main {    
17.     public static void main(String[] args) {    
18.         Animal myAnimal = new Animal();   
19.         Animal myDog = new Dog();   
20.         myAnimal.makeSound();   
21.         myDog.makeSound();     
22.     }    
23. }    

**Output:**

Animal makes a sound
Dog barks

## Method Overloading Vs. Method Overriding

The following table shows the main differences of method overloading and method overriding:

|Characteristic|Method Overloading|Method Overriding|
|---|---|---|
|**Purpose**|It increases the code readability.|It is used to provide the specific implementation of the method that is already provided by its super class.|
|**Class Relationship**|Method overloading is performed _within class_.|Method overriding occurs _in two classes_ that have IS-A (inheritance) relationship.|
|**Parameters**|Number and type of parameter must be different.|Number and type of parameter must be the same.|
|**Polymorphism Type**|It performs compile-time (static) polymorphism.|It performs runtime (dynamic) polymorphism.|
|**Return Type**|In Java, method overloading cannot be performed by changing return type of the method only. Return type can be same or different in method overloading. But you must have to change the parameter.|Return type must be same or covariant.|
|**Binding Type**|It is called static binding or early binding.|It is called dynamic binding or late binding.|
|**Error Detection**|Errors are detected at compile-time.|Errors detected at runtime.|
|**Applicability to Private/Final**|It is applicable to both private and final methods.|It is not applicable to private and final methods.|
|**Static Methods**|Static methods can be overloaded.|Static methods cannot be overridden.|
|**Implementation Scope**|Implemented in a single class.|Implemented in two classes (parent and child).|