# Chapter 10 — OOP Principles

> **লক্ষ্য:** OOP-এর ৪টি মূল Principle এবং Real Project-এ কখন ব্যবহার করতে হয়।

---

# 10.1 Encapsulation

## কী?

Data এবং Method একসাথে রাখা এবং Data Hide করা।

```ts
class User {
  private password = "123";

  checkPassword(pass: string) {
    return this.password === pass;
  }
}
```

## Use Case

- Password
- Token
- Bank Balance

---

# 10.2 Inheritance

## কী?

একটি Class-এর Feature আরেকটি Class ব্যবহার করা।

```ts
class Person {
  name = "Asif";
}

class Student extends Person {}
```

## Use Case

- Admin → User
- Student → Person

---

# 10.3 Polymorphism

## কী?

একই Method, ভিন্ন Behavior।

```ts
class Animal {
  sound() {}
}

class Dog extends Animal {
  override sound() {
    console.log("Bark");
  }
}

class Cat extends Animal {
  override sound() {
    console.log("Meow");
  }
}
```

## Use Case

একই Function বিভিন্ন Object Handle করতে পারে।

---

# 10.4 Abstraction

## কী?

যা দরকার শুধু সেটাই দেখানো।

```ts
abstract class Animal {
  abstract sound(): void;
}
```

## Use Case

Framework, Library Design।

---

# 10.5 Composition

## কী?

একটি Class-এর ভিতরে অন্য Class ব্যবহার করা।

```ts
class Engine {}

class Car {
  engine = new Engine();
}
```

## Use Case

Modern Application Development

> Composition > Inheritance (বেশিরভাগ ক্ষেত্রে)

---

# 10.6 Association

## কী?

দুটি Object একে অপরকে ব্যবহার করে।

```ts
class Teacher {}

class Student {
  teacher: Teacher;
}
```

## Use Case

User → Role

Post → Author

---

# 10.7 Aggregation

## কী?

একটি Object অন্য Object ব্যবহার করে, কিন্তু তার উপর নির্ভরশীল নয়।

```ts
class Department {
  students: Student[] = [];
}
```

Student আলাদাভাবেও থাকতে পারে।

---

# 10.8 Dependency Injection (Intro)

## কী?

নিজে Object না বানিয়ে বাইরে থেকে নেওয়া।

```ts
class UserService {
  constructor(
    private db: Database
  ) {}
}
```

## Use Case

NestJS

Angular

Spring Boot

---

# 10.9 SOLID (Introduction)

- S → Single Responsibility
- O → Open Closed
- L → Liskov Substitution
- I → Interface Segregation
- D → Dependency Inversion

> এগুলো Design Pattern Chapter-এ বিস্তারিত শিখব।

---

# 10.10 Composition vs Inheritance

## Inheritance

```ts
class Dog extends Animal {}
```

সম্পর্ক:

**is-a**

---

## Composition

```ts
class Car {
  engine = new Engine();
}
```

সম্পর্ক:

**has-a**

> নতুন Project-এ Composition বেশি Preferred।

---

# 10.11 Best Practices

- Encapsulation ব্যবহার করো
- Deep Inheritance Avoid করো
- Composition Prefer করো
- Interface দিয়ে Contract তৈরি করো
- OOP ব্যবহার করো যখন Object-এর Behavior আছে

---

# 📝 Quick Revision

- Encapsulation → Data Hide
- Inheritance → Code Reuse
- Polymorphism → Same Method, Different Behavior
- Abstraction → Hide Complexity
- Composition → has-a
- Inheritance → is-a
- Association → Object Relation
- Aggregation → Weak Ownership
- Dependency Injection → Outside থেকে Dependency
- SOLID → Clean Code Principles