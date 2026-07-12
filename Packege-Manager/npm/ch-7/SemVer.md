# 🏷️ Chapter 07 — Semantic Versioning (SemVer)

> **Level:** Beginner → Professional Backend Developer

---

# 🎯 Learning Objectives

এই Chapter শেষ করার পর তুমি জানতে পারবে—

- Semantic Versioning (SemVer) কী?
- Version Number কী বোঝায়?
- `^`, `~`, `*` এর ব্যবহার
- Best Practices

---

# 🤔 Semantic Versioning (SemVer) কী?

**Semantic Versioning (SemVer)** হলো Software-এর Version Number দেওয়ার একটি Standard Rule।

Example

```text
1.4.2
```

এটি তিনটি অংশ নিয়ে গঠিত।

```text
MAJOR.MINOR.PATCH
```

---

# Version Breakdown

## 1️⃣ MAJOR

```text
2.0.0
```

Breaking Change হলে MAJOR Version বাড়ে।

অর্থাৎ পুরোনো Code নতুন Version-এর সাথে কাজ নাও করতে পারে।

---

## 2️⃣ MINOR

```text
1.5.0
```

নতুন Feature যোগ হলে MINOR Version বাড়ে।

পুরোনো Code সাধারণত ঠিকই কাজ করে।

---

## 3️⃣ PATCH

```text
1.5.3
```

Bug Fix বা ছোট পরিবর্তনের জন্য PATCH Version বাড়ে।

---

# package.json Example

```json
{
  "dependencies": {
    "express": "^5.1.0"
  }
}
```

এখানে `^` খুব গুরুত্বপূর্ণ।

---

# Version Symbols

## `^` (Caret)

```json
{
  "express": "^5.1.0"
}
```

মানে

```text
>=5.1.0 <6.0.0
```

Major Version Change হবে না।

👉 সবচেয়ে বেশি ব্যবহৃত।

---

## `~` (Tilde)

```json
{
  "express": "~5.1.0"
}
```

মানে

```text
>=5.1.0 <5.2.0
```

শুধু Patch Update হবে।

---

## Exact Version

```json
{
  "express": "5.1.0"
}
```

শুধুমাত্র এই Version Install হবে।

---

## `*`

```json
{
  "express": "*"
}
```

যে কোনো Version Install হতে পারে।

❌ Production-এ Recommended নয়।

---

# কোনটা বেশি ব্যবহার হয়?

| Symbol | Usage |
|---------|--------|
| `^` | ✅ Most Common |
| `~` | মাঝে মাঝে |
| Exact Version | গুরুত্বপূর্ণ Package |
| `*` | ❌ Avoid |

---

# Best Practices ✅

- সাধারণ Project-এ `^` ব্যবহার করো।
- Production-এ `*` ব্যবহার করো না।
- Team Project-এ `package-lock.json` Commit করো।

---

# Common Mistakes ❌

❌ `*` ব্যবহার করা।

❌ SemVer না বুঝে Package Update করা।

---

# Quick Revision

| Part | Meaning |
|------|----------|
| Major | Breaking Change |
| Minor | New Feature |
| Patch | Bug Fix |

---

# Summary

- SemVer = Version Number-এর Standard।
- Format = `MAJOR.MINOR.PATCH`
- `^` = Most Common
- `~` = Patch Update
- `*` = Avoid in Production