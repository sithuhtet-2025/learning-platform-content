Java static synchronization ensures thread safety for shared static resources by locking the class-level object instead of individual instances.

In this chapter**,** we will learn how static synchronization works and how it ensures safe access to shared static data in a multithreaded environment.

## What Is Static Synchronization?

Although a synchronized method ensures that only one thread can access it at a time, it applies an **instance-level lock**, which may not be sufficient when multiple objects or static members are involved. In such cases, the execution order of threads is not guaranteed across different instances.

**Static synchronization** solves this problem by applying a **class-level lock** instead of an object-level lock. When a static method is declared as synchronized, the lock is placed on the **Class object**, ensuring that only one thread can execute any static synchronized method of that class at a time.

For an example, if a class contains multiple static synchronized methods (such as demo1, demo2, demo3, and demo4), and one thread is executing demo1, no other thread can access any of the other static synchronized methods simultaneously. This guarantees consistent behavior for shared static resources.

## Creating Static Synchronization Block

Static synchronization is achieved by applying a lock at the class level instead of the object level. While static synchronized methods automatically lock the class, you can also explicitly create a static synchronized block by locking the Class object.

### Syntax

Here is the syntax:

[](https://www.tpointtech.com/static-synchronization-in-java#)[](https://www.tpointtech.com/static-synchronization-in-java#)[](https://www.tpointtech.com/static-synchronization-in-java#)

1. synchronized (ClassName.class) {  
2.     // code  
3. }  

## Why Static Synchronization Is Needed?

Suppose there are two objects of a shared class Table, named object1 and object2. When using **synchronized methods** or **synchronized blocks**, threads working on the **same object** (for example, t1 and t2) do not interfere with each other because they share a single object-level lock.

However, threads operating on **different objects** (such as t1 with object1 and t3 with object2) can still interfere with each other because each object has its **own lock**. This means synchronization at the instance level is not sufficient to protect shared static resources.

To avoid such interference across multiple objects, **static synchronization** is used. It applies a **class-level lock**, ensuring that only one thread can access the shared resource at a time, regardless of how many objects of the class are created.

Therefore, static synchronization is preferred when a shared resource must be accessed in a **thread-safe and consistent manner across all instances** of a class.

## Example of Static Synchronization

The following example demonstrates how static synchronization applies a class-level lock to ensure that only one thread executes the method at a time, even when multiple objects are created.

### Example

[](https://www.tpointtech.com/static-synchronization-in-java#)[](https://www.tpointtech.com/static-synchronization-in-java#)[](https://www.tpointtech.com/static-synchronization-in-java#)

1. class Print  
2. {  
3. // static synchronized method declaration  
4.     public static synchronized void printMessage(String s)  
5.     {  
6.         for(int i = 0; i < 4; i++)  
7.         {  
8.             System.out.print("Good Night: ");  
9.             System.out.println(s);  
10.             try{  
11.                 Thread.sleep(1000);  //sleep thread for 1 sec  
12.             }  
13.             catch(InterruptedException e)  
14.             {  
15.             }  
16.         }  
17.     }  
18. }  
19. class MyThrd extends Thread {  
20.     Print p;  
21.     String s;  
22.     MyThrd(Print p, String s)  
23.     {  
24.         this.p = p;  
25.         this.s = s;  
26.     }  
27.     public void run()  
28.     {  
29.         p.printMessage(s);  
30.     }  
31. }  
32. public class Main {  
33.     public static void main(String arg[])  
34.     {  
35.         Print p1 = new Print();  
36.         Print p2 = new Print();  
37.         MyThrd th1 = new MyThrd(p1,"Mahi");  
38.         MyThrd th2 = new MyThrd(p2,"Sachin");  
39.         th1.start(); // start thread th1  
40.         th2.start(); // start thread th2  
41.     }   
42. }  

**Output:**

Good Night: Mahi
Good Night: Mahi
Good Night: Mahi
Good Night: Mahi
Good Night: Sachin
Good Night: Sachin
Good Night: Sachin
Good Night: Sachin

Good Night: Mahi
Good Night: Mahi
Good Night: Mahi
Good Night: Mahi
Good Night: Sachin
Good Night: Sachin
Good Night: Sachin
Good Night: Sachin

**Explanation:**

In this program, **Print** contains a static synchronized method, **MyThrd** creates and runs threads that call this method, and **Main** starts multiple threads. Since the method is static synchronized, the first thread acquires the class-level lock and executes the method, while the other thread waits until the lock is released, ensuring thread-safe and ordered execution.

## Static Synchronization by Using the Anonymous Class

In static synchronization using an anonymous class, threads are created without defining separate thread classes, while synchronization is still maintained at the **class level**. Since the method is static synchronized, all threads share the same class-level lock, ensuring that only one thread executes the method at a time.

### Example

In this example, multiple threads are created using anonymous classes, and static synchronization ensures that each thread executes the printTable() method one after another without interference.

[](https://www.tpointtech.com/static-synchronization-in-java#)[](https://www.tpointtech.com/static-synchronization-in-java#)[](https://www.tpointtech.com/static-synchronization-in-java#)

1. //Creating a class that contains a static synchronized method   
2. class Table{    
3.  synchronized static  void printTable(int n){    
4.    for(int i=1;i<=10;i++){    
5.      System.out.println(n*i);    
6.      try{    
7.        Thread.sleep(100);    
8.      }catch(Exception e){}    
9.    }    
10.  }    
11. }    
12. //Creating a Main class to call static synchronized method on threads run  
13. public class Main {    
14.  public static void main(String[] args) {    
15.     Thread t1=new Thread(){    
16.         public void run(){    
17.             Table.printTable(1);    
18.         }    
19.     };    
20.     Thread t2=new Thread(){    
21.         public void run(){    
22.             Table.printTable(10);    
23.         }    
24.     };    
25.     Thread t3=new Thread(){    
26.         public void run(){    
27.             Table.printTable(100);    
28.         }    
29.     };    
30.     Thread t4=new Thread(){    
31.         public void run(){    
32.             Table.printTable(1000);    
33.         }    
34.     };    
35.     t1.start();    
36.     t2.start();    
37.     t3.start();    
38.     t4.start();    

39.  }    
40. }    

**Output:**

100
200
300
400
500
600
700
800
900
1000
10
20
30
40
50
60
70
80
90
100
1000
2000
3000
4000
5000
6000
7000
8000
9000
10000
1
2
3
4
5
6
7
8
9
10

## Synchronized Block on a Class Lock

A synchronized block on a class lock is used to achieve static synchronization without declaring the entire method as static synchronized.

In this approach, the lock is acquired on the **ClassName.class** object, which represents the class-level monitor. This ensures that only one thread can execute the synchronized block across all instances of the class.

A static synchronized method is internally equivalent to a synchronized block that locks the class object.

### Example

In the following example, a synchronized block locks the **Table.class** object to provide class-level synchronization for a shared static resource.

[](https://www.tpointtech.com/static-synchronization-in-java#)[](https://www.tpointtech.com/static-synchronization-in-java#)[](https://www.tpointtech.com/static-synchronization-in-java#)

1. class Table {  

2.     static void printTable(int n) {  
3.         synchronized (Table.class) {   // class-level lock  
4.             for (int i = 1; i <= 5; i++) {  
5.                 System.out.println(n * i);  
6.                 try {  
7.                     Thread.sleep(400);  
8.                 } catch (Exception e) {  
9.                     System.out.println(e);  
10.                 }  
11.             }  
12.         }  
13.     }  
14. }  

15. class MyThread extends Thread {  
16.     int n;  

17.     MyThread(int n) {  
18.         this.n = n;  
19.     }  

20.     public void run() {  
21.         Table.printTable(n);  
22.     }  
23. }  

24. public class Main {  
25.     public static void main(String[] args) {  
26.         MyThread t1 = new MyThread(5);  
27.         MyThread t2 = new MyThread(100);  

28.         t1.start();  
29.         t2.start();  
30.     }  
31. }  

**Output:**

5
10
15
20
25
100
200
300
400
500

## Difference Between Synchronization and Static Synchronization

The following table shows the difference between synchronization and static synchronization.

|Aspect|Synchronization|Static Synchronization|
|---|---|---|
|**Scope of Lock**|It locks the instance (object level).|It locks the class object (class level)|
|**Use**|It applies to instance methods or blocks.|It applies to static methods or blocks.|
|**Lock Context**|Lock is associated with the current object instance.|The lock is related to the .class object of the class.|
|**Thread Access**|It ensures that only one thread accesses the synchronized instance code of the same object at a time.|It ensures only one thread accesses the synchronized static code of the entire class at a time.|
|**Impact**|It affects thread safety at the instance level.|It affects thread safety for shared static resources.|
|**Uses**|To synchronize instance-specific data access.|To synchronize shared data across all instances.|
|**Declaration**|synchronized void instanceMethod()|static synchronized void staticMethod()|
|**Uses**|It is commonly used.|It is not widely used.|
|**Instances**|In synchronization, for each object, a new instance is created.|In static synchronization, for the entire program, there is only one instance.|