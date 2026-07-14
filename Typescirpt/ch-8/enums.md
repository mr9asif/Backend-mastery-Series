# Chapter 8 — Enums

> **লক্ষ্য:** Enum কী, কীভাবে কাজ করে, কখন ব্যবহার করতে হয় এবং কখন Avoid করতে হয়।

---

# 8.1 Enum কী?

**Enum (Enumeration)** হলো Related Constant Value-এর একটি Group।

Example

```ts
enum Role {
  Admin,
  User,
  Guest,
}
```

ব্যবহার

```ts
let role: Role = Role.Admin;
```

---

# 8.2 Numeric Enum

Default Enum।

```ts
enum Direction {
  Up,
  Down,
  Left,
  Right,
}
```

Value

```ts
Up = 0
Down = 1
Left = 2
Right = 3
```

---

# 8.3 Custom Value

নিজে Value দিতে পারো।

```ts
enum Status {
  Success = 200,
  NotFound = 404,
  Error = 500,
}
```

---

# 8.4 String Enum

```ts
enum Role {
  Admin = "ADMIN",
  User = "USER",
}
```

ব্যবহার

```ts
Role.Admin;
```

---

# 8.5 Mixed Enum

Number + String একসাথে।

```ts
enum Test {
  A = 1,
  B = "Hello",
}
```

⚠️ ব্যবহার না করাই ভালো।

---

# 8.6 Enum Access

```ts
enum Color {
  Red,
  Blue,
}

console.log(Color.Red);
```

Result

```ts
0
```

---

# 8.7 Reverse Mapping

শুধু Numeric Enum-এ কাজ করে।

```ts
enum Color {
  Red,
  Blue,
}

console.log(Color[0]);
```

Result

```ts
"Red"
```

String Enum-এ Reverse Mapping নেই।

---

# 8.8 Computed Enum

```ts
enum Size {
  Small = 10,
  Medium = Small * 2,
}
```

---

# 8.9 const enum

Compile-এর সময় Remove হয়ে যায়।

```ts
const enum Role {
  Admin,
  User,
}

let role = Role.Admin;
```

Compile হলে

```js
let role = 0;
```

কোনো Enum Object তৈরি হয় না।

---

# 8.10 Behind the Scenes

Normal Enum

```ts
enum Role {
  Admin,
}
```

Compile হলে

```js
var Role;

(function (Role) {
  Role[(Role["Admin"] = 0)] = "Admin";
})(Role || (Role = {}));
```

অর্থাৎ Runtime-এ Object তৈরি হয়।

---

# 8.11 Enum vs Literal Union

Enum

```ts
enum Theme {
  Light,
  Dark,
}
```

Literal Union

```ts
type Theme =
  | "light"
  | "dark";
```

---

# 8.12 কোনটা ব্যবহার করবে?

**Frontend / Backend Project**

✅ বেশি ব্যবহার হয়

```ts
type Theme =
  | "light"
  | "dark";
```

কারণ

- Lightweight
- Better Type Inference
- Runtime Code তৈরি হয় না

---

Enum ব্যবহার করা হয়

- Status Code
- Permission
- Fixed Constants
- Legacy Project

---

# 8.13 Enum Member Type

```ts
enum Role {
  Admin,
  User,
}

let role: Role = Role.User;
```

Role নিজেই একটি Type।

---

# 8.14 Common Mistakes

❌

Mixed Enum ব্যবহার করা।

---

❌

সব জায়গায় Enum ব্যবহার করা।

---

❌

String Literal Union ব্যবহার করা যেত, তবুও Enum ব্যবহার করা।

---

# 8.15 Best Practices

- String Enum > Numeric Enum
- Mixed Enum Avoid
- সম্ভব হলে Literal Union ব্যবহার করো
- Performance দরকার হলে `const enum`
- Public API-তে Literal Union বেশি Preferred

---

# 📝 Quick Revision

- Enum → Related Constant-এর Group
- Numeric Enum → Default (0,1,2...)
- String Enum → String Value
- Mixed Enum → Avoid
- Reverse Mapping → শুধু Numeric Enum
- const enum → Runtime Object তৈরি হয় না
- Enum Compile হয়ে Object হয়
- Modern Project → Literal Union বেশি Preferred