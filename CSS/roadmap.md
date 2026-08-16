# CSS Roadmap — Beginner to Advanced

A complete CSS roadmap focused on **frontend development, real-world projects, and interview preparation**.

---

# Phase 1 — CSS Fundamentals

## 1. CSS Basics

- What is CSS?
- CSS syntax
- CSS rules
- Selectors
- Declarations
- Properties
- Values
- CSS comments
- Inline CSS
- Internal CSS
- External CSS
- CSS Cascade

## 2. Selectors

- Universal selector `*`
- Element selector
- Class selector
- ID selector
- Attribute selector
- Grouping selector
- Descendant selector
- Child selector `>`
- Adjacent sibling selector `+`
- General sibling selector `~`
- Pseudo-class
- Pseudo-element

## 3. Specificity

- What is specificity?
- Specificity calculation
- Specificity hierarchy
- Inline styles
- ID specificity
- Class / attribute / pseudo-class specificity
- Element / pseudo-element specificity
- `!important`
- Specificity conflicts
- Source order
- Cascade layers
- CSS Cascade order

---

# Phase 2 — Box Model & Core CSS

## 4. Box Model

- Content
- Padding
- Border
- Margin
- Box model calculation
- `box-sizing`
- `content-box`
- `border-box`
- Margin collapsing

## 5. Width & Height

- `width`
- `height`
- `min-width`
- `max-width`
- `min-height`
- `max-height`
- `auto`
- Percentage-based sizing
- Viewport-based sizing
- Intrinsic sizing
- Extrinsic sizing

## 6. CSS Units

### Absolute Units

- `px`

### Relative Units

- `%`
- `em`
- `rem`
- `vw`
- `vh`
- `vmin`
- `vmax`
- `ch`
- `ex`

### Modern Viewport Units

- `dvh`
- `svh`
- `lvh`
- `dvw`
- `svw`
- `lvw`

## 7. Colors & Backgrounds

### Color Formats

- Named colors
- HEX
- RGB
- RGBA
- HSL
- HSLA
- Modern color functions

### Background Properties

- `background-color`
- `background-image`
- `background-size`
- `background-position`
- `background-repeat`
- `background-attachment`
- `background-origin`
- `background-clip`
- Multiple backgrounds

### Gradients

- Linear gradient
- Radial gradient
- Conic gradient
- Gradient overlays
- Multiple gradients

---

# Phase 3 — Typography

## 8. Text & Fonts

- `font-family`
- `font-size`
- `font-weight`
- `font-style`
- `font-variant`
- `font-stretch`
- `line-height`
- `letter-spacing`
- `word-spacing`
- `text-align`
- `text-align-last`
- `text-indent`
- `text-decoration`
- `text-decoration-line`
- `text-decoration-style`
- `text-decoration-color`
- `text-transform`
- `text-overflow`
- `white-space`
- `word-break`
- `overflow-wrap`
- `hyphens`

## 9. Modern Font Handling

- Web-safe fonts
- Web fonts
- `@font-face`
- Font loading
- Font fallback
- Fallback fonts
- System font stack
- Variable fonts
- Font weight ranges
- Font display
- Font performance

---

# Phase 4 — Display & Positioning

## 10. Display

- `block`
- `inline`
- `inline-block`
- `none`
- `flex`
- `grid`
- `table`
- `table-row`
- `table-cell`
- `contents`
- `flow-root`

## 11. Positioning

### Position Values

- `static`
- `relative`
- `absolute`
- `fixed`
- `sticky`

### Position Properties

- `top`
- `right`
- `bottom`
- `left`
- `inset`
- `inset-block`
- `inset-inline`

### Advanced Positioning Concepts

- Containing block
- Positioning context
- Absolute positioning
- Relative positioning
- Fixed positioning
- Sticky positioning
- Scroll containers
- `z-index`
- Stacking order
- Stacking context

### Interview Focus

- What does `position: relative` do?
- What is an absolutely positioned element relative to?
- `absolute` vs `fixed`
- `fixed` vs `sticky`
- Why does `z-index` sometimes not work?
- What is a stacking context?

