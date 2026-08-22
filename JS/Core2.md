## JavaScript Object, Prototype & Prototypal Inheritance — Summary

### 1. Object

Object হলো related data এবং methods রাখার একটি collection।

```
const user = {
name: "Reja",
greet() {
console.log("Hello");
},
};
```

### 2. Prototype

প্রতিটি সাধারণ object-এর একটি prototype link থাকে।

যখন কোনো property object-এর ভিতরে পাওয়া যায় না, JavaScript prototype-এ খোঁজে।

object
↓
prototype
↓
null

Example:

```
const user = {
name: "Reja",
};

user.toString();
```

toString() user-এর own property নয়। এটি Object.prototype থেকে পাওয়া যায়।

3. Prototype Chain

JavaScript property খোঁজে এভাবে:

Object নিজে
↓
তার Prototype
↓
আরও Prototype
↓
Object.prototype
↓
null 4. Prototypal Inheritance

একটি object অন্য object-এর prototype থেকে property বা method ব্যবহার করতে পারলে তাকে Prototypal Inheritance বলে।

const animal = {
eat() {
console.log("Eating");
},
};

const dog = Object.create(animal);

dog.eat();

Search:

dog
↓
animal
↓
eat() found 5. Important: Copy হয় না

Inheritance-এর সময় method copy হয় না।

বরং object-এর মধ্যে একটি prototype link তৈরি হয়।

```
dog ───→ animal 6. Constructor ও Prototype
function User(name) {
this.name = name;
}

User.prototype.greet = function () {
console.log(`Hello ${this.name}`);
};
`
const user1 = new User("Reja");
```

Relationship:

user1
↓
User.prototype
↓
Object.prototype
↓
null

User.prototype-এর method সব User object share করতে পারে।

7. prototype vs [[Prototype]]
   User.prototype
   → Constructor function-এর property

```
Object [[Prototype]]
→ Object যে prototype-এর সাথে linked
Object.getPrototypeOf(user) === User.prototype;
// true 8. Class-ও Prototype ব্যবহার করে
class Animal {
eat() {
console.log("Eating");
}
}

class Dog extends Animal {
bark() {
console.log("Woof");
}
}

Behind the scenes:

dog
↓
Dog.prototype
↓
Animal.prototype
↓
Object.prototype
↓
null
```

Interview Answer

A prototype is an object that JavaScript uses for property and method lookup. If a property is not found on an object itself, JavaScript searches its prototype chain. Prototypal inheritance allows objects to inherit properties and methods through this prototype chain without copying them.
