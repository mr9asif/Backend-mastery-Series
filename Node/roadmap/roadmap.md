# 🚀 Phase 01 — Node.js Foundation & Core Runtime

> **Goal:** Build a deep understanding of Node.js from the ground up. By the end of this phase, you should understand **how Node.js works internally**, not just how to write code with it.

---

# 📚 Table of Contents

- Chapter 01 — What is Node.js?
- Chapter 02 — JavaScript Runtime
- Chapter 03 — V8 Engine
- Chapter 04 — Node.js Architecture
- Chapter 05 — Event Loop
- Chapter 06 — Call Stack
- Chapter 07 — Memory (Heap & Stack)
- Chapter 08 — Garbage Collection
- Chapter 09 — Module System (CommonJS & ESM)
- Chapter 10 — npm Package Resolution
- Chapter 11 — Core Modules
- Chapter 12 — File System (`fs`)
- Chapter 13 — Path Module
- Chapter 14 — OS Module
- Chapter 15 — Process Object
- Chapter 16 — Environment Variables
- Chapter 17 — Events & EventEmitter
- Chapter 18 — Streams
- Chapter 19 — Buffers
- Chapter 20 — Timers
- Chapter 21 — Async Programming
- Chapter 22 — HTTP Module
- Chapter 23 — Error Handling
- Chapter 24 — Debugging
- Chapter 25 — Worker Threads
- Chapter 26 — Child Processes
- Chapter 27 — Performance & Profiling
- Chapter 28 — Node.js Best Practices
- Chapter 29 — Real Project Workflow
- Chapter 30 — Interview Preparation

---

# Chapter 01 — What is Node.js?

## Topics

- What is Node.js?
- Why was Node.js created?
- History of Node.js
- Ryan Dahl and the origin of Node.js
- Node.js vs Browser JavaScript
- Features of Node.js
- Advantages & Limitations
- When to use Node.js
- When not to use Node.js
- Real-world use cases
- How Node.js executes JavaScript

### 🎯 Outcome

Understand what Node.js is and why it exists.

---

# Chapter 02 — JavaScript Runtime

## Topics

- What is a Runtime?
- Runtime vs Compiler
- Browser Runtime vs Node Runtime
- Components of a JavaScript Runtime
- Event Loop
- APIs
- Runtime Environment

### 🎯 Outcome

Understand how JavaScript runs outside the browser.

---

# Chapter 03 — V8 Engine

## Topics

- What is the V8 Engine?
- Parsing
- Ignition Interpreter
- TurboFan Compiler
- JIT Compilation
- Optimization
- Deoptimization
- Garbage Collection in V8
- Memory Management

### 🎯 Outcome

Understand how JavaScript code is executed internally.

---

# Chapter 04 — Node.js Architecture

## Topics

- Overall Architecture
- Single Threaded Nature
- Event Driven Architecture
- Non-blocking I/O
- libuv
- Thread Pool
- Event Queue
- Worker Threads
- Request Lifecycle

### 🎯 Outcome

Understand Node.js architecture from a system perspective.

---

# Chapter 05 — Event Loop

## Topics

- What is the Event Loop?
- Event Loop Phases
- Timers
- Pending Callbacks
- Poll
- Check
- Close Callbacks
- Microtasks
- Macrotasks
- process.nextTick()
- queueMicrotask()
- setImmediate()

### 🎯 Outcome

Master asynchronous execution flow.

---

# Chapter 06 — Call Stack

## Topics

- Stack Frames
- Function Calls
- Execution Context
- Stack Overflow
- Recursion
- Execution Order

### 🎯 Outcome

Understand synchronous execution.

---

# Chapter 07 — Memory (Heap & Stack)

## Topics

- Stack Memory
- Heap Memory
- Primitive Values
- Reference Values
- Memory Allocation
- Memory Leaks
- Memory Optimization

### 🎯 Outcome

Understand how memory works in JavaScript.

---

# Chapter 08 — Garbage Collection

## Topics

- Memory Lifecycle
- Mark & Sweep
- Generational GC
- Memory Leaks
- WeakMap
- WeakSet

### 🎯 Outcome

Understand automatic memory management.

---

# Chapter 09 — Module System (CommonJS & ESM)

## Topics

### CommonJS

- require()
- module.exports
- exports

### ES Modules

- import
- export
- export default
- Dynamic Import

### Comparison

- CommonJS vs ESM
- Module Resolution
- Circular Dependencies

### 🎯 Outcome

Master Node.js module systems.

---

# Chapter 10 — npm Package Resolution

## Topics

- Module Resolution Algorithm
- node_modules Lookup
- package.json
- exports
- main
- index.js
- Local Packages
- Global Packages

### 🎯 Outcome

Understand how Node finds packages.

---

# Chapter 11 — Core Modules

## Topics

- fs
- path
- os
- http
- https
- events
- stream
- buffer
- crypto
- url
- util
- child_process
- worker_threads
- timers

### 🎯 Outcome

Know all major built-in modules.

---

# Chapter 12 — File System (fs)

## Topics

- Reading Files
- Writing Files
- Appending
- Renaming
- Deleting
- Directories
- Sync vs Async APIs
- Streams

### 🎯 Outcome

Master file handling.

---

# Chapter 13 — Path Module

## Topics

