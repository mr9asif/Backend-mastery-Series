# 📦 Chapter 02 — npm CLI Commands

> **Level:** Beginner → Intermediate  
> **Goal:** npm CLI-এর গুরুত্বপূর্ণ Commands, তাদের কাজ এবং কখন ব্যবহার করতে হয় তা শেখা।

---

# 📚 What is npm CLI?

**CLI (Command Line Interface)** হলো Terminal বা Command Prompt-এর মাধ্যমে npm ব্যবহার করার Interface।

অর্থাৎ Terminal-এ `npm` লিখে যে Commands চালাও, সেগুলোই npm CLI Commands।

Example:

```bash
npm install express
```

এখানে `npm` হলো CLI Tool।

---

# 🛠️ npm CLI Commands

## 1️⃣ `npm init`

### কী করে?

নতুন Node.js Project Initialize করে এবং `package.json` তৈরি করে।

### Syntax

```bash
npm init
```

Quick Setup

```bash
npm init -y
```

### কখন ব্যবহার করবে?

- নতুন Project শুরু করার সময়
- `package.json` তৈরি করার জন্য

---

## 2️⃣ `npm install`

### কী করে?

Package Install করে।

### একটি Package Install

```bash
npm install express
```

Shortcut

```bash
npm i express
```

### সব Dependencies Install

```bash
npm install
```

এটি `package.json` দেখে সব Package Install করে।

### Dev Dependency Install

```bash
npm install -D typescript
```

অথবা

```bash
npm install --save-dev typescript
```

### Global Install

```bash
npm install -g typescript
```

### কখন ব্যবহার করবে?

- নতুন Package Install
- GitHub থেকে Project Clone করার পরে
- Dependency Install করার জন্য

---

## 3️⃣ `npm uninstall`

### কী করে?

Package Remove করে।

### Syntax

```bash
npm uninstall express
```

### Dev Dependency Remove

```bash
npm uninstall typescript
```

### কখন ব্যবহার করবে?

যখন কোনো Package আর দরকার হবে না।

---

## 4️⃣ `npm update`

### কী করে?

Installed Packages Update করে।

### Syntax

```bash
npm update
```

### কখন ব্যবহার করবে?

Compatible Version Update করার জন্য।

---

## 5️⃣ `npm list`

### কী করে?

Installed Packages দেখায়।

### Syntax

```bash
npm list
```

Top Level Packages

```bash
npm list --depth=0
```

### কখন ব্যবহার করবে?

Project-এ কী কী Package Install আছে দেখতে।

---

## 6️⃣ `npm outdated`

### কী করে?

যেসব Package-এর নতুন Version Available আছে সেগুলো দেখায়।

### Syntax

```bash
npm outdated
```

### কখন ব্যবহার করবে?

Package Update করার আগে।

---

## 7️⃣ `npm run`

### কী করে?

`package.json`-এর Scripts Run করে।

Example

```json
{
  "scripts": {
    "dev": "tsx watch src/server.ts",
    "build": "tsc",
    "start": "node dist/server.js"
  }
}
```

Run

```bash
npm run dev

npm run build

npm run start
```

### কখন ব্যবহার করবে?

Project-এর Custom Scripts চালানোর জন্য।

---

## 8️⃣ `npm audit`

### কী করে?

Security Vulnerability Check করে।

### Syntax

```bash
npm audit
```

Auto Fix

```bash
npm audit fix
```

### কখন ব্যবহার করবে?

Production Deploy করার আগে।

---

## 9️⃣ `npm doctor`

### কী করে?

npm Installation এবং Environment Check করে।

### Syntax

```bash
npm doctor
```

### কখন ব্যবহার করবে?

npm-এ সমস্যা হলে।

---

## 🔟 `npm cache`

### কী করে?

npm Cache Manage করে।

Verify Cache

```bash
npm cache verify
```

Clear Cache

