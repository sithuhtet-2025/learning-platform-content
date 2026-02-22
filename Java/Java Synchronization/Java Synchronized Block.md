In this chapter, you will learn what a synchronized block is, why it is used, and how to implement it with practical examples.

## What is a Synchronized Block?

A synchronized block is used to synchronize a **specific portion of code** instead of synchronizing the entire method. It allows better control over shared resources and improves performance by reducing the scope of synchronization.

For a given object, only one [thread](https://www.tpointtech.com/threads-in-java) can execute the synchronized block at a time and excessive use of [synchronization](https://www.tpointtech.com/synchronization-in-java) may impact application performance. Overall, synchronized blocks are generally more efficient than synchronized methods due to their limited scope.

### Need of Synchronized Block

Sometimes, a method may contain many lines of code, but only a few of them need synchronization. In such cases, using a synchronized block is more efficient than synchronizing the entire method. If all the code inside a method is placed within a synchronized block, it behaves the same as a synchronized method.

## Syntax

To create/define a synchronized block, you need to use the "synchronized" keyword. Here is the syntax to define a synchronized block:

[](https://www.tpointtech.com/java-synchronized-block#)[](https://www.tpointtech.com/java-synchronized-block#)[](https://www.tpointtech.com/java-synchronized-block#)

1. synchronized (objectReference) {  
2.     // critical section  
3. }  

## Example of Synchronized Block

Consider this example, where only a specific part of the method is synchronized to prevent [multiple threads](https://www.tpointtech.com/multithreading-in-java) from accessing the shared resource simultaneously.

### Example

[](https://www.tpointtech.com/java-synchronized-block#)[](https://www.tpointtech.com/java-synchronized-block#)[](https://www.tpointtech.com/java-synchronized-block#)

1. class Table {      
2.     void printTable(int n) {        
3.         synchronized (this) { // synchronized block        
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

15. class MyThread1 extends Thread {        
16.     Table t;        
17.     MyThread1(Table t) {        
18.         this.t = t;        
19.     }        
20.     public void run() {        
21.         t.printTable(5);        
22.     }        
23. }        

24. class MyThread2 extends Thread {        
25.     Table t;        
26.     MyThread2(Table t) {        
27.         this.t = t;        
28.     }        
29.     public void run() {        
30.         t.printTable(100);        
31.     }        
32. }        

33. public class Main {        
34.     public static void main(String args[]) {        
35.         Table obj = new Table();        
36.         MyThread1 t1 = new MyThread1(obj);        
37.         MyThread2 t2 = new MyThread2(obj);        
38.         t1.start();        
39.         t2.start();        
40.     }        
41. }       

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

## Synchronized Block Using Anonymous Class

This approach uses a synchronized block inside a method while creating threads through anonymous classes. It reduces code length and ensures that only one thread at a time can access the shared resource.

### Example

In this example, the threads are created using anonymous classes to reduce code length while still ensuring thread safety.

[](https://www.tpointtech.com/java-synchronized-block#)[](https://www.tpointtech.com/java-synchronized-block#)[](https://www.tpointtech.com/java-synchronized-block#)

1. //Creating a class which containse synchronized block within method  
2. class Table    
3. {        
4.  void printTable(int n){      
5.    synchronized(this){//synchronized block      
6.      for(int i=1;i<=5;i++){      
7.       System.out.println(n*i);      
8.       try{      
9.        Thread.sleep(400);      
10.       }catch(Exception e){System.out.println(e);}      
11.      }      
12.    }      
13.  }//end of the method      
14. }      

15. //Creating Main class to create and start threads  
16. public class Main{      
17.  public static void main(String args[]){      
18.   final Table obj = new Table();//only one object      
19.   Thread t1=new Thread(){  
20.     public void run(){      
21.       obj.printTable(5);      
22.     }   
23.   };  
24.   Thread t2=new Thread(){  
25.     public void run(){      
26.       obj.printTable(100);      
27.     }   
28.   };  
29.   t1.start();      
30.   t2.start();      
31.  }      
32. }      

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

## Message Passing Example using Synchronized Block

In this concept, a synchronized block is used to allow only one thread to send or process a message at a time, ensuring ordered execution and preventing message interference between threads.

### Example

In this example, a synchronized block ensures that only one thread sends a message at a time.

[](https://www.tpointtech.com/java-synchronized-block#)[](https://www.tpointtech.com/java-synchronized-block#)[](https://www.tpointtech.com/java-synchronized-block#)

1. // A Sender class    
2. class Sender     
3. {     
4.   public void SenderMsg(String msg)    
5.   {     
6.     System.out.println("Sending a Message: "  + msg);    
7.     try    
8.     {     
9.       Thread.sleep(800);     
10.     }     
11.     catch (Exception e)     
12.     {     
13.       System.out.println("Thread interrupted.");     
14.     }     
15.     System.out.println(msg+ "Sent");    
16.   }    
17. }     
18. // A Sender class for sending a message using Threads     
19. class SenderThread extends Thread     
20. {     
21.   private String msg;     
22.   Sender sd;     

23.   // Receiver method to receive a message object and a message to be sent     
24.   SenderThread(String m, Sender obj)    
25.   {     
26.     msg = m;    
27.     sd = obj;     
28.   }     

29.   public void run()     
30.   {     
31.     // Checks that only one thread sends a message at a time.     
32.     synchronized(sd)     
33.     {     
34.       // synchronizing the sender object     
35.       sd.SenderMsg(msg);    
36.     }     
37.   }     
38. }     
39. // Creating a main class     
40. public class Main  
41. {     
42.   public static void main(String args[])     
43.   {     
44.     Sender sender = new Sender();     
45.     SenderThread sender1 = new SenderThread("Hola " , sender);    
46.     SenderThread sender2 =  new SenderThread("Welcome to TpointTech website ", sender);    

47.     sender1.start();     
48.     sender2.start();     

49.     // wait for threads to end     
50.     try    
51.     {     
52.       sender1.join();     
53.       sender2.join();     
54.     }     
55.     catch(Exception e)     
56.     {     
57.       System.out.println("Interrupted");     
58.     }     
59.   }     
60. }    

**Output:**

Sending a Message: Hola
Hola Sent
Sending a Message: Welcome to TpointTech website
Welcome to TpointTech website Sent