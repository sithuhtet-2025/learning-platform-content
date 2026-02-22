In Java, **call by value** and **call by reference** explain how values are passed to methods. In this chapter, we will learn how Java passes data to methods and understand the difference between call by value and call by reference using examples.

## Call by Value

In Java, when a method is called by passing a value as an argument, it is referred to as **call by value**. With Java's call-by-value feature, a copy of the variable is passed to the method. As a result, any modifications made within the method only affect that method and do not impact the original variable in the main method.

This is the primary distinction between Java's call-by-reference and call-by-value functions. Passing a variable with basic data types is considered a call by value; therefore, any modifications made to the variable will not be reflected in the caller's scope.

### Important Points to Remember

- Java **always** uses call by value, even for objects.
- When a primitive type (like int, double, float) is passed to a method, a **copy** of the value is made.
- Changes inside the method **do not** affect the original variable

### Example 1: Call by Value with Primitive Data

The following example demonstrates how Java uses call by value when passing primitive data to a method.

[](https://www.tpointtech.com/call-by-value-and-call-by-reference-in-java#)[](https://www.tpointtech.com/call-by-value-and-call-by-reference-in-java#)[](https://www.tpointtech.com/call-by-value-and-call-by-reference-in-java#)

1. class Main {    
2.  int data=50;    
3.  void change(int data)  {    
4.  data=data+100;  //changes will be in the local variable only    
5.  }    
6.  public static void main(String args[]) {    
7.    Main op=new Main ();    
8.    System.out.println("before change "+op.data);    
9.    op.change(500);    
10.    System.out.println("after change "+op.data);    
11.  }    
12. }    

**Output:**

before change 50
after change 50

### Example 2: Call by Value with Object Reference

The following example demonstrates how Java passes object references using call by value that allows changes to the object's instance variables.

[](https://www.tpointtech.com/call-by-value-and-call-by-reference-in-java#)[](https://www.tpointtech.com/call-by-value-and-call-by-reference-in-java#)[](https://www.tpointtech.com/call-by-value-and-call-by-reference-in-java#)

1. class Main {    
2.  int data=50;    
3.  void change(Main op) {    
4.  op.data=op.data+100; //changes will be in the instance variable    
5.  }    
6.  public static void main(String args[]) {    
7.    Main op=new Main();    
8.    System.out.println("before change "+op.data);    
9.    op.change(op); //passing object    
10.    System.out.println("after change "+op.data);    
11.  }    
12. }    

**Output:**

before change 50
after change 150

## Call by Reference (Object Reference)

In Java, **Call by Reference** means passing a reference (memory address) of the object by value to a method. Even though Java strictly uses call by value, it duplicates the reference before passing it as a value to the method when we send the reference of an object. The most important difference between call by value and call by reference in Java is that the copied reference also points to the same address, ensuring that all modifications are reflected in the main method.

### Important Points to Remember

- Java **does not** support true call by reference; it passes the reference by value.
- When an object is passed, a **copy of the reference** is made.
- The reference still points to the same object, so modifications **inside the method** affect the original object.

### Example: Modifying Object Inside a Method (Call by Reference)

The following example demonstrates how passing an object as a parameter allows a method to modify the object's actual data.

[](https://www.tpointtech.com/call-by-value-and-call-by-reference-in-java#)[](https://www.tpointtech.com/call-by-value-and-call-by-reference-in-java#)[](https://www.tpointtech.com/call-by-value-and-call-by-reference-in-java#)

1. class Data {  
2.     int value;  
3. }  
4. public class Main {  
5.     public static void main(String[] args) {  
6.         Data obj = new Data();  
7.         obj.value = 10;  
8.         modifyObject(obj);  
9.         System.out.println("After the method call, value = " + obj.value); // Modified to 15  
10.     }  
11. //passing object as parameter  
12.     static void modifyObject(Data d) {  
13.         d.value = d.value + 5; // Changes the actual object  
14.     }  
15. }  

**Output:**

After the method call, value = 15

## Differences Between Call by Value and Call by Reference

The following tables shows the key differences between call by value and call by reference based on different aspects:

|Feature|Call by Value|Call by Reference|
|---|---|---|
|**Definition**|A copy of the actual value is passed to the method.|A copy of the reference (address) is passed to the method.|
|**Java Support**|Java uses call by value for both primitive types and objects.|Java does not support true call by reference; instead, it passes the reference by value.|
|**Effect on Original Data**|Changes made to the value inside the method do not affect the original variable.|Changes to the object's state within the method impact the original object (but not the reference itself).|
|**Applicable to**|It is applicable to primitive types (like int, double, float, etc.) only.|It is applicable to objects ( instances of classes) only.|
|**Objects**|A copy of the reference to the object is passed. Changes to the object's attributes affect the original object.|Not applicable, as Java does not support true call-by-reference.|
|**Example with Primitives**|If an int is passed, modifying it inside the method does not impact the original int.|Not applicable.|
|**Example with Objects**|If an object is passed, modifying its fields will affect the original object, but reassigning the reference will not.|Not applicable.|
|**Memory Consumption**|It requires more memory because a copy of the variable is created.|The reference points to the same memory location as the original object, so no more memory is needed.|
|**True call by Reference?**|Yes|No|