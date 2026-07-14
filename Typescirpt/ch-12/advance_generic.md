# Chapter 12 — Advanced Generics

> **Prerequisite:**
> - Chapter 4 (Objects & Interfaces)
> - Chapter 11 (Generics)

> **লক্ষ্য:** Advanced Generic Techniques শিখে Reusable ও Type-safe Code লেখা।

---

# 12.1 keyof + Generic

## কী?

Object-এর Key নিয়ে কাজ করা।

```ts
function getValue<T, K extends keyof T>(
  obj: T,
  key: K
) {
  return obj[key];
}
```

```ts
const user = {
  name: "Asif",
  age: 21,
};

getValue(user, "name");
```

## Use Case

- Dynamic Property Access
- Utility Function

---

# 12.2 Multiple Constraints

```ts
function merge<
  T extends object,
  U extends object
>(a: T, b: U) {
  return {
    ...a,
    ...b,
  };
}
```

## Use Case

Object Merge

---

# 12.3 Generic with Interface

```ts
interface ApiResponse<T> {
  success: boolean;
  data: T;
}
```

```ts
interface User {
  name: string;
}

const res: ApiResponse<User> = {
  success: true,
  data: {
    name: "Asif",
  },
};
```

---

# 12.4 Generic with Class

```ts
class Storage<T> {
  constructor(
    public value: T
  ) {}
}
```

```ts
const storage = new Storage(100);
```

---

# 12.5 Generic Function Type

```ts
type Identity = <T>(
  value: T
) => T;
```

---

# 12.6 Generic Default

```ts
type Api<
  T = string
> = {
  data: T;
};
```

## Use Case

Default Response Type

---

# 12.7 Generic Factory

```ts
function create<T>(
  value: T
) {
  return {
    value,
  };
}
```

## Use Case

Object Factory

---

# 12.8 Generic Repository Pattern

```ts
interface Repository<T> {
  get(): T;
  save(data: T): void;
}
```

## Use Case

- Prisma
- MongoDB
- SQL Repository

---

# 12.9 Generic Promise

```ts
Promise<string>
Promise<number>
Promise<User>
```

## Use Case

Async Function

---

# 12.10 Generic Map

```ts
Map<string, number>
```

Key → string

Value → number

---

# 12.11 Generic Set

```ts
Set<number>
```

---

# 12.12 Generic Record

```ts
Record<string, number>
```

## Use Case

Dictionary

Config

Cache

---

# 12.13 Generic extends vs implements

```ts
T extends User
```

মানে

Generic Restriction

---

```ts
class Admin implements User
```

মানে

Interface Follow করা।

---

# 12.14 Common Mistakes

❌

Generic লিখেও `any` ব্যবহার করা।

---

❌

অপ্রয়োজনীয় Generic লেখা।

```ts
function test<T>() {}
```

যদি Generic দরকারই না হয়,
তাহলে ব্যবহার করো না।

---

# 12.15 Best Practices

- Generic-এর Meaningful Name ব্যবহার করো (`TUser`, `TData`)
- Constraint ব্যবহার করো
- Reusable Component-এ Generic ব্যবহার করো
- API Response Generic রাখো
- Repository Pattern Generic রাখো

---

# 📝 Quick Revision

- `keyof` + Generic
- Multiple Constraint
- Generic Interface
- Generic Class
- Generic Function Type
- Generic Default
- Generic Factory
- Generic Repository
- Generic Promise
- Generic Map
- Generic Set
- Generic Record
- `extends` → Restrict
- `implements` → Contract