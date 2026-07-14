# Chapter 2 — Understanding Every Type

> **লক্ষ্য:** TypeScript-এর প্রতিটি Type, তাদের পার্থক্য এবং কখন কোনটি ব্যবহার করতে হয় তা শেখা।

---

# 2.1 string

Text সংরক্ষণ করে।

```ts
let name: string = "Asif";
```

Methods

```ts
name.toUpperCase();
name.toLowerCase();
```

---

# 2.2 number

সব ধরনের Number।

```ts
let age: number = 21;
let price: number = 99.99;
```

JavaScript-এ `int`, `float`, `double` নেই।

সবই `number`।

---

# 2.3 boolean

শুধু `true` অথবা `false`।

```ts
let isLogin: boolean = true;
```

---

# 2.4 bigint

খুব বড় Integer রাখার জন্য।

```ts
let num: bigint = 999999999999999999999n;
```

> শেষে `n` লিখতে হয়।

---

# 2.5 symbol

Unique Value তৈরি করে।

```ts
const id = Symbol();
```

```ts
Symbol() === Symbol(); // false
```

মূলত Unique Identifier হিসেবে ব্যবহার হয়।

---

# 2.6 null

Intentional Empty Value।

```ts
let value: null = null;
```

অর্থ → এখানে ইচ্ছা করে কোনো Value রাখা হয়নি।

---

# 2.7 undefined

Variable-এর কোনো Value নেই।

```ts
let value: undefined = undefined;
```

---

# 2.8 any

সব ধরনের Value রাখা যায়।

```ts
let value: any = 10;

value = "Hello";

value = true;
```

❌ Type Checking বন্ধ।

---

# 2.9 unknown

সব ধরনের Value রাখা যায়।

কিন্তু ব্যবহার করার আগে Type Check করতে হবে।

```ts
let value: unknown = "Hello";

if (typeof value === "string") {
  console.log(value.toUpperCase());
}
```

✅ Safe Version of `any`

---

# 2.10 void

Function কিছু Return না করলে।

```ts
function greet(): void {
  console.log("Hello");
}
```

---

# 2.11 never

Function কখনো Return করবে না।

```ts
function error(): never {
  throw new Error();
}
```

অথবা

```ts
while (true) {}
```

---

# 2.12 object

শুধু Object গ্রহণ করে।

```ts
let user: object = {
  name: "Asif",
};
```

❌ Property Access করা যায় না।

```ts
user.name; // Error
```

কারণ TypeScript জানে না ভিতরে কী আছে।

---

# 2.13 Object

JavaScript-এর Built-in Object Type।

```ts
let value: Object = {};
```

এটিও খুব কম ব্যবহার করা হয়।

---

# 2.14 {}

মানে **যেকোনো Non-nullish Value**।

```ts
let value: {} = "Hello";

value = 100;

value = true;

value = [];

value = {};
```

❌ শুধুমাত্র

```ts
null
undefined
```

রাখা যায় না।

---

# 2.15 object vs Object vs {}

| Type | কী রাখে |
|------|----------|
| object | শুধু Object |
| Object | সব Object Wrapper |
| {} | সব Non-nullish Value |

**Best Practice**

বাস্তব Project-এ এগুলো খুব কম ব্যবহার করা হয়।

বরং

```ts
type User = {
  name: string;
};
```

অথবা

```ts
interface User {
  name: string;
}
```

ব্যবহার করা হয়।

---

# 2.16 কখন কোন Type ব্যবহার করবে?

| Situation | Type |
|-----------|------|
| Text | string |
| Number | number |
| True/False | boolean |
| Large Integer | bigint |
| Unique Value | symbol |
| Empty | null |
| No Value | undefined |
| Unknown Data | unknown |
| Anything (Avoid) | any |
| No Return | void |
| Never Return | never |

---

# 🔥 Best Practices

- `any` ব্যবহার করো না
- `unknown` Prefer করো
- `object`, `Object`, `{}` Avoid করো
- নিজের Object Type তৈরি করো
- Primitive Types যতটা সম্ভব Explicit রাখো

---

# 📝 Quick Revision

- `string` → Text
- `number` → সব Number
- `boolean` → true / false
- `bigint` → বড় Integer
- `symbol` → Unique Value
- `null` → Intentional Empty
- `undefined` → Value নেই
- `any` → Type Checking বন্ধ
- `unknown` → Safe `any`
- `void` → কিছু Return করে না
- `never` → কখনো Return করে না
- `object` → শুধু Object
- `Object` → Built-in Object Type
- `{}` → সব Non-nullish Value