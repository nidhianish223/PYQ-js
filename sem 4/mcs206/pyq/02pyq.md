question 1 :
) What is inheritance ? List and explain the
types of inheritances supported by Java.
Write a Java program to illustrate
implementation of inheritance.

# Inheritance in Java

## Definition

**Inheritance** is an important feature of Object-Oriented Programming (OOP) in Java. It is a mechanism by which one class **acquires the properties and methods of another class**.

The class whose properties are inherited is called the **parent class (superclass/base class)**, and the class that inherits them is called the **child class (subclass/derived class)**.

In Java, inheritance is mainly achieved using the **`extends`** keyword.

### Syntax

```java
class Parent {
    // properties and methods
}

class Child extends Parent {
    // additional properties and methods
}
```

Inheritance provides **code reusability**, reduces code duplication, and supports **method overriding and polymorphism**.

---

# Types of Inheritance Supported by Java

Java supports the following types of inheritance:

## 1. Single Inheritance

In single inheritance, **one child class inherits from one parent class**.

```text
    Animal
       |
      Dog
```

Example:

```java
class Animal {
    void eat() {
        System.out.println("Animal eats");
    }
}

class Dog extends Animal {
    void bark() {
        System.out.println("Dog barks");
    }
}
```

Here, `Dog` inherits the `eat()` method from `Animal`.

---

## 2. Multilevel Inheritance

In multilevel inheritance, a class inherits from another derived class, forming a **chain of inheritance**.

```text
    Animal
       |
      Dog
       |
    Puppy
```

Example:

```java
class Animal {
    void eat() {
        System.out.println("Animal eats");
    }
}

class Dog extends Animal {
    void bark() {
        System.out.println("Dog barks");
    }
}

class Puppy extends Dog {
    void play() {
        System.out.println("Puppy plays");
    }
}
```

Here, `Puppy` can access methods of both `Dog` and `Animal`.

---

## 3. Hierarchical Inheritance

In hierarchical inheritance, **multiple child classes inherit from the same parent class**.

```text
        Animal
       /      \
     Dog      Cat
```

Example:

```java
class Animal {
    void eat() {
        System.out.println("Animal eats");
    }
}

class Dog extends Animal {
    void bark() {
        System.out.println("Dog barks");
    }
}

class Cat extends Animal {
    void meow() {
        System.out.println("Cat meows");
    }
}
```

Here, both `Dog` and `Cat` inherit the `eat()` method from `Animal`.

---

## 4. Multiple Inheritance

In multiple inheritance, **one child class inherits from more than one parent class**.

```text
   Father     Mother
      \        /
       \      /
        Child
```

**Java does not support multiple inheritance through classes.**

For example, this is not allowed:

```java
class A {
}

class B {
}

// Not allowed in Java
class C extends A, B {
}
```

Java avoids this because it can create ambiguity when both parent classes contain methods with the same name.

However, **multiple inheritance can be achieved using interfaces**.

Example:

```java
interface A {
    void showA();
}

interface B {
    void showB();
}

class C implements A, B {

    public void showA() {
        System.out.println("Interface A");
    }

    public void showB() {
        System.out.println("Interface B");
    }
}
```

---

## 5. Hybrid Inheritance

Hybrid inheritance is a **combination of two or more types of inheritance**, such as hierarchical and multiple inheritance.

Java does **not support hybrid inheritance through classes** because it may lead to ambiguity.

However, hybrid inheritance can be implemented using **interfaces**.

---

# Java Program to Illustrate Inheritance

The following program demonstrates **single inheritance**:

```java
class Animal {

    void eat() {
        System.out.println("Animal is eating");
    }
}

class Dog extends Animal {

    void bark() {
        System.out.println("Dog is barking");
    }
}

public class Main {

    public static void main(String[] args) {

        Dog d = new Dog();

        d.eat();   // Inherited method
        d.bark();  // Child class method
    }
}
```

