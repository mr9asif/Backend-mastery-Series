# CSS & Tailwind Project Setup

## 1. React + Vite + TypeScript

### Recommended Structure

```text
src/
├── components/
│   ├── ui/
│   │   ├── Button.tsx
│   │   ├── Card.tsx
│   │   └── Input.tsx
│   │
│   └── features/
│       ├── auth/
│       └── dashboard/
│
├── lib/
│   └── utils.ts
│
├── styles/
│   └── globals.css
│
├── App.tsx
└── main.tsx
```

main.tsx

```
import React from "react";
import ReactDOM from "react-dom/client";
import App from "./App";
import "./styles/globals.css";

ReactDOM.createRoot(document.getElementById("root")!).render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
);
```

### NextJs + typescript

```text
src/
├── app/
│   ├── layout.tsx
│   ├── page.tsx
│   └── globals.css
│
├── components/
│   ├── ui/
│   │   ├── Button.tsx
│   │   ├── Card.tsx
│   │   └── Input.tsx
│   │
│   └── features/
│       ├── auth/
│       └── dashboard/
│
├── lib/
│   └── utils.ts
│
└── styles/
```

#### app/layout.tsx

```
import "./globals.css";

export default function RootLayout({
  children,
}: {
  children: React.ReactNode;
}) {
  return (
    <html lang="en">
      <body>{children}</body>
    </html>
  );
}
```

#### global css

```
/* globals.css */

:root {
  --color-primary: #6366f1;
  --color-background: #ffffff;
  --color-foreground: #111827;

  --radius-md: 8px;

  --sidebar-width: 280px;
}

* {
  box-sizing: border-box;
}

body {
  margin: 0;
  background: var(--color-background);
  color: var(--color-foreground);
}
```

#### use css variable

```
.card {
  background: var(--color-background);
  border-radius: var(--radius-md);
}
```

### Tailwind css v4

```
@import "tailwindcss";

@theme {
  --color-primary: #6366f1;
  --color-secondary: #14b8a6;

  --color-background: #ffffff;
  --color-foreground: #111827;

  --radius-card: 12px;

  --font-display: "Inter", sans-serif;
}
```

### @theme vs :root

```
@theme {
  --color-primary: #6366f1;
  --radius-card: 12px;
}
```

then:

```
<div className="bg-primary rounded-card">
  Card
</div>
```

#### normal css variable

```
:root {
  --sidebar-width: 280px;
  --header-height: 64px;
}
```

then:

```
<div className="w-[var(--sidebar-width)]">
  Sidebar
</div>
```
