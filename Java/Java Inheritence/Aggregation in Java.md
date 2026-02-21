**Aggregation** in Java represents a HAS-A relationship where one class contains a reference to another class. In this chapter, we will learn about the aggregation with definition and real-life examples.

## What Is Aggregation in Java?

If a class has a reference to another class (i.e., an entity reference), it is known as **Aggregation**. Aggregation represents a **HAS-A relationship**, where one object uses another object as part of its functionality.

## Understanding Aggregation with an Example

Consider a situation, Employee object contains many informations such as id, name, emailId etc. It contains one more object named address, which contains its own informations such as city, state, country, zipcode etc. as given below.

[](https://www.tpointtech.com/aggregation-in-java#)[](https://www.tpointtech.com/aggregation-in-java#)[](https://www.tpointtech.com/aggregation-in-java#)

1. class Employee{  
2. int id;  
3. String name;  
4. Address address;//Address is a class  
5. ...  
6. }  

In such case, Employee has an entity reference address, so relationship is Employee HAS-A address.

## Example of Aggregation

In the following example, the **Circle** class uses the Operation class through object reference to calculate the area.

![aggregation example](https://images.tpointtech.com/images/aggregation.JPG)

### Example

[](https://www.tpointtech.com/aggregation-in-java#)[](https://www.tpointtech.com/aggregation-in-java#)[](https://www.tpointtech.com/aggregation-in-java#)

1. class Operation{    
2.  int square(int n){    
3.   return n*n;    
4.  }    
5. }    

6. class Circle{    
7.  Operation op;//aggregation (HAS-A Relationship)   
8.  double pi=3.14;    

9.  double area(int radius){    
10.    op=new Operation();    
11.    int rsquare=op.square(radius);//code reusability (i.e. delegates the method call).    
12.    return pi*rsquare;    
13.  }    
14. }  
15. public class Main{  
16.  public static void main(String args[]){    
17.    Circle c=new Circle();    
18.    double result=c.area(5);    
19.    System.out.println(result);    
20.  }    
21. }   

Output:78.5

## Why use Aggregation?

The following are the reasons to use aggregation in Java:

- **Code Reusability:** Aggregation is helpful to reuse the code as it allows one class to reuse the functionality of another class without inheriting it.
- **Better Design:** It is useful when classes are related through a HAS-A relationship, not an IS-A relationship.

> **Note:** Inheritance should be used only if the relationship is-a is maintained throughout the lifetime of the objects involved; otherwise, aggregation is the best choice.

## Real-Time Example of Aggregation

In this example, Employee has an object of Address, address object contains its own informations such as city, state, country etc. In such case relationship is Employee HAS-A Address.

### Example

[](https://www.tpointtech.com/aggregation-in-java#)[](https://www.tpointtech.com/aggregation-in-java#)[](https://www.tpointtech.com/aggregation-in-java#)

1. class Address {    
2.  String city,state,country;    

3.  public Address(String city, String state, String country) {    
4.     this.city = city;    
5.     this.state = state;    
6.     this.country = country;    
7.  }    
8. }    
9. //Employee class that has Address  
10. class Emp {    
11.     int id;    
12.     String name;    
13.     Address address;  //Emp Has-A Address  

14.  public Emp(int id, String name,Address address) {    
15.     this.id = id;    
16.     this.name = name;    
17.     this.address=address;    
18.  }    

19.  void display(){    
20.   System.out.println(id+" "+name);    
21.   System.out.println(address.city+" "+address.state+" "+address.country);    
22.  }    
23. }  
24. //Main class   
25. public class Main{  
26.  public static void main(String[] args) {    
27.   Address address1=new Address("gzb","UP","india");    
28.   Address address2=new Address("gno","UP","india");    
29.   Emp e=new Emp(111,"varun",address1);    
30.   Emp e2=new Emp(112,"arun",address2);    

31.   e.display();    
32.   e2.display();      
33.  }    
34. }    

111 varun
gzb UP india
112 arun
gno UP india