# Chapter 3 — Functions

> **লক্ষ্য:** TypeScript-এ Function সম্পূর্ণভাবে শেখা।

---

# 3.1 Basic Function

```ts
function greet() {
  console.log("Hello");
}
```

---

# 3.2 Parameter Type

Parameter-এর Type নির্দিষ্ট করা।

```ts
function greet(name: string) {
  console.log(name);
}
```

❌ ভুল Type দিলে Error।

---

# 3.3 Return Type

Function কী Return করবে তা লিখে দেওয়া।

```ts
function add(a: number, b: number): number {
  return a + b;
}
```

Syntax

```ts
function name(): ReturnType {}
```

> **Best Practice:** Return Type লিখে দেওয়া ভালো।

---

# 3.4 Optional Parameter (`?`)

Parameter না দিলেও Function চলবে।

```ts
function greet(name?: string) {
  console.log(name);
}
```

Call

```ts
greet();
greet("Asif");
```

---

# 3.5 Default Parameter

Default Value সেট করা।

```ts
function greet(name = "Guest") {
  console.log(name);
}
```

---

# 3.6 Rest Parameter

একাধিক Value নেওয়া।

```ts
function sum(...numbers: number[]) {
  console.log(numbers);
}
```

Call

```ts
sum(1, 2, 3, 4);
```

---

# 3.7 Function Expression

Function Variable-এ রাখা।

```ts
const greet = function (name: string) {
  return name;
};
```

---

# 3.8 Arrow Function

```ts
const greet = (name: string): string => {
  return name;
};
```

Short Form

```ts
const add = (a: number, b: number) => a + b;
```

---

# 3.9 Function Type

Function-ও একটি Type।

```ts
let add: (a: number, b: number) => number;
```

Assign

```ts
add = (a, b) => a + b;
```

---

# 3.10 Type Alias for Function

```ts
type Add = (a: number, b: number) => number;

const sum: Add = (a, b) => a + b;
```

> বড় Project-এ বেশি ব্যবহার হয়।

---

# 3.11 Callback Function

একটি Function-এর ভিতরে আরেকটি Function পাঠানো।

```ts
function process(callback: () => void) {
  callback();
}

process(() => {
  console.log("Done");
});
```

---

# 3.12 Higher Order Function (HOF)

যে Function—

- Function Receive করে
- অথবা Function Return করে

```ts
function greet(fn: () => void) {
  fn();
}
```

---

# 3.13 Function Overloading

একই Function-এর একাধিক Signature।

```ts
function add(a: number, b: number): number;
function add(a: string, b: string): string;

function add(a: any, b: any) {
  return a + b;
}
```

---

# 3.14 void Function

কিছু Return করে না।

```ts
function print(): void {
  console.log("Hello");
}
```

---

# 3.15 never Function

কখনো Return করে না।

```ts
function error(): never {
  throw new Error();
}
```

---

# 3.16 this

Normal Function-এ `this` থাকে।

```ts
const user = {
  name: "Asif",

  greet() {
    console.log(this.name);
  },
};
```

Arrow Function-এর নিজের `this` নেই।

---

# 3.17 Behind the Scenes

TypeScript Compile হওয়ার পর সব Type মুছে যায়।

```ts
function add(a: number, b: number): number {
  return a + b;
}
```

Compile হলে

```js
function add(a, b) {
  return a + b;
}
```

> Runtime-এ Type থাকে না।

---

# 🔥 Best Practices

- সব Parameter-এর Type দাও
- Return Type লিখো
- Arrow Function বেশি ব্যবহার করো
- Function Type Alias ব্যবহার করো
- `any` Avoid করো

---

# 📝 Quick Revision

- Function → কাজ করার Block
- Parameter → Input
- Return Type → Output-এর Type
- Optional → `?`
- Default → Default Value
- Rest → `...`
- Function Expression → Variable-এ Function
- Arrow Function → Modern Syntax
- Function Type → Function-এর Type
- Type Alias → Reusable Function Type
- Callback → Function-এর ভিতরে Function
- Higher Order Function → Function Receive/Return করে
- Overloading → Multiple Signature
- `void` → কিছু Return করে না
- `never` → কখনো Return করে না
- Arrow Function-এর নিজের `this` নেই
- Compile-এর পরে সব Type মুছে যায়