---

# Phase 5 — Flexbox ⭐

## 12. Flexbox Fundamentals

- What is Flexbox?
- Flex container
- Flex items
- `display: flex`
- Main axis
- Cross axis
- `flex-direction`
- `flex-wrap`
- `flex-flow`

## 13. Flexbox Alignment

- `justify-content`
- `align-items`
- `align-content`
- `align-self`
- `place-content`
- `place-items`
- `place-self`

## 14. Flex Sizing

- `flex-grow`
- `flex-shrink`
- `flex-basis`
- `flex`
- `gap`
- `row-gap`
- `column-gap`

## 15. Advanced Flexbox

- Flex item sizing algorithm
- Flex basis
- Free space distribution
- Shrinking behavior
- Growing behavior
- `min-width: 0`
- `min-height: 0`
- Nested flex containers
- Equal-height layouts
- Centering layouts
- Common flexbox bugs
- Overflow in flex layouts
- Flexbox debugging

## 16. Flexbox Interview Concepts

- Main axis vs cross axis
- `justify-content` vs `align-items`
- `align-items` vs `align-content`
- `flex-grow` vs `flex-shrink`
- `flex-basis` vs `width`
- `flex: 1` meaning
- Why `min-width: 0` is sometimes required

---

# Phase 6 — CSS Grid ⭐

## 17. Grid Fundamentals

- What is CSS Grid?
- Grid container
- Grid items
- Grid columns
- Grid rows
- Grid tracks
- Grid lines
- `display: grid`
- `grid-template-columns`
- `grid-template-rows`
- `gap`
- `row-gap`
- `column-gap`

## 18. Grid Placement

- `grid-column`
- `grid-column-start`
- `grid-column-end`
- `grid-row`
- `grid-row-start`
- `grid-row-end`
- `grid-area`
- Grid line numbers
- Named grid lines
- Named grid areas

## 19. Grid Sizing

- `fr`
- `auto`
- `minmax()`
- `min-content`
- `max-content`
- `fit-content()`
- `repeat()`

## 20. Responsive Grid

- `auto-fit`
- `auto-fill`
- Auto-placement
- `grid-auto-flow`
- `grid-auto-columns`
- `grid-auto-rows`
- Responsive card grids
- Dynamic columns

## 21. Advanced Grid

- Nested grids
- Grid alignment
- `justify-items`
- `align-items`
- `justify-content`
- `align-content`
- `place-items`
- `place-content`
- Complex dashboard layouts
- Magazine layouts
- Holy Grail layout
- Full-page layouts

## 22. Grid vs Flexbox

- When to use Flexbox
- When to use Grid
- One-dimensional layouts
- Two-dimensional layouts
- Flexbox vs Grid in real projects

---

# Phase 7 — Responsive Design ⭐

## 23. Responsive Fundamentals

- What is responsive design?
- Mobile-first design
- Desktop-first design
- Breakpoints
- Media queries
- `@media`
- `min-width`
- `max-width`
- Orientation queries
- Resolution queries

## 24. Responsive Units

- `%`
- `rem`
- `em`
- `vw`
- `vh`
- `vmin`
- `vmax`
- `dvh`
- `svh`
- `lvh`

## 25. Modern Responsive CSS

- `clamp()`
- `min()`
- `max()`
- `minmax()`
- Container queries
- Fluid typography
- Fluid spacing
- Fluid layouts
- Responsive images
- Responsive typography

## 26. Responsive Images

- Responsive image sizing
- `width: 100%`
- `max-width: 100%`
- `object-fit`
- `object-position`
- `aspect-ratio`
- Image cropping
- Image containers

## 27. Responsive Design Interview Concepts

- Mobile-first vs desktop-first
- How breakpoints work
- `em` vs `rem` in media queries
- Media query vs container query
- Fluid vs fixed layouts
- Responsive vs adaptive design

---

# Phase 8 — Pseudo Classes & Pseudo Elements

