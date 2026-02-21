Java arrays are objects that store multiple elements of the same data type in a single, contiguous memory block. In this chapter, we will learn about Java arrays, their types, features, and how to use them in programs.

## What is an Array?

An array is a collection of elements of the same type stored in a single, contiguous block of memory. Arrays allow us to group similar data together and access them using an index.

## Array in Java

In Java, an array is an object that stores elements of a similar data type in contiguous memory locations. It is a data structure used to store a fixed number of elements.

Arrays in Java are **index-based**, meaning the first element is at index 0, the second at index 1, and so on.

In Java, an array is considered an object of a dynamically created class. All arrays in Java:

- Implement the Serializable and Cloneable interfaces
- Derive from the Object class

Arrays can store **primitive values** or **objects**, and Java supports both **single-dimensional** and **multi-dimensional** arrays.

Java also supports **anonymous arrays**, which are not available in C/C++. This feature allows us to create and pass arrays without explicitly declaring a variable.

Arrays are of two types, single dimensional and multi-dimensional.

![Java Arrays](https://d2jdgazzki9vjm.cloudfront.net/core/images/java-arrays.png)

## Single-Dimensional Array in Java

A single-dimensional array in Java is a linear collection of elements of the same data type. It can be declared and instantiated using the following syntax.

### Syntax of Declaring an Array

Below is the syntax to declare a single dimensional array in Java:

[](https://www.tpointtech.com/java-arrays#)[](https://www.tpointtech.com/java-arrays#)[](https://www.tpointtech.com/java-arrays#)

1. dataType[] arr; (or)  
2. dataType []arr; (or)  
3. dataType arr[];  

### Syntax of Instantiation of an Array

Below is the syntax to Instantiate a single dimensional array in Java:

[](https://www.tpointtech.com/java-arrays#)[](https://www.tpointtech.com/java-arrays#)[](https://www.tpointtech.com/java-arrays#)

1. arrayRefVar=new datatype[size];  

### Example of Single Dimensional Array

Let's see the simple example of java array, where we are going to declare, instantiate, initialize and traverse an array.

### Source Code

[](https://www.tpointtech.com/java-arrays#)[](https://www.tpointtech.com/java-arrays#)[](https://www.tpointtech.com/java-arrays#)

1. public class Main{    
2.  public static void main(String args[]){    
3.     //declaration and instantiation of an array  
4.     int a[]=new int[5];  
5.     a[0]=10;//initialization    
6.     a[1]=20;    
7.     a[2]=70;    
8.     a[3]=40;    
9.     a[4]=50;    
10.     //traversing array    
11.     for(int i=0;i<a.length;i++){//length is the property of array    
12.         System.out.println(a[i]);    
13.     }  
14.  }  
15. }    

**Output:**

10
20
70
40
50

## Multidimensional Array (Two-Dimensional Array)

A [multidimensional array](https://www.tpointtech.com/multidimensional-arrays-in-java) (two-dimensional array) in Java is an array of arrays, where each element of the main array is itself an array. It is used to store data in a **table-like structure** with rows and columns.

### Syntax of Declaring a Two-Dimensional Array

Below is the syntax to declare a two-dimensional array in Java:

[](https://www.tpointtech.com/java-arrays#)[](https://www.tpointtech.com/java-arrays#)[](https://www.tpointtech.com/java-arrays#)

1. dataType[][] arrayName;  

### Syntax of Instantiation of a Two-Dimensional Array

Below is the syntax to instantiate a two-dimensional array in Java:

[](https://www.tpointtech.com/java-arrays#)[](https://www.tpointtech.com/java-arrays#)[](https://www.tpointtech.com/java-arrays#)

1. arrayName = new dataType[rows][columns];  

or you can combine declaration and instantiation:

[](https://www.tpointtech.com/java-arrays#)[](https://www.tpointtech.com/java-arrays#)[](https://www.tpointtech.com/java-arrays#)

1. dataType[][] arrayName = new dataType[rows][columns];  

### Example of Two-Dimensional Array

Let's see a simple example of a two-dimensional array in Java, where we declare, instantiate, initialize, and traverse the array:

[](https://www.tpointtech.com/java-arrays#)[](https://www.tpointtech.com/java-arrays#)[](https://www.tpointtech.com/java-arrays#)

1. public class Main {  
2.     public static void main(String[] args) {  
3.         // Declare and instantiate a 2D array  
4.         int[][] numbers = new int[2][3];  

5.         // Initialize the array  
6.         numbers[0][0] = 10;  
7.         numbers[0][1] = 20;  
8.         numbers[0][2] = 30;  
9.         numbers[1][0] = 40;  
10.         numbers[1][1] = 50;  
11.         numbers[1][2] = 60;  

12.         // Traverse and print the array  
13.         for (int i = 0; i < numbers.length; i++) {  
14.             for (int j = 0; j < numbers[i].length; j++) {  
15.                 System.out.print(numbers[i][j] + " ");  
16.             }  
17.             System.out.println();  
18.         }  
19.     }  
20. }  

**Output:**

10 20 30
40 50 60

## Accessing Array Elements Using For Each Loop

We can access the array elements using [**for-each loop**](https://www.tpointtech.com/for-each-loop). The Java for-each loop accesses the array elements one by one. It holds an array element in a variable, then executes the body of the loop.

### Syntax

The syntax of the for-each loop is given below:

[](https://www.tpointtech.com/java-arrays#)[](https://www.tpointtech.com/java-arrays#)[](https://www.tpointtech.com/java-arrays#)

1. for(data_type variable:array){  
2. //body of the loop  
3. }  

Let's see the example of printing the elements of the Java array using the for-each loop.

### Example

[](https://www.tpointtech.com/java-arrays#)[](https://www.tpointtech.com/java-arrays#)[](https://www.tpointtech.com/java-arrays#)

1. //Java Program to print the array elements using for-each loop    
2. public class Main{    
3.  public static void main(String args[]){    
4.     //declaration and initialization of an array  
5.     int arr[]={33,3,4,5};    
6.     //traversal of an array using for-each loop    
7.     for(int i:arr)    
8.         System.out.println(i);    
9.  }  
10. }    

**Output:**

33
3
4
5

## Passing Array to a Method

We can pass the Java array to the method so that we can reuse the same logic on any array. When we pass an array to a method in Java, we are essentially passing a reference to the array. It means that the method will have access to the same array data as the calling code, and any modifications made to the array within the method will affect the original array.

Let's see the simple example to get the minimum number of an array using a method.

### Example

[](https://www.tpointtech.com/java-arrays#)[](https://www.tpointtech.com/java-arrays#)[](https://www.tpointtech.com/java-arrays#)

1. //Java Program to demonstrate the way of passing an array to method.    
2. public class Main{    
3. //creating a method which receives an array as a parameter    
4.     static void min(int arr[]){    
5.         int min=arr[0];    
6.         for(int i=1;i<arr.length;i++)    
7.             if(min>arr[i])    
8.                 min=arr[i];    

9.         System.out.println(min);    
10.     }    

11.  public static void main(String args[]){    
12.     int a[]={33,3,4,5};//declaring and initializing an array    
13.     min(a);//passing array to method    
14.  }  
15. }    

**Output:**

3

**Explanation**

This Java program demonstrates the concept of passing an array to a method. The min method takes an integer array arr as a parameter and finds the minimum element in the array using a simple iterative loop. In the main method, an integer array a is declared and initialized with values {33, 3, 4, 5}, and then the min method is called with this array as an argument. The min method iterates through the array to find the minimum element and prints it to the console.

## Anonymous Array

Java's anonymous arrays eliminate the requirement for separate declarations of array variables by enabling developers to build and initialize arrays directly within method calls or other expressions. When working with temporary arrays that are just needed for a single job and don't need a persistent reference within the program, this is quite helpful.

Java supports the feature of an anonymous array, so we do not need to declare the array while passing an array to the method.

### Example

[](https://www.tpointtech.com/java-arrays#)[](https://www.tpointtech.com/java-arrays#)[](https://www.tpointtech.com/java-arrays#)

1. //Java Program to demonstrate the way of passing an anonymous array to method    
2. public class Main{    
3.     //creating a method which receives an array as a parameter    
4.     static void printArray(int arr[]){    
5.         for(int i=0;i<arr.length;i++)    
6.             System.out.println(arr[i]);    
7.     }    
8.  public static void main(String args[]){    
9.     printArray(new int[]{10,22,44,66});//passing anonymous array to method    
10.  }  
11. }    

**Output:**

10
22
44
66

**Explanation**

In this example, the printArray method takes an integer array as a parameter and prints each element of the array. In the main method, an anonymous array {10, 20, 30} is directly passed as an argument to the printArray method. This concise syntax demonstrates the usage of anonymous arrays in Java, allowing for more streamlined code without the need for intermediate variable declarations.

## Returning Array from the Method

In Java, methods are not limited to returning simple data types or objects; they can also return arrays. This feature allows for more flexibility in method design and enables developers to encapsulate complex logic for generating arrays within methods.

### Example

[](https://www.tpointtech.com/java-arrays#)[](https://www.tpointtech.com/java-arrays#)[](https://www.tpointtech.com/java-arrays#)

1. //Java Program to return an array from the method    
2. public class Main{    
3.     //creating method which returns an array    
4.     static int[] get(){    
5.         return new int[]{10,30,50,90,60};    
6.     }    
7.  public static void main(String args[]){    
8.     //calling method which returns an array    
9.     int arr[]=get();    
10.     //printing the values of an array    
11.     for(int i=0;i<arr.length;i++)    
12.         System.out.println(arr[i]);    
13.  }  
14. }  

**Output:**

10
30
50
90
60

**Explanation**

The example demonstrates how to return an array from a method in Java and subsequently use the returned array in the calling code. By encapsulating array creation and initialization logic within the get method, the code becomes more modular and reusable.

## ArrayIndexOutOfBoundsException

In Java, the ArrayIndexOutOfBoundsException is a runtime exception thrown by the Java Virtual Machine (JVM) when attempting to access an invalid index of an array. This exception occurs if the index is negative, equal to the size of the array, or greater than the size of the array while traversing the array.

### Example

The following example demonstrates ArrayIndexOutOfBoundsException in Java array:

[](https://www.tpointtech.com/java-arrays#)[](https://www.tpointtech.com/java-arrays#)[](https://www.tpointtech.com/java-arrays#)

1. //Java Program to demonstrate the case of   
2. //ArrayIndexOutOfBoundsException in a Java Array.  
3. public class TestArrayException{  
4. public static void main(String args[]){  
5. int arr[]={50,60,70,80};  
6. for(int i=0;i<=arr.length;i++){  
7. System.out.println(arr[i]);  
8. }  
9. }}  

**Output:**

Exception in thread "main" java.lang.ArrayIndexOutOfBoundsException: 4
at TestArrayException.main(TestArrayException.java:5)
50
60
70
80

## Jagged Arrays

In Java, a jagged array is an array of arrays where each row of the array can have a different number of columns. This contrasts with a regular two-dimensional array, where each row has the same number of columns.

### Declaring and Initializing a Jagged Array

To declare a jagged array in Java, you first declare the array of arrays, and then you initialize each row separately with its own array of columns.

[](https://www.tpointtech.com/java-arrays#)[](https://www.tpointtech.com/java-arrays#)[](https://www.tpointtech.com/java-arrays#)

1. int arr[][] = new int[3][];    
2. arr[0] = new int[3];    
3. arr[1] = new int[4];    
4. arr[2] = new int[2];  

### Example

The following example demonstrates the use of jagged array in Java:

### Example

[](https://www.tpointtech.com/java-arrays#)[](https://www.tpointtech.com/java-arrays#)[](https://www.tpointtech.com/java-arrays#)

1. //Java Program to illustrate the jagged array    
2. public class Main{    
3.     public static void main(String[] args){    
4.         //declaring a 2D array with odd columns    
5.         int arr[][] = new int[3][];    
6.         arr[0] = new int[3];    
7.         arr[1] = new int[4];    
8.         arr[2] = new int[2];    
9.         //initializing a jagged array    
10.         int count = 0;    
11.         for (int i=0; i<arr.length; i++)    
12.             for(int j=0; j<arr[i].length; j++)    
13.                 arr[i][j] = count++;    

14.         //printing the data of a jagged array     
15.         for (int i=0; i<arr.length; i++){    
16.             for (int j=0; j<arr[i].length; j++){    
17.                 System.out.print(arr[i][j]+" ");    
18.             }    
19.             System.out.println();//new line    
20.         }    
21.     }    
22. }    

**Output:**

0 1 2
3 4 5 6
7 8

**Explanation**

This Java program demonstrates the concept of a jagged array, where an array of arrays is created, with each inner array having a different number of columns. Initially, a 2D array named arr is declared with 3 rows, but with each row having a different number of columns: the first row has 3 columns, the second row has 4 columns, and the third row has 2 columns. The program then initializes the jagged array by filling it with sequential values starting from 0. Finally, it iterates through the array and prints out each element, row by row, separated by a space, with a newline character indicating the end of each row.

## Arrays as Objects

In Java, an array is an object. However, arrays have a special feature in Java where the JVM generates a proxy class for each array object. This proxy class represents the runtime type of the array. To obtain the class name of a Java array, you can use the getClass().getName() method, which is available on all Java objects. This method returns a String representing the fully qualified name of the class of the object, including any package information.

### Example

The following example shows how to get the runtime class name of an array in Java using the getClass().getName() method.

### Example

[](https://www.tpointtech.com/java-arrays#)[](https://www.tpointtech.com/java-arrays#)[](https://www.tpointtech.com/java-arrays#)

1. //Java Program to get the class name of array in Java    
2. public class Main{    
3.  public static void main(String args[]){    
4.     //declaration and initialization of array    
5.     int arr[]={4,4,5};    
6.     //getting the class name of Java array    
7.     Class c=arr.getClass();    
8.     String name=c.getName();    
9.     //printing the class name of Java array     
10.     System.out.println(name);    
11.  }  
12. }    

**Output:**

[I

**Explanation**

This Java program demonstrates how to retrieve the class name of an array in Java using the getClass().getName() method. It initializes an array arr with integer values, obtains the runtime class of the array using getClass(), and retrieves the class name using getName(). The obtained class name, typically represented by a single character followed by square brackets, reflects the dimensionality and type of elements in the array.

## Copying Arrays

Copying an array in Java can be achieved using the arraycopy() method of the System class. This method allows you to copy elements from a source array to a destination array with a specified starting position and length.

### Syntax of arraycopy() method

Below is the syntax of arraycopy() method:

[](https://www.tpointtech.com/java-arrays#)[](https://www.tpointtech.com/java-arrays#)[](https://www.tpointtech.com/java-arrays#)

1. public static void arraycopy(  
2. Object src, int srcPos,Object dest, int destPos, int length  
3. )  

Here, src is the source array, srcPos is the starting position in the source array, dest is the destination array, destPos is the starting position in the destination array, and length is the number of elements to be copied.

### Example

The following example demonstrates how to copy elements from one array to another in Java using the System.arraycopy() method.

### Example

[](https://www.tpointtech.com/java-arrays#)[](https://www.tpointtech.com/java-arrays#)[](https://www.tpointtech.com/java-arrays#)

1. //Java Program to copy a source array into a destination array in Java    
2. public class Main {    
3.     public static void main(String[] args) {    
4.         //declaring a source array    
5.         char[] copyFrom = { 'd', 'e', 'c', 'a', 'f', 'f', 'e',    
6.                 'i', 'n', 'a', 't', 'e', 'd' };    
7.         //declaring a destination array    
8.         char[] copyTo = new char[7];    
9.         //copying array using System.arraycopy() method    
10.         System.arraycopy(copyFrom, 2, copyTo, 0, 7);    
11.         //printing the destination array    
12.         System.out.println(String.valueOf(copyTo));    
13.     }    
14. }    

**Output:**

caffein

**Explanation**

The Java program initializes two character arrays, copyFrom and copyTo, with predefined values. It then utilizes the System.arraycopy() method to copy a portion of the copyFrom array into the copyTo array, starting from index 2 and copying 7 elements. Finally, it prints the contents of the copyTo array, resulting in the output "caffein".

## Cloning an Array

In Java, arrays implement the Cloneable interface, allowing us to create clones of arrays. If we create a clone of a single-dimensional array, it creates a deep copy of the Java array. It means it will copy the actual value. But, if we create the clone of a multidimensional array, it creates a shallow copy of the Java array, which means it copies the references.

This distinction is important because modifying elements in a shallow copied multidimensional array will affect both the original and cloned arrays, while in a deep copied single-dimensional array, modifications will not impact the original.

### Example

The following example demonstrates the closing of an array in Java:

[](https://www.tpointtech.com/java-arrays#)[](https://www.tpointtech.com/java-arrays#)[](https://www.tpointtech.com/java-arrays#)

1. //Java Program to clone the array    
2. class TestarrayClone{    
3. public static void main(String args[]){    
4. int arr[]={33,3,4,5};    
5. System.out.println("Printing original array:");    
6. for(int i:arr)    
7. System.out.println(i);    
8. System.out.println("Printing clone of the array:");    
9. int carr[]=arr.clone();    
10. for(int i:carr)    
11. System.out.println(i);    
12. System.out.println("Are both equal?");    
13. System.out.println(arr==carr);    
14. }  
15. }    

**Output:**

Printing original array:
33
3
4
5
Printing clone of the array:
33
3
4
5
Are both equal?
False

**Explanation**

An integer array called arr is initialised with the numbers {33, 3, 4, 5} in this Java programme, and its elements are printed. Then, it uses the clone() method to duplicate arr, assigns the result to carr, and prints the items of the duplicated array. The last line of the programme compares arr and carr using the == operator; the result evaluates to false, meaning that arr and carr are distinct array objects. The elements in both arrays, though, are the same.

## Addition Two Multidimensional Arrays (Two Matrices)

A fundamental operation in linear algebra and computer science, matrix addition is frequently utilised in a variety of applications, including scientific computing, computer graphics, and image processing. To create a new matrix with the same dimensions as the original, matching elements from each matrix must be added when adding two matrices in Java. This Java program shows how to add matrices effectively by using stacked loops to do a basic example of the process.

### Example

Let's see a simple example that adds two matrices.

[](https://www.tpointtech.com/java-arrays#)[](https://www.tpointtech.com/java-arrays#)[](https://www.tpointtech.com/java-arrays#)

1. //Java Program to demonstrate the addition of two matrices in Java  
2. class ArrayAddition{  
3. public static void main(String args[]){  
4. //creating two matrices  
5. int a[][]={{1,3,4},{3,4,5}};  
6. int b[][]={{1,3,4},{3,4,5}};  

7. //creating another matrix to store the sum of two matrices  
8. int c[][]=new int[2][3];  

9. //adding and printing addition of 2 matrices  
10. for(int i=0;i<2;i++){  
11. for(int j=0;j<3;j++){  
12. c[i][j]=a[i][j]+b[i][j];  
13. System.out.print(c[i][j]+" ");  
14. }  
15. System.out.println();//new line  
16. }  

17. }}  

**Output:**

2 6 8
6 8 10

**Explanation**

This Java program demonstrates matrix addition by adding two predefined matrices, a and b, element-wise and storing the result in matrix c. The matrices a and b are initialized with values, and matrix c is created to store the sum. It iterates through each element of the matrices using nested loops, adding corresponding elements from a and b and storing the result in the corresponding position in c. Finally, it prints the resulting matrix c. The output displays the element-wise addition of the two matrices, with each element in the resulting matrix c being the sum of the corresponding elements in a and b.

## Multiplication Two Multidimensional Arrays (Two Matrices)

Matrix multiplication is a crucial operation in mathematics and computer science, often utilized in various applications such as graphics rendering, optimization algorithms, and scientific computing. In Java, multiplying two matrices involves a systematic process where each element in the resulting matrix is computed by taking the dot product of a row from the first matrix and a column from the second matrix.

![Matrix Multiplication in Java](https://d2jdgazzki9vjm.cloudfront.net/cpp/images/matrix-multiplication-in-cpp1.png)

### Example

The following example demonstrates multiplication of two matrices:

[](https://www.tpointtech.com/java-arrays#)[](https://www.tpointtech.com/java-arrays#)[](https://www.tpointtech.com/java-arrays#)

1. //Java Program to multiply two matrices  
2. public class MatrixMultiplicationExample{  
3. public static void main(String args[]){  
4. //creating two matrices    
5. int a[][]={{1,1,1},{2,2,2},{3,3,3}};    
6. int b[][]={{1,1,1},{2,2,2},{3,3,3}};    

7. //creating another matrix to store the multiplication of two matrices    
8. int c[][]=new int[3][3];  //3 rows and 3 columns  

9. //multiplying and printing multiplication of 2 matrices    
10. for(int i=0;i<3;i++){    
11. for(int j=0;j<3;j++){    
12. c[i][j]=0;      
13. for(int k=0;k<3;k++)      
14. {      
15. c[i][j]+=a[i][k]*b[k][j];      
16. }//end of k loop  
17. System.out.print(c[i][j]+" ");  //printing matrix element  
18. }//end of j loop  
19. System.out.println();//new line    
20. }    
21. }}  

**Output:**

6 6 6
12 12 12
18 18 18

**Explanation**

This Java program computes the multiplication of two 3x3 matrices, 'a' and 'b', storing the result in matrix 'c'. It initializes matrices 'a' and 'b' with predefined values and creates matrix 'c' to store the result. Using nested loops, it iterates through each element of the resulting matrix 'c', calculating the dot product of corresponding row and column elements from matrices 'a' and 'b'. The computed result for each element is accumulated in the corresponding position of 'c'.

## Arrays Programs

The following are the important arrays programs in Java:

- [Java Program to copy all elements of one array into another array](https://www.tpointtech.com/java-program-to-copy-all-elements-of-one-array-into-another-array)
- [Java Program to find the frequency of each element in the array](https://www.tpointtech.com/java-program-to-find-the-frequency-of-each-element-in-the-array)
- [Java Program to left rotate the elements of an array](https://www.tpointtech.com/java-program-to-left-rotate-the-elements-of-an-array)
- [Java Program to print the duplicate elements of an array](https://www.tpointtech.com/java-program-to-print-the-duplicate-elements-of-an-array)
- [Java Program to print the elements of an array](https://www.tpointtech.com/java-program-to-print-the-elements-of-an-array)
- [Java Program to print the elements of an array in reverse order](https://www.tpointtech.com/java-program-to-print-the-elements-of-an-array-in-reverse-order)
- [Java Program to print the elements of an array present on even position](https://www.tpointtech.com/java-program-to-print-the-elements-of-an-array-present-on-even-position)
- [8) Java Program to print the elements of an array present on odd position](https://www.tpointtech.com/java-program-to-print-the-elements-of-an-array-present-on-odd-position)
- [Java Program to print the largest element in an array](https://www.tpointtech.com/java-program-to-print-the-largest-element-in-an-array)
- [Java Program to print the smallest element in an array](https://www.tpointtech.com/java-program-to-print-the-smallest-element-in-an-array)
- [Java Program to print the number of elements present in an array](https://www.tpointtech.com/java-program-to-print-the-number-of-elements-present-in-an-array)
- [Java Program to print the sum of all the items of the array](https://www.tpointtech.com/java-program-to-print-the-sum-of-all-the-items-of-the-array)
- [Java Program to right rotate the elements of an array](https://www.tpointtech.com/java-program-to-right-rotate-the-elements-of-an-array)
- [Java Program to sort the elements of an array in ascending order](https://www.tpointtech.com/java-program-to-sort-the-elements-of-an-array-in-ascending-order)
- [Java Program to sort the elements of an array in descending order](https://www.tpointtech.com/java-program-to-sort-the-elements-of-an-array-in-descending-order)
- [Find 3rd Largest Number in an Array](https://www.tpointtech.com/java-program-to-find-third-largest-number-in-an-array)
- [Find 2nd Largest Number in an Array](https://www.tpointtech.com/java-program-to-find-second-largest-number-in-an-array)
- [Find Largest Number in an Array](https://www.tpointtech.com/java-program-to-find-largest-number-in-an-array)
- [Find 2nd Smallest Number in an Array](https://www.tpointtech.com/java-program-to-find-second-smallest-number-in-an-array)
- [Find Smallest Number in an Array](https://www.tpointtech.com/java-program-to-find-smallest-number-in-an-array)
- [Remove Duplicate Element in an Array](https://www.tpointtech.com/java-program-to-remove-duplicate-element-in-an-array)
- [Add Two Matrices](https://www.tpointtech.com/java-program-to-add-two-matrices)
- [Multiply Two Matrices](https://www.tpointtech.com/java-program-to-multiply-two-matrices)
- [Print Odd and Even Number from an Array](https://www.tpointtech.com/java-program-to-print-odd-and-even-numbers-from-an-array)
- [Transpose matrix](https://www.tpointtech.com/java-program-to-transpose-matrix)
- [Java Program to subtract the two matrices](https://www.tpointtech.com/java-program-to-subtract-the-two-matrices)
- [Java Program to determine whether a given matrix is an identity matrix](https://www.tpointtech.com/java-program-to-determine-whether-a-given-matrix-is-an-identity-matrix)
- [Java Program to determine whether a given matrix is a sparse matrix](https://www.tpointtech.com/java-program-to-determine-whether-a-given-matrix-is-a-sparse-matrix)
- [Java Program to determine whether two matrices are equal](https://www.tpointtech.com/java-program-to-determine-whether-two-matrices-are-equal)
- [Java Program to display the lower triangular matrix](https://www.tpointtech.com/java-program-to-display-the-lower-triangular-matrix)
- [Java Program to display the upper triangular matrix](https://www.tpointtech.com/java-program-to-display-the-upper-triangular-matrix)
- [Java Program to find the frequency of odd & even numbers in the given matrix](https://www.tpointtech.com/java-program-to-find-the-frequency-of-odd-and-even-numbers-in-the-given-matrix)
- [Java Program to find the product of two matrices](https://www.tpointtech.com/java-program-to-find-the-product-of-two-matrices)
- [Java Program to find the sum of each row and each column of a matrix](https://www.tpointtech.com/java-program-to-find-the-sum-of-each-row-and-each-column-of-a-matrix)
- [Java Program to find the transpose of a given matrix](https://www.tpointtech.com/java-program-to-find-the-transpose-of-a-given-matrix)