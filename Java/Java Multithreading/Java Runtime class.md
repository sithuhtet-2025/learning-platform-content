The **Java Runtime class** is used to interact with the Java runtime environment. It provides methods to execute external processes, invoke garbage collection, and obtain information about total and free memory.

In a Java application, only one instance of the **java.lang.Runtime** class exists. This instance is shared by the entire application.

The **Runtime.getRuntime()** method is used to obtain this **singleton instance** of the Runtime class.

## Importing Runtime Class

The Runtime class belongs to the **java.lang** package. Since this package is imported automatically by Java, no explicit import statement is required to use the Runtime class in a program.

## Constructors of Java Runtime Class

The **java.lang.Runtime** class does not provide any public constructors. This is because the Runtime class follows the **singleton design pattern**.

An object of the Runtime class cannot be created using the [new keyword](https://www.tpointtech.com/new-keyword-in-java). The only way to obtain its instance is by calling the **Runtime.getRuntime() method**, which returns the single Runtime instance associated with the Java application.

## Methods of Java Runtime Class

The following table lists the important methods of the Java Runtime class along with their descriptions.

|Method|Description|
|---|---|
|public static Runtime getRuntime()|returns the instance of Runtime class.|
|public void exit(int status)|terminates the current virtual machine.|
|public void addShutdownHook(Thread hook)|registers new hook thread.|
|public Process exec(String command)throws IOException|executes given command in a separate process.|
|public int availableProcessors()|returns no. of available processors.|
|public long freeMemory()|returns amount of free memory in JVM.|
|public long totalMemory()|returns amount of total memory in JVM.|

## Examples of Runtime Class Methods

The following examples demonstrate how different methods of the Java Runtime class are used in real programs.

### Example 1: Runtime exec() Method

This example shows how to execute an external program using the exec() method.

[](https://www.tpointtech.com/java-runtime-class#)[](https://www.tpointtech.com/java-runtime-class#)[](https://www.tpointtech.com/java-runtime-class#)

1. public class Runtime1{  
2.  public static void main(String args[])throws Exception{  
3.   Runtime.getRuntime().exec("notepad");//will open a new notepad  
4.  }  
5. }  

### Example 2: Shut Down System Using Runtime Class

This example demonstrates how to shut down the system using the shutdown command.

Here you can use -s switch to shutdown system, -r switch to restart system and -t switch to specify time delay.

[](https://www.tpointtech.com/java-runtime-class#)[](https://www.tpointtech.com/java-runtime-class#)[](https://www.tpointtech.com/java-runtime-class#)

1. public class Runtime2{  
2.  public static void main(String args[])throws Exception{  
3.   Runtime.getRuntime().exec("shutdown -s -t 0");  
4.  }  
5. }  

### Example 3: Shut Down Windows System Using Full Path

This example shows how to shut down a Windows system by providing the full path of the shutdown command.

[](https://www.tpointtech.com/java-runtime-class#)[](https://www.tpointtech.com/java-runtime-class#)[](https://www.tpointtech.com/java-runtime-class#)

1. public class Runtime2{  
2.  public static void main(String args[])throws Exception{  
3.   Runtime.getRuntime().exec("c:\\Windows\\System32\\shutdown -s -t 0");  
4.  }  
5. }  

### Example 4: Restart System Using Runtime Class

This example demonstrates how to restart the system using the Runtime class.

[](https://www.tpointtech.com/java-runtime-class#)[](https://www.tpointtech.com/java-runtime-class#)[](https://www.tpointtech.com/java-runtime-class#)

1. public class Runtime3{  
2.  public static void main(String args[])throws Exception{  
3.   Runtime.getRuntime().exec("shutdown -r -t 0");  
4.  }  
5. }  

### Example 5: Using availableProcessors() Method

This example prints the number of processors available to the JVM.

[](https://www.tpointtech.com/java-runtime-class#)[](https://www.tpointtech.com/java-runtime-class#)[](https://www.tpointtech.com/java-runtime-class#)

1. public class Runtime4{  
2.  public static void main(String args[])throws Exception{  
3.   System.out.println(Runtime.getRuntime().availableProcessors());  
4.  }  
5. }  

### Example 6: Using freeMemory() and totalMemory() Methods

This example shows how memory changes before and after garbage collection.

[](https://www.tpointtech.com/java-runtime-class#)[](https://www.tpointtech.com/java-runtime-class#)[](https://www.tpointtech.com/java-runtime-class#)

1. public class MemoryTest{  
2.  public static void main(String args[])throws Exception{  
3.   Runtime r=Runtime.getRuntime();  
4.   System.out.println("Total Memory: "+r.totalMemory());  
5.   System.out.println("Free Memory: "+r.freeMemory());  

6.   for(int i=0;i<10000;i++){  
7.    new MemoryTest();  
8.   }  
9.   System.out.println("After creating 10000 instance, Free Memory: "+r.freeMemory());  
10.   System.gc();  
11.   System.out.println("After gc(), Free Memory: "+r.freeMemory());  
12.  }  
13. }  

**Output:**

Total Memory: 100139008
Free Memory: 99474824
After creating 10000 instance, Free Memory: 99310552
After gc(), Free Memory: 100182832