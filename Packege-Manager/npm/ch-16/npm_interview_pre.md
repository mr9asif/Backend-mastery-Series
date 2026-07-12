# 🎯 Chapter 16 — Interview Preparation

> **Level:** Beginner → Professional Backend Developer

---

# 📚 Beginner Level Questions

## 1. npm কী?

👉 npm হলো Node.js-এর Default Package Manager।

---

## 2. Node.js আর npm কি একই জিনিস?

❌ না।

- Node.js → Runtime
- npm → Package Manager

---

## 3. Package কী?

Reusable Library বা Software যেটা Project-এ ব্যবহার করা যায়।

Example:

- Express
- Prisma
- React

---

## 4. Module কী?

Reusable JavaScript/TypeScript File বা Code-এর অংশ।

---

## 5. package.json কী?

Project-এর Configuration File।

---

## 6. package-lock.json কী?

Exact Dependency Version Store করে।

---

## 7. node_modules কী?

সব Installed Package-এর Folder।

---

## 8. dependencies আর devDependencies-এর পার্থক্য কী?

| dependencies | devDependencies |
|--------------|-----------------|
| Production-এ লাগে | শুধু Development-এ লাগে |

---

## 9. npm install কী করে?

- package.json পড়ে
- Package Download করে
- node_modules তৈরি করে
- package-lock.json Update করে

---

## 10. npm install আর npm install package-name এর পার্থক্য কী?

```bash
npm install
```

➡ package.json-এর সব Dependency Install করে।

```bash
npm install express
```

➡ শুধু Express Install করে।

---

# 📚 Intermediate Level Questions

## 1. npm Registry কী?

JavaScript Package-এর Online Store।

---

## 2. Local Package আর Global Package-এর পার্থক্য কী?

Local

```bash
npm install express
```

Global

```bash
npm install -g typescript
```

---

## 3. npm এবং npx-এর পার্থক্য কী?

| npm | npx |
|------|------|
| Package Install করে | Package Execute করে |

---

## 4. SemVer কী?

Software Versioning Standard।

```text
MAJOR.MINOR.PATCH
```

---

## 5. package-lock.json Git-এ Commit করা উচিত?

✅ অবশ্যই।

---

## 6. node_modules GitHub-এ Push করা উচিত?

❌ না।

---

## 7. npm cache কী?

Downloaded Package-এর Local Cache।

---

## 8. npm Scripts কী?

package.json-এর Shortcut Commands।

---

# 📚 Senior Level Questions

## 1. npm install কীভাবে কাজ করে?

High Level Flow

```text
Read package.json
        │
        ▼
Resolve Dependencies
        │
        ▼
Check package-lock.json
        │
        ▼
Download Packages
        │
        ▼
Create node_modules
```

---

## 2. package.json আর package-lock.json একসাথে কেন দরকার?

- package.json → কোন Package লাগবে
- package-lock.json → কোন Exact Version লাগবে

---

## 3. dependencies-এ TypeScript রাখবে?

❌ না।

কারণ TypeScript Production-এ Run হয় না।

এটি Development Tool।

---

## 4. কেন package-lock.json Commit করা হয়?

Team-এর সবাই একই Dependency Version ব্যবহার করার জন্য।

---

## 5. npm audit কেন ব্যবহার করা হয়?

Project-এর Security Vulnerability Check করার জন্য।

---

# 💡 Interview Tips

✅ শুধু Definition মুখস্থ করো না।

বোঝার চেষ্টা করো—

- Why?
- How?
- When?

---

উদাহরণ

Interviewer

> package.json কী?

খারাপ Answer

> এটা Configuration File.

ভালো Answer

> package.json হলো Node.js Project-এর Configuration File যেখানে Project Information, Dependencies, Scripts এবং Metadata থাকে। npm এবং Node.js Project Manage করার জন্য এই File ব্যবহার করে।

---

# 🚀 Quick Revision

- Node.js = Runtime
- npm = Package Manager
- Package = Library
- Module = Reusable Code
- package.json = Project Configuration
- package-lock.json = Dependency Lock
- node_modules = Installed Packages
- npx = Execute Package
- npm Registry = Online Package Store

---

# 🎯 Final Interview Advice

Interview-এর আগে অবশ্যই Practice করো—

- npm Commands
- package.json
- package-lock.json
- node_modules
- Dependencies
- npm Scripts

কারণ এগুলো Backend Interview-তে খুবই Common।