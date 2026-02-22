In this chapter, we will learn about the toString() method in Java, how it is used to represent objects as readable strings, and how overriding it helps in displaying meaningful object information.

## What is toString() Method

The **toString()** method is used to represent an object as a string. It returns the string representation of an object.

When you print an object using System.out.println(), the Java compiler internally calls the **toString()** method on that object. By overriding the **toString()** method, you can return a meaningful output, such as the current state or data of the object, instead of the default class name and hash code.

## Understanding the Problem Without toString() Method

By default, if we print an object in Java, it prints the **reference value** of that object instead of its actual data. This happens because Java internally calls the **toString()** method of the Object class, which returns the class name followed by a hashcode.

### Example

Let us understand this with a simple example:

[](https://www.tpointtech.com/understanding-tostring\(\)-method#)[](https://www.tpointtech.com/understanding-tostring\(\)-method#)[](https://www.tpointtech.com/understanding-tostring\(\)-method#)

1. class Student {  
2.     int rollno;  
3.     String name;  
4.     String city;  

5.     Student(int rollno, String name, String city) {  
6.         this.rollno = rollno;  
7.         this.name = name;  
8.         this.city = city;  
9.     }  

10.     public static void main(String args[]) {  
11.         Student s1 = new Student(101, "Raj", "Lucknow");  
12.         Student s2 = new Student(102, "Vijay", "Ghaziabad");  

13.         System.out.println(s1); // internally calls s1.toString()  
14.         System.out.println(s2); // internally calls s2.toString()  
15.     }  
16. }  

**Output:**

Student@1fee6fc
Student@1eed786

As you can see, printing **s1** and **s2** displays only the class name and hashcode, not the actual values of the object fields. This output is not very useful when we want to see the object’s data.

## How toString() Method Improves Object Output?

To print meaningful information, we can override the toString() method in our class and return the desired object details.

Here is the correct code by overriding the toString() method in our class:

[](https://www.tpointtech.com/understanding-tostring\(\)-method#)[](https://www.tpointtech.com/understanding-tostring\(\)-method#)[](https://www.tpointtech.com/understanding-tostring\(\)-method#)

1. class Student {  
2.     int rollno;  
3.     String name;  
4.     String city;  

5.     Student(int rollno, String name, String city) {  
6.         this.rollno = rollno;  
7.         this.name = name;  
8.         this.city = city;  
9.     }  

10.     // Overriding the toString() method  
11.     public String toString() {  
12.         return rollno + " " + name + " " + city;  
13.     }  

14.     public static void main(String args[]) {  
15.         Student s1 = new Student(101, "Raj", "Lucknow");  
16.         Student s2 = new Student(102, "Vijay", "Ghaziabad");  

17.         System.out.println(s1); // internally calls s1.toString()  
18.         System.out.println(s2); // internally calls s2.toString()  
19.     }  
20. }  

**Output:**

101 Raj lucknow
102 Vijay ghaziabad

**Explanation:**

In this program, the **toString()** method is overridden to return the values of **_rollno_**, **_name_**, and **_city_**. When the object is printed, Java internally calls the overridden **toString()** method, which results in a clear and meaningful output instead of a reference value.