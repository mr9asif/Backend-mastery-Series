## What is CSS?

CSS is a stylesheet language used to control the presentation, layout, appearance, and responsive design of HTML elements.

## CaseCade

When multiple CSS rules target the same element, the cascade determines which declarations win based on factors such as importance, specificity, and source order.

## Selector

## Group Selector[]

```
<input type="text">
<input type="email">

input[type="email"] {
border: 2px solid green;
}
```

## Grouping Selector ,

```
h1,
h2,
h3 {
  font-family: sans-serif;
}
```

## Descendant Selector

```
.card p {
  color: gray;
}

<div class="card">
  <p>Hello</p>

  <div>
    <p>World</p>
  </div>
</div>

```

দুটো <p>-ই select হবে।

কারণ তারা .card-এর descendant।

### Important

Descendant মানে শুধু direct child না।

যেকোনো depth-এর ভিতরে থাকলেই হবে।

## Child Selector >

```
.card > p {
  color: red;
}

<div class="card">
  <p>Direct child</p>

  <div>
    <p>Nested paragraph</p>
  </div>
</div>

```

### শুধু প্রথম <p> select হবে।

## Adjacent Sibling Selector +

```
h2 + p {
  color: red;
}
<h2>Title</h2>
<p>This will be red.</p>
<p>This will NOT be red.</p>
```

শুধু প্রথম <p> select হবে।

কারণ সেটাই h2-এর immediately next sibling।

## General Sibling Selector ~

```
h2 ~ p {
  color: red;
}
<h2>Title</h2>
<p>One</p>
<p>Two</p>
<p>Three</p>
```

তিনটা <p>-ই select হবে।

কারণ তারা h2-এর পরে থাকা siblings।

## Pseudo-class

```
selector:pseudo-class

button:hover {
  background: black;
}

```

```
:hover

Mouse element-এর উপর গেলে:

button:hover {
  transform: scale(1.05);
}
:focus

Input focus করলে:

input:focus {
  outline: 2px solid blue;
}
:active

Element active অবস্থায়:

button:active {
  transform: scale(0.98);
}
:disabled
button:disabled {
  opacity: 0.5;
}
:checked
input:checked {
  accent-color: blue;
}

Checkbox/radio-এর ক্ষেত্রে useful।

Structural Pseudo-classes
:first-child
li:first-child {
  color: red;
}

Parent-এর first child যদি li হয়, select হবে।

:last-child
li:last-child {
  color: blue;
}
:nth-child()
li:nth-child(2) {
  color: green;
}

দ্বিতীয় child select হবে।

আর:

li:nth-child(odd)

Odd position।

li:nth-child(even)

Even position।

Powerful Modern Pseudo-classes

এগুলো advanced CSS-এর জন্য খুব important।

:not()
button:not(.primary) {
  background: gray;
}

মানে:

.primary নয় এমন button select করো।

:is()
:is(h1, h2, h3) {
  line-height: 1.2;
}

একাধিক selector group করার সহজ উপায়।

:where()
:where(h1, h2, h3) {
  margin: 0;
}

:is()-এর মতো grouping করতে পারে, কিন্তু এর specificity 0।

এটা CSS architecture-এ খুব useful।

:has() ⭐⭐⭐

এটা modern CSS-এর অত্যন্ত powerful selector।

.card:has(img) {
  padding: 0;
}

মানে:

যে .card-এর ভিতরে img আছে, সেই .card select করো।

আরেকটি:

.form-group:has(input:invalid) {
  border-color: red;
}

এখানে input invalid হলে তার parent .form-group style করা যায়।

আগে এই ধরনের parent-based styling অনেক ক্ষেত্রে JavaScript ছাড়া কঠিন ছিল।

```

## Pseudo-element

Pseudo-element দিয়ে কোনো element-এর specific part বা generated content style করা যায়।

Syntax:

```
selector::pseudo-element

সবচেয়ে common:

p::first-letter {
  font-size: 40px;
}

শুধু প্রথম letter style হবে।

::before
.button::before {
  content: "";
}

Element-এর content-এর আগে generated content তৈরি করতে পারে।

::after
placeholder

```

## Specificity

p → 0-0-0-1
.text → 0-0-1-0
#title → 0-1-0-0
inline → 1-0-0-0
