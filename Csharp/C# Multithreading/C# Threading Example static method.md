#
We can call static and non-static methods on the execution of the thread. To call the static and non-static methods, you need to pass method name in the constructor of ThreadStart class. For static method, we don't need to create the instance of the class. You can refer it by the name of class.

[](https://www.tpointtech.com/c-sharp-threading-example#)[](https://www.tpointtech.com/c-sharp-threading-example#)[](https://www.tpointtech.com/c-sharp-threading-example#)

1. using System;  
2. using System.Threading;  
3. public class MyThread  
4. {  
5.     public static void Thread1()  
6.     {  
7.         for (int i = 0; i < 10; i++)  
8.         {  
9.             Console.WriteLine(i);  
10.         }  
11.     }  
12. }  
13. public class ThreadExample  
14. {  
15.     public static void Main()  
16.     {  
17.         Thread t1 = new Thread(new ThreadStart(MyThread.Thread1));  
18.         Thread t2 = new Thread(new ThreadStart(MyThread.Thread1));  
19.         t1.Start();  
20.         t2.Start();  
21.     }  
22. }  

Output:

The output of the above program can be anything because there is context switching between the threads.

0
1
2
3
4
5
0
1
2
3
4
5
6
7
8
9
6
7
8
9

### C# Threading Example: non-static method

For non-static method, you need to create instance of the class so that you can refer it in the constructor of ThreadStart class.

[](https://www.tpointtech.com/c-sharp-threading-example#)[](https://www.tpointtech.com/c-sharp-threading-example#)[](https://www.tpointtech.com/c-sharp-threading-example#)

1. using System;  
2. using System.Threading;  
3. public class MyThread  
4. {  
5.     public void Thread1()  
6.     {  
7.         for (int i = 0; i < 10; i++)  
8.         {  
9.             Console.WriteLine(i);  
10.         }  
11.     }  
12. }  
13. public class ThreadExample  
14. {  
15.     public static void Main()  
16.     {  
17.         MyThread mt = new MyThread();  
18.         Thread t1 = new Thread(new ThreadStart(mt.Thread1));  
19.         Thread t2 = new Thread(new ThreadStart(mt.Thread1));  
20.         t1.Start();  
21.         t2.Start();  
22.     }  
23. }  

Output:

Like above program output, the output of this program can be anything because there is context switching between the threads.

0
1
2
3
4
5
0
1
2
3
4
5
6
7
8
9
6
7
8
9

### C# Threading Example: performing different tasks on each thread

Let's see an example where we are executing different methods on each thread.

[](https://www.tpointtech.com/c-sharp-threading-example#)[](https://www.tpointtech.com/c-sharp-threading-example#)[](https://www.tpointtech.com/c-sharp-threading-example#)

1. using System;  
2. using System.Threading;  

3. public class MyThread  
4. {  
5.     public static void Thread1()  
6.     {  
7.         Console.WriteLine("task one");  
8.     }  
9.     public static void Thread2()  
10.     {  
11.         Console.WriteLine("task two");  
12.     }  
13. }  
14. public class ThreadExample  
15. {  
16.     public static void Main()  
17.     {  
18.         Thread t1 = new Thread(new ThreadStart(MyThread.Thread1));  
19.         Thread t2 = new Thread(new ThreadStart(MyThread.Thread2));  
20.         t1.Start();  
21.         t2.Start();  
22.     }  
23. }  

Output:

task one
task two