# Java Expert Programming Tutorial Guide

**Written by Brian McCarthy**

This repository is a hands-on Java programming guide with Java source examples, interview prep notes, section folders, ZIP-based course/source archives, and Java 8 study material.

## Table of Contents

- [Project File Structure](#project-file-structure)
- [Project Links](#project-links)
- [Section Folder ZIP Notes](#section-folder-zip-notes)
- [How to Use This Repository](#how-to-use-this-repository)
- [Java Programming Tutorial Guide](#java-programming-tutorial-guide)
- [Java Example Files and Code Samples](#java-example-files-and-code-samples)
- [Course Section Code Samples S04-S21](#course-section-code-samples-s04-s21)
- [Java Example Files and Explanations](#java-example-files-and-explanations)
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

## Section Folder ZIP Notes

The project contains section folders whose names begin with `s01`, `s02`, `s03`, and continue through later course sections. If those folders contain ZIP archives, extract each ZIP locally and commit the extracted `.java` files back into the matching section folder so they can be viewed directly in GitHub without downloading and unzipping archives.

```bash
git clone https://github.com/BrianGator/Java-Expert-Programming-Guide.git
cd Java-Expert-Programming-Guide

for dir in s{01..21}*; do
  if [ -d "$dir" ]; then
    find "$dir" -name "*.zip" -print0 | while IFS= read -r -d '' zipfile; do
      target="${zipfile%.zip}"
      mkdir -p "$target"
      unzip -o "$zipfile" -d "$target"
    done
  fi
done

git add .
git commit -m "Extract Java section source files"
git push
```

PowerShell:

```powershell
Get-ChildItem -Directory -Filter "s*" | Where-Object { $_.Name -match '^s(0[1-9]|1[0-9]|2[0-1])' } | ForEach-Object {
    Get-ChildItem $_.FullName -Filter "*.zip" -Recurse | ForEach-Object {
        $target = Join-Path $_.DirectoryName $_.BaseName
        New-Item -ItemType Directory -Force -Path $target | Out-Null
        Expand-Archive -Path $_.FullName -DestinationPath $target -Force
    }
}
```

## How to Use This Repository

1. Clone the repository.
2. Open it in IntelliJ IDEA, Eclipse, VS Code, or another Java IDE.
3. Browse `Java-Example-Files/` by topic.
4. Browse the section folders for section-specific examples and extracted source files.
5. Open one `.java` file at a time.
6. Read the matching topic note in `Java-Interview-Questions-And-Answers/`.
7. Use the Java 8 PDF for interview review.

```bash
git clone https://github.com/BrianGator/Java-Expert-Programming-Guide.git
cd Java-Expert-Programming-Guide
```

Some files declare packages such as `com.in28minutes.java.flow`, so an IDE import is usually easier than compiling every file manually.

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

## Java Example Files and Code Samples

### Arrays — `ArrayExamples.java`

Array declaration, indexed access, traversal, and aggregation.

```java
int[] scores = { 95, 88, 76, 100 };
int total = 0;

for (int score : scores) {
    total += score;
}

double average = (double) total / scores.length;
System.out.println("Average score: " + average);
System.out.println("First score: " + scores[0]);
```

Explanation: arrays store fixed-size values of the same type. Indexes start at `0`, and enhanced `for` loops make traversal simple.

Source: [Java-Example-Files/arrays/ArrayExamples.java](Java-Example-Files/arrays/ArrayExamples.java)

### Strings — `StringExamples.java`

String behavior and common operations.

```java
String course = "Java Expert Programming";

System.out.println(course.length());
System.out.println(course.toUpperCase());
System.out.println(course.contains("Java"));
System.out.println(course.substring(0, 4));
```

Explanation: `String` objects are immutable. Methods such as `toUpperCase()` return a new string instead of changing the original.

Source: [Java-Example-Files/string/StringExamples.java](Java-Example-Files/string/StringExamples.java)

### Flow — `ForLoopExample.java`, `WhileLoopExamples.java`, `DoWhileLoopExamples.java`, `BreakExamples.java`, `ContinueExamples.java`

Loops and flow-control statements.

```java
for (int i = 0; i < 5; i++) {
    if (i == 3) {
        continue;
    }
    System.out.println("For loop value: " + i);
}

int count = 0;
while (count < 3) {
    System.out.println("While loop value: " + count);
    count++;
}

do {
    System.out.println("Do-while runs at least once");
} while (false);
```

Explanation: `for` is useful when the iteration count is known. `while` runs while a condition is true. `do-while` runs once before checking the condition. `continue` skips one iteration, and `break` exits a loop.

Sources: [flow folder](Java-Example-Files/flow)

### Operators — `LogicalOperators.java`, `IncrementAndDecrementOperators.java`

Boolean logic and increment/decrement behavior.

```java
int age = 25;
boolean hasLicense = true;

if (age >= 18 && hasLicense) {
    System.out.println("Allowed to drive");
}

int counter = 0;
System.out.println(counter++); // prints 0, then increments
System.out.println(++counter); // increments first, then prints 2
```

Explanation: `&&` requires both conditions to be true. Post-increment uses the current value first; pre-increment increments before evaluation.

Sources: [Java-Example-Files/operators](Java-Example-Files/operators)

### Variables — `VariablesExample.java`, `StaticAndMemberVariables.java`, `PassingVariablesToMethods.java`

Scope, static fields, instance fields, and method arguments.

```java
class Counter {
    static int globalCount = 0;
    int instanceCount = 0;

    void increment() {
        int localCount = 1;
        instanceCount += localCount;
        globalCount++;
    }
}
```

Explanation: `localCount` exists only inside the method. `instanceCount` belongs to an object. `globalCount` belongs to the class.

Sources: [Java-Example-Files/variables](Java-Example-Files/variables)

### Modifiers — `DefaultAccessClass.java`, `AbstractClassExample.java`, `FinalClass.java`, `ExampleClass.java`

Access modifiers and non-access modifiers.

```java
abstract class Report {
    abstract void generate();
}

final class PdfReport extends Report {
    public void generate() {
        System.out.println("Generating PDF report");
    }
}
```

Explanation: `abstract` classes can define incomplete behavior. `final` classes cannot be extended. Access modifiers such as `public`, `private`, and package-private control visibility.

Sources: [Java-Example-Files/classmodifiers](Java-Example-Files/classmodifiers), [Java-Example-Files/membermodifiers](Java-Example-Files/membermodifiers)

### OOP — `EncapsulationExample.java`, `InheritanceExamples.java`, `InterfaceExamples.java`

Encapsulation, inheritance, polymorphism, abstraction, and interfaces.

```java
interface Payable {
    double calculatePay();
}

class Employee implements Payable {
    private double hourlyRate;
    private int hoursWorked;

    Employee(double hourlyRate, int hoursWorked) {
        this.hourlyRate = hourlyRate;
        this.hoursWorked = hoursWorked;
    }

    public double calculatePay() {
        return hourlyRate * hoursWorked;
    }
}

Payable worker = new Employee(40.0, 35);
System.out.println(worker.calculatePay());
```

Explanation: the private fields demonstrate encapsulation. The interface demonstrates abstraction. The `Payable` reference pointing to `Employee` demonstrates polymorphism.

Sources: [Java-Example-Files/oops](Java-Example-Files/oops)

### Enums — `Enum.java`, `EnumAdvanced.java`, `EnumAdvanced2.java`

Basic and advanced enum usage.

```java
enum Difficulty {
    EASY(1), MEDIUM(2), HARD(3);

    private final int level;

    Difficulty(int level) {
        this.level = level;
    }

    public int getLevel() {
        return level;
    }
}

System.out.println(Difficulty.HARD.getLevel());
```

Explanation: enums define a fixed set of constants. Advanced enums can include fields, constructors, and methods.

Sources: [Java-Example-Files/enums](Java-Example-Files/enums)

### Generics — `GenericsExamples.java`, `GenericsExamples2.java`

Type-safe generic programming.

```java
import java.util.ArrayList;
import java.util.List;

List<String> names = new ArrayList<>();
names.add("Brian");
names.add("Java");

for (String name : names) {
    System.out.println(name.toUpperCase());
}
```

Explanation: generics prevent invalid values from being added to a collection and remove the need for manual casting.

Sources: [Java-Example-Files/generics](Java-Example-Files/generics)

### Object Methods — `ToStringExamples.java`, `EqualsHashCodeExamples.java`

`toString`, `equals`, and `hashCode`.

```java
class User {
    private final int id;

    User(int id) {
        this.id = id;
    }

    public String toString() {
        return "User{id=" + id + "}";
    }

    public boolean equals(Object obj) {
        if (this == obj) return true;
        if (!(obj instanceof User)) return false;
        User other = (User) obj;
        return this.id == other.id;
    }

    public int hashCode() {
        return Integer.hashCode(id);
    }
}
```

Explanation: `toString()` controls readable output. `equals()` controls logical equality. `hashCode()` supports hash-based collections.

Sources: [Java-Example-Files/object](Java-Example-Files/object)

### Files and Serialization — `ConsoleExamples.java`, `SerializationExamples.java`

Console I/O and object serialization.

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

Explanation: `Serializable` marks an object as eligible for serialization. This allows object state to be written to a stream and restored later.

Sources: [Java-Example-Files/files](Java-Example-Files/files), [Java-Example-Files/serialization](Java-Example-Files/serialization)

### Threads — `ThreadExamples.java`, `ThreadExampleSynchronized.java`, `ThreadPriority.java`, `ThreadDeadlock.java`

Thread creation, priority, synchronization, and deadlock.

```java
class SafeCounter {
    private int count = 0;

    public synchronized void increment() {
        count++;
    }

    public int getCount() {
        return count;
    }
}
```

Explanation: `synchronized` protects shared state so only one thread can execute the method at a time. This helps prevent race conditions.

Sources: [Java-Example-Files/threads](Java-Example-Files/threads)

### Varargs — `VariableArgumentExamples.java`

Variable-length method arguments.

```java
public static int sum(int... numbers) {
    int total = 0;
    for (int number : numbers) {
        total += number;
    }
    return total;
}

System.out.println(sum(1, 2, 3));
System.out.println(sum(10, 20, 30, 40));
```

Explanation: varargs allow a method to accept zero or more arguments of the same type.

Source: [Java-Example-Files/varargs/VariableArgumentExamples.java](Java-Example-Files/varargs/VariableArgumentExamples.java)

### Miscellaneous — `SameType.java`, `PrintfExamples.java`, `AssertExamples.java`, `CalendarExamples.java`

Formatting, assertions, dates, and miscellaneous Java examples.

```java
String name = "Brian";
int score = 95;
System.out.printf("Student: %s | Score: %d%n", name, score);

int age = 25;
assert age >= 0 : "Age cannot be negative";
```

Explanation: `printf` formats output using placeholders. `assert` documents assumptions and helps catch invalid development-time states.

Sources: [Java-Example-Files/others](Java-Example-Files/others)

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

Explanation: a `while` loop repeats while its condition remains true. Remember to update loop state to avoid infinite loops.

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

Explanation: `@SpringBootApplication` enables component scanning, auto-configuration, and configuration support for a Spring Boot app.

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

| Area | Files | Explanation |
|---|---|---|
| Arrays | [ArrayExamples.java](Java-Example-Files/arrays/ArrayExamples.java) | Array declaration, access, and traversal. |
| Strings | [StringExamples.java](Java-Example-Files/string/StringExamples.java) | String behavior and common operations. |
| Flow | [ForLoopExample.java](Java-Example-Files/flow/ForLoopExample.java), [WhileLoopExamples.java](Java-Example-Files/flow/WhileLoopExamples.java), [DoWhileLoopExamples.java](Java-Example-Files/flow/DoWhileLoopExamples.java), [BreakExamples.java](Java-Example-Files/flow/BreakExamples.java), [ContinueExamples.java](Java-Example-Files/flow/ContinueExamples.java) | Loops and flow-control statements. |
| Operators | [LogicalOperators.java](Java-Example-Files/operators/LogicalOperators.java), [IncrementAndDecrementOperators.java](Java-Example-Files/operators/IncrementAndDecrementOperators.java) | Boolean logic and increment/decrement behavior. |
| Variables | [VariablesExample.java](Java-Example-Files/variables/scope/VariablesExample.java), [StaticAndMemberVariables.java](Java-Example-Files/variables/StaticAndMemberVariables.java), [PassingVariablesToMethods.java](Java-Example-Files/variables/PassingVariablesToMethods.java) | Scope, static fields, instance fields, and method arguments. |
| Modifiers | [DefaultAccessClass.java](Java-Example-Files/classmodifiers/defaultaccess/a/DefaultAccessClass.java), [AbstractClassExample.java](Java-Example-Files/classmodifiers/nonaccess/abstractclass/AbstractClassExample.java), [FinalClass.java](Java-Example-Files/classmodifiers/nonaccess/finalclass/FinalClass.java), [ExampleClass.java](Java-Example-Files/membermodifiers/access/ExampleClass.java) | Access modifiers and non-access modifiers. |
| OOP | [EncapsulationExample.java](Java-Example-Files/oops/encapsulation/EncapsulationExample.java), [InheritanceExamples.java](Java-Example-Files/oops/inheritance/InheritanceExamples.java), [InterfaceExamples.java](Java-Example-Files/oops/interfaces/InterfaceExamples.java) | Encapsulation, inheritance, polymorphism, abstraction, and interfaces. |
| Enums | [Enum.java](Java-Example-Files/enums/Enum.java), [EnumAdvanced.java](Java-Example-Files/enums/EnumAdvanced.java), [EnumAdvanced2.java](Java-Example-Files/enums/EnumAdvanced2.java) | Basic and advanced enum usage. |
| Generics | [GenericsExamples.java](Java-Example-Files/generics/GenericsExamples.java), [GenericsExamples2.java](Java-Example-Files/generics/GenericsExamples2.java) | Type-safe generic programming. |
| Object Methods | [ToStringExamples.java](Java-Example-Files/object/ToStringExamples.java), [EqualsHashCodeExamples.java](Java-Example-Files/object/EqualsHashCodeExamples.java) | `toString`, `equals`, and `hashCode`. |
| Files and Serialization | [ConsoleExamples.java](Java-Example-Files/files/ConsoleExamples.java), [SerializationExamples.java](Java-Example-Files/serialization/SerializationExamples.java) | Console I/O and object serialization. |
| Threads | [ThreadExamples.java](Java-Example-Files/threads/ThreadExamples.java), [ThreadExampleSynchronized.java](Java-Example-Files/threads/ThreadExampleSynchronized.java), [ThreadPriority.java](Java-Example-Files/threads/ThreadPriority.java), [ThreadDeadlock.java](Java-Example-Files/threads/ThreadDeadlock.java) | Thread creation, priority, synchronization, and deadlock. |
| Varargs | [VariableArgumentExamples.java](Java-Example-Files/varargs/VariableArgumentExamples.java) | Variable-length method arguments. |
| Miscellaneous | [SameType.java](Java-Example-Files/others/SameType.java), [PrintfExamples.java](Java-Example-Files/others/PrintfExamples.java), [AssertExamples.java](Java-Example-Files/others/assertexample/AssertExamples.java), [CalendarExamples.java](Java-Example-Files/others/date/CalendarExamples.java) | Formatting, assertions, dates, and miscellaneous Java examples. |

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
