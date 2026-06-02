# Java Expert Programming Tutorial Guide

**Written by Brian McCarthy**

This repository is a hands-on Java programming guide with Java source examples, interview prep notes, section folders, ZIP-based course/source archives, and Java 8 study material.

## Table of Contents

- [Project File Structure](#project-file-structure)
- [Project Links](#project-links)
- [Java Programming Tutorial Guide](#java-programming-tutorial-guide)
- [Course Section Code Samples S04-S21](#course-section-code-samples-s04-s21)
- [Java Example Files and Explanations](#java-example-files-and-explanations)
- [Java Interview Questions and Answers Code Samples](#java-interview-questions-and-answers-code-samples)
- [Interview Questions and PDF](#interview-questions-and-pdf)
- [PDF Text Alternative Notes](#pdf-text-alternative-notes)

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

- **Variables:** store values in memory using primitive types, reference types, static fields, instance fields, and local variables.
- **Operators:** perform arithmetic, comparison, logical, assignment, increment, decrement, and bitwise operations.
- **Conditions:** branch program execution with `if`, `else if`, `else`, and `switch`.
- **Arrays:** store fixed-size collections using indexed access.
- **Loops:** repeat logic with `for`, enhanced `for`, `while`, and `do-while`.
- **OOP:** organize code with classes, objects, encapsulation, inheritance, polymorphism, abstraction, and interfaces.
- **Lambdas:** use Java 8 functional syntax to simplify functional-interface implementations.
- **Generics:** enforce compile-time type safety for classes, methods, and collections.
- **Error Handling:** manage failures with `try`, `catch`, `finally`, and custom exceptions.
- **Spring Boot:** build web APIs, secure applications, render Thymeleaf views, and apply AOP cross-cutting concerns.

## Course Section Code Samples S04-S21

### S04 - Variables

```java
int quantity = 5;
double price = 19.99;
String productName = "Java Book";
boolean inStock = true;

double total = quantity * price;
System.out.println(productName + " total: $" + total);
```

Explanation: variables store typed values. Primitive variables hold simple values, while reference variables such as `String` point to objects.

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

Explanation: arithmetic operators calculate values, comparison operators return booleans, and logical operators combine boolean expressions.

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

Explanation: conditional statements execute different blocks depending on boolean expressions.

### S07 - Arrays

```java
String[] skills = { "Java", "Spring Boot", "SQL" };

for (int i = 0; i < skills.length; i++) {
    System.out.println((i + 1) + ". " + skills[i]);
}
```

Explanation: arrays use zero-based indexes and expose their fixed length through the `length` property.

### S08 - Loops

```java
int number = 1;

while (number <= 5) {
    System.out.println(number);
    number++;
}
```

Explanation: a `while` loop repeats while its condition remains true. Update loop state to avoid infinite loops.

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
```

Explanation: this class encapsulates task state and exposes behavior through methods.

### S10 - Lambda Expressions Java 8

```java
import java.util.Arrays;
import java.util.List;

List<String> names = Arrays.asList("Brian", "Java", "Spring");
names.forEach(name -> System.out.println(name.toUpperCase()));
```

Explanation: lambda expressions provide concise implementations of functional interfaces and are commonly used with collections.

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

Explanation: `T` is a type parameter. The compiler enforces the type when the class is used.

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

Explanation: `try` contains risky code, `catch` handles the exception, and `finally` runs whether an exception occurs or not.

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
```

Explanation: Javadoc comments document classes and methods so developers can generate API documentation.

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

Explanation: `@SpringBootApplication` enables component scanning, auto-configuration, and configuration support.

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

Explanation: `@RestController` exposes web endpoints, and `@GetMapping` maps HTTP GET requests to a Java method.

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

Explanation: Spring Security controls which routes are public and which require authentication.

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

Explanation: a Thymeleaf controller returns a template name and passes data to the page through the `Model`.

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

Explanation: this REST controller exposes a basic task API with GET and POST endpoints.

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

Explanation: AOP separates cross-cutting concerns such as logging from core business logic.

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

Explanation: this summary-style example combines variables, operators, strings, booleans, and output.

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

Explanation: bitwise operators work at the binary bit level. They are useful for flags, masks, low-level logic, and performance-sensitive operations.

## Java Example Files and Explanations

The course section samples above already cover the core programming concepts from S04-S21. This section focuses on additional Java example topics from [Java-Example-Files](Java-Example-Files) that are useful for perusal without repeating the same concept coverage.

### Console Formatting — `PrintfExamples.java`

```java
String name = "Brian";
int score = 95;
double completion = 98.75;

System.out.printf("Student: %s | Score: %d | Completion: %.2f%%%n", name, score, completion);
```

Explanation: `printf` uses format specifiers such as `%s`, `%d`, and `%.2f` to create structured console output.

Source: [Java-Example-Files/others/PrintfExamples.java](Java-Example-Files/others/PrintfExamples.java)

### Assertions — `AssertExamples.java`

```java
int age = 25;
assert age >= 0 : "Age cannot be negative";
System.out.println("Valid age: " + age);
```

Explanation: assertions document assumptions and help catch invalid program states during development.

Source: [Java-Example-Files/others/assertexample/AssertExamples.java](Java-Example-Files/others/assertexample/AssertExamples.java)

### Date and Calendar — `CalendarExamples.java`

```java
import java.util.Calendar;

Calendar calendar = Calendar.getInstance();
calendar.set(2026, Calendar.JUNE, 2);

System.out.println(calendar.get(Calendar.YEAR));
System.out.println(calendar.get(Calendar.MONTH));
System.out.println(calendar.get(Calendar.DAY_OF_MONTH));
```

Explanation: `Calendar` represents date/time fields. Months are zero-based, so `Calendar.JUNE` is safer than hard-coded numbers.

Source: [Java-Example-Files/others/date/CalendarExamples.java](Java-Example-Files/others/date/CalendarExamples.java)

### Same-Type Comparison — `SameType.java`

```java
Object value = "Java";

if (value instanceof String) {
    String text = (String) value;
    System.out.println(text.toUpperCase());
}
```

Explanation: `instanceof` checks the runtime type before casting, reducing the risk of `ClassCastException`.

Source: [Java-Example-Files/others/SameType.java](Java-Example-Files/others/SameType.java)

### Console Input / Output — `ConsoleExamples.java`

```java
import java.util.Scanner;

Scanner scanner = new Scanner(System.in);
System.out.print("Enter your name: ");
String name = scanner.nextLine();
System.out.println("Hello, " + name);
```

Explanation: `Scanner` reads console input, while `System.out.print` and `System.out.println` write output.

Source: [Java-Example-Files/files/ConsoleExamples.java](Java-Example-Files/files/ConsoleExamples.java)

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

Explanation: implementing `Serializable` marks an object as eligible to be written to and restored from an object stream.

Source: [Java-Example-Files/serialization/SerializationExamples.java](Java-Example-Files/serialization/SerializationExamples.java)

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

Explanation: deadlocks can happen when threads acquire shared locks in different orders. The prevention strategy is to acquire locks consistently.

Source: [Java-Example-Files/threads/ThreadDeadlock.java](Java-Example-Files/threads/ThreadDeadlock.java)

## Java Interview Questions and Answers Code Samples

### `basics-class-object.md` — Class and Object Basics

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

Explanation: `Book` is a class. `book` is an object. The constructor initializes state, and the method defines behavior.

### `abstract-class.md` — Abstract Class

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
```

Explanation: abstract classes cannot be instantiated directly. Subclasses must implement abstract methods.

### `arrays.md` — Arrays

```java
int[] numbers = { 10, 20, 30 };

for (int i = 0; i < numbers.length; i++) {
    System.out.println("Index " + i + ": " + numbers[i]);
}
```

Explanation: arrays store fixed-size ordered values and are accessed by zero-based indexes.

### `constructors.md` — Constructors

```java
class Product {
    private String name;
    private double price;

    Product(String name, double price) {
        this.name = name;
        this.price = price;
    }
}
```

Explanation: constructors initialize new objects and can require mandatory values at creation time.

### `enum.md` — Enum

```java
enum OrderStatus {
    NEW,
    PROCESSING,
    SHIPPED,
    DELIVERED
}

OrderStatus status = OrderStatus.PROCESSING;
System.out.println(status);
```

Explanation: enums model a fixed set of valid constants, which is safer than using free-form strings.

### `file-io.md` — File I/O

```java
import java.nio.file.Files;
import java.nio.file.Path;
import java.util.List;

Path path = Path.of("notes.txt");
Files.writeString(path, "Java file example");
String content = Files.readString(path);
System.out.println(content);
```

Explanation: `Files` and `Path` provide modern APIs for reading and writing files.

### `generics.md` — Generics

```java
class Repository<T> {
    private T item;

    void save(T item) {
        this.item = item;
    }

    T find() {
        return item;
    }
}

Repository<String> repository = new Repository<>();
repository.save("Java");
System.out.println(repository.find());
```

Explanation: generics let a class operate on a type selected by the caller while preserving compile-time safety.

### `inheritance-and-polymorphism.md` — Inheritance and Polymorphism

```java
class Animal {
    String sound() {
        return "Unknown";
    }
}

class Dog extends Animal {
    String sound() {
        return "Bark";
    }
}

Animal animal = new Dog();
System.out.println(animal.sound());
```

Explanation: inheritance reuses behavior, while polymorphism lets a parent reference call subclass behavior at runtime.

### `interfaces.md` — Interfaces

```java
interface ReportExporter {
    void export(String reportName);
}

class PdfExporter implements ReportExporter {
    public void export(String reportName) {
        System.out.println("Exporting PDF: " + reportName);
    }
}
```

Explanation: interfaces define contracts. Implementing classes provide the concrete behavior.

### `object-methods.md` — Object Methods

```java
class Account {
    private int id;

    Account(int id) {
        this.id = id;
    }

    public String toString() {
        return "Account{id=" + id + "}";
    }
}

System.out.println(new Account(101));
```

Explanation: overriding `toString()` creates useful, readable output for logging and debugging.

### `serialization.md` — Serialization

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

Explanation: serialization converts object state into a stream that can be stored or transferred.

### `threads-and-synchronization.md` — Threads and Synchronization

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

Explanation: `synchronized` prevents multiple threads from modifying shared state at the same time.

### `wrapper-classes.md` — Wrapper Classes

```java
int primitiveValue = 10;
Integer wrapperValue = primitiveValue; // autoboxing
int unboxedValue = wrapperValue;       // unboxing

System.out.println(Integer.max(primitiveValue, unboxedValue));
```

Explanation: wrapper classes such as `Integer`, `Double`, and `Boolean` provide object versions of primitive values and utility methods.

## Interview Questions and PDF

| Topic | File |
|---|---|
| Class and object basics | [basics-class-object.md](Java-Interview-Questions-And-Answers/basics-class-object.md) |
| Abstract classes | [abstract-class.md](Java-Interview-Questions-And-Answers/abstract-class.md) |
| Arrays | [arrays.md](Java-Interview-Questions-And-Answers/arrays.md) |
| Constructors | [constructors.md](Java-Interview-Questions-And-Answers/constructors.md) |
| Enums | [enum.md](Java-Interview-Questions-And-Answers/enum.md) |
| File I/O | [file-io.md](Java-Interview-Questions-And-Answers/file-io.md) |
| Generics | [generics.md](Java-Interview-Questions-And-Answers/generics.md) |
| Inheritance and polymorphism | [inheritance-and-polymorphism.md](Java-Interview-Questions-And-Answers/inheritance-and-polymorphism.md) |
| Interfaces | [interfaces.md](Java-Interview-Questions-And-Answers/interfaces.md) |
| Object methods | [object-methods.md](Java-Interview-Questions-And-Answers/object-methods.md) |
| Serialization | [serialization.md](Java-Interview-Questions-And-Answers/serialization.md) |
| Threads and synchronization | [threads-and-synchronization.md](Java-Interview-Questions-And-Answers/threads-and-synchronization.md) |
| Wrapper classes | [wrapper-classes.md](Java-Interview-Questions-And-Answers/wrapper-classes.md) |

PDF reference:

- [Java-Interview-Questions-And-Answers PDF - Java 8](_Java-Interview-Questions-And-Answers-(Java8).pdf)

## PDF Text Alternative Notes

- The PDF is linked above for direct viewing.
- The PDF could not be converted to TXT through the available GitHub fetch method because the binary PDF content was unsupported/too large.
- The `Java-Interview-Questions-And-Answers/` Markdown files are the easiest text-based alternative for browsing Java interview material in GitHub.
