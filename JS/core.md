### 1. JavaScript কী?

JavaScript হলো একটি high-level, interpreted/JIT-compiled, dynamically typed programming language, যা মূলত web page-কে interactive এবং dynamic করার জন্য ব্যবহৃত হয়।

### 2. ECMAScript কী?

এটা খুব important।

অনেকে JavaScript এবং ECMAScript একই জিনিস মনে করে, কিন্তু technically পুরোপুরি same না।

সহজভাবে:

ECMAScript হলো JavaScript-এর specification বা standard।

আর JavaScript হলো সেই specification follow করে তৈরি language implementation।

উদাহরণ:

ভাবো:

ECMAScript = Rule Book
JavaScript = সেই Rule Book follow করা language

ECMAScript বলে দেয়:

let
const
Arrow functions
Classes
Promises
Modules

এসব কীভাবে কাজ করবে।

ES6 / ES2015

সবচেয়ে famous version:

ES6 = ECMAScript 2015

এখানে আসে:

let
const
arrow functions
classes
template literals
destructuring
spread/rest
promises

এরপর প্রতি বছর নতুন ECMAScript version আসে।

Interview Answer

ECMAScript is the official specification or standard that defines how JavaScript should behave. JavaScript engines implement this specification.

### 3. JavaScript Engine কী?

JavaScript code computer directly বুঝতে পারে না।

তাই JavaScript code execute করার জন্য একটি JavaScript Engine লাগে।

Example:

const x = 10 + 20;

তুমি code লেখার পর JavaScript engine সেটা process এবং execute করে।

Popular JavaScript engines:

Engine Used By
V8 Chrome, Node.js
SpiderMonkey Firefox
JavaScriptCore Safari

সব engine-এর কাজ মূলত:

JavaScript code → Machine-understandable instructions → Execution

### 4. V8 Engine কী?

V8 হলো Google's JavaScript Engine।

এটি মূলত ব্যবহৃত হয়:

Google Chrome
Node.js

V8 JavaScript code execute করে efficiently।

একটি important point:

অনেকে বলে:

JavaScript is interpreted language.

আবার কেউ বলে:

JavaScript is compiled language.

Modern JavaScript engine-এর ক্ষেত্রে দুটো statement পুরো picture দেয় না।

Modern engines সাধারণত JIT (Just-In-Time) compilation ব্যবহার করে।

সহজভাবে:

```
JavaScript Code
       ↓
JavaScript Engine
       ↓
Parsing
       ↓
Bytecode / Internal Representation
       ↓
JIT Optimization & Compilation
       ↓
Machine Code
       ↓
Execution
```

Interview-এ safe answer:

Modern JavaScript engines use interpretation and Just-In-Time (JIT) compilation techniques to execute JavaScript efficiently.

### 5. JavaScript কি Single-Threaded?

হ্যাঁ, JavaScript-এর main execution thread single-threaded।

মানে একটি সময়ে main thread একটাই কাজ execute করে।

উদাহরণ:

```
console.log("A");
console.log("B");
console.log("C");

Output:

A
B
C
```

JavaScript একটার পর একটা execute করে।

কিন্তু প্রশ্ন আসতে পারে:

তাহলে setTimeout, API request, fetch() এগুলো কীভাবে asynchronous?

এর কারণ:

JavaScript language/runtime ecosystem-এর মধ্যে থাকে:

JavaScript Engine
Call Stack
Web APIs বা host APIs
Task Queue
Microtask Queue
Event Loop

এই পুরো topic আমরা পরে Event Loop chapter-এ deeply পড়ব।

এখন শুধু মনে রাখো:

JavaScript main thread single-threaded, কিন্তু runtime environment-এর সাহায্যে asynchronous operations handle করতে পারে।

#### JavaScript is fundamentally single-threaded and synchronous in its execution model. However, its runtime environment provides APIs and an event loop that allow it to handle asynchronous operations.

```
Q1: What is JavaScript?

Answer:

JavaScript is a high-level, dynamically typed programming language primarily used to create interactive and dynamic web applications. It can run in browsers and server-side environments such as Node.js.

Q2: Is JavaScript single-threaded?

Answer:

Yes, JavaScript's main execution model is single-threaded, meaning it executes code on one main call stack. However, asynchronous operations can be handled with the help of the runtime environment, APIs, queues, and the event loop.

Q3: What is ECMAScript?

Answer:

ECMAScript is the official specification or standard that defines the rules and features of JavaScript. JavaScript engines implement the ECMAScript specification.

Q4: What is the difference between JavaScript and ECMAScript?

Answer:

ECMAScript is the specification, while JavaScript is a programming language implementation based on that specification.

Q5: What is a JavaScript Engine?

Answer:

A JavaScript engine is software that parses, compiles, optimizes, and executes JavaScript code.

Examples include V8, SpiderMonkey, and JavaScriptCore.

Q6: What is V8?

Answer:

V8 is Google's open-source JavaScript engine. It is used by Google Chrome and Node.js to execute JavaScript code.

Q7: Is JavaScript interpreted or compiled?

Best Answer:

Modern JavaScript engines use both interpretation and Just-In-Time compilation techniques. JavaScript is typically parsed and executed through internal representations such as bytecode, while frequently executed code may be optimized and compiled to machine code.

Q8: What is JIT Compilation?

Answer:

JIT stands for Just-In-Time compilation. It is a technique where code is compiled and optimized during runtime to improve execution performance.

Q9: Is JavaScript synchronous or asynchronous?

Answer:

JavaScript is fundamentally synchronous and single-threaded, but it can handle asynchronous operations using runtime-provided APIs, callbacks, promises, async/await, and the event loop.

Q10: How can JavaScript handle asynchronous operations if it is single-threaded?

Answer:

JavaScript uses its runtime environment for asynchronous operations. For example, browsers provide Web APIs and Node.js provides runtime APIs. When asynchronous work completes, callbacks or promise reactions are queued, and the event loop coordinates when they can run on the main call stack.
```
