# Chapter 15 — Modules & Namespaces

> **Prerequisite:**
> - JavaScript ES Modules
> - Chapter 13 (Type Manipulation)

> **লক্ষ্য:** TypeScript-এ File Management এবং Module System শেখা।

---

# 15.1 Module কী?

## কী?

প্রতিটি File-ই একটি Module।

এক Module থেকে অন্য Module-এ Code Share করা যায়।

---

# 15.2 export

কোনো Variable/Function/Class বাইরে ব্যবহার করার জন্য।

```ts
export const name = "Asif";

export function greet() {}
```

## Use Case

Reusable Code

---

# 15.3 import

অন্য File থেকে Code আনা।

```ts
import { greet } from "./user";
```

---

# 15.4 export default

এক File-এ একটি Main Export।

```ts
export default function greet() {}
```

Import

```ts
import greet from "./user";
```

> **Note:** একটি File-এ একটিই `default export` রাখা যায়।

---

# 15.5 Named Export vs Default Export

### Named Export

```ts
export const name = "";
export const age = 20;
```

```ts
import { name, age } from "./user";
```

---

### Default Export

```ts
export default User;
```

```ts
import User from "./user";
```

---

# 15.6 Re-export (Barrel Export)

একটি File থেকে সব Export করা।

```ts
export * from "./user";
export * from "./post";
```

Import

```ts
import { User } from "./index";
```

## Use Case

Clean Import

---

# 15.7 Type-only Import

শুধু Type Import করা।

```ts
import type { User } from "./types";
```

## Use Case

Performance + Clean Code

---

# 15.8 Type-only Export

```ts
export type User = {
  name: string;
};
```

---

# 15.9 Path Alias

Long Path ছোট করা।

❌

```ts
import User from "../../../../types/user";
```

✅

```ts
import User from "@/types/user";
```

## Use Case

Large Project

---

# 15.10 Module Resolution

TypeScript কীভাবে File খুঁজে পায়।

```ts
import User from "./user";
```

Search করবে

- user.ts
- user.tsx
- user.d.ts
- user/index.ts

---

# 15.11 CommonJS

পুরোনো Module System

```ts
const fs = require("fs");

module.exports = {};
```

## Use Case

Old Node.js Project

---

# 15.12 ES Module

Modern Module System

```ts
import fs from "fs";

export default {};
```

## Use Case

React

Next.js

Modern Node.js

---

# 15.13 Namespace (Legacy)

```ts
namespace App {
  export const name = "TS";
}
```

> ❌ Modern Project-এ ব্যবহার করা হয় না।

Modules ব্যবহার করো।

---

# 15.14 Real Project Structure

```text
src/
│
├── components/
├── pages/
├── hooks/
├── services/
├── utils/
├── types/
├── lib/
├── config/
└── index.ts
```

---

# 15.15 Common Mistakes

❌

সবকিছু `default export` করা।

---

❌

Long Relative Path ব্যবহার করা।

---

❌

Namespace ব্যবহার করা।

---

# 15.16 Best Practices

- Named Export Prefer করো
- Type হলে `import type`
- Barrel Export ব্যবহার করো
- Path Alias ব্যবহার করো
- Namespace Avoid করো
- ES Module ব্যবহার করো

---

# 📝 Quick Revision

- Module → File
- export → বাইরে পাঠায়
- import → বাইরে থেকে আনে
- default → Main Export
- Named Export → Multiple Export
- Barrel → Re-export
- import type → শুধু Type
- export type → শুধু Type
- Path Alias → Short Import
- Module Resolution → File Search
- CommonJS → require()
- ES Module → import/export
- Namespace → Legacy