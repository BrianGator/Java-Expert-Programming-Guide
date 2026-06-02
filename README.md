# Java Expert Programming Tutorial Guide

**Written by Brian McCarthy**

This repository is a hands-on Java programming guide with Java source examples, interview prep notes, section folders, ZIP-based course/source archives, and Java 8 study material.

## Table of Contents

- [Project Links](#project-links)
- [Java Programming Tutorial Guide](#java-programming-tutorial-guide)
- [Course Section Code Samples S04-S21](#course-section-code-samples-s04-s21)
- [Java Example Files and Explanations](#java-example-files-and-explanations)
- [Interview Questions and PDF](#interview-questions-and-pdf)

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

**Detailed explanation:** Arithmetic operators calculate values, integer division truncates decimals, `%` returns the remainder, and `&&` requires both boolean expressions to be true.

**Expected output:**

```text
13
7
30
3
1
true
```

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

**Detailed explanation:** Java evaluates `if` branches from top to bottom. Since `87 >= 80`, the second branch executes.

**Expected output:**

```text
B
```

### S07 - Arrays

```java
String[] skills = { "Java", "Spring Boot", "SQL" };

for (int i = 0; i < skills.length; i++) {
    System.out.println((i + 1) + ". " + skills[i]);
}
```

**Detailed explanation:** Arrays store multiple values of the same type. `skills.length` gives the array size and `skills[i]` accesses an element.

**Expected output:**

```text
1. Java
2. Spring Boot
3. SQL
```

### S08 - Loops

```java
int number = 1;

while (number <= 5) {
    System.out.println(number);
    number++;
}
```

**Detailed explanation:** A `while` loop checks its condition before each iteration. Incrementing `number` prevents an infinite loop.

**Expected output:**

```text
1
2
3
4
5
```

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

**Detailed explanation:** The class encapsulates task state with private fields and exposes behavior through methods.

**Expected output:**

```text
false
true
```

### S10 - Lambda Expressions Java 8

```java
import java.util.Arrays;
import java.util.List;

List<String> names = Arrays.asList("Brian", "Java", "Spring");
names.forEach(name -> System.out.println(name.toUpperCase()));
```

**Detailed explanation:** `forEach` accepts a functional interface, and the lambda expression supplies the action for each list element.

**Expected output:**

```text
BRIAN
JAVA
SPRING
```

### S11 - Generic Types

```java
class Box<T> {
    private T value;
    void setValue(T value) { this.value = value; }
    T getValue() { return value; }
}

Box<String> box = new Box<>();
box.setValue("Java Generics");
System.out.println(box.getValue());
```

**Detailed explanation:** `T` is a type parameter. `Box<String>` accepts and returns only `String` values.

**Expected output:**

```text
Java Generics
```

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

**Detailed explanation:** Division by zero throws `ArithmeticException`. The `catch` block handles it, and `finally` runs afterward.

**Expected output:**

```text
Cannot divide by zero: / by zero
Cleanup always runs
```

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

**Detailed explanation:** Javadoc comments document method behavior, parameters, and return values.

**Expected output:**

```text
85.0
```

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

**Detailed explanation:** `@SpringBootApplication` enables component scanning, auto-configuration, and configuration support.

**Expected result:**

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

**Detailed explanation:** `@RestController` returns data directly in the HTTP response body, and `@GetMapping` maps GET requests.

**Expected HTTP result:**

```text
GET /hello
200 OK
Hello from Spring Boot
```

### S16 - Spring Boot Security

```java
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

**Detailed explanation:** Public routes are allowed, while other routes require authentication.

**Expected result:**

```text
GET /public/info -> allowed
GET /dashboard -> redirects to login or requires authentication
```

### S17 - Spring Boot Thymeleaf

```java
@Controller
public class PageController {
    @GetMapping("/dashboard")
    public String dashboard(Model model) {
        model.addAttribute("title", "Java Dashboard");
        return "dashboard";
    }
}
```

**Detailed explanation:** A Thymeleaf controller returns a template name and passes data through the `Model`.

**Expected result:**

```text
GET /dashboard -> renders dashboard.html with title = Java Dashboard
```

### S18 - Spring Boot Task Manager Application API

```java
@RestController
@RequestMapping("/api/tasks")
public class TaskController {
    private final List<String> tasks = new ArrayList<>();

    @GetMapping
    public List<String> getTasks() { return tasks; }

    @PostMapping
    public String addTask(@RequestBody String task) {
        tasks.add(task);
        return task;
    }
}
```

**Detailed explanation:** `GET /api/tasks` returns the task list, and `POST /api/tasks` adds a new task.

**Expected HTTP result:**

```text
POST /api/tasks body: "Study Java"
Response: Study Java
GET /api/tasks
Response: ["Study Java"]
```

### S19 - Spring Boot AOP

```java
@Aspect
@Component
public class LoggingAspect {
    @Before("execution(* com.example..*(..))")
    public void logBeforeMethod() {
        System.out.println("Method is about to execute");
    }
}
```

**Detailed explanation:** AOP applies cross-cutting logic, such as logging, before or after matching methods.

**Expected output/result:**

```text
Method is about to execute
```

### S20 - Summary

```java
String topic = "Java";
int examplesCompleted = 21;
boolean readyForInterview = examplesCompleted >= 20;

System.out.println(topic + " examples completed: " + examplesCompleted);
System.out.println("Ready for interview review: " + readyForInterview);
```

**Detailed explanation:** This combines strings, integers, boolean expressions, comparison operators, and console output.

**Expected output:**

```text
Java examples completed: 21
Ready for interview review: true
```

### S21 - Bitwise Operators

```java
int a = 5;  // binary 0101
int b = 3;  // binary 0011

System.out.println(a & b);
System.out.println(a | b);
System.out.println(a ^ b);
System.out.println(a << 1);
System.out.println(a >> 1);
```

**Detailed explanation:** Bitwise operators work on binary bits. `&`, `|`, and `^` compare bits; shifts move bits left or right.

**Expected output:**

```text
1
7
6
10
2
```

## Java Example Files and Explanations

The course section samples above cover the core programming concepts from S04-S21. This section focuses on additional Java example topics from [Java-Example-Files](Java-Example-Files) without repeating the same concept coverage.

### Console Formatting — `PrintfExamples.java`

```java
String name = "Brian";
int score = 95;
double completion = 98.75;
System.out.printf("Student: %s | Score: %d | Completion: %.2f%%%n", name, score, completion);
```

**Detailed explanation:** `printf` uses format specifiers such as `%s`, `%d`, `%.2f`, and `%%` for structured console output.

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

**Detailed explanation:** Assertions document assumptions and can catch invalid states when the JVM is run with `-ea`.

**Expected output:**

```text
Valid age: 25
```

### Date and Calendar — `CalendarExamples.java`

```java
Calendar calendar = Calendar.getInstance();
calendar.set(2026, Calendar.JUNE, 2);
System.out.println(calendar.get(Calendar.YEAR));
System.out.println(calendar.get(Calendar.MONTH));
System.out.println(calendar.get(Calendar.DAY_OF_MONTH));
```

**Detailed explanation:** `Calendar` stores date/time fields. Months are zero-based internally, so June prints as `5`.

**Expected output:**

```text
2026
5
2
```

### Same-Type Comparison — `SameType.java`

```java
Object value = "Java";
if (value instanceof String) {
    String text = (String) value;
    System.out.println(text.toUpperCase());
}
```

**Detailed explanation:** `instanceof` checks runtime type before casting, reducing the risk of `ClassCastException`.

**Expected output:**

```text
JAVA
```

### Console Input / Output — `ConsoleExamples.java`

```java
Scanner scanner = new Scanner(System.in);
System.out.print("Enter your name: ");
String name = scanner.nextLine();
System.out.println("Hello, " + name);
```

**Detailed explanation:** `Scanner` reads user input from the console.

**Expected interactive result:**

```text
Enter your name: Brian
Hello, Brian
```

### Serialization — `SerializationExamples.java`

```java
class Customer implements Serializable {
    private static final long serialVersionUID = 1L;
    private String name;

    Customer(String name) {
        this.name = name;
    }
}
```

**Detailed explanation:** `Serializable` marks a class as eligible for object serialization. `serialVersionUID` helps Java verify compatibility during deserialization.

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

**Detailed explanation:** Deadlocks can occur when two threads acquire locks in conflicting order. The prevention strategy is to acquire locks consistently.

**Expected result:** The simplified snippet prints normally if no competing thread takes locks in reverse order.

```text
First thread acquired both locks
```

## Interview Questions and PDF

PDF reference:

- [Java-Interview-Questions-And-Answers PDF - Java 8](_Java-Interview-Questions-And-Answers-(Java8).pdf)

### Class and Object Basics

**Q1: What is the difference between a class and an object?**

**Answer:** A class is a blueprint. An object is a runtime instance created from that blueprint.

```java
class Book {
    String title;
    Book(String title) { this.title = title; }
    void printTitle() { System.out.println(title); }
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

### Abstract Class

**Q1: What is an abstract class?**

**Answer:** An abstract class is a base class that can define shared behavior and require subclasses to implement missing behavior.

```java
abstract class Shape { abstract double area(); }
class Circle extends Shape {
    private double radius;
    Circle(double radius) { this.radius = radius; }
    double area() { return Math.PI * radius * radius; }
}
System.out.println(new Circle(2).area());
```

**Expected output:**

```text
12.566370614359172
```

### Arrays

**Q: How do you access elements in an array?**

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

### Constructors

**Q: What is a constructor?**

**Answer:** A constructor initializes a new object when `new` is used.

```java
class Product {
    private String name;
    private double price;
    Product(String name, double price) { this.name = name; this.price = price; }
    public String toString() { return name + ": " + price; }
}
System.out.println(new Product("Book", 19.99));
```

**Expected output:**

```text
Book: 19.99
```

### Enum

**Q: Why use an enum?**

**Answer:** Enums restrict values to a known, fixed set.

```java
enum OrderStatus { NEW, PROCESSING, SHIPPED, DELIVERED }
OrderStatus status = OrderStatus.PROCESSING;
System.out.println(status);
```

**Expected output:**

```text
PROCESSING
```

### File I/O

**Q: How do you write and read a small text file?**

**Answer:** Use `Files.writeString` and `Files.readString` for simple text operations.

```java
Path path = Path.of("notes.txt");
Files.writeString(path, "Java file example");
String content = Files.readString(path);
System.out.println(content);
```

**Expected output:**

```text
Java file example
```

### Generics

**Q: What problem do generics solve?**

**Answer:** Generics provide type safety and reduce casts.

```java
List<String> names = new ArrayList<>();
names.add("Java");
System.out.println(names.get(0).toUpperCase());
```

**Expected output:**

```text
JAVA
```

### Inheritance and Polymorphism

**Q: What is polymorphism?**

**Answer:** Polymorphism lets a superclass reference point to a subclass object and call overridden behavior.

```java
class Animal { String sound() { return "Unknown"; } }
class Dog extends Animal { String sound() { return "Bark"; } }
Animal animal = new Dog();
System.out.println(animal.sound());
```

**Expected output:**

```text
Bark
```

### Interfaces

**Q: What is an interface?**

**Answer:** An interface defines a contract that implementing classes must follow.

```java
interface ReportExporter { void export(String reportName); }
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

### Object Methods

**Q: Why override `toString()`?**

**Answer:** To provide readable object output for logs and debugging.

```java
class Account {
    private int id;
    Account(int id) { this.id = id; }
    public String toString() { return "Account{id=" + id + "}"; }
}
System.out.println(new Account(101));
```

**Expected output:**

```text
Account{id=101}
```

### Serialization

**Q: What is serialization?**

**Answer:** Serialization converts object state into a byte stream so it can be saved or transferred.

```java
class SessionData implements Serializable {
    private static final long serialVersionUID = 1L;
    private String username;
    SessionData(String username) { this.username = username; }
}
```

**Expected result:** `SessionData` can be serialized if its fields are serializable.

### Threads and Synchronization

**Q: How do you create a thread with `Runnable`?**

```java
Runnable task = () -> System.out.println("Running task");
Thread thread = new Thread(task);
thread.start();
```

**Expected output:**

```text
Running task
```

### Wrapper Classes

**Q: What are wrapper classes?**

**Answer:** Wrapper classes provide object versions of primitive types, such as `Integer` for `int` and `Double` for `double`.

```java
int primitiveValue = 10;
Integer wrapperValue = primitiveValue;
int unboxedValue = wrapperValue;
System.out.println(Integer.max(primitiveValue, unboxedValue));
```

**Expected output:**

```text
10
```
