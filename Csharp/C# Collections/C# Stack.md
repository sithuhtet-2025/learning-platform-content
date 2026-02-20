In the C# programming language, the Stack<T> class is commonly utilized to push and pop elements. It uses the concept of a Stack that arranges elements in LIFO (Last In First Out) order. It can have duplicate elements. It is found in System.Collections.Generic namespace.

![C# Stack](https://images.tpointtech.com/cpp/images/csharp-stack.png)

In C#, the Stack class is commonly utilized when we need to manage data in a LIFO structure. It enables us to perform several useful operations effectively that can help to add, remove, and view elements.

### Syntax:

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-stack#)[](https://www.tpointtech.com/c-sharp-stack#)[](https://www.tpointtech.com/c-sharp-stack#)

1. Stack stack_name = new Stack();  

In this syntax,

- **stack_name:** It represents the name of the stack.

## Key Operations of the C# Stack Class

The C# stack class allows us to perform several operations. Some of them are as follows:

### 1) Push(T item) Function

In the C# programming language, the Push (T item) method is commonly utilized to insert an item onto the top of the stack. It follows the LIFO (Last-In-First-Out) principle, which means that the most recently added item in the stack will be removed first.

**C# Stack Class Example Using push() method**

Let us take an example to illustrate the stack class using the push() method in C#.

### Example

[](https://www.tpointtech.com/c-sharp-stack#)[](https://www.tpointtech.com/c-sharp-stack#)[](https://www.tpointtech.com/c-sharp-stack#)

1. using System;  
2. using System.Collections.Generic;  
3. class Tpoint  
4. {  
5.     static void Main()  
6.     {  
7.         Stack<string> stack = new Stack<string>();  
8.         stack.Push("Apple");  
9.         stack.Push("Banana");  
10.         stack.Push("Cherry");  
11.         Console.WriteLine("Elements after Push:");  
12.         foreach (var i in stack)  
13.             Console.WriteLine(i);  
14.     }  
15. }  

**Output:**

Elements after Push:
Cherry
Banana
Apple

**Explanation:**

In this example, we create a generic stack of strings that pushes three items ("Apple", "Banana", "Cherry") onto it, and prints the stack. Because a stack operates in LIFO order, the last pushed item ("Cherry") is printed first in the output, which is followed by "Banana" and then "Apple".

### 2) Pop() Function

In the C# programming language, the pop() function is commonly utilized to remove and return the item from the top of the stack.

**C# Stack Class Example using the pop() function**

Let's consider an example to demonstrate the stack class using the pop() function in C#.

### Example

[](https://www.tpointtech.com/c-sharp-stack#)[](https://www.tpointtech.com/c-sharp-stack#)[](https://www.tpointtech.com/c-sharp-stack#)

1. using System;  
2. using System.Collections.Generic;  
3. class pop  
4. {  
5.     static void Main()  
6.     {  
7.         Stack<int> s = new Stack<int>();  
8.         s.Push(100);  
9.         s.Push(200);  
10.         s.Push(300);  
11.         Console.WriteLine("Popped element: " + s.Pop());  
12.         Console.WriteLine("Remaining elements:");  
13.         foreach (var j in s)  
14.             Console.WriteLine(j);  
15.     }  
16. }  

**Output:**

Popped element: 300
Remaining elements:
200
100

**Output:**

In this example, we create an integer stack, where we insert 100, 200, and 300 into it. After that, it deletes and prints the top value with Pop() (which returns 300). Finally, it prints the rest of the elements, which display 200 and 100 in LIFO fashion.

### 3) Peek() Function

In the C# programming language, it is commonly utilized to return the item at the top of the stack, but it does not remove it.

**C# Stack class Example using the peek() function**

Let us consider a simple example to demonstrate the stack class using the peek() function in C#.

### Example

[](https://www.tpointtech.com/c-sharp-stack#)[](https://www.tpointtech.com/c-sharp-stack#)[](https://www.tpointtech.com/c-sharp-stack#)

1. using System;  
2. using System.Collections.Generic;  
3. class Tpoint  
4. {  
5.     static void Main()  
6.     {  
7.         Stack<string> stack = new Stack<string>();  
8.         stack.Push("Red");  
9.         stack.Push("Green");  
10.         stack.Push("Blue");  
11.         Console.WriteLine("Top element: " + stack.Peek());  
12.         Console.WriteLine("Stack after Peek:");  
13.         foreach (var item in stack)  
14.             Console.WriteLine(item);  
15.     }  
16. }  

**Output:**

Top element: Blue
Stack after Peek (unchanged):
Blue
Green
Red

**Explanation:**

In this example, we have created a stack of strings that pushes "Red", "Green", and "Blue" into the stack, and then we use the Peek() function to display the top item ("Blue") without popping it. After that, it prints the contents of the stack, which do not change: Blue, Green, Red.

### 4) Contains(T item) Function

In the C# programming language, the contains(T item) function is commonly utilized to determine whether a specific element exists within the stack. It searches the stack for the specified value. If the element is present in the stack, it returns a true value; otherwise, it returns a false value.

**C# Stack class Example using the contains() function**

Let's take an example to demonstrate the stack class using the contains() function in C#.

### Example

[](https://www.tpointtech.com/c-sharp-stack#)[](https://www.tpointtech.com/c-sharp-stack#)[](https://www.tpointtech.com/c-sharp-stack#)

1. using System;  
2. using System.Collections.Generic;  
3. class stack  
4. {  
5.     static void Main()  
6.     {  
7.         Stack<int> st = new Stack<int>();  
8.         st.Push(5);  
9.         st.Push(10);  
10.         st.Push(15);  
11.         Console.WriteLine("Does the stack contain 10 in it: " + st.Contains(10));  
12.         Console.WriteLine("Does the stack contain 20 in it: " + st.Contains(20));  
13.     }  
14. }  

**Output:**

Does the stack contain 10 in it: True
Does the stack contain 20 in it: False

**Explanation:**

In this example, we create a stack of integers that pushes elements 5, 10, and 15 onto it. After that, we use the Contains() function to check whether 10 and 20 are in the stack. It outputs True for 10 because it is there, and False for 20 because it is not.

### 5) Count() Function

The count() function in the C# programming language is commonly utilized to get the number of elements in the stack. In simple words, it is used to calculate the total no of elements in the stack.

**C# Stack class Example using the count() function**

Let us take an example to demonstrate the stack class using the count() function in C#.

### Example

[](https://www.tpointtech.com/c-sharp-stack#)[](https://www.tpointtech.com/c-sharp-stack#)[](https://www.tpointtech.com/c-sharp-stack#)

1. using System;  
2. using System.Collections.Generic;  
3. class counting  
4. {  
5.     static void Main()  
6.     {  
7.         Stack<char> stack = new Stack<char>();  
8.         stack.Push('A');  
9.         stack.Push('B');  
10.         stack.Push('C');  
11.         stack.Push('D');  
12.         Console.WriteLine("Total elements in stack: " + stack.Count);  
13.     }  
14. }  

**Output:**

Total elements in stack: 4

**Explanation:**

In this example, we have created a stack of characters that pushes 'A', 'B', 'C', and 'D' onto it. After that, it prints the number of elements using the Count() function, which is 4.

### 6) Clear() Function

In the C# programming language, the clear() function is commonly utilized to clear all items from the stack.

**C# Stack class Example using the clear() function**

Let's consider a simple example to illustrate the stack class using the clear() function in C#.

### Example

[](https://www.tpointtech.com/c-sharp-stack#)[](https://www.tpointtech.com/c-sharp-stack#)[](https://www.tpointtech.com/c-sharp-stack#)

1. using System;  
2. using System.Collections.Generic;  
3. class Tpoint  
4. {  
5.     static void Main()  
6.     {  
7.         Stack<string> stack = new Stack<string>();  
8.         stack.Push("a");  
9.         stack.Push("b");  
10.         stack.Push("c");  
11.         Console.WriteLine("Count before Clear: " + stack.Count);  
12.         stack.Clear();  
13.         Console.WriteLine("Count after Clear: " + stack.Count);  
14.     }  
15. }  

**Output:**

Count before Clear: 3
Count after Clear: 0

**Explanation:**

In this example, we have created a stack of strings taht pushes "a", "b", and "c" onto it. After that, we use the count() function to display the count of elements of the stack before clearing it as 3. Next, we delete all elements using the Clear() function, and again we count the total elements in the stack using the count() function, which is now 0.

### 7) ToArray() Function

In the C# programming language, the ToArray() function is commonly utilized to copy the elements of the stack into a new array.

**C# Stack class Example using the ToArray() function**

Let us take an example to demonstrate the stack class using the ToArray() function in C#.

### Example

[](https://www.tpointtech.com/c-sharp-stack#)[](https://www.tpointtech.com/c-sharp-stack#)[](https://www.tpointtech.com/c-sharp-stack#)

1. using System;  
2. using System.Collections.Generic;  
3. class Tpoint  
4. {  
5.     static void Main()  
6.     {  
7.         Stack<int> stack = new Stack<int>();  
8.         stack.Push(1);  
9.         stack.Push(2);  
10.         stack.Push(3);  
11.         int[] arr = stack.ToArray();  
12.         Console.WriteLine("Array elements:");  
13.         foreach (int n in arr)  
14.             Console.WriteLine(n);  
15.     }  
16. }  

**Output:**

Array elements:
3
2
1

**Explanation:**

In this example, we have created a stack of integers that pushes 1, 2, and 3 onto it. After that, we use the ToArray() function to copy the stack to an array. Next, it prints the array elements in LIFO fashion, which is displayed as 3, 2, 1.

### C# Stack class Example using the Push, Pop, and Peek() Operations

Let's see an example of a generic Stack<T> class that stores elements using the Push() method, removes elements using the Pop() method, and iterates elements using a for-each loop.

### Example

[](https://www.tpointtech.com/c-sharp-stack#)[](https://www.tpointtech.com/c-sharp-stack#)[](https://www.tpointtech.com/c-sharp-stack#)

1. using System;    
2. using System.Collections.Generic;      
3. public class StackExample    
4. {    
5.     public static void Main(string[] args)    
6.     {    
7.         Stack<string> names = new Stack<string>();    
8.         names.Push("Albert");    
9.         names.Push("Peter");    
10.         names.Push("James");    
11.         names.Push("Michael");    
12.         names.Push("Robert");      
13.         foreach (string name in names)    
14.         {    
15.             Console.WriteLine(name);    
16.         }      
17.         Console.WriteLine("Peek element: "+names.Peek());    
18.         Console.WriteLine("Pop: "+ names.Pop());    
19.         Console.WriteLine("After Pop, Peek element: " + names.Peek());    

20.     }    
21. }   

**Output:**

Robert
Michael
James
Peter
Albert
Peek element: Robert
Pop: Robert
After Pop, Peek element: Michael

**Explanation:**

In this example, we have created a Stack of strings named names that includes several elements using the Push() method. The elements are displayed using a foreach loop, which shows the Last-In-First-Out (LIFO) order. After that, the Peek() method retrieves the top element without removing it, while the Pop() method removes the top element from the stack. Finally, we print the updated top element after performing the pop operation.

## Features of the Stack<T> class in C#

There are several features of the stack class in C#. Some of them are as follows:

- In the C# stack class, we can include the elements using the Push() method.
- The top element can be retrieved and popped through Pop(), or simply retrieved without removal through Peek().
- It is not indexable.
- It supports null (for reference types) and duplicate items.
- We can have an empty stack or initialize it from a collection or an array.
- The Stack<T> class grows dynamically as elements are pushed, but also has a capacity property to allow for optimization of memory.

## Conclusion

In conclusion, the Stack class in C# is an effective class that uses the Last In, First Out (LIFO) principle, which makes it a better choice for several scenarios, such as reversing data, expression evaluation, and undo operations. It allows us to perform several operations, such as Push, Pop, and Peek, with type safety and fast performance. However, it gives access only to the top element. Overall, the Stack gives a simple and effective method to handle the temporary or sequential data in C#.