### Output

```text
Animal is eating
Dog is barking
```

### Explanation

* `Animal` is the **parent class**.
* `Dog` is the **child class**.
* `extends` is used to establish inheritance.
* `Dog` inherits the `eat()` method from `Animal`.
* `Dog` also has its own `bark()` method.
* The object `d` of `Dog` can access both `eat()` and `bark()`.

# Conclusion

Inheritance allows a class to **reuse the properties and methods of an existing class**. Java supports **single, multilevel, and hierarchical inheritance through classes**. Multiple and hybrid inheritance are **not supported through classes**, but they can be achieved using **interfaces**. Inheritance improves code reusability and is an important concept of OOP.
-----------------------------------------------------------------------------------------------
question 2:
Write a Java program which takes a string
as input and displays its reverse. Also, find
is length.

# Java Program to Find Reverse and Length of a String

### Program

```java
import java.util.Scanner;

public class Main {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        // Take string input from user
        System.out.print("Enter a string: ");
        String str = sc.nextLine();

        // Find length of the string
        int length = str.length();

        // Find reverse of the string
        String reverse = "";

        for (int i = length - 1; i >= 0; i--) {
            reverse = reverse + str.charAt(i);
        }

        // Display result
        System.out.println("Original String = " + str);
        System.out.println("Reverse String = " + reverse);
        System.out.println("Length = " + length);

        sc.close();
    }
}
```

### Sample Output

```text
Enter a string: Hello

Original String = Hello
Reverse String = olleH
Length = 5
```

### Explanation

1. `Scanner` is used to take input from the user.
2. `str.length()` returns the **length of the string**.
3. The `for` loop starts from the **last character** (`length - 1`) and moves towards the first character.
4. `str.charAt(i)` gets the character at index `i`.
5. Each character is added to `reverse`.
6. Finally, the program displays the **original string, reversed string, and its length*
-----------------------------------------------------------------------------------------------
question 3:
What is constructor ? Explain the need of
parameterised constructor in Java
program with the help of an example. 

# Constructor in Java

A **constructor** is a special member of a class that is used to **initialize objects**. It has the **same name as the class** and does not have a return type, not even `void`.

A constructor is automatically called when an object of the class is created.

### Example

```java
class Student {

    String name;
    int age;

    // Constructor
    Student() {
        name = "Rahul";
        age = 20;
    }
}
```

## Parameterised Constructor

A **parameterised constructor** is a constructor that accepts one or more parameters. It is used to initialize an object with **different values at the time of object creation**.

### Need of Parameterised Constructor

1. It allows us to initialize objects with specific values.
2. Different objects can have different values.
3. It reduces the need to assign values separately after creating an object.
4. It makes the program more convenient and readable.

### Example Program

```java
class Student {

    String name;
    int age;

    // Parameterised constructor
    Student(String n, int a) {
        name = n;
        age = a;
    }

    void display() {
        System.out.println("Name = " + name);
        System.out.println("Age = " + age);
    }
}

public class Main {

    public static void main(String[] args) {

        Student s1 = new Student("Rahul", 20);
        Student s2 = new Student("Aman", 22);

        s1.display();
        s2.display();
    }
}
```

### Output

```text
Name = Rahul
Age = 20
Name = Aman
Age = 22
```

### Explanation

Here, `Student(String n, int a)` is a **parameterised constructor**. When `s1` is created, `"Rahul"` and `20` are passed to the constructor. Similarly, `"Aman"` and `22` are passed for `s2`.

Thus, a parameterised constructor helps initialize **different objects with different values during object creation**.
---------------------------------------------------------------------------------------
question 4:
What is object oriented programming ?
Explain the concept of encapsulation with
the help of an example.

# Object-Oriented Programming (OOP)

## Definition

**Object-Oriented Programming (OOP)** is a programming paradigm in which a program is designed using **objects and classes**. An object represents a real-world entity and contains **data (properties)** and **methods (behaviour)**.

