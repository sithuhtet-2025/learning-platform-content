The **this** keyword in Java is used to refer to the current object of a class and access its members. In this chapter, we will learn how this is used with variables, methods, and constructors with the help of examples.

## What Is this Keyword in Java?

In Java, the **"this"** keyword is a reference to the current object of a class. It is mainly used to differentiate between instance variables and parameters with the same name, call one constructor from another, or pass the current object as an argument to methods or constructors.

![this Keyword in Java](https://images.tpointtech.com/core/images/this-keyword-in-java.png)

## Characteristics of this Keyword

The following are the characteristics of this keyword in Java:

- **Represents the Current Object:** Think of this as a way for an object to refer to itself. If an object is calling a method, this points to that specific instance.
- **Helps Avoid Confusion:** If a method parameter has the same name as an instance variable, this makes it clear which one is the instance variable.
- **Calls Other Methods in the Same Class:** We don't always need this, but we can use it explicitly to call another method within the same class.
- **Supports Constructor Chaining:** this() can be used inside a constructor to call another constructor in the same class, helping reuse code.
- **Passes the Current Object as an Argument:** Sometimes, we need to send the current object to another method or class. This makes that possible.
- **Returns the Current Object:** A method can return this, allowing method chaining, which is common in fluent APIs.

## 1. Using this to Refer to Current Class Instance Variables

Java this keyword can be used to refer current class instance variable. If the instance variables and parameters are ambiguous, this keyword resolves the problem of ambiguity.

### Example without this keyword

Let's understand the problem if we do not use this keyword by the example given below:

### Example

[](https://www.tpointtech.com/this-keyword-in-java#)[](https://www.tpointtech.com/this-keyword-in-java#)[](https://www.tpointtech.com/this-keyword-in-java#)

1. class Student{    
2. int rollno;    
3. String name;    
4. float fee;    
5. Student(int rollno,String name,float fee){    
6. rollno=rollno;    
7. name=name;    
8. fee=fee;    
9. }    
10. void display(){System.out.println(rollno+" "+name+" "+fee);}    
11. }    
12. public class Main{    
13. public static void main(String args[]){    
14. Student s1=new Student(111,"Ankit",5000f);    
15. Student s2=new Student(112,"Sumit",6000f);    
16. s1.display();    
17. s2.display();    
18. }}    

**Output:**

0 null 0.0
0 null 0.0

**Explanation:**

In the above example, parameters (formal arguments) and instance variables are the same. So, we are using this keyword to distinguish the local variable and instance variable.

### Example: Using this keyword

Let us take another example to demonstrate the working of this keyword in Java.

### Example

[](https://www.tpointtech.com/this-keyword-in-java#)[](https://www.tpointtech.com/this-keyword-in-java#)[](https://www.tpointtech.com/this-keyword-in-java#)

1. class Student{    
2. int rollno;    
3. String name;    
4. float fee;    
5. Student(int rollno,String name,float fee){    
6. this.rollno=rollno;    
7. this.name=name;    
8. this.fee=fee;    
9. }    
10. void display(){System.out.println(rollno+" "+name+" "+fee);}    
11. }    
12. public class Main{    
13. public static void main(String args[]){    
14. Student s1=new Student(111,"Ankit",5000f);    
15. Student s2=new Student(112,"Sumit",6000f);    
16. s1.display();    
17. s2.display();    
18. }}    

**Output:**

111 Ankit 5000.0
112 Sumit 6000.0

### Example: Without requiring this keyword

If local variables(formal arguments) and instance variables are different, there is no need to use this keyword like in the following program:

### Example

[](https://www.tpointtech.com/this-keyword-in-java#)[](https://www.tpointtech.com/this-keyword-in-java#)[](https://www.tpointtech.com/this-keyword-in-java#)

1. class Student{    
2. int rollno;    
3. String name;    
4. float fee;    
5. Student(int r,String n,float f){    
6. rollno=r;    
7. name=n;    
8. fee=f;    
9. }    
10. void display(){System.out.println(rollno+" "+name+" "+fee);}    
11. }    
12.   class Main {    
13. public static void main(String args[]){    
14. Student s1=new Student(111,"Ankit",5000f);    
15. Student s2=new Student(112,"Sumit",6000f);    
16. s1.display();    
17. s2.display();    
18. }}    

**Output:**

111 Ankit 5000.0
112 Sumit 6000.0

> **Note:** It is a better approach to use meaningful names for variables. So we use the same name, for instance, variables and parameters in real-time, and always use this keyword.

## 2. Using this to Call Current Class Methods

You may invoke the method of the current class by using this keyword. If you do not use this keyword, the compiler automatically adds this keyword while invoking the method.

Let's see the following example to demonstrate how to use the this keyword to call current class methods in Java.

### Example

[](https://www.tpointtech.com/this-keyword-in-java#)[](https://www.tpointtech.com/this-keyword-in-java#)[](https://www.tpointtech.com/this-keyword-in-java#)

1. class A{    
2. void m(){System.out.println("hello m");}    
3. void n(){    
4. System.out.println("hello n");    
5. //m();//same as this.m()    
6. this.m();    
7. }    
8. }    
9. class Main{    
10. public static void main(String args[]){    
11. A a=new A();    
12. a.n();    
13. }}    

**Output:**

hello n
hello m

## 3. Using this() to Call the Current Class Constructor

The this() constructor call can be used to invoke the current class constructor. It is used to reuse the constructor. In other words, it is used for constructor chaining.

### Example: Calling Default Constructor From Parameterized Constructor

Let us take an example to demonstrate how to call the default constructor from parameterized constructor in Java.

### Example

[](https://www.tpointtech.com/this-keyword-in-java#)[](https://www.tpointtech.com/this-keyword-in-java#)[](https://www.tpointtech.com/this-keyword-in-java#)

1. class A{    
2. A(){System.out.println("hello a");}    
3. A(int x){    
4. this();    
5. System.out.println(x);    
6. }    
7. }    
8. public class Main{    
9. public static void main(String args[]){    
10. A a=new A(10);    
11. }}    

**Output:**

hello a
10

### Example: Calling Parameterized Constructor From Default Constructor

Let us take an example to demonstrate how to call the parameterized constructor from default constructor in Java.

### Example

[](https://www.tpointtech.com/this-keyword-in-java#)[](https://www.tpointtech.com/this-keyword-in-java#)[](https://www.tpointtech.com/this-keyword-in-java#)

1. class A{    
2. A(){    
3. this(5);    
4. System.out.println("hello a");    
5. }    
6. A(int x){    
7. System.out.println(x);    
8. }    
9. }    
10. class Main{    
11. public static void main(String args[]){    
12. A a=new A();    
13. }}    

**Output:**

5
hello a

### Real usage of this() constructor call

The this() constructor call should be used to reuse the constructor from the constructor. It maintains the chain between the constructors i.e. it is used for constructor chaining. Let's see the example given below that displays the actual use of this keyword.

The this() constructor call should be used to reuse the constructor from the constructor. It maintains the chain between the constructors, i.e., it is used for constructor chaining.

Let's see the example given below that displays the actual use of this keyword.

### Example

[](https://www.tpointtech.com/this-keyword-in-java#)[](https://www.tpointtech.com/this-keyword-in-java#)[](https://www.tpointtech.com/this-keyword-in-java#)

1. class Student{    
2.     int rollno;    
3.     String name,course;    
4.     float fee;    
5.     Student(int rollno,String name,String course)  
6.     {    
7.         this.rollno=rollno;    
8.         this.name=name;    
9.         this.course=course;    
10.     }    
11.     Student(int rollno,String name,String course,float fee)  
12.     {    
13.         this(rollno,name,course);//reusing constructor    
14.         this.fee=fee;    
15.     }    
16.     void display()  
17.     {  
18.         System.out.println(rollno+" "+name+" "+course+" "+fee);  
19.     }    
20. }    
21. public class Main{    
22.     public static void main(String args[]){    
23.         Student s1=new Student(111,"ankit","java");    
24.         Student s2=new Student(112,"sumit","java",6000f);    
25.         s1.display();    
26.         s2.display();    
27.     }  
28. }    

**Output:**

111 ankit java 0.0
112 sumit java 6000.0

**Rule:** Call to this() must be the first statement in the constructor.

### Example

In the following example, a compile-time error occurs because the this() constructor call is not the first statement inside the constructor.

[](https://www.tpointtech.com/this-keyword-in-java#)[](https://www.tpointtech.com/this-keyword-in-java#)[](https://www.tpointtech.com/this-keyword-in-java#)

1. class Student{    
2. int rollno;    
3. String name,course;    
4. float fee;    
5. Student(int rollno,String name,String course){    
6. this.rollno=rollno;    
7. this.name=name;    
8. this.course=course;    
9. }    
10. Student(int rollno,String name,String course,float fee){    
11. this.fee=fee;    
12. this(rollno,name,course);//C.T.Error    
13. }    
14. void display(){System.out.println(rollno+" "+name+" "+course+" "+fee);}    
15. }    
16. class Main{    
17. public static void main(String args[]){    
18. Student s1=new Student(111,"Ankit","Java");    
19. Student s2=new Student(112,"Sumit","Java",6000f);    
20. s1.display();    
21. s2.display();    
22. }}    

**Output:**

Compile Time Error: Call to this must be the first statement in the constructor

## 4. Using this to Pass the Current Object as a Method Argument

Java this keyword can also be passed as an argument in the method. It is mainly used in event handling.

### Example

Let's take an example to demonstrate how to use the this keyword to Pass the Current Object as a Method Argument.

### Example

[](https://www.tpointtech.com/this-keyword-in-java#)[](https://www.tpointtech.com/this-keyword-in-java#)[](https://www.tpointtech.com/this-keyword-in-java#)

1. class Main{    
2.   void m(Main obj){    
3.   System.out.println("method is invoked");    
4.   }    
5.   void p(){    
6.   m(this);    
7.   }    
8.   public static void main(String args[]){    
9.   Main m = new Main();    
10.   m.p();    
11.   }    
12. }    

**Output:**

method is invoked

### Application

In event handling (or) in a situation where we have to provide reference of a class to another one. It is used to reuse one object in many methods.

## 5. Using this to Pass the Current Object in a Constructor Call

We can pass the this keyword in the constructor also. It is useful if we have to use one object in multiple classes.

### Example

Let's take an example to demonstrate how to use this keyword to ass the Current Object in a Constructor Call.

[](https://www.tpointtech.com/this-keyword-in-java#)[](https://www.tpointtech.com/this-keyword-in-java#)[](https://www.tpointtech.com/this-keyword-in-java#)

1. class B{    
2.   A4 obj;    
3.   B(A4 obj){    
4.     this.obj=obj;    
5.   }    
6.   void display(){    
7.     System.out.println(obj.data);//using data member of A4 class    
8.   }    
9. }    
10.   class Main {    
11.   int data=10;    
12.   A4(){    
13.    B b=new B(this);    
14.    b.display();    
15.   }    
16.   public static void main(String args[]){    
17.    A4 a=new A4();    
18.   }    
19. }    

**Output:**

10

## 6. Using this to Return the Current Class Instance

We can return this keyword as a statement from the method. In such a case, the return type of the method must be the class type (non-primitive).

### Syntax

It has the following syntax:

[](https://www.tpointtech.com/this-keyword-in-java#)[](https://www.tpointtech.com/this-keyword-in-java#)[](https://www.tpointtech.com/this-keyword-in-java#)

1. return_type method_name(){  
2. return this;  
3. }  

### Example of this keyword that you return as a statement from the method

Let us take an example of this keyword that you return as a statement from the method.

### Example

[](https://www.tpointtech.com/this-keyword-in-java#)[](https://www.tpointtech.com/this-keyword-in-java#)[](https://www.tpointtech.com/this-keyword-in-java#)

1. class A{    
2. A getA(){    
3. return this;    
4. }    
5. void msg(){System.out.println("Hello Java");}    
6. }    
7. class Main{    
8. public static void main(String args[]){    
9. new A().getA().msg();    
10. }    
11. }    

**Output:**

Hello Java

### Proving this keyword

Let's prove that this keyword refers to the current class instance variable. In this program, we are printing the reference variable, and this output of both variables are same.

### Example

[](https://www.tpointtech.com/this-keyword-in-java#)[](https://www.tpointtech.com/this-keyword-in-java#)[](https://www.tpointtech.com/this-keyword-in-java#)

1. class Main{    
2. void m(){    
3. System.out.println(this);//prints same reference ID   
4. }    
5. public static void main(String args[]){    
6. Main obj=new Main();    
7. System.out.println(obj);//prints the reference ID    
8. obj.m();    
9. }    
10. }    

**Output:**

A5@22b3ea59
A5@22b3ea59