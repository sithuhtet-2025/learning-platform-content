In the C# programming language, the SortedList<TKey, TValue> is an array of key/value pairs. It stores values on the basis of a key. The SortedList<TKey, TValue> class contains unique keys and maintains ascending order on the basis of key. With the help of the key, we can easily search or remove elements. It is found in System.Collections.Generic namespace. It is like the SortedDictionary<TKey, TValue> class.

### Syntax

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-sortedlist#)[](https://www.tpointtech.com/c-sharp-sortedlist#)[](https://www.tpointtech.com/c-sharp-sortedlist#)

1. SortedList<TKey, TValue> variable_name = new SortedList<TKey, TValue>();  

Or

[](https://www.tpointtech.com/c-sharp-sortedlist#)[](https://www.tpointtech.com/c-sharp-sortedlist#)[](https://www.tpointtech.com/c-sharp-sortedlist#)

1. SortedList<TKey, TValue> variable_name = new SortedList<TKey, TValue>  
2. {  
3.     { key1, value1 },  
4.     { key2, value2 },  
5.     { key3, value3 }  
6. };  

In this example,

- **TKey:** It is used to represent the type of keys in the sorted list.
- **Tvalue:** It is used to represent the type of value in the sorted list.
- **SortedList<TKey, TValue>:** It is used to represent a generic class that is used to store the unique keys and values in ascending order of the keys.

### C# Simple Example for SortedList

Let us take an example to illustrate the SortedList in C++.

### Example

[](https://www.tpointtech.com/c-sharp-sortedlist#)[](https://www.tpointtech.com/c-sharp-sortedlist#)[](https://www.tpointtech.com/c-sharp-sortedlist#)

1. using System;  
2. using System.Collections.Generic;  

3. class Tpoint  
4. {  
5.     static void Main()  
6.     {  
7.         // Here, we have created a SortedList of string keys and int values  
8.         SortedList<string, int> marks = new SortedList<string, int>  
9.         {  
10.             { "C++", 85 },  
11.             { "Java", 90 },  
12.             { "Python", 95 }  
13.         };  

14.         foreach (KeyValuePair<string, int> kvp in marks)  
15.         {  
16.             Console.WriteLine($"{kvp.Key}: {kvp.Value}");  
17.         }  
18.     }  
19. }  

**Output:**

C++: 85
Java: 90
Python: 95

**Explanation:**

In this example, we have created a SortedList with string keys that represent programming languages and integer values that represent marks. After that, we have utilized the SortedList method that automatically sorts the entries by key in ascending order, and the foreach loop iterates through each key-value pair to display them in sorted order.

## Key Features of the SortedList

There are several key features of the SortedList in C#. Some of the main features are as follows:

There are several features of the SortedList Function in C#. Some of them are as follows:

- In C#, every key in the SortedList should be unique and cannot be null. However, the SortedList values can be duplicates or null.
- It is useful to implement several interfaces, including IDictionary<TKey, TValue>, ICollection<KeyValuePair<TKey, TValue>>, IEnumerable<KeyValuePair<TKey, TValue>>, and read-only methods.
- It is used to store as key-value pairs in order of ascending keys, with an array-based data structure.
- It provides fast retrieval by key or by index, but slower insertions and deletions than some collections, such as SortedDictionary<TKey, TValue>.
- It supports fast memory usage and direct access to the value/index, particularly when the keys are not frequently changing.
- It is used to sort its keys in ascending order by default using the IComparer<TKey> interface. We can also provide a custom comparer to define a different sorting order, such as descending or case-insensitive sorting.

## Common Operations

There are several common operations of SortedList in C#. Some of the main operations in C# are as follows:

- **Insertion**

In the C# programming language, we can insert a new key-value pair into the SortedList. The key must be unique and not null. If it is a duplicate key or null, it raises an exception. Values may be null or repeated if the type is so enabled. If we want to perform an add operation, the collection inserts the pair in the appropriate sorted position by key automatically.

**C# Add Operation using the SortedList**

Let us take an example to illustrate the insertion operation using the SortedList in C#.

### Example

[](https://www.tpointtech.com/c-sharp-sortedlist#)[](https://www.tpointtech.com/c-sharp-sortedlist#)[](https://www.tpointtech.com/c-sharp-sortedlist#)

1. using System;  
2. using System.Collections.Generic;  
3. class Example_Add  
4. {  
5.     static void Main()  
6.     {  
7.         SortedList<string, int> marks = new SortedList<string, int>();  
8.         marks.Add("C++", 90);  
9.         marks.Add("Python", 85);  
10.         Console.WriteLine("Added successfully.");  
11.     }  
12. }  

**Output:**

Added successfully.

**Explanation:**

In this example, we have created a SortedList that contains subject names as keys and their marks as values. It has two entries, C++ with 90 and Python with 85. As the keys are sorted automatically, they are arranged in alphabetical order. Once the items are entered, it simply displays Added successfully to acknowledge the procedure.

- **Remove**

In the C# programming language, we can delete the element with the given key from the SortedList. If the key is not found, nothing happens. This action can make the array underneath rearrange elements to preserve order.

**C# SortedList Example for Remove Operation**

Let us take an example to illustrate the remove operation using the SortedList in C#.

### Example

[](https://www.tpointtech.com/c-sharp-sortedlist#)[](https://www.tpointtech.com/c-sharp-sortedlist#)[](https://www.tpointtech.com/c-sharp-sortedlist#)

1. using System;  
2. using System.Collections.Generic;  
3. class Example_Remove  
4. {  
5.     static void Main()  
6.     {  
7.         SortedList<string, int> marks = new SortedList<string, int> { { "C++", 90 }, { "Java", 85 } };  
8.         marks.Remove("C++");  
9.         Console.WriteLine("C++ removed.");  
10.     }  
11. }  

**Output:**

C++ removed.

**Explanation:**

In this example, we have created a SortedList with two subjects and their marks. After that, it deletes the entry for the key C++ from the list. Next, it prints a message that indicates C++ removed to ensure deletion.

- **ContainsKey**

In C#, this function determines whether the SortedList contains an element with the given key. It returns true value if the key is present; otherwise, it returns false. It is an efficient lookup operation based on sorted keys.

**C# SortedList Example for ContainsKey Operation**

Let us take an example to illustrate the ContainsKey operation using the SortedList in C#.

### Example

[](https://www.tpointtech.com/c-sharp-sortedlist#)[](https://www.tpointtech.com/c-sharp-sortedlist#)[](https://www.tpointtech.com/c-sharp-sortedlist#)

1. using System;  
2. using System.Collections.Generic;  
3. class Example_ContainsKey  
4. {  
5.     static void Main()  
6.     {  
7.         SortedList<int, string> students = new SortedList<int, string>();  
8.         students.Add(101, "Riya");  
9.         students.Add(102, "Aman");  
10.         if (students.ContainsKey(103))  
11.             Console.WriteLine("Student with ID 103 exists.");  
12.         else  
13.             Console.WriteLine("Student with ID 103 not found.");  
14.     }  
15. }  

**Output:**

Student with ID 103 not found.

**Explanation:**

In this example, we have created a SortedList in which student IDs serve as keys and names are stored as values. It inserts two students with IDs 101 and 102. After that, it searches for key 103. Because it doesn't exist, the program prints Student with ID 103 not found.

- **ContainsValue**

This function checks whether the SortedList contains at least one element with the specified value. It is a linear search through the values because the values are not sorted.

**C# SortedList Example for ContainsValue Operation**

Let us take an example to illustrate the ContainsValue operation using the SortedList in C#.

### Example

[](https://www.tpointtech.com/c-sharp-sortedlist#)[](https://www.tpointtech.com/c-sharp-sortedlist#)[](https://www.tpointtech.com/c-sharp-sortedlist#)

1. using System;  
2. using System.Collections.Generic;  
3. class Example_ContainsValue  
4. {  
5.     static void Main()  
6.     {  
7.         SortedList<string, double> products = new SortedList<string, double>  
8.         {  
9.             { "Laptop", 50000 },  
10.             { "Mobile", 20000 },  
11.             { "Tablet", 15000 }  
12.         };  
13.         double price = 20000;  
14.         if (products.ContainsValue(price))  
15.             Console.WriteLine("A product with price " + price + " is available.");  
16.         else  
17.             Console.WriteLine("No product with price " + price + " found.");  
18.     }  
19. }  

**Output:**

A product with price 20000 is available.

**Explanation:**

In this example, we generate a SortedList where product names serve as keys and prices are the corresponding values. It verifies whether any product has a price of 20000 or not. Since Mobile has that price, the program outputs A product with price 20000 is available.

- **Keys**

In the C# programming language, the Keys property gets the collection of all keys in the SortedList, which is sorted in ascending order. The collection is in the order of the sorted keys and is enumerable.

**C# SortedList Example for Keys Operation**

Let us take an example to illustrate the Keys operation using the SortedList in C#.

### Example

[](https://www.tpointtech.com/c-sharp-sortedlist#)[](https://www.tpointtech.com/c-sharp-sortedlist#)[](https://www.tpointtech.com/c-sharp-sortedlist#)

1. using System;  
2. using System.Collections.Generic;  
3. class Example_Keys  
4. {  
5.     static void Main()  
6.     {  
7.         SortedList<string, string> countries = new SortedList<string, string>  
8.         {  
9.             { "US", "United States" },  
10.             { "IN", "India" },  
11.             { "UK", "United Kingdom" },  
12.             { "CA", "Canada" }  
13.         };  
14.         Console.WriteLine("Country codes in sorted order:");  
15.         foreach (string code in countries.Keys)  
16.             Console.WriteLine(code);  
17.     }  
18. }  

**Output:**

Country codes in sorted order:
CA
IN
UK
US

**Explanation:**

In this example, we have created a SortedList of country codes as keys and country names as values, loop over the Keys collection, which is sorted automatically, and display each country code alphabetically.

- **Values**

In the C# programming language, the value is a collection of all values in the SortedList based on the sorted keys. The values may be retrieved by index or enumerated by key.

**C# SortedList Example for Values**

Let us take an example to illustrate the values using the SortedList in C#.

### Example

[](https://www.tpointtech.com/c-sharp-sortedlist#)[](https://www.tpointtech.com/c-sharp-sortedlist#)[](https://www.tpointtech.com/c-sharp-sortedlist#)

1. using System;  
2. using System.Collections.Generic;  
3. class Example_Values  
4. {  
5.     static void Main()  
6.     {  
7.         SortedList<string, string> country = new SortedList<string, string>  
8.         {  
9.             { "US", "United States" },  
10.             { "IN", "India" },  
11.             { "UK", "United Kingdom" },  
12.             { "CA", "Canada" }  
13.         };  
14.         Console.WriteLine("Countries in key-sorted order:");  
15.         foreach (string c in country.Values)  
16.             Console.WriteLine(c);  
17.     }  
18. }  

**Output:**

Countries in key-sorted order:
Canada
India
United Kingdom
United States

**Explanation:**

In this example, we have created a SortedList with country codes as keys and country names as values. The keys are sorted alphabetically automatically. After that, it loops through the Values collection and prints out the country names in the order of the sorted keys: Canada, India, United Kingdom, United States.

- **Item[TKey]**

In C#, the Item[TKey] is an indexer to read or write the value for a given key. If the key does not yet exist during setting, an exception is raised. It allows direct key-based access to values.

**C# SortedList Example for Item[TKey]**

Let us take an example to illustrate the Item[TKey] using the SortedList in C#.

### Example

[](https://www.tpointtech.com/c-sharp-sortedlist#)[](https://www.tpointtech.com/c-sharp-sortedlist#)[](https://www.tpointtech.com/c-sharp-sortedlist#)

1. using System;  
2. using System.Collections.Generic;  
3. class Example_Indexer  
4. {  
5.     static void Main()  
6.     {  
7.         SortedList<string, int> marks = new SortedList<string, int>  
8.         {  
9.             { "Math", 90 },  
10.             { "Science", 85 },  
11.             { "English", 80 }  
12.         };  
13.         Console.WriteLine("Marks in Science: " + marks["Science"]);  
14.         marks["Science"] = 95;  
15.         Console.WriteLine("Updated Marks in Science: " + marks["Science"]);  
16.     }  
17. }  

**Output:**

Marks in Science: 85
Updated Marks in Science: 95

**Explanation:**

In this example, we have created a SortedList where subjects are used as keys and marks as values. It initially prints the marks for Science using the indexer, and then it changes the value to 95 and prints the new marks.

- **Count**

In the C# programming language, the Count property is used to return the number of key-value pairs currently stored in a SortedList<TKey, TValue>. It reflects the actual elements in the collection, independent of the internal Capacity allocated for storage.

**C# SortedList Example for Count**

Let us take an example to illustrate the Count using the SortedList in C#.

### Example

[](https://www.tpointtech.com/c-sharp-sortedlist#)[](https://www.tpointtech.com/c-sharp-sortedlist#)[](https://www.tpointtech.com/c-sharp-sortedlist#)

1. using System;  
2. using System.Collections.Generic;  
3. class Example_Count  
4. {  
5.     static void Main()  
6.     {  
7.         SortedList<string, int> library = new SortedList<string, int>  
8.         {  
9.             { "Harry Potter", 5 },  
10.             { "The Hobbit", 3 },  
11.             { "1984", 4 }  
12.         };  
13.         Console.WriteLine("Total books in library: " + library.Count);  
14.     }  
15. }  

**Output:**

Total books in library: 3

**Explanation:**

In this example, we have created a SortedList with book titles as keys and their counts as values. After that, it displays the number of entries in the list using Count, which is 3 here.

## Difference between C# SortedList<TKey, TValue> and SortedDictionary<TKey, TValue>

In the C# programming language, the SortedList<TKey, TValue> class uses less memory than SortedDictionary<TKey, TValue>. It is recommended to use SortedList<TKey, TValue> if we have to store and retrieve key/value pairs. The SortedDictionary<TKey, TValue> class is faster than the SortedList<TKey, TValue> class if we perform insertion and removal for unsorted data.

## Features of the SortedList Function in C#

There are several features of the SortedList Function in C#. Some of them are as follows:

- In C#, this function is very useful to maintain the keys automatically in ascending order, which can be accessed by key or by index.
- It is used to give keys-values collections that can be iterated in sorted order.
- In C#, every key in the SortedList should be unique and cannot be null. However, the SortedList values can be duplicates or null.
- It is useful to implement several interfaces, including IDictionary<TKey, TValue>, ICollection<KeyValuePair<TKey, TValue>>, IEnumerable<KeyValuePair<TKey, TValue>>, and read-only methods.
- It takes an O(log n) complexity using the binary search on the keys, and enables direct access to values by index.

## Conclusion

In conclusion, the C# SortedList<TKey, TValue> is a fast, array-based collection of unique keys and their associated values in automatically sorted order by key, with fast lookups by key and index for datasets of moderate size. It is best suited to applications where retrieval, ordered iteration, and memory efficiency are emphasized over insertions or deletions that occur frequently, such as in ordered lookup tables, ranking structures, and data where consistent ordering of the keys is important.