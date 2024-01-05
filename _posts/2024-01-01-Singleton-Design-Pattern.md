---
title: Singleton Design Pattern
date: 2024-01-01 00:00:00 +0530
categories: [Software Architecture]
tags: [design patterns]
---

## Singleton Design Pattern

### Problem

- **Shared Resource:** Imagine having a class responsible for managing the database connection or logging mechanism. You want to ensure that only one instance of this class exists to avoid multiple connections or log files.

- **Single Access Point:** Applications often require configuration. For instance, configuring database connection parameters. You want a single access point for the configuration parameters to prevent multiple instances and conflicting configurations.

### Solution

The **Singleton pattern** is a creational design pattern that ensures a class has only one instance while providing a global access point to this instance. The following steps are involved in implementing the Singleton pattern:

1. **Constructor Hiding:** The constructor of the singleton class should be private or protected to prevent external instantiation.

2. **Global Access Point:** The singleton class should provide a global access point to retrieve its instance. This access point should be static and return the same instance every time it's called.

### Simple Singleton

```java
public class Database {
    private static Database instance = new Database();

    private Database() {
    }

    public static Database getInstance() {
        return instance;
    }
}
```

To implement the `getInstance()` method, a static variable is used for lazy initialization.

### Thread-Safe Singleton

To make the simple singleton thread-safe, make the `getInstance()` method synchronized.

```java
public class Database {
    private static Database instance = null;

    private Database() {
    }

    public static synchronized Database getInstance() {
        if (instance == null) {
            instance = new Database();
        }
        return instance;
    }
}
```

### Double-Checked Locking

To improve efficiency, use double-checked locking.

```java
public class Database {
    private static Database instance = null;

    private Database() {
    }

    public static Database getInstance() {
        if (instance == null) {
            synchronized (Database.class) {
                if (instance == null) {
                    instance = new Database();
                }
            }
        }
        return instance;
    }
}
```

### Summary

- The singleton pattern ensures a class has only one instance with a global access point.
- Use cases: Shared resources like database connections, logging mechanisms, and objects that should be instantiated only once, such as configuration objects.
- Hide the constructor of the singleton class by making it private.
- Add a static method to return the instance, creating it if it doesn't exist.
- For thread safety, make the `getInstance()` method synchronized or use double-checked locking.


