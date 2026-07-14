# Chapter 7 — Type Assertion & Type Casting

> **লক্ষ্য:** Type Assertion, Type Casting, Non-null Assertion এবং Const Assertion সম্পূর্ণভাবে শেখা।

---

# 7.1 Type Assertion কী?

TypeScript-কে **বিশ্বাস করানো** যে একটি Value-এর Type কী।

> এটি Runtime-এ কিছু পরিবর্তন করে না, শুধু Compiler-কে জানায়।

Syntax

```ts
value as Type
```

Example

```ts
let value: unknown = "Hello";

let name = value as string;
```

---

# 7.2 কেন Type Assertion ব্যবহার করি?

যখন TypeScript Type বুঝতে পারে না, কিন্তু Developer জানে।

Example

```ts
const input = document.getElementById("username") as HTMLInputElement;

input.value = "Asif";
```

---

# 7.3 Angle Bracket Assertion

পুরোনো Syntax

```ts
let value = <string>data;
```

❌ React (TSX)-এ Problem করে।

> **Best Practice:** সবসময় `as` ব্যবহার করো।

---

# 7.4 Type Assertion ≠ Type Conversion

অনেকেই ভুল করে এই দুইটি এক মনে করে।

### Type Assertion

```ts
let value = "100" as unknown;
```

➡️ শুধু Compiler-এর জন্য।

---

### Type Conversion

```ts
Number("100");
String(100);
Boolean(1);
```

➡️ Runtime-এ Value পরিবর্তন হয়।

---

# 7.5 Double Assertion

এক Type থেকে সরাসরি অন্য Type-এ যাওয়া সম্ভব না হলে।

```ts
let value = "Hello" as unknown as number;
```

⚠️ খুব কম ব্যবহার করবে।

---

# 7.6 Non-null Assertion (`!`)

TypeScript-কে বলা,

> "আমি নিশ্চিত এটা `null` বা `undefined` নয়।"

```ts
const input = document.getElementById("name")!;

input.innerHTML = "Hello";
```

❌ যদি আসলেই `null` হয় তাহলে Runtime Error হবে।

---

# 7.7 Optional Chaining (`?.`)

Property না থাকলেও Error হবে না।

```ts
user.address?.city;
```

Equivalent

```ts
if (user.address) {
  user.address.city;
}
```

---

# 7.8 Nullish Coalescing (`??`)

`null` বা `undefined` হলে Default Value দেয়।

```ts
let name = user.name ?? "Guest";
```

Difference

```ts
"" || "Guest"
```

➡️ `"Guest"`

কিন্তু

```ts
"" ?? "Guest"
```

➡️ `""`

---

# 7.9 Const Assertion (`as const`)

সব Property Readonly হয়ে যায়।

```ts
const user = {
  name: "Asif",
} as const;
```

Result

```ts
{
 readonly name: "Asif";
}
```

---

# 7.10 Assertion Function

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

---

# 7.11 Assertion vs Annotation

### Annotation

```ts
let age: number = 20;
```

➡️ Variable Declare করার সময়।

---

### Assertion

```ts
let age = data as number;
```

➡️ পরে Compiler-কে জানানো।

---

# 7.12 Behind the Scenes

```ts
let age = value as number;
```

Compile হলে

```js
let age = value;
```

সব Assertion মুছে যায়।

Runtime-এ কোনো Assertion থাকে না।

---

# 7.13 কখন ব্যবহার করবে?

| Situation | Solution |
|-----------|----------|
| DOM Element | `as HTMLInputElement` |
| Unknown Type | `as Type` |
| Null নিশ্চিত | `!` |
| Readonly Object | `as const` |
| Default Value | `??` |

---

# 7.14 Common Mistakes

❌

```ts
value as any
```

Type Safety নষ্ট করে।

---

❌

```ts
document.getElementById("id")!
```

Null Check ছাড়া ব্যবহার করা।

---

❌

সব জায়গায় Assertion ব্যবহার করা।

যেখানে সম্ভব Type Narrowing ব্যবহার করো।

---

# 7.15 Best Practices

- `as` Prefer করো
- `!` খুব কম ব্যবহার করো
- `unknown` + Type Guard ব্যবহার করো
- `as const` ব্যবহার করো Immutable Data-এর জন্য
- Type Assertion দিয়ে Error Hide করো না

---

# 📝 Quick Revision

- `as` → Type Assertion
- `<Type>` → Old Assertion Syntax
- Assertion ≠ Type Conversion
- `!` → Non-null Assertion
- `?.` → Optional Chaining
- `??` → Nullish Coalescing
- `as const` → Readonly + Literal Type
- Assertion Function → `asserts`
- Compile-এর পরে সব Assertion মুছে যায়