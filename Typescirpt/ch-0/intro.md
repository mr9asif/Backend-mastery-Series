# Chapter 0 — Introduction to TypeScript

> **লক্ষ্য:** TypeScript কী, কেন এসেছে, এবং কীভাবে কাজ করে তা বোঝা।

---

# 0.1 TypeScript কী?

**TypeScript (TS)** হলো JavaScript-এর একটি **Superset**।

অর্থাৎ,

- ✅ সব JavaScript কোড = Valid TypeScript
- ❌ সব TypeScript কোড = Valid JavaScript নয় (Compile করার আগে)

---

# 0.2 কেন TypeScript?

JavaScript-এ Type Checking নেই।

**JavaScript**

```js
let age = 20;
age = "Twenty";
```

➡️ কোনো Error দেখাবে না।

**TypeScript**

```ts
let age: number = 20;
age = "Twenty"; // ❌ Error
```

**সুবিধা**

- কম Bug
- ভালো Auto Suggestion
- Refactoring সহজ
- বড় Project Manage করা সহজ

---

# 0.3 TypeScript কীভাবে কাজ করে?

```text
TypeScript (.ts)
      │
      ▼
TypeScript Compiler (tsc)
      │
      ▼
JavaScript (.js)
      │
      ▼
Browser / Node.js
```

> **মনে রাখবে:** Browser বা Node.js TypeScript বোঝে না, তারা শুধু JavaScript চালায়।

---

# 0.4 Compile কী?

Compile = **`.ts` → `.js`** এ রূপান্তর করা।

```bash
tsc app.ts
```

---

# 0.5 Compile Time vs Runtime

## Compile Time

- Type Check হয়
- Error ধরা পড়ে
- JavaScript তৈরি হয়

## Runtime

- JavaScript Execute হয়
- Browser / Node.js কোড চালায়

---

# 0.6 Type Erasure

Compile হওয়ার পর সব Type মুছে যায়।

**TypeScript**

```ts
let age: number = 20;
```

**JavaScript (Compile হওয়ার পর)**

```js
let age = 20;
```

> অর্থাৎ Type শুধু Development-এর সময় থাকে।

---

# 0.7 TypeScript Install

```bash
npm install -g typescript
```

Version দেখো

```bash
tsc --version
```

---

# 0.8 প্রথম Program

```ts
let message: string = "Hello TypeScript";

console.log(message);
```

Compile

```bash
tsc index.ts
```

Run

```bash
node index.js
```

---

# 📝 Quick Revision

- TypeScript = JavaScript + Types
- TypeScript হলো JavaScript-এর Superset
- `tsc` TypeScript কে JavaScript এ Compile করে
- Browser / Node.js শুধু JavaScript চালায়
- Compile Time = Type Check
- Runtime = Code Execute
- Compile-এর পরে সব Type মুছে যায় (**Type Erasure**)