```bash
npm cache clean --force
```

### কখন ব্যবহার করবে?

Package Download-এ সমস্যা হলে।

---

## 1️⃣1️⃣ `npm version`

### কী করে?

Project Version Update করে।

### Syntax

```bash
npm version patch

npm version minor

npm version major
```

### কখন ব্যবহার করবে?

নিজের Package Publish করার আগে Version Change করার জন্য।

---

## 1️⃣2️⃣ `npm login`

### কী করে?

npm Registry-তে Login করে।

### Syntax

```bash
npm login
```

### কখন ব্যবহার করবে?

নিজের Package Publish করার আগে।

---

## 1️⃣3️⃣ `npm whoami`

### কী করে?

বর্তমানে কোন npm Account Login করা আছে তা দেখায়।

### Syntax

```bash
npm whoami
```

---

## 1️⃣4️⃣ `npm publish`

### কী করে?

নিজের Package npm Registry-তে Publish করে।

### Syntax

```bash
npm publish
```

### কখন ব্যবহার করবে?

নিজের Library বা Package Publish করার সময়।

---

## 1️⃣5️⃣ `npm root`

### কী করে?

Installed Packages কোথায় Store হয়েছে তা দেখায়।

### Syntax

```bash
npm root
```

Global Packages

```bash
npm root -g
```

---

## 1️⃣6️⃣ `npm prefix`

### কী করে?

Current npm Project-এর Root Directory দেখায়।

### Syntax

```bash
npm prefix
```

---

# ⭐ Most Used Commands (Daily)

| Command | Purpose |
|----------|----------|
| `npm init -y` | নতুন Project তৈরি |
| `npm install` | সব Dependency Install |
| `npm install package-name` | নতুন Package Install |
| `npm install -D package-name` | Dev Dependency Install |
| `npm install -g package-name` | Global Install |
| `npm uninstall package-name` | Package Remove |
| `npm update` | Package Update |
| `npm run dev` | Development Server চালানো |
| `npm run build` | Project Build |
| `npm run start` | Production Server চালানো |
| `npm list --depth=0` | Installed Packages দেখা |
| `npm outdated` | পুরনো Package Check |
| `npm audit` | Security Check |

---

# 💡 Best Practices

- ✅ নতুন Project শুরু করলে `npm init -y` ব্যবহার করো।
- ✅ Project Clone করার পরে `npm install` চালাও।
- ✅ Development Tools (`typescript`, `eslint`, `prettier`) `-D` দিয়ে Install করো।
- ✅ `package-lock.json` Git-এ Commit করো।
- ✅ Production-এর আগে `npm audit` চালাও।

---

# ⚠️ Common Mistakes

❌ `node_modules` Git-এ Push করা।

❌ সব Package Global Install করা।

❌ `package-lock.json` Delete করে দেওয়া।

❌ `npm install` না চালিয়ে Project Run করার চেষ্টা করা।

---

# 🧠 Quick Revision

| Command | কী কাজ করে? |
|----------|-------------|
| `npm init` | Project Initialize |
| `npm install` | Package Install |
| `npm uninstall` | Package Remove |
| `npm update` | Package Update |
| `npm list` | Installed Packages দেখা |
| `npm outdated` | নতুন Version Check |
| `npm run` | Script Run |
| `npm audit` | Security Check |
| `npm doctor` | npm Health Check |
| `npm cache` | Cache Manage |
| `npm version` | Version Change |
| `npm login` | npm Login |
| `npm publish` | Package Publish |

---

# 🎯 Learning Outcome

এই Chapter শেষ করার পর তুমি জানতে পারবে—

- npm CLI কী
- সবচেয়ে বেশি ব্যবহৃত npm Commands
- কোন Command কখন ব্যবহার করতে হয়
- Development ও Production-এ কোন Command গুরুত্বপূর্ণ
- Interview-এ আসা Basic npm Commands-এর উত্তর
```