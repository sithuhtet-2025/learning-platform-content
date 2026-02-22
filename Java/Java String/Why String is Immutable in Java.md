Strings in Java are immutable that means their values cannot be changed once they are created. In this chapter, we will learn why Java strings are immutable and how immutability improves security and performance.

## Why String is Immutable in Java?

Strings are immutable to provide security, memory efficiency, and reliable program behavior. Because strings are widely used to store sensitive information such as passwords, file paths, and URLs, immutability prevents their values from being altered once created. It also allows Java to use the string pool efficiently, where multiple references can safely share the same string object, saving memory.

Immutable strings are inherently thread-safe and provide consistent hash values that makes strings dependable when used as keys in collections like HashMap.

## Understanding String Immutability With Example

Let's consider the following example to understand the concept of string immutability.

[](https://www.tpointtech.com/why-string-is-immutable-in-java#)[](https://www.tpointtech.com/why-string-is-immutable-in-java#)[](https://www.tpointtech.com/why-string-is-immutable-in-java#)

1. class Testimmutablestring{  
2.  public static void main(String args[]){  
3.    String s="Sachin";  
4.    s.concat(" Tendulkar");//concat() method appends the string at the end  
5.    System.out.println(s);//will print Sachin because strings are immutable objects  
6.  }  
7. }  

**Output:**

Sachin

Now it can be understood by the diagram given below. Here Sachin is not changed but a new object is created with Sachin Tendulkar. That is why String is known as immutable.

![Immutable String in Java](https://images.tpointtech.com/core/images/immutable-string-in-java.png)

As you can see in the above figure that two objects are created but **_s_** reference variable still refers to "Sachin" not to "Sachin Tendulkar".

But if we explicitly assign it to the reference variable, it will refer to "Sachin Tendulkar" object.

For example:

[](https://www.tpointtech.com/why-string-is-immutable-in-java#)[](https://www.tpointtech.com/why-string-is-immutable-in-java#)[](https://www.tpointtech.com/why-string-is-immutable-in-java#)

1. class Testimmutablestring1{  
2.  public static void main(String args[]){  
3.    String s="Sachin";  
4.    s=s.concat(" Tendulkar");  
5.    System.out.println(s);  
6.  }  
7. }  

**Output:**

Sachin Tendulkar

In such a case, s points to the "Sachin Tendulkar". Please notice that still Sachin object is not modified.

## Why String Objects are Immutable in Java?

Java uses the concept of string literals, where multiple reference variables can point to the same string object stored in the string pool.

For example, if several reference variables refer to the same string value "Sachin", and that string were mutable, a change made through one reference would affect all others. This could lead to unexpected behavior in programs.

To prevent such issues and ensure safe and predictable behavior, **String objects are immutable in Java**.

The following features of the String class contribute to its immutability:

- **ClassLoader**  
    The ClassLoader uses String objects as arguments to load classes. If strings were mutable, their values could be changed after being passed to the class loader that may cause a different or incorrect class to be loaded. To prevent such misinterpretation and ensure that the correct class is always loaded, String objects are made immutable.
- **Thread Safety**  
    Since String objects are immutable, they can be safely shared between multiple threads without requiring synchronization. Because their values cannot be changed so there is no risk of data inconsistency when the same string object is accessed by multiple threads.
- **Security**  
    As seen in class loading, immutable strings prevent unauthorized changes to critical values. For example, in banking applications, sensitive data such as usernames and passwords are stored as strings. Because strings cannot be modified, this helps protect the application from malicious alterations and enhances overall security.
- **Heap Memory Optimization**  
    The immutability of strings also helps optimize heap memory usage. When a new string is created, the [JVM](https://www.tpointtech.com/jvm-java-virtual-machine) checks whether the same value already exists in the string pool. If it does, the existing string object is reused instead of creating a new one. This reuse of string objects reduces memory consumption and improves performance.