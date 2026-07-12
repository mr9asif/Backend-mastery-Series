# 📦 Chapter 03 — package.json Deep Dive

> **Level:** Beginner → Professional Backend Developer

---

# 🎯 Learning Objectives

এই Chapter শেষ করার পর তুমি জানতে পারবে—

- `package.json` কী?
- কেন লাগে?
- কীভাবে কাজ করে?
- প্রতিটি গুরুত্বপূর্ণ Field-এর কাজ
- Real Project-এ কীভাবে ব্যবহার করা হয়
- Best Practices
- Common Mistakes

---

# 🤔 package.json কী?

`package.json` হলো একটি **Configuration File** যা একটি Node.js Project-এর পরিচয় (Identity) এবং Configuration ধারণ করে।

এটা Project-এর **Brain** বা **Blueprint** বলা যায়।

npm, Node.js এবং অন্যান্য Tool এই File পড়েই Project সম্পর্কে তথ্য জানতে পারে।

---

# 🧠 সহজভাবে বুঝো

ধরো তুমি একটা নতুন কোম্পানি খুললে।

তোমার কোম্পানির একটা পরিচয় থাকবে—

- কোম্পানির নাম
- Version
- Owner
- কী কাজ করে
- কী কী Software ব্যবহার করে

ঠিক তেমনি একটা Node.js Project-এর পরিচয় থাকে `package.json`-এ।

---

# 📂 Example

```json
{
  "name": "gearup-backend",
  "version": "1.0.0",
  "type": "module",
  "scripts": {
    "dev": "tsx watch src/server.ts"
  }
}
```

---

# কেন package.json দরকার?

এটা ছাড়া npm জানবে না—

- Project-এর নাম কী?
- কোন Packages লাগবে?
- কোন Scripts চালাতে হবে?
- Project কোন Module System ব্যবহার করছে?
- Project Publish করা যাবে কিনা?

অর্থাৎ npm-এর জন্য `package.json` অত্যন্ত গুরুত্বপূর্ণ।

---

# package.json কীভাবে তৈরি হয়?

```bash
npm init
```

অথবা

```bash
npm init -y
```

---

# package.json Structure

একটি সাধারণ package.json দেখতে এমন হতে পারে—

```json
{
  "name": "gearup-backend",
  "version": "1.0.0",
  "description": "",
  "type": "module",
  "scripts": {},
  "dependencies": {},
  "devDependencies": {}
}
```

---

# গুরুত্বপূর্ণ Fields

## 1. name

Project-এর নাম।

```json
{
  "name": "gearup-backend"
}
```

✔ Unique হওয়া ভালো।

---

## 2. version

Project-এর বর্তমান Version।

```json
{
  "version": "1.0.0"
}
```

Format

```
Major.Minor.Patch

1.0.0
```

Example

- 1.0.0 → প্রথম Stable Release
- 1.1.0 → নতুন Feature
- 1.1.1 → Bug Fix

---

## 3. description

Project সম্পর্কে ছোট Description।

```json
{
  "description": "Sports Rental Backend API"
}
```

---

## 4. type

Project কোন Module System ব্যবহার করবে।

```json
{
  "type": "module"
}
```

এর ফলে

```js
import express from "express";
```

ব্যবহার করতে পারবে।

যদি না দাও

Node.js Default CommonJS ব্যবহার করবে।

---

## 5. scripts ⭐

সবচেয়ে গুরুত্বপূর্ণ Section।

```json
{
  "scripts": {
    "dev": "tsx watch src/server.ts",
    "build": "tsc",
    "start": "node dist/server.js"
  }
}
```

Run করতে

```bash
npm run dev

npm run build

npm run start
```

Scripts-এর উদ্দেশ্য হলো Long Command ছোট করে ব্যবহার করা।

---

## 6. dependencies ⭐

Production-এ যেসব Package লাগবে।

Example

```json
{
  "dependencies": {
    "express": "^5.1.0",
    "zod": "^4.0.0",
    "jsonwebtoken": "^9.0.2"
  }
}
```

Install

```bash
npm install express
```

Automatically এখানে যোগ হবে।

---

## 7. devDependencies ⭐

Development-এর সময় যেসব Package লাগে।

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

---

## 8. private

```json
{
  "private": true
}
```

এটা দিলে Project npm Registry-তে ভুল করে Publish হবে না।

Backend Project-এ সাধারণত এটা `true` রাখা হয়।

---

## 9. engines

কোন Node Version লাগবে।

```json
{
  "engines": {
    "node": ">=22"
  }
}
```

Team Project-এর জন্য খুবই Useful।

---

## 10. packageManager

Project কোন Package Manager ব্যবহার করছে।

```json
{
  "packageManager": "npm@11.4.2"
}
```

এতে Team-এর সবাই একই Package Manager Version ব্যবহার করতে পারে।

---

# package.json কীভাবে কাজ করে?

যখন তুমি চালাও—

```bash
npm install
```

npm প্রথমে `package.json` পড়ে।

তারপর—

- Dependencies দেখে
- Packages Download করে
- node_modules তৈরি করে
- package-lock.json Update করে

---

# Real Project Example

ধরো তোমার GearUp Project।

```json
{
  "name": "gearup-backend",

  "type": "module",

  "scripts": {
    "dev": "tsx watch src/server.ts",
    "build": "tsc",
    "start": "node dist/server.js"
  },

  "dependencies": {
    "express": "^5.1.0",
    "@prisma/client": "^6.0.0",
    "jsonwebtoken": "^9.0.2"
  },

  "devDependencies": {
    "typescript": "^5.9.2",
    "tsx": "^4.20.3",
    "prisma": "^6.0.0"
  }
}
```

---

# Best Practices ✅

- Project শুরুতেই `npm init -y` করো।
- Backend Project-এ `"private": true` রাখো।
- Development Tools `devDependencies`-এ রাখো।
- Runtime Packages `dependencies`-এ রাখো।
- Scripts-এর নাম Standard রাখো (`dev`, `build`, `start`, `test`)।
- `package.json` Git-এ Commit করো।

---

# Common Mistakes ❌

❌ TypeScript `dependencies`-এ রাখা।

❌ `package.json` Manual Edit করে Syntax Error করা।

❌ Script-এর নাম এলোমেলো রাখা।

❌ Project-এর Name বারবার পরিবর্তন করা।

---

# 🔥 Senior Tips

### 1.

সব Backend Project-এ

```json
{
  "private": true
}
```

রাখার অভ্যাস করো।

---

### 2.

সব Team Project-এ

```json
{
  "engines": {
    "node": ">=22"
  }
}
```

ব্যবহার করো।

---

### 3.

Scripts Standard রাখো।

```text
dev
build
start
test
lint
format
```

---

# Interview Questions

### package.json কী?

---

### dependencies আর devDependencies-এর পার্থক্য কী?

---

### type: module কেন ব্যবহার করি?

---

### npm install কীভাবে package.json ব্যবহার করে?

---

### scripts-এর উদ্দেশ্য কী?

---

# Quick Revision

| Field | কাজ |
|--------|------|
| name | Project-এর নাম |
| version | Project Version |
| description | Project Description |
| type | Module System |
| scripts | Commands |
| dependencies | Runtime Packages |
| devDependencies | Development Packages |
| private | Publish বন্ধ করে |
| engines | Required Node Version |
| packageManager | কোন Package Manager ব্যবহার হবে |

---

# Summary

- `package.json` হলো একটি Node.js Project-এর Configuration File।
- npm এবং Node.js দুটোই এই File ব্যবহার করে।
- Project-এর Identity, Scripts এবং Dependencies এখানে থাকে।
- Backend Project-এর সবচেয়ে গুরুত্বপূর্ণ File-গুলোর একটি হলো `package.json`।
- একজন Backend Developer-এর `package.json` ভালোভাবে বোঝা বাধ্যতামূলক।
```