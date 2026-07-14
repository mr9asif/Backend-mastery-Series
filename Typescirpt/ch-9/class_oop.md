# Chapter 9 — Classes & OOP

> **লক্ষ্য:** TypeScript-এ Class, Inheritance এবং OOP-এর Core Concepts শেখা।

---

# 9.1 Class

## কী?

Object তৈরির Blueprint।

## Syntax

```ts
class User {
  name = "Asif";
}

const user = new User();
```

## Use Case

- User
- Product
- Order Model

---

# 9.2 Constructor

## কী?

Object তৈরি হওয়ার সময় Automatically Call হয়।

```ts
class User {
  constructor(public name: string) {}
}

const user = new User("Asif");
```

## Use Case

Object Initialize করতে।

---

# 9.3 Property & Method

```ts
class User {
  name = "Asif";

  greet() {
    console.log("Hello");
  }
}
```

- Property → Data
- Method → Function

---

# 9.4 Parameter Property

Constructor-এর মধ্যেই Property Declare করা।

```ts
class User {
  constructor(
    public name: string,
    public age: number
  ) {}
}
```

## Use Case

Boilerplate Code কমাতে।

---

# 9.5 Access Modifier

## public (Default)

সব জায়গা থেকে Access করা যায়।

```ts
public name: string;
```

---

## private

শুধু Class-এর ভিতরে Access করা যায়।

```ts
private password: string;
```

Use Case

Password, Token, Secret Data।

---

## protected

Class + Child Class Access করতে পারে।

```ts
protected age: number;
```

Use Case

Inheritance।

---

# 9.6 readonly

একবার Assign করার পরে পরিবর্তন করা যায় না।

```ts
readonly id = 1;
```

Use Case

ID, CreatedAt

---

# 9.7 static

Object ছাড়াই Access করা যায়।

```ts
class MathUtil {
  static PI = 3.14;
}

MathUtil.PI;
```

Use Case

Utility Function, Constant।

---

# 9.8 Getter

Property Read করার Custom Method।

```ts
class User {
  private _name = "Asif";

  get name() {
    return this._name;
  }
}
```

---

# 9.9 Setter

Property Update করার Custom Method।

```ts
class User {
  private _name = "";

  set name(value: string) {
    this._name = value;
  }
}
```

---

# 9.10 Inheritance (`extends`)

একটি Class-এর Feature আরেকটি Class ব্যবহার করে।

```ts
class Person {
  name = "Asif";
}

class Student extends Person {}
```

## Use Case

Code Reuse।

---

# 9.11 super

Parent Class-এর Constructor/Method Call করতে।

```ts
class Person {
  constructor(public name: string) {}
}

class Student extends Person {
  constructor(name: string) {
    super(name);
  }
}
```

---

# 9.12 Method Overriding

Child Class Parent-এর Method পরিবর্তন করে।

```ts
class Animal {
  sound() {
    console.log("Sound");
  }
}

class Dog extends Animal {
  override sound() {
    console.log("Bark");
  }
}
```

> `override` ব্যবহার করলে ভুল Method Name হলে Compiler Error দেয়।

---

# 9.13 Abstract Class

নিজে Object তৈরি করা যায় না।

```ts
abstract class Animal {
  abstract sound(): void;
}

class Dog extends Animal {
  sound() {
    console.log("Bark");
  }
}
```

## Use Case

Common Rule Define করতে।

---

# 9.14 Interface + implements

Class-কে একটি Contract Follow করায়।

```ts
interface User {
  login(): void;
}

class Admin implements User {
  login() {
    console.log("Login");
  }
}
```

## Use Case

API Contract, Service Layer।

---

# 9.15 Interface vs Abstract

| Interface | Abstract |
|-----------|----------|
| শুধু Structure | Structure + Implementation |
| Property/Method Declaration | Method Body থাকতে পারে |
| implements | extends |

---

# 9.16 this

বর্তমান Object-কে নির্দেশ করে।

```ts
class User {
  name = "Asif";

  greet() {
    console.log(this.name);
  }
}
```

---

# 9.17 #private

JavaScript-এর Real Private Field।

```ts
class User {
  #password = "123";
}
```

> `private` = TypeScript Feature  
> `#private` = JavaScript Feature

---

# 9.18 Best Practices

- `public` না লিখলেও চলে
- Sensitive Data → `private`
- Constant → `readonly`
- Utility → `static`
- Code Reuse → `extends`
- Contract → `interface`
- Common Base Logic → `abstract`
- `override` ব্যবহার করো

---

# 📝 Quick Revision

- Class → Blueprint
- Object → `new`
- Constructor → Initialize
- Property → Data
- Method → Function
- public → সবাই Access
- private → শুধু Class
- protected → Class + Child
- readonly → পরিবর্তন করা যায় না
- static → Class Member
- getter → Read
- setter → Update
- extends → Inheritance
- super → Parent Access
- override → Parent Method পরিবর্তন
- abstract → Object তৈরি করা যায় না
- implements → Interface Follow
- this → Current Object
- #private → Real Runtime Private