You can call the private method from outside the class by changing the runtime behaviour of the class.

With the help of **java.lang.Class** class and **java.lang.reflect.Method** class, we can call a private method from any other class.

### Required methods of Method class

**1) public void setAccessible(boolean status) throws SecurityException** sets the accessibility of the method.

**2) public Object invoke(Object method, Object... args) throws IllegalAccessException, IllegalArgumentException, InvocationTargetException** is used to invoke the method.

### Required method of Class class

**1) public Method getDeclaredMethod(String name,Class[] parameterTypes)throws NoSuchMethodException,SecurityException:** returns a Method object that reflects the specified declared method of the class or interface represented by this Class object.

### Example of calling private method from another class

Let's see the simple example to call private method from another class.

File: A.java

[](https://www.tpointtech.com/how-to-call-private-method-from-another-class-in-java#)[](https://www.tpointtech.com/how-to-call-private-method-from-another-class-in-java#)[](https://www.tpointtech.com/how-to-call-private-method-from-another-class-in-java#)

1. public class A {  
2.   private void message(){System.out.println("hello java"); }  
3. }  

File: MethodCall.java

[](https://www.tpointtech.com/how-to-call-private-method-from-another-class-in-java#)[](https://www.tpointtech.com/how-to-call-private-method-from-another-class-in-java#)[](https://www.tpointtech.com/how-to-call-private-method-from-another-class-in-java#)

1. import java.lang.reflect.Method;  
2. public class MethodCall{  
3. public static void main(String[] args)throws Exception{  

4.     Class c = Class.forName("A");  
5.     Object o= c.newInstance();  
6.     Method m =c.getDeclaredMethod("message", null);  
7.     m.setAccessible(true);  
8.     m.invoke(o, null);  
9. }  
10. }  

**Output:**

hello java

### Another example to call parameterized private method from another class

Let's see the example to call parameterized private method from another class

File: A.java

[](https://www.tpointtech.com/how-to-call-private-method-from-another-class-in-java#)[](https://www.tpointtech.com/how-to-call-private-method-from-another-class-in-java#)[](https://www.tpointtech.com/how-to-call-private-method-from-another-class-in-java#)

1. class A{  
2. private void cube(int n){System.out.println(n*n*n);}  
3. }  

File: M.java

[](https://www.tpointtech.com/how-to-call-private-method-from-another-class-in-java#)[](https://www.tpointtech.com/how-to-call-private-method-from-another-class-in-java#)[](https://www.tpointtech.com/how-to-call-private-method-from-another-class-in-java#)

1. import java.lang.reflect.*;  
2. class M{  
3. public static void main(String args[])throws Exception{  
4. Class c=A.class;  
5. Object obj=c.newInstance();  

6. Method m=c.getDeclaredMethod("cube",new Class[]{int.class});  
7. m.setAccessible(true);  
8. m.invoke(obj,4);  
9. }}  

**Output:**

64

### Accessing Private Constructors of a class

We know that constructors of a class are a special kind of method this is used to instantiate the class. To access the private constructor, we use the method getDeclaredConstructor(). The getDeclaredConstructor() is used to access a parameterless as well as a parametrized constructor of a class. The following example shows the same.

**FileName:** PvtConstructorDemo.java

[](https://www.tpointtech.com/how-to-call-private-method-from-another-class-in-java#)[](https://www.tpointtech.com/how-to-call-private-method-from-another-class-in-java#)[](https://www.tpointtech.com/how-to-call-private-method-from-another-class-in-java#)

1. // important import statements  
2. import java.lang.reflect.Constructor;  
3. import java.lang.reflect.Modifier;  
4. import java.lang.reflect.InvocationTargetException;  

5. class Vehicle   
6. {  

7. // private fields of the class Vehicle  
8. private Integer vId;  
9. private String vName;  

10. // parameterless constructor  
11. private Vehicle()  
12. {  

13. }  

14. // parameterized constructor  
15. private Vehicle(Integer vId, String vName)   
16. {  
17.    this.vId = vId;  
18.    this.vName = vName;  
19. }  

20. // setter methods of the class Vehicle  
21. public void setVehicleId(Integer vId)  
22. {  
23.    this.vId = vId;  
24. }  

25. public void setVehicleName(String vName)  
26. {  
27.    this.vName = vName;   
28. }  

29. // getter methods of the class Vehicle  
30. public Integer getVehicleId()   
31. {  
32.    return vId;  
33. }  

34. public String getVehicleName()   
35. {  
36.   return vName;  
37. }  
38. }   

39. public class PvtConstructorDemo   
40. {  
41. // the createObj() method is used to create an object of   
42. // the Vehicle class using the parameterless constructor.   
43. public void craeteObj(int vId, String vName) throws InstantiationException, IllegalAccessException,   
44. IllegalArgumentException, InvocationTargetException, NoSuchMethodException   
45. {  
46. // using the parametereless contructor  
47. Constructor<Vehicle> constt = Vehicle.class.getDeclaredConstructor();  

48. constt.setAccessible(true);  
49. Object obj = constt.newInstance();  
50. if (obj instanceof Vehicle)   
51. {  
52.   Vehicle v = (Vehicle)obj;  
53.    v.setVehicleId(vId);  
54.    v.setVehicleName(vName);  
55.      System.out.println("Vehicle Id: " +  v.getVehicleId());  
56.      System.out.println("Vehicle Name: " +  v.getVehicleName());  
57. }  
58. }  

59. // the craeteObjByConstructorName() method is used to create an object   
60. // of the Vehicle class using the parameterized constructor.   
61. public void craeteObjByConstructorName(int vId, String vName) throws NoSuchMethodException, SecurityException,  
62. InstantiationException, IllegalAccessException, IllegalArgumentException, InvocationTargetException  
63. {  

64. // using the parameterized contructor  
65. Constructor<Vehicle> constt = Vehicle.class.getDeclaredConstructor(Integer.class, String.class);  

66. if (Modifier.isPrivate(constt.getModifiers()))   
67. {  
68. constt.setAccessible(true);  

69. Object obj = constt.newInstance(vId, vName);  
70. if(obj instanceof Vehicle)  
71. {  
72.      Vehicle v = (Vehicle)obj;  
73.      System.out.println("Vehicle Id: " +  v.getVehicleId());  
74.      System.out.println("Vehicle Name: " + v.getVehicleName());  
75. }  
76. }  
77. }     

78. // delegating the responsibility to Java Virtual Machine (JVM) to handle the raised   
79. // exception  
80. // main method  
81. public static void main(String argvs[]) throws InstantiationException,   
82. IllegalAccessException, IllegalArgumentException, InvocationTargetException,   
83. NoSuchMethodException, SecurityException   
84. {  

85.    // creating an object of the class PvtConstructorDemo  
86.    PvtConstructorDemo ob = new PvtConstructorDemo();  
87.    ob.craeteObj(20, "Indica");  
88.    System.out.println(" -------------------------- ");  
89.    ob.craeteObjByConstructorName(30, "Alto");  
90. }  
91. }  

**Output:**

Vehicle Id: 20
Vehicle Name: Indica
--------------------------
Vehicle Id: 30
Vehicle Name: Alto