The main features of OOP are:

1. **Encapsulation**
2. **Inheritance**
3. **Polymorphism**
4. **Abstraction**

OOP makes programs more **secure, reusable, modular, and easier to maintain**.

---

# Encapsulation

**Encapsulation** is the process of **binding data and methods together into a single unit called a class**.

It also provides **data hiding** by restricting direct access to the data. In Java, encapsulation is commonly achieved by declaring variables as **`private`** and accessing them through **public getter and setter methods**.

### Example

```java id="x8p9z4"
class Student {

    // Private data members
    private String name;
    private int marks;

    // Setter method
    public void setName(String name) {
        this.name = name;
    }

    public void setMarks(int marks) {
        this.marks = marks;
    }

    // Getter methods
    public String getName() {
        return name;
    }

    public int getMarks() {
        return marks;
    }
}

public class Main {

    public static void main(String[] args) {

        Student s = new Student();

        s.setName("Rahul");
        s.setMarks(85);

        System.out.println("Name = " + s.getName());
        System.out.println("Marks = " + s.getMarks());
    }
}
```

### Output

```text
Name = Rahul
Marks = 85
```

## Explanation

In the above example:

* `Student` is a **class**.
* `name` and `marks` are declared as **private**, so they cannot be accessed directly from outside the class.
* `setName()` and `setMarks()` are **setter methods** used to assign values.
* `getName()` and `getMarks()` are **getter methods** used to access values.
* Thus, data and methods are **encapsulated inside the `Student` class**.

### Advantages of Encapsulation

1. **Data hiding** – protects data from direct access.
2. **Security** – controls how data can be accessed or modified.
3. **Maintainability** – changes can be made inside the class without affecting other code.
4. **Controlled access** – getter and setter methods control access to data.
5. **Improves code organization**.
------------------------------------------------------------------------------------------------
question 5:
What is an object in Java ? Explain how an
object is assigned to another object, with
the help of Java code.

# Object in Java

An **object** is an instance of a class. It is a real-world entity that has **state (data)** and **behaviour (methods)**.

An object is created using the `new` keyword.

### Syntax

```java
ClassName objectName = new ClassName();
```

For example:

```java
Student s1 = new Student();
```

Here, `s1` is an object of the `Student` class.

---

# Assigning One Object to Another Object

In Java, one object can be assigned to another object using the **assignment operator (`=`)**.

When one object is assigned to another, **a reference is copied, not the actual object**. Therefore, both reference variables point to the **same object in memory**.

### Example

```java
class Student {

    String name;
    int marks;

    void display() {
        System.out.println("Name = " + name);
        System.out.println("Marks = " + marks);
    }
}

public class Main {

    public static void main(String[] args) {

        // Creating first object
        Student s1 = new Student();

        s1.name = "Rahul";
        s1.marks = 80;

        // Assigning s1 to s2
        Student s2 = s1;

        // Display using s2
        s2.display();

        // Changing value using s2
        s2.marks = 90;

        System.out.println("Marks using s1 = " + s1.marks);
    }
}
```

### Output

```text
Name = Rahul
Marks = 80
Marks using s1 = 90
```

### Explanation

Initially:

```text
Student s1 = new Student();
```

creates an object.

Then:

```java
Student s2 = s1;
```

does **not create a new object**. Instead, the reference stored in `s1` is copied to `s2`.

Therefore:

```text
s1 ──────┐
         ↓
      Student Object
         ↑
s2 ──────┘
```

Both `s1` and `s2` refer to the **same object**. So, when we change `s2.marks` to `90`, the value accessed through `s1.marks` also becomes `90`.

### Important Point

> **Object assignment in Java copies the reference, not the object itself.**
------------------------------------------------------------------------------------------
question 6:
What is Java thread model ? Explain
thread life cycle in Java with the help of a
diagram.

# Java Thread Model and Thread Life Cycle