## 28. Important Pseudo-classes

- `:hover`
- `:focus`
- `:focus-visible`
- `:focus-within`
- `:active`
- `:visited`
- `:link`
- `:checked`
- `:indeterminate`
- `:disabled`
- `:enabled`
- `:required`
- `:optional`
- `:valid`
- `:invalid`
- `:in-range`
- `:out-of-range`
- `:read-only`
- `:read-write`
- `:placeholder-shown`

## 29. Structural Pseudo-classes

- `:first-child`
- `:last-child`
- `:only-child`
- `:nth-child()`
- `:nth-last-child()`
- `:first-of-type`
- `:last-of-type`
- `:only-of-type`
- `:nth-of-type()`
- `:nth-last-of-type()`
- `:empty`
- `:root`

## 30. Modern Pseudo-classes

- `:not()`
- `:is()`
- `:where()`
- `:has()`

## 31. Pseudo-elements

- `::before`
- `::after`
- `::first-letter`
- `::first-line`
- `::selection`
- `::placeholder`
- `::marker`
- `::backdrop`
- `::file-selector-button`

## 32. Pseudo-class vs Pseudo-element

- What is a pseudo-class?
- What is a pseudo-element?
- Syntax difference
- Practical use cases
- Interview differences

---

# Phase 9 — Advanced CSS

## 33. CSS Variables ⭐

- What are CSS custom properties?
- Custom property syntax
- `--variable`
- `var()`
- Global variables
- Local variables
- Component variables
- Fallback values
- Variable inheritance
- Variable scope
- Dynamic variables
- Theme variables

## 34. CSS Functions

- `calc()`
- `min()`
- `max()`
- `clamp()`
- `minmax()`
- `repeat()`
- `var()`
- `url()`
- `attr()`

## 35. CSS Transitions

- `transition-property`
- `transition-duration`
- `transition-delay`
- `transition-timing-function`
- `transition`
- Linear timing
- Ease timing
- Cubic-bezier
- Step timing functions
- Hover transitions
- Interactive transitions

## 36. CSS Transforms

- `transform`
- `translate()`
- `translateX()`
- `translateY()`
- `translateZ()`
- `scale()`
- `scaleX()`
- `scaleY()`
- `rotate()`
- `rotateX()`
- `rotateY()`
- `rotateZ()`
- `skew()`
- `skewX()`
- `skewY()`
- `transform-origin`
- 2D transforms
- 3D transforms
- Transform stacking

## 37. CSS Animations

- `@keyframes`
- `animation-name`
- `animation-duration`
- `animation-delay`
- `animation-iteration-count`
- `animation-direction`
- `animation-fill-mode`
- `animation-play-state`
- `animation-timing-function`
- `animation`
- Animation timing functions
- Keyframe design
- Infinite animations
- Loading animations
- Entrance animations
- Exit animations

## 38. Animation Performance

- `transform` animations
- `opacity` animations
- Layout-triggering animations
- GPU acceleration basics
- Compositor-friendly animations
- Avoiding expensive animations
- `will-change`
- `prefers-reduced-motion`

---

# Phase 10 — Advanced Visual CSS

## 39. Shadows

- `box-shadow`
- `text-shadow`
- Multiple shadows
- Inset shadows
- Soft shadows
- Layered shadows

## 40. Borders

- Border width
- Border style
- Border color
- Border radius
- Individual borders
- `border-image`
- Border images
- `outline`
- `outline-offset`
- Border vs outline

## 41. Overflow

- `overflow`
- `overflow-x`
- `overflow-y`
- `overflow: visible`
- `overflow: hidden`
- `overflow: auto`
- `overflow: scroll`
- `overflow: clip`
- Scroll containers
- Horizontal scrolling
- Vertical scrolling
- Scroll behavior

## 42. Images

- `object-fit`
- `object-position`
- `aspect-ratio`
- `object-fit: cover`
- `object-fit: contain`
- Image cropping
- Image positioning
- Responsive image containers

## 43. Gradients

