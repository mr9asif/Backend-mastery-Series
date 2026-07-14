# Chapter 16 — TypeScript Compiler & tsconfig

> **Prerequisite:**
> - Chapter 15 (Modules)

> **লক্ষ্য:** TypeScript Compiler এবং `tsconfig.json` সম্পূর্ণভাবে বোঝা।

---

# 16.1 Compiler (tsc)

## কী?

TypeScript কে JavaScript-এ Compile করে।

```bash
tsc
```

## Use Case

Project Build

---

# 16.2 tsconfig.json

## কী?

TypeScript Project-এর Configuration File।

```json
{
  "compilerOptions": {}
}
```

---

# 16.3 target

JavaScript Version।

```json
{
  "target": "ES2022"
}
```

## Use Case

পুরোনো Browser Support হলে ES2017/ES2018

নতুন Project হলে ES2022+

---

# 16.4 module

Module System।

```json
{
  "module": "NodeNext"
}
```

Common Values

- NodeNext
- ESNext
- CommonJS

---

# 16.5 rootDir

Source Code Folder।

```json
{
  "rootDir": "./src"
}
```

---

# 16.6 outDir

Compiled Code কোথায় যাবে।

```json
{
  "outDir": "./dist"
}
```

---

# 16.7 strict

সব Strict Rule চালু করে।

```json
{
  "strict": true
}
```

✅ সব Project-এ `true` রাখো।

---

# 16.8 noImplicitAny

Implicit `any` Allow করবে কি না।

```json
{
  "noImplicitAny": true
}
```

---

# 16.9 strictNullChecks

`null` এবং `undefined` আলাদা Type হিসেবে Check করবে।

```json
{
  "strictNullChecks": true
}
```

---

# 16.10 moduleResolution

Import কীভাবে Resolve হবে।

```json
{
  "moduleResolution": "NodeNext"
}
```

---

# 16.11 baseUrl

Base Import Path।

```json
{
  "baseUrl": "./src"
}
```

---

# 16.12 paths

Path Alias।

```json
{
  "paths": {
    "@/*": ["*"]
  }
}
```

Import

```ts
import User from "@/types/user";
```

---

# 16.13 include

কোন File Compile হবে।

```json
{
  "include": ["src"]
}
```

---

# 16.14 exclude

কোন File Compile হবে না।

```json
{
  "exclude": [
    "node_modules",
    "dist"
  ]
}
```

---

# 16.15 sourceMap

Debug করার জন্য।

```json
{
  "sourceMap": true
}
```

---

# 16.16 declaration

`.d.ts` File Generate করবে।

```json
{
  "declaration": true
}
```

## Use Case

Library Publish

---

# 16.17 incremental

আগের Build Cache ব্যবহার করে।

```json
{
  "incremental": true
}
```

## Use Case

Large Project

---

# 16.18 watch

File Change হলে Auto Compile।

```bash
tsc --watch
```

---

# 16.19 Build Commands

Compile

```bash
tsc
```

Watch

```bash
tsc --watch
```

Init

```bash
tsc --init
```

---

# 16.20 Recommended tsconfig

```json
{
  "compilerOptions": {
    "target": "ES2022",
    "module": "NodeNext",
    "moduleResolution": "NodeNext",
    "rootDir": "./src",
    "outDir": "./dist",
    "strict": true,
    "baseUrl": "./src",
    "paths": {
      "@/*": ["*"]
    },
    "sourceMap": true,
    "declaration": true,
    "incremental": true
  },
  "include": ["src"],
  "exclude": [
    "node_modules",
    "dist"
  ]
}
```

---

# 16.21 Common Mistakes

❌ `strict: false`

---

❌ `dist` Folder Include করা।

---

❌ `rootDir` না দেওয়া।

---

❌ Relative Path বেশি ব্যবহার করা।

---

# 16.22 Best Practices

- `strict: true`
- `rootDir = src`
- `outDir = dist`
- Path Alias ব্যবহার করো
- `sourceMap = true`
- `incremental = true`
- `dist` Git-এ Push করো না

---

# 📝 Quick Revision

- `tsc` → Compiler
- `tsconfig` → Config File
- `target` → JS Version
- `module` → Module System
- `rootDir` → Source Folder
- `outDir` → Build Folder
- `strict` → Strict Mode
- `noImplicitAny` → any Block
- `strictNullChecks` → Null Check
- `baseUrl` → Base Path
- `paths` → Alias
- `include` → Compile Files
- `exclude` → Ignore Files
- `sourceMap` → Debug
- `declaration` → .d.ts
- `incremental` → Faster Build
- `watch` → Auto Compile