# 📦 Chapter 06 — Dependency Management

> **Level:** Beginner → Professional Backend Developer

---

# 🎯 Learning Objectives

এই Chapter শেষ করার পর তুমি জানতে পারবে—

- Dependency কী?
- Dependency-এর বিভিন্ন ধরন
- কখন কোনটা ব্যবহার করতে হয়
- Best Practices

---

# 🤔 Dependency কী?

**Dependency** হলো এমন একটি Package, যার উপর তোমার Project নির্ভর (Depend) করে।

সহজভাবে,

> **তোমার Project ঠিকভাবে চলার জন্য যে Package গুলো দরকার, সেগুলোই Dependency।**

উদাহরণ

```bash
npm install express
```

এখানে `express` হলো তোমার Project-এর একটি Dependency।

---

# Dependency-এর ধরন

## 1️⃣ dependencies

Project Run করার জন্য যেসব Package লাগে।

Example

```json
{
  "dependencies": {
    "express": "^5.1.0",
    "zod": "^4.0.0",
    "@prisma/client": "^6.0.0"
  }
}
```

Install

```bash
npm install express
```

### কখন ব্যবহার করবে?

যেসব Package Production-এ লাগবে।

যেমন

- Express
- Prisma Client
- JWT
- bcrypt
- Zod

---

## 2️⃣ devDependencies

Development-এর সময় লাগে, কিন্তু Production-এ লাগে না।

Example

```json
{
  "devDependencies": {
    "typescript": "^5.9.2",
    "tsx": "^4.20.3",
    "eslint": "^9.0.0"
  }
}
```

Install

```bash
npm install -D typescript
```

### কখন ব্যবহার করবে?

Development Tools-এর জন্য।

যেমন

- TypeScript
- ESLint
- Prettier
- Prisma CLI
- Nodemon

---

## 3️⃣ peerDependencies

অন্য Package-এর সাথে Compatible Version নিশ্চিত করার জন্য।

এটি সাধারণ Project-এ খুব বেশি ব্যবহার করতে হয় না।

মূলত Library Developer-রা ব্যবহার করে।

Example

```json
{
  "peerDependencies": {
    "react": "^19.0.0"
  }
}
```

---

## 4️⃣ optionalDependencies

Optional Package।

Install না হলেও Project চলবে।

ব্যবহার খুব কম।

---

# Dependency Flow

```text
package.json
      │
      ▼
Dependencies
      │
      ▼
npm install
      │
      ▼
node_modules
```

---

# Real Project Example

### dependencies

```text
Express
Prisma Client
Zod
bcrypt
JWT
Cookie Parser
```

### devDependencies

```text
TypeScript
TSX
ESLint
Prettier
Prisma CLI
```

---

# Best Practices ✅

- Runtime Package → `dependencies`
- Development Tool → `devDependencies`
- `peerDependencies` সাধারণ Project-এ খুব কম লাগে।
- Package Install করার সময় চিন্তা করো এটা Production-এ লাগবে নাকি শুধু Development-এ।

---

# Common Mistakes ❌

❌ `typescript` কে `dependencies`-এ রাখা।

❌ `express` কে `devDependencies`-এ রাখা।

❌ সব Package একই Category-তে রাখা।

---

# 🔥 Senior Tips

### Backend Project-এ সাধারণত

**dependencies**

- express
- zod
- bcrypt
- jsonwebtoken
- @prisma/client

**devDependencies**

- typescript
- tsx
- prisma
- eslint
- prettier

এটাই Industry Standard।

---

# Quick Revision

| Type | কখন ব্যবহার হবে? |
|------|------------------|
| dependencies | Production-এ লাগবে |
| devDependencies | Development-এর সময় লাগবে |
| peerDependencies | Library Compatibility |
| optionalDependencies | Optional Package |

---

# Summary

- **Dependency** = Project চালানোর জন্য প্রয়োজনীয় Package।
- **dependencies** = Runtime Packages।
- **devDependencies** = Development Tools।
- **peerDependencies** = Library Compatibility।
- **optionalDependencies** = Optional Packages।
- Backend Developer হিসেবে সবচেয়ে বেশি ব্যবহার করবে **dependencies** এবং **devDependencies**।
```