## Java Thread Model

A **thread** is a lightweight, independent path of execution within a program. Java supports **multithreading**, which means that multiple threads can execute concurrently within a program.

The **Java Thread Model** provides a mechanism for creating and managing multiple threads. It allows different tasks of a program to run independently and improves the utilization of CPU resources.

For example, a program can have separate threads for:

* Reading data
* Performing calculations
* Handling user input
* Performing background tasks

A thread can be created in Java mainly by:

1. Extending the `Thread` class.
2. Implementing the `Runnable` interface.

---

# Thread Life Cycle in Java

A thread passes through different states during its execution. The main states are:

### 1. New

When a thread object is created but the `start()` method has not been called, the thread is in the **New** state.

```java
Thread t = new Thread();
```

### 2. Runnable

After calling the `start()` method, the thread enters the **Runnable** state. It is ready to run and waits for the CPU.

```java
t.start();
```

The JVM's thread scheduler decides when the thread gets CPU time.

### 3. Running

When the thread scheduler selects a runnable thread, it starts executing its `run()` method. The thread is then considered to be **running**.

```java
public void run() {
    // thread task
}
```

### 4. Waiting / Timed Waiting

A running thread may temporarily stop executing because it is waiting for another thread or for a specified period of time.

Methods such as:

* `wait()`
* `sleep()`
* `join()`

can cause a thread to wait.

After the required condition is satisfied, the thread can become **Runnable** again.

### 5. Blocked

A thread enters the **Blocked** state when it is waiting to acquire a lock, usually to enter a synchronized section.

After the lock becomes available, it returns to the **Runnable** state.

### 6. Terminated (Dead)

When the `run()` method completes, or the thread terminates because of an uncaught exception, the thread enters the **Terminated** state.

A terminated thread cannot be restarted.

---

# Thread Life Cycle Diagram

```text
                    start()
        +--------------------------+
        |                          |
        v                          |
     +-------+                +-----------+
     |  NEW  |--------------->| RUNNABLE  |
     +-------+                +-----------+
                                  |
                                  | Scheduler
                                  v
                            +-----------+
                            | RUNNING   |
                            +-----------+
                              /   |    \
                             /    |     \
                       sleep()   wait()  lock unavailable
                           |       |          |
                           v       v          v
                    +----------------+    +---------+
                    | TIMED WAITING  |    | BLOCKED |
                    +----------------+    +---------+
                           |                 |
                           +------->---------+
                                  |
                                  v
                              RUNNABLE
                                  |
                                  |
                           run() completes
                                  |
                                  v
                           +-------------+
                           | TERMINATED  |
                           +--------------
------------------------------------------------------------------------------------------------
question 7:
What is a package ? Explain how you
can create your own package in Java.
What are the different types of packages in
Java ?

# Package in Java

## Definition

A **package** in Java is a collection of related **classes, interfaces, and sub-packages**. It is used to organize Java programs and avoid naming conflicts.

Packages provide **code organization, reusability, and access protection**.

Examples of commonly used Java packages are `java.lang`, `java.util`, `java.io`, etc.

---

# How to Create Your Own Package

We can create a user-defined package using the **`package` keyword**.

### Step 1: Create a Java class with a package declaration

```java
package mypackage;

public class Student {

    public void display() {
        System.out.println("Hello from my package");
    }
}
```

Save this file as:

```text
Student.java
```

### Step 2: Compile the class

```text
javac -d . Student.java
```

The `-d .` option creates the required package directory.

The structure will be:

```text
mypackage
   |
   └── Student.class
```

### Step 3: Use the user-defined package

Create another Java file:

```java
import mypackage.Student;

public class Main {

