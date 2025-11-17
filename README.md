# MethodChanning

## 👨‍💻 Author

**Arpit Choubey — SDET | QA | Automation Engineer**
🔗 **LinkedIn** | **Medium**

## ⭐ Support

If this repository helps you, please **Star 🌟** it!

## Folder Structure

```
MethodChanning/
├── eclipse-workspace/
│   └── SeleniumPractice/
│       └── MethodChanning2/
│           └── src/
│               └── MethodChaningConcepts/
│                   ├── Demo.java
│                   ├── MethodRepo.java
│                   ├── StreamExample.java
│                   └── package-info.java
├── .classpath
├── .gitignore
├── .project
└── README.md
```

## Project overview

This small Java repository demonstrates **method chaining** (also called the named-parameter idiom) and a simple example of using Java Streams to transform lists. The sample code files included show how a class can return `this` from methods to allow multiple method calls to be chained in one statement, and how mapping with streams replaces manual loops.

Files in this repository

* `src/MethodChaningConcepts/MethodRepo.java` – The class that implements methods returning `this` so they can be chained.
* `src/MethodChaningConcepts/Demo.java` – A simple `main` showing both single calls and chained calls to `MethodRepo`.
* `src/MethodChaningConcepts/StreamExample.java` – Example showing a manual loop to append `"Fruit"` and the equivalent using Java Streams (`map` + `collect`).
* `package-info.java`, `.gitignore`, etc. – small project metadata files.

---

## What is method chaining?

Method chaining is an object-oriented coding style where methods return the object (usually `this`) so multiple calls can be invoked in a single expression. This produces compact, readable code like:

```java
methodrepo.printAge(99).printName("Ram Kumar");
```

Each method performs its action and returns the same object instance so the next method call continues on that instance.

**Benefits**

* Fluent and readable code (reduces temporary variables)
* Helpful for builder-style APIs and configuration DSLs
* Encourages immutability patterns when implemented with new objects (not shown here)

**Trade-offs / cautions**

* Debugging a long chain can be slightly harder (harder to log intermediate states)
* If methods mutate shared state care must be taken for thread-safety

---

## Quick walkthrough of the provided code

### `MethodRepo` (core idea)

```java
public MethodRepo printName(String Name) {
    System.out.println("Name is " + Name);
    return this;
}

public MethodRepo printAge(int Age) {
    System.out.println("Age is " + Age);
    return this;
}
```

Both methods print a value and return `this`, enabling chaining.

### `Demo` (usage)

```java
MethodRepo methodrepo = new MethodRepo();
methodrepo.printAge(36);
methodrepo.printName("Arpit");

// Method chaining example:
methodrepo.printAge(99).printName("Ram Kumar");
```

Shows normal separate calls and one chained call.

### `StreamExample` (list transformation)

* Demonstrates manual loop building a new `List<String>` by appending `"Fruit"` to each element and printing before/after.
* Then shows the equivalent with `names.stream().map(x -> x + "Fruit").collect(Collectors.toList())`.

---

## How to run

1. Import the project into your IDE (Eclipse, IntelliJ) as a Java project or compile with `javac`.
2. Run `Demo` to see method chaining output.
3. Run `StreamExample` to compare manual loop vs stream mapping.

Example output (Demo):

```
Age is 36
Name is Arpit
Age is 99
Name is Ram Kumar
```

## Notes & suggestions

* Consider renaming the package from `MethodChaningConcepts` to `methodchaining` (consistent naming) and fix the spelling `MethodChanning` vs `MethodChaining` if desired.
* Add JavaDoc comments to methods for clearer documentation.
* Add a small unit test for the `MethodRepo` behavior if you later evolve the example into a library.

---


