# Language Fundamentals - Reserved Words in Java

## 1. Reserved Words for Data Types

### byte
- **Size**: 1 byte (8 bits)
- **Range**: -128 to 127
- **Use**: When memory optimization is important
```java
byte age = 25;
byte temperature = -10;
```

### short
- **Size**: 2 bytes (16 bits)
- **Range**: -32,768 to 32,767
- **Use**: When you need a number larger than byte but smaller than int
```java
short year = 2024;
short salary = 30000;
```

### int
- **Size**: 4 bytes (32 bits)
- **Range**: -2^31 to 2^31-1
- **Use**: Most commonly used integer type
```java
int population = 1000000;
int count = 42;
```

### long
- **Size**: 8 bytes (64 bits)
- **Range**: -2^63 to 2^63-1
- **Use**: When int range is insufficient
```java
long distanceToSun = 149600000L; // Note the 'L' suffix
long worldPopulation = 8000000000L;
```

### float
- **Size**: 4 bytes (32 bits)
- **Precision**: ~6-7 decimal digits
- **Use**: Decimal numbers with less precision
```java
float pi = 3.14f; // Note the 'f' suffix
float price = 19.99f;
```

### double
- **Size**: 8 bytes (64 bits)
- **Precision**: ~15 decimal digits
- **Use**: Default choice for decimal numbers
```java
double salary = 55000.75;
double scientificValue = 1.23e-10;
```

### char
- **Size**: 2 bytes (16 bits)
- **Range**: 0 to 65,535 (Unicode characters)
- **Use**: Single character storage
```java
char grade = 'A';
char symbol = '$';
char unicode = '\u0041'; // 'A'
```

### boolean
- **Size**: Not precisely defined (typically 1 bit)
- **Values**: true or false
- **Use**: Logical operations and conditions
```java
boolean isActive = true;
boolean hasPermission = false;
```

---

## 2. Reserved Words for Flow Control

### if
- **Use**: Conditional execution
```java
int age = 18;
if (age >= 18) {
    System.out.println("Adult");
}
```

### else
- **Use**: Alternative execution path
```java
if (age >= 18) {
    System.out.println("Adult");
} else {
    System.out.println("Minor");
}
```

### switch
- **Use**: Multi-way branching
```java
int day = 2;
switch (day) {
    case 1:
        System.out.println("Monday");
        break;
    case 2:
        System.out.println("Tuesday");
        break;
    default:
        System.out.println("Other day");
}
```

### case
- **Use**: Individual cases in switch statement
- See switch example above

### default
- **Use**: Default case when no case matches
- See switch example above

### for
- **Use**: Loop with initialization, condition, and increment
```java
for (int i = 0; i < 5; i++) {
    System.out.println("Count: " + i);
}

// Enhanced for loop
int[] numbers = {1, 2, 3, 4, 5};
for (int num : numbers) {
    System.out.println(num);
}
```

### do
- **Use**: Execute at least once, then check condition
```java
int i = 0;
do {
    System.out.println("Count: " + i);
    i++;
} while (i < 5);
```

### while
- **Use**: Loop while condition is true
```java
int count = 0;
while (count < 5) {
    System.out.println("Count: " + count);
    count++;
}
```

### break
- **Use**: Exit from loop or switch
```java
for (int i = 0; i < 10; i++) {
    if (i == 5) {
        break; // Exits the loop when i is 5
    }
    System.out.println(i);
}
```

### continue
- **Use**: Skip current iteration and continue with next
```java
for (int i = 0; i < 10; i++) {
    if (i % 2 == 0) {
        continue; // Skip even numbers
    }
    System.out.println(i); // Prints only odd numbers
}
```

### return
- **Use**: Exit method and optionally return a value
```java
public int add(int a, int b) {
    return a + b;
}

public void printMessage() {
    System.out.println("Hello");
    return; // Optional for void methods
}
```

---

## 3. Keywords for Modifiers

### public
- **Use**: Accessible from anywhere
```java
public class MyClass {
    public int publicVariable = 10;
    
    public void publicMethod() {
        System.out.println("Public method");
    }
}
```

### private
- **Use**: Accessible only within the same class
```java
public class BankAccount {
    private double balance;
    
    private void validateTransaction() {
        // Only accessible within this class
    }
}
```

### protected
- **Use**: Accessible within package and by subclasses
```java
public class Parent {
    protected int protectedValue = 100;
    
    protected void protectedMethod() {
        // Accessible in subclasses
    }
}
```

### static
- **Use**: Belongs to class rather than instance
```java
public class MathUtils {
    static int count = 0;
    
    static int add(int a, int b) {
        return a + b;
    }
}
// Usage: MathUtils.add(5, 3);
```

### final
- **Use**: Cannot be changed (constant), method cannot be overridden, class cannot be extended
```java
final int MAX_VALUE = 100; // Constant
final class FinalClass { } // Cannot be extended

class Parent {
    final void finalMethod() { } // Cannot be overridden
}
```

### abstract
- **Use**: Incomplete class or method that must be implemented
```java
abstract class Animal {
    abstract void makeSound(); // No implementation
    
    void sleep() {
        System.out.println("Sleeping...");
    }
}

class Dog extends Animal {
    void makeSound() {
        System.out.println("Bark!");
    }
}
```

### synchronized
- **Use**: Thread-safe access to methods or blocks
```java
public class Counter {
    private int count = 0;
    
    public synchronized void increment() {
        count++; // Thread-safe increment
    }
}
```

### native
- **Use**: Method implemented in native code (C/C++)
```java
public class NativeExample {
    public native void nativeMethod();
    
    static {
        System.loadLibrary("nativeLib");
    }
}
```

