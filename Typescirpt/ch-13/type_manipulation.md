# Chapter 13 — Type Manipulation

> **Prerequisite:**
> - Chapter 4 (Objects & Interfaces)
> - Chapter 11 (Generics)
> - Chapter 12 (Advanced Generics)

> **লক্ষ্য:** TypeScript-এর Type System ব্যবহার করে নতুন Type তৈরি করা।

---

# 13.1 keyof

## কী?

Object-এর সব Key-এর Union Type বের করে।

```ts
type User = {
  name: string;
  age: number;
};

type Keys = keyof User;
```

Result

```ts
"name" | "age"
```

## Use Case

- Dynamic Key
- Generic Function

---

# 13.2 typeof

## কী?

কোনো Variable-এর Type বের করে।

```ts
const user = {
  name: "Asif",
};

type User = typeof user;
```

## Use Case

একই Type বারবার না লিখে Reuse করা।

---

# 13.3 Indexed Access Type

## কী?

একটি Type-এর নির্দিষ্ট Property-এর Type বের করা।

```ts
type User = {
  name: string;
  age: number;
};

type Name = User["name"];
```

Result

```ts
string
```

## Use Case

একটি Property-এর Type Reuse করা।

---

# 13.4 keyof + Indexed Access

```ts
type User = {
  name: string;
  age: number;
};

type Value = User[keyof User];
```

Result

```ts
string | number
```

---

# 13.5 Mapped Type

## কী?

একটি Type-এর সব Property নিয়ে নতুন Type তৈরি করা।

```ts
type User = {
  name: string;
  age: number;
};

type ReadonlyUser = {
  readonly [K in keyof User]: User[K];
};
```

## Use Case

- Readonly
- Partial
- Pick
- Record

---

# 13.6 Conditional Type

## কী?

Condition অনুযায়ী Type Return করে।

```ts
type Check<T> =
  T extends string
    ? "Yes"
    : "No";
```

```ts
type A = Check<string>;
```

Result

```ts
"Yes"
```

---

# 13.7 infer

## কী?

Conditional Type-এর ভিতরে Type বের করার Keyword।

```ts
type Return<T> =
  T extends (...args: any[]) => infer R
    ? R
    : never;
```

## Use Case

ReturnType Utility-এর ভিতরের Logic।

---

# 13.8 Template Literal Type

## কী?

Type দিয়েই String তৈরি করা।

```ts
type Color =
  "red"
  | "blue";

type Bg = `bg-${Color}`;
```

Result

```ts
"bg-red" | "bg-blue"
```

## Use Case

- Tailwind Class
- API Route
- Event Name

---

# 13.9 Recursive Type

## কী?

নিজেকেই Reference করে।

```ts
type Node = {
  value: string;
  children?: Node[];
};
```

## Use Case

- Tree
- Comment
- Folder Structure

---

# 13.10 Distributive Conditional Type

```ts
type Test<T> =
  T extends string
    ? T
    : never;

type Result =
  Test<
    string | number
  >;
```

Result

```ts
string
```

---

# 13.11 Type Remapping

Mapped Type-এর Key পরিবর্তন করা।

```ts
type User = {
  name: string;
};

type NewUser = {
  [K in keyof User as `get${Capitalize<K>}`]: User[K];
};
```

Result

```ts
{
  getName: string;
}
```

---

# 13.12 satisfies

## কী?

Type Check করবে, কিন্তু Original Type পরিবর্তন করবে না।

```ts
type User = {
  name: string;
};

const user = {
  name: "Asif",
} satisfies User;
```

## Use Case

Configuration Object

---

# 13.13 Common Mistakes

❌ `typeof` এবং JavaScript `typeof` এক মনে করা।

> JS `typeof` → Runtime  
> TS `typeof` → Compile Time

---

❌ Generic ছাড়া Conditional Type লেখা।

---

❌ Mapped Type-এর বদলে Manual Type লেখা।

---

# 13.14 Best Practices

- Dynamic Type-এর জন্য `keyof`
- Existing Variable-এর জন্য `typeof`
- Property Type-এর জন্য Indexed Access
- Reusable Type-এর জন্য Mapped Type
- Logic-এর জন্য Conditional Type
- Type Extract করার জন্য `infer`
- String Pattern-এর জন্য Template Literal
- Config Object-এ `satisfies`

---

# 📝 Quick Revision

- `keyof` → Object-এর Key
- `typeof` → Variable-এর Type
- `T["key"]` → Property Type
- `[K in keyof T]` → Mapped Type
- `extends ? :` → Conditional Type
- `infer` → Type Extract
- `` `text-${T}` `` → Template Literal
- Recursive → Self Reference
- Distribution → Union আলাদা আলাদা Check
- `as` → Key Rename
- `satisfies` → Type Check + Original Type ঠিক রাখে