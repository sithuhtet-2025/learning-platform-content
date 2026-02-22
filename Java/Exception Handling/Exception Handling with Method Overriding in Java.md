Exception handling in Java with method overriding defines the rules for how a subclass can handle, restrict, or extend exceptions thrown by an overridden method.

## Rules of Exception Handling with Method Overriding

There are many rules if we talk about method overriding with exception handling.

Some of the rules are listed below:

- **If the superclass method does not declare an exception**
    - If the superclass method does not declare an exception, subclass overridden method cannot declare the checked exception but it can declare unchecked exception.
- **If the superclass method declares an exception**
    - If the superclass method declares an exception, subclass overridden method can declare same, subclass exception or no exception but cannot declare parent exception.

## If the superclass method does not declare an exception

### Rule 1

If the superclass method does not declare an exception, subclass overridden method cannot declare the checked exception.

### Example

In the following example, the child class attempts to override a parent class method by declaring a checked exception, which results in a compile-time error because the parent method does not throw any exception.

[](https://www.tpointtech.com/exception-handling-with-method-overriding#)[](https://www.tpointtech.com/exception-handling-with-method-overriding#)[](https://www.tpointtech.com/exception-handling-with-method-overriding#)

1. import java.io.*;    
2. class Parent{   

3.   // defining the method   
4.   void msg() {  
5.     System.out.println("parent method");  
6.     }    
7. }    

8. public class TestExceptionChild extends Parent{    

9.   // overriding the method in child class  
10.   // gives compile time error  
11.   void msg() throws IOException {    
12.     System.out.println("TestExceptionChild");    
13.   }  

14.   public static void main(String args[]) {    
15.    Parent p = new TestExceptionChild();    
16.    p.msg();    
17.   }    
18. }    

**Output:**

![Exception Handling with Method Overriding in Java](https://images.tpointtech.com/core/images/exception-handling-with-method-overriding.png)

### Rule 2

If the superclass method does not declare an exception, subclass overridden method cannot declare the checked exception but can declare unchecked exception.

### Example

In the following example, the child class successfully overrides the parent class method by throwing an unchecked exception, which is allowed even though the parent method does not declare any exception.

[](https://www.tpointtech.com/exception-handling-with-method-overriding#)[](https://www.tpointtech.com/exception-handling-with-method-overriding#)[](https://www.tpointtech.com/exception-handling-with-method-overriding#)

1. import java.io.*;    
2. class Parent{    
3.   void msg() {  
4.     System.out.println("parent method");  
5.   }    
6. }    

7. class TestExceptionChild1 extends Parent{    
8.   void msg()throws ArithmeticException {    
9.     System.out.println("child method");    
10.   }    

11.   public static void main(String args[]) {    
12.    Parent p = new TestExceptionChild1();    
13.    p.msg();    
14.   }    
15. }   

**Output:**

![Exception Handling with Method Overriding in Java](https://images.tpointtech.com/core/images/exception-handling-with-method-overriding2.png)

## If the superclass method declares an exception

If the superclass method declares an exception, subclass overridden method can declare the same subclass exception or no exception but cannot declare parent exception.

### Example: Subclass Overridden Method Declares Parent Exception

In the following example, the child class attempts to override the parent method by declaring a broader checked exception, which causes a compile-time error because an overridden method cannot throw a wider exception than the parent method.

[](https://www.tpointtech.com/exception-handling-with-method-overriding#)[](https://www.tpointtech.com/exception-handling-with-method-overriding#)[](https://www.tpointtech.com/exception-handling-with-method-overriding#)

1. import java.io.*;    
2. class Parent{    
3.   void msg()throws ArithmeticException {  
4.     System.out.println("parent method");  
5.   }    
6. }    

7. public class TestExceptionChild2 extends Parent{    
8.   void msg()throws Exception {  
9.     System.out.println("child method");  
10.   }    

11.   public static void main(String args[]) {    
12.    Parent p = new TestExceptionChild2();    

13.    try {    
14.    p.msg();    
15.    }  
16.    catch (Exception e){}   

17.   }    
18. }     

**Output:**

![Exception Handling with Method Overriding in Java](https://images.tpointtech.com/core/images/exception-handling-with-method-overriding3.png)

### Example: Subclass Overridden Method Declares Same Exception

In the following example, the child class overrides the parent class method by declaring the same exception, which is valid and does not cause any compile-time error.

[](https://www.tpointtech.com/exception-handling-with-method-overriding#)[](https://www.tpointtech.com/exception-handling-with-method-overriding#)[](https://www.tpointtech.com/exception-handling-with-method-overriding#)

1. import java.io.*;    
2. class Parent{    
3.   void msg() throws Exception {  
4.     System.out.println("parent method");  
5.   }    
6. }    

7. public class TestExceptionChild3 extends Parent {    
8.   void msg()throws Exception {  
9.     System.out.println("child method");  
10.   }    

11.   public static void main(String args[]){    
12.    Parent p = new TestExceptionChild3();    

13.    try {    
14.    p.msg();    
15.    }  
16.    catch(Exception e) {}    
17.   }    
18. }    

**Output:**

![Exception Handling with Method Overriding in Java](https://images.tpointtech.com/core/images/exception-handling-with-method-overriding4.png)

### Example: Subclass Overridden Method Declares Subclass Exception

In the following example, the child class overrides the parent method by declaring a subclass (narrower) exception, which is allowed in Java method overriding.

[](https://www.tpointtech.com/exception-handling-with-method-overriding#)[](https://www.tpointtech.com/exception-handling-with-method-overriding#)[](https://www.tpointtech.com/exception-handling-with-method-overriding#)

1. import java.io.*;    
2. class Parent{    
3.   void msg()throws Exception {  
4.     System.out.println("parent method");  
5.   }    
6. }    

7. class TestExceptionChild4 extends Parent{    
8.   void msg()throws ArithmeticException {  
9.     System.out.println("child method");  
10.   }    

11.   public static void main(String args[]){    
12.    Parent p = new TestExceptionChild4();    

13.    try {    
14.    p.msg();    
15.    }  
16.    catch(Exception e) {}    
17.   }    
18. }    

**Output:**

![Exception Handling with Method Overriding in Java](https://images.tpointtech.com/core/images/exception-handling-with-method-overriding5.png)

### Example: Subclass Overridden Method Declares No Exception

In the following example, the child class overrides the parent method without declaring any exception, which is valid even though the parent method throws an exception.

[](https://www.tpointtech.com/exception-handling-with-method-overriding#)[](https://www.tpointtech.com/exception-handling-with-method-overriding#)[](https://www.tpointtech.com/exception-handling-with-method-overriding#)

1. import java.io.*;    
2. class Parent {    
3.   void msg()throws Exception{  
4.     System.out.println("parent method");  
5.   }    
6. }    

7. class TestExceptionChild5 extends Parent{    
8.   void msg() {  
9.     System.out.println("child method");  
10.   }    

11.   public static void main(String args[]){    
12.    Parent p = new TestExceptionChild5();    

13.    try {    
14.    p.msg();    
15.    }  
16.    catch(Exception e) {}  

17.   }    
18. }     

**Output:**

![Exception Handling with Method Overriding in Java](https://images.tpointtech.com/core/images/exception-handling-with-method-overriding6.png)