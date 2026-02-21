In Java, the **super** keyword provides a way for a subclass to access members (methods, variables, or constructors) of its immediate parent class.

## What is super Keyword in Java?

The **super keyword** is a reference variable used to refer to the immediate parent class object. Whenever you create an instance of a subclass, an instance of the parent class is created implicitly, which is accessed using the super reference variable.

## Advantages of Using super Keyword

Here are the advantages of using the super keyword in Java:

1. **Simplifies Constructor Chaining:** The super() call ensures that the parent class's constructor is executed before the child class's, maintaining proper initialization across the inheritance hierarchy.
2. **Access to Overridden Methods:** It allows a subclass to invoke a method from the parent class even when the subclass has overridden the method. This is useful for extending functionality without completely overriding it.
3. **Access to Hidden Fields:** It provides access to parent class fields that subclass fields may hide with the same name.
4. **Code Reusability:** By invoking the parent class's methods or constructors, it promotes code reuse and reduces redundancy.
5. **Maintains Hierarchical Relationships:** It preserves and utilizes the hierarchical structure of inheritance, making the code more organized and easier to manage.

## Using super to Access Parent Class Instance Variables

We can use the super keyword to access the data member or field of the parent class. It is used if parent class and child class have the same fields.

The following example demonstrates how the super keyword can be used to access an instance variable of the parent class when it is hidden by a subclass variable.

### Example