- Linear gradients
- Radial gradients
- Conic gradients
- Gradient direction
- Color stops
- Transparent gradients
- Gradient overlays
- Multiple gradients
- Gradient backgrounds

## 44. Filters

- `filter`
- `blur()`
- `brightness()`
- `contrast()`
- `grayscale()`
- `hue-rotate()`
- `invert()`
- `opacity()`
- `saturate()`
- `sepia()`
- `drop-shadow()`

## 45. Clipping & Masking

- `clip-path`
- Circle clipping
- Polygon clipping
- Ellipse clipping
- CSS masks
- `mask-image`
- `mask-size`
- `mask-position`
- CSS shapes

---

# Phase 11 — Modern CSS ⭐⭐⭐

## 46. Modern Selectors

- `:is()`
- `:where()`
- `:has()`
- `:not()`
- Selector nesting
- Selector specificity with modern selectors

## 47. Container Queries

- What are container queries?
- `container-type`
- `container-name`
- `@container`
- Inline-size containers
- Component-level responsiveness
- Container query units
- `cqw`
- `cqh`
- `cqi`
- `cqb`
- `cqmin`
- `cqmax`

## 48. Cascade Layers

- What are cascade layers?
- `@layer`
- Creating layers
- Layer ordering
- Layer specificity
- `!important` and layers
- CSS architecture with layers

## 49. Native CSS Nesting

- Native CSS nesting
- Nested selectors
- Nesting syntax
- Parent selector `&`
- Nesting best practices
- Nesting vs preprocessor nesting

## 50. Modern Color

- `oklch()`
- `oklab()`
- `color-mix()`
- Color interpolation
- Color spaces
- Modern color systems
- Accessible color systems

## 51. Logical Properties

- `margin-inline`
- `margin-inline-start`
- `margin-inline-end`
- `margin-block`
- `margin-block-start`
- `margin-block-end`
- `padding-inline`
- `padding-block`
- `inset-inline`
- `inset-block`
- Logical width
- Logical height
- Writing modes

---

# Phase 12 — CSS Architecture

## 52. CSS Organization

- Component-based CSS
- Global CSS
- Local CSS
- Utility classes
- CSS Modules
- Scoped CSS
- CSS architecture
- Organizing large CSS codebases
- Avoiding CSS conflicts

## 53. Naming Conventions

- Semantic naming
- Component naming
- BEM
- Block
- Element
- Modifier
- Naming conventions
- Avoiding overly specific selectors
- Avoiding unclear class names

## 54. Design Systems

- What is a design system?
- Design tokens
- Color tokens
- Spacing tokens
- Typography tokens
- Radius tokens
- Shadow tokens
- Breakpoint tokens
- Component tokens
- Semantic tokens

## 55. Theming

- Light theme
- Dark theme
- CSS variables
- Theme switching
- System theme detection
- `prefers-color-scheme`
- Component-level themes
- Theme architecture

---

# Phase 13 — CSS Layout Mastery

> Focus on understanding **how to think about layouts**, not just memorizing properties.

## 56. Navigation Layouts

- Navbar
- Responsive navbar
- Mobile navigation
- Sidebar navigation
- Dropdown navigation
- Mega menu

## 57. Application Layouts

- Dashboard
- Admin panel
- Sidebar + content
- Header + sidebar + content
- Responsive dashboard
- Multi-column layouts

## 58. Content Layouts

- Hero section
- Card grid
- Blog layout
- Article layout
- Magazine layout
- Portfolio layout
- Pricing section
- Feature section

## 59. UI Components

- Modal
- Dropdown
- Tooltip
- Toast
- Tabs
- Accordion
- Breadcrumb
- Pagination
- Badge
- Alert
- Skeleton loader
- Loading spinner
- Progress bar

## 60. Form Layouts

- Login form
- Register form
- Contact form
- Search form
- Checkout form
- Responsive forms
- Form validation states

## 61. Real-world Pages

- Landing page
- Authentication page
- Dashboard
- Admin panel
- E-commerce page
- Product page
- Blog
- Portfolio
- Chat UI
- Social media UI
- SaaS application UI

