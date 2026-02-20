In the C# programming language, the Thread.Sleep() method is a static method inside the System.Threading namespace. It pauses the execution of the current thread for a specified duration. The thread does not consume CPU resources, which allows other threads to execute during this pause.

![C# Thread Sleep() Method](https://images.tpointtech.com/csharp/images/c-sharp-thread-sleep.png)

In C#, the Thread.Sleep methods can take an integer value. It represents a millisecond or a TimeSpan object to specify the duration. For Example, Thread.Sleep(1000) means to pause the thread for 1 second, while Thread.Sleep(Timeout.Infinite) can be used to pause the thread indefinitely.

### Syntax of the Thread.Sleep() function in C#

In C#, the Thread.Sleep() method is used to pause the execution of the current thread for a specific duration. It has two main overloads, which have the following syntaxes.

**Using int millisecondsTimeout:**

This parameter takes an integer value that specifies the amount of time for which the thread will pause using a milliseconds object.

[](https://www.tpointtech.com/c-sharp-thread-sleep#)[](https://www.tpointtech.com/c-sharp-thread-sleep#)[](https://www.tpointtech.com/c-sharp-thread-sleep#)

1. Thread.Sleep(int millisecondsTimeout);  

In this syntax,

- **Sleep():** The Thread.Sleep() method is commonly used to pause the execution of the current thread.
- **millisecondsTimeout:** It is an integer value that specifies the number of milliseconds for which the current thread should pause.

**Using Timespan timeout:**

In C#, the TimeSpan parameter specifies the duration of the sleep in the form of a TimeSpan object. It provides better readability because we can specify time in seconds, minutes, hours, or days.

[](https://www.tpointtech.com/c-sharp-thread-sleep#)[](https://www.tpointtech.com/c-sharp-thread-sleep#)[](https://www.tpointtech.com/c-sharp-thread-sleep#)

1. Thread.Sleep(TimeSpan timeout);  

### C# Simple Thread.Sleep() Example using Main Thread

Let us take an example to illustrate the Thread.Sleep() method using the Main Thread in C#.

### Example

[](https://www.tpointtech.com/c-sharp-thread-sleep#)[](https://www.tpointtech.com/c-sharp-thread-sleep#)[](https://www.tpointtech.com/c-sharp-thread-sleep#)

1. using System;  
2. using System.Threading;  
3. class Tpoint  
4. {  
5.     static void Main()  
6.     {  
7.         Console.WriteLine("The Main Thread Starts here");  
8.         // Loop in the main thread  
9.         for (int m = 1; m <= 10; m++)  
10.         {  
11.             Console.WriteLine("The Main Thread Count is " + m);  
12.             Thread.Sleep(1000); // Pause for 1 second  
13.         }  
14.         Console.WriteLine("The Main Thread Ends.");  
15.     }  
16. }  

**Output:**

The Main Thread Starts here
The Main Thread Count is 1
The Main Thread Count is 2
The Main Thread Count is 3
The Main Thread Count is 4
The Main Thread Count is 5
The Main Thread Count is 6
The Main Thread Count is 7
The Main Thread Count is 8
The Main Thread Count is 9
The Main Thread Count is 10
The Main Thread Ends.

**Explanation:**

In this example, we demonstrate the use of the Thread.Sleep() method in C#. It starts by printing a message, and then we use a for loop from 1 to 10 to iterate over each number, where it prints the count and pauses for 1 second using the Thread.Sleep(1000) function. Finally, it displays a message, which indicates that the Main thread has ended.

### C# Thread.Sleep() Example using int millisecondsTimeout

Let us take an example to illustrate the Thread.Sleep() function using the int milliseconds in the [C# programming language](https://www.tpointtech.com/c-sharp-tutorial).

### Example

[](https://www.tpointtech.com/c-sharp-thread-sleep#)[](https://www.tpointtech.com/c-sharp-thread-sleep#)[](https://www.tpointtech.com/c-sharp-thread-sleep#)

1. using System;  
2. using System.Threading;  
3. class Tpoint  
4. {  
5.     static void Main()  
6.     {  
7.         Console.WriteLine("Thread starts...");  
8.         // Pause the thread for 1 second  
9.         Thread.Sleep(1000);  
10.         Console.WriteLine("1 second passed");  
11.         // Pause the thread for 5 seconds   
12.         Thread.Sleep(5000);  
13.         Console.WriteLine("5 seconds passed");  
14.         Console.WriteLine("Thread ends...");  
15.     }  
16. }  

**Output:**

Thread starts...
1 second passed
5 seconds passed
Thread ends...

**Explanation:**

In this example, we demonstrate how the Thread.Sleep(int milliseconds) methods work in C#. First, the program starts by printing "Thread starts...". After that, we use the Thread.Sleep(1000) function and prints the message "1 second passed". Next, we use the Thread.Sleep(5000) function to pause for 5 seconds and prints the message "5 seconds passed". Finally, we print the message "Thread ends...".

### C# Thread.Sleep Example using Timespan Parameter

Let us take an example to illustrate the timespan parameter in Thread.Sleep() method in C#.

### Example

[](https://www.tpointtech.com/c-sharp-thread-sleep#)[](https://www.tpointtech.com/c-sharp-thread-sleep#)[](https://www.tpointtech.com/c-sharp-thread-sleep#)

1. using System;  
2. using System.Threading;  
3. class Tpoint  
4. {  
5.     static void Main()  
6.     {  
7.         Console.WriteLine("Main Thread starts...");  

8.         // Sleep using TimeSpan of 2 seconds  
9.         TimeSpan ts = TimeSpan.FromSeconds(2);  
10.         Thread.Sleep(ts);  
11.         Console.WriteLine("2 seconds passed");  
12.         // Sleep using TimeSpan of 1 minute  
13.         Thread.Sleep(TimeSpan.FromMinutes(1));  
14.         Console.WriteLine("1 minute passed");  
15.     }  
16. }  

**Output:**

Main Thread starts...
2 seconds passed
1 minute passed

**Explanation:**

In this example, we demonstrate how to use the TimeSpan parameter with the Thread.Sleep() method in C#. First, the program starts by printing the message "Main Threads starts...". After that, we use the TimeSpan.FromSeconds(2) to pause the thread for 2 seconds. Next, we use the (TimeSpan.FromMinutes(1)) to pause the thread for 1 minute and print "1 minute passed".

## Features of Thread.Sleep() Method in C#

There are several features of the Thread.Sleep() method in C#. Some main features are as follows:

- In C#, the Thread.Sleep() method is a blocking method, which means that the current thread stops executing for the specified duration.
- It supports two parameters: int millisecondTimeout and Timespan timeout.
- It is a static method of a thread class. It is directly called using the Thread.Sleep() method.
- It saves CPU resources because the sleeping thread does not consume processor time.

## Conclusion

In conclusion, the C# Thread.Sleep() method is a static method inside the System.Threading namespace. It is used to pause the execution of the current thread for a specified time. It has two overloads: int millisecondTimeout and Timespan timeout. It provides a simple way to control the timing and flow of thread execution in C#.