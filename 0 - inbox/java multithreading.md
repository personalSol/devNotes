---
status: newBorn
related-links: []
created: 2025-04-14T14:26
updated: 2025-04-14T14:37
---
---

## THEORY
### ☕ **Java Multithreading

- **Robust Support**
    - Java provides strong built-in support for **multithreading**, enabling applications to perform **multiple tasks simultaneously**.
    - Improves overall **performance** and **responsiveness**.

---

### ⚙️ **How Multithreading Works in Java**

- **Definition**
    - Multithreading = concurrent execution of **two or more threads** to maximize **CPU utilization**.
    - Supported via the `java.lang` package — easy to implement.

---

### 🧠 **Execution Environments**

- **Single-Core Systems**
    - Threads are managed by the **JVM** and **OS**.
    - Use **time-slicing** to switch between threads, creating the **illusion of parallelism**.
- **Multi-Core Systems**
    - JVM can assign threads to **different cores**, enabling **true parallel execution**.
    - Results in much better performance for CPU-bound tasks.

---

### 🧵 **Thread Lifecycle in Java**

- When a Java program starts, the **main thread** begins execution and runs the `main()` method.
- You can create new threads in two main ways:
    - **Extending** the `Thread` class
    - **Implementing** the `Runnable` interface

## CODE Part

- to check the current thread: `System.out.println(Thread.currentThread().getName());`
# Reference
`related tags + notes + source + link(if any)`
 
- [[tG not-tagged]]
- 