# 🚀 JavaScript Interview Preparation Roadmap

> **Goal:** JavaScript থেকে Basic → Advanced → Interview Ready হওয়া।
>
> **Study Method:**  
> প্রতিটি topic-এর জন্য:
>
> 1. Concept
> 2. Deep Explanation
> 3. Examples
> 4. Important Notes
> 5. Interview Questions
> 6. MCQ Practice
> 7. Output Prediction
> 8. Coding Practice

---

# 📚 PHASE 0 — JAVASCRIPT FOUNDATION

## 1. Introduction to JavaScript

### Concepts

- [ ] What is JavaScript?
- [ ] History of JavaScript
- [ ] ECMAScript
- [ ] ES6+
- [ ] JavaScript Engine
- [ ] V8 Engine
- [ ] Browser vs Node.js
- [ ] JavaScript Runtime
- [ ] How JavaScript Code Executes
- [ ] Single-Threaded JavaScript
- [ ] Synchronous vs Asynchronous JavaScript

### 🎯 Interview Questions

- What is JavaScript?
- Is JavaScript single-threaded?
- What is ECMAScript?
- What is a JavaScript engine?
- What is V8?
- Browser JavaScript vs Node.js?
- Is JavaScript synchronous or asynchronous?

---

# 📦 PHASE 1 — VARIABLES & DATA TYPES

## 2. Variables

### Concepts

- [ ] `var`
- [ ] `let`
- [ ] `const`
- [ ] Declaration
- [ ] Initialization
- [ ] Assignment
- [ ] Redeclaration
- [ ] Reassignment

### 🎯 Interview Questions

- Difference between `var`, `let`, and `const`?
- When should you use `let`?
- When should you use `const`?
- Why is `var` generally avoided?
- Can a `const` object be modified?
- Can `let` be redeclared?
- Can `var` be redeclared?

---

## 3. Data Types

### Primitive Types

- [ ] String
- [ ] Number
- [ ] Boolean
- [ ] Undefined
- [ ] Null
- [ ] Symbol
- [ ] BigInt

### Non-Primitive Types

- [ ] Object
- [ ] Array
- [ ] Function

### Important Concepts

- [ ] Primitive vs Reference Type
- [ ] Mutable vs Immutable
- [ ] Stack vs Heap
- [ ] Pass by Value
- [ ] Pass by Reference Behavior

### 🎯 Interview Questions

- What are primitive data types?
- Primitive vs non-primitive?
- Difference between `null` and `undefined`?
- Why is `typeof null === "object"`?
- Is JavaScript pass by value or pass by reference?
- What is mutable vs immutable?
- How are objects stored in memory?

---

# 🔄 PHASE 2 — TYPE COERCION & OPERATORS

## 4. Type Conversion & Coercion

### Concepts

- [ ] Explicit Type Conversion
- [ ] Implicit Type Coercion
- [ ] `Number()`
- [ ] `String()`
- [ ] `Boolean()`
- [ ] Truthy Values
- [ ] Falsy Values
- [ ] `==`
- [ ] `===`

### 🎯 Interview Questions

- Difference between `==` and `===`?
- What is type coercion?
- What are falsy values?
- Why does `"5" - 2` work?
- Why does `"5" + 2` produce a string?
- Why is `[] == false` true?
- Why is `null == undefined` true?

---

## 5. Operators

### Concepts

- [ ] Arithmetic Operators
- [ ] Assignment Operators
- [ ] Comparison Operators
- [ ] Logical Operators
- [ ] Ternary Operator
- [ ] Nullish Coalescing `??`
- [ ] Optional Chaining `?.`
- [ ] Logical Assignment Operators

### 🎯 Interview Questions

- Difference between `||` and `??`?
- Difference between `==` and `Object.is()`?
- What is optional chaining?
- How does short-circuit evaluation work?

---

# 🌍 PHASE 3 — SCOPE & HOISTING

## 6. Scope

### Concepts

- [ ] Global Scope
- [ ] Function Scope
- [ ] Block Scope
- [ ] Module Scope
- [ ] Lexical Scope
- [ ] Scope Chain
- [ ] Shadowing

### 🎯 Interview Questions

- What is scope?
- What is lexical scope?
- What is scope chain?
- Function scope vs block scope?
- What is variable shadowing?
- Can `var` be block scoped?

---

## 7. Hoisting

### Concepts

- [ ] Variable Hoisting
- [ ] Function Hoisting
- [ ] `var` Hoisting
- [ ] `let` and `const`
- [ ] Function Declaration
- [ ] Function Expression
- [ ] Arrow Function Hoisting
- [ ] Temporal Dead Zone (TDZ)

### 🎯 Interview Questions

- What is hoisting?
- Are `let` and `const` hoisted?
- What is TDZ?
- Function declaration vs function expression?
- Why can `var` return `undefined` before declaration?
- Why does `let` throw an error before initialization?

---

# ⚙️ PHASE 4 — EXECUTION CONTEXT

## 8. Execution Context

### Concepts

- [ ] Global Execution Context
- [ ] Function Execution Context
- [ ] Creation Phase
- [ ] Execution Phase
- [ ] Memory Allocation
- [ ] Variable Environment
- [ ] Lexical Environment
- [ ] Call Stack

### 🎯 Interview Questions

- What is execution context?
- What happens during the creation phase?
- What is the execution phase?
- What is the call stack?
- How does JavaScript execute multiple functions?

---

# 🧩 PHASE 5 — FUNCTIONS

## 9. Function Fundamentals

### Concepts

- [ ] Function Declaration
- [ ] Function Expression
- [ ] Anonymous Function
- [ ] Named Function
- [ ] Arrow Function
- [ ] Parameters vs Arguments
- [ ] Default Parameters
- [ ] Rest Parameters
- [ ] Return Statement

### 🎯 Interview Questions

- Function declaration vs function expression?
- Arrow function vs regular function?
- Parameters vs arguments?
- What are default parameters?
- What is a rest parameter?

---

## 10. Advanced Functions

### Concepts

- [ ] First-Class Functions
- [ ] Higher-Order Functions
- [ ] Callback Functions
- [ ] Pure Functions
- [ ] Impure Functions
- [ ] IIFE
- [ ] Recursive Functions

### 🎯 Interview Questions

- What is a first-class function?
- What is a higher-order function?
- What is a callback?
- What is callback hell?
- What is a pure function?
- What is an IIFE?
- What is recursion?

---

# 🎯 PHASE 6 — `this`, CALL, APPLY & BIND

## 11. `this` Keyword

### Concepts

- [ ] Global Context
- [ ] Function Context
- [ ] Object Method
- [ ] Arrow Function
- [ ] Class
- [ ] Constructor Function
- [ ] Event Handler
- [ ] Strict Mode

### 🎯 Interview Questions

- What does `this` refer to?
- `this` in regular function vs arrow function?
- Why don't arrow functions have their own `this`?
- What happens to `this` in strict mode?
- How does `this` work inside an object method?

---

## 12. `call()`, `apply()` & `bind()`

### Concepts

- [ ] Function Borrowing
- [ ] Explicit Binding
- [ ] `call()`
- [ ] `apply()`
- [ ] `bind()`

### 🎯 Interview Questions

- Difference between `call`, `apply`, and `bind`?
- Which one returns a new function?
- When should you use `bind()`?
- What is function borrowing?

---

# 🧱 PHASE 7 — OBJECTS

## 13. Objects

### Concepts

- [ ] Object Creation
- [ ] Properties
- [ ] Methods
- [ ] Dot Notation
- [ ] Bracket Notation
- [ ] Computed Properties
- [ ] Object Destructuring

### Important Methods

- [ ] `Object.keys()`
- [ ] `Object.values()`
- [ ] `Object.entries()`
- [ ] `Object.assign()`
- [ ] `Object.freeze()`
- [ ] `Object.seal()`
- [ ] `Object.hasOwn()`

### 🎯 Interview Questions

- How do you create an object?
- Dot vs bracket notation?
- What are computed properties?
- `Object.freeze()` vs `Object.seal()`?
- How do you check if a property exists?

---

## 14. Object Copying

### Concepts

- [ ] Reference Copy
- [ ] Shallow Copy
- [ ] Deep Copy
- [ ] Spread Operator
- [ ] `Object.assign()`
- [ ] `structuredClone()`
- [ ] JSON Cloning Limitations

### 🎯 Interview Questions

- Shallow copy vs deep copy?
- Why doesn't spread create a deep copy?
- How do you deep clone an object?
- What are limitations of JSON cloning?

---

# 📚 PHASE 8 — ARRAYS

## 15. Array Fundamentals

### Concepts

- [ ] Array Creation
- [ ] Index
- [ ] Mutation
- [ ] Array Length

### Important Methods

```text
push()
pop()
shift()
unshift()

slice()
splice()

concat()
join()

includes()
indexOf()
at()
```
