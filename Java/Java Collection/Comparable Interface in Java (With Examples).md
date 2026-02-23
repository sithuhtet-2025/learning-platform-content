
Java Comparable interface is used to order the objects of the user-defined class. This interface is found in java.lang package and contains only one method named compareTo(Object). It provides a single sorting sequence only, i.e., you can sort the elements on the basis of single data member only. For example, it may be rollno, name, age or anything else.

### compareTo(Object obj) method

**public int compareTo(Object obj):** It is used to compare the current object with the specified object. It returns

- positive integer, if the current object is greater than the specified object.
- negative integer, if the current object is less than the specified object.
- zero, if the current object is equal to the specified object.

---

We can sort the elements of:

1. String objects
2. Wrapper class objects
3. User-defined class objects

### Collections class

**Collections** class provides static methods for sorting the elements of collections. If collection elements are of Set or Map, we can use TreeSet or TreeMap. However, we cannot sort the elements of List. Collections class provides methods for sorting the elements of List type elements.

### Method of Collections class for sorting List elements

**public void sort(List list):** It is used to sort the elements of List. List elements must be of the Comparable type.

#### Note: String class and Wrapper classes implement the Comparable interface by default. So if you store the objects of string or wrapper classes in a list, set or map, it will be Comparable by default.

---

## Java Comparable Example

Let's see the example of the Comparable interface that sorts the list elements on the basis of age.

File: Student.java

[](https://www.tpointtech.com/comparable-interface-in-java#)[](https://www.tpointtech.com/comparable-interface-in-java#)[](https://www.tpointtech.com/comparable-interface-in-java#)

1. class Student implements Comparable<Student>{  
2. int rollno;  
3. String name;  
4. int age;  
5. Student(int rollno,String name,int age){  
6. this.rollno=rollno;  
7. this.name=name;  
8. this.age=age;  
9. }  

10. public int compareTo(Student st){  
11. if(age==st.age)  
12. return 0;  
13. else if(age>st.age)  
14. return 1;  
15. else  
16. return -1;  
17. }  
18. }  

File: TestSort1.java

### Example

[](https://www.tpointtech.com/comparable-interface-in-java#)[](https://www.tpointtech.com/comparable-interface-in-java#)[](https://www.tpointtech.com/comparable-interface-in-java#)

1. import java.util.*;  
2. public class TestSort1{  
3. public static void main(String args[]){  
4. ArrayList<Student> al=new ArrayList<Student>();  
5. al.add(new Student(101,"Vijay",23));  
6. al.add(new Student(106,"Ajay",27));  
7. al.add(new Student(105,"Jai",21));  

8. Collections.sort(al);  
9. for(Student st:al){  
10. System.out.println(st.rollno+" "+st.name+" "+st.age);  
11. }  
12. }  
13. }  

**Output:**

105 Jai 21
101 Vijay 23
106 Ajay 27

## Java Comparable Example: reverse order

Let's see the same example of the Comparable interface that sorts the list elements on the basis of age in reverse order.

File: Student.java

[](https://www.tpointtech.com/comparable-interface-in-java#)[](https://www.tpointtech.com/comparable-interface-in-java#)[](https://www.tpointtech.com/comparable-interface-in-java#)

1. class Student implements Comparable<Student>{    
2.  int rollno;    
3.  String name;    
4.  int age;    
5.  Student(int rollno,String name,int age){    
6.  this.rollno=rollno;    
7.  this.name=name;    
8.  this.age=age;    
9.  }    

10.  public int compareTo(Student st){    
11.  if(age==st.age)    
12.  return 0;    
13.  else if(age<st.age)    
14.  return 1;    
15.  else    
16.  return -1;    
17.  }    
18.  }    

File: TestSort2.java

### Example

[](https://www.tpointtech.com/comparable-interface-in-java#)[](https://www.tpointtech.com/comparable-interface-in-java#)[](https://www.tpointtech.com/comparable-interface-in-java#)

1. import java.util.*;    
2. public class TestSort2{    
3. public static void main(String args[]){    
4. ArrayList<Student> al=new ArrayList<Student>();    
5. al.add(new Student(101,"Vijay",23));    
6. al.add(new Student(106,"Ajay",27));    
7. al.add(new Student(105,"Jai",21));    

8. Collections.sort(al);    
9. for(Student st:al){    
10. System.out.println(st.rollno+" "+st.name+" "+st.age);    
11. }    
12. }    
13. }    

**Output:**

106 Ajay 27
101 Vijay 23
105 Jai 21