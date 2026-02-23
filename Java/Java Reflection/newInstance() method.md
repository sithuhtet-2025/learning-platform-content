The **newInstance()** method of **Class** class and **Constructor** class is used to create a new instance of the class.

The newInstance() method of Class class can invoke zero-argument constructor, whereas newInstance() method of Constructor class can invoke any number of arguments. So, Constructor class is preferred over Class class.

### Syntax of newInstance() method of Class class

**public T newInstance()throws InstantiationException,IllegalAccessException**

Here T is the generic version. You can think of it as Object class. You will learn about generics later.

### newInstance() Method Example-1

Let's see the simple example to use newInstance() method.

**FileName:** Test.java

[](https://www.tpointtech.com/new-instance\(\)-method#)[](https://www.tpointtech.com/new-instance\(\)-method#)[](https://www.tpointtech.com/new-instance\(\)-method#)

1. class Simple{  
2.  void message(){System.out.println("Hello Java");}  
3. }  

4. class Test{  
5.  public static void main(String args[]){  
6.   try{  
7.   Class c=Class.forName("Simple");  
8.   Simple s=(Simple)c.newInstance();  
9.   s.message();  

10.   }catch(Exception e){System.out.println(e);}  

11.  }  
12. }  

**Output:**

Hello java

### newInstance() method Example-2

We have learned in the introductory part of this topic that the newInstance() method of the Class class can only invoke the parameterless constructor. Let's understand the same with the help of an example.

**FileName:** ReflectionExample1.java

[](https://www.tpointtech.com/new-instance\(\)-method#)[](https://www.tpointtech.com/new-instance\(\)-method#)[](https://www.tpointtech.com/new-instance\(\)-method#)

1. // important import statements  
2. import static java.lang.System.out;  
3. import java.lang.reflect.*;  
4. import javax.swing.*;  

5. public class ReflectionExample1  
6. {  
7. // Allowing Java Virtual Machine to handle the ClassNotFoundException  
8. // main method  
9. public static void main(String argvs[]) throws ClassNotFoundException  
10. {  

11. Object ob = null;  
12. Class classDefinition = Class.forName("javax.swing.JLabel");  
13. ob = classDefinition.newInstance();  

14. // instance variable for holding the instance of the class  
15. JLabel l1;  

16. // checking whether the created object ob is  
17. // the instance of JLabel or not.  
18. // If yes, do the typecasting; otherwise, terminate the method  
19. if(ob instanceof JLabel)  
20. {  
21. l1 = (JLabel)ob;  
22. }  
23. else  
24. {  
25. return;  
26. }  

27. // reaching here means the typecasting has been done  
28. // now we can invoke the getText() method  
29. out.println(l1.getText());  

30. }  
31. }  

**Output:**

/ReflectionExample1.java:15: error: unreported exception InstantiationException; must be caught or declared to be thrown
ob = classDefinition.newInstance();
^
Note: /ReflectionExample1.java uses or overrides a deprecated API.
Note: Recompile with -Xlint:deprecation for details.
1 error

**Explanation:** The newInstance() method of the Class class only invokes the zero-argument constructor. However, we need to invoke the non-zero argument constructor for that, we need to use the newInstance() method of the class Constructor.

The following program shows how one can use the newInstance() method of the class Constructor to avoid the exception that has come in the above example.

**FileName:** ReflectionExample2.java

[](https://www.tpointtech.com/new-instance\(\)-method#)[](https://www.tpointtech.com/new-instance\(\)-method#)[](https://www.tpointtech.com/new-instance\(\)-method#)

1. // important import statements  
2. import static java.lang.System.out;  
3. import java.lang.reflect.*;  
4. import javax.swing.*;  

5. public class ReflectionExample2  
6. {  
7. // main method  
8. public static void main(String argvs[])   
9. {  
10. try   
11. {  
12. Class[] t = { String.class };  
13. Class classDef = Class.forName("javax.swing.JLabel");   

14. // getting the constructor  
15. Constructor cons = classDef.getConstructor(t);  

16. // setting the label  
17. Object[] objct = { "My JLabel in Reflection."};  

18. // getting the instance by invoking the correct constructor this time  
19. Object ob = cons.newInstance(objct);  

20. // instance variable for holding the instance of the class  
21. JLabel l1;  

22. // checking whether the created object ob is  
23. // the instance of JLabel or not.  
24. // If yes, do the typecasting; otherwise, exit from the method  
25. if(ob instanceof JLabel)  
26. {  
27. l1 = (JLabel)ob;  
28. }  
29. else  
30. {  
31. // exiting from the method using the return statement  
32. return;  
33. }  

34. // if the control reaches here, then it means the typecasting has been done  
35. // now we can print the label of the JLabel instance  
36. out.println(l1.getText());  
37. }  
38. // relevant catch block for handling the raised exceptions.  
39. catch (InstantiationException ie)   
40. {  
41. out.println(ie);  
42. }   
43. catch (IllegalAccessException ie)   
44. {  
45. System.out.println(ie);  
46. }    

47. catch (InvocationTargetException ie)   
48. {  
49. out.println(ie);  
50. }  
51. catch (ClassNotFoundException e)   
52. {  
53. out.println(e);  
54. }  

55. catch (NoSuchMethodException e)   
56. {  
57. out.println(e);  
58. }  
59. }  
60. }  

**Output:**

My JLabel in Reflection.