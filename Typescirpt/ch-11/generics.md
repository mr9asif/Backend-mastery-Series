# Chapter 11 — Generics

> **লক্ষ্য:** Reusable ও Type-safe Code লেখা শেখা।

---

# 11.1 Generic কী?

## কী?

একটি Type-এর পরিবর্তে Placeholder ব্যবহার করা।

```ts
function identity<T>(value: T): T {
  return value;
}
```

## Use Case

একই Function সব Type-এর জন্য ব্যবহার করা।

---

# 11.2 Generic কেন?

Generic ছাড়া

```ts
function stringFn(value: string) {
  return value;
}

function numberFn(value: number) {
  return value;
}
```

Generic দিয়ে

```ts
function identity<T>(value: T): T {
  return value;
}
```

একটাই Function সব Type Handle করবে।

---

# 11.3 Generic Type

```ts
identity<string>("Hello");

identity<number>(100);
```

TypeScript বেশিরভাগ সময় নিজেই Type বুঝে নেয়।

```ts
identity("Hello");
```

---

# 11.4 Multiple Generic

```ts
function pair<T, U>(
  a: T,
  b: U
) {
  return [a, b];
}
```

```ts
pair("Asif", 21);
```

---

# 11.5 Generic Interface

```ts
interface Box<T> {
  value: T;
}
```

```ts
const box: Box<string> = {
  value: "Hello",
};
```

---

# 11.6 Generic Type Alias

```ts
type ApiResponse<T> = {
  data: T;
};
```

```ts
type User = {
  name: string;
};

const res: ApiResponse<User> = {
  data: {
    name: "Asif",
  },
};
```

## Use Case

API Response

---

# 11.7 Generic Class

```ts
class Box<T> {
  constructor(
    public value: T
  ) {}
}
```

```ts
const box = new Box("Hello");
```

---

# 11.8 Generic Array

```ts
const names: Array<string> = [
  "A",
  "B",
];
```

Equivalent

```ts
const names: string[] = [
  "A",
  "B",
];
```

---

# 11.9 Generic Constraint (`extends`)

Type Restrict করা।

```ts
function print<T extends string>(
  value: T
) {
  return value;
}
```

শুধু `string` Accept করবে।

---

# 11.10 Generic with Object

```ts
function getName<
  T extends {
    name: string;
  }
>(user: T) {
  return user.name;
}
```

## Use Case

Object Validation

---

# 11.11 Generic Default

Default Type দেওয়া।

```ts
type Api<T = string> = {
  data: T;
};
```

---

# 11.12 Behind the Scenes

```ts
function identity<T>(x: T) {
  return x;
}
```

Compile হলে

```js
function identity(x) {
  return x;
}
```

> Generic শুধু Compile Time-এ থাকে।

---

# 11.13 Common Mistakes

❌

```ts
function test<T>(a: T) {
  return a.name;
}
```

Error

কারণ `T`-তে `name` থাকার নিশ্চয়তা নেই।

Solution

```ts
T extends {
  name: string;
}
```

---

# 11.14 Best Practices

- `T`, `K`, `V`, `U` নাম ব্যবহার করো
- Generic-এর উপর Constraint দাও
- অপ্রয়োজনীয় Generic লিখো না
- `any`-এর পরিবর্তে Generic ব্যবহার করো

---

# 📝 Quick Revision

- Generic → Type Placeholder
- `<T>` → Generic Type
- Multiple Generic → `<T, U>`
- Generic Interface
- Generic Type Alias
- Generic Class
- Generic Array
- `extends` → Constraint
- Default Generic
- Generic Runtime-এ থাকে না