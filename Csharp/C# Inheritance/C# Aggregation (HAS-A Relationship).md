
In the C# programming language, aggregation is a relationship in which one class holds a reference to another class. It allows reusing a class inside another class. It is a type of association that represents a "Has-A" relationship between different classes, where both classes can exist independently, but one class contains a reference to the other class. It helps to promote code reusability, simplicity, and maintainability.

### Syntax:

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-aggregation#)[](https://www.tpointtech.com/c-sharp-aggregation#)[](https://www.tpointtech.com/c-sharp-aggregation#)

1. class ClassA  
2. {  
3.     // fields, methods, etc.  
4. }  
5. class ClassB  
6. {  
7.     // Aggregation: ClassB has a reference to ClassA  
8.     ClassA obj;  
9.     // Constructor to accept an existing ClassA object  
10.     public ClassB(ClassA obj)  
11.     {  
12.         this.obj = obj;  
13.     }  
14.     // methods, etc.  
15. }     

In this syntax,

ClassA is a standalone class with its own fields and methods, and ClassB contains a reference to an object of ClassA to represent the aggregation.

### C# Aggregation Example

Let us take an example to illustrate the aggregation in C#.

### Example

[](https://www.tpointtech.com/c-sharp-aggregation#)[](https://www.tpointtech.com/c-sharp-aggregation#)[](https://www.tpointtech.com/c-sharp-aggregation#)

1. using System;  
2. // create a class   
3. class information  
4. {  
5.     public string City;  
6.     public string Country;  
7.     public long Contact;  
8.     // declaration constructor   
9.     public information(string city, string country, long contact)  
10.     {  
11.         City = city;  
12.         Country = country;  
13.         Contact = contact;  
14.     }  
15. }  
16. // declare a student class  
17. class Stu  
18. {  
19.     public int Id;  
20.     public string Name;  
21.     public information Ddr;  // Aggregation  
22.     public Stu(int id, string name, information ddr)  
23.     {  
24.         Id = id;  
25.         Name = name;  
26.         Ddr = ddr;   
27.     }  
28.     public void Display()  
29.     {  
30.         Console.WriteLine("ID is " + Id + ", Name is " + Name);  
31.         Console.WriteLine("City is " + Ddr.City + ", State is " + Ddr.Country + ", Contact is " + Ddr.Contact);  
32.     }  
33. }  
34. class Program  
35. {  
36.     static void Main()  
37.     {  
38.         // Use Details   
39.         information d1 = new information("New York", "USA", 356545161);  
40.         Stu s1 = new Stu(1, "John", d1);  
41.         s1.Display();  
42.     }  
43. }  

**Output:**

ID is 1, Name is John
City is New York, State is USA, Contact is 356545161

**Explanation:**

In the C# program, we define two classes: Student and Information. The information class stores several details such as city, state, and contact number. The student class stores basic details, ID, and Name, and also holds a reference to an information object. In the main() method, it creates the information object and passes it to a student object, which shows the combined data.

## Composition in C#

In the [C# programming language](https://www.tpointtech.com/c-sharp-tutorial), the composition is a special type of aggregation that represents a part-of relationship. If the parent object is deleted under composition, the child object is also destroyed because it cannot exist independently.

**For Example:** A House has Rooms. If the house is destroyed, the rooms also disappear.

### Syntax:

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-aggregation#)[](https://www.tpointtech.com/c-sharp-aggregation#)[](https://www.tpointtech.com/c-sharp-aggregation#)

1. class Part  
2. {  
3.     // method, member;  
4. }  
5. class Whole  
6. {     
7.     privatePart part; // Composition  
8.     public Whole()  
9.     {  
10.         part = new Part(); // Child created inside parent  
11.     }  
12. }     

In this syntax,

The Part class is a separate component (child) created and owned by the Whole class (parent). The parent class creates the part class within itself, so the part's life is completely dependent on the parent. If the parent is deleted, the child is also deleted.

### C# Composition Example:

Let us take an example to illustrate the composition in C# using a Home and Room.

### Example

[](https://www.tpointtech.com/c-sharp-aggregation#)[](https://www.tpointtech.com/c-sharp-aggregation#)[](https://www.tpointtech.com/c-sharp-aggregation#)

1. using System;  
2. // Declare a class Room  
3. class Room  
4. {  
5.     public string Name { get; set; }   // Property should match the constructor  
6.     public Room(string n)  
7.     {  
8.         Name = n;      // Use Name with uppercase to match property  
9.     }  
10.     public void ShowRoom()  
11.     {  
12.         Console.WriteLine("The room is " + Name);  
13.     }  
14. }  
15. // Declare a class House  
16. class home  
17. {  
18.     private Room room; // Composition: House contains a Room  
19.     public home(string roomName)  
20.     {  
21.         room = new Room(roomName); // Child object created in constructor  
22.     }  
23.     public void Show()  
24.     {  
25.         room.ShowRoom();  // Call the Room's method  
26.         Console.WriteLine("This room belongs to the house.");  
27.     }  
28. }  
29. // Main Program  
30. class Program  
31. {  
32.     static void Main()  
33.     {  
34.         home myhome = new home("Living Room");  
35.         myhome.Show();  
36.         // Room cannot exist without the home  
37.     }  
38. }  

**Output:**

The room is the Living Room
This room is part of the house.

**Explanation:**

In this example, we create two classes named Room and House. The room class contains the name property and also includes the ShowRoom() method to display the name of the room. After that, the house class demonstrates composition by creating its own Room object and calling the ShowHouse() method. In the main method(), we create an instance of the House class and call the ShowHouse() method to show the desired output.

## Difference between Aggregation and Composition

In C#, the aggregation and composition differ in the following ways.

|Aggregation|Composition|
|---|---|
|It is a special type of association.|It is a special type of aggregation.|
|Every object has its own life cycle.|The child object does not have its own life cycle. It mainly depends on its parent's life cycle.|
|It is a weak association.|It is a strong association.|
|Aggregation means one object just uses another class. It means one class is fully made up of another class.|The composition indicates that one object is contained in another class.|
|The parent class is not responsible to create or destroy the child class.|The parent class is responsible to create or remove the child class.|

## Aggregation Function in LINQ

In C#, aggregation functions in [LINQ](https://www.tpointtech.com/linq) are those functions that combine the values of several rows as input and then return the output as a single value. Hence, we can say that the C# aggregate function will always produce a single value.

The real-life example of an aggregation function is calculating the total sales revenue of a company.

The following is the list of the methods that are used to perform the aggregation operation.

|Methods|Description|
|---|---|
|**Aggregate**|It carries out a custom aggregation operation on the elements of a collection.|
|**Count**|It counts the elements in the collection.|
|**Average**|It determines the average of the collection of values.|
|**LargeCount**|It counts the elements in the large collection|
|**Max**|It calculates the maximum value of the collection.|
|**Min**|It calculates the minimum value of the collection.|
|**Sum**|It determines the sum of the values of the collection.|

### C# LINQ Aggregation Example

Let us take an example to calculate the sum of the numbers.

### Example

[](https://www.tpointtech.com/c-sharp-aggregation#)[](https://www.tpointtech.com/c-sharp-aggregation#)[](https://www.tpointtech.com/c-sharp-aggregation#)

1. using System;  
2. using System.Linq;  
3. public class Tpoint {  
4.     // Main Method  
5.     static public void Main()  
6.     {  
7.         int[] seq = {200, 400, 500, 600, 100,   
8.                           8, 99, 9, 5, 6};  
9.         Console.WriteLine("The total of all the number is: ");  
10.         // Using Sum() aggregation function  
11.         int res = seq.Sum();  
12.         Console.WriteLine(res);  
13.     }  
14. }  

**Output:**

The total of all the numbers is:
1927

**Explanation:**

In this example, we apply the Sum() aggregation function from the System.Linq.namespace. First, we define the integer array and initialize the sequence of numbers. In the main() function, it calculates the total sum of the elements in the array using the Sum() method. Finally, we use the Console.WriteLine() function to print the output.

## Advantages of Using C# Aggregation

Several advantages of C# aggregation are as follows:

- It represents a unidirectional HAS-A relationship between the objects of two classes.
- It also helps to enhance code reusability.
- It improves the code's readability and make it understandable to represent the relationship.
- It consists of more restrictions as compared to the association.

## Conclusion

In conclusion, the C# aggregation is the process by which one class holds a reference to another class. It promotes cleaner code organization, which allows for better flexibility, scalability, and reuse of components. This approach is useful in large applications. In order to improve maintainability and facilitate future updates, components must interact without forming strong dependencies.