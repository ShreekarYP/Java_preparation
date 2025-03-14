# Java_preparation
notes for preparation 

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Here’s a structured **interview-style Q&A** summary based on what you asked yesterday:  

---

### **🔹 Abstraction vs. Interface**  
**🔸 Interviewer:** What is abstraction in Java?  
**✅ You:**  
Abstraction is the process of hiding implementation details and showing only essential features. It can be achieved using **abstract classes** (partial abstraction) and **interfaces** (100% abstraction).  

**🔸 Interviewer:** What is the difference between an abstract class and an interface?  
**✅ You:**  
| Feature | Abstract Class | Interface |
|---------|--------------|-----------|
| **Methods** | Can have both abstract and concrete methods | Can have abstract, default, and static methods |
| **Variables** | Can have instance variables (any access modifier) | Only public, static, and final variables (constants) |
| **Constructors** | ✅ Yes, can have constructors | ❌ No constructors allowed |
| **Multiple Inheritance** | ❌ Not supported (can extend only one class) | ✅ Supported (can implement multiple interfaces) |
| **Access Modifiers** | Can be `public`, `protected`, `private` | Methods are `public` by default |
| **Final Methods** | ✅ Can have final methods | ❌ Cannot have final methods (as they must be overridden) |

---

### **🔹 Object vs. Instance**  
**🔸 Interviewer:** What is the difference between creating an object and creating an instance?  
**✅ You:**  
- **Object creation** involves memory allocation (`new` keyword).  
- **Instance** refers to the actual reference variable that points to the object.  
```java
Car c = new Car(); // "new Car()" creates the object, "c" is the instance
```

---

### **🔹 Why Can't We Create an Object of an Abstract Class or Interface?**  
**🔸 Interviewer:** Can we create an object of an abstract class?  
**✅ You:**  
No, an **abstract class** cannot be instantiated because it is incomplete. However, we can create an **anonymous inner class** to provide implementations and instantiate it.  

**🔸 Interviewer:** Why can’t we create an object of an interface?  
**✅ You:**  
Interfaces define a **contract**, not behavior. Since interfaces don’t have constructors and are fully abstract, they cannot be instantiated directly.

---

### **🔹 Lambda Expressions & Anonymous Inner Class**  
**🔸 Interviewer:** What is a lambda expression?  
**✅ You:**  
A lambda expression is a **shorter way to implement functional interfaces** (interfaces with a single abstract method).  

```java
interface Greeting {
    void sayHello();
}

public class LambdaExample {
    public static void main(String[] args) {
        Greeting greet = () -> System.out.println("Hello, Java!");
        greet.sayHello();
    }
}
```

**🔸 Interviewer:** Can we use lambda expressions with an abstract class?  
**✅ You:**  
No, **lambda expressions only work with functional interfaces**. Abstract classes can have multiple methods, so they **cannot** be replaced by lambda expressions.

**🔸 Interviewer:** What is an anonymous inner class?  
**✅ You:**  
An **anonymous inner class** is a class without a name that is used for one-time object creation.  
Example:
```java
Greeting greet = new Greeting() {  // Anonymous class
    public void sayHello() {
        System.out.println("Hello, Java!");
    }
};
greet.sayHello();
```

---

### **🔹 String vs. StringBuffer vs. StringBuilder**  
**🔸 Interviewer:** Why is `String` non-primitive?  
**✅ You:**  
Because `String` is a **class** in Java, not a primitive type like `int` or `char`. It **stores characters as an object and provides methods** for manipulation.

**🔸 Interviewer:** What is the difference between `String`, `StringBuffer`, and `StringBuilder`?  
**✅ You:**  

| Feature | String | StringBuffer | StringBuilder |
|---------|--------|-------------|--------------|
| **Mutability** | Immutable | Mutable | Mutable |
| **Thread Safety** | ✅ Thread-safe | ✅ Thread-safe (Synchronized) | ❌ Not thread-safe |
| **Performance** | Slower (New object on modification) | Faster than `String`, but slower than `StringBuilder` | Fastest |

---

### **🔹 Synchronization & Thread Safety**  
**🔸 Interviewer:** What is synchronization?  
**✅ You:**  
Synchronization is a process that **controls access to shared resources** in multi-threading. It ensures that only one thread can access a critical section at a time.

**🔸 Interviewer:** Why is `StringBuffer` synchronized but not `StringBuilder`?  
**✅ You:**  
`StringBuffer` is synchronized to handle multiple threads safely, while `StringBuilder` is **not synchronized**, making it faster for single-threaded applications.

---

### **🔹 `this` vs. `super` Keyword**  
**🔸 Interviewer:** What is the difference between `this` and `super`?  
**✅ You:**  
| Keyword | `this` | `super` |
|---------|--------|--------|
| **Refers to** | Current class instance | Parent class instance |
| **Used for** | Instance variables, methods, constructors | Parent class variables, methods, constructors |
| **Constructor Call** | `this()` calls a constructor in the same class | `super()` calls the parent class constructor |

---

### **🔹 Miscellaneous Quick Answers**
🔹 **Primitive Data Types Sizes**  
| Data Type | Size (Bytes) | Size (Bits) |
|-----------|------------|------------|
| `byte` | 1 | 8 |
| `short` | 2 | 16 |
| `int` | 4 | 32 |
| `long` | 8 | 64 |
| `float` | 4 | 32 |
| `double` | 8 | 64 |
| `char` | 2 | 16 |
| `boolean` | JVM-dependent (typically 1 bit) | JVM-dependent |

🔹 **1 Byte = 8 Bits**  

---

### **🔹 Final Takeaway for Interviews**
If an interviewer asks **conceptual** questions, follow this approach:  
✔ **Define clearly** (What it is)  
✔ **Explain why** (Reason behind it)  
✔ **Give an example** (Simple Java code)  
✔ **Compare if needed** (Table format is best)

Would you like me to format this into a PDF or a structured notes document for quick revision? 🚀
