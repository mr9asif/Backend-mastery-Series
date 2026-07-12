# 🔐 Chapter 13 — npm Security

> **Level:** Beginner → Professional Backend Developer

---

# 🎯 Learning Objectives

এই Chapter শেষ করার পর তুমি জানতে পারবে—

- npm Security কেন গুরুত্বপূর্ণ
- Package Install করার আগে কী Check করবে
- Security Commands

---

# কেন Security গুরুত্বপূর্ণ?

তুমি যে Package Install করছো, সেটি Third-party Code।

অর্থাৎ সেই Code তোমার Project-এ Run হবে।

তাই সব Package Trusted হওয়া উচিত।

---

# Package Install করার আগে কী দেখবে?

- GitHub Repository
- Weekly Downloads
- Last Update
- Documentation
- Community Support

---

# Security Commands

Check Vulnerability

```bash
npm audit
```

Auto Fix

```bash
npm audit fix
```

---

# Best Practices ✅

- সবসময় Trusted Package ব্যবহার করো।
- অপ্রয়োজনীয় Package Install করো না।
- সময়ে সময়ে `npm audit` চালাও।
- Package নিয়মিত Update রাখো।

---

# Common Mistakes ❌

❌ Random Package Install করা।

❌ Warning Ignore করা।

❌ Unmaintained Package ব্যবহার করা।

---

# Summary

- npm Package Install করার আগে Package Verify করো।
- `npm audit` Security Check-এর জন্য ব্যবহার করো।
- Trusted এবং Active Package ব্যবহার করো।