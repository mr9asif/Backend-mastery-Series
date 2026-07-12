# ⚙️ Chapter 08 — npm Scripts

> **Level:** Beginner → Professional Backend Developer

---

# 🎯 Learning Objectives

এই Chapter শেষ করার পর তুমি জানতে পারবে—

- npm Scripts কী?
- কেন ব্যবহার করা হয়?
- কীভাবে Script লিখতে হয়?
- সবচেয়ে Common Scripts

---

# 🤔 npm Scripts কী?

**npm Scripts** হলো `package.json`-এর একটি Section, যেখানে Project-এর বিভিন্ন Command Shortcut আকারে রাখা হয়।

এতে বড় বড় Command বারবার লিখতে হয় না।

---

# Example

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

# Script Run

```bash
npm run dev
```

এটি চালাবে

```bash
tsx watch src/server.ts
```

---

# কেন ব্যবহার করি?

ধরো প্রতিবার লিখতে হচ্ছে—

```bash
tsx watch src/server.ts
```

অনেক বড় Command।

তাই আমরা Shortcut বানাই।

```bash
npm run dev
```

---

# Most Common Scripts

## Development

```json
"dev": "tsx watch src/server.ts"
```

Run

```bash
npm run dev
```

---

## Build

```json
"build": "tsc"
```

Run

```bash
npm run build
```

---

## Start

```json
"start": "node dist/server.js"
```

Run

```bash
npm start
```

> `start` Script-এর জন্য `run` লিখতে হয় না।

---

## Test

```json
"test": "jest"
```

Run

```bash
npm test
```

---

## Lint

```json
"lint": "eslint ."
```

Run

```bash
npm run lint
```

---

## Format

```json
"format": "prettier --write ."
```

Run

```bash
npm run format
```

---

# package.json Example

```json
{
  "scripts": {
    "dev": "tsx watch src/server.ts",
    "build": "tsc",
    "start": "node dist/server.js",
    "lint": "eslint .",
    "format": "prettier --write ."
  }
}
```

---

# Special Scripts

এগুলো `run` ছাড়াই চালানো যায়।

```bash
npm start

npm test

npm stop

npm restart
```

---

# Best Practices ✅

- Standard Script Name ব্যবহার করো।
- সব Project-এ একই Naming Follow করো।

Common Scripts

```text
dev
build
start
test
lint
format
```

---

# Common Mistakes ❌

❌ একই কাজের জন্য ভিন্ন ভিন্ন Script Name ব্যবহার করা।

❌ Script-এর ভিতরে খুব বড় ও জটিল Command লেখা।

---

# 🔥 Senior Tips

Backend Project-এ সাধারণত এই Scripts থাকে—

```json
{
  "scripts": {
    "dev": "tsx watch src/server.ts",
    "build": "tsc",
    "start": "node dist/server.js",
    "lint": "eslint .",
    "format": "prettier --write .",
    "seed": "tsx prisma/seed.ts"
  }
}
```

এগুলো Industry Standard-এর খুব কাছাকাছি।

---

# Quick Revision

| Script | Purpose |
|---------|----------|
| dev | Development Server |
| build | Build Project |
| start | Run Production |
| test | Run Tests |
| lint | Check Code Quality |
| format | Format Code |

---

# Summary

- npm Scripts হলো Command Shortcut।
- এগুলো `package.json`-এর `scripts` Section-এ থাকে।
- `npm run <script>` দিয়ে চালানো হয়।
- `start` ও `test` Script `run` ছাড়াও চালানো যায়।
- Standard Script Naming ব্যবহার করা Best Practice।