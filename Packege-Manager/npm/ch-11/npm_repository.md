# 🌐 Chapter 11 — npm Registry

> **Level:** Beginner → Professional Backend Developer

---

# 🎯 Learning Objectives

এই Chapter শেষ করার পর তুমি জানতে পারবে—

- npm Registry কী?
- কীভাবে কাজ করে?
- Package কোথা থেকে আসে?
- Registry Publish কী?

---

# 🤔 npm Registry কী?

**npm Registry** হলো একটি Online Database যেখানে লক্ষ লক্ষ JavaScript Package সংরক্ষণ করা থাকে।

সহজভাবে,

> **npm Registry = JavaScript Package Store**

---

# কীভাবে কাজ করে?

যখন চালাও

```bash
npm install express
```

Flow

```text
Your Project
      │
      ▼
npm CLI
      │
      ▼
npm Registry
      │
      ▼
Download Package
      │
      ▼
node_modules
```

---

# Registry-তে কী থাকে?

- Express
- React
- Prisma
- Zod
- TypeScript
- NestJS

এবং আরও লক্ষ লক্ষ Package।

---

# Registry URL

Official Registry

```text
https://registry.npmjs.org/
```

---

# Publish কী?

যদি তুমি নিজের Library তৈরি করো,

তাহলে

```bash
npm publish
```

দিয়ে npm Registry-তে Upload করতে পারবে।

তারপর অন্য Developer

```bash
npm install your-package-name
```

দিয়ে ব্যবহার করতে পারবে।

---

# Best Practices ✅

- সবসময় Trusted Package Install করো।
- Package Install করার আগে Weekly Downloads ও Maintenance দেখে নাও।
- Official npm Registry ব্যবহার করো।

---

# Common Mistakes ❌

❌ Unknown Package Install করা।

❌ Package Name ভালোভাবে Check না করে Install করা।

---

# 🔥 Senior Tips

- বড় Company-গুলো অনেক সময় নিজেদের **Private Registry** ব্যবহার করে।
- Package Install করার আগে Security ও Maintenance Check করা ভালো অভ্যাস।

---

# Summary

- npm Registry হলো Online Package Store।
- `npm install` Registry থেকে Package Download করে।
- `npm publish` দিয়ে নিজের Package Publish করা যায়।
- Official Registry হলো `https://registry.npmjs.org/`।