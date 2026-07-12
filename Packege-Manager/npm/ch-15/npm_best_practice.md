# ⭐ Chapter 15 — npm Best Practices

> **Level:** Professional Backend Developer

---

# 🎯 Best Practices

## 1. সবসময় `npm init -y` দিয়ে Project শুরু করো।

---

## 2. Runtime Package এবং Development Package আলাদা রাখো।

Runtime

```bash
npm install express
```

Development

```bash
npm install -D typescript
```

---

## 3. `package-lock.json` Git-এ Commit করো।

✅ Yes

---

## 4. `node_modules` কখনো GitHub-এ Push করো না।

`.gitignore`

```gitignore
node_modules/
```

---

## 5. Standard Scripts ব্যবহার করো।

```text
dev
build
start
test
lint
format
```

---

## 6. `npm audit` মাঝে মাঝে চালাও।

```bash
npm audit
```

---

## 7. Global Package কম ব্যবহার করো।

যেখানে সম্ভব

```bash
npx
```

ব্যবহার করো।

---

## 8. অপ্রয়োজনীয় Package Install করো না।

যত কম Dependency, তত ভালো।

---

## 9. Trusted Package ব্যবহার করো।

Install করার আগে—

- GitHub
- Weekly Downloads
- Last Update

Check করো।

---

## 10. README.md লিখার অভ্যাস করো।

একটি Professional Project-এ সবসময় README থাকা উচিত।

---

# 🔥 Senior Tips

- Package Install করার আগে Documentation পড়ো।
- Version বুঝে Update করো।
- Dependency নিয়মিত Review করো।
- Project Clean রাখো।

---

# Quick Checklist ✅

- [ ] `package.json` ঠিক আছে
- [ ] `package-lock.json` Commit করা হয়েছে
- [ ] `node_modules` Ignore করা হয়েছে
- [ ] `.env` Ignore করা হয়েছে
- [ ] `npm audit` চালানো হয়েছে
- [ ] Scripts ঠিকভাবে Configure করা হয়েছে
- [ ] শুধু প্রয়োজনীয় Package Install করা হয়েছে

---

# Summary

একজন Professional Backend Developer হিসেবে—

- npm-এর Basic Commands জানতে হবে।
- Dependency Management বুঝতে হবে।
- `package.json` ও `package-lock.json` ভালোভাবে জানতে হবে।
- Security ও Best Practices Follow করতে হবে।
- Clean ও Maintainable Project Structure বজায় রাখতে হবে।