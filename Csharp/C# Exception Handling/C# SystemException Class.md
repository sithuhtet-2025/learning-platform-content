The SystemException is a predefined exception class in the C# programming language. It is used to handle system-related exceptions. It works as a base class for the system exception namespace. The SystemException class is used to represent errors that occur during program execution and are thrown by the Common Language Runtime (CLR).

![C# SystemException Class](https://images.tpointtech.com/csharp/images/c-sharp-systemexception.png)

In the [C# programming language](https://www.tpointtech.com/c-sharp-tutorial), most of the built-in exceptions (such as IndexOutOfRangeException, NullReferenceException, InvalidCastException, etc.) are derived from the SystemException.

### Syntax:

It has the following syntax:

[](https://www.tpointtech.com/c-sharp-systemexception#)[](https://www.tpointtech.com/c-sharp-systemexception#)[](https://www.tpointtech.com/c-sharp-systemexception#)

1. [SerializableAttribute]    
2. [ComVisibleAttribute(true)]    
3. public class SystemException : Exception    

### C# SystemException Class Example

Let us take an example to illustrate the SystemException class in C#.

### Example

[](https://www.tpointtech.com/c-sharp-systemexception#)[](https://www.tpointtech.com/c-sharp-systemexception#)[](https://www.tpointtech.com/c-sharp-systemexception#)

1. using System;    
2. namespace CSharpProgram    
3. {    
4.     class Program    
5.     {    
6.         static void Main(string[] args)    
7.         {    
8.             try    
9.             {    
10.                 int[] arr = new int[5];    
11.                 arr[10] = 25;    
12.             }    
13.             catch (SystemException e)    
14.             {    
15.                 Console.WriteLine(e);    
16.             }    
17.         }    
18.     }    
19. }    

**Output:**

System.IndexOutOfRangeException: Index was outside the bounds of the array.

**Explanation:**

In this example, we have taken an array of size 5, but the code tries to access index 10, which is out of range. After that, it causes a System.IndexOutOfRangeException, which is a subclass of SystemException, is caught in the catch block where the exception details are displayed.

### Important Points about SystemException in C#

Several important points about SystemException in C# are as follows:

- It represents the base class for all exceptions that are thrown by the runtime environment.
- It offers standard [constructors](https://www.tpointtech.com/c-sharp-constructor) and [properties](https://www.tpointtech.com/c-sharp-properties) to access error details, such as message, stack trace, and many inner exceptions.
- It is not compulsory to create our own custom exceptions from SystemException. Instead, we can create them directly from Exception.

SystemExceptions consists of rich constructors, properties, and methods that we have tabulated below.

### C# SystemException Constructors

The table below shows several types of SystemException constructors in C#.

|Constructors|Description|
|---|---|
|SystemException()|It is used to initialize a new instance of the SystemException class.|
|SystemException(SerializationInfo,StreamingContext)|It is used to initialize a new instance of the SystemException class with serialized data.|
|SystemException(String)|It is used to initialize a new instance of the SystemException class with a specified error message.|
|SystemException(String,Exception)|It is used to initialize a new instance of the SystemException class with a specified error message and a reference to the inner exception that is the cause of this exception.|

### C# SystemException Properties

The table below shows several types of SystemException properties in C#.

|Property|Description|
|---|---|
|Data|It is used to get a collection of key/value pairs that provide additional user-defined information about the exception.|
|HelpLink|It is used to get or set a link to the help file associated with this exception.|
|HResult|It is used to get or set HRESULT, a coded numerical value that is assigned to a specific exception.|
|InnerException|It is used to get the Exception instance that caused the current exception.|
|Message|It is used to get a message that describes the current exception.|
|Source|It is used to get or set the name of the application that causes the error.|
|StackTrace|It is used to get a string representation of the immediate frames on the call stack.|
|TargetSite|It is used to get the method that throws the current exception.|

### C# SystemException Methods

The table below shows several types of SystemException methods in C#.

|Method|Description|
|---|---|
|Equals(Object)|It is used to check that the specified object is equal to the current object or not.|
|Finalize()|It is used to free resources and perform cleanup operations.|
|GetBaseException()|It is used to get root exception.|
|GetHashCode()|It is used to get hash code.|
|GetObjectData(SerializationInfo,StreamingContext)|It is used to get object data.|
|GetType()|It is used to get the runtime type of the current instance.|
|MemberwiseClone()|It is used to create a shallow copy of the current Object.|
|ToString()|It is used to create and return a string representation of the current exception.|

### C# SystemException Example using Catching Specific Exception

Let us take an example to illustrate the System Exception by catching a specific exception in C.

### Example

[](https://www.tpointtech.com/c-sharp-systemexception#)[](https://www.tpointtech.com/c-sharp-systemexception#)[](https://www.tpointtech.com/c-sharp-systemexception#)

1. using System;  

2. class Tpoint  
3. {  
4.     static void Main()  
5.     {  
6.         try  
7.         {  
8.             string str = null;  
9.             Console.WriteLine(str.Length); // NullReferenceException  
10.         }  
11.         catch (NullReferenceException ex)  
12.         {  
13.             Console.WriteLine("Caught a NullReferenceException: " + ex.Message);  
14.         }  
15.         catch (SystemException ex)  
16.         {  
17.             Console.WriteLine("Caught another SystemException: " + ex.Message);  
18.         }  
19.     }  
20. }  

**Output:**

Caught a NullReferenceException: Object reference not set to an instance of an object

**Explanation:**

In this example, we try to access the Length property of a null string, which throws a NullReferenceException. First, we use the catch block that handles it specifically, while the second catch is used for SystemException that would handle any other system-level exceptions if they occurred.

## Conclusion

In conclusion, the SystemException class is an important class that acts as the base for all runtime exceptions that are thrown by the [Common Language Runtime (CLR)](https://www.tpointtech.com/net-common-language-runtime). If we do not use it to throw exceptions directly, it gives a method to find multiple runtime errors. It is commonly used in specific exceptions, which provides better error handling and debugging.