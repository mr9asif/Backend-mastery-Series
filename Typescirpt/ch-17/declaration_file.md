# Chapter 17 — Declaration Files (.d.ts)

> **Prerequisite:**
> - Chapter 16 (Compiler & tsconfig)

> **লক্ষ্য:** `.d.ts` File কী, কেন লাগে এবং কখন ব্যবহার করতে হয়।

---

# 17.1 .d.ts কী?

## কী?

শুধু **Type Declaration** রাখার File।

> এখানে JavaScript Code থাকে না, শুধু Type থাকে।

---

# 17.2 কেন লাগে?

যখন TypeScript কোনো JavaScript Code-এর Type জানে না।

```
JavaScript Code
      │
      ▼
   .d.ts File
      │
      ▼
 TypeScript Type বুঝে
```

---

# 17.3 Basic Example

```ts
declare function greet(
  name: string
): void;
```

এখানে শুধু Function-এর Type বলা হয়েছে।

---

# 17.4 declare Keyword

## কী?

TypeScript-কে বলে,

> "এই জিনিসটি অন্য কোথাও আছে, শুধু Type জানিয়ে দিলাম।"

```ts
declare const API_URL: string;
```

---

# 17.5 Module Declaration

যদি কোনো JS Package-এর Type না থাকে।

```ts
declare module "my-library";
```

---

# 17.6 Global Declaration

Global Variable Declare করা।

```ts
declare global {
  interface Window {
    myApp: string;
  }
}
```

ব্যবহার

```ts
window.myApp;
```

---

# 17.7 Custom Type Declaration

```ts
declare module "*.png";
```

## Use Case

React Project-এ

```ts
import logo from "./logo.png";
```

---

# 17.8 Third-party Types

অনেক Library-এর Type আলাদা Package-এ থাকে।

```bash
npm install -D @types/node
```

আরও উদাহরণ

```bash
@types/express
@types/react
@types/jest
```

---

# 17.9 declare vs interface

### declare

কোনো Existing জিনিসের Type জানায়।

---

### interface

নতুন Type তৈরি করে।

---

# 17.10 tsconfig + declaration

```json
{
  "declaration": true
}
```

Build করলে

```
index.ts
```

↓

```
index.js
index.d.ts
```

---

# 17.11 Real Project Use Cases

- npm Package
- React
- Express
- Vite
- Image Import
- Environment Variable
- Third-party JS Library

---

# 17.12 Common Mistakes

❌ `.d.ts` File-এ Logic লেখা।

---

❌ `declare` দিয়ে Variable তৈরি করা।

---

❌ সব Library-এর জন্য নিজে Type লেখা।

আগে `@types/...` আছে কিনা দেখো।

---

# 17.13 Best Practices

- আগে `@types` Package খুঁজো
- `.d.ts`-এ শুধু Type রাখো
- `declare` শুধু Existing Object-এর জন্য
- Global Type কম ব্যবহার করো

---

# 📝 Quick Revision

- `.d.ts` → Type Declaration
- `declare` → Existing Thing-এর Type
- `declare module` → Module Type
- `declare global` → Global Type
- `@types/*` → Third-party Types
- `"declaration": true` → `.d.ts` Generate