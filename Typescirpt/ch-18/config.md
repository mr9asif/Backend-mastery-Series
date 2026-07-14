# Chapter 12 — `tsconfig.json` (Complete Mastery)

## 📖 What is `tsconfig.json`?

`tsconfig.json` হলো **TypeScript Project Configuration File**।

এটি `tsc` (TypeScript Compiler)-কে বলে দেয়—

- কোন JavaScript version-এ compile করবে
- কোন file compile করবে
- output কোথায় যাবে
- কতটা strict type checking হবে
- module কীভাবে resolve হবে

Example:

```json
{
  "compilerOptions": {}
}
```

---

# compilerOptions

সব configuration এখানে লেখা হয়।

---

# 1. target

JavaScript-এর কোন version-এ compile হবে।

```json
{
  "target": "ES2022"
}
```

Example

TypeScript

```ts
const user = {
  name: "Asif",
};
```

Compile হতে পারে

```js
var user = {
  name: "Asif",
};
```

অথবা

```js
const user = {
  name: "Asif",
};
```

Target অনুযায়ী output পরিবর্তন হবে।

### Common Values

- ES5
- ES2015
- ES2016
- ES2017
- ES2018
- ES2019
- ES2020
- ES2021
- ES2022
- ESNext

### Backend Recommendation

```text
ES2022
```

---

# 2. module

Module system নির্ধারণ করে।

```json
{
  "module": "NodeNext"
}
```

Common Values

- CommonJS
- ESNext
- Node16
- NodeNext

### Backend

```text
NodeNext
```

### Frontend (Vite)

```text
ESNext
```

---

# 3. lib

JavaScript-এর কোন built-in API ব্যবহার করতে পারবে।

```json
{
  "lib": ["ES2022"]
}
```

Browser Project

```json
{
  "lib": ["DOM", "ES2022"]
}
```

> Node Project-এ সাধারণত `@types/node` ব্যবহার করা হয়।

---

# 4. rootDir

Source code কোথায় আছে।

```json
{
  "rootDir": "./src"
}
```

Example

```
project/
│
├── src/
│   ├── app.ts
│   └── server.ts
```

---

# 5. outDir

Compiled JavaScript কোথায় যাবে।

```json
{
  "outDir": "./dist"
}
```

Example

```
src/
dist/
```

---

# 6. strict

সব strict rule enable করে।

```json
{
  "strict": true
}
```

Production Project

```text
Always true ✅
```

---

# 7. noImplicitAny

Implicit `any` allow করবে কি না।

```json
{
  "noImplicitAny": true
}
```

Wrong

```ts
function add(a, b) {}
```

Correct

```ts
function add(a: number, b: number) {}
```

---

# 8. strictNullChecks

`null` এবং `undefined` strictly check করবে।

```json
{
  "strictNullChecks": true
}
```

Wrong

```ts
let name: string = null;
```

Result

```
Error
```

---

# 9. declaration

`.d.ts` file generate করবে।

```json
{
  "declaration": true
}
```

Useful For

- npm package
- library

Backend API project-এ সাধারণত দরকার হয় না।

---

# 10. removeComments

Compile করার সময় comments remove করবে।

```json
{
  "removeComments": true
}
```

Before

```ts
// user object
const user = {};
```

After

```js
const user = {};
```

---

# 11. sourceMap

Debugging-এর জন্য `.map` file generate করবে।

```json
{
  "sourceMap": true
}
```

VS Code Debugger-এ Original TypeScript file দেখাবে।

---

# 12. baseUrl

Import shortcut।

```json
{
  "baseUrl": "./src"
}
```

Without

```ts
import user from "../../../services/user";
```

With

```ts
import user from "services/user";
```

---

# 13. paths

Import alias তৈরি করে।

```json
{
  "paths": {
    "@/*": ["./src/*"]
  }
}
```

Example

```ts
import User from "@/models/user";
```

Instead of

```ts
import User from "../../../models/user";
```

---

# 14. include

কোন file compile হবে।

```json
{
  "include": ["src"]
}
```

অথবা

```json
{
  "include": ["src/**/*.ts"]
}
```

---

# 15. exclude

কোন file compile হবে না।

```json
{
  "exclude": [
    "node_modules",
    "dist"
  ]
}
```

---

# 16. moduleResolution

Import resolve কিভাবে করবে।

```json
{
  "moduleResolution": "NodeNext"
}
```

Options

- Classic
- Node
- Node16
- NodeNext
- Bundler

Backend

```text
NodeNext
```

Frontend

```text
Bundler
```

---

# 17. resolveJsonModule

JSON import করতে পারবে।

```json
{
  "resolveJsonModule": true
}
```

Example

```json
{
  "name": "Asif"
}
```

```ts
import user from "./user.json";
```

Without Option

```
Error
```

---

# 18. isolatedModules

প্রতিটি file independently compile হবে।

```json
{
  "isolatedModules": true
}
```

Useful For

- Vite
- Next.js
- Babel
- SWC

---

# 19. esModuleInterop

CommonJS package সহজে import করতে সাহায্য করে।

```json
{
  "esModuleInterop": true
}
```

Without

```ts
import express from "express";
```

অনেক সময় Error হতে পারে।

With

```ts
import express from "express";
```

ঠিকভাবে কাজ করবে।

---

# 20. forceConsistentCasingInFileNames

Windows/Linux filename case mismatch detect করবে।

```json
{
  "forceConsistentCasingInFileNames": true
}
```

---

# 21. skipLibCheck

`node_modules` type checking skip করবে।

```json
{
  "skipLibCheck": true
}
```

Compilation faster হয়।

---

# 22. noUnusedLocals

Unused variable detect করবে।

```json
{
  "noUnusedLocals": true
}
```

---

# 23. noUnusedParameters

Unused parameter detect করবে।

```json
{
  "noUnusedParameters": true
}
```

---

# 24. noEmit

Type check করবে কিন্তু JavaScript generate করবে না।

```json
{
  "noEmit": true
}
```

Vite / Next.js-এ অনেক সময় ব্যবহার করা হয়।

---

# 25. allowJs

JavaScript file-ও compile করবে।

```json
{
  "allowJs": true
}
```

---

# 26. checkJs

JavaScript file-এও type checking করবে।

```json
{
  "checkJs": true
}
```

---

# ✅ Real Backend `tsconfig.json`

```json
{
  "compilerOptions": {
    "target": "ES2022",
    "module": "NodeNext",
    "moduleResolution": "NodeNext",

    "rootDir": "./src",
    "outDir": "./dist",

    "strict": true,
    "noImplicitAny": true,
    "strictNullChecks": true,

    "esModuleInterop": true,
    "resolveJsonModule": true,

    "sourceMap": true,
    "skipLibCheck": true,
    "forceConsistentCasingInFileNames": true,

    "baseUrl": "./src",
    "paths": {
      "@/*": ["*"]
    }
  },

  "include": ["src"],
  "exclude": ["node_modules", "dist"]
}
```

---

# 🎯 Interview Questions

1. `target` এবং `module`-এর মধ্যে পার্থক্য কী?
2. `rootDir` ও `outDir` কী কাজে লাগে?
3. `strict` enable করলে কী কী rule চালু হয়?
4. `baseUrl` এবং `paths` কেন ব্যবহার করা হয়?
5. `moduleResolution` কী? `NodeNext` এবং `Bundler`-এর পার্থক্য কী?
6. `declaration` file কী? কখন ব্যবহার করা হয়?
7. `sourceMap` debugging-এ কীভাবে সাহায্য করে?
8. `esModuleInterop` কেন দরকার?
9. `resolveJsonModule` কী সমস্যা সমাধান করে?
10. `include` এবং `exclude`-এর মধ্যে পার্থক্য কী?

---

# ⭐ মনে রাখার শর্টকাট

| Option | Purpose |
|---------|---------|
| `target` | কোন JS version-এ compile হবে |
| `module` | Module system |
| `lib` | Built-in JavaScript APIs |
| `rootDir` | Source folder |
| `outDir` | Output folder |
| `strict` | সব strict checking |
| `noImplicitAny` | Implicit any বন্ধ |
| `strictNullChecks` | null/undefined check |
| `declaration` | `.d.ts` generate |
| `removeComments` | Comment remove |
| `sourceMap` | Debugging |
| `baseUrl` | Import shortcut |
| `paths` | Alias |
| `include` | কোন file compile হবে |
| `exclude` | কোন file compile হবে না |
| `moduleResolution` | Import resolve |
| `resolveJsonModule` | JSON import |
| `isolatedModules` | Per-file compilation |
| `esModuleInterop` | CommonJS compatibility |
| `skipLibCheck` | Library type check skip |
| `forceConsistentCasingInFileNames` | Filename case check |
| `noUnusedLocals` | Unused variable detect |
| `noUnusedParameters` | Unused parameter detect |
| `allowJs` | JavaScript compile |
| `checkJs` | JavaScript type check |
| `noEmit` | JS output generate করবে না |