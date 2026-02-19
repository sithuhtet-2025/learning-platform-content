
In the C# programming language, the array class is in the System namespace, which offers techniques for array creation, searching, sorting, and manipulating arrays. However, it is not part of the System.Collections namespace, it implements interfaces like IList, ICollection, and IEnumerable, which allows it to be treated as a collection.

![C# Array Class](https://images.tpointtech.com/csharp/images/c-sharp-array-class.png)

### Syntax of Array Class:

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-array-class#)[](https://www.tpointtech.com/c-sharp-array-class#)[](https://www.tpointtech.com/c-sharp-array-class#)

1. Array arrayName = Array.CreateInstance(typeof(datatype), length);   

In this syntax,

- **arrayName:** It represents the name of the array.
- **typeof(datatype):** It represents the [data type](https://www.tpointtech.com/data-type-definition) of array elements.
- **length:** It represents the length of the array elements.

### C# Array Class Example

Let’s take an example to define the array class in C#.

### Example

[](https://www.tpointtech.com/c-sharp-array-class#)[](https://www.tpointtech.com/c-sharp-array-class#)[](https://www.tpointtech.com/c-sharp-array-class#)

1. using System;  
2. namespace CSProgram  
3. {  
4.     class Program  
5.     {  
6.         static void Main(string[] args)  
7.         {  
8.             // declaring an array  
9.             int[] originalarray = new int[6] { 5, 8, 9, 25, 0, 7 };  
10.             // Create an empty array for copying  
11.             int[] copiedArray = new int[6];  
12. // calculate the length of the original array  
13.             Console.WriteLine("The Length of original array: " + originalarray.Length);  
14.             // Apply sorting to the original array  
15.             Array.Sort(originalarray);  
16.             Console.Write("The Sorted original array elements: ");  
17.             // printing sorted array  
18.             DisplayArray(originalarray);  
19.             // searching the element  
20.             Console.WriteLine(" \n The Index position of 25 is " + Array.IndexOf( originalarray, 25));  
21.             // duplicate array to a sorted form  
22.             Array.Copy(originalarray, copiedArray, originalarray.Length);  
23.             Console.Write(" The Copied array elements: ");  
24.             // print the copied array  
25.             DisplayArray(copiedArray);  
26.             // Reverse the sequence of the original array  
27.             Array.Reverse(originalarray);  
28.             Console.Write("\n The Original array in reverse order: ");  
29.             // print the reversed array  
30.             DisplayArray(originalarray);  
31.         }  
32.         // User-defined method to print array elements  
33.         static void DisplayArray( int[] array )  
34.         {  
35.             foreach (int element in array)  
36.             {  
37.                 Console.Write( element + " " );  
38.             }  
39.         }  
40.     }  
41. }   

**Output:**

The Length of the original array: 6
The Sorted original array elements: 0 5 7 8 9 25
The Index position of 25 is 5
The Copied array elements: 0 5 7 8 9 25
The Original array in reverse order: 25 9 8 7 5 0

**Explanation:**

In this example, we create an integer array and assign the values to it. The elements are rearranged in a sorted order using the [sort() function](https://www.tpointtech.com/cpp-algorithm-sort-function), and then it prints the sorted elements. After that, it copies the sorted array into a new array and displays the copied values. Finally, it reverses the original array and prints the reversed elements.

### Important Points of the Array Class in C#:

There are several important points of the array class in C#. Some of them are as follows:

- The length of an array is determined by how many elements it contains.
- The index of the first element of an array always starts with zero by default.
- An array has a default size of 2GB.
- The arrays with the same type use the same class object.

## C# Array Properties

There are several properties of the array class in C#. Some of them are as follows:

|Properties|Description|
|---|---|
|IsFixedSize|It is used to get a value indicating whether the Array has a fixed size or not.|
|IsReadOnly|It is used to check whether Array is read-only or not.|
|IsSynchronized|It is used to check whether access to the Array is synchronized or not.|
|Length|It is used to get the total number of elements in all the dimensions of the Array.|
|LongLength|It is used to get a 64-bit integer that represents the total number of elements in all the dimensions of the Array.|
|Rank|It is used to get the rank (number of dimensions) of the Array.|
|SyncRoot|It is used to get an object that can be used to synchronize access to the Array.|

## C# Array Method

There are several methods of the array class in C#. Some of them are as follows:

|Method|Description|
|---|---|
|AsReadOnly<T>(T[])|It returns a read-only wrapper for the specified array.|
|BinarySearch(Array,Int32,Int32,Object)|It is used to search a range of elements in a one-dimensional sorted array for a value.|
|BinarySearch(Array,Object)|It is used to search an entire one-dimensional sorted array for a specific element.|
|Clear(Array,Int32,Int32)|It is used to set a range of elements in an array to the default value.|
|Clone()|It is used to create a shallow copy of the Array.|
|Copy(Array,Array,Int32)|It is used to copy elements of an array into another array by specifying the starting index.|
|CopyTo(Array,Int32)|It copies all the elements of the current one-dimensional array to the specified one-dimensional array, starting at the specified destination array index.|
|CreateInstance(Type,Int32)|It is used to create a one-dimensional Array of the specified Type and length.|
|Empty<T>()|It is used to return an empty array.|
|Finalize()|It is used to free resources and perform cleanup operations.|
|Find<T>(T[],Predicate<T>)|It is used to search for an element that matches the conditions defined by the specified predicate.|
|IndexOf(Array,Object)|It is used to search for the specified object and returns the index of its first occurrence in a one-dimensional array.|
|Initialize()|It is used to initialize every element of the value-type Array by calling the default constructor of the value type.|
|Reverse(Array)|It is used to reverse the sequence of the elements in the entire one-dimensional Array.|
|Sort(Array)|It is used to sort the elements in an entire one-dimensional Array.|
|ToString()|It is used to return a string that represents the current object.|

### Illustration of the Array Length property

Let’s take an illustrate example to determine the size of an array using the Length property in the [C# programming](https://www.tpointtech.com/c-sharp-tutorial) language.

### Example

[](https://www.tpointtech.com/c-sharp-array-class#)[](https://www.tpointtech.com/c-sharp-array-class#)[](https://www.tpointtech.com/c-sharp-array-class#)

1. using System;  
2. class Program  
3. {  
4.     static void Main()  
5.     {  
6.         int[] num_bers = { 100, 200, 300, 400, 500 };  
7.         Console.WriteLine("The length of an array is: " + num_bers.Length);  
8.     }  
9. }  

**Output:**

The length of the array is: 5

**Explanation:**

In this example, first, we create an integer array and assign the values. After that, we use the Length property to calculate the size of an array. Finally, we use the Console.WriteLine() function to print the output.

### Example: Using the rank property to determine the array dimensions

Let’s take an illustrate example to calculate the array dimensions using the rank property.

### Example

[](https://www.tpointtech.com/c-sharp-array-class#)[](https://www.tpointtech.com/c-sharp-array-class#)[](https://www.tpointtech.com/c-sharp-array-class#)

1. using System;         
2. class Program  
3. {         
4.     static void Main()  
5.     {  
6.         // declaration of 1-D array  
7.         int[] num_ber = { 10, 20, 30, 40, 50 };  
8.         // Using Rank property to get the number of dimensions  
9.         Console.WriteLine("The number of dimensions: " + num_ber.Rank);  
10.         // displaying each element  
11.         Console.WriteLine("The elements of the array:");  
12.         for (int i = 0; i < num_ber.Length; i++)  
13.         {  
14.             Console.Write(num_ber[i] + " ");  
15.         }  
16.     }  
17. }   

**Output:**

The number of dimensions: 1
Elements of the array:
10 20 30 40 50

**Explanation:**

In this example, first, we create a [one-dimensional array](https://www.tpointtech.com/one-dimensional-array-in-java) in C#, and then use the rank property to calculate the dimensions of the array. After that, we use the for loop to iterate over the elements of the array. Finally, we are using the Console.WriteLine() function to print the output.

## Conclusion

In the C# programming language, the array class is in the System namespace, which offers techniques for array creation, searching, sorting, and manipulating arrays. It is the key factor for any programmer to create a software application. It has several properties and methods to perform a particular task.