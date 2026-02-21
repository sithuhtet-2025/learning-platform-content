The **Java for-each loop** is a simple and easy way to go through elements of an array or collection one by one.

## Java for-each Loop

The Java for-each loop or enhanced for loop is introduced since J2SE 5.0. It provides an alternative approach to traverse the array or collection in Java. It is mainly used to traverse the array or collection elements.

## Advantages of Java for-each loop

The main advantage of the for-each loop is that it eliminates the possibility of common programming bugs, such as index-out-of-bound errors. It makes the code cleaner, shorter, and more readable. The loop is called a for-each loop because it processes each element one by one automatically

## Limitations of for-each Loop

The drawback of the enhanced for loop is that it cannot traverse the elements in reverse order. Here, you do not have the option to skip any element because it does not work on an index basis. Moreover, you cannot traverse the odd or even elements only.

## When to Use for-each Loop

However, it is recommended to use the Java for-each loop for traversing the elements of array and collection because it makes the code readable.

## Syntax of for-each Loop

The syntax of Java for-each loop consists of data_type with the variable followed by a colon (:), then array or collection.

[](https://www.tpointtech.com/for-each-loop-in-java#)[](https://www.tpointtech.com/for-each-loop-in-java#)[](https://www.tpointtech.com/for-each-loop-in-java#)

1. for(data_type variable : array | collection){  
2. //body of for-each loop  
3. }  

## How for-each Loop Works?

The Java for-each loop traverses the array or collection until the last element. For each element, it stores the element in the variable and executes the body of the for-each loop.

The following are the steps:

1. The loop starts with the first element of the array or collection.
2. The current element is stored in the loop variable.
3. The statements inside the loop body are executed.
4. The process repeats for each element until the last element is reached.

## for each Loop Examples

Practice these examples to understand the concept of for each loop in Java.

### Example 1: Traversing Array Elements

In this example, the Java for-each loop goes through each element of the arr array one by one. During every iteration, the current value of the array is stored in the variable i, and System.out.println(i) prints that value. The loop continues automatically until all elements of the array are printed.

### Example

[](https://www.tpointtech.com/for-each-loop-in-java#)[](https://www.tpointtech.com/for-each-loop-in-java#)[](https://www.tpointtech.com/for-each-loop-in-java#)

1. //An example of Java for-each loop  
2. class Main{  
3.   public static void main(String args[]){  
4.    //declaring an array  
5.    int arr[]={12,13,14,44};  
6.    //traversing the array with for-each loop  
7.    for(int i:arr){  
8.      System.out.println(i);  
9.    }  
10.  }   
11. }  

**Output:**

12
13
14
44

### Example 2: Calculating Sum of Array Elements

In this example, the Java for-each loop iterates through each element of the arr array. During every iteration, the current element is stored in the variable i and added to the total variable. After the loop finishes, the program prints the sum of all array elements.

### Example

[](https://www.tpointtech.com/for-each-loop-in-java#)[](https://www.tpointtech.com/for-each-loop-in-java#)[](https://www.tpointtech.com/for-each-loop-in-java#)

1. class Main{  
2.   public static void main(String args[]){  
3.    int arr[]={12,13,14,44};  
4.    int total=0;  
5.    for(int i:arr){  
6.      total=total+i;  
7.    }  
8.   System.out.println("Total: "+total);  
9.  }   
10. }  

**Output:**

Total: 83

### Example 3: Traversing Collection Elements

This example demonstrates how the Java for-each loop is used to traverse an ArrayList and print each element one by one.

### Example

[](https://www.tpointtech.com/for-each-loop-in-java#)[](https://www.tpointtech.com/for-each-loop-in-java#)[](https://www.tpointtech.com/for-each-loop-in-java#)

1. import java.util.*;  
2. class Main{  
3.   public static void main(String args[]){  
4.    //Creating a list of elements  
5.    ArrayList<String> list=new ArrayList<String>();  
6.    list.add("vimal");  
7.    list.add("sonoo");  
8.    list.add("ratan");  
9.    //traversing the list of elements using for-each loop  
10.    for(String s:list){  
11.      System.out.println(s);  
12.    }  

13.  }   
14. }  

**Output:**

vimal
sonoo
ratan