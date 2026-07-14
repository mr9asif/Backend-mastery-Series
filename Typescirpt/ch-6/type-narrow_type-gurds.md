# Chapter 6 — Type Narrowing & Type Guards

> **লক্ষ্য:** Runtime-এ Type কীভাবে নিশ্চিত করতে হয় এবং TypeScript কীভাবে Type Narrow করে তা শেখা।

---

# 6.1 Type Narrowing কী?

একটি বড় Type থেকে ছোট/নির্দিষ্ট Type বের করাকে **Type Narrowing** বলে।

```ts
let value: string | number;
```

এখানে Type দুইটি।

যদি নিশ্চিত হও এটা `string`, তাহলে Type Narrow হয়েছে।

---

# 6.2 typeof Guard

Primitive Type Check করার জন্য।

```ts
let value: string | number = "Hello";

if (typeof value === "string") {
  console.log(value.toUpperCase());
}
```

Supported

- string
- number
- boolean
- bigint
- symbol
- undefined
- function
- object

---

# 6.3 instanceof Guard

Class বা Constructor Check করার জন্য।

```ts
class Dog {}

const animal = new Dog();

if (animal instanceof Dog) {
  console.log("Dog");
}
```

---

# 6.4 in Operator

Property আছে কিনা Check করে।

```ts
type Cat = {
  meow: () => void;
};

type Dog = {
  bark: () => void;
};

function sound(animal: Cat | Dog) {
  if ("meow" in animal) {
    animal.meow();
  } else {
    animal.bark();
  }
}
```

---

# 6.5 Truthy Narrowing

Truthy/Falsy দিয়েও Narrow করা যায়।

```ts
function print(name?: string) {
  if (name) {
    console.log(name);
  }
}
```

---

# 6.6 Equality Narrowing

```ts
function print(a: string | number) {
  if (a === "hello") {
    console.log(a);
  }
}
```

---

# 6.7 User Defined Type Guard

নিজেই Type Guard তৈরি করা।

```ts
type Cat = {
  meow: () => void;
};

function isCat(
  animal: any
): animal is Cat {
  return "meow" in animal;
}
```

ব্যবহার

```ts
if (isCat(animal)) {
  animal.meow();
}
```

---

# 6.8 Type Predicate

Syntax

```ts
parameter is Type
```

Example

```ts
function isString(
  value: unknown
): value is string {
  return typeof value === "string";
}
```

---

# 6.9 Discriminated Union

সব Object-এ একটি Common Property থাকে।

```ts
type Circle = {
  kind: "circle";
  radius: number;
};

type Square = {
  kind: "square";
  side: number;
};
```

ব্যবহার

```ts
function area(shape: Circle | Square) {
  if (shape.kind === "circle") {
    return Math.PI * shape.radius ** 2;
  }

  return shape.side ** 2;
}
```

✅ Real Project-এ সবচেয়ে বেশি ব্যবহৃত Pattern।

---

# 6.10 Exhaustive Checking

সব Case Handle হয়েছে কিনা নিশ্চিত করা।

```ts
type Shape = Circle | Square;

function area(shape: Shape) {
  switch (shape.kind) {
    case "circle":
      return 1;

    case "square":
      return 2;

    default:
      const x: never = shape;
      return x;
  }
}
```

যদি নতুন Type যোগ করো,

TypeScript Error দিবে।

---

# 6.11 Control Flow Analysis

TypeScript Code Flow Analyze করে।

```ts
let value: string | number;

if (typeof value === "string") {
```

এই Block-এর ভিতরে

```ts
value
```

Type হয়ে যায়

```ts
string
```

Block শেষ হলে আবার

```ts
string | number
```

হয়ে যায়।

এটাকেই বলে

**Control Flow Analysis**

---

# 6.12 asserts

নিজের Assertion Function তৈরি করা।

```ts
function assertString(
  value: unknown
): asserts value is string {
  if (typeof value !== "string") {
    throw new Error();
  }
}
```

ব্যবহার

```ts
assertString(value);

value.toUpperCase();
```

এখন TS জানে `value` হলো `string`।

---

# 6.13 satisfies (TS 4.9+)

Type Check করবে,

কিন্তু Original Type নষ্ট করবে না।

```ts
type User = {
  name: string;
};

const user = {
  name: "Asif",
} satisfies User;
```

✅ `:` এর চেয়ে অনেক ক্ষেত্রে ভালো।

---

# 6.14 Behind the Scenes

Type Narrowing Runtime-এ হয় না।

এটা শুধুই Compiler-এর Analysis।

Compile হওয়ার পরে

```ts
typeof
instanceof
```

থাকে,

কিন্তু

```ts
string
number
User
```

Type থাকে না।

---

# 6.15 Common Mistakes

❌

Union Type-এর Method সরাসরি Call করা।

```ts
value.toUpperCase();
```

---

❌

`any` ব্যবহার করে Guard Skip করা।

---

❌

Discriminated Union ব্যবহার না করা।

---

# 6.16 Best Practices

- `unknown` ব্যবহার করো
- User Defined Type Guard তৈরি করো
- Object Union হলে Discriminated Union ব্যবহার করো
- Switch-এর শেষে `never` দিয়ে Exhaustive Check করো
- নতুন Project-এ `satisfies` Prefer করো

---

# 📝 Quick Revision

- Narrowing → Type ছোট করা
- `typeof` → Primitive Check
- `instanceof` → Class Check
- `in` → Property Check
- Truthy → Boolean Check
- Equality → Value Check
- User Defined Guard → নিজের Guard
- `is` → Type Predicate
- Discriminated Union → Common Literal Property
- Exhaustive Check → `never`
- Control Flow Analysis → Compiler Code Flow Analyze করে
- `asserts` → Assertion Function
- `satisfies` → Type Check + Original Type বজায় রাখে