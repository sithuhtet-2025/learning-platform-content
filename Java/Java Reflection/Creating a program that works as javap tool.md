Following methods of **java.lang.Class** class can be used to display the metadata of a class.

|Method|Description|
|---|---|
|public Field[] getDeclaredFields()throws SecurityException|returns an array of Field objects reflecting all the fields declared by the class or interface represented by this Class object.|
|public Constructor[] getDeclaredConstructors()throws SecurityException|returns an array of Constructor objects reflecting all the constructors declared by the class represented by this Class object.|
|public Method[] getDeclaredMethods()throws SecurityException|returns an array of Method objects reflecting all the methods declared by the class or interface represented by this Class object.|

### Example of creating javap tool

Let's create a program that works like javap tool.

[](https://www.tpointtech.com/creating-javap-tool#)[](https://www.tpointtech.com/creating-javap-tool#)[](https://www.tpointtech.com/creating-javap-tool#)

1. import java.lang.reflect.*;  

2. public class MyJavap{  
3.    public static void main(String[] args)throws Exception {  
4.     Class c=Class.forName(args[0]);  

5.     System.out.println("Fields........");  
6.     Field f[]=c.getDeclaredFields();  
7.     for(int i=0;i<f.length;i++)  
8.         System.out.println(f[i]);  

9.     System.out.println("Constructors........");  
10.     Constructor con[]=c.getDeclaredConstructors();  
11.     for(int i=0;i<con.length;i++)  
12.         System.out.println(con[i]);  

13.         System.out.println("Methods........");  
14.     Method m[]=c.getDeclaredMethods();  
15.     for(int i=0;i<m.length;i++)  
16.         System.out.println(m[i]);  
17.    }  
18. }  

At runtime, you can get the details of any class, it may be user-defined or pre-defined class.

### Output:

![creating a program that works like javap tool](https://images.tpointtech.com/images/javapoutput1.JPG) ![creating a program that works like javap tool](https://images.tpointtech.com/images/javapoutput2.JPG)