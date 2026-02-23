The **javap command** disassembles a class file. The javap command displays information about the fields, constructors and methods present in a class file.

### Syntax to use javap tool

Let's see how to use javap tool or command.

[](https://www.tpointtech.com/understanding-javap-tool#)[](https://www.tpointtech.com/understanding-javap-tool#)[](https://www.tpointtech.com/understanding-javap-tool#)

1. javap fully_class_name  

### Example to use javap tool

[](https://www.tpointtech.com/understanding-javap-tool#)[](https://www.tpointtech.com/understanding-javap-tool#)[](https://www.tpointtech.com/understanding-javap-tool#)

1. javap java.lang.Object  

**Output:**

Compiled from "Object.java"
public class java.lang.Object {
public java.lang.Object();
public final native java.lang.Class<?> getClass();
public native int hashCode();
public boolean equals(java.lang.Object);
protected native java.lang.Object clone() throws java.lang.CloneNotSupportedException;
public java.lang.String toString();
public final native void notify();
public final native void notifyAll();
public final native void wait(long) throws java.lang.InterruptedException;
public final void wait(long, int) throws java.lang.InterruptedException;
public final void wait() throws java.lang.InterruptedException;
protected void finalize() throws java.lang.Throwable;
static {};
}

### Another example to use javap tool for your class

Let's use the javap command for our java file.

**FileName:** Simple.java

[](https://www.tpointtech.com/understanding-javap-tool#)[](https://www.tpointtech.com/understanding-javap-tool#)[](https://www.tpointtech.com/understanding-javap-tool#)

1. class Simple{  
2. public static void main(String args[]){  
3. System.out.println("hello java");  
4. }  
5. }  

Now let's use the javap tool to disassemble the class file.

[](https://www.tpointtech.com/understanding-javap-tool#)[](https://www.tpointtech.com/understanding-javap-tool#)[](https://www.tpointtech.com/understanding-javap-tool#)

1. javap Simple  

**Output:**

Compiled from "Simple.java"
class Simple {
Simple();
public static void main(java.lang.String[]);
}

### javap -c command

You can use the javap -c command to see disassembled code. The code that reflects the java bytecode.

[](https://www.tpointtech.com/understanding-javap-tool#)[](https://www.tpointtech.com/understanding-javap-tool#)[](https://www.tpointtech.com/understanding-javap-tool#)

1. javap -c Simple  

**Output:**

Compiled from "Simple.java"
class Simple {
Simple();
Code:
0: aload_0
1: invokespecial #1 // Method java/lang/Object."":()V
4: return

public static void main(java.lang.String[]);
Code:
0: getstatic #2 // Field java/lang/System.out:Ljava/io/PrintStream;
3: ldc #3 // String hello java
5: invokevirtual #4 // Method java/io/PrintStream.println:(Ljava/lang/String;)V
8: return
}

## Options of javap tool

The important options of javap tool are as follows.

|Option|Description|
|---|---|
|-help|prints the help message.|
|-l|prints line number and local variable|
|-c|disassembles the code|
|-s|prints internal type signature|
|-sysinfo|shows system info (path, size, date, MD5 hash)|
|-constants|shows static final constants|
|-version|shows version information|

Let's see how one can use these options with the help of an example. For the following file (ABC.java) we will use the above-mentioned options.

**FileName:** ABC.java

[](https://www.tpointtech.com/understanding-javap-tool#)[](https://www.tpointtech.com/understanding-javap-tool#)[](https://www.tpointtech.com/understanding-javap-tool#)

1. public class ABC  
2. {  
3. // main method  
4. public static void main(String argvs[])  
5. {  
6. // declaring an integer array  
7. int arr[] = {6, 7, 8, 6, 8, 0, 4};  

8. // caculating size of the array  
9. int size = arr.length;  

10. // printing size of the array  
11. System.out.println("The size of the array is " + size );  

12. System.out.println("The 8th index of the array is " + arr[8] );  

13. }  
14. }  

**Command:** javap -c ABC

**Output:**

Compiled from "ABC.java"
public class ABC {
public ABC();
Code:
0: aload_0
1: invokespecial #1 // Method java/lang/Object."":()V
4: return

public static void main(java.lang.String[]);
Code:
0: bipush 7
2: newarray int
4: dup
5: iconst_0
6: bipush 6
8: iastore
9: dup
10: iconst_1
11: bipush 7
13: iastore
14: dup
15: iconst_2
16: bipush 8
18: iastore
19: dup
20: iconst_3
21: bipush 6
23: iastore
24: dup
25: iconst_4
26: bipush 8
28: iastore
29: dup
30: iconst_5
31: iconst_0
32: iastore
33: dup
34: bipush 6
36: iconst_4
37: iastore
38: astore_1
39: aload_1
40: arraylength
41: istore_2
42: getstatic #7 // Field java/lang/System.out:Ljava/io/PrintStream;
45: iload_2
46: invokedynamic #13, 0 // InvokeDynamic #0:makeConcatWithConstants:(I)Ljava/lang/String;
51: invokevirtual #17 // Method java/io/PrintStream.println:(Ljava/lang/String;)V
54: getstatic #7 // Field java/lang/System.out:Ljava/io/PrintStream;
57: aload_1
58: bipush 8
60: iaload
61: invokedynamic #23, 0 // InvokeDynamic #1:makeConcatWithConstants:(I)Ljava/lang/String;
66: invokevirtual #17 // Method java/io/PrintStream.println:(Ljava/lang/String;)V
69: return
}

**Command:** javap -l ABC

**Output:**

Compiled from "ABC.java"
public class ABC {
public ABC();
LineNumberTable:
line 1: 0

public static void main(java.lang.String[]);
LineNumberTable:
line 6: 0
line 9: 39
line 12: 42
line 14: 54
line 16: 69
}

**Command:** javap -s ABC

**Output:**

Compiled from "ABC.java"
public class ABC {
public ABC();
descriptor: ()V

public static void main(java.lang.String[]);
descriptor: ([Ljava/lang/String;)V
}

**Command:** javap -sysinfo ABC

**Output:**

Classfile /C:/Users/Nikhil Kumar/Documents/ABC.class
Last modified Sep 11, 2021; size 970 bytes
SHA-256 checksum 576adf03386399a4691e0ce5b6c5aa5d964b082a1a61299bac5632942e413312
Compiled from "ABC.java"
public class ABC {
public ABC();
public static void main(java.lang.String[]);
}

**Command:** javap -constants ABC

**Output:**

Compiled from "ABC.java"
public class ABC {
public ABC();
public static void main(java.lang.String[]);
}

**Command:** javap -version ABC

**Output:**

14
Compiled from "ABC.java"
public class ABC {
public ABC();
public static void main(java.lang.String[]);
}