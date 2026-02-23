We can sort the elements of:

1. String objects
2. Wrapper class objects
3. User-defined class objects

|   |
|---|
|**Collections** class provides static methods for sorting the elements of a collection. If collection elements are of a Set type, we can use TreeSet. However, we cannot sort the elements of List. Collections class provides methods for sorting the elements of List type elements.|

### Method of Collections class for sorting List elements

**public void sort(List list):** is used to sort the elements of List. List elements must be of the Comparable type.

#### Note: String class and Wrapper classes implement the Comparable interface. So if you store the objects of string or wrapper classes, it will be Comparable.

### Example to sort string objects

### Example

[](https://www.tpointtech.com/sorting-in-collection-framework#)[](https://www.tpointtech.com/sorting-in-collection-framework#)[](https://www.tpointtech.com/sorting-in-collection-framework#)

1. import java.util.*;  
2. class Main{  
3. public static void main(String args[]){  

4. ArrayList<String> al=new ArrayList<String>();  
5. al.add("Viru");  
6. al.add("Saurav");  
7. al.add("Mukesh");  
8. al.add("Tahir");  

9. Collections.sort(al);  
10. Iterator itr=al.iterator();  
11. while(itr.hasNext()){  
12. System.out.println(itr.next());  
13.  }  
14. }  
15. }  

**Output:**

Mukesh
Saurav
Tahir
Viru

### Example to sort string objects in reverse order

### Example

[](https://www.tpointtech.com/sorting-in-collection-framework#)[](https://www.tpointtech.com/sorting-in-collection-framework#)[](https://www.tpointtech.com/sorting-in-collection-framework#)

1. import java.util.*;  
2. class Main{  
3. public static void main(String args[]){  

4. ArrayList<String> al=new ArrayList<String>();  
5.         al.add("Viru");    
6.         al.add("Saurav");    
7.         al.add("Mukesh");    
8.         al.add("Tahir");   

9.         Collections.sort(al,Collections.reverseOrder());  
10.         Iterator i=al.iterator();  
11.         while(i.hasNext())  
12.         {  
13.             System.out.println(i.next());  
14.         }  
15. }  
16. }  

**Output:**

Viru
Tahir
Saurav
Mukesh

### Example to sort Wrapper class objects

### Example

[](https://www.tpointtech.com/sorting-in-collection-framework#)[](https://www.tpointtech.com/sorting-in-collection-framework#)[](https://www.tpointtech.com/sorting-in-collection-framework#)

1. import java.util.*;  
2. class Main{  
3. public static void main(String args[]){  

4. ArrayList al=new ArrayList();  
5. al.add(Integer.valueOf(201));  
6. al.add(Integer.valueOf(101));  
7. al.add(230);//internally will be converted into objects as Integer.valueOf(230)  

8. Collections.sort(al);  

9. Iterator itr=al.iterator();  
10. while(itr.hasNext()){  
11. System.out.println(itr.next());  
12.  }  
13. }  
14. }  

**Output:**

101
201
230

### Example to sort user-defined class objects

### Example

[](https://www.tpointtech.com/sorting-in-collection-framework#)[](https://www.tpointtech.com/sorting-in-collection-framework#)[](https://www.tpointtech.com/sorting-in-collection-framework#)

1. import java.util.*;  

2. class Student implements Comparable<Student> {  
3.     public String name;  
4.   public Student(String name) {  
5.     this.name = name;  
6.   }  
7.   public int compareTo(Student person) {  
8.     return name.compareTo(person.name);  

9.   }   
10. }  
11. public class Main {  
12.   public static void main(String[] args) {  
13.       ArrayList<Student> al=new ArrayList<Student>();  
14.       al.add(new Student("Viru"));  
15.       al.add(new Student("Saurav"));  
16.       al.add(new Student("Mukesh"));  
17.       al.add(new Student("Tahir"));  

18.     Collections.sort(al);  
19.     for (Student s : al) {  
20.       System.out.println(s.name);  
21.     }  
22.   }  
23. }  

**Output:**

Mukesh
Saurav
Tahir
Viru