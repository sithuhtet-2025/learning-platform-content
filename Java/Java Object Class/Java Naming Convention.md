Java naming conventions are rules to follow when deciding what to name your identifiers, such as class, package, variable, constant, method, etc.

But it is not forced to follow. So, it is known as a convention, not a rule. Several Java communities, such as Sun Microsystems and Netscape suggest these conventions.

All the classes, interfaces, packages, methods, and fields of the Java programming language are named according to the Java naming convention. Failure to follow these conventions may generate confusion or erroneous code.

## Advantage of Naming Conventions in Java

By using standard Java naming conventions, you make your code easier to read for yourself and other programmers. Readability of a Java program is very important. It indicates that less time is spent figuring out what the code does.

1. **Enhanced Maintainability:** Consistent naming conventions make it easier to maintain and update the code. Developers can quickly understand the purpose and usage of different components, reducing the time and effort required for modifications and debugging.
2. **Improved Collaboration:** Adhering to naming conventions when working in a team ensures that all team members can understand and contribute to the codebase more efficiently. It also reduces the learning curve for new developers and facilitates smoother code reviews and pair programming sessions.
3. **Reduced Errors:** Clear and consistent naming helps prevent errors that can arise from misinterpreting the role of variables, methods, or classes. It reduces the likelihood of introducing bugs due to misunderstandings about what a piece of code is supposed to do.
4. **Code Consistency:** Naming conventions promote a uniform coding style across the project, making the codebase look coherent and professional. This uniformity is crucial for large projects where multiple developers are contributing code over an extended period.
5. **Better Integration with Development Tools:** Many development tools, such as IDEs and static code analysers, are designed to work well with standard naming conventions. When these conventions are followed, these tools can provide better code completion, refactoring, and error detection.

## Java Naming Conventions Rules for Different Identifiers

The following table shows the popular conventions used for the different identifiers.

|Identifiers Type|Naming Rules|Examples|
|---|---|---|
|Class|It should start with the uppercase letter.  <br>It should be a noun such as Color, Button, System, Thread, etc.  <br>Use appropriate words, instead of acronyms.|public class **Employee**  <br>{  <br>//code snippet  <br>}|
|Interface|It should start with the uppercase letter.  <br>It should be an adjective such as Runnable, Remote, ActionListener.  <br>Use appropriate words, instead of acronyms.|interface **Printable**  <br>{  <br>//code snippet  <br>}|
|Method|It should start with lowercase letter.  <br>It should be a verb such as main(), print(), println().  <br>If the name contains multiple words, start it with a lowercase letter followed by an uppercase letter such as actionPerformed().|class Employee  <br>{  <br>// method  <br>void **draw()**  <br>{  <br>//code snippet  <br>}  <br>}|
|Variable|It should start with a lowercase letter such as id, name.  <br>It should not start with the special characters like & (ampersand), $ (dollar), _ (underscore).  <br>If the name contains multiple words, start it with the lowercase letter followed by an uppercase letter such as firstName, lastName.  <br>Avoid using one-character variables such as x, y, z.|class Employee  <br>{  <br>// variable  <br>int **id**;  <br>//code snippet  <br>}|
|Package|It should be a lowercase letter such as java, lang.  <br>If the name contains multiple words, it should be separated by dots (.) such as java.util, java.lang.|//package  <br>package **com.javatpoint;**  <br>class Employee  <br>{  <br>//code snippet  <br>}|
|Constant|It should be in uppercase letters such as RED, YELLOW.  <br>If the name contains multiple words, it should be separated by an underscore(_) such as MAX_PRIORITY.  <br>It may contain digits but not as the first letter.|class Employee  <br>{  <br>//constant  <br>static final int **MIN_AGE** = 18;  <br>//code snippet  <br>}|

## CamelCase in Java Naming Conventions

Java follows the camel-case syntax for naming the class, interface, method, and variable.

If the name is combined with two words, the second word will always start with an uppercase letter, such as actionPerformed(), firstName, ActionEvent, ActionListener, etc.

This approach improves readability by clearly distinguishing the different parts of a name. Here's a detailed breakdown of how camelCase is applied in various contexts within Java:

**1. Classes and Interfaces:** PascalCase (Upper CamelCase): Each word starts with an uppercase letter. This style is used for naming classes and interfaces.

**Examples:** ActionEvent, ActionListener, EmployeeDetails, AccountManager.

**2. Methods and Variables:** CamelCase (Lower CamelCase): The first word starts with a lowercase letter, and each subsequent word starts with an uppercase letter. This style is used for naming methods and variables.

**Examples:** actionPerformed(), firstName, calculateInterest(), accountBalance.

## Readability and Consistency

Using camelCase makes the names easier to read and comprehend. It also provides visual cues about the structure and function of the identifier. This technique helps maintain and tidy up the code by avoiding the use of underscores and reducing name complexity.

### Example of Naming Convention

### Example

[](https://www.tpointtech.com/java-naming-conventions#)[](https://www.tpointtech.com/java-naming-conventions#)[](https://www.tpointtech.com/java-naming-conventions#)

1. public class Main {  
2.      public static void main(String[] args)  
3.      {  
4.        int var=98;  //as per naming convention variable name in lower case (var)  
5.        System.out.println("Initial value of variable is: " + var);  
6.      }  
7. }  

**Output:**

Initial value of variable is: 98

In the above code, we have defined all the identifiers as per the naming convention rules.

All keywords in Java are in lower case. So, we have defined a class as public by using the class and public keywords. The first letter of the class name must be in capital letters, so we have named the class as Main.

In the next statement, we have used other Java keywords like public, static, and void. The method name starts with lower case, so here main() is the method that is the starting point of the Java program. Inside the main() method, we have passed String-type arguments.

In the next statement, we have defined and initialised a variable of type int named var in lower case letters.

Again, in the next statement, we have followed naming convention rules. In which the first letter of System is in capital letters because it is a class name. out is in lower case because object first letter must be in lower case. The println() is a method, so it is also in lower case.