    public static void main(String[] args) {

        Student s = new Student();

        s.display();
    }
}
```

### Output

```text
Hello from my package
```

Here, `mypackage` is a **user-defined package**, and the `Student` class belongs to that package.

---

# Types of Packages in Java

There are mainly **two types of packages** in Java:

## 1. Built-in Packages

Built-in packages are packages that are already provided by Java. They contain classes and interfaces that can be directly used by programmers.

Examples:

| Package     | Use                                              |
| ----------- | ------------------------------------------------ |
| `java.lang` | Basic classes such as `String`, `Math`, `System` |
| `java.util` | Utility classes such as `Scanner`, `ArrayList`   |
| `java.io`   | Input and output operations                      |
| `java.net`  | Networking                                       |
| `java.sql`  | Database connectivity                            |
| `java.awt`  | GUI and graphics                                 |

Example:

```java
import java.util.Scanner;
```

---

## 2. User-Defined Packages

User-defined packages are packages **created by the programmer** to organize their own classes and interfaces.

Example:

```java
package mypackage;

public class Student {
    public void show() {
        System.out.println("Student class");
    }
}
```

The package can then be imported into another program:

```java
import mypackage.Student;
```

---

# Advantages of Packages

1. **Organize classes** in a systematic way.
2. **Avoid naming conflicts** between classes.
3. Provide **access protection**.
4. Make code easier to **maintain and reuse**.
5. Allow related classes and interfaces to be grouped together.

## Conclusion

A package is a group of related Java classes and interfaces. Java provides **built-in packages**, while programmers can also create **user-defined packages** using the `package` keyword. Packages help in organizing programs, avoiding naming conflicts, and providing access control.
----------------------------------------------------------------------------------------------
question 8:
(b) What is an Exception ? What are the
different types of Exceptions ? Explain the
need of exception handling in Java. Also,
explain how exceptions, which are “checked
by compiler”, are handled with the help of
an example

## (b) Exception and Exception Handling in Java

### 1. What is an Exception?

An **exception** is an abnormal or unexpected event that occurs during the execution of a program and interrupts the normal flow of the program.

For example, dividing a number by zero or trying to open a file that does not exist can cause an exception.

**Example:**

```java
int a = 10 / 0;
```

This statement causes an `ArithmeticException`.

---

### 2. Types of Exceptions

Exceptions in Java are mainly divided into two types:

#### (i) Checked Exceptions

Checked exceptions are **checked by the compiler at compile time**. The programmer must handle them using `try-catch` or declare them using `throws`.

Examples:

* `IOException`
* `FileNotFoundException`
* `SQLException`
* `ClassNotFoundException`

#### (ii) Unchecked Exceptions

Unchecked exceptions are **not checked by the compiler at compile time**. They generally occur during program execution.

Examples:

* `ArithmeticException`
* `NullPointerException`
* `ArrayIndexOutOfBoundsException`
* `NumberFormatException`

---

### 3. Need for Exception Handling

Exception handling is required in Java for the following reasons:

1. It prevents the **abnormal termination** of a program.
2. It maintains the **normal flow of program execution**.
3. It allows errors to be handled in a **systematic manner**.
4. It provides meaningful **error messages** to the user.
5. It separates **error-handling code** from normal program code.
6. It makes programs more **reliable and robust**.

Java provides keywords such as `try`, `catch`, `finally`, `throw`, and `throws` for exception handling.

---

### 4. Handling Checked Exceptions

Since checked exceptions are checked by the compiler, they must be either:

* handled using a `try-catch` block, or
* declared using the `throws` keyword.

### Example:

```java
import java.io.FileReader;
import java.io.FileNotFoundException;

