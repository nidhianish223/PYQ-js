question 1: 
Briefly discuss the concept of dynamic
binding with a suitable example.

## Dynamic Binding in Java

**Dynamic binding** is a mechanism in Java in which the method to be executed is determined at **runtime** rather than at compile time. It is also known as **late binding** or **runtime binding**.

Dynamic binding mainly occurs when **method overriding** is used. A superclass reference variable refers to an object of a subclass, and the overridden method of the actual object is executed.

### Example:

```java
class Animal {
    void sound() {
        System.out.println("Animal makes a sound");
    }
}

class Dog extends Animal {
    @Override
    void sound() {
        System.out.println("Dog barks");
    }
}

class Main {
    public static void main(String[] args) {

        Animal a = new Dog();

        a.sound();
    }
}
```

### Output:

```text
Dog barks
```

### Explanation:

In the statement:

```java
Animal a = new Dog();
```

`a` is a reference variable of the **Animal** class, but it refers to an object of the **Dog** class.

When the statement:

```java
a.sound();
```

is executed, Java determines at runtime that the actual object is a `Dog`. Therefore, the overridden `sound()` method of the `Dog` class is called.

Thus, the method execution depends on the **actual object at runtime**, not on the reference type.

### Advantages of Dynamic Binding

1. It supports **runtime polymorphism**.
2. It provides flexibility in object-oriented programming.
3. It allows a superclass reference to refer to different subclass objects.
4. It makes programs easier to extend and maintain.

### Conclusion

Therefore, dynamic binding is an important feature of Java that allows the appropriate overridden method to be selected **during runtime**. It is mainly achieved through **method overriding and inheritance**.
-------------------------------------------------------------------------------------------------------------------------------------------
question 2 :
Illustrate the execution of while loop and
do---while loop with suitable code in Java
for each.
 While Loop and Do-While Loop in Java
### 1. While Loop
A **while loop** is used to repeat a set of statements as long as the given condition is **true**.

**Syntax:**

```java
while (condition) {
    // statements
}
```

**Example:**

```java
class Main {
    public static void main(String[] args) {

        int i = 1;

        while (i <= 5) {
            System.out.println(i);
            i++;
        }
    }
}
```

**Output:**

```text
1
2
3
4
5
```

**Execution:**

1. `i` is initialized to `1`.
2. Java checks `i <= 5`.
3. If the condition is true, the statement is executed.
4. `i++` increases the value of `i` by 1.
5. The condition is checked again.
6. When `i` becomes `6`, the condition becomes false and the loop stops.

### 2. Do-While Loop

A **do-while loop** is also used to repeat statements. The main difference is that it **executes the statements at least once** before checking the condition.

**Syntax:**

```java
do {
    // statements
} while (condition);
```

**Example:**

```java
class Main {
    public static void main(String[] args) {

        int i = 1;

        do {
            System.out.println(i);
            i++;
        } while (i <= 5);
    }
}

**Output:**
1
2
3
4
5

**Execution:**

1. `i` is initialized to `1`.
2. The statements inside `do` are executed.
3. `i++` increases the value of `i`.
4. Java checks the condition `i <= 5`.
5. If the condition is true, the loop runs again.
6. When the condition becomes false, the loop stops.

### Difference

| While Loop                                      | Do-While Loop                                |
| ----------------------------------------------- | -------------------------------------------- |
| Condition is checked first.                     | Condition is checked after execution.        |
| It may execute **zero times**.                  | It executes **at least once**.               |
| `while` comes before the statements.            | `do` comes before the statements.            |
| Semicolon is not used after `while(condition)`. | Semicolon is used after `while(condition);`. |

-------------------------------------------------------------------------------------------------------------------------------------
question 3:
What are access specifiers ? Briefly discuss
the purpose of public, private, protected
and default access specifiers.

## Access Specifiers in Java

**Access specifiers** are keywords in Java that decide **who can access a class, variable, method or constructor**.

Java has four main access specifiers:

1. **Public**
2. **Private**
3. **Protected**
4. **Default**

### 1. Public

The `public` access specifier allows a member to be accessed **from anywhere** in the program.

```java
public int marks = 90;
```
It can be accessed from the same class, another class, and another package.

### 2. Private

The `private` access specifier allows a member to be accessed **only inside the same class**.

```java
private int marks = 90;
```
It is mainly used to **protect data** and achieve encapsulation.

### 3. Protected

The `protected` access specifier allows access **within the same package** and also in **child classes** of another package.

```java
protected int marks = 90;
```
It is mainly useful when inheritance is used.

### 4. Default

When no access specifier is written, it is called **default access**.

```java
int marks = 90;
```
Default members can be accessed **only within the same package.

### Conclusion

Access specifiers are used to **control the visibility and accessibility of data and methods** in Java. They help provide **security and encapsulation** in a program.
---------------------------------------------------------------------------------------------------------------------------------------------
question 4:
Compare Hierarchical inheritance with
Multiple inheritance. Give suitable pseudo
code and block diagram for each.

## Compare Hierarchical Inheritance with Multiple Inheritance

**Inheritance** is an important feature of Object-Oriented Programming. It allows one class to use the properties and methods of another class.

### 1. Hierarchical Inheritance

In **hierarchical inheritance**, **one parent class is inherited by two or more child classes**.

For example, `Animal` is the parent class and `Dog` and `Cat` are child classes.

### Block Diagram

```text
                 Animal
                /      \
               /        \
            Dog          Cat
```

### Pseudocode

```text
Class Animal
    sound()
        Print "Animal makes sound"

Class Dog extends Animal
    bark()
        Print "Dog barks"

Class Cat extends Animal
    meow()
        Print "Cat meows"
```

Here, both `Dog` and `Cat` can use the methods of the `Animal` class.

### Example in Java

```java
class Animal {
    void sound() {
        System.out.println("Animal makes sound");
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

---

## 2. Multiple Inheritance

In **multiple inheritance**, **one child class inherits from two or more parent classes**.

For example, a `Child` class may get features from both `Father` and `Mother`.

### Block Diagram

```text
          Father        Mother
             \            /
              \          /
               \        /
                Child
```

### Pseudocode

```text
Class Father
    property1

Class Mother
    property2

Class Child extends Father, Mother
    display()
        Print property1
        Print property2
```

The `Child` class gets features from both `Father` and `Mother`.

### Multiple Inheritance in Java

Java **does not support multiple inheritance using classes**.

For example, this is not allowed:

```java
class Child extends Father, Mother {
}
```

Java avoids this because if both parent classes have the same method, it may create confusion about which method should be called.

However, Java supports multiple inheritance through **interfaces**.

---

## Difference between Hierarchical and Multiple Inheritance

| Hierarchical Inheritance                                   | Multiple Inheritance                                               |
| ---------------------------------------------------------- | ------------------------------------------------------------------ |
| One parent class has two or more child classes.            | One child class has two or more parent classes.                    |
| Structure is **one-to-many**.                              | Structure is **many-to-one**.                                      |
| Example: `Animal → Dog, Cat`                               | Example: `Father + Mother → Child`                                 |
| It uses one common parent class.                           | It uses multiple parent classes.                                   |
| It is supported by Java classes.                           | It is not supported by Java classes.                               |
| It can be implemented using `extends`.                     | It can be achieved in Java using interfaces.                       |
| It is useful when different classes share common features. | It is useful when one class needs features from different sources. |
-------------------------------------------------------------------------------------------------------------------------------------------------
question 4:
Differentiate between overloading and
overriding. Give suitable example for each.

# Differentiate between Overloading and Overriding

**Overloading and overriding are two important concepts of polymorphism in Java.** Although both use the same method name, they are different in their working and purpose.

## 1. Method Overloading

**Method overloading** means defining **more than one method with the same name but different parameters** in the same class.

The parameters may differ in their **number or data type**.

### Example:

```java
class Calculator {

    int add(int a, int b) {
        return a + b;
    }

    int add(int a, int b, int c) {
        return a + b + c;
    }

    public static void main(String[] args) {
        Calculator c = new Calculator();

        System.out.println(c.add(10, 20));
        System.out.println(c.add(10, 20, 30));
    }
}
```

**Output:**
30
60
```
Here, both methods have the name `add`, but they have different numbers of parameters. Therefore, it is called **method overloading**.

---

## 2. Method Overriding

**Method overriding** occurs when a **child class provides its own version of a method that is already defined in the parent class**.

The method name and parameters remain the same.

### Example:

```java
class Animal {

    void sound() {
        System.out.println("Animal makes sound");
    }
}

class Dog extends Animal {

    @Override
    void sound() {
        System.out.println("Dog barks");
    }

    public static void main(String[] args) {
        Dog d = new Dog();
        d.sound();
    }
}
```
**Output:**

```text
Dog barks
```
Here, the `Dog` class provides its own version of the `sound()` method of the `Animal` class. Therefore, it is called **method overriding**.

## Difference between Overloading and Overriding

| Method Overloading                                  | Method Overriding                                                   |
| --------------------------------------------------- | ------------------------------------------------------------------- |
| Same method name with different parameters.         | Same method name with the same parameters.                          |
| Usually occurs in the same class.                   | Occurs between parent and child classes.                            |
| Inheritance is not required.                        | Inheritance is required.                                            |
| It is **compile-time polymorphism**.                | It is **runtime polymorphism**.                                     |
| Parameters must be different.                       | Parameters must be the same.                                        |
| A method can be overloaded several times.           | A child class can override a parent method.                         |
| It provides different ways to perform an operation. | It allows a child class to change the behaviour of a parent method. |
| Example: `add(int,int)` and `add(int,int,int)`.     | Example: `Animal.sound()` and `Dog.sound()`.                        |
-----------------------------------------------------------------------------------------------------------------------------------------------------
question 6:
(f) What are annotations in Java ? Briefly
discuss the purpose of the following, Built-
in Java annotations : 5

(i) @ Override
(ii) @ Suppress Warning
(iii) @ Deprecated

## Annotations in Java

**Annotations** in Java are special instructions or information given to the compiler, JVM, or other tools about a program. They start with the symbol **`@`**.

Annotations do not directly change the main logic of a program. They provide additional information about classes, methods, or variables.

### (i) `@Override`

`@Override` is used when a **child class overrides a method of its parent class**.

It helps the compiler check whether the method is actually overriding a parent method.

**Example:**

```java
class Animal {
    void sound() {
        System.out.println("Animal sound");
    }
}

class Dog extends Animal {
    @Override
    void sound() {
        System.out.println("Dog barks");
    }
}
```

Here, `@Override` tells Java that the `sound()` method in `Dog` is overriding the method of `Animal`.

---

### (ii) `@SuppressWarnings`

`@SuppressWarnings` is used to **tell the compiler not to show certain warnings** for a particular part of the program.

**Example:**

```java
@SuppressWarnings("deprecation")
class Test {
    // code
}
```

It is useful when we know that a warning is safe to ignore.

---

### (iii) `@Deprecated`

`@Deprecated` is used to indicate that a **class, method, or field is old and should not be used in new programs**.

It tells programmers that a better alternative may be available.

**Example:**

```java
class Test {

    @Deprecated
    void oldMethod() {
        System.out.println("Old method");
    }
}
```

When `oldMethod()` is used, the compiler can give a warning that the method is deprecated.
--------------------------------------------------------------------------------------
question 7:
Differentiate between class and interface
in Java.
## Difference between Class and Interface in Java

A **class** and an **interface** are both used to define the structure and behaviour of objects in Java. However, they are used for different purposes.

### Class

A **class** is a blueprint for creating objects. It can contain **variables, methods, constructors, and blocks**. A class can also provide the complete implementation of methods.

### Example of Class

```java
class Student {
    int marks;

    void display() {
        System.out.println("Student details");
    }
}
```

Here, `Student` is a class containing a variable `marks` and a method `display()`.

---

### Interface

An **interface** is used to define a set of methods that a class should implement. It is mainly used to achieve **abstraction** and **multiple inheritance through interfaces**.

### Example of Interface

```java
interface Animal {
    void sound();
}

class Dog implements Animal {
    public void sound() {
        System.out.println("Dog barks");
    }
}
```

Here, `Animal` is an interface and `Dog` implements the `sound()` method.

---

### Difference between Class and Interface

| Class                                                    | Interface                                                                                                                                          
| A class is a blueprint for creating objects.             | An interface defines a set of rules/behaviour for classes.                                                                                         |
| It is declared using the `class` keyword.                | It is declared using the `interface` keyword.                                                                                                      |
| A class can contain variables, methods and constructors. | An interface can contain constants and method declarations, as well as `default` and `static` methods.                                             |
| A class can have constructors.                           | An interface does not have constructors.                                                                                                           |
| A class can provide complete method implementation.      | Traditionally, interfaces mainly contain abstract methods; modern Java also allows `default`, `static`, and `private` methods with implementation. |
| A class is extended using `extends`.                     | An interface is implemented using `implements`.                                                                                                    |
| A class can extend only one class.                       | A class can implement multiple interfaces.                                                                                                         |
| Classes are used to create objects.                      | Interfaces are used mainly to achieve abstraction and define common behaviour.                                                                     |
| A class can have instance variables.                     | Interface fields are implicitly `public`, `static`, and `final`.                                                                                   |
| Example: `class Student`                                 | Example: `interface Animal`                                                                                                  
--------------------------------------------------------------------------
question 8:
Write a program in Java to print the name
of week days, (MON to SUN) when the
user enters the number between 1 to 7.
Support your code with suitable comments.

## Java Program to Print Week Days

The following program accepts a number from **1 to 7** and prints the corresponding day of the week.

```java
import java.util.Scanner;

class WeekDays {
    public static void main(String[] args) {

        // Create Scanner object to take input
        Scanner sc = new Scanner(System.in);

        // Ask the user to enter a number
        System.out.print("Enter a number (1-7): ");
        int n = sc.nextInt();

        // Use switch statement to print the day
        switch (n) {
            case 1:
                System.out.println("MON");
                break;

            case 2:
                System.out.println("TUE");
                break;

            case 3:
                System.out.println("WED");
                break;

            case 4:
                System.out.println("THU");
                break;

            case 5:
                System.out.println("FRI");
                break;

            case 6:
                System.out.println("SAT");
                break;

            case 7:
                System.out.println("SUN");
                break;

            // If number is not between 1 and 7
            default:
                System.out.println("Invalid number");
        }

        sc.close();
    }
}
```

### Sample Output

```text
Enter a number (1-7): 3
WED
```

### Explanation

* `Scanner` is used to take input from the user.
* The user enters a number between **1 and 7**.
* The `switch` statement checks the number.
* Each `case` represents one day.
* `break` stops the execution after the matching case.
* `default` displays **"Invalid number"** if the user enters a number other than 1 to 7.

### Mapping

**1 → MON**
**2 → TUE**
**3 → WED**
**4 → THU**
**5 → FRI**
**6 → SAT**
**7 → SUN**
---------------------------------------------------------------------------------------------
question 9:
Compare the concepts of Final, Finally and
Finalize in Java with example.
# Difference between `final`, `finally` and `finalize()` in Java

`final`, `finally` and `finalize()` are three different concepts in Java. Although their names are similar, their purposes are different.

## 1. `final`

`final` is a **keyword** in Java. It is used to prevent further changes.

It can be used with a **variable, method and class**.

### Example:

```java
class Test {

    final int number = 10;

    void display() {
        System.out.println(number);
    }
}
Here, the value of `number` cannot be changed because it is declared as `final`.

```java
number = 20;    // Error
```
**Uses of `final`:**

* Final variable → value cannot be changed.
* Final method → cannot be overridden.
* Final class → cannot be inherited.
---
## 2. `finally`

`finally` is a **block** used with exception handling.

The `finally` block normally executes whether an exception occurs or not. It is commonly used for **cleanup work**, such as closing resources.

### Example:

```java
class Test {
    public static void main(String[] args) {

        try {
            System.out.println("Try block");
        }
        catch (Exception e) {
            System.out.println("Exception");
        }
        finally {
            System.out.println("Finally block");
        }
    }
}
```
**Output:**
```text
Try block
Finally block
```
## 3. `finalize()`

`finalize()` was a method associated with garbage collection. It could be called by the garbage collector before an object was reclaimed.

### Example:

```java
class Test {

    @Override
    protected void finalize() {
        System.out.println("Object is being destroyed");
    }
}

However, **`finalize()` is deprecated and should not be used in modern Java programs**. It is not a reliable way to perform cleanup.
## Comparison

| `final`                                      | `finally`                                         | `finalize()`                                                           |
| -------------------------------------------- | ------------------------------------------------- | ---------------------------------------------------------------------- |
| It is a **keyword**.                         | It is a **block**.                                | It is a **method**.                                                    |
| Used to restrict changes.                    | Used in exception handling.                       | Historically associated with object cleanup before garbage collection. |
| Can be used with variable, method and class. | Used with `try` and `catch`.                      | Defined as a method in a class.                                        |
| Final variable cannot be changed.            | Finally block is used for cleanup code.           | Not reliable for cleanup.                                              |
| Final method cannot be overridden.           | Usually executes whether exception occurs or not. | Deprecated in modern Java.                                             |
| Final class cannot be inherited.             | Helps execute important cleanup code.             | Should not be used in new Java programs.                               |
--------------------------------------------------------------------------------------------------------------------------------------------------------
question 10:
Explain the use of “Super” keyword in Java
with the help of an example.
## `super` Keyword in Java

The **`super` keyword** in Java is used to refer to the **parent class**.

It is mainly used when a child class wants to access the **variables, methods, or constructor of its parent class**.

### Uses of `super` Keyword

There are three main uses of `super`:

### 1. To access the parent class variable

If the parent and child class have variables with the same name, `super` is used to access the parent class variable.

```java
class Student {
    int marks = 80;
}

class Result extends Student {
    int marks = 90;

    void display() {
        System.out.println(super.marks);
        System.out.println(marks);
    }
}
``
**Output:**
```text
80
90
```
Here, `super.marks` refers to the `marks` variable of the parent class.
---
### 2. To call the parent class method

`super` can be used to call a method of the parent class.

```java
class Animal {
    void sound() {
        System.out.println("Animal makes sound");
    }
}

class Dog extends Animal {

    void sound() {
        super.sound();
        System.out.println("Dog barks");
    }
}
```

**Output:**

```text
Animal makes sound
Dog barks
```

Here, `super.sound()` calls the `sound()` method of the parent class.

---

### 3. To call the parent class constructor

`super()` is used to call the constructor of the parent class.

```java
class Animal {

    Animal() {
        System.out.println("Animal constructor");
    }
}

class Dog extends Animal {

    Dog() {
        super();
        System.out.println("Dog constructor");
    }
}
```

**Output:**

```text
Animal constructor
Dog constructor
```

Here, `super()` calls the constructor of the parent class.

### Important Points

* `super` refers to the **immediate parent class**.
* `super.variable` is used to access the parent class variable.
* `super.method()` is used to call the parent class method.
* `super()` is used to call the parent class constructor.
* `super()` must be the **first statement inside a constructor**.
------------------------------------------------------------------------------------------------
question 10:
Briefly discuss the various states of thread
life cycle. Also draw block diagram for
thread life cycle.
