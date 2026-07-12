# ⚙️ Chapter 10 — npm Configuration (.npmrc)

> **Level:** Beginner → Professional Backend Developer

---

# 🎯 Learning Objectives

এই Chapter শেষ করার পর তুমি জানতে পারবে—

- `.npmrc` কী?
- কেন ব্যবহার করা হয়?
- কোথায় থাকে?
- Common Configuration

---

# 🤔 .npmrc কী?

`.npmrc` হলো npm-এর **Configuration File**।

npm কীভাবে কাজ করবে, কোন Registry ব্যবহার করবে, Authentication Token কী হবে—এসব Configuration এখানে রাখা হয়।

---

# কোথায় থাকে?

এটি বিভিন্ন জায়গায় থাকতে পারে।

- User Level
- Project Level
- Global Level

Project-এর ভিতরে থাকলে শুধু সেই Project-এর জন্য কাজ করবে।

---

# Example

```text
project/

├── .npmrc
├── package.json
└── src/
```

---

# Example Configuration

Registry Change

```text
registry=https://registry.npmjs.org/
```

Save Exact Version

```text
save-exact=true
```

Authentication Token

```text
//registry.npmjs.org/:_authToken=YOUR_TOKEN
```

---

# কখন ব্যবহার করবে?

- Private Registry ব্যবহার করলে
- npm Login Token Store করতে
- Team Configuration Share করতে

---

# Best Practices ✅

- Secret Token GitHub-এ Push করো না।
- Project Specific Configuration Project-এর `.npmrc`-এ রাখো।

---

# Common Mistakes ❌

❌ `.npmrc`-এ Token রেখে Public GitHub-এ Push করা।

---

# Summary

- `.npmrc` হলো npm-এর Configuration File।
- Registry, Token এবং বিভিন্ন npm Settings এখানে থাকে।
- Sensitive Information GitHub-এ Push করা উচিত নয়।