public class Main {
    public static void main(String[] args) {

        try {
            FileReader file = new FileReader("data.txt");
            System.out.println("File opened successfully");
        }
        catch (FileNotFoundException e) {
            System.out.println("File not found");
        }
    }
}
```

### Explanation:

* `FileReader` is used to open a file.
* If `data.txt` does not exist, `FileNotFoundException` occurs.
* Since `FileNotFoundException` is a **checked exception**, the compiler requires it to be handled.
* The `try` block contains the code that may generate the exception.
* The `catch` block handles the exception and displays an appropriate message.

### Output:

If the file does not exist:

```text
File not found
```

### Conclusion

Exception handling is an important feature of Java that helps to handle runtime problems in a controlled manner. **Checked exceptions must be caught or declared using `throws`**, which ensures that such errors are properly handled by the programmer.
------------------------------------------------------------------------------------------
question 9:
 What is JDBC ? Briefly explain the core
components of JDBC. Write and explain
necessary steps to create a JDBC
application.

# JDBC (Java Database Connectivity)

## 1. What is JDBC?

**JDBC stands for Java Database Connectivity.** It is a standard Java API used to connect Java applications with databases.

JDBC allows a Java program to:

* Establish a connection with a database.
* Execute SQL queries and commands.
* Retrieve data from the database.
* Insert, update and delete records.
* Process the results returned by the database.

JDBC provides database-independent connectivity, so a Java application can work with databases such as MySQL, Oracle, PostgreSQL, etc., using suitable JDBC drivers.

---

## 2. Core Components of JDBC

The important components of JDBC are:

### (i) JDBC API

It provides classes and interfaces such as `Connection`, `Statement`, `PreparedStatement`, and `ResultSet` for database operations.

### (ii) JDBC Driver

A JDBC driver is software that enables Java applications to communicate with a particular database.

### (iii) DriverManager

`DriverManager` manages JDBC drivers and helps establish a connection between the Java application and database.

### (iv) Connection

The `Connection` object represents a connection between the Java application and the database.

### (v) Statement

`Statement` is used to execute SQL statements.

Example:

```java
Statement st = con.createStatement();
```

### (vi) ResultSet

`ResultSet` stores the data returned by a `SELECT` query and allows the program to read the records.

---

## 3. Steps to Create a JDBC Application

The following steps are generally required:

### Step 1: Import JDBC Packages

Import the required JDBC classes.

```java
import java.sql.*;
```

### Step 2: Load/Register the JDBC Driver

The JDBC driver is loaded so that Java can communicate with the database.

```java
Class.forName("com.mysql.cj.jdbc.Driver");
```

### Step 3: Establish Database Connection

Use `DriverManager.getConnection()` to connect to the database.

```java
Connection con = DriverManager.getConnection(
    "jdbc:mysql://localhost:3306/studentdb",
    "root",
    "password"
);
```

### Step 4: Create Statement

Create a `Statement` object to execute SQL queries.

```java
Statement st = con.createStatement();
```

### Step 5: Execute SQL Query

Execute the required SQL query.

```java
ResultSet rs = st.executeQuery("SELECT * FROM student");
```

### Step 6: Process the Result

Use `ResultSet` to read the records.

```java
while (rs.next()) {
    System.out.println(rs.getInt("id"));
    System.out.println(rs.getString("name"));
}
```

### Step 7: Close the Connection

Finally, close the database connection and other resources.

```java
con.close();
```

---

## 4. Example of JDBC Application

```java
import java.sql.*;

public class Main {
    public static void main(String[] args) {

        try {
            // Load JDBC driver
            Class.forName("com.mysql.cj.jdbc.Driver");

            // Establish connection
            Connection con = DriverManager.getConnection(
                "jdbc:mysql://localhost:3306/studentdb",
                "root",
                "password"
            );

            // Create statement
            Statement st = con.createStatement();

            // Execute query
            ResultSet rs = st.executeQuery(
                "SELECT * FROM student"
            );

            // Display records
            while (rs.next()) {
                System.out.println(
                    rs.getInt("id") + " " +
                    rs.getString("name")
                );
            }

            // Close connection
            con.close();

        } catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

### Conclusion

JDBC provides a standard mechanism for connecting Java applications with databases. The main steps are **loading the driver, establishing a connection, creating a statement, executing SQL, processing the result, and closing the connection**.
----------------------------------------------------------------------------------------
question 10:

