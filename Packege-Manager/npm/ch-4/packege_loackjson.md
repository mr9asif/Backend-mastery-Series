# 🔒 Chapter 04 — package-lock.json Deep Dive

> **Level:** Beginner → Professional Backend Developer

---

# 🎯 Learning Objectives

এই Chapter শেষ করার পর তুমি জানতে পারবে—

- `package-lock.json` কী?
- কেন এটি দরকার?
- npm কীভাবে এটি ব্যবহার করে?
- কেন Git-এ Commit করতে হয়?
- Delete করলে কী হয়?
- Best Practices এবং Common Mistakes

---

# 🤔 package-lock.json কী?

`package-lock.json` হলো npm-এর **Lock File**।

এটি Project-এর সমস্ত Installed Package-এর **Exact Version** এবং Dependency Tree সংরক্ষণ করে।

সহজভাবে বললে,

> **package.json বলে "কি লাগবে", আর package-lock.json বলে "ঠিক কোন Version লাগবে"।**

---

# 🧠 সহজভাবে বুঝো

ধরো তুমি একটি Cake-এর Recipe লিখলে।

Recipe-তে লেখা আছে—

- Flour
- Sugar
- Butter

কিন্তু কোন Brand?

কোন Quantity?

কোন Quality?

এসব লেখা নেই।

এখন তুমি যদি সব Detail লিখে রাখো—

- Flour → Fresh Brand
- Sugar → XYZ Brand
- Butter → ABC Brand

তাহলে পরের বারও একই Cake হবে।

`package-lock.json` ঠিক এই কাজটাই করে।

---

# package.json vs package-lock.json

| package.json | package-lock.json |
|--------------|-------------------|
| কোন Package লাগবে | কোন Exact Version লাগবে |
| Developer Edit করতে পারে | npm Automatically Generate করে |
| Human Friendly | npm Friendly |
| Project Configuration | Dependency Lock |

---

# Example

## package.json

```json
{
  "dependencies": {
    "express": "^5.1.0"
  }
}
```

এখানে `^` মানে 5.x.x Version Install হতে পারে।

---

## package-lock.json

```json
{
  "packages": {
    "node_modules/express": {
      "version": "5.1.0"
    }
  }
}
```

এখানে Exact Version Store হয়।

---

# package-lock.json কীভাবে তৈরি হয়?

যখন প্রথমবার চালাও—

```bash
npm install
```

npm

- Package Download করে
- `node_modules` তৈরি করে
- `package-lock.json` Generate করে

---

# package-lock.json কেন দরকার?

ধরো Team-এ ৫ জন Developer কাজ করছে।

আজ তুমি Install করলে

```text
express 5.1.0
```

এক মাস পরে নতুন Version Release হলো

```text
express 5.2.0
```

যদি Lock File না থাকে,

তাহলে একজনের Computer-এ 5.1.0

আরেকজনের Computer-এ 5.2.0

Install হতে পারে।

ফলে

- Bug
- Different Behaviour
- Deployment Problem

হতে পারে।

Lock File এই Problem Solve করে।

---

# npm কীভাবে ব্যবহার করে?

যখন চালাও

```bash
npm install
```

Flow

```text
Read package.json
        │
        ▼
Read package-lock.json
        │
        ▼
Install Exact Versions
        │
        ▼
Create node_modules
```

---

# package-lock.json-এর ভিতরে কী থাকে?

- Package Name
- Exact Version
- Dependencies
- Integrity Hash
- Resolved URL

Developer সাধারণত এগুলো Edit করে না।

---

# Delete করলে কী হবে?

Delete করলে কোনো সমস্যা হবে না।

আবার

```bash
npm install
```

চালালে নতুন করে Generate হবে।

তবে Team Project-এ Delete করা উচিত নয়।

---

# Git-এ Commit করবো?

✅ অবশ্যই।

কারণ Team-এর সবাই যেন একই Version ব্যবহার করে।

এটি Production-এর জন্যও খুব গুরুত্বপূর্ণ।

---

# Real Project Example

তোমার Project

```text
gearup-backend/

package.json

package-lock.json

node_modules/
```

GitHub-এ Push করবে

✅ `package.json`

✅ `package-lock.json`

❌ `node_modules`

---

# Best Practices ✅

- সব সময় `package-lock.json` Git-এ Commit করো।
- Manual Edit করো না।
- Delete না করাই ভালো।
- Team Project-এ সব সময় Lock File রাখো।

---

# Common Mistakes ❌

❌ `package-lock.json` Git Ignore করা।

❌ Manual Edit করা।

❌ Conflict হলে পুরো File Delete করে দেওয়া।

❌ Lock File ছাড়া Team Project চালানো।

---

# 🔥 Senior Tips

### 1.

`package-lock.json` সব সময় Version Control-এ রাখো।

---

### 2.

Production Deployment-এ Exact Dependency Version থাকা খুব গুরুত্বপূর্ণ।

---

### 3.

Lock File-এর কারণে Development, Testing এবং Production Environment একই Package Version ব্যবহার করে।

---

# Interview Questions

### package-lock.json কী?

---

### package.json আর package-lock.json-এর পার্থক্য কী?

---

### কেন Git-এ Commit করতে হয়?

---

### Delete করলে কী হবে?

---

### npm install কীভাবে package-lock.json ব্যবহার করে?

---

# Quick Revision

| Topic | Description |
|--------|-------------|
| package-lock.json | Dependency Lock File |
| Created By | npm |
| Edited By | সাধারণত npm |
| Purpose | Exact Package Version Store করা |
| Git Commit | ✅ Yes |
| Delete করা যাবে? | ✅ যাবে, কিন্তু Recommended নয় |

---

# Summary

- `package-lock.json` হলো npm-এর Lock File।
- এটি Exact Package Version Store করে।
- Team-এর সবাই একই Dependency ব্যবহার করতে পারে।
- npm Automatically এটি Generate এবং Update করে।
- Backend Project-এ `package-lock.json` Git-এ Commit করা Best Practice।
```