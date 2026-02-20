In the C# programming language, a reflection is the process of describing the metadata of types at runtime. The System.Reflection namespace contains the required classes for reflection. It allows us to discover information about classes, methods, properties, and fields. We can use it to create objects, call methods, or access data dynamically. It is commonly used in scenarios like serialization, testing, and plugin systems.

![C# Reflection](https://images.tpointtech.com/csharp/images/c-sharp-reflection.png)

## Namespace for Reflection

The System.Reflection namespace provides classes and interfaces required to perform reflection in C#.

[](https://www.tpointtech.com/c-sharp-reflection#)[](https://www.tpointtech.com/c-sharp-reflection#)[](https://www.tpointtech.com/c-sharp-reflection#)

1. using System.Reflection;  

In this syntax,

- **using:** It is the keyword used to include a namespace in a C# program.
- **Reflection:** It is the [namespace](https://www.tpointtech.com/c-sharp-namespaces) that contains all the classes and interfaces needed for reflection.

### C# Reflection Example

Let us take an example to illustrate the reflection in C#.

### Example

[](https://www.tpointtech.com/c-sharp-reflection#)[](https://www.tpointtech.com/c-sharp-reflection#)[](https://www.tpointtech.com/c-sharp-reflection#)

1. using System;     
2. class TPoint  
3. {     
4.     public string name;  
5.     public int age;  
6.     public void greet()  
7.     {  
8.         Console.WriteLine("Welcome! ");  
9.     }  
10. }  
11. class tech  
12. {  
13.     static void Main()  
14.     {  
15.         // Get type   
16.         Type type = typeof(TPoint);  
17.         Console.WriteLine("Class Name is " + type.Name );  
18.         Console.WriteLine("\nThe fields are ");  
19.         foreach (var f in type.GetFields())  
20.         {  
21.             Console.WriteLine("- " + f.Name );  
22.         }  
23.         Console.WriteLine("\n The methods are " );  
24.         foreach ( var m in type.GetMethods())  
25.         {  
26.             Console.WriteLine("- " + m.Name );  
27.         }  
28.     }  
29. }  

**Output:**

Class Name is TPoint
The fields are
- name
- age

The methods are
- greet
- Equals
- GetHashCode
- GetType
- ToString

**Explanation:**

In this example, we define the class named Person that contains two public fields, name and age, and one method greet(). It prints only Hello to the Console. Inside the Main() method of the TPoint class, we use the typeof(Person) function to get the type information of the Person class, and then it prints the name of the class using the GetFields() and GetMethods() methods.

## Application of Reflection:

Reflection has several applications in the [C# programming language](https://www.tpointtech.com/c-sharp-tutorial). Some of them are as follows:

- It allows for access to attribute data during program execution.
- It enables examining and instantiating various types or classes from an assembly.
- It allows calling methods and accessing properties during run time. It also supports late binding.
- It allows the creation and use of new types during program execution.

## Accessing Metadata using Reflection

In C#, reflection allows us to view attribute information. If we want to access the attributes associated with a class, we need to create a MemberInfo object from the System.Reflection namespace. It is done by defining an instance of the target class, as shown below:

[](https://www.tpointtech.com/c-sharp-reflection#)[](https://www.tpointtech.com/c-sharp-reflection#)[](https://www.tpointtech.com/c-sharp-reflection#)

1. System.Reflection.MemberInfo info = typeof(MyClass);  

## C# Reflection Hierarchy

In C#, the reflection is provided by the System.Reflection namespace, which follows a clear hierarchy of metadata classes that represent assemblies, modules, types, and their members. This namespace includes classes such as.

![C# Reflection](https://images.tpointtech.com/csharp/images/c-sharp-reflection2.png)

## C# Type Class

In C#, the Type class is the primary way to access the metadata. It provides methods and properties to inspect type information such as class name, methods, [properties](https://www.tpointtech.com/c-sharp-properties), [constructors](https://www.tpointtech.com/c-sharp-constructor), base type, and many more.

### C# Type Properties

A list of important properties of the Type class is given below:

|Property|Description|
|---|---|
|Assembly|It gets the assembly for this type.|
|AssemblyQualifiedName|It gets the assembly-qualified name for this type.|
|Attributes|It gets the attributes associated with the type.|
|BaseType|It gets the base or parent type.|
|FullName|It gets the fully qualified name of the type.|
|IsAbstract|It is used to check if the type is Abstract.|
|IsArray|It is used to check if the type is an Array.|
|IsClass|It is used to check if the type is Class.|
|IsEnum|It is used to check if the type is Enum.|
|IsInterface|It is used to check if the type is an Interface.|
|IsNested|It is used to check if the type is Nested.|
|IsPrimitive|It is used to check if the type is Primitive.|
|IsPointer|It is used to check if the type is Pointer.|
|IsNotPublic|It is used to check if the type is not Public.|
|IsPublic|It is used to check if the type is Public.|
|IsSealed|It is used to check if the type is Sealed.|
|IsSerializable|It is used to check if the type is Serializable.|
|MemberType|It is used to check if the type is a Member type or a Nested type.|
|Module|It gets the module of the type.|
|Name|It gets the name of the type.|
|Namespace|It gets the namespace of the type.|

### C# Type Methods

A list of important methods of the Type class is given below:

|Method|Description|
|---|---|
|GetConstructors()|It returns all the public constructors for the Type.|
|GetConstructors(BindingFlags)|It returns all the constructors for the Type with specified BindingFlags.|
|GetFields()|It returns all the public fields for the Type.|
|GetFields(BindingFlags)|It returns all the public constructors for the Type with specified BindingFlags.|
|GetMembers()|It returns all the public members for the Type.|
|GetMembers(BindingFlags)|It returns all the members for the Type with specified BindingFlags.|
|GetMethods()|It returns all the public methods for the Type.|
|GetMethods(BindingFlags)|It returns all the methods for the Type with specified BindingFlags.|
|GetProperties()|It returns all the public properties for the Type.|
|GetProperties(BindingFlags)|It returns all the properties for the Type with specified BindingFlags.|
|GetType()|It gets the current Type.|
|GetType(String)|It gets the Type for the given name.|

### Types of Reflection in C#

C# provides mainly four types of reflection, as follows.

![C# Reflection](https://images.tpointtech.com/csharp/images/c-sharp-reflection3.png)

Here, we will discuss the different types of Reflection one by one.

### 1) Type Reflection

In C#, we can use the Type class from the System.Reflection namespace to get metadata about a class, such as its name, methods, fields, and properties. It is commonly done using the GetType() method or the typeof operator.

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-reflection#)[](https://www.tpointtech.com/c-sharp-reflection#)[](https://www.tpointtech.com/c-sharp-reflection#)

1. Type typeInfo = typeof(ClassName);  

**C# Type Reflection Example**

Let us take an example to illustrate the GetType info using reflection in C#.

### Example

[](https://www.tpointtech.com/c-sharp-reflection#)[](https://www.tpointtech.com/c-sharp-reflection#)[](https://www.tpointtech.com/c-sharp-reflection#)

1. using System;  
2. using System.Reflection;  
3. class people  
4. {  
5.     public string name = "John";  
6.     public int age = 20;  
7.     public void Msg()  
8.     {     
9.         Console.WriteLine("Welcome");  
10.     }  
11. }  
12. class Program  
13. {  
14.     static void Main()  
15.     {  
16.         // Get Type using typeof  
17.         Type type = typeof(people);  
18.         Console.WriteLine("Class Name: " + type.Name);  
19.         // List public fields  
20.         foreach (var field in type.GetFields())  
21.         {  
22.             Console.WriteLine("Field: " + field.Name);  
23.         }  
24.         // List public methods  
25.         foreach (var method in type.GetMethods())  
26.         {  
27.             Console.WriteLine("Method: " + method.Name);  
28.         }  
29.     }  
30. }  

**Output:**

Class Name: people
Field: name
Field: age
Method: Msg
Method: Equals
Method: GetHashCode
Method: GetType
Method: ToString

**Explanation:**

In this example, we use the reflection to get information about the people class. The typeof(people) expression returns the Type object for the class, which holds name, fields, and methods. First, we print the class name using type.Name, and then we use the GetFields() method to print all the public fields in the class, and the GetMethod() methods print all the public methods, including both user-defined methods and built-in methods.

### 2) Assembly Reflection

In C#, we can use reflection to get information about the assembly where a [class or object](https://www.tpointtech.com/c-sharp-object-and-class) is defined. It is performed using the System.Reflection namespace, mainly the Assembly class.

**C# Assembly Reflection Example:**

Let us take an example to illustrate the assembly reflection in C#.

### Example

[](https://www.tpointtech.com/c-sharp-reflection#)[](https://www.tpointtech.com/c-sharp-reflection#)[](https://www.tpointtech.com/c-sharp-reflection#)

1. using System;  
2. using System.Reflection;  
3. class TPoint  
4. {  
5.     public string Name = "John";  
6.     public int Age = 30;  
7. }  
8. class Program  
9. {  
10.     static void Main()  
11.     {  
12.         // Creating an object  
13.         TPoint p = new TPoint();  
14.         Type type = p.GetType();  
15.         Assembly assembly = type.Assembly;  
16.         // Display Assembly information  
17.         Console.WriteLine("Class Name: " + type.Name);  
18.         Console.WriteLine("Assembly Full Name: " + assembly.FullName);  
19.         Console.WriteLine("Assembly Location: " + assembly.Location);  
20.     }  
21. }  

**Output:**

Class Name: TPoint
Assembly Full Name: Main, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null
Assembly Location: /tmp/2yFuUluxrd/Main.exe

**Explanation:**

In this example, we have taken the GetAssembly to retrieve the information about the assembly. First, we create an object p of the class TPoint, and then we use the p.GetType() to obtain the type information of the class. After that, we use the type.Assembly to access the assembly data, such as the name and file location.

### 3) Member Reflection

In the C# programming language, the member reflection allows us to access and work with specific members of a class, including methods, fields, properties, and constructors, at run-time.

**C# Member Reflection Example**

Let us take an example to demonstrate the member reflection in C#.

### Example

[](https://www.tpointtech.com/c-sharp-reflection#)[](https://www.tpointtech.com/c-sharp-reflection#)[](https://www.tpointtech.com/c-sharp-reflection#)

1. using System;  
2. using System.Reflection;  
3. class Tech    
4. {  
5.     public string Name = "John";  
6.     public void Tpoint()  
7.     {  
8.         Console.WriteLine("Welcome, " + Name);  
9.     }  
10. }  
11. class Program  
12. {  
13.     static void Main()  
14.     {  
15.         Tech t = new Tech();  
16.         Type type = t.GetType();  
17.         FieldInfo field = type.GetField("Name");  
18.         field.SetValue(t, "Alice");  
19.         MethodInfo method = type.GetMethod("Tpoint");    
20.         method.Invoke(t, null);   
21.     }  
22. }  

**Output:**

Welcome, Alice

**Explanation:**

In this example, we have created the class names as Tech with the field Name = "John" and method Tpoint() that prints a welcome message. Inside the main method, we create an object of the Tech class, and then use reflection to change the Name field to "Alice". After that, we use the reflection to call the Tpoint() method and print the output.

### 4) Attribute Reflection

In C#, the attribute reflection is a way to read metadata that we have added in our code using attributes. We can use reflection to inspect these attributes at runtime and use that information to control how the program behaves.

**C# Attribute Reflection Example**

Let us take an example to illustrate the attribute reflection in C#.

### Example

[](https://www.tpointtech.com/c-sharp-reflection#)[](https://www.tpointtech.com/c-sharp-reflection#)[](https://www.tpointtech.com/c-sharp-reflection#)

1. using System;  
2. using System.Reflection;  
3. [AttributeUsage(AttributeTargets.Method)]  
4. public class LogAttribute : Attribute { }  
5. public class TPoint  
6. {  
7.     [Log]  
8.     public void Message()  
9.     {  
10.         Console.WriteLine("Welcome Welcome Welcome");  
11.     }  
12. }  
13. public class tech  
14. {  
15.     public static void Main()  
16.     {  
17.         MethodInfo mm = typeof(TPoint).GetMethod("Message");  
18.         if (mm.GetCustomAttribute<LogAttribute>() != null)  
19.         {  
20.          Console.WriteLine("The TPoint method has a Log attribute.");  
21.         }  
22.     }  
23. }  

**Output:**

The TPoint method has a Log attribute.

**Explanation:**

In this example, we create a custom LogAttribute and apply it to a method named Message() in the TPoint class. Inside the main() method, we use reflection to check whether the Message() method has the LogAttribute applied. If the attribute is present, the program prints a confirmation message.

## Conclusion

In conclusion, C# Reflection is a comprehensive feature that allows programs to inspect and interact with object types, fields, properties, methods, and attributes at runtime. The System.Reflection namespace contains the required classes for reflection. Reflection also enables access to attribute data during program execution.