[](https://www.tpointtech.com/super-keyword-in-java#)[](https://www.tpointtech.com/super-keyword-in-java#)[](https://www.tpointtech.com/super-keyword-in-java#)

1. //Java Program to illustrate the use of super keyword  
2. //Creating parent class  
3. class Animal{    
4.     String color="white";    
5. }    
6. //Creating child class  
7. class Dog extends Animal{    
8.     String color="black";    
9.     void printColor(){    
10.         System.out.println(color);//prints color of Dog class    
11.         System.out.println(super.color);//prints color of Animal class    
12.     }    
13. }    
14. //Creating Main class to create object and call methods  
15. public class Main{    
16.     public static void main(String args[]){    
17.         Dog d=new Dog();    
18.         d.printColor();    
19.     }  
20. }    

Output:

black
white

In the above example, Animal and Dog both classes have a common property color. If we print the color property, it will print the color of the current class by default. To access the parent property, we need to use the super keyword.

## Using super to Invoke Parent Class Methods

The super keyword can also be used to invoke the parent class method. It should be used if the subclass contains the same method as the parent class. In other words, it is used if a method is overridden.

The following example demonstrates how the super keyword can be used to call a method of the parent class from a subclass.

### Example

[](https://www.tpointtech.com/super-keyword-in-java#)[](https://www.tpointtech.com/super-keyword-in-java#)[](https://www.tpointtech.com/super-keyword-in-java#)

1. //Java Program to illustrate the use of super()  
2. //Creating parent class  
3. class Animal{    
4.     void eat(){System.out.println("eating...");}    
5. }    
6. //Creating child class  
7. class Dog extends Animal{    
8.     void eat(){System.out.println("eating bread...");}    
9.     void bark(){System.out.println("barking...");}    
10.     void work(){    
11.         super.eat();    
12.         bark();    
13.     }    
14. }    
15. //Creating Main class to create object and call methods  
16. public class Main{    
17.     public static void main(String args[]){    
18.         Dog d=new Dog();    
19.         d.work();    
20.     }  
21. }    

Output:

eating...
barking...

In the above example, Animal and Dog both classes have the eat() method. If we call the eat() method from the Dog class, it will call the eat() method of the Dog class by default because priority is given to local.

To call the parent class method, we need to use the super keyword.

## Using super to Invoke Parent Class Constructor

The super keyword can also be used to invoke the parent class constructor. Let's see a simple example:

The following example demonstrates how the super keyword is used to call the constructor of the parent class from a subclass.

### Example

[](https://www.tpointtech.com/super-keyword-in-java#)[](https://www.tpointtech.com/super-keyword-in-java#)[](https://www.tpointtech.com/super-keyword-in-java#)

1. class Animal{    
2.     Animal(){System.out.println("animal is created");}    
3. }    
4. class Dog extends Animal{    
5.     Dog(){    
6.         super();  //calls the constructor of parent class  
7.         System.out.println("dog is created");    
8.     }    
9. }    
10. public class Main{    
11.     public static void main(String args[]){    
12.         Dog d=new Dog();    
13.     }  
14. }    

Output:

animal is created
dog is created

#### Note: super() is added in each class constructor automatically by the compiler if there is no super() or this().

As we know well, the default constructor is provided by the compiler automatically if there is no constructor. But, it also adds super() as the first statement.

### Another Example: Using super Keyword

Another example of a super keyword is where super() is provided by the compiler implicitly.

### Example

[](https://www.tpointtech.com/super-keyword-in-java#)[](https://www.tpointtech.com/super-keyword-in-java#)[](https://www.tpointtech.com/super-keyword-in-java#)

1. class Animal{    
2.     Animal(){System.out.println("animal is created");}    
3. }    
4. class Dog extends Animal{    
5.     Dog(){    
6.         System.out.println("dog is created");    
7.     }    
8. }    
9. public class Main{    
10.     public static void main(String args[]){    
11.         Dog d=new Dog();    
12.     }  
13. }  

Output:

animal is created
dog is created

## Real-Time Use of Super Keyword

Let's see the real use of the super keyword. Here, the Emp class inherits the Person class, so all the properties of the Person will be inherited by Emp by default. To initialize all the properties, we are using the parent class constructor from the child class. In such a way, we are reusing the parent class constructor.

Let us take an example to demonstrate the real-time use of super keyword in Java.

### Example

[](https://www.tpointtech.com/super-keyword-in-java#)[](https://www.tpointtech.com/super-keyword-in-java#)[](https://www.tpointtech.com/super-keyword-in-java#)

1. class Person{    
2.     int id;    
3.     String name;    
4.     Person(int id,String name){    
5.         this.id=id;    
6.         this.name=name;    
7.     }    
8. }    
9. class Emp extends Person{    
10.     float salary;    
11.     Emp(int id,String name,float salary){    
12.         super(id,name);//reusing parent constructor    
13.         this.salary=salary;    
14.     }    
15.     void display(){System.out.println(id+" "+name+" "+salary);}    
16. }    
17. public class Main{    
18.     public static void main(String[] args){    
19.         Emp e1=new Emp(1,"ankit",45000f);    
20.         e1.display();    
21.     }  
22. }    

Output:

1 ankit 45000

## Characteristics of super Keyword

The following are the main characteristics of the super keyword in Java:

### 1. Calling the Parent Class Constructor

When we create an object of a subclass, Java automatically calls the constructor of the parent class. If we want to call the parent class constructor explicitly, we can use super(). It is typically done to ensure that the parent class is properly initialized before the child class starts.

### 2. Calling a Parent Class Method

If a method in the parent class is overridden in the child class, the child class can still call the parent class's version of that method using super.methodName(). It is useful when the child class wants to extend or add extra functionality to the method, but still needs to use the original functionality from the parent.

### 3. Accessing Parent Class Fields

If both the parent and child classes have variables (fields) with the same name, super allows the child class to access the parent class's version of the field. It helps avoid confusion between the two variables and makes it clear that we are referring to the one in the parent class.

### 4. First Statement in Constructor

When using super() to call the parent class's constructor, it must be the very first statement in the child class's constructor. It ensures that the parent class is initialized before the child class starts its own initialization.

### 5. Cannot Be Used in Static Contexts

The super keyword cannot be used in static methods or static variables. It is because static methods and variables belong to the class itself, not to a specific object. Since super refers to the parent class of an object, it's not allowed in static contexts.

### 6. Not Always Necessary

If the parent class's method is not overridden in the child class, we don't need to use super to call the parent class's method. The child class will automatically call the parent class's method when the method is invoked.