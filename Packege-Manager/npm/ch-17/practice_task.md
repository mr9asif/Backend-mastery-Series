# 💻 Chapter 17 — Hands-on Practice Projects

> **Goal:** npm সম্পর্কে শেখা বিষয়গুলো Practice করে বাস্তবে ব্যবহার করা।

---

# 🥇 Project 01 — My First Node.js Project

### Objective

- npm init
- package.json
- node_modules

### Tasks

- নতুন Folder তৈরি করো।
- `npm init -y` চালাও।
- Express Install করো।
- package.json Observe করো।
- node_modules দেখো।

---

# 🥈 Project 02 — Dependency Practice

### Objective

dependencies এবং devDependencies বুঝা।

### Install

```bash
npm install express

npm install zod

npm install -D typescript

npm install -D tsx
```

### Tasks

দেখো—

- কোন Package কোথায় গেছে?
- package.json কীভাবে Update হয়েছে?

---

# 🥉 Project 03 — npm Scripts

### package.json

```json
{
  "scripts": {
    "dev": "node index.js",
    "hello": "echo Hello World"
  }
}
```

Run

```bash
npm run hello

npm run dev
```

---

# 🏅 Project 04 — Local vs Global

Install

```bash
npm install cowsay
```

Run

```bash
npx cowsay "Hello npm"
```

তারপর

```bash
npm install -g cowsay
```

Run

```bash
cowsay "Hello npm"
```

Difference Observe করো।

---

# 🏆 Project 05 — package-lock.json

### Tasks

- একটি নতুন Project তৈরি করো।
- Express Install করো।
- package-lock.json দেখো।
- Delete করো।
- আবার `npm install` চালাও।
- Compare করো।

---

# 🎖️ Project 06 — npm Registry

Tasks

- https://www.npmjs.com এ যাও।
- Express Search করো।
- Prisma Search করো।
- Zod Search করো।

নিচের Information দেখো—

- Version
- Weekly Downloads
- Repository
- Documentation

---

# 🏅 Project 07 — npm Security

Run

```bash
npm audit

npm audit fix
```

দেখো npm কী Report দেয়।

---

# 🏅 Project 08 — Build Your Own Backend Setup

নিচের Package Install করো।

```bash
npm install express zod dotenv

npm install -D typescript tsx prisma eslint prettier
```

তারপর Configure করো—

- package.json
- scripts
- .gitignore

---

# 🚀 Mini Challenge

নিজে একটি Backend Project Setup করো যেখানে থাকবে—

- package.json
- package-lock.json
- node_modules
- Express
- TypeScript
- npm Scripts
- Git
- README.md

---

# ✅ Final Checklist

Practice করতে পারলে তুমি পারবে—

- [ ] npm init
- [ ] npm install
- [ ] npm uninstall
- [ ] npm update
- [ ] npm Scripts
- [ ] package.json
- [ ] package-lock.json
- [ ] node_modules
- [ ] npx
- [ ] npm audit
- [ ] Local vs Global Package

---

# 🎯 Learning Outcome

এই Chapter-এর সব Practice শেষ করলে তুমি—

- npm নিয়ে Confident হবে।
- নতুন Node.js Project নিজে Setup করতে পারবে।
- Real Backend Project শুরু করতে পারবে।
- TypeScript + Express শেখার জন্য পুরোপুরি প্রস্তুত থাকবে।