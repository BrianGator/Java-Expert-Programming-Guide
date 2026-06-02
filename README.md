# Java Expert Programming Tutorial Guide

**Written by Brian McCarthy**

This repository is a hands-on Java programming guide with Java source examples, interview prep notes, section folders, ZIP-based course/source archives, and Java 8 study material.

## Table of Contents

- [Project File Structure](#project-file-structure)
- [Project Links](#project-links)
- [Section Folder ZIP Notes](#section-folder-zip-notes)
- [How to Use This Repository](#how-to-use-this-repository)
- [Java Programming Tutorial Guide](#java-programming-tutorial-guide)
- [Code Samples](#code-samples)
- [Java Example Files and Explanations](#java-example-files-and-explanations)
- [Interview Questions and PDF](#interview-questions-and-pdf)
- [PDF Text Alternative Notes](#pdf-text-alternative-notes)

## Project File Structure

```text
Java-Expert-Programming-Guide/
├── README.md
├── _Java-Interview-Questions-And-Answers-(Java8).pdf
├── s01*/
├── s02*/
├── s03*/
├── s04*/
├── s05*/
├── s06*/
├── s07*/
├── s08*/
├── s09*/
├── s10*/
├── s11*/
├── s12*/
├── s13*/
├── s14*/
├── s15*/
├── s16*/
├── s17*/
├── s18*/
├── s19*/
├── s20*/
├── s21*/
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

> The `s01*` through `s21*` entries represent section folders whose names begin with `s01`, `s02`, `s03`, and so on through `s21`. These section folders may contain ZIP archives or course/source files for each section.

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

The repository includes section folders named from `s01*` through `s21*`. If those folders contain ZIP archives, extract each ZIP locally and commit the extracted `.java` files back into the matching section folder so they can be viewed directly in GitHub without downloading and unzipping archives.

Recommended local extraction workflow:

```bash
git clone https://github.com/BrianGator/Java-Expert-Programming-Guide.git
cd Java-Expert-Programming-Guide

# macOS/Linux/Git Bash example: extract ZIP files inside section folders
for dir in s{01..21}*; do
  if [ -d "$dir" ]; then
    find "$dir" -name "*.zip" -print0 | while IFS= read -r -d '' zipfile; do
      target="${zipfile%.zip}"
      mkdir -p "$target"
      unzip -o "$zipfile" -d "$target"
    done
  fi
done

# Optional: keep only relevant Java/source files for easier GitHub browsing
find s{01..21}* -type f \
  ! -name "*.java" \
  ! -name "*.md" \
  ! -name "*.txt" \
  ! -name "*.xml" \
  ! -name "*.properties" \
  ! -name "pom.xml" \
  ! -name "build.gradle" \
  -print

git status
git add s01* s02* s03* s04* s05* s06* s07* s08* s09* s10* s11* s12* s13* s14* s15* s16* s17* s18* s19* s20* s21*
git commit -m "Extract Java section source files"
git push
```

PowerShell extraction workflow:

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
4. Browse `s01*` through `s21*` for section-specific examples and extracted source files.
5. Open one `.java` file at a time.
6. Read the matching topic note in `Java-Interview-Questions-And-Answers/`.
7. Use the Java 8 PDF for interview review.

```bash
git clone https://github.com/BrianGator/Java-Expert-Programming-Guide.git
cd Java-Expert-Programming-Guide
```

Some files declare packages such as `com.in28minutes.java.flow`, so an IDE import is usually easier than compiling every file manually.

## Java Programming Tutorial Guide

### 1. Classes and Objects

A class is a blueprint. An object is an instance of a class. Fields store state and methods define behavior.

Related files:

- [Java-Example-Files/basics/Actor.java](Java-Example-Files/basics/Actor.java)
- [Java-Example-Files/basics/Cricketer.java](Java-Example-Files/basics/Cricketer.java)
- [Java-Interview-Questions-And-Answers/basics-class-object.md](Java-Interview-Questions-And-Answers/basics-class-object.md)

### 2. Variables, Scope, and Parameters

Java variables can be local variables, instance variables, or static variables. Scope controls where each variable can be accessed.

Related files:

- [Java-Example-Files/variables/scope/VariablesExample.java](Java-Example-Files/variables/scope/VariablesExample.java)
- [Java-Example-Files/variables/StaticAndMemberVariables.java](Java-Example-Files/variables/StaticAndMemberVariables.java)
- [Java-Example-Files/variables/PassingVariablesToMethods.java](Java-Example-Files/variables/PassingVariablesToMethods.java)

### 3. Flow Control

Flow control includes `for`, enhanced `for`, `while`, `do-while`, `break`, and `continue`.

Related files:

- [Java-Example-Files/flow/ForLoopExample.java](Java-Example-Files/flow/ForLoopExample.java)
- [Java-Example-Files/flow/WhileLoopExamples.java](Java-Example-Files/flow/WhileLoopExamples.java)
- [Java-Example-Files/flow/DoWhileLoopExamples.java](Java-Example-Files/flow/DoWhileLoopExamples.java)
- [Java-Example-Files/flow/BreakExamples.java](Java-Example-Files/flow/BreakExamples.java)
- [Java-Example-Files/flow/ContinueExamples.java](Java-Example-Files/flow/ContinueExamples.java)

### 4. Arrays and Strings

Arrays store fixed-size collections. Strings store immutable text values.

Related files:

- [Java-Example-Files/arrays/ArrayExamples.java](Java-Example-Files/arrays/ArrayExamples.java)
- [Java-Example-Files/string/StringExamples.java](Java-Example-Files/string/StringExamples.java)

### 5. Object-Oriented Programming

OOP uses encapsulation, inheritance, polymorphism, and abstraction to structure maintainable code.

Related files:

- [Java-Example-Files/oops/encapsulation/EncapsulationExample.java](Java-Example-Files/oops/encapsulation/EncapsulationExample.java)
- [Java-Example-Files/oops/inheritance/InheritanceExamples.java](Java-Example-Files/oops/inheritance/InheritanceExamples.java)
- [Java-Example-Files/oops/interfaces/InterfaceExamples.java](Java-Example-Files/oops/interfaces/InterfaceExamples.java)
- [Java-Interview-Questions-And-Answers/inheritance-and-polymorphism.md](Java-Interview-Questions-And-Answers/inheritance-and-polymorphism.md)

### 6. Interfaces and Abstract Classes

Interfaces define contracts. Abstract classes define partial base implementations.

Related files:

- [Java-Example-Files/oops/interfaces/Flyable.java](Java-Example-Files/oops/interfaces/Flyable.java)
- [Java-Example-Files/oops/interfaces/Bird.java](Java-Example-Files/oops/interfaces/Bird.java)
- [Java-Example-Files/oops/interfaces/Aeroplane.java](Java-Example-Files/oops/interfaces/Aeroplane.java)
- [Java-Interview-Questions-And-Answers/interfaces.md](Java-Interview-Questions-And-Answers/interfaces.md)
- [Java-Interview-Questions-And-Answers/abstract-class.md](Java-Interview-Questions-And-Answers/abstract-class.md)

### 7. Generics

Generics provide compile-time type safety and reduce casting.

Related files:

- [Java-Example-Files/generics/GenericsExamples.java](Java-Example-Files/generics/GenericsExamples.java)
- [Java-Example-Files/generics/GenericsExamples2.java](Java-Example-Files/generics/GenericsExamples2.java)

### 8. Object Methods

`toString`, `equals`, and `hashCode` are inherited from `Object` and are important for debugging, comparison, maps, and sets.

Related files:

- [Java-Example-Files/object/ToStringExamples.java](Java-Example-Files/object/ToStringExamples.java)
- [Java-Example-Files/object/EqualsHashCodeExamples.java](Java-Example-Files/object/EqualsHashCodeExamples.java)

### 9. Threads and Synchronization

Java supports concurrent work using `Thread`, `Runnable`, `start()`, and synchronization patterns.

Related files:

- [Java-Example-Files/threads/ThreadExamples.java](Java-Example-Files/threads/ThreadExamples.java)
- [Java-Example-Files/threads/ThreadExampleSynchronized.java](Java-Example-Files/threads/ThreadExampleSynchronized.java)
- [Java-Example-Files/threads/ThreadPriority.java](Java-Example-Files/threads/ThreadPriority.java)
- [Java-Example-Files/threads/ThreadDeadlock.java](Java-Example-Files/threads/ThreadDeadlock.java)

### 10. Java 8 Lambda Expressions

Lambda expressions provide concise function-style syntax for functional interfaces.

Related file:

- [Java-Example-Files/LambdaExpressionsTest.java](Java-Example-Files/LambdaExpressionsTest.java)

## Code Samples

### For Loop Example

```java
for (int i = 0; i < 10; i++) {
    System.out.print(i);
}

int[] numbers = { 1, 2, 3, 4, 5 };
for (int number : numbers) {
    System.out.print(number);
}
```

Explanation: the first loop uses a counter. The second loop is an enhanced `for` loop for arrays.

Source: [Java-Example-Files/flow/ForLoopExample.java](Java-Example-Files/flow/ForLoopExample.java)

### Inheritance Example

```java
abstract class Animal {
    abstract String bark();
}

class Dog extends Animal {
    String bark() {
        return "Bow Bow";
    }
}

Animal animal = new Dog();
System.out.println(animal.bark());
```

Explanation: `Dog` extends `Animal` and implements the abstract behavior. The superclass reference demonstrates polymorphism.

Source: [Java-Example-Files/oops/inheritance/InheritanceExamples.java](Java-Example-Files/oops/inheritance/InheritanceExamples.java)

### Thread Example

```java
class BattingStatisticsThread extends Thread {
    public void run() {
        System.out.println("Running Batting Statistics");
    }
}

BattingStatisticsThread thread = new BattingStatisticsThread();
thread.start();
```

Explanation: extending `Thread` and calling `start()` runs the `run()` method on a separate execution path.

Source: [Java-Example-Files/threads/ThreadExamples.java](Java-Example-Files/threads/ThreadExamples.java)

## Java Example Files and Explanations

| Area | Files | Explanation |
|---|---|---|
| Basics | [Actor.java](Java-Example-Files/basics/Actor.java), [Cricketer.java](Java-Example-Files/basics/Cricketer.java) | Class and object basics. |
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
