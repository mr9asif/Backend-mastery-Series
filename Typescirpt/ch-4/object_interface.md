# Chapter 4 — Objects & Interfaces

> **লক্ষ্য:** Object, Type Alias, Interface এবং তাদের পার্থক্য সম্পূর্ণভাবে শেখা।

---

# 4.1 Object Type

Object-এর প্রতিটি Property-এর Type নির্ধারণ করা যায়।

```ts
let user: {
  name: string;
  age: number;
} = {
  name: "Asif",
  age: 21,
};
```

✅ Structure আগে থেকেই Fixed থাকে।

---

# 4.2 Nested Object

Object-এর ভিতরে Object রাখা যায়।

```ts
let user = {
  name: "Asif",
  address: {
    city: "Dhaka",
    zip: 1200,
  },
};
```

---

# 4.3 Optional Property (`?`)

Property থাকতেও পারে, নাও থাকতে পারে।

```ts
type User = {
  name: string;
  age?: number;
};
```

```ts
const user: User = {
  name: "Asif",
};
```

---

# 4.4 Readonly Property

পরবর্তীতে পরিবর্তন করা যাবে না।

```ts
type User = {
  readonly id: number;
  name: string;
};
```

```ts
user.id = 2; // ❌ Error
```

---

# 4.5 Type Alias

নিজের Type তৈরি করা।

```ts
type User = {
  name: string;
  age: number;
};
```

ব্যবহার

```ts
const user: User = {
  name: "Asif",
  age: 21,
};
```

---

# 4.6 Interface

Object-এর Blueprint।

```ts
interface User {
  name: string;
  age: number;
}
```

```ts
const user: User = {
  name: "Asif",
  age: 21,
};
```

---

# 4.7 Type vs Interface

## Type

```ts
type User = {
  name: string;
};
```

## Interface

```ts
interface User {
  name: string;
}
```

দুটোই প্রায় একই কাজ করে।

---

# 4.8 পার্থক্য

| Type | Interface |
|------|-----------|
| Object + Primitive + Union + Tuple | মূলত Object |
| Declaration Merge হয় না | Declaration Merge হয় |
| Complex Type তৈরি করা যায় | Object Design-এর জন্য Best |

---

# 4.9 Interface Extension

একটি Interface থেকে আরেকটি Interface তৈরি করা।

```ts
interface Person {
  name: string;
}

interface Student extends Person {
  roll: number;
}
```

---

# 4.10 Type Intersection

দুইটি Type একসাথে Merge করা।

```ts
type Person = {
  name: string;
};

type Student = {
  roll: number;
};

type User = Person & Student;
```

---

# 4.11 Interface Multiple Extension

```ts
interface A {
  a: string;
}

interface B {
  b: number;
}

interface C extends A, B {}
```

---

# 4.12 Declaration Merging

শুধু Interface-এ কাজ করে।

```ts
interface User {
  name: string;
}

interface User {
  age: number;
}
```

Result

```ts
interface User {
  name: string;
  age: number;
}
```

❌ Type Alias-এ সম্ভব নয়।

---

# 4.13 Index Signature

আগে থেকে Property Name জানা না থাকলে।

```ts
interface Scores {
  [key: string]: number;
}
```

```ts
const score: Scores = {
  math: 90,
  english: 95,
};
```

---

# 4.14 Readonly Array

```ts
const numbers: readonly number[] = [1, 2, 3];
```

```ts
numbers.push(4); // ❌ Error
```

---

# 4.15 Optional Chaining

```ts
user.address?.city;
```

যদি `address` না থাকে তাহলে Error হবে না।

---

# 4.16 Nullish Coalescing

```ts
let name = user.name ?? "Guest";
```

`null` বা `undefined` হলে Default Value নেয়।

---

# 4.17 Structural Typing (Duck Typing)

TypeScript Name দেখে Type Match করে না।

Structure দেখে Match করে।

```ts
interface User {
  name: string;
}

const person = {
  name: "Asif",
};

const user: User = person;
```

✅ কারণ Structure একই।

> এটিই TypeScript-এর সবচেয়ে গুরুত্বপূর্ণ Concept।

---

# 4.18 Excess Property Check

```ts
interface User {
  name: string;
}

const user: User = {
  name: "Asif",
  age: 21,
};
```

❌ Error

কারণ অতিরিক্ত Property আছে।

---

# 4.19 Type Assertion

Developer TypeScript-কে বলে দেয় Type কী।

```ts
const input = document.getElementById("name") as HTMLInputElement;
```

> সাবধানে ব্যবহার করবে।

---

# 4.20 const Assertion

```ts
const colors = ["red", "blue"] as const;
```

Result

```ts
readonly ["red", "blue"]
```

---

# 4.21 keyof

Object-এর সব Key-এর Union তৈরি করে।

```ts
type User = {
  name: string;
  age: number;
};

type Keys = keyof User;
```

Result

```ts
"name" | "age"
```

---

# 4.22 Common Mistakes

❌ সব জায়গায় `any` ব্যবহার করা

❌ Object-এর বদলে `Object` লেখা

❌ Type আর Interface-এর পার্থক্য না জানা

❌ Excess Property Error না বোঝা

---

# 4.23 Best Practice

- Object-এর জন্য `interface` Prefer করো
- Union/Intersection-এর জন্য `type` ব্যবহার করো
- `readonly` ব্যবহার করো যেখানে পরিবর্তন হবে না
- `any` Avoid করো
- Optional Property শুধুমাত্র দরকার হলে ব্যবহার করো

---

# 📝 Quick Revision

- Object → Key + Value
- Nested Object → Object-এর ভিতরে Object
- Optional → `?`
- Readonly → পরিবর্তন করা যায় না
- Type Alias → নিজের Type
- Interface → Object Blueprint
- `extends` → Interface Inheritance
- `&` → Type Merge
- Declaration Merging → শুধু Interface
- Index Signature → Dynamic Key
- Structural Typing → Structure Match
- Excess Property Check → Extra Property Error
- Type Assertion → `as`
- Const Assertion → `as const`
- `keyof` → Object-এর সব Key