---

# Phase 14 — CSS Performance & Accessibility

## 62. CSS Rendering

- Browser rendering process
- Style calculation
- Layout
- Paint
- Composite
- Rendering pipeline

## 63. Performance

- Reflow
- Repaint
- Composite
- Layout thrashing
- Expensive selectors
- Expensive animations
- CSS optimization
- Reducing unnecessary CSS
- Avoiding excessive nesting
- Efficient animations
- `transform` and `opacity`
- `will-change`

## 64. Accessibility

- Accessible color contrast
- Focus states
- `:focus-visible`
- Keyboard navigation
- Reduced motion
- `prefers-reduced-motion`
- Accessible form states
- Visible interactive states
- Avoiding color-only communication
- Responsive accessibility

---

# Phase 15 — CSS Interview Core Concepts ⭐⭐⭐

## 65. Cascade & Specificity

- What is CSS Cascade?
- What is specificity?
- How is specificity calculated?
- Inline vs ID vs Class vs Element
- What is `!important`?
- What is source order?
- What are cascade layers?
- How does inheritance work?

## 66. Box Model

- What is the CSS Box Model?
- Content vs padding vs border vs margin
- `content-box` vs `border-box`
- Why use `box-sizing: border-box`?
- Margin collapsing

## 67. Display

- `display: block`
- `display: inline`
- `display: inline-block`
- `display: none`
- `display: contents`
- `display: flex`
- `display: grid`

## 68. Visibility

- `display: none`
- `visibility: hidden`
- `opacity: 0`
- Differences between them
- Accessibility implications
- Layout implications

## 69. Positioning

- `static`
- `relative`
- `absolute`
- `fixed`
- `sticky`
- Containing block
- `z-index`
- Stacking context
- Why `z-index` doesn't work

## 70. Flexbox Interview Questions

- What is Flexbox?
- Main axis vs cross axis
- `justify-content` vs `align-items`
- `align-items` vs `align-content`
- `flex-grow` vs `flex-shrink`
- `flex-basis` vs `width`
- What does `flex: 1` mean?
- Why use `min-width: 0`?

## 71. Grid Interview Questions

- What is CSS Grid?
- Grid vs Flexbox
- What is `fr`?
- What is `minmax()`?
- What is `repeat()`?
- `auto-fit` vs `auto-fill`
- What is grid auto-placement?
- Named grid areas

## 72. Units Interview Questions

- `px` vs `%`
- `em` vs `rem`
- `%` vs `vw`
- `vh` vs `dvh`
- `em` vs `rem` in media queries
- When should you use `rem`?
- When should you use `em`?

## 73. Responsive Design Interview Questions

- What is responsive design?
- Mobile-first vs desktop-first
- What are breakpoints?
- What are media queries?
- Media query vs container query
- Fluid vs fixed layouts
- What is fluid typography?
- What is `clamp()`?

## 74. Modern CSS Interview Questions

- What are CSS variables?
- What is `calc()`?
- What is `clamp()`?
- What is `min()`?
- What is `max()`?
- What is `:is()`?
- What is `:where()`?
- What is `:has()`?
- What is CSS nesting?
- What are container queries?
- What are cascade layers?
- What are logical properties?
- What is `oklch()`?
- What is `color-mix()`?

## 75. Animation Interview Questions

- Transition vs animation
- Transform vs position
- What is `@keyframes`?
- What is `animation-fill-mode`?
- What is `animation-direction`?
- What is `prefers-reduced-motion`?
- How do you optimize CSS animations?

## 76. Performance Interview Questions

- What is reflow?
- What is repaint?
- What is compositing?
- Reflow vs repaint
- Repaint vs composite
- Which CSS properties are expensive to animate?
- Why are `transform` and `opacity` preferred for animations?
- What is GPU acceleration?
- What is `will-change`?

---

# Phase 16 — CSS Practice Projects

## Beginner Projects

- [ ] Simple profile card
- [ ] Login form
- [ ] Registration form
- [ ] Product card
- [ ] Pricing card
- [ ] Navigation bar
- [ ] Simple landing page

## Intermediate Projects

- [ ] Responsive navbar
- [ ] Sidebar
- [ ] Dashboard
- [ ] Card grid
- [ ] Pricing section
- [ ] Hero section
- [ ] Blog layout
- [ ] Portfolio page
- [ ] E-commerce product page
- [ ] Admin panel

## Advanced Projects

- [ ] Responsive SaaS landing page
- [ ] Complex dashboard
- [ ] E-commerce website UI
- [ ] Chat application UI
- [ ] Social media UI
- [ ] Admin dashboard
- [ ] Multi-column magazine layout
- [ ] Design system
- [ ] Dark/light theme system
- [ ] Fully responsive application UI

---

# 🎯 Final CSS Mastery Checklist

## Fundamentals

- [ ] CSS Syntax
- [ ] Selectors
- [ ] Cascade
- [ ] Specificity
- [ ] Inheritance
- [ ] Box Model
- [ ] Units
- [ ] Colors
- [ ] Typography

## Layout

- [ ] Display
- [ ] Position
- [ ] Flexbox
- [ ] Grid
- [ ] Responsive Design

## Modern CSS

- [ ] CSS Variables
- [ ] CSS Functions
- [ ] Modern Selectors
- [ ] Container Queries
- [ ] Cascade Layers
- [ ] CSS Nesting
- [ ] Modern Colors
- [ ] Logical Properties

## Visual CSS

- [ ] Shadows
- [ ] Borders
- [ ] Gradients
- [ ] Filters
- [ ] Transforms
- [ ] Transitions
- [ ] Animations
- [ ] Clipping
- [ ] Masking

## Architecture

- [ ] CSS Organization
- [ ] Naming
- [ ] BEM
- [ ] Design Tokens
- [ ] Theming
- [ ] Component-based CSS
- [ ] CSS Modules
- [ ] Utility Classes

## Performance

- [ ] Reflow
- [ ] Repaint
- [ ] Composite
- [ ] Layout performance
- [ ] Animation performance
- [ ] CSS optimization
- [ ] `will-change`
- [ ] GPU acceleration

## Accessibility

- [ ] Focus states
- [ ] Keyboard accessibility
- [ ] Color contrast
- [ ] Reduced motion
- [ ] Accessible forms
- [ ] Responsive accessibility

## Interview

- [ ] Cascade
- [ ] Specificity
- [ ] Box Model
- [ ] `box-sizing`
- [ ] Display
- [ ] Positioning
- [ ] Stacking Context
- [ ] `z-index`
- [ ] Flexbox
- [ ] Grid
- [ ] Responsive Design
- [ ] Units
- [ ] Pseudo-classes
- [ ] Pseudo-elements
- [ ] CSS Variables
- [ ] CSS Functions
- [ ] Container Queries
- [ ] Modern CSS
- [ ] Transitions
- [ ] Animations
- [ ] Performance
- [ ] Accessibility

---

# 🚀 CSS Mastery Goal

By completing this roadmap, you should be able to:

- Build responsive layouts from scratch
- Understand how CSS actually works
- Debug CSS confidently
- Build production-quality interfaces
- Master Flexbox and Grid
- Build complex responsive layouts
- Use modern CSS features
- Create scalable CSS architecture
- Build reusable UI components
- Create light/dark themes
- Optimize CSS performance
- Build accessible interfaces
- Answer common CSS interview questions
- Implement real-world frontend layouts without relying heavily on tutorials

---

# 📌 Learning Method

For every major topic:

1. Learn the concept
2. Understand how it works
3. Write the CSS yourself
4. Build a small example
5. Intentionally break it
6. Debug the problem
7. Explain why it works
8. Use it in a real project
9. Revise the concept
10. Practice interview questions

> **Learn → Understand → Code → Build → Break → Debug → Explain → Revise**

## Final Goal

> **Don't memorize CSS. Understand how CSS works.**
