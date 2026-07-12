# 🚀 Chapter 09 — npm Cache

> **Level:** Beginner → Professional Backend Developer

---

# 🎯 Learning Objectives

এই Chapter শেষ করার পর তুমি জানতে পারবে—

- npm Cache কী?
- কেন ব্যবহার করা হয়?
- Cache-এর সুবিধা
- Common Commands

---

# 🤔 npm Cache কী?

**npm Cache** হলো npm-এর একটি Local Storage যেখানে Download করা Packages সাময়িকভাবে সংরক্ষণ করা হয়।

এর ফলে একই Package বারবার Internet থেকে Download করতে হয় না।

---

# কেন Cache ব্যবহার করা হয়?

ধরো তুমি

```bash
npm install express
```

চালালে।

প্রথমবার

```
Internet
    │
    ▼
Download
    │
    ▼
Cache
    │
    ▼
Project
```

পরবর্তীতে একই Version লাগলে npm Cache থেকেও ব্যবহার করতে পারে।

এতে Install দ্রুত হয়।

---

# Useful Commands

Cache Check

```bash
npm cache verify
```

Cache Clean

```bash
npm cache clean --force
```

---

# কখন ব্যবহার করবে?

- Package Install-এ সমস্যা হলে
- Corrupted Cache হলে
- Debug করার সময়

---

# Best Practices ✅

- সাধারণত Cache নিয়ে কিছু করতে হয় না।
- Problem না হলে Cache Delete করার দরকার নেই।

---

# Common Mistakes ❌

❌ অকারণে বারবার Cache Clean করা।

---

# Summary

- npm Cache Download করা Package সংরক্ষণ করে।
- Install Speed বাড়ায়।
- Problem হলে `npm cache verify` বা `npm cache clean --force` ব্যবহার করা যায়।