In Java, an [array](https://www.tpointtech.com/java-arrays) is a collection of the same data type that dynamically creates objects and can contain elements of primitive types. Java also allows us to store objects in an array.

## Array of Objects

An array of objects is a collection of multiple objects stored in a single variable. It stores the references to the objects. It is useful when managing multiple instances of a class efficiently.

![How to Create Array of Objects in Java](https://images.tpointtech.com/core/images/how-to-create-array-of-objects-in-java.png)

## Creating an Array of Objects

Before creating an array of objects, we must create instances of the class using the new keyword. We can use any of the following statements to create an array of objects.

[](https://www.tpointtech.com/array-of-objects-in-java#)[](https://www.tpointtech.com/array-of-objects-in-java#)[](https://www.tpointtech.com/array-of-objects-in-java#)

1. ClassName obj[]=new ClassName[array_length]; //declare and instantiate an array of objects  

Or

[](https://www.tpointtech.com/array-of-objects-in-java#)[](https://www.tpointtech.com/array-of-objects-in-java#)[](https://www.tpointtech.com/array-of-objects-in-java#)

1. ClassName[] objArray;  

Or

[](https://www.tpointtech.com/array-of-objects-in-java#)[](https://www.tpointtech.com/array-of-objects-in-java#)[](https://www.tpointtech.com/array-of-objects-in-java#)

1. ClassName objeArray[];  

Suppose, we have created a class named Employee. We want to keep records of 20 employees of a company having three departments. In this case, we will not create 20 separate variables. Instead of this, we will create an array of objects, as follows.

[](https://www.tpointtech.com/array-of-objects-in-java#)[](https://www.tpointtech.com/array-of-objects-in-java#)[](https://www.tpointtech.com/array-of-objects-in-java#)

1. Employee department1[20];  
2. Employee department2[20];  
3. Employee department3[20];  

The above statements create an array of objects with 20 elements.

## Initializing an Array of Objects

After the objects are instantiated, the array has to be initialized with values. In contrast to a variety of primitive types, an array of objects cannot be initialized in the same way. It is necessary to initialize each element or object in an array of objects. An array contains pointers to the real class through its objects.

Consequently, it is highly recommended to generate actual objects of the class after declaring and instantiating an array of objects. The constructors can set up the array. Actual objects can have their initial values assigned by the application by supplying values to the constructor. A class's independent member method can also be used to assign data to an object.

The elements of an array of objects must be initialized after they have been created. Two common approaches are available to perform this:

1. Using the Constructor
2. Using Setter Methods

Here, we are going to discuss approached one by one.

### 1. Using the Constructor

By providing variables to the constructor individually, we can define starting values for each object as the actual objects are being created. Every single real object is made with its unique values.

### Example

[](https://www.tpointtech.com/array-of-objects-in-java#)[](https://www.tpointtech.com/array-of-objects-in-java#)[](https://www.tpointtech.com/array-of-objects-in-java#)

1. // Java program to demonstrate initializing an array of objects using a constructor  
2. public class Main {  
3.     public static void main(String args[]) {  
4.         // Declaring an array of Book  
5.         Book[] books;  
6.         // Allocating memory for 3 Book objects  
7.         books = new Book[3];  
8.         // Initializing the elements of the array using the constructor  
9.         books[0] = new Book(101, "Java Basics");  
10.         books[1] = new Book(102, "Data Structures");  
11.         books[2] = new Book(103, "Operating Systems");  
12.         System.out.println("Book details:");  
13.         for (int i = 0; i < books.length; i++) {  
14.             books[i].display();  
15.         }  
16.     }  
17. }  
18. // Creating a Book class with id and title as attributes  
19. class Book {  
20.     public int bookId;  
21.     public String title;  
22.     // Book class constructor  
23.     Book(int bookId, String title) {  
24.         this.bookId = bookId;  
25.         this.title = title;  
26.     }  
27.     // display() method to display the book data  
28.     public void display() {  
29.         System.out.println("Book ID: " + bookId + ", Title: " + title);  
30.     }  
31. }  

**Output:**

Book details:
Book ID: 101, Title: Java Basics
Book ID: 102, Title: Data Structures
Book ID: 103, Title: Operating Systems

### 2. Using Setter Methods

Using setter methods, we may assign values after creating objects. The initial values of the objects are assigned using a member function of the corresponding class that is formed.

### Example

[](https://www.tpointtech.com/array-of-objects-in-java#)[](https://www.tpointtech.com/array-of-objects-in-java#)[](https://www.tpointtech.com/array-of-objects-in-java#)

1. // Java program to demonstrate initializing an array of objects using setter methods  
2. public class Main {  
3.     public static void main(String args[]) {  
4.         // Declaring an array of Book  
5.         Book[] books;  
6.         // Allocating memory for 3 objects of type Book  
7.         books = new Book[3];  
8.         // Creating actual Book objects  
9.         books[0] = new Book();  
10.         books[1] = new Book();  
11.         books[2] = new Book();  
12.         // Assigning data to Book objects using the setter method  
13.         books[0].setData(201, "Java Programming");  
14.         books[1].setData(202, "Algorithms");  
15.         books[2].setData(203, "Database Systems");  
16.         // Displaying the book data  
17.         System.out.println("Book details:");  
18.         for (int i = 0; i < books.length; i++) {  
19.             books[i].display();  
20.         }  
21.     }  
22. }  
23. // Creating a Book class with id and title as attributes  
24. class Book {  
25.     public int bookId;  
26.     public String title;  
27.     // Setter method to set the data  
28.     public void setData(int bookId, String title) {  
29.         this.bookId = bookId;  
30.         this.title = title;  
31.     }  
32.     // display() method to show book details  
33.     public void display() {  
34.         System.out.println("Book ID: " + bookId + ", Title: " + title);  
35.     }  
36. }  

**Output:**

Book details:
Book ID: 201, Title: Java Programming
Book ID: 202, Title: Algorithms
Book ID: 203, Title: Database Systems

## Example: Creating an Array of Objects

In the following program, we have created a class named Product and initialized an array of objects using the constructor. We have created a constructor of the class Product that contains the product ID and product name. In the main() function, we have created individual objects of the class Product. After that, we passed initial values to each of the objects using the constructor.

### Example

[](https://www.tpointtech.com/array-of-objects-in-java#)[](https://www.tpointtech.com/array-of-objects-in-java#)[](https://www.tpointtech.com/array-of-objects-in-java#)

1. public class Main  {    
2.     public static void main(String args[])   {    
3.         //create an array of product objects     
4.         Product[] obj = new Product[5] ;    
5.         //create & initialize actual product objects using constructor    
6.         obj[0] = new Product(23907,"Dell Laptop");    
7.         obj[1] = new Product(91240,"HP 630");    
8.         obj[2] = new Product(29823,"LG OLED TV");    
9.         obj[3] = new Product(11908,"MI Note Pro Max 9");    
10.         obj[4] = new Product(43590,"Kingston USB");    
11.         //display the product object data    
12.         System. out.println("Product Object 1:");    
13.         obj[0].display();    
14.         System.out.println("Product Object 2:");    
15.         obj[1].display();    
16.         System.out.println("Product Object 3:");    
17.         obj[2].display();    
18.         System.out.println("Product Object 4:");    
19.         obj[3].display();    
20.         System.out.println("Product Object 5:");    
21.         obj[4].display();    
22.     }    
23. }    
24.  //Product class with product ID and product name as attributes    
25. class Product  {    
26.     int pro_Id;    
27.     String pro_name;    
28.     //Product class constructor    
29.     Product(int pid, String n)  {    
30.         pro_Id = pid;    
31.         pro_name = n;    
32.     }     
33.     public void display()  {    
34.         System.out.print("Product ID = "+pro_ID + "  " + " Product Name = "+pro_name);    
35.         System.out.println();    
36.     }    
37. }    

**Output:**

Product Object 1:
Product ID = 23907 Product Name = Dell Laptop
Product Object 2:
Product ID = 91240 Product Name = HP 630
Product Object 3:
Product ID = 29823 Product Name = LG OLED TV
Product Object 4:
Product ID = 11908 Product Name = MI Note Pro Max 9
Product Object 5:
Product ID = 43590 Product Name = Kingston USB