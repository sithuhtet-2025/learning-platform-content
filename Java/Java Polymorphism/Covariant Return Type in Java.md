The **covariant return type** in Java allows the return type of an [overridden metho](https://www.tpointtech.com/method-overriding-in-java) to be a subtype of the return type defined in the superclass. In other words, we can say the **covariant return type** specifies that the return type may vary in the same direction as the subclass.

Before Java 5, it was not possible to override any method by changing the return type. Since Java 5 or later versions, it is possible to override a method by changing the return type if a subclass overrides any method whose return type is Non-Primitive, but it changes its return type to subclass type.

**Note:** If you are a beginner to Java, skip this topic and return to it after OOPs concepts.

## Example of Covariant Return Type

In this example, class **B1** overrides the **get()** method of class **A** using a **covariant return type**. The overridden method in **B1** returns **B1** instead of **A**, allowing us to call the **message()** method directly on the returned object. This demonstrates how **covariant return types** enable more specific return types in method overriding.

[](https://www.tpointtech.com/covariant-return-type-in-java#)[](https://www.tpointtech.com/covariant-return-type-in-java#)[](https://www.tpointtech.com/covariant-return-type-in-java#)

1. class A{      
2. A get(){return this;}      
3. }      
4. class B1 extends A{      
5. @Override    
6. B1 get(){return this;}      
7. void message(){System.out.println("Welcome to the covariant return type");}      
8. public static void main(String args[]){      
9. new B1().get().message();      
10. }      
11. }    

**Output:**

Welcome to the covariant return type

## Advantages of Covariant Return Type

There are following advantages of Covariant Return Type in Java.

1. Covariant return type assists to stay away from the confusing type casts in the class hierarchy and makes the code more usable, readable, and maintainable.
2. In the method overriding, the covariant return type provides the liberty to have more to-the-point return types.
3. Covariant return type helps in preventing the run-time _ClassCastExceptions_on returns.

Let's take an example to understand the advantages of the covariant return type:

### Example

[](https://www.tpointtech.com/covariant-return-type-in-java#)[](https://www.tpointtech.com/covariant-return-type-in-java#)[](https://www.tpointtech.com/covariant-return-type-in-java#)

1. class A1    
2. {    
3.     A1 foo()    
4.     {    
5.         return this;    
6.     }    
7.     void print()    
8.     {    
9.         System.out.println("Inside the class A1");    
10.     }    
11. }    
12. // A2 is the child class of A1    
13. class A2 extends A1    
14. {    
15.     @Override    
16.     A1 foo()    
17.     {    
18.         return this;    
19.     }    
20.     void print()    
21.     {    
22.         System.out.println("Inside the class A2");    
23.     }    
24. }    
25. // A3 is the child class of A2    
26. class A3 extends A2    
27. {    
28.     @Override    
29.     A1 foo()    
30.     {    
31.         return this;    
32.     }    
33.     @Override    
34.     void print()    
35.     {    
36.         System.out.println("Inside the class A3");    
37.     }    
38. }    
39. public class Main  
40. {    
41.     // main method    
42.     public static void main(String argvs[])    
43.     {    
44.        A1 a1 = new A1();    
45.        // this is ok    
46.        a1.foo().print();    
47.        A2 a2 = new A2();    
48.        // we need to do the type casting to make it     
49.        // more clear to reader about the kind of object created     
50.        ((A2)a2.foo()).print();    
51.        A3 a3 = new A3();    
52.        // doing the type casting    
53.        ((A3)a3.foo()).print();    
54.     }    
55. }    

**Output:**

Inside the class A1
Inside the class A2
Inside the class A3

**Explanation:**

In the above program, class A3 inherits class A2, and class A2 inherits class A1. Thus, A1 is the parent of classes A2 and A3. Hence, any object of classes A2 and A3 is also of type A1. As the return type of the method _foo()_ is the same in every class, we do not know the exact type of object the method is actually returning.

We can only deduce that the returned object will be of type A1, which is the most generic class. We cannot say for sure that the returned object will be of A2 or A3. It is where we need to do the typecasting to find out the specific type of object returned from the method _foo()_.

It not only makes the code verbose. It also requires precision from the programmer to ensure that typecasting is done properly; otherwise, there are fair chances of getting the _ClassCastException_.

To exacerbate it, think of a situation where the hierarchical structure goes down to 10 - 15 classes or even more, and in each class, the method _foo()_ has the same return type. That is enough to give a nightmare to the reader and writer of the code.

The better way to write the above is:

### Example

[](https://www.tpointtech.com/covariant-return-type-in-java#)[](https://www.tpointtech.com/covariant-return-type-in-java#)[](https://www.tpointtech.com/covariant-return-type-in-java#)

1. class A1  
2. {  
3.     A1 foo()  
4.     {  
5.         return this;  
6.     }  

7.     void print()  
8.     {  
9.         System.out.println("Inside the class A1");  
10.     }  
11. }  

12. // A2 is the child class of A1  
13. class A2 extends A1  
14. {  
15.     @Override  
16.     A2 foo()  
17.     {  
18.         return this;  
19.     }  

20.     void print()  
21.     {  
22.         System.out.println("Inside the class A2");  
23.     }  
24. }  

25. // A3 is the child class of A2  
26. class A3 extends A2  
27. {  
28.     @Override  
29.     A3 foo()  
30.     {  
31.         return this;  
32.     }  

33.     @Override  
34.     void print()  
35.     {  
36.         System.out.println("Inside the class A3");  
37.     }  
38. }  

39. public class CovariantExample  
40. {  
41.     // main method  
42.     public static void main(String argvs[])  
43.     {  
44.        A1 a1 = new A1();  

45.        a1.foo().print();  

46.        A2 a2 = new A2();  

47.        a2.foo().print();  

48.        A3 a3 = new A3();  

49.        a3.foo().print();  

50.     }  
51. }  

**Output:**

Inside the class A1
Inside the class A2
Inside the class A3

**Explanation:** In the above program, no typecasting is needed as the return type is specific. Hence, there is no confusion about knowing the type of object getting returned from the method _foo()_. Also, even if we write the code for the 10 - 15 classes, there would be no confusion regarding the return types of the methods. All this is possible because of the covariant return type.

## How JVM Supports Covariant Return Types?

JVM always allows return type-based overloading. JVM uses the full signature of a method for lookup/resolution. Full signature means it includes return type in addition to argument types. i.e., a class can have two or more methods differing only by return type. javac uses this fact to implement covariant return types.

In other words, the covariant return type is implemented by allowing a subclass method to return a subtype of the superclass method's return type. The subclass method must have the same signature as the superclass method but can return a more specific type.

## Method Overriding Using Covariant Return Type in Java

If a method in a class returns a non-primitive type, then the same method in a subclass of that class can use the same nonprimitive type or a subclass of that nonprimitive type as the return type to override that method.

If class A has a method whose return type is an Object type, then the same method in a child class B (child of class A) can use a Number or Integer as a return type to override that method because Number and Integer classes are covariant of the Object class.

### Example

Let's take an example to demonstrate the method overriding using the covariant return type in Java.

### Example

[](https://www.tpointtech.com/covariant-return-type-in-java#)[](https://www.tpointtech.com/covariant-return-type-in-java#)[](https://www.tpointtech.com/covariant-return-type-in-java#)

1. class A {  
2.     Object print() {      
3.       System.out.println("print method of class A");  
4.       return new Object();  
5.     }   
6.  }   
7.  class B extends A {     
8.     Integer print() {  
9.       System.out.println("print method of class B");  
10.       return new Integer(2);  
11.     }      
12.     public static void main(String [] args) {  
13.       B b = new B();    
14.       b.print();  
15.       A a = new B();    
16.       a.print();      
17.     }  
18.  }  

**Output:**

print method of class B
print method of class B

As we can see in the above program, the print() method in class B is overriding the print() method of parent class A, though the return type of the child class method is Integer type It's happening because Java allows to use of covariant return type while overriding the method.