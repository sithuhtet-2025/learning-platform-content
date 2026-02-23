In Java, Comparable and Comparator both are interfaces used to sort objects. Comparable is used for defining the natural ordering of the objects within the class. Comparator is used for externally defining the custom sorting logic.

## Comparable Interface

- It defines **natural ordering** within a class.
- It is implemented **inside** the class being sorted.
- It uses the compareTo() method.
- It allows sorting **by one**.
- It allows sorting in a single order. In other words, multiple criteria are not allowed to do the sorting.

**To read more:** [Comparable Interface](https://www.tpointtech.com/comparable-interface-in-java)

### Example: Comparable Interface

Let's see the example of a Comparable interface that sorts the list elements on the basis of age.

### Example

[](https://www.tpointtech.com/difference-between-comparable-and-comparator#)[](https://www.tpointtech.com/difference-between-comparable-and-comparator#)[](https://www.tpointtech.com/difference-between-comparable-and-comparator#)

1. //Java Program to demonstrate the use of Java Comparable.      
2. //Creating a class which implements Comparable Interface      
3. import java.util.*;  
4. class Student implements Comparable<Student> {  
5.     int rollno;  
6.     String name;  
7.     int age;  
8.     Student(int rollno, String name, int age) {  
9.         this.rollno = rollno;  
10.         this.name = name;  
11.         this.age = age;  
12.     }  
13.     public int compareTo(Student st) {  
14.         if (age == st.age)  
15.             return 0;  
16.         else if (age > st.age)  
17.             return 1;  
18.         else  
19.             return -1;  
20.     }  
21. }  
22. //Creating a test class to sort the elements      
23. public class Main {  
24.     public static void main(String args[]) {  
25.         ArrayList<Student> al = new ArrayList<Student>();  
26.         al.add(new Student(101, "Peter", 23));  
27.         al.add(new Student(106, "Andrew", 27));  
28.         al.add(new Student(105, "John", 21));  
29.         Collections.sort(al);  
30.         for (Student st : al) {  
31.             System.out.println(st.rollno + " " + st.name + " " + st.age);  
32.         }  
33.     }  
34. }  

**Output:**

105 John 21
101 Peter 23
106 Andrew 27

## Comparator Interface

- It defines **custom sorting logic.**
- It is implemented **in a separate class**or using lambda expressions.
- It uses the compare() method.
- It allows sorting **by multiple criteria**.

**To read more:** [Comparator Interface](https://www.tpointtech.com/java-comparator)

### Example: Comparator Interface

Let's see an example of the Java Comparator interface where we are sorting the elements of a list using different comparators.

### Example

[](https://www.tpointtech.com/difference-between-comparable-and-comparator#)[](https://www.tpointtech.com/difference-between-comparable-and-comparator#)[](https://www.tpointtech.com/difference-between-comparable-and-comparator#)

1. import java.util.*;  
2. class Student {  
3.     int rollno;  
4.     String name;  
5.     int age;  
6.     Student(int rollno, String name, int age) {  
7.         this.rollno = rollno;  
8.         this.name = name;  
9.         this.age = age;  
10.     }  
11. }  
12. class AgeComparator implements Comparator<Student> {  
13.     public int compare(Student s1, Student s2) {  
14.         if (s1.age == s2.age)  
15.             return 0;  
16.         else if (s1.age > s2.age)  
17.             return 1;  
18.         else  
19.             return -1;  
20.     }  
21. }  
22. class NameComparator implements Comparator<Student> {  
23.     public int compare(Student s1, Student s2) {  
24.         return s1.name.compareTo(s2.name);  
25.     }  
26. }  
27. public class Main {  
28.     public static void main(String args[]) {  
29. //Creating a list of students      
30.         ArrayList<Student> al = new ArrayList<Student>();  
31.         al.add(new Student(101, "Peter", 23));  
32.         al.add(new Student(106, "Andrew", 27));  
33.         al.add(new Student(105, "Jack", 21));  
34.         System.out.println("Sorting by Name");  
35. //Using NameComparator to sort the elements      
36.         Collections.sort(al, new NameComparator());  
37. //Traversing the elements of list      
38.         for (Student st : al) {  
39.             System.out.println(st.rollno + " " + st.name + " " + st.age);  
40.         }  
41.         System.out.println("sorting by Age");  
42. //Using AgeComparator to sort the elements      
43.         Collections.sort(al, new AgeComparator());  
44. //Traversing the list again      
45.         for (Student st : al) {  
46.             System.out.println(st.rollno + " " + st.name + " " + st.age);  
47.         }  
48.     }  
49. }  

**Output:**

Sorting by Name
106 Andrew 27
105 Jack 21
101 Peter 23
sorting by Age
105 Jack 21
101 Peter 23
106 Andrew 27

## Difference Between Comparable and Comparator

However, there are many differences between Comparable and Comparator interfaces that are given in the following below.

|Comparable|Comparator|
|---|---|
|It is introduced in Java 1.2.|Introduced in Java 1.2, enhanced in Java 8 with default methods and lambdas.|
|**Syntax:** class Student implements Comparable<Student> { public int compareTo(Student s) { ... } }|**Syntax:** class StudentComparator implements Comparator<Student> { public int compare(Student s1, Student s2) { ... } }|
|Comparable provides a **single sorting sequence**. In other words, we can sort the collection on the basis of a single element such as id, name, and price.|The Comparator provides **multiple sorting sequences**. In other words, we can sort the collection on the basis of multiple elements such as id, name, and price etc.|
|Comparable **affects the original class**, i.e., the actual class is modified.|Comparator **does not affect the original class**, i.e., the actual class is not modified.|
|Comparable provides **compareTo() method** to sort elements.|Comparator provides **compare() method** to sort elements.|
|Comparable is present in **java.lang** package.|A Comparator is present in the **java.util** package.|
|We can sort the list elements of Comparable type by **Collections.sort(List)** method.|We can sort the list elements of Comparator type by **Collections.sort(List, Comparator)** method.|
|Comparable is used when the class is having natural/default ordering.|Comparator is used when we need customized sorting or different sorting sequences.|
|Only one compareTo() method can be implemented, restricting flexibility.|Multiple Comparator classes or lambda expressions can be written to achieve different sorting strategies.|
|It is suitable for default sorting like String, Integer, etc.|It is suitable when objects need to be sorted in different ways, like ascending/descending or by multiple fields.|
|Comparable is implemented by the class whose instances are to be sorted.|Comparator is implemented in a separate class or passed as an anonymous class/lambda to the sort method.|
|Difficult to change ordering once implemented in class.|Easy to switch sorting logic by passing a different Comparator.|

## Java Comparable Example

Let's see the example of a Comparable interface that sorts the list elements on the basis of age.