- path.join()
- path.resolve()
- path.basename()
- path.dirname()
- path.extname()
- Cross-platform Paths

### 🎯 Outcome

Work with file paths correctly.

---

# Chapter 14 — OS Module

## Topics

- CPU
- Memory
- Platform
- Architecture
- Hostname
- Uptime
- Network Interfaces

### 🎯 Outcome

Read system information.

---

# Chapter 15 — Process Object

## Topics

- process.argv
- process.env
- process.cwd()
- process.exit()
- process.pid
- process.stdin
- process.stdout
- Signals

### 🎯 Outcome

Understand the running Node process.

---

# Chapter 16 — Environment Variables

## Topics

- Environment Variables
- dotenv
- Configuration
- Secrets
- Best Practices

### 🎯 Outcome

Manage application configuration securely.

---

# Chapter 17 — Events & EventEmitter

## Topics

- EventEmitter
- emit()
- on()
- once()
- removeListener()
- Custom Events

### 🎯 Outcome

Understand event-driven programming.

---

# Chapter 18 — Streams

## Topics

- Readable Stream
- Writable Stream
- Duplex Stream
- Transform Stream
- Piping
- Backpressure

### 🎯 Outcome

Process large data efficiently.

---

# Chapter 19 — Buffers

## Topics

- What is Buffer?
- Binary Data
- Encoding
- Decoding
- Buffer Allocation
- File Processing

### 🎯 Outcome

Handle binary data effectively.

---

# Chapter 20 — Timers

## Topics

- setTimeout()
- setInterval()
- clearTimeout()
- clearInterval()
- setImmediate()
- process.nextTick()

### 🎯 Outcome

Master scheduling in Node.js.

---

# Chapter 21 — Async Programming

## Topics

- Callback
- Callback Hell
- Promise
- async/await
- Promise.all()
- Promise.race()
- Promise.any()
- Promise.allSettled()

### 🎯 Outcome

Write clean asynchronous code.

---

# Chapter 22 — HTTP Module

## Topics

- HTTP Server
- HTTP Client
- Request
- Response
- Headers
- Routing
- Status Codes

### 🎯 Outcome

Build servers without Express.

---

# Chapter 23 — Error Handling

## Topics

- try...catch
- Error Object
- Custom Errors
- Async Errors
- Unhandled Rejections
- Uncaught Exceptions

### 🎯 Outcome

Handle errors professionally.

---

# Chapter 24 — Debugging

## Topics

- Node Inspector
- Chrome DevTools
- VS Code Debugger
- console
- breakpoints
- stack traces

### 🎯 Outcome

Debug Node applications efficiently.

---

# Chapter 25 — Worker Threads

## Topics

- Why Worker Threads?
- CPU Intensive Tasks
- Message Passing
- SharedArrayBuffer
- Worker Pool

### 🎯 Outcome

Understand multithreading in Node.js.

---

# Chapter 26 — Child Processes

## Topics

- spawn()
- exec()
- execFile()
- fork()
- IPC
- Process Management

### 🎯 Outcome

Run external programs from Node.js.

---

# Chapter 27 — Performance & Profiling

## Topics

- Performance Hooks
- CPU Profiling
- Memory Profiling
- Benchmarking
- Event Loop Delay
- Optimization Techniques

### 🎯 Outcome

Write high-performance Node.js applications.

---

# Chapter 28 — Node.js Best Practices

## Topics

- Folder Structure
- Error Handling
- Async Patterns
- Security
- Logging
- Configuration
- Environment Variables
- Dependency Management
- Clean Code

### 🎯 Outcome

Follow production-ready coding practices.

---

# Chapter 29 — Real Project Workflow

## Topics

- Project Setup
- Configuration
- Development Workflow
- Build Process
- Deployment
- Monitoring
- Logging
- Maintenance

### 🎯 Outcome

Understand how real Node.js projects are developed and maintained.

---

# Chapter 30 — Interview Preparation

## Beginner

- What is Node.js?
- What is npm?
- What is Event Loop?
- What is V8?

## Intermediate

- CommonJS vs ESM
- Heap vs Stack
- Event Loop Phases
- Streams
- Buffers

## Advanced

- libuv
- Thread Pool
- Worker Threads
- Child Processes
- Garbage Collection
- Performance Optimization
- Module Resolution

### 🎯 Outcome

Be ready for Node.js interviews from beginner to senior level.

---

# 🎯 Final Learning Outcome

After completing this phase, you will be able to:

- Explain how Node.js works internally.
- Understand the complete Node.js runtime architecture.
- Master asynchronous programming and the Event Loop.
- Work confidently with built-in Node.js modules.
- Build HTTP servers without Express.
- Handle files, streams, buffers, and processes.
- Optimize performance and debug applications.
- Follow production-ready best practices.
- Answer beginner, intermediate, and senior-level Node.js interview questions.
- Build a strong foundation before learning Express, TypeScript, and backend frameworks.

---

# 🚀 Next Phase

After completing **Phase 01 — Node.js Foundation & Core Runtime**, continue with:

- **Phase 02 — TypeScript Mastery**
- **Phase 03 — Express.js Mastery**
- **Phase 04 — REST API Design**
- **Phase 05 — PostgreSQL**
- **Phase 06 — Prisma ORM**
- **Phase 07 — Authentication & Authorization**
- **...and the remaining Backend Engineering roadmap.**