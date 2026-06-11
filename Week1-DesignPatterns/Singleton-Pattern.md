
# Singleton Design Pattern

## What is Singleton?

Singleton is a Creational Design Pattern that ensures:

1. Only ONE object of a class exists.
2. A global access point is provided to that object.

Think:

- Database Connection Manager
- Logger
- Configuration Manager

You only need one object throughout the application.

---

## Real Life Example

Imagine a college principal.

A college can have:

- Many students
- Many teachers

But only ONE principal.

No matter who asks for the principal, they get the same person.

This is Singleton.

---

## Why do we need Singleton?

Without Singleton:

```java
Database db1 = new Database();
Database db2 = new Database();
Database db3 = new Database();
```

Multiple objects get created.

This wastes memory and resources.

With Singleton:

```java
Database db = Database.getInstance();
```

Only one object exists.

---

## Basic Singleton Implementation

```java
class Singleton {

    private static Singleton instance;

    private Singleton() {
    }

    public static Singleton getInstance() {

        if(instance == null) {
            instance = new Singleton();
        }

        return instance;
    }
}
```

Usage:

```java
Singleton obj1 = Singleton.getInstance();
Singleton obj2 = Singleton.getInstance();

System.out.println(obj1 == obj2);
```

Output:

true

Both variables point to the same object.

---

## Advantages

- Saves memory
- Centralized access
- Easy configuration management
- Useful for shared resources

---

## Disadvantages

- Harder to unit test
- Can become global state
- Not ideal if overused

---

## Interview Question

Q: Why is constructor private?

A:
To prevent users from creating objects using:

```java
new Singleton();
```

Only the class itself can create the object.

---

## Where is Singleton Used?

- Spring Beans (default scope)
- Logger
- Configuration Manager
- Database Connection Manager

---

## Key Takeaway

Singleton ensures:

ONE Class
→ ONE Object
→ Global Access
