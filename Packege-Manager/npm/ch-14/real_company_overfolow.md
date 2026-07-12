# 🏢 Chapter 14 — Real Company Workflow

> **Level:** Professional Backend Developer

---

# একটি নতুন Project শুরু হলে সাধারণ Workflow

## 1. Create Project

```bash
mkdir project-name

cd project-name

npm init -y
```

---

## 2. Install Dependencies

```bash
npm install express zod dotenv
```

---

## 3. Install Development Tools

```bash
npm install -D typescript tsx eslint prettier
```

---

## 4. Create Folder Structure

```text
src/
prisma/
package.json
tsconfig.json
.env
.gitignore
```

---

## 5. Configure Scripts

```json
{
  "scripts": {
    "dev": "tsx watch src/server.ts",
    "build": "tsc",
    "start": "node dist/server.js"
  }
}
```

---

## 6. Development

```bash
npm run dev
```

---

## 7. Build

```bash
npm run build
```

---

## 8. Production

```bash
npm start
```

---

# GitHub-এ কী Push হবে?

✅ Push হবে

```text
src/
prisma/
package.json
package-lock.json
README.md
```

❌ Push হবে না

```text
node_modules/
.env
dist/
```

---

# Summary

Company-তে সাধারণত Flow হয়—

```text
Create Project
      │
Install Packages
      │
Configure Project
      │
Develop
      │
Build
      │
Deploy
```