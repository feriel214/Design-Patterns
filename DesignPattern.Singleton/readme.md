# 🧩 Singleton Design Pattern in C#

## Overview
- **Type**: Creational Design Pattern  
- **Definition**: Ensures that a class has **only one instance** and provides a **global point of access** to it.  
- **Why**: Useful when exactly one object is needed to coordinate actions across the system.  
- **Common Use Cases**:
  - Configuration manager  
  - Logging service  
  - Database connection manager  
  - Caching / thread pool  

---

## Implementations

### 🔹 Singleton (Not Thread-Safe)
- Instance created only on first access.  
- Simple, but **unsafe in multithreaded environments**.  
- Multiple threads could create multiple instances at the same time.  
- Suitable only for **single-threaded applications** or prototypes.  

---

### 🔹 Singleton (Thread-Safe with Lock)
- Uses a `lock` to ensure only one thread creates the instance.  
- Guarantees safety in multithreaded environments.  
- Slight performance overhead due to locking at every access.  
- Recommended when **thread safety is required**, but performance is not critical.  

---

### 🔹 Singleton (Double-Check Locking)
- Checks instance twice: once **before** acquiring the lock and once **inside**.  
- Reduces performance cost by locking only on the **first initialization**.  
- Thread-safe and more efficient than simple locking.  
- Commonly used in **high-performance multithreaded applications**.  

---

### 🔹 Singleton (Lazy Loading)
- Uses the built-in `.NET `Lazy<T>` class.  
- Instance is created only **when first needed**.  
- Thread-safe **by default** without extra code.  
- Preferred modern way: **clean, efficient, and safe**.  

---

### 🔹 Singleton (Eager Loading)
- Instance is created **at program startup**, even if never used.  
- Very simple and inherently thread-safe.  
- Can **waste resources** if the instance is heavy and unused.  
- Good when the singleton is **always needed**.  

---

## ✅ Summary
- Use **Not Thread-Safe** only for single-threaded scenarios.  
- Use **Thread-Safe with Lock** for simple safety in multi-threaded apps.  
- Use **Double-Check Locking** for performance-sensitive apps.  
- Use **Lazy Loading** for modern, clean, and thread-safe design.  
- Use **Eager Loading** when the singleton is guaranteed to be needed.  
