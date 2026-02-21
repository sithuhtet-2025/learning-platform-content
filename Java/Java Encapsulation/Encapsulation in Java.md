Encapsulation in Java is an important concept in object-oriented programming that helps protect data and restrict direct access to class members. In this chapter, we will learn how encapsulation works and how access modifiers are used to achieve it.

## What is Encapsulation in Java?

**Encapsulation** is the process of wrapping data and code (methods) together into a single unit. A capsule is a good example of encapsulation because it contains a mixture of several medicines in one unit.

We can create a fully encapsulated class by making all the data members **private**. After that, we provide **setter** and **getter** methods to set and access the data safely. This hides the implementation (controlled access) and protects the data from unwanted modification.

![encapsulation in java](https://images.tpointtech.com/core/images/encapsulation-in-java.png)

We can create a fully encapsulated class in Java by making all the data members of the class **private**. Now we can use setter and getter methods to set and get the data in it.

## Why Use Encapsulation in Java?

The following are the important reasons to use the encapsulation:

- Encapsulation helps to protect data and control access to it.
- It protects sensitive data from being access directly.
- It hides unnecessary data from the user of a class, and only shows the functionality of a class.
- Changes can be made internally without affecting the external interface.
- It is easier to scale applications because it provides flexibility to add or modify features without impacting the entire codebase.
- Encapsulated classes can be reused across projects.

## Example of Encapsulation

Let's see an example of encapsulation using a class with a single field and its setter and getter methods.

### Fully Encapsulated Class

Here, we have **Student** class with a private **name** field and public **getName()** and **setName()** methods.

[](https://www.tpointtech.com/encapsulation-in-java#)[](https://www.tpointtech.com/encapsulation-in-java#)[](https://www.tpointtech.com/encapsulation-in-java#)

1. //A Java class which is a fully encapsulated class.    
2. //It has a private data member and getter and setter methods.    
3. package com.tpointtech;    
4. public class Student{    
5. //private data member    
6. private String name;    
7. //getter method for name    
8. public String getName(){    
9. return name;    
10. }    
11. //setter method for name    
12. public void setName(String name){    
13. this.name=name    
14. }    
15. }    

### Test Class

Here, we have **Main** class that creates a **Student** object, sets the **nam**e, and prints it.

### Example

[](https://www.tpointtech.com/encapsulation-in-java#)[](https://www.tpointtech.com/encapsulation-in-java#)[](https://www.tpointtech.com/encapsulation-in-java#)

1. //A Java class to test the encapsulated class.    
2. package com.tpointtech;    
3. class Main {    
4. public static void main(String[] args) {    
5. //creating an instance of the encapsulated class    
6. Student s=new Student();    
7. //setting value in the name member    
8. s.setName("vijay");    
9. //getting value of the name member    
10. System.out.println(s.getName());    
11. }    
12. }    

**Output:**

vijay

### Read-Only Class

The **Student** class with a private **college** field and only a **getCollege()** method.

In this class, the value of college cannot be changed from outside the class.

[](https://www.tpointtech.com/encapsulation-in-java#)[](https://www.tpointtech.com/encapsulation-in-java#)[](https://www.tpointtech.com/encapsulation-in-java#)

1. //A Java class which has only getter methods.  
2. public class Student{  
3. //private data member  
4. private String college="AKG";  
5. //getter method for college  
6. public String getCollege(){  
7. return college;  
8. }  
9. }  

Now, you cannot change the value of the college data member, which is "AKG".

[](https://www.tpointtech.com/encapsulation-in-java#)[](https://www.tpointtech.com/encapsulation-in-java#)[](https://www.tpointtech.com/encapsulation-in-java#)

1. s.setCollege("KITE");//will render compile time error  

### Write-Only Class

The **Student** class with a private **college** field and only a **setCollege()** method.

[](https://www.tpointtech.com/encapsulation-in-java#)[](https://www.tpointtech.com/encapsulation-in-java#)[](https://www.tpointtech.com/encapsulation-in-java#)

1. //A Java class which has only setter methods.  
2. public class Student{  
3. //private data member  
4. private String college;  
5. //getter method for college  
6. public void setCollege(String college){  
7. this.college=college;  
8. }  
9. }  

In this class, you can set the value of college, but you cannot read it from outside:

Now, you cannot get the value of the college; you can only change the value of the college data member.

[](https://www.tpointtech.com/encapsulation-in-java#)[](https://www.tpointtech.com/encapsulation-in-java#)[](https://www.tpointtech.com/encapsulation-in-java#)

1. System.out.println(s.getCollege());//Compile Time Error, because there is no such method  
2. System.out.println(s.college);//Compile Time Error, because the college data member is private.   
3. //So, it can't be accessed from outside the class  

The data member is private, so it cannot be accessed directly from outside the class.

## Real-Life Example of Encapsulation

The following example demonstrates how encapsulation works in a real-life scenario using a bank account. All data members are private, and access is provided through public getter and setter methods.

### Code

[](https://www.tpointtech.com/encapsulation-in-java#)[](https://www.tpointtech.com/encapsulation-in-java#)[](https://www.tpointtech.com/encapsulation-in-java#)

1. //A Account class, which is a fully encapsulated class.      
2. //It has a private data member and getter and setter methods.      
3. class Account {      
4. //private data members      
5. private long acc_no;      
6. private String name,email;      
7. private float amount;      
8. //public getter and setter methods      
9. public long getAcc_no() {      
10.     return acc_no;      
11. }      
12. public void setAcc_no(long acc_no) {      
13.     this.acc_no = acc_no;      
14. }      
15. public String getName() {      
16.     return name;      
17. }      
18. public void setName(String name) {      
19.     this.name = name;      
20. }      
21. public String getEmail() {      
22.     return email;      
23. }      
24. public void setEmail(String email) {      
25.     this.email = email;      
26. }      
27. public float getAmount() {      
28.     return amount;      
29. }      
30. public void setAmount(float amount) {      
31.     this.amount = amount;      
32. }      
33. }      
34. //A Java class to test the encapsulated class Account.      
35. public class Main {      
36. public static void main(String[] args) {      
37.     //creating instance of Account class      
38.     Account acc=new Account();      
39.     //setting values through setter methods      
40.     acc.setAcc_no(7560504000L);      
41.     acc.setName("Sonoo Jaiswal");      
42.     acc.setEmail("sonoojaiswal@tpointtech.com");      
43.     acc.setAmount(500000f);      
44.     //getting values through getter methods      
45.     System.out.println(acc.getAcc_no()+" "+acc.getName()+" "+acc.getEmail()+" "+acc.getAmount());      
46. }      
47. }   

**Output:**

7560504000 Sonoo Jaiswal sonoojaiswal@tpointtech.com 500000.0

The Java Bean class is an example of a fully encapsulated class.

## Advantages of Encapsulation in Java

Encapsulation offers various advantages, especially ensuring code organization and better design.

1. **Data Protection:** Encapsulation restricts direct access to fields of a class, preserving the integrity of data by allowing controlled access through getter and setter methods.
2. **Enhanced Security:** By hiding internal implementation details and exposing only necessary functionality, encapsulation makes code less vulnerable to unintended interference and misuse.
3. **Improved Maintainability:** Changes to implementation can be made without affecting external code, as long as the public interface remains consistent.
4. **Increased Flexibility:** Encapsulation allows developers to modify or extend the behavior of objects without altering the code that uses them.
5. **Encourages Modularity:** Encapsulation helps in dividing the program into distinct modules, making it easier to debug and test.
6. **Promotes Abstraction:** It simplifies how data is handled by hiding unnecessary details from users of a class.

## Disadvantages of Encapsulation in Java

Several disadvantages of Encapsulation in Java are as follows:

1. **Increase Code Complexity:** It increases code complexity due to the getter and setter methods for every field. It leads to longer code.
2. **Decrease Performance:** It decreases performance by invoking the getter and setter methods instead of directly accessing variables. It may have a slight impact on performance.
3. **Impractical for Small-Scale Programs:** In small-scale applications, implementing encapsulation might feel excessive or unnecessary.
4. **Mismanagement of Setters and Getters:** Poorly implemented getter and setter methods can disrupt the concept of encapsulation if they expose too much or allow unintended behavior.
5. **Learning Curve:** It can be challenging for bingers because understanding and correctly applying encapsulation may slow down initial progress.