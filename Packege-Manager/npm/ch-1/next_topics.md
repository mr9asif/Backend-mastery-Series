# 📦 NPM Overview

> **Goal:** এই Note-এর উদ্দেশ্য হলো npm-এর গুরুত্বপূর্ণ Concept গুলোর একটি **Bird's Eye View** দেওয়া। এখানে শুধু Overview থাকবে। প্রতিটি Topic পরে আলাদাভাবে Deep Dive করা হবে।

---

# 1️⃣ What is a Package Manager?

**Package Manager** হলো এমন একটি Tool, যার কাজ হলো Project-এর **Package (Library)** install, update, remove এবং manage করা।

### Popular Package Managers

- npm
- Yarn
- pnpm
- Bun

**Example**

```bash
npm install express
```

---

# 2️⃣ npm Registry

**npm Registry** হলো একটি Online Database যেখানে লক্ষ লক্ষ JavaScript Package সংরক্ষিত থাকে।

যখন তুমি লিখো—

```bash
npm install express
```

npm Registry থেকে Express Package Download হয়।

> 🌐 ভাবতে পারো এটি JavaScript Package-এর একটি "App Store"।

---

# 3️⃣ Local vs Global Packages

### Local Package

শুধু বর্তমান Project-এ ব্যবহার হয়।

```bash
npm install express
```

### Global Package

পুরো Computer থেকে ব্যবহার করা যায়।

```bash
npm install -g typescript
```

---

# 4️⃣ npm Architecture

npm মূলত ৩টি অংশ নিয়ে কাজ করে।

```text
npm CLI
     │
     ▼
npm Registry
     │
     ▼
Your Project
```

- **npm CLI** → Command চালায়
- **Registry** → Package Store
- **Project** → Package ব্যবহার করে

---

# 5️⃣ npm Installation

Node.js Install করলে npm সাধারণত Automatic Install হয়ে যায়।

Version Check

```bash
node -v

npm -v
```

Update

```bash
npm install -g npm
```

---

# 6️⃣ How npm Works Internally (Overview)

যখন তুমি

```bash
npm install express
```

চালাও,

npm—

- Registry-তে যায়
- Package খুঁজে বের করে
- Download করে
- Dependencies Download করে
- `node_modules`-এ Save করে
- `package.json` Update করে
- `package-lock.json` তৈরি/Update করে

---

# 7️⃣ What Happens After Running `npm install`

Flow:

```text
npm install
      │
      ▼
Read package.json
      │
      ▼
Connect to Registry
      │
      ▼
Download Packages
      │
      ▼
Resolve Dependencies
      │
      ▼
Create node_modules
      │
      ▼
Update package-lock.json
```

---

# 8️⃣ npm CLI Overview

**CLI (Command Line Interface)** হলো Terminal-এর মাধ্যমে npm ব্যবহার করার উপায়।

Common Commands

```bash
npm init

npm install

npm uninstall

npm update

npm run dev

npm list

npm audit
```

---

# 9️⃣ npm Folder Structure

একটি সাধারণ npm Project-এর Structure

```text
project/
│
├── node_modules/
├── package.json
├── package-lock.json
├── src/
├── .gitignore
└── README.md
```

### গুরুত্বপূর্ণ File

- **package.json** → Project Information & Dependencies
- **package-lock.json** → Exact Package Versions
- **node_modules/** → Installed Packages

---

# 🧠 Quick Mental Model

```text
Package Manager
       │
       ▼
      npm
       │
       ▼
   npm Registry
       │
       ▼
Download Packages
       │
       ▼
node_modules
       │
       ▼
Your Project Uses Them
```

---

# 📚 Summary

- **Package Manager** → Package Manage করার Tool
- **npm** → Default Package Manager for Node.js
- **Registry** → Online Package Store
- **Local Package** → শুধু Project-এর জন্য
- **Global Package** → পুরো Computer-এর জন্য
- **CLI** → Terminal থেকে npm ব্যবহার করার Interface
- **node_modules** → Installed Packages-এর Folder
- **package.json** → Project Configuration
- **package-lock.json** → Package Version Lock File

---