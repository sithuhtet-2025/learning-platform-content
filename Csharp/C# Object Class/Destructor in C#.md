
In the C# programming language, a destructor is a special method defined in a class that is utilized to perform cleanup operations before an object is removed from memory. A class contains only one destructor in the program. It is prefixed by a tilde (~) symbol followed by the class name.

Destructors are automatically called by the garbage collector (GC) before the object is reclaimed. These are mainly used to release unmanaged resources (such as file handles, database connections, network sockets, etc.).

As the [.NET](https://www.tpointtech.com/net-framework) garbage collector automatically manages memory for managed objects, destructors can be helpful when the class interacts with resources like files, database connections, and native handles.

### Syntax:

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-destructor#)[](https://www.tpointtech.com/c-sharp-destructor#)[](https://www.tpointtech.com/c-sharp-destructor#)

1. class class_name {  
2.     // Destructor  
3.     ~class_name()  
4.     {  
5.         // Cleanup code here  
6.     }  
7. }  

In this syntax;

- **class class_name:** It is used to define the class name.
- **~class_name:** It is used to define the destructor.

### C# Destructor Example

Let us take an example to illustrate the destructor in C#.

### Example

[](https://www.tpointtech.com/c-sharp-destructor#)[](https://www.tpointtech.com/c-sharp-destructor#)[](https://www.tpointtech.com/c-sharp-destructor#)

1. using System;  

2. class Tpointtech  
3. {  
4.     public Tpointtech()      // using Constructor  
5.     {  
6.         Console.WriteLine("An instance of Tpointtech class is created.");  
7.     }  
8.     ~Tpointtech()     // Destructor  
9.     {  
10.         Console.WriteLine("An instance of Tpointtech class is destroyed.");  
11.         // Cleanup code  
12.     }  
13. }  

14. class Program  
15. {  
16.     static void Main()  
17.     {  
18.         Tpointtech tpoint = new Tpointtech();  

19.         // garbage collection to define the destructor call  
20.         tpoint = null;  
21.         GC.Collect();  
22.         GC.WaitForPendingFinalizers();  
23.     }  
24. }  

**Output:**

An instance of Tpointtech class is created.
An instance of Tpointtech class is destroyed.

**Explanation:**

In this example, we have taken a class constructor. When we create an object of the Tpointtech class, the constructor executes and shows a message. After setting the object to null, the Garbage Collector is forced to run using GC.Collect() and GC.WaitForPendingFinalizers() functions, which invoke the destructor. After that, the destructor runs automatically to perform cleanup tasks before the object is destroyed.

### Key Characteristics of Destructors

Several main characteristics of the destructor in the [C# programming language](https://www.tpointtech.com/c-sharp-tutorial) are as follows:

- A destructor cannot take parameters and does not return any value.
- It does not have [access modifiers](https://www.tpointtech.com/c-sharp-access-modifiers) (public, private, etc.).
- Only one destructor is allowed per class.
- It cannot be called manually. It is executed automatically by the garbage collector.
- We can only define destructors in classes, not in [structs](https://www.tpointtech.com/c-sharp-structs).
- We cannot inherit or overload the destructor.

### C# Destructor Example with File Handling

Let us take an example to illustrate the destructor with file handling in C#.

### Example

[](https://www.tpointtech.com/c-sharp-destructor#)[](https://www.tpointtech.com/c-sharp-destructor#)[](https://www.tpointtech.com/c-sharp-destructor#)

1. using System;  
2. using System.IO;  

3. class File_hand  
4. {  
5.     private FileStream file;  

6.     // using Constructor  
7.     public File_hand(string fileName)  
8.     {  
9.         file = new FileStream(fileName, FileMode.OpenOrCreate);  
10.         Console.WriteLine("File opened successfully.");  
11.     }  

12.     // using Destructor  
13.     ~File_hand()  
14.     {  
15.         file.Close();  
16.         Console.WriteLine("File closed successfully.");  
17.     }  
18. }  

19. class Tpointtech  
20. {  
21.     static void Main(string[] args)  
22.     {  
23.         File_hand f = new File_hand("sample.txt");  
24.         Console.WriteLine("Working with file...");  
25.     }  
26. }  

**Output:**

File opened successfully.
Working with file...
File closed successfully.

**Explanation:**

In this example, we have created a class called File_hand, and its constructor opens a file when the object is created. The destructor ensures that the file is closed successfully when the Garbage Collector destroys the object. It ensures safe resource management by automatically releasing the file handle when it is no longer required.

## How Destructors Work with the Garbage Collector in C#?

C# uses a non-deterministic garbage collection system, which means that we can't predict exactly when the garbage collector will execute or when the destructor will be invoked. The runtime decides when it's a good time to cleanup memory based on available resources and memory pressure.

## When to use a Destructor in C#?

In [C# programming](https://www.tpointtech.com/c-sharp-tutorial), a destructor should be utilized when a class performs several tasks with unmanaged resources, such as database connections, network sockets, file handling, and many others. The main use of a destructor is to act as a cleanup mechanism to ensure that unmanaged resources are properly released before the object is destroyed.

C# destructors can also serve as a backup safety net if the Dispose() method is not explicitly invoked. Moreover, destructors are also useful when we deal with unmanaged resources, and the IDisposable interface with the Dispose() method is suitable for cleanup resources. If we are working with interop code that interacts with native libraries or APIs, it is very beneficial.

### IDisposable and Dispose Pattern in C#

Let us take an example to illustrate the IDisposable and Dispose Pattern in C#.

### Example

[](https://www.tpointtech.com/c-sharp-destructor#)[](https://www.tpointtech.com/c-sharp-destructor#)[](https://www.tpointtech.com/c-sharp-destructor#)

1. using System;  
2. using System.IO;  

3. class file_handle : IDisposable  
4. {  
5.     private FileStream file;  
6.     private bool disposed = false;  

7.     public file_handle(string fileName)  
8.     {  
9.         file = new FileStream(fileName, FileMode.OpenOrCreate);  
10.         Console.WriteLine("File Opened");  
11.     }  

12.     // Public Dispose method  
13.     public void Dispose()  
14.     {  
15.         Dispose(true);  
16.         GC.SuppressFinalize(this);   
17.     }  

18.     // using cleanup logic  
19.     protected virtual void Dispose(bool disposing)  
20.     {  
21.         if (!disposed)  
22.         {  
23.             if (disposing)  
24.             {  
25.                 // Dispose managed resources  
26.                 file?.Close();  
27.                 Console.WriteLine("File Closed");  
28.             }  

29.             // Dispose unmanaged resources  

30.             disposed = true;  
31.         }  
32.     }  

33.     // Destructor  
34.     ~file_handle()  
35.     {  
36.         Dispose(false);  
37.     }  
38. }  

39. class Tpoint  
40. {  
41.     static void Main()  
42.     {  
43.         using (file_handle fh = new file_handle("sample.txt"))  
44.         {  
45.             Console.WriteLine("Working with file");  
46.         } // Dispose() is automatically invoked  
47.     }  
48. }  

**Output:**

File Opened
Working with file
File Closed

**Explanation:**

In this example, we have taken the file_handle class that opens a file in its constructor and ensures cleanup through the Dispose() method, which is automatically invoked at the end of the using block. After that, the Dispose(bool disposing) method releases both managed and unmanaged resources, while the destructor behaves as a safety net if the Dispose() method is not explicitly called.

## Destructor and Finalize Method in C#

In the C# programming language, both destructors and the Finalize() method are mainly utilized for resource cleanup, but they differ in several aspects. A destructor in C# is essentially a syntax wrapper around the Finalize() method provided by the .NET runtime. If we write a destructor in C#, the compiler automatically translates it into an override of the Object.Finalize() method. We can override the Finalize() manually, but defining a destructor is the simpler and safer option.

### Syntax:

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-destructor#)[](https://www.tpointtech.com/c-sharp-destructor#)[](https://www.tpointtech.com/c-sharp-destructor#)

1. protected override void Finalize()  
2. {  
3.     try  
4.     {  
5.         // Cleanup code  
6.     }  
7.     finally  
8.     {  
9.         base.Finalize();  
10.     }  
11. }  

### C# Destructor and Finalize Method Example

Let us take an example to illustrate the destructor and finalize method in C#.

### Example

[](https://www.tpointtech.com/c-sharp-destructor#)[](https://www.tpointtech.com/c-sharp-destructor#)[](https://www.tpointtech.com/c-sharp-destructor#)

1. using System;  

2. class Tpoint  
3. {  
4.     public Tpoint()  
5.     {  
6.         Console.WriteLine("The Object is created successfully");  
7.     }  

8.     protected override void Finalize()  
9.     {  
10.         try  
11.         {  
12.             Console.WriteLine("Finalize method called: Explicit cleanup.");  
13.         }  
14.         finally  
15.         {  
16.             base.Finalize();  
17.         }  
18.     }  
19. }  

20. class Program  
21. {  
22.     static void Main()  
23.     {  
24.         Tpoint obj = new Tpoint();  
25.         obj = null;  

26.         GC.Collect();  
27.         GC.WaitForPendingFinalizers();  

28.         Console.WriteLine("Main method execution finished successfully");  
29.     }  
30. }  

**Output:**

main.cs(10,29): error CS0249: Do not override `object.Finalize()'. Use destructor syntax instead

**Explanation:**

In this example, we have taken the class Tpoint, and then take a [constructor](https://www.tpointtech.com/c-sharp-constructor) that creates an object, while the Finalize() method is automatically called by the garbage collector to cleanup resources before object destruction. Finally, the program ensures that the Finalize() method executes before the main method ends by forcing garbage collection using GC.Collect() and GC.WaitForPendingFinalizers() methods.

## Differences between Constructor and Destructor in C#

There are several differences between a constructor and a destructor in C#. Some of them are as follows:

|Features|Constructors|Destructors|
|---|---|---|
|**Purpose**|It initializes the object upon creation.|It performs the cleanup operations before destroying the object.|
|**Invocation**|It is explicitly invoked during the object creation.|It is automatically invoked by the Garbage Collector when the object is destroyed.|
|**Resource Allocation**|It is utilized for resource allocation.|It is often utilized for resource deallocation.|
|**Parametrization**|It can accept parameters for custom initialization.|It doesn't allow any parameters.|
|**Instances**|Several constructors can be defined with different parameters.|A class contains only one destructor and doesn't contain any overloads.|

## Conclusion

In conclusion, C# destructor offer a technique to cleanup before an object is destroyed. They are automatically invoked by the garbage collector when an object becomes unreachable. They are useful in specific scenarios, such as unmanaged resources or native code interaction. In modern C# programming, it is better to use IDisposable and implement the Dispose() pattern for more predictable and efficient resource management.