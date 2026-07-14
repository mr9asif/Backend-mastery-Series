# Chapter 14 — Utility Types

> **Prerequisite:**
> - Chapter 13 (Type Manipulation)

> **লক্ষ্য:** TypeScript-এর Built-in Utility Types ব্যবহার করে দ্রুত নতুন Type তৈরি করা।

---

# 14.1 Partial<T>

## কী?

সব Property Optional করে।

```ts
interface User {
  name: string;
  age: number;
}

type UpdateUser = Partial<User>;
```

## Use Case

Update API (`PATCH`)

---

# 14.2 Required<T>

## কী?

সব Optional Property Required করে।

```ts
type User = {
  name?: string;
};

type NewUser = Required<User>;
```

## Use Case

Validation

---

# 14.3 Readonly<T>

## কী?

সব Property Readonly করে।

```ts
type User = Readonly<{
  name: string;
}>;
```

## Use Case

Immutable Data

---

# 14.4 Pick<T, K>

## কী?

নির্দিষ্ট Property বেছে নেয়।

```ts
type User = {
  name: string;
  age: number;
};

type BasicUser = Pick<User, "name">;
```

## Use Case

Profile Response

---

# 14.5 Omit<T, K>

## কী?

নির্দিষ্ট Property বাদ দেয়।

```ts
type User = {
  name: string;
  password: string;
};

type PublicUser = Omit<User, "password">;
```

## Use Case

API Response

---

# 14.6 Record<K, T>

## কী?

Key এবং Value দিয়ে Object তৈরি করে।

```ts
type User = Record<string, number>;
```

## Use Case

Dictionary

Cache

---

# 14.7 Exclude<T, U>

## কী?

Union থেকে Type বাদ দেয়।

```ts
type T =
  Exclude<
    string | number,
    number
  >;
```

Result

```ts
string
```

---

# 14.8 Extract<T, U>

## কী?

Union থেকে শুধু Matching Type রাখে।

```ts
type T =
  Extract<
    string | number,
    string
  >;
```

Result

```ts
string
```

---

# 14.9 NonNullable<T>

## কী?

null এবং undefined বাদ দেয়।

```ts
type T =
  NonNullable<
    string | null
  >;
```

Result

```ts
string
```

---

# 14.10 ReturnType<T>

## কী?

Function-এর Return Type বের করে।

```ts
function getUser() {
  return {
    name: "Asif",
  };
}

type User =
  ReturnType<typeof getUser>;
```

## Use Case

API Function

---

# 14.11 Parameters<T>

## কী?

Function-এর Parameter Type বের করে।

```ts
function add(
  a: number,
  b: number
) {}

type Args =
  Parameters<typeof add>;
```

Result

```ts
[number, number]
```

---

# 14.12 ConstructorParameters<T>

Constructor-এর Parameter Type বের করে।

```ts
class User {
  constructor(
    name: string
  ) {}
}

type P =
  ConstructorParameters<
    typeof User
  >;
```

---

# 14.13 InstanceType<T>

Class-এর Instance Type বের করে।

```ts
class User {}

type U =
  InstanceType<
    typeof User
  >;
```

---

# 14.14 Awaited<T>

Promise-এর ভিতরের Type বের করে।

```ts
type Data =
  Awaited<
    Promise<string>
  >;
```

Result

```ts
string
```

---

# 14.15 ThisParameterType<T>

Function-এর `this` Type বের করে।

```ts
function greet(
  this: { name: string }
) {}

type T =
  ThisParameterType<
    typeof greet
  >;
```

---

# 14.16 OmitThisParameter<T>

Function থেকে `this` Remove করে।

---

# 14.17 ThisType<T>

Object Literal-এ `this` Type Define করতে।

> খুব কম ব্যবহার হয়।

---

# 14.18 Common Mistakes

❌ Manual Type লিখা

```ts
type UserUpdate = {
  name?: string;
  age?: number;
};
```

এর বদলে

```ts
Partial<User>
```

---

❌

Password Remove করতে নতুন Type বানানো।

```ts
Omit<User, "password">
```

ব্যবহার করো।

---

# 14.19 Best Practices

- Update → Partial
- Response → Pick / Omit
- Immutable → Readonly
- Dynamic Object → Record
- Function Type → ReturnType / Parameters
- Promise → Awaited

---

# 📝 Quick Revision

- Partial → Optional
- Required → Required
- Readonly → Readonly
- Pick → Select
- Omit → Remove
- Record → Object
- Exclude → Remove Union
- Extract → Keep Union
- NonNullable → Remove null
- ReturnType → Function Return
- Parameters → Function Params
- ConstructorParameters → Constructor Params
- InstanceType → Class Instance
- Awaited → Promise Type
- ThisParameterType → this Type
- OmitThisParameter → Remove this
- ThisType → Define this