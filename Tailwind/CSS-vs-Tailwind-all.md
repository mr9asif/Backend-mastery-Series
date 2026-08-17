# CSS → Tailwind Quick Revision

> Tailwind v4 — Quick Reference
>
> Format:
> CSS → Tailwind

---

# 1. Display

| CSS                     | Tailwind       |
| ----------------------- | -------------- |
| `display: block`        | `block`        |
| `display: inline`       | `inline`       |
| `display: inline-block` | `inline-block` |
| `display: flex`         | `flex`         |
| `display: inline-flex`  | `inline-flex`  |
| `display: grid`         | `grid`         |
| `display: inline-grid`  | `inline-grid`  |
| `display: none`         | `hidden`       |

```html
<div class="block">Block</div>

<div class="flex">Flex</div>

<div class="grid">Grid</div>

<div class="hidden">Hidden</div>
```

#### Width and Height

```
| CSS                   | Tailwind   |
| --------------------- | ---------- |
| `width: 100%`         | `w-full`   |
| `width: 100vw`        | `w-screen` |
| `width: auto`         | `w-auto`   |
| `width: fit-content`  | `w-fit`    |
| `width: max-content`  | `w-max`    |
| `width: min-content`  | `w-min`    |
| `height: 100%`        | `h-full`   |
| `height: 100vh`       | `h-screen` |
| `height: auto`        | `h-auto`   |
| `height: fit-content` | `h-fit`    |
```

```
# CSS → Tailwind Complete Quick Reference

| # | CSS | Tailwind |
|---:|---|---|
| 1 | `display: block` | `block` |
| 2 | `display: inline` | `inline` |
| 3 | `display: inline-block` | `inline-block` |
| 4 | `display: flex` | `flex` |
| 5 | `display: inline-flex` | `inline-flex` |
| 6 | `display: grid` | `grid` |
| 7 | `display: inline-grid` | `inline-grid` |
| 8 | `display: none` | `hidden` |
| 9 | `position: static` | `static` |
| 10 | `position: relative` | `relative` |
| 11 | `position: absolute` | `absolute` |
| 12 | `position: fixed` | `fixed` |
| 13 | `position: sticky` | `sticky` |
| 14 | `top: 0` | `top-0` |
| 15 | `right: 0` | `right-0` |
| 16 | `bottom: 0` | `bottom-0` |
| 17 | `left: 0` | `left-0` |
| 18 | `inset: 0` | `inset-0` |
| 19 | `z-index: 10` | `z-10` |
| 20 | `width: 100%` | `w-full` |
| 21 | `width: 100vw` | `w-screen` |
| 22 | `width: auto` | `w-auto` |
| 23 | `width: fit-content` | `w-fit` |
| 24 | `width: max-content` | `w-max` |
| 25 | `width: min-content` | `w-min` |
| 26 | `width: 50%` | `w-1/2` |
| 27 | `width: 33.333%` | `w-1/3` |
| 28 | `width: 66.666%` | `w-2/3` |
| 29 | `height: 100%` | `h-full` |
| 30 | `height: 100vh` | `h-screen` |
| 31 | `height: auto` | `h-auto` |
| 32 | `height: fit-content` | `h-fit` |
| 33 | `min-height: 100vh` | `min-h-screen` |
| 34 | `min-width: 0` | `min-w-0` |
| 35 | `max-width: 1280px` | `max-w-7xl` |
| 36 | `max-width: 100%` | `max-w-full` |
| 37 | `padding: 4px` | `p-1` |
| 38 | `padding: 8px` | `p-2` |
| 39 | `padding: 12px` | `p-3` |
| 40 | `padding: 16px` | `p-4` |
| 41 | `padding: 20px` | `p-5` |
| 42 | `padding: 24px` | `p-6` |
| 43 | `padding: 32px` | `p-8` |
| 44 | `padding: 40px` | `p-10` |
| 45 | `padding: 48px` | `p-12` |
| 46 | `padding: 20px 30px` | `px-[30px] py-[20px]` |
| 47 | `padding-top: 20px` | `pt-5` |
| 48 | `padding-right: 20px` | `pr-5` |
| 49 | `padding-bottom: 20px` | `pb-5` |
| 50 | `padding-left: 20px` | `pl-5` |
| 51 | `padding-inline: 20px` | `px-5` |
| 52 | `padding-block: 20px` | `py-5` |
| 53 | `margin: 4px` | `m-1` |
| 54 | `margin: 8px` | `m-2` |
| 55 | `margin: 12px` | `m-3` |
| 56 | `margin: 16px` | `m-4` |
| 57 | `margin: 24px` | `m-6` |
| 58 | `margin: 32px` | `m-8` |
| 59 | `margin-top: 16px` | `mt-4` |
| 60 | `margin-right: 16px` | `mr-4` |
| 61 | `margin-bottom: 16px` | `mb-4` |
| 62 | `margin-left: 16px` | `ml-4` |
| 63 | `margin-inline: auto` | `mx-auto` |
| 64 | `margin-inline: 16px` | `mx-4` |
| 65 | `margin-block: 16px` | `my-4` |
| 66 | `gap: 4px` | `gap-1` |
| 67 | `gap: 8px` | `gap-2` |
| 68 | `gap: 12px` | `gap-3` |
| 69 | `gap: 16px` | `gap-4` |
| 70 | `gap: 24px` | `gap-6` |
| 71 | `gap: 32px` | `gap-8` |
| 72 | `row-gap: 16px` | `gap-y-4` |
| 73 | `column-gap: 16px` | `gap-x-4` |
| 74 | `flex-direction: row` | `flex-row` |
| 75 | `flex-direction: column` | `flex-col` |
| 76 | `flex-direction: row-reverse` | `flex-row-reverse` |
| 77 | `flex-direction: column-reverse` | `flex-col-reverse` |
| 78 | `flex-wrap: wrap` | `flex-wrap` |
| 79 | `flex-wrap: nowrap` | `flex-nowrap` |
| 80 | `justify-content: flex-start` | `justify-start` |
| 81 | `justify-content: center` | `justify-center` |
| 82 | `justify-content: flex-end` | `justify-end` |
| 83 | `justify-content: space-between` | `justify-between` |
| 84 | `justify-content: space-around` | `justify-around` |
| 85 | `justify-content: space-evenly` | `justify-evenly` |
| 86 | `align-items: flex-start` | `items-start` |
| 87 | `align-items: center` | `items-center` |
| 88 | `align-items: flex-end` | `items-end` |
| 89 | `align-items: stretch` | `items-stretch` |
| 90 | `align-items: baseline` | `items-baseline` |
| 91 | `align-self: auto` | `self-auto` |
| 92 | `align-self: center` | `self-center` |
| 93 | `align-self: flex-start` | `self-start` |
| 94 | `align-self: flex-end` | `self-end` |
| 95 | `flex: 1` | `flex-1` |
| 96 | `flex-grow: 1` | `grow` |
| 97 | `flex-grow: 0` | `grow-0` |
| 98 | `flex-shrink: 1` | `shrink` |
| 99 | `flex-shrink: 0` | `shrink-0` |
| 100 | `display: grid` | `grid` |
| 101 | `grid-template-columns: repeat(1, 1fr)` | `grid-cols-1` |
| 102 | `grid-template-columns: repeat(2, 1fr)` | `grid-cols-2` |
| 103 | `grid-template-columns: repeat(3, 1fr)` | `grid-cols-3` |
| 104 | `grid-template-columns: repeat(4, 1fr)` | `grid-cols-4` |
| 105 | `grid-template-columns: repeat(6, 1fr)` | `grid-cols-6` |
| 106 | `grid-template-columns: repeat(12, 1fr)` | `grid-cols-12` |
| 107 | `grid-column: span 2` | `col-span-2` |
| 108 | `grid-column: span 3` | `col-span-3` |
| 109 | `grid-column: 1 / -1` | `col-span-full` |
| 110 | `grid-auto-flow: row` | `grid-flow-row` |
| 111 | `grid-auto-flow: column` | `grid-flow-col` |
| 112 | `font-size: 12px` | `text-xs` |
| 113 | `font-size: 14px` | `text-sm` |
| 114 | `font-size: 16px` | `text-base` |
| 115 | `font-size: 18px` | `text-lg` |
| 116 | `font-size: 20px` | `text-xl` |
| 117 | `font-size: 24px` | `text-2xl` |
| 118 | `font-size: 30px` | `text-3xl` |
| 119 | `font-size: 36px` | `text-4xl` |
| 120 | `font-size: 48px` | `text-5xl` |
| 121 | `font-size: 60px` | `text-6xl` |
| 122 | `font-weight: 400` | `font-normal` |
| 123 | `font-weight: 500` | `font-medium` |
| 124 | `font-weight: 600` | `font-semibold` |
| 125 | `font-weight: 700` | `font-bold` |
| 126 | `font-weight: 800` | `font-extrabold` |
| 127 | `font-style: italic` | `italic` |
| 128 | `font-style: normal` | `not-italic` |
| 129 | `text-align: left` | `text-left` |
| 130 | `text-align: center` | `text-center` |
| 131 | `text-align: right` | `text-right` |
| 132 | `line-height: 1` | `leading-none` |
| 133 | `line-height: 1.25` | `leading-tight` |
| 134 | `line-height: 1.5` | `leading-normal` |
| 135 | `line-height: 1.625` | `leading-relaxed` |
| 136 | `letter-spacing: -0.025em` | `tracking-tight` |
| 137 | `letter-spacing: normal` | `tracking-normal` |
| 138 | `letter-spacing: 0.025em` | `tracking-wide` |
| 139 | `text-decoration: underline` | `underline` |
| 140 | `text-decoration: line-through` | `line-through` |
| 141 | `text-transform: uppercase` | `uppercase` |
| 142 | `text-transform: lowercase` | `lowercase` |
| 143 | `text-transform: capitalize` | `capitalize` |
| 144 | `white-space: nowrap` | `whitespace-nowrap` |
| 145 | `overflow: hidden` | `overflow-hidden` |
| 146 | `overflow: auto` | `overflow-auto` |
| 147 | `overflow: scroll` | `overflow-scroll` |
| 148 | `overflow-x: auto` | `overflow-x-auto` |
| 149 | `overflow-y: auto` | `overflow-y-auto` |
| 150 | `text-overflow: ellipsis` | `truncate` |
| 151 | `color: black` | `text-black` |
| 152 | `color: white` | `text-white` |
| 153 | `color: #6366f1` | `text-[#6366f1]` |
| 154 | `background-color: white` | `bg-white` |
| 155 | `background-color: black` | `bg-black` |
| 156 | `background-color: #6366f1` | `bg-[#6366f1]` |
| 157 | `opacity: 0` | `opacity-0` |
| 158 | `opacity: 0.5` | `opacity-50` |
| 159 | `opacity: 0.75` | `opacity-75` |
| 160 | `opacity: 1` | `opacity-100` |
| 161 | `border: 1px solid` | `border` |
| 162 | `border-width: 2px` | `border-2` |
| 163 | `border-top` | `border-t` |
| 164 | `border-right` | `border-r` |
| 165 | `border-bottom` | `border-b` |
| 166 | `border-left` | `border-l` |
| 167 | `border-color: #e5e7eb` | `border-gray-200` |
| 168 | `border-radius: 4px` | `rounded` |
| 169 | `border-radius: 6px` | `rounded-md` |
| 170 | `border-radius: 8px` | `rounded-lg` |
| 171 | `border-radius: 12px` | `rounded-xl` |
| 172 | `border-radius: 16px` | `rounded-2xl` |
| 173 | `border-radius: 9999px` | `rounded-full` |
| 174 | `box-shadow` | `shadow` |
| 175 | `box-shadow: 0 4px 6px ...` | `shadow-md` |
| 176 | `box-shadow: 0 10px 15px ...` | `shadow-lg` |
| 177 | `box-shadow: none` | `shadow-none` |
| 178 | `object-fit: cover` | `object-cover` |
| 179 | `object-fit: contain` | `object-contain` |
| 180 | `object-fit: fill` | `object-fill` |
| 181 | `cursor: pointer` | `cursor-pointer` |
| 182 | `cursor: not-allowed` | `cursor-not-allowed` |
| 183 | `cursor: wait` | `cursor-wait` |
| 184 | `user-select: none` | `select-none` |
| 185 | `pointer-events: none` | `pointer-events-none` |
| 186 | `visibility: hidden` | `invisible` |
| 187 | `visibility: visible` | `visible` |
| 188 | `transition` | `transition` |
| 189 | `transition: color` | `transition-colors` |
| 190 | `transition: opacity` | `transition-opacity` |
| 191 | `transition: transform` | `transition-transform` |
| 192 | `transition-duration: 200ms` | `duration-200` |
| 193 | `transition-timing-function: ease` | `ease-in` |
| 194 | `transition-timing-function: ease-in-out` | `ease-in-out` |
| 195 | `transform: scale(1.05)` | `scale-105` |
| 196 | `transform: rotate(45deg)` | `rotate-45` |
| 197 | `transform: translateY(-4px)` | `-translate-y-1` |
| 198 | `background-size: cover` | `bg-cover` |
| 199 | `background-size: contain` | `bg-contain` |
| 200 | `background-position: center` | `bg-center` |
| 201 | `background-repeat: no-repeat` | `bg-no-repeat` |
| 202 | `aspect-ratio: 16 / 9` | `aspect-video` |
| 203 | `aspect-ratio: 1 / 1` | `aspect-square` |
| 204 | `list-style: none` | `list-none` |
| 205 | `list-style: disc` | `list-disc` |
| 206 | `list-style: decimal` | `list-decimal` |
| 207 | `:hover` | `hover:` |
| 208 | `:focus` | `focus:` |
| 209 | `:focus-visible` | `focus-visible:` |
| 210 | `:active` | `active:` |
| 211 | `:disabled` | `disabled:` |
| 212 | `:checked` | `checked:` |
| 213 | `:invalid` | `invalid:` |
| 214 | `@media` | `sm:`, `md:`, `lg:`, `xl:`, `2xl:` |
| 215 | Dark mode | `dark:` |
| 216 | Parent hover state | `group-hover:` |
| 217 | Sibling state | `peer-*` |
| 218 | Parent based on child | `has-*` |
| 219 | Data attribute state | `data-*` |
| 220 | ARIA state | `aria-*` |
| 221 | CSS `width: 317px` | `w-[317px]` |
| 222 | CSS `height: 450px` | `h-[450px]` |
| 223 | CSS `padding: 20px` | `p-[20px]` |
| 224 | CSS `margin-top: 37px` | `mt-[37px]` |
| 225 | CSS `font-size: 18px` | `text-[18px]` |
| 226 | CSS `background: #123456` | `bg-[#123456]` |
| 227 | CSS `border-radius: 14px` | `rounded-[14px]` |
| 228 | CSS `width: clamp(...)` | `w-[clamp(...)]` |
| 229 | CSS `width: calc(...)` | `w-[calc(...)]` |
| 230 | CSS variable | `var(--variable)` |
| 231 | CSS variable as width | `w-[var(--sidebar-width)]` |
| 232 | `aspect-ratio: 4 / 3` | `aspect-[4/3]` |
| 233 | `content-visibility: auto` | Custom utility: `@utility content-auto` |
| 234 | CSS container query | `@container` |
| 235 | Container breakpoint | `@md:`, `@lg:` |
| 236 | CSS `:root` variable | `:root { --name: value; }` |
| 237 | Tailwind design token | `@theme { --color-primary: ... }` |
| 238 | CSS custom property | `--color-primary: #...` |
| 239 | CSS variable usage | `var(--color-primary)` |
| 240 | Conditional classes | `cn(...)` |
| 241 | Class composition | `clsx(...)` |
| 242 | Tailwind class conflict resolution | `tailwind-merge` |
| 243 | `display: flex; align-items: center; justify-content: center` | `flex items-center justify-center` |
| 244 | `display: flex; justify-content: space-between` | `flex justify-between` |
| 245 | `display: grid; grid-template-columns: repeat(3, 1fr)` | `grid grid-cols-3` |
| 246 | `width: 100%; max-width: 1280px; margin: auto` | `w-full max-w-7xl mx-auto` |
| 247 | `position: absolute; inset: 0` | `absolute inset-0` |
| 248 | `display: flex; flex: 1` | `flex flex-1` |
| 249 | `display: flex; flex-direction: column; gap: 16px` | `flex flex-col gap-4` |
| 250 | `display: grid; gap: 24px` | `grid gap-6` |
```
