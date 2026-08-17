# `cn()` in Tailwind

## 1. What is `cn()`?

`cn()` is a small helper function commonly used in React + Tailwind projects, especially with shadcn/ui.

> `cn()` is **not** a built-in Tailwind function.

It combines two utilities:

- `clsx` → conditional class names handle করে
- `tailwind-merge` → conflicting Tailwind classes merge করে

The common implementation:

```ts
import { clsx, type ClassValue } from "clsx";
import { twMerge } from "tailwind-merge";

export function cn(...inputs: ClassValue[]) {
  return twMerge(clsx(inputs));
}

## Installation
```

npm install clsx tailwind-merge

```

## React + Vite + TypeScript Setup or nextjs
src/lib/utils


import { clsx, type ClassValue } from "clsx";
import { twMerge } from "tailwind-merge";

export function cn(...inputs: ClassValue[]) {
  return twMerge(clsx(inputs));
}
```

### more example

```
function Button({ active }: { active: boolean }) {
  return (
    <button
      className={
        active
          ? "rounded-lg bg-blue-500 px-4 py-2 text-white"
          : "rounded-lg bg-gray-300 px-4 py-2 text-black"
      }
    >
      Login
    </button>
  );
}

--Using CN

import { cn } from "@/lib/utils";

function Button({ active }: { active: boolean }) {
  return (
    <button
      className={cn(
        "rounded-lg px-4 py-2",
        active && "bg-blue-500 text-white",
        !active && "bg-gray-300 text-black"
      )}
    >
      Login
    </button>
  );
}
```
