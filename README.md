# Java Expert Programming Tutorial Guide

**Written by Brian McCarthy**

This repository is a hands-on Java programming guide with Java source examples, interview prep notes, section folders, ZIP-based course/source archives, and Java 8 study material.

## Table of Contents

- [Project File Structure](#project-file-structure)
- [Project Links](#project-links)
- [Java Programming Tutorial Guide](#java-programming-tutorial-guide)
- [Course Section Code Samples S04-S21](#course-section-code-samples-s04-s21)
- [Java Example Files and Explanations](#java-example-files-and-explanations)
- [Interview Questions and PDF](#interview-questions-and-pdf)

## Project File Structure

```text
Java-Expert-Programming-Guide/
├── README.md
├── _Java-Interview-Questions-And-Answers-(Java8).pdf
├── Java-Interview-Questions-And-Answers/
│   ├── basics-class-object.md
│   ├── abstract-class.md
│   ├── arrays.md
│   ├── constructors.md
│   ├── enum.md
│   ├── file-io.md
│   ├── generics.md
│   ├── inheritance-and-polymorphism.md
│   ├── interfaces.md
│   ├── object-methods.md
│   ├── serialization.md
│   ├── threads-and-synchronization.md
│   └── wrapper-classes.md
└── Java-Example-Files/
    ├── LambdaExpressionsTest.java
    ├── arrays/
    ├── basics/
    ├── classmodifiers/
    ├── enums/
    ├── files/
    ├── flow/
    ├── generics/
    ├── membermodifiers/
    ├── object/
    ├── oops/
    ├── operators/
    ├── others/
    ├── serialization/
    ├── string/
    ├── threads/
    ├── variables/
    └── varargs/
```

## Project Links

| Resource | Link |
|---|---|
| Java example source folder | [Java-Example-Files](Java-Example-Files) |
| Java interview notes folder | [Java-Interview-Questions-And-Answers](Java-Interview-Questions-And-Answers) |
| Java 8 interview PDF | [_Java-Interview-Questions-And-Answers-(Java8).pdf](_Java-Interview-Questions-And-Answers-(Java8).pdf) |
| Flow control examples | [Java-Example-Files/flow](Java-Example-Files/flow) |
| OOP examples | [Java-Example-Files/oops](Java-Example-Files/oops) |
| Thread examples | [Java-Example-Files/threads](Java-Example-Files/threads) |
| Generics examples | [Java-Example-Files/generics](Java-Example-Files/generics) |
| Object method examples | [Java-Example-Files/object](Java-Example-Files/object) |

## Java Programming Tutorial Guide

- **Variables:** store typed values in memory. Java separates primitive values such as `int`, `double`, and `boolean` from reference values such as `String`, arrays, and objects.
- **Operators:** transform or compare values. Arithmetic operators produce numeric results, comparison operators produce booleans, and logical operators combine boolean expressions.
- **Conditions:** choose which code path runs. `if`, `else if`, `else`, and `switch` make program behavior data-dependent.
- **Arrays:** store fixed-size indexed collections. Arrays are zero-based, so the first element is at index `0`.
- **Loops:** repeat work. `for` works well when the number of iterations is known; `while` works well when repetition depends on a condition.
- **OOP:** organizes software around classes, objects, encapsulation, inheritance, polymorphism, abstraction, and interfaces.
- **Lambdas:** Java 8 lambda expressions provide concise implementations of functional interfaces.
- **Generics:** enforce compile-time type safety for reusable classes, methods, and collections.
- **Error Handling:** separates normal logic from failure logic using `try`, `catch`, `finally`, and exception types.
- **Spring Boot:** simplifies Java web/API development through auto-configuration, dependency injection, controllers, security, templates, and AOP.

## Course Section Code Samples S04-S21

### S04 - Variables

```java
int quantity = 5;
double price = 19.99;
String productName = "Java Book";
boolean inStock = true;

double total = quantity * price;
System.out.println(productName + " total: $" + total);
System.out.println("Available: " + inStock);
```

**Detailed explanation:** `quantity` is an integer, `price` is a decimal value, `productName` is a reference to a `String` object, and `inStock` is a boolean flag. Java is statically typed, so each variable has a declared type and the compiler checks whether assignments and operations are valid.

**Expected output:**

```text
Java Book total: $99.94999999999999
Available: true
```

**Expected result:** The program calculates `5 * 19.99`. The long decimal is normal floating-point behavior with `double`.

### S05 - Operators

```java
int a = 10;
int b = 3;

System.out.println(a + b);
System.out.println(a - b);
System.out.println(a * b);
System.out.println(a / b);
System.out.println(a % b);
System.out.println(a > b && b > 0);
```

**Detailed explanation:** Arithmetic operators perform numeric calculations. Integer division with `/` discards the decimal part. The modulo operator `%` returns the remainder. The logical `&&` operator returns `true` only when both expressions are true.

**Expected output:**

```text
13
7
30
3
1
true
```

**Expected result:** The code demonstrates arithmetic, remainder, comparison, and logical evaluation.

### S06 - Conditions

```java
int score = 87;

if (score >= 90) {
    System.out.println("A");
} else if (score >= 80) {
    System.out.println("B");
} else {
    System.out.println("Needs improvement");
}
```

**Detailed explanation:** Java evaluates the `if` conditions from top to bottom. Since `87 >= 90` is false but `87 >= 80` is true, the second branch runs and the remaining `else` block is skipped.

**Expected output:**

```text
B
```

**Expected result:** The score maps to the `B` category.

### S07 - Arrays

```java
String[] skills = { "Java", "Spring Boot", "SQL" };

for (int i = 0; i < skills.length; i++) {
    System.out.println((i + 1) + ". " + skills[i]);
}
```

**Detailed explanation:** An array stores multiple values of the same type. `skills.length` gives the number of elements. `skills[i]` accesses the current element by index.

**Expected output:**

```text
1. Java
2. Spring Boot
3. SQL
```

**Expected result:** Each skill is printed in order with a human-friendly number starting at `1`.

### S08 - Loops

```java
int number = 1;

while (number <= 5) {
    System.out.println(number);
    number++;
}
```

**Detailed explanation:** A `while` loop checks the condition before each iteration. The `number++` statement is critical because it moves the loop toward completion.

**Expected output:**

```text
1
2
3
4
5
```

**Expected result:** The loop prints numbers `1` through `5` and then stops when `number` becomes `6`.

### S09 - OOP

```java
class Task {
    private String title;
    private boolean complete;

    Task(String title) {
        this.title = title;
    }

    void markComplete() {
        complete = true;
    }

    boolean isComplete() {
        return complete;
    }
}

Task task = new Task("Study Java");
System.out.println(task.isComplete());
task.markComplete();
System.out.println(task.isComplete());
```

**Detailed explanation:** The class encapsulates state through private fields. The constructor initializes a new object. Methods expose behavior without letting outside code directly modify private fields.

**Expected output:**

```text
false
true
```

**Expected result:** The task begins incomplete and becomes complete after `markComplete()` runs.

### S10 - Lambda Expressions Java 8

```java
import java.util.Arrays;
import java.util.List;

List<String> names = Arrays.asList("Brian", "Java", "Spring");
names.forEach(name -> System.out.println(name.toUpperCase()));
```

**Detailed explanation:** `forEach` expects a functional interface. The lambda `name -> ...` supplies the behavior to run for each element.

**Expected output:**

```text
BRIAN
JAVA
SPRING
```

**Expected result:** Each string is converted to uppercase and printed.

### S11 - Generic Types

```java
class Box<T> {
    private T value;

    void setValue(T value) {
        this.value = value;
    }

    T getValue() {
        return value;
    }
}

Box<String> box = new Box<>();
box.setValue("Java Generics");
System.out.println(box.getValue());
```

**Detailed explanation:** `T` is a placeholder type. `Box<String>` means this instance only accepts and returns `String` values.

**Expected output:**

```text
Java Generics
```

**Expected result:** The compiler prevents putting non-String values into `Box<String>`.

### S12 - Error Handling

```java
try {
    int result = 10 / 0;
    System.out.println(result);
} catch (ArithmeticException ex) {
    System.out.println("Cannot divide by zero: " + ex.getMessage());
} finally {
    System.out.println("Cleanup always runs");
}
```

**Detailed explanation:** Division by zero throws `ArithmeticException`. The `catch` block handles the error, and `finally` runs afterward regardless of success or failure.

**Expected output:**

```text
Cannot divide by zero: / by zero
Cleanup always runs
```

**Expected result:** The program does not crash because the exception is handled.

### S13 - Documentation

```java
/**
 * Calculates the final price after applying a discount.
 *
 * @param price original item price
 * @param discount discount amount
 * @return final price after discount
 */
public double calculateFinalPrice(double price, double discount) {
    return price - discount;
}

System.out.println(calculateFinalPrice(100.00, 15.00));
```

**Detailed explanation:** Javadoc comments describe method behavior, parameters, and return values. Tools can generate HTML documentation from these comments.

**Expected output:**

```text
85.0
```

**Expected result:** The method returns the discounted price.

### S14 - Spring Boot Init

```java
import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication
public class JavaGuideApplication {
    public static void main(String[] args) {
        SpringApplication.run(JavaGuideApplication.class, args);
    }
}
```

**Detailed explanation:** `@SpringBootApplication` combines configuration, auto-configuration, and component scanning. `SpringApplication.run` starts the embedded application context and web server when web dependencies are present.

**Expected result:** Running the application starts Spring Boot. Console logs normally show that the application context started successfully.

```text
Started JavaGuideApplication in ... seconds
```

### S15 - Spring Boot Basics

```java
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RestController;

@RestController
public class HelloController {
    @GetMapping("/hello")
    public String hello() {
        return "Hello from Spring Boot";
    }
}
```

**Detailed explanation:** `@RestController` tells Spring to return method values directly in the HTTP response body. `@GetMapping("/hello")` maps a GET request to the `hello()` method.

**Expected HTTP result:**

```text
GET /hello
200 OK
Hello from Spring Boot
```

### S16 - Spring Boot Security

```java
import org.springframework.context.annotation.Bean;
import org.springframework.security.config.annotation.web.builders.HttpSecurity;
import org.springframework.security.web.SecurityFilterChain;

@Bean
SecurityFilterChain securityFilterChain(HttpSecurity http) throws Exception {
    return http
        .authorizeHttpRequests(auth -> auth
            .requestMatchers("/public/**").permitAll()
            .anyRequest().authenticated())
        .formLogin(form -> form.permitAll())
        .build();
}
```

**Detailed explanation:** Requests under `/public/**` are allowed without login. All other routes require authentication. Form login is enabled for unauthenticated users.

**Expected result:**

```text
GET /public/info -> allowed
GET /dashboard -> redirects to login or returns 401/302 depending on configuration
```

### S17 - Spring Boot Thymeleaf

```java
import org.springframework.stereotype.Controller;
import org.springframework.ui.Model;
import org.springframework.web.bind.annotation.GetMapping;

@Controller
public class PageController {
    @GetMapping("/dashboard")
    public String dashboard(Model model) {
        model.addAttribute("title", "Java Dashboard");
        return "dashboard";
    }
}
```

**Detailed explanation:** A `@Controller` returns a view name instead of raw data. The `Model` passes values into a Thymeleaf template named `dashboard.html`.

**Expected result:**

```text
GET /dashboard -> renders dashboard.html with title = Java Dashboard
```

### S18 - Spring Boot Task Manager Application API

```java
import org.springframework.web.bind.annotation.*;
import java.util.*;

@RestController
@RequestMapping("/api/tasks")
public class TaskController {
    private final List<String> tasks = new ArrayList<>();

    @GetMapping
    public List<String> getTasks() {
        return tasks;
    }

    @PostMapping
    public String addTask(@RequestBody String task) {
        tasks.add(task);
        return task;
    }
}
```

**Detailed explanation:** The controller exposes REST endpoints. `GET /api/tasks` returns the current list, while `POST /api/tasks` adds a task to the in-memory list.

**Expected HTTP result:**

```text
POST /api/tasks body: "Study Java"
Response: Study Java

GET /api/tasks
Response: ["Study Java"]
```

### S19 - Spring Boot AOP

```java
import org.aspectj.lang.annotation.Aspect;
import org.aspectj.lang.annotation.Before;
import org.springframework.stereotype.Component;

@Aspect
@Component
public class LoggingAspect {
    @Before("execution(* com.example..*(..))")
    public void logBeforeMethod() {
        System.out.println("Method is about to execute");
    }
}
```

**Detailed explanation:** AOP applies logic across multiple methods without placing that logic inside every method. This is useful for logging, timing, auditing, and security checks.

**Expected output/result:**

```text
Method is about to execute
```

The message appears before matching methods execute.

### S20 - Summary

```java
public class JavaSummary {
    public static void main(String[] args) {
        String topic = "Java";
        int examplesCompleted = 21;
        boolean readyForInterview = examplesCompleted >= 20;

        System.out.println(topic + " examples completed: " + examplesCompleted);
        System.out.println("Ready for interview review: " + readyForInterview);
    }
}
```

**Detailed explanation:** This combines strings, integers, boolean expressions, comparison operators, and console output in one small program.

**Expected output:**

```text
Java examples completed: 21
Ready for interview review: true
```

### S21 - Bitwise Operators

```java
int a = 5;  // binary 0101
int b = 3;  // binary 0011

System.out.println(a & b);  // 0001 = 1
System.out.println(a | b);  // 0111 = 7
System.out.println(a ^ b);  // 0110 = 6
System.out.println(a << 1); // 1010 = 10
System.out.println(a >> 1); // 0010 = 2
```

**Detailed explanation:** Bitwise operators compare or shift individual binary bits. `&` keeps bits that are on in both numbers, `|` keeps bits that are on in either number, `^` keeps bits that differ, and shifts move bits left or right.

**Expected output:**

```text
1
7
6
10
2
```

## Java Example Files and Explanations

The course section samples above cover the core programming concepts from S04-S21. This section focuses on additional Java example topics from [Java-Example-Files](Java-Example-Files) that are useful for perusal without repeating the same concept coverage.

### Console Formatting — `PrintfExamples.java`

```java
String name = "Brian";
int score = 95;
double completion = 98.75;

System.out.printf("Student: %s | Score: %d | Completion: %.2f%%%n", name, score, completion);
```

**Detailed explanation:** `printf` uses placeholders to format output. `%s` formats a string, `%d` formats an integer, `%.2f` formats a decimal with two digits after the decimal point, and `%%` prints a literal percent sign.

**Expected output:**

```text
Student: Brian | Score: 95 | Completion: 98.75%
```

### Assertions — `AssertExamples.java`

```java
int age = 25;
assert age >= 0 : "Age cannot be negative";
System.out.println("Valid age: " + age);
```

**Detailed explanation:** Assertions are development-time checks. They are disabled by default unless the JVM runs with `-ea`. When enabled, a failed assertion throws `AssertionError`.

**Expected output when assertion passes:**

```text
Valid age: 25
```

**Expected result if `age = -1` and assertions are enabled:**

```text
Exception in thread "main" java.lang.AssertionError: Age cannot be negative
```

### Date and Calendar — `CalendarExamples.java`

```java
import java.util.Calendar;

Calendar calendar = Calendar.getInstance();
calendar.set(2026, Calendar.JUNE, 2);

System.out.println(calendar.get(Calendar.YEAR));
System.out.println(calendar.get(Calendar.MONTH));
System.out.println(calendar.get(Calendar.DAY_OF_MONTH));
```

**Detailed explanation:** `Calendar` stores date/time fields. Months are zero-based internally, so using constants such as `Calendar.JUNE` is clearer than hard-coding `5`.

**Expected output:**

```text
2026
5
2
```

**Expected result:** The month prints as `5` because `Calendar.JUNE` maps to the zero-based month value for June.

### Same-Type Comparison — `SameType.java`

```java
Object value = "Java";

if (value instanceof String) {
    String text = (String) value;
    System.out.println(text.toUpperCase());
}
```

**Detailed explanation:** `instanceof` checks the runtime type before casting. This pattern prevents invalid casts and makes type-specific behavior safer.

**Expected output:**

```text
JAVA
```

### Console Input / Output — `ConsoleExamples.java`

```java
import java.util.Scanner;

Scanner scanner = new Scanner(System.in);
System.out.print("Enter your name: ");
String name = scanner.nextLine();
System.out.println("Hello, " + name);
```

**Detailed explanation:** `Scanner` reads input from the console. `nextLine()` reads a full line. This is useful for small command-line programs.

**Expected interactive result:**

```text
Enter your name: Brian
Hello, Brian
```

### Serialization — `SerializationExamples.java`

```java
import java.io.Serializable;

class Customer implements Serializable {
    private static final long serialVersionUID = 1L;
    private String name;

    Customer(String name) {
        this.name = name;
    }
}
```

**Detailed explanation:** `Serializable` marks a class as eligible for object serialization. `serialVersionUID` helps Java verify class compatibility when deserializing saved objects.

**Expected result:** Objects of `Customer` can be written to an `ObjectOutputStream` and restored with an `ObjectInputStream` if all fields are serializable.

### Thread Deadlock — `ThreadDeadlock.java`

```java
Object lockA = new Object();
Object lockB = new Object();

Thread first = new Thread(() -> {
    synchronized (lockA) {
        synchronized (lockB) {
            System.out.println("First thread acquired both locks");
        }
    }
});
```

**Detailed explanation:** A deadlock can occur when two threads hold different locks and each waits for the other lock. The safest prevention strategy is to acquire locks in a consistent order everywhere.

**Expected result:** This simplified snippet prints normally if no competing thread takes the locks in the reverse order. A full deadlock example would hang instead of completing.

```text
First thread acquired both locks
```

## Interview Questions and PDF

PDF reference:

- [Java-Interview-Questions-And-Answers PDF - Java 8](_Java-Interview-Questions-And-Answers-(Java8).pdf)

### `basics-class-object.md` — Class and Object Basics

**Q1: What is the difference between a class and an object?**

**Answer:** A class is a blueprint. An object is a runtime instance created from that blueprint.

```java
class Book {
    String title;

    Book(String title) {
        this.title = title;
    }

    void printTitle() {
        System.out.println(title);
    }
}

Book book = new Book("Java 8 Guide");
book.printTitle();
```

**Expected output:**

```text
Java 8 Guide
```

**Q2: What is object state and object behavior?**

**Answer:** State is data stored in fields. Behavior is logic exposed through methods.

```java
class LightSwitch {
    boolean on;

    void turnOn() {
        on = true;
    }
}
```

**Expected result:** Calling `turnOn()` changes the object's state from `false` to `true`.

### `abstract-class.md` — Abstract Class

**Q1: What is an abstract class?**

**Answer:** An abstract class is a base class that can define shared behavior and require subclasses to implement missing behavior.

```java
abstract class Shape {
    abstract double area();
}

class Circle extends Shape {
    private double radius;

    Circle(double radius) {
        this.radius = radius;
    }

    double area() {
        return Math.PI * radius * radius;
    }
}

System.out.println(new Circle(2).area());
```

**Expected output:**

```text
12.566370614359172
```

**Q2: Can an abstract class have concrete methods?**

**Answer:** Yes. Abstract classes can contain both abstract and concrete methods.

```java
abstract class BaseReport {
    void printHeader() {
        System.out.println("Report Header");
    }
}
```

**Expected result:** Subclasses inherit `printHeader()` without needing to reimplement it.

### `arrays.md` — Arrays

**Q1: How do you access elements in an array?**

**Answer:** Use zero-based indexes.

```java
int[] numbers = { 10, 20, 30 };
System.out.println(numbers[0]);
System.out.println(numbers[2]);
```

**Expected output:**

```text
10
30
```

**Q2: What happens if an array index is invalid?**

**Answer:** Java throws `ArrayIndexOutOfBoundsException`.

```java
int[] numbers = { 1, 2 };
System.out.println(numbers[5]);
```

**Expected result:**

```text
Exception in thread "main" java.lang.ArrayIndexOutOfBoundsException
```

### `constructors.md` — Constructors

**Q1: What is a constructor?**

**Answer:** A constructor initializes a new object when `new` is used.

```java
class Product {
    private String name;
    private double price;

    Product(String name, double price) {
        this.name = name;
        this.price = price;
    }

    public String toString() {
        return name + ": " + price;
    }
}

System.out.println(new Product("Book", 19.99));
```

**Expected output:**

```text
Book: 19.99
```

**Q2: Can constructors be overloaded?**

**Answer:** Yes. A class can define multiple constructors with different parameter lists.

```java
class User {
    User() {
        System.out.println("Default user");
    }

    User(String name) {
        System.out.println(name);
    }
}
```

**Expected result:** `new User()` prints `Default user`; `new User("Brian")` prints `Brian`.

### `enum.md` — Enum

**Q1: Why use an enum?**

**Answer:** Enums restrict values to a known, fixed set.

```java
enum OrderStatus {
    NEW, PROCESSING, SHIPPED, DELIVERED
}

OrderStatus status = OrderStatus.PROCESSING;
System.out.println(status);
```

**Expected output:**

```text
PROCESSING
```

**Q2: Can enums have fields and methods?**

**Answer:** Yes. Enums can be more than simple constants.

```java
enum Priority {
    HIGH(3), MEDIUM(2), LOW(1);

    private final int level;

    Priority(int level) {
        this.level = level;
    }

    int getLevel() {
        return level;
    }
}

System.out.println(Priority.HIGH.getLevel());
```

**Expected output:**

```text
3
```

### `file-io.md` — File I/O

**Q1: How do you write and read a small text file?**

**Answer:** Use `Files.writeString` and `Files.readString` for simple text operations.

```java
import java.nio.file.Files;
import java.nio.file.Path;

Path path = Path.of("notes.txt");
Files.writeString(path, "Java file example");
String content = Files.readString(path);
System.out.println(content);
```

**Expected output:**

```text
Java file example
```

**Q2: What exception type is common with file operations?**

**Answer:** Many file operations can throw `IOException` when paths are invalid, permissions fail, or disks are unavailable.

**Expected result:** Production code should handle or declare checked file I/O exceptions.

### `generics.md` — Generics

**Q1: What problem do generics solve?**

**Answer:** Generics provide type safety and reduce casts.

```java
import java.util.ArrayList;
import java.util.List;

List<String> names = new ArrayList<>();
names.add("Java");
System.out.println(names.get(0).toUpperCase());
```

**Expected output:**

```text
JAVA
```

**Q2: How do you create a generic class?**

```java
class Repository<T> {
    private T item;

    void save(T item) { this.item = item; }
    T find() { return item; }
}

Repository<String> repository = new Repository<>();
repository.save("Java");
System.out.println(repository.find());
```

**Expected output:**

```text
Java
```

### `inheritance-and-polymorphism.md` — Inheritance and Polymorphism

**Q1: What is inheritance?**

**Answer:** Inheritance lets a subclass reuse and specialize behavior from a superclass.

```java
class Animal {
    String sound() { return "Unknown"; }
}

class Dog extends Animal {
    String sound() { return "Bark"; }
}

System.out.println(new Dog().sound());
```

**Expected output:**

```text
Bark
```

**Q2: What is polymorphism?**

**Answer:** Polymorphism lets a superclass reference point to a subclass object and call overridden behavior.

```java
Animal animal = new Dog();
System.out.println(animal.sound());
```

**Expected output:**

```text
Bark
```

### `interfaces.md` — Interfaces

**Q1: What is an interface?**

**Answer:** An interface defines a contract that implementing classes must follow.

```java
interface ReportExporter {
    void export(String reportName);
}

class PdfExporter implements ReportExporter {
    public void export(String reportName) {
        System.out.println("Exporting PDF: " + reportName);
    }
}

ReportExporter exporter = new PdfExporter();
exporter.export("Weekly Report");
```

**Expected output:**

```text
Exporting PDF: Weekly Report
```

**Q2: Why program to an interface?**

**Answer:** It reduces coupling. Code can depend on `ReportExporter` instead of a specific class such as `PdfExporter`.

### `object-methods.md` — Object Methods

**Q1: Why override `toString()`?**

**Answer:** To provide readable object output for logs and debugging.

```java
class Account {
    private int id;

    Account(int id) { this.id = id; }

    public String toString() {
        return "Account{id=" + id + "}";
    }
}

System.out.println(new Account(101));
```

**Expected output:**

```text
Account{id=101}
```

**Q2: Why override `equals()` and `hashCode()` together?**

**Answer:** Equal objects must return the same hash code for hash-based collections to work correctly.

**Expected result:** Objects that are logically equal behave correctly in `HashSet` and as `HashMap` keys.

### `serialization.md` — Serialization

**Q1: What is serialization?**

**Answer:** Serialization converts object state into a byte stream so it can be saved or transferred.

```java
import java.io.Serializable;

class SessionData implements Serializable {
    private static final long serialVersionUID = 1L;
    private String username;

    SessionData(String username) {
        this.username = username;
    }
}
```

**Expected result:** `SessionData` can be serialized if its fields are serializable.

**Q2: Why define `serialVersionUID`?**

**Answer:** It helps Java verify class compatibility when deserializing stored objects.

### `threads-and-synchronization.md` — Threads and Synchronization

**Q1: How do you create a thread with `Runnable`?**

```java
Runnable task = () -> System.out.println("Running task");
Thread thread = new Thread(task);
thread.start();
```

**Expected output:**

```text
Running task
```

**Q2: Why use `synchronized`?**

**Answer:** To prevent multiple threads from changing shared state at the same time.

```java
class Counter {
    private int count;

    synchronized void increment() {
        count++;
    }

    int getCount() {
        return count;
    }
}
```

**Expected result:** Updates to `count` are protected from race conditions when all access is synchronized consistently.

### `wrapper-classes.md` — Wrapper Classes

**Q1: What are wrapper classes?**

**Answer:** Wrapper classes provide object versions of primitive types, such as `Integer` for `int` and `Double` for `double`.

```java
int primitiveValue = 10;
Integer wrapperValue = primitiveValue; // autoboxing
int unboxedValue = wrapperValue;       // unboxing

System.out.println(Integer.max(primitiveValue, unboxedValue));
```

**Expected output:**

```text
10
```

**Q2: Why are wrappers useful?**

**Answer:** Collections and generic types work with objects, not primitives, so wrappers let primitive-style values be used in APIs such as `List<Integer>`.

```java
import java.util.ArrayList;
import java.util.List;

List<Integer> numbers = new ArrayList<>();
numbers.add(5);
System.out.println(numbers.get(0));
```

**Expected output:**

```text
5
```
