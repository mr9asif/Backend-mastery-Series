# 🟢 What is Node.js?

> **Level:** Beginner → Intermediate

---

# 🎯 Learning Objectives

After completing this lesson, you will be able to:

- Understand what Node.js is.
- Know why Node.js was created.
- Explain the difference between JavaScript and Node.js.
- Understand where Node.js is used.
- Build a strong foundation before learning npm.

---

# 🧠 Mental Model

> **Node.js is a JavaScript Runtime Environment that allows JavaScript to run outside the browser.**

JavaScript is a language.

Node.js is the environment that executes that language on your computer or server.

---

# 🤔 Why was Node.js created?

Before Node.js (2009),

JavaScript could only run inside web browsers.

For example:

- Chrome
- Firefox
- Edge
- Safari

This meant developers could only use JavaScript for frontend development.

Backend development was mostly done using:

- PHP
- Java
- C#
- Python
- Ruby

Ryan Dahl asked a simple question:

> "Why can't JavaScript run on the server?"

The answer to that question became **Node.js**.

---

# 📖 What is Node.js?

Node.js is an **open-source, cross-platform JavaScript runtime environment** built on Google's **V8 JavaScript Engine**.

It allows developers to build:

- Backend APIs
- Web Servers
- REST APIs
- Real-time Applications
- CLI Tools
- Automation Scripts
- Microservices

using JavaScript.

---

# 🏗️ How Node.js Works

```text
JavaScript Code
        │
        ▼
     Node.js
        │
        ▼
     V8 Engine
        │
        ▼
Machine Code
        │
        ▼
Operating System
```

Node.js receives your JavaScript code, uses the V8 Engine to execute it, and communicates with your operating system.

---

# 🌍 Real-World Example

When you run:

```bash
node app.js
```

Node.js:

1. Reads `app.js`
2. Parses the JavaScript code
3. Executes it using the V8 Engine
4. Displays the output

Example:

```js
console.log("Hello Backend!");
```

Output:

```text
Hello Backend!
```

---

# 💡 JavaScript vs Node.js

| JavaScript | Node.js |
|------------|----------|
| Programming Language | Runtime Environment |
| Defines syntax and rules | Executes JavaScript |
| Runs in browser | Runs outside browser |
| Cannot directly access the file system | Can access files, OS, network, processes |

---

# 🌟 Features of Node.js

- Fast (powered by V8)
- Non-blocking I/O
- Event-driven architecture
- Cross-platform
- Huge npm ecosystem
- Great for APIs and real-time apps

---

# 📌 Where is Node.js Used?

Common use cases:

- REST APIs
- Authentication Servers
- Chat Applications
- E-commerce Backends
- Streaming Services
- File Upload Services
- CLI Tools
- Automation Scripts

---

# ⚠️ Common Misconceptions

❌ Node.js is a programming language.

✔️ Wrong.

Node.js is a runtime.

---

❌ Node.js and JavaScript are the same.

✔️ Wrong.

JavaScript is the language.

Node.js is one environment where that language runs.

---

# 💡 Best Practices

- Learn Node.js before Express.
- Understand the runtime, not just the syntax.
- Learn Node.js core modules before using frameworks.

---

# 📝 Practice

Answer these questions:

1. What is Node.js?
2. Who created Node.js?
3. Why was Node.js created?
4. Is Node.js a programming language?
5. What is the main job of Node.js?

---

# 📚 Summary

- JavaScript is a programming language.
- Node.js is a JavaScript runtime environment.
- Node.js allows JavaScript to run outside the browser.
- Node.js is built on Google's V8 Engine.
- It is widely used for backend development, APIs, and server-side applications.