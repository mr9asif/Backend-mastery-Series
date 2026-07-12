# ⚡ Chapter 12 — npx

> **Level:** Beginner → Professional Backend Developer

---

# 🎯 Learning Objectives

এই Chapter শেষ করার পর তুমি জানতে পারবে—

- npx কী?
- npm আর npx-এর পার্থক্য
- কখন npx ব্যবহার করবে

---

# 🤔 npx কী?

**npx (Node Package Execute)** হলো npm-এর একটি Tool, যা Package Install না করেও Run করতে পারে।

সহজভাবে,

> **npm = Package Install করে**
>
> **npx = Package Execute করে**

---

# Example

Create React App

```bash
npx create-react-app my-app
```

Prisma Initialize

```bash
npx prisma init
```

TypeScript Compiler

```bash
npx tsc --init
```

---

# npm vs npx

| npm | npx |
|------|------|
| Package Install করে | Package Run করে |
| Package Save করতে পারে | সাধারণত Save করে না |
| বারবার ব্যবহার হওয়া Package | একবার Run করার জন্য ভালো |

---

# কখন npx ব্যবহার করবে?

✅ CLI Tool Run করার সময়

যেমন

- Prisma
- TypeScript
- Create React App
- Vite

---

# Best Practices ✅

- একবার ব্যবহার হবে এমন Tool-এর জন্য `npx` ব্যবহার করো।
- Global Install কম করার চেষ্টা করো।

---

# Summary

- `npm` = Install
- `npx` = Execute
- CLI Tool চালানোর জন্য `npx` খুবই Useful।