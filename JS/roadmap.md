## JavaScript Interview Preparation Roadmap

### PHASE 0 — JavaScript Foundation

1. Introduction to JavaScript
   What is JavaScript?
   History of JavaScript
   ECMAScript / ES6+
   JavaScript Engine
   V8 Engine
   Browser vs Node.js
   JavaScript Runtime
   How JavaScript code executes
   Single-threaded language
   Synchronous vs Asynchronous JavaScript
   Interview Questions
   What is JavaScript?
   Is JavaScript single-threaded?
   What is ECMAScript?
   What is a JavaScript engine?
   What is V8?
   Browser JavaScript vs Node.js?
   Is JavaScript synchronous or asynchronous?

PHASE 1 — VARIABLES & DATA TYPES 2. Variables
var
let
const
Declaration
Initialization
Assignment
Redeclaration
Reassignment
Interview Questions
Difference between var, let, and const?
When should you use let?
When should you use const?
Why is var generally avoided?
Can a const object be modified?
Can let be redeclared?
Can var be redeclared?

3. Data Types
   Primitive Types
   String
   Number
   Boolean
   Undefined
   Null
   Symbol
   BigInt
   Non-Primitive Types
   Object
   Array
   Function
   Concepts
   Primitive vs Reference Type
   Mutable vs Immutable
   Stack vs Heap
   Pass by Value
   Pass by Reference behavior
   Interview Questions
   What are primitive data types?
   Primitive vs non-primitive?
   Difference between null and undefined?
   Why is typeof null "object"?
   Is JavaScript pass by value or pass by reference?
   What is mutable vs immutable?
   How are objects stored in memory?

### PHASE 2 — TYPE COERCION & OPERATORS

4. Type Conversion & Coercion
   Explicit Type Conversion
   Implicit Type Coercion
   Number()
   String()
   Boolean()
   Truthy Values
   Falsy Values
   ==
   ===
   Interview Questions
   Difference between == and ===?
   What is type coercion?
   What are falsy values?
   Why does "5" - 2 work?
   Why does "5" + 2 produce a string?
   Why is [] == false true?
   null == undefined কেন true?

5. Operators
   Arithmetic Operators
   Assignment Operators
   Comparison Operators
   Logical Operators
   Ternary Operator
   Nullish Coalescing ??
   Optional Chaining ?.
   Logical Assignment
   Interview Questions
   Difference between || and ???
   Difference between == and Object.is()?
   What is optional chaining?
   How does short-circuit evaluation work?

### PHASE 3 — SCOPE & HOISTING

6. Scope
   Global Scope
   Function Scope
   Block Scope
   Module Scope
   Lexical Scope
   Scope Chain
   Shadowing
   Interview Questions
   What is scope?
   What is lexical scope?
   What is scope chain?
   Function scope vs block scope?
   What is variable shadowing?
   Can var be block scoped?

7. Hoisting
   Variable Hoisting
   Function Hoisting
   var Hoisting
   let and const
   Function Declaration
   Function Expression
   Arrow Function Hoisting
   Temporal Dead Zone (TDZ)
   Interview Questions
   What is hoisting?
   Are let and const hoisted?
   What is TDZ?
   Function declaration vs function expression?
   Why can var return undefined before declaration?
   Why does let throw an error before initialization?

### PHASE 4 — EXECUTION CONTEXT

8. Execution Context
   Global Execution Context
   Function Execution Context
   Creation Phase
   Execution Phase
   Memory Allocation
   Variable Environment
   Lexical Environment
   Call Stack
   Interview Questions
   What is execution context?
   What happens during the creation phase?
   What is the execution phase?
   What is the call stack?
   How does JavaScript execute multiple functions?

### PHASE 5 — FUNCTIONS

9. Functions Fundamentals
   Function Declaration
   Function Expression
   Anonymous Function
   Named Function
   Arrow Function
   Parameters vs Arguments
   Default Parameters
   Rest Parameters
   Return Statement
   Interview Questions
   Function declaration vs expression?
   Arrow function vs regular function?
   Parameters vs arguments?
   What are default parameters?
   What is a rest parameter?

10. Advanced Functions
    First-Class Functions
    Higher-Order Functions
    Callback Functions
    Pure Functions
    Impure Functions
    IIFE
    Recursive Functions
    Interview Questions
    What is a first-class function?
    What is a higher-order function?
    What is a callback?
    What is callback hell?
    What is a pure function?
    What is an IIFE?
    What is recursion?

### PHASE 6 — this, CALL, APPLY, BIND

11. this Keyword
    Global Context
    Function Context
    Object Method
    Arrow Function
    Class
    Constructor Function
    Event Handler
    Strict Mode
    Interview Questions
    What does this refer to?
    this in regular function vs arrow function?
    Why don't arrow functions have their own this?
    What happens to this in strict mode?
    How does this work inside an object method?

12. call, apply, bind
    Function Borrowing
    Explicit Binding
    call()
    apply()
    bind()
    Interview Questions
    Difference between call, apply, and bind?
    Which one returns a new function?
    When should you use bind()?
    What is function borrowing?

### PHASE 7 — OBJECTS

13. Objects
    Object Creation
    Properties
    Methods
    Dot Notation
    Bracket Notation
    Computed Properties
    Object Destructuring
    Object Methods
    Important Methods
    Object.keys()
    Object.values()
    Object.entries()
    Object.assign()
    Object.freeze()
    Object.seal()
    Object.hasOwn()
    Interview Questions
    How do you create an object?
    Dot vs bracket notation?
    What are computed properties?
    Object.freeze() vs Object.seal()?
    How do you check if a property exists?

14. Object Copying
    Reference Copy
    Shallow Copy
    Deep Copy
    Spread Operator
    Object.assign()
    structuredClone()
    JSON cloning limitations
    Interview Questions
    Shallow copy vs deep copy?
    Why doesn't spread create a deep copy?
    How do you deep clone an object?
    What are limitations of JSON cloning?

### PHASE 8 — ARRAYS

15. Array Fundamentals
    Array Creation
    Index
    Mutation
    Array Length
    Important Methods
    push
    pop
    shift
    unshift
    slice
    splice
    concat
    join
    includes
    indexOf
    at

16. Array Iteration Methods
    forEach
    map
    filter
    reduce
    find
    findIndex
    some
    every
    sort
    flat
    flatMap
    Interview Questions
    map() vs forEach()?
    find() vs filter()?
    some() vs every()?
    slice() vs splice()?
    How does reduce() work?
    Does sort() mutate the original array?
    How do you sort numbers correctly?

### PHASE 9 — DESTRUCTURING, SPREAD & REST

17. Modern JavaScript Features
    Array Destructuring
    Object Destructuring
    Default Values
    Nested Destructuring
    Spread Operator
    Rest Operator
    Interview Questions
    Spread vs Rest?
    Can spread create a deep copy?
    How do you merge objects?
    How do you destructure nested objects?

### PHASE 10 — CLOSURE 🔥

18. Closure
    Lexical Environment
    Outer Function
    Inner Function
    Preserving Variables
    Private Variables
    Closure Use Cases
    Interview Questions
    What is a closure?
    How does closure work?
    Why does a closure remember outer variables?
    Real-world use cases?
    Can closures cause memory leaks?
    Closure vs scope?

### PHASE 11 — ASYNCHRONOUS JAVASCRIPT 🔥

19. JavaScript Runtime
    JavaScript Engine
    Call Stack
    Web APIs
    Callback Queue
    Microtask Queue
    Task / Macrotask Queue
    Event Loop
    Interview Questions
    What is the event loop?
    What is the call stack?
    What are Web APIs?
    Microtask vs macrotask?
    Which runs first: Promise or setTimeout()?

20. Callbacks
    Synchronous Callback
    Asynchronous Callback
    Callback Hell
    Error-First Callback
    Interview Questions
    What is callback hell?
    How can callback hell be solved?
    What is an error-first callback?

21. Promises
    Promise States
    Pending
    Fulfilled
    Rejected
    .then()
    .catch()
    .finally()
    Promise Chaining
    Error Propagation
    Static Methods
    Promise.all()
    Promise.allSettled()
    Promise.race()
    Promise.any()
    Interview Questions
    What is a Promise?
    Promise states?
    Promise chaining কীভাবে কাজ করে?
    Promise.all() vs Promise.allSettled()?
    Promise.race() vs Promise.any()?
    What happens when one Promise fails in Promise.all()?

22. Async / Await
    async
    await
    Error Handling
    try/catch
    Sequential Execution
    Parallel Execution
    Promise.all()
    Interview Questions
    What does async return?
    What does await do?
    Can await block the entire JavaScript thread?
    How do you run async operations in parallel?
    How do you handle errors?

### PHASE 12 — PROTOTYPES & INHERITANCE 🔥

23. Prototype
    prototype
    **proto**
    Prototype Chain
    Property Lookup
    Prototype Inheritance
    Interview Questions
    What is a prototype?
    prototype vs **proto**?
    What is prototype chain?
    How does JavaScript find a property?
    What is prototypal inheritance?

24. Constructor Functions
    Constructor Function
    new Keyword
    Instance
    instanceof
    Interview Questions
    What does the new keyword do?
    What happens internally when using new?
    Constructor function vs class?

### PHASE 13 — CLASSES & OOP

25. Classes
    Class Declaration
    Constructor
    Instance Methods
    Static Methods
    Private Fields
    Getters
    Setters
    extends
    super

26. OOP Concepts
    Encapsulation
    Inheritance
    Polymorphism
    Abstraction
    Interview Questions
    Explain four pillars of OOP.
    What is encapsulation?
    How does inheritance work in JavaScript?
    What are static methods?
    What does super() do?

### PHASE 14 — DOM & EVENTS

27. DOM
    DOM Tree
    Selecting Elements
    Creating Elements
    Updating Elements
    Removing Elements
    Important APIs
    querySelector
    querySelectorAll
    getElementById
    createElement
    append
    appendChild
    remove

28. Events
    Event Object
    Event Bubbling
    Event Capturing
    Event Delegation
    preventDefault()
    stopPropagation()
    stopImmediatePropagation()
    Interview Questions
    What is event bubbling?
    What is event capturing?
    What is event delegation?
    preventDefault() vs stopPropagation()?
    Why is event delegation useful?

### PHASE 15 — DEBOUNCE & THROTTLE 🔥

29. Debouncing
    Concept
    Search Input Use Case
    API Optimization
    Implement from scratch
30. Throttling
    Concept
    Scroll Event
    Resize Event
    Implement from scratch
    Interview Questions
    Debounce vs throttle?
    When would you use debounce?
    When would you use throttle?
    Implement debounce.
    Implement throttle.

### PHASE 16 — ADVANCED FUNCTION CONCEPTS

31. Currying
    Currying
    Partial Application
    Function Composition
    Questions
    What is currying?
    Implement sum(1)(2)(3).
    Currying vs partial application?

32. Memoization
    Cache
    Optimization
    Closure-based Memoization
    Questions
    What is memoization?
    How does memoization improve performance?
    Implement a memoize function.

33. Function Utilities
    নিজে implement করতে হবে:
    once()
    debounce()
    throttle()
    memoize()
    curry()
    compose()
    pipe()

### PHASE 17 — ITERATORS & GENERATORS

34. Iterators
    Iterable
    Iterator
    Iterator Protocol
    Symbol.iterator
35. Generators
    function\*
    yield
    next()
    Generator Use Cases
    Interview Questions
    What is an iterator?
    What is an iterable?
    What is a generator?
    Generator vs normal function?

### PHASE 18 — MAP, SET & WEAK COLLECTIONS

36. Map
    Key-Value Storage
    Any Type as Key
    Iteration
37. Set
    Unique Values
    Removing Duplicates
38. WeakMap & WeakSet
    Weak References
    Garbage Collection
    Limitations
    Interview Questions
    Map vs Object?
    Set vs Array?
    What is WeakMap?
    Why are WeakMaps useful?

### PHASE 19 — SYMBOL & ADVANCED OBJECT FEATURES

39. Symbol
    Unique Values
    Symbol Properties
    Well-Known Symbols
40. Property Descriptors
    Writable
    Enumerable
    Configurable
    Getters
    Setters

### PHASE 20 — MODULES

41. JavaScript Modules
    ES Modules
    export
    import
    Named Export
    Default Export
    CommonJS
    require
    module.exports
    Interview Questions
    CommonJS vs ES Modules?
    Named vs default export?
    Can ES modules be loaded dynamically?
    What is dynamic import?

### PHASE 21 — ERROR HANDLING

42. Errors
    try
    catch
    finally
    throw
    Custom Errors
    Error Object
    Interview Questions
    How do you handle errors?
    throw vs return?
    What does finally do?
    How do you create a custom error?

### PHASE 22 — MEMORY MANAGEMENT & PERFORMANCE

43. Memory Management
    Stack
    Heap
    Garbage Collection
    Reachability
    Memory Leak
    Common Memory Leaks
    Global Variables
    Forgotten Timers
    Event Listeners
    Closures
    Detached DOM Elements
    Interview Questions
    How does garbage collection work?
    What is a memory leak?
    Common causes of memory leaks?

44. Performance Optimization
    Debouncing
    Throttling
    Memoization
    Lazy Loading
    Code Splitting Concept
    Event Delegation
    Avoiding Unnecessary Work

### PHASE 23 — ADVANCED / RARE BUT VALUABLE TOPICS

45. Strict Mode
    "use strict"
    Changes in behavior
    this
    Silent errors
46. Event Loop Advanced
    Microtasks
    Macrotasks
    queueMicrotask
    Promise Jobs
    Timer Queue
47. Dynamic Import
    import()
    Lazy Loading
48. Proxy & Reflect
    Proxy
    Handler
    Trap
    Reflect API
49. Proxy Use Cases
    Validation
    Logging
    Reactive State
    Access Control

### PHASE 24 — CODING INTERVIEW QUESTIONS

String Problems
Reverse a string
Check palindrome
Check anagram
Character frequency
First non-repeating character
Longest word
Capitalize words
Array Problems
Remove duplicates
Find duplicates
Two Sum
Find maximum/minimum
Find missing number
Flatten nested array
Chunk an array
Rotate an array
Intersection of arrays
Merge sorted arrays
Object Problems
Deep clone
Deep comparison
Group array by property
Convert object to array
Convert array to object
Count object property frequency
Function Problems
Implement debounce
Implement throttle
Implement once
Implement memoize
Implement curry
Implement pipe
Implement compose
Polyfills / Custom Implementations
Custom map
Custom filter
Custom reduce
Custom bind
Custom Promise.all
Deep clone

### PHASE 25 — OUTPUT / TRICKY QUESTIONS 🔥

প্রতিটি নিচের topic থেকে output prediction practice করতে হবে:

1. Hoisting
   var
   let
   const
   Function declaration
   Function expression
2. Scope
   Block scope
   Function scope
   Shadowing
3. Closure
   Loop + closure
   var vs let
   Private state
4. this
   Object method
   Regular function
   Arrow function
   call, apply, bind
5. Type Coercion

-

* # ==
  Arrays
  Objects
  null
  undefined

6. Event Loop
   setTimeout
   Promise
   async/await
   Microtask
   Macrotask
7. Objects
   Reference
   Shallow Copy
   Deep Copy
   Mutation
8. Prototype
   Prototype chain
   Inheritance
   Property lookup

### PHASE 26 — FINAL INTERVIEW PREPARATION

Conceptual Questions
প্রতিটি topic-এর জন্য:
Beginner Questions
Intermediate Questions
Advanced Questions
Follow-up Questions
Scenario-based Questions
MCQ Practice
আমরা করব:
Basic MCQ
Intermediate MCQ
Advanced MCQ
Output MCQ
Tricky MCQ
Target:
500+ JavaScript MCQ

Mock Interview
আমাদের mock interview হবে 4 Level-এ।
Level 1 — Beginner
Variables
Data Types
Functions
Scope
Hoisting
Level 2 — Intermediate
Closure
this
Array Methods
Objects
Promise
Level 3 — Advanced
Event Loop
Prototype
Async/Await
Memory
Performance
Level 4 — Real Interview
একদম interviewer style:
Introduction
Concept Questions
Follow-up Questions
Output Questions
Coding Challenge
Scenario-based Questions
শেষে আমি তোমাকে দেব:
Score / 10
Strong Areas
Weak Areas
Wrong Concepts
Improved Answers
Interview Feedback

⭐ MOST IMPORTANT TOPICS — MUST MASTER
এই 15টা topic JavaScript interview-এর জন্য সবচেয়ে বেশি priority:
var, let, const
Data Types
Type Coercion
Scope
Hoisting
Execution Context
Functions
this
Closure
Objects & Arrays
Event Loop
Promise
Async/Await
Prototype & Prototype Chain
Debounce & Throttle