### strictfp (since 1.2)
- **Use**: Ensures floating-point calculations are consistent across platforms
```java
public strictfp class StrictCalculation {
    double calculate() {
        return 10.5 * 2.3;
    }
}
```

### transient
- **Use**: Field is not serialized
```java
class User implements Serializable {
    String username;
    transient String password; // Not serialized
}
```

### volatile
- **Use**: Variable value may be modified by different threads
```java
public class SharedResource {
    private volatile boolean flag = true;
    
    public void stop() {
        flag = false; // Immediately visible to all threads
    }
}
```

---

## 4. Keywords for Exception Handling

### try
- **Use**: Block of code that might throw an exception
```java
try {
    int result = 10 / 0;
} catch (ArithmeticException e) {
    System.out.println("Cannot divide by zero");
}
```

### catch
- **Use**: Handle specific exception
```java
try {
    int[] arr = new int[5];
    arr[10] = 50;
} catch (ArrayIndexOutOfBoundsException e) {
    System.out.println("Index out of bounds: " + e.getMessage());
}
```

### finally
- **Use**: Code that always executes, regardless of exception
```java
try {
    // Risky code
    FileReader file = new FileReader("test.txt");
} catch (IOException e) {
    System.out.println("Error reading file");
} finally {
    System.out.println("This always executes");
    // Close resources here
}
```

### throw
- **Use**: Manually throw an exception
```java
public void checkAge(int age) {
    if (age < 18) {
        throw new IllegalArgumentException("Age must be 18 or above");
    }
}
```

### throws
- **Use**: Declare that method may throw exception
```java
public void readFile(String filename) throws IOException {
    FileReader file = new FileReader(filename);
    // File operations
}
```

### assert (since 1.4)
- **Use**: Test assumptions during development
```java
public void setAge(int age) {
    assert age >= 0 : "Age cannot be negative";
    this.age = age;
}
// Run with: java -ea YourClass (enable assertions)
```

---

## 5. Class Related Keywords

### class
- **Use**: Define a class
```java
public class Student {
    String name;
    int rollNumber;
    
    void displayInfo() {
        System.out.println("Name: " + name);
    }
}
```

### package
- **Use**: Group related classes
```java
package com.example.myapp;

public class MyClass {
    // Class definition
}
```

### import
- **Use**: Use classes from other packages
```java
import java.util.ArrayList;
import java.util.*;

public class MyClass {
    ArrayList<String> list = new ArrayList<>();
}
```

### extends
- **Use**: Inherit from a class
```java
class Animal {
    void eat() {
        System.out.println("Eating...");
    }
}

class Dog extends Animal {
    void bark() {
        System.out.println("Barking...");
    }
}
```

### implements
- **Use**: Implement an interface
```java
interface Drawable {
    void draw();
}

class Circle implements Drawable {
    public void draw() {
        System.out.println("Drawing Circle");
    }
}
```

### interface
- **Use**: Define a contract that classes must follow
```java
interface Vehicle {
    void start();
    void stop();
    
    default void honk() {
        System.out.println("Honk!");
    }
}

class Car implements Vehicle {
    public void start() {
        System.out.println("Car starting...");
    }
    
    public void stop() {
        System.out.println("Car stopping...");
    }
}
```

---

## 6. Object Related Keywords

### new
- **Use**: Create new object instance
```java
Student student = new Student();
ArrayList<String> list = new ArrayList<>();
int[] array = new int[10];
```

### instanceof
- **Use**: Check if object is instance of a class
```java
String str = "Hello";
if (str instanceof String) {
    System.out.println("str is a String");
}

Animal animal = new Dog();
if (animal instanceof Dog) {
    Dog dog = (Dog) animal;
}
```

### super
- **Use**: Reference parent class
```java
class Animal {
    String name = "Animal";
    
    void display() {
        System.out.println("I am an animal");
    }
}

class Dog extends Animal {
    String name = "Dog";
    
    void display() {
        super.display(); // Calls parent method
        System.out.println("Parent name: " + super.name);
        System.out.println("My name: " + this.name);
    }
}
```

### this
- **Use**: Reference current object
```java
class Student {
    String name;
    int age;
    
    Student(String name, int age) {
        this.name = name; // Distinguish from parameter
        this.age = age;
    }
    
    void setName(String name) {
        this.name = name;
    }
    
    Student getSelf() {
        return this; // Return current object
    }
}
```

---

## Summary Table

| Category | Keywords | Count |
|----------|----------|-------|
| Data Types | byte, short, int, long, float, double, char, boolean | 8 |
| Flow Control | if, else, switch, case, default, for, do, while, break, continue, return | 11 |
| Modifiers | public, private, protected, static, final, abstract, synchronized, native, strictfp, transient, volatile | 11 |
| Exception Handling | try, catch, finally, throw, throws, assert | 6 |
| Class Related | class, package, import, extends, implements, interface | 6 |
| Object Related | new, instanceof, super, this | 4 |
| **Total** | | **46** |

## Additional Notes

### Reserved Words vs Keywords
- All keywords are reserved words
- Reserved words also include: `const`, `goto` (reserved but not used)
- Literals like `true`, `false`, `null` are also reserved

### Naming Conventions
- Cannot use reserved words as identifiers (variable names, method names, class names)
- Java is case-sensitive: `int` is a keyword, but `Int` is a valid identifier

### Version-Specific Keywords
- `assert` - Added in Java 1.4
- `strictfp` - Added in Java 1.2
- `enum` - Added in Java 5.0 (not in your list but important)
