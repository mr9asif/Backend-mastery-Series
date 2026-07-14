# Chapter 5 — Union, Intersection & Literal Types

> **লক্ষ্য:** একাধিক Type নিয়ে কাজ করা এবং TypeScript-এর Flexible Type System বোঝা।

---

# 5.1 Union Type (`|`)

একটি Variable একাধিক Type ধারণ করতে পারে।

```ts
let value: string | number;

value = "Hello";
value = 100;
```

✅ দুইটিই Valid।

---

# 5.2 Union কেন ব্যবহার করি?

যখন Data একাধিক Type হতে পারে।

```ts
function print(id: string | number) {
  console.log(id);
}
```

Call

```ts
print(1);
print("101");
```

---

# 5.3 Union-এর সমস্যা

```ts
let value: string | number;

value.toUpperCase(); // ❌ Error
```

কারণ TS জানে না এটা `string` নাকি `number`।

---

# 5.4 Literal Type

একটি নির্দিষ্ট Value-ই Type।

```ts
let status: "success";

status = "success";
```

```ts
status = "failed"; // ❌ Error
```

---

# 5.5 Multiple Literal Type

```ts
type Status =
  | "pending"
  | "success"
  | "failed";
```

```ts
let status: Status;

status = "pending";
```

---

# 5.6 Literal Type-এর Use Case

API Status

```ts
type Status =
  | "loading"
  | "success"
  | "error";
```

Theme

```ts
type Theme =
  | "light"
  | "dark";
```

Role

```ts
type Role =
  | "admin"
  | "user"
  | "guest";
```

---

# 5.7 Intersection Type (`&`)

দুই বা তার বেশি Type একসাথে Merge করা।

```ts
type Person = {
  name: string;
};

type Student = {
  roll: number;
};

type User = Person & Student;
```

Result

```ts
{
  name: string;
  roll: number;
}
```

---

# 5.8 Intersection কেন ব্যবহার করি?

বিভিন্ন Type Combine করার জন্য।

```ts
type Timestamp = {
  createdAt: Date;
};

type User = {
  name: string;
};

type UserWithTime =
  User & Timestamp;
```

---

# 5.9 Union vs Intersection

## Union

```ts
string | number
```

➡️ যেকোনো একটি।

---

## Intersection

```ts
A & B
```

➡️ দুটোই থাকতে হবে।

---

# 5.10 Literal + Union

সবচেয়ে বেশি ব্যবহৃত Combination।

```ts
type Direction =
  | "left"
  | "right"
  | "up"
  | "down";
```

---

# 5.11 Object Union

```ts
type Cat = {
  meow: () => void;
};

type Dog = {
  bark: () => void;
};

let pet: Cat | Dog;
```

এখানে `pet.meow()` সরাসরি Call করা যাবে না।

আগে Type Narrow করতে হবে।

---

# 5.12 Common Mistakes

❌

```ts
let value: string | number;

value.toUpperCase();
```

কারণ Type নিশ্চিত নয়।

---

❌

Intersection মানে "অথবা" মনে করা।

```ts
A & B
```

মানে **A এবং B দুটোই।**

---

# 5.13 Best Practices

- Fixed Value-এর জন্য Literal Type ব্যবহার করো।
- Multiple Option-এর জন্য Union ব্যবহার করো।
- Object Merge-এর জন্য Intersection ব্যবহার করো।
- Magic String লিখো না।

---

# 📝 Quick Revision

- `|` → Union (একাধিক Type)
- `&` → Intersection (সব Type একসাথে)
- Literal Type → নির্দিষ্ট Value
- Literal + Union → সবচেয়ে বেশি ব্যবহৃত Pattern
- Union-এ Method Call করার আগে Type Narrow করতে হয়