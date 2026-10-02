# Java Data Types & Wrapper Classes — Deep Study Notes

## 1. Primitive Data Types in Java

Java has **8 primitive data types**:

1. `byte`
2. `short`
3. `int`
4. `long`
5. `float`
6. `double`
7. `char`
8. `boolean`

A primitive data type is a **basic data type built into Java**. It stores a value directly.

Example:

```java
int age = 25;
```

Here:

* `int` = data type
* `age` = variable
* `25` = value

---

# 2. What is a Wrapper Class?

For every primitive data type, Java provides a corresponding **Wrapper Class**.

The wrapper class represents the primitive value as an object and also provides useful constants and methods.

### Primitive → Wrapper

| Primitive | Wrapper Class |
| --------- | ------------- |
| `byte`    | `Byte`        |
| `short`   | `Short`       |
| `int`     | `Integer`     |
| `long`    | `Long`        |
| `float`   | `Float`       |
| `double`  | `Double`      |
| `char`    | `Character`   |
| `boolean` | `Boolean`     |

### Easy way to remember

```text
byte    → Byte
short   → Short
int     → Integer
long    → Long
float   → Float
double  → Double
char    → Character
boolean → Boolean
```

⚠️ Notice:

`int → Integer`, **not** `Int`

`char → Character`, **not** `Char`

---

# 3. Why are Wrapper Classes useful?

Wrapper classes provide predefined constants that tell us information about primitive types.

For example, `Integer` provides:

```java
Integer.MIN_VALUE
Integer.MAX_VALUE
Integer.BYTES
Integer.SIZE
```

These tell us:

* minimum value
* maximum value
* number of bytes
* number of bits

---

# 4. MIN_VALUE

`MIN_VALUE` gives information about the minimum value associated with a numeric type.

Example:

```java
System.out.println(Integer.MIN_VALUE);
```

Output:

```text
-2147483648
```

So the minimum `int` value is:

**-2,147,483,648**

---

# 5. MAX_VALUE

`MAX_VALUE` gives the maximum value of a numeric type.

Example:

```java
System.out.println(Integer.MAX_VALUE);
```

Output:

```text
2147483647
```

Therefore:

**int range = -2,147,483,648 to 2,147,483,647**

---

# 6. BYTES

`BYTES` tells us how many **bytes** are used by the primitive type.

Example:

```java
System.out.println(Integer.BYTES);
```

Output:

```text
4
```

Therefore:

**int = 4 bytes**

---

# 7. SIZE

`SIZE` tells us the number of **bits**.

Example:

```java
System.out.println(Integer.SIZE);
```

Output:

```text
32
```

Because:

**1 byte = 8 bits**

Therefore:

**4 bytes × 8 = 32 bits**

---

# 8. Important Data Type Table

| Data Type | Wrapper     |             Bytes | Bits | Range / Values    |
| --------- | ----------- | ----------------: | ---: | ----------------- |
| `byte`    | `Byte`      |                 1 |    8 | -128 to 127       |
| `short`   | `Short`     |                 2 |   16 | -32,768 to 32,767 |
| `int`     | `Integer`   |                 4 |   32 | -2³¹ to 2³¹−1     |
| `long`    | `Long`      |                 8 |   64 | -2⁶³ to 2⁶³−1     |
| `float`   | `Float`     |                 4 |   32 | Floating-point    |
| `double`  | `Double`    |                 8 |   64 | Floating-point    |
| `char`    | `Character` |                 2 |   16 | 0 to 65,535       |
| `boolean` | `Boolean`   | Not fixed by Java |    — | `true` / `false`  |

---

# 9. How is byte range calculated?

This is important for understanding rather than memorizing.

For a **signed n-bit integer**:

```text
Minimum = -2^(n-1)
Maximum = 2^(n-1) - 1
```

### byte

`byte` has **8 bits**.

Therefore:

```text
Minimum = -2^7
         = -128

Maximum = 2^7 - 1
         = 127
```

So:

```text
byte = -128 to 127
```

---

# 10. short Range

`short` = 16 bits.

```text
Minimum = -2^15
         = -32768

Maximum = 2^15 - 1
         = 32767
```

Therefore:

```text
short = -32768 to 32767
```

---

# 11. int Range

`int` = 32 bits.

```text
Minimum = -2^31
Maximum = 2^31 - 1
```

Therefore:

```text
-2147483648 to 2147483647
```

---

# 12. long Range

`long` = 64 bits.

```text
Minimum = -2^63
Maximum = 2^63 - 1
```

Therefore:

```text
-9223372036854775808
to
9223372036854775807
```

---

# 13. Character Data Type

`char` is different from integer types.

Java `char` uses **16 bits (2 bytes)** and represents a UTF-16 code unit.

Example:

```java
char ch = 'A';
```

Wrapper class:

```java
Character
```

You can check:

```java
Character.MIN_VALUE
Character.MAX_VALUE
Character.BYTES
Character.SIZE
```

The range of a Java `char` is:

```text
\u0000 to \uFFFF
```

Numerically:

```text
0 to 65535
```

### Important

`char` is **unsigned**.

So unlike `byte`, it does not have negative values.

---

# 14. Boolean Data Type

`boolean` can contain only two logical values:

```java
true
false
```

Example:

```java
boolean isPassed = true;
```

Wrapper class:

```java
Boolean
```

It provides:

```java
Boolean.TRUE
Boolean.FALSE
```

But don't write:

```java
Boolean.MIN_VALUE
Boolean.MAX_VALUE
Boolean.BYTES
```

These are not available.

### Why?

Java language specification does not define a fixed storage size for `boolean`.

So don't say:

> boolean always takes 1 byte.

That's a common misconception.

The safe exam answer is:

> **Java does not specify a fixed size for the boolean type. It can represent only true or false.**

---

# 15. Important Point About Float

This is a very important correction to understand.

You may see:

```java
Float.MIN_VALUE
```

and assume it means:

> "Most negative float value."

❌ That's wrong.

For floating-point types, `MIN_VALUE` means the **smallest positive non-zero value**.

For `Float`:

```java
Float.MIN_VALUE
```

is approximately:

```text
1.4 × 10^-45
```

while:

```java
-Float.MAX_VALUE
```

is approximately:

```text
-3.4 × 10^38
```

So:

### Integer

`MIN_VALUE` → most negative value

### Floating point

`MIN_VALUE` → smallest positive non-zero value

This distinction is very useful in interviews.

---

# 16. Example Program

You can check the size and range of a data type using its wrapper class.

```java
public class DataSizeRange {
    public static void main(String[] args) {

        System.out.println("Int Minimum Value: " + Integer.MIN_VALUE);
        System.out.println("Int Maximum Value: " + Integer.MAX_VALUE);
        System.out.println("Int Bytes: " + Integer.BYTES);
        System.out.println("Int Bits: " + Integer.SIZE);
    }
}
```

Output:

```text
Int Minimum Value: -2147483648
Int Maximum Value: 2147483647
Int Bytes: 4
Int Bits: 32
```

---

# 17. Example for byte

```java
public class DataSizeRange {
    public static void main(String[] args) {

        System.out.println("Byte Minimum Value: " + Byte.MIN_VALUE);
        System.out.println("Byte Maximum Value: " + Byte.MAX_VALUE);
        System.out.println("Byte Bytes: " + Byte.BYTES);
        System.out.println("Byte Bits: " + Byte.SIZE);
    }
}
```

Output:

```text
Byte Minimum Value: -128
Byte Maximum Value: 127
Byte Bytes: 1
Byte Bits: 8
```

---

# 18. What does `Integer.MIN_VALUE` actually mean?

Break it into parts:

```java
Integer.MIN_VALUE
```

### `Integer`

Wrapper class for `int`.

### `MIN_VALUE`

A predefined constant inside the `Integer` class.

Therefore:

```text
Integer.MIN_VALUE
        ↓
minimum value of int
```

Similarly:

```java
Integer.MAX_VALUE
```

means maximum value of `int`.

And:

```java
Integer.BYTES
```

means number of bytes used by `int`.

---

# 19. Why is it called a Wrapper?

Think of it like this:

```text
        Wrapper Class
      ┌───────────────┐
      │   Integer     │
      │               │
      │ int value     │
      │ MIN_VALUE     │
      │ MAX_VALUE     │
      │ BYTES         │
      │ SIZE          │
      └───────────────┘
             ↓
            int
```

The class provides additional functionality around the primitive type.

---

# 20. Primitive vs Wrapper Class

| Primitive              | Wrapper                        |
| ---------------------- | ------------------------------ |
| `int`                  | `Integer`                      |
| Basic data type        | Class                          |
| Stores primitive value | Object can represent the value |
| Does not have methods  | Has methods and constants      |
| `int x = 10;`          | `Integer x = 10;`              |

Example:

```java
int a = 10;
Integer b = 10;
```

Both represent the value `10`, but they are different Java types.

---

# 21. Autoboxing and Unboxing

This is related to wrapper classes and is **important for deeper study**.

### Autoboxing

Converting primitive → wrapper automatically.

```java
int a = 10;
Integer b = a;
```

Java automatically converts:

```text
int → Integer
```

This is called **autoboxing**.

---

### Unboxing

Converting wrapper → primitive automatically.

```java
Integer a = 10;
int b = a;
```

Java converts:

```text
Integer → int
```

This is called **unboxing**.

---

# 22. Wrapper Classes and `java.lang`

The wrapper classes are available in the `java.lang` package.

Examples:

```java
java.lang.Integer
java.lang.Byte
java.lang.Short
java.lang.Long
java.lang.Float
java.lang.Double
java.lang.Character
java.lang.Boolean
```

Because `java.lang` is automatically imported, normally you can simply write:

```java
Integer
```

instead of:

```java
java.lang.Integer
```

---

# 23. `javap` Command

The video also introduces the command:

```text
javap
```

`javap` is a Java class-file disassembler/tool that can display information about a compiled class.

For example:

```text
javap java.lang.Integer
```

It can show members of the `Integer` class.

You may see constants such as:

```text
MIN_VALUE
MAX_VALUE
BYTES
SIZE
```

This helps us understand what is available inside the class.

---

# 24. Most Important Things to Remember

### Remember these 8 pairs:

```text
byte    → Byte
short   → Short
int     → Integer
long    → Long
float   → Float
double  → Double
char    → Character
boolean → Boolean
```

### Remember sizes:

```text
byte    = 1 byte
short   = 2 bytes
int     = 4 bytes
long    = 8 bytes

float   = 4 bytes
double  = 8 bytes

char    = 2 bytes
boolean = no fixed size specified by Java
```

---

# 25. Common Interview Questions

### Q1. What is a wrapper class?

**Answer:**

> A wrapper class is a class that represents a primitive data type as an object and provides useful methods and constants. For example, `Integer` is the wrapper class for `int`.

---

### Q2. What is the wrapper class of int?

> `Integer`

---

### Q3. What is the wrapper class of char?

> `Character`

---

### Q4. How do you find the minimum value of int?

```java
Integer.MIN_VALUE
```

---

### Q5. How do you find the maximum value of int?

```java
Integer.MAX_VALUE
```

---

### Q6. How do you find the size of int?

```java
Integer.BYTES
```

or

```java
Integer.SIZE
```

`BYTES` gives **bytes**, while `SIZE` gives **bits**.

---

### Q7. How many bytes does int take?

> 4 bytes.

---

### Q8. How many bits does int take?

> 32 bits.

---

### Q9. Does Boolean have MIN_VALUE and MAX_VALUE?

> No. Boolean has only `TRUE` and `FALSE`; `MIN_VALUE` and `MAX_VALUE` are not defined for it.

---

### Q10. Is boolean always 1 byte?

> No. Java does not specify a fixed storage size for `boolean`.

---

# ⭐ Final Mental Map

```text
                 JAVA DATA TYPES
                       |
             ┌─────────┴─────────┐
             |                   |
         Primitive            Wrapper
             |                   |
          int  ─────────────→ Integer
          byte ─────────────→ Byte
          short ────────────→ Short
          long ─────────────→ Long
          float ────────────→ Float
          double ───────────→ Double
          char ─────────────→ Character
          boolean ──────────→ Boolean
                                |
                    ┌───────────┼───────────┐
                    ↓           ↓           ↓
               MIN_VALUE   MAX_VALUE     BYTES
                                            |
                                      SIZE → bits
```

**Core idea:**
`Primitive → Wrapper Class → useful constants`

For example:

```java
Integer.MIN_VALUE   // minimum int value
Integer.MAX_VALUE   // maximum int value
Integer.BYTES       // 4
Integer.SIZE        // 32
```

This is the main concept you should understand from the video.
