# TypeScript Master Roadmap (2026)

> Goal: Become a **Job-Ready Full Stack TypeScript Developer** using
> **React, Node.js, Express, Prisma, PostgreSQL**.

------------------------------------------------------------------------

# Phase 1 --- TypeScript Fundamentals

-   What is TypeScript
-   Why TypeScript
-   How TypeScript Works
-   TypeScript Compiler
-   Installing TypeScript
-   `tsconfig.json`
-   Compile TypeScript
-   Run TypeScript (`tsx`, `ts-node`)
-   Variables (`let`, `const`)
-   Type Annotation
-   Type Inference
-   Basic Types
-   `any`
-   `unknown`
-   `never`
-   `void`

**Outcome** - Write TypeScript files - Compile and run projects -
Understand type errors

------------------------------------------------------------------------

# Phase 2 --- Type System

## Primitive Types

-   string
-   number
-   boolean
-   bigint
-   symbol
-   null
-   undefined

## Reference Types

-   Array
-   Tuple
-   Object
-   Readonly
-   Function
-   Date

## Other Types

-   Literal Types
-   Union Types
-   Intersection Types
-   Type Alias
-   Interface
-   Type vs Interface
-   Enum (Numeric, String, Const)

## Operators

-   `typeof`
-   `keyof`
-   `in`
-   `instanceof`

------------------------------------------------------------------------

# Phase 3 --- Functions

-   Function Types
-   Arrow Functions
-   Named Functions
-   Optional Parameters
-   Default Parameters
-   Rest Parameters
-   Function Overloading
-   Return Types
-   `void`
-   `never`
-   Callbacks
-   Async Functions
-   Promise
-   Generic Functions

**Real-world** - Controllers - Services - Middleware - Helper Functions

------------------------------------------------------------------------

# Phase 4 --- Objects & OOP

## Object Types

-   Nested Objects
-   Optional Properties
-   Readonly Properties
-   Index Signatures

## Classes

-   Class
-   Constructor
-   Properties
-   Methods
-   Access Modifiers
-   public
-   private
-   protected
-   readonly

## OOP

-   Inheritance
-   `extends`
-   `super`
-   Abstract Classes
-   Interfaces (`implements`)
-   Getter / Setter
-   Static Members

------------------------------------------------------------------------

# Phase 5 --- Advanced Types

-   Type Narrowing
-   Type Guards
-   Type Assertions
-   Non-null Assertion (`!`)
-   Optional Chaining (`?.`)
-   Nullish Coalescing (`??`)
-   Discriminated Unions
-   Mapped Types
-   Conditional Types
-   Indexed Access Types
-   Template Literal Types

------------------------------------------------------------------------

# Phase 6 --- Generics

-   Generic Functions
-   Generic Interfaces
-   Generic Classes
-   Generic Types
-   Constraints
-   Default Generics
-   Multiple Generics

## Real-world

-   APIResponse`<T>`{=html}
-   Pagination`<T>`{=html}
-   Repository`<T>`{=html}
-   Cache`<T>`{=html}
-   Result`<T>`{=html}

------------------------------------------------------------------------

# Phase 7 --- Modules & Project Setup

-   Import / Export
-   Default Export
-   Named Export
-   Path Aliases
-   Module Resolution
-   ES Modules
-   CommonJS

## Type Definitions

-   `@types`
-   `.d.ts`

## tsconfig

-   strict
-   noImplicitAny
-   target
-   module
-   rootDir
-   outDir
-   baseUrl

------------------------------------------------------------------------

# Phase 8 --- Backend TypeScript

## Folder Structure

``` text
src/
 ├── controllers/
 ├── services/
 ├── routes/
 ├── middlewares/
 ├── helpers/
 ├── types/
 ├── interfaces/
 ├── utils/
 └── config/
```

## Topics

-   Express Types
-   Request / Response / NextFunction
-   Middleware Types
-   Error Types
-   JWT Types
-   Environment Variables
-   Prisma Types
-   Zod Types
-   Async Handler
-   Custom Error
-   Global Error Handler
-   Repository Pattern
-   Service Layer
-   DTO
-   API Response Types
-   Validation Types

## Advanced

-   Declaration Merging
-   Express Request Extension (`req.user`)
-   Global Types
-   Namespaces
-   Module Augmentation

## Real-world

-   Pagination
-   Filtering
-   Sorting
-   Generic Services
-   Response Builders
-   Error Builders

------------------------------------------------------------------------

# Phase 9 --- React TypeScript

-   Component Props
-   Children
-   React.FC
-   useState
-   useEffect
-   useMemo
-   useRef
-   useContext
-   useReducer

## Events

-   ChangeEvent
-   MouseEvent
-   KeyboardEvent
-   FormEvent

## Forms

-   Input
-   Select
-   Textarea

## API

-   Axios Types
-   React Query Types
-   Mutations
-   Queries
-   Error Types

## Routing

-   React Router Types

## Context API

-   Providers
-   Reducers

## Custom Hooks

-   useAuth()
-   useUser()
-   usePost()

------------------------------------------------------------------------

# Phase 10 --- Production-Level TypeScript

## Utility Types

-   Readonly
-   ReadonlyArray
-   Record
-   Pick
-   Omit
-   Exclude
-   Extract
-   Partial
-   Required
-   ReturnType
-   Parameters
-   Awaited
-   InstanceType

## Advanced

-   infer
-   Conditional Types
-   Recursive Types
-   Mapped Types

## Design Patterns

-   Repository
-   Factory
-   Singleton
-   Dependency Injection

## Error Handling

-   Typed Errors
-   Validation Errors
-   API Errors

## Quality

-   Strict Mode
-   ESLint
-   Prettier
-   Best Practices

------------------------------------------------------------------------

# Extra Topics

-   Declaration Files
-   Module Augmentation
-   Namespaces
-   Decorators
-   Metadata
-   Reflect
-   ts-node
-   tsx
-   swc
-   esbuild

------------------------------------------------------------------------

# Full-Stack Topics

-   DTO
-   API Response
-   Axios Generics
-   React Query Generics
-   Prisma Types
-   Express Types
-   JWT Payload Types
-   Environment Types
-   Request User Types
-   Pagination Types

------------------------------------------------------------------------

# Recommended Learning Order

1.  Introduction
2.  Setup & Compiler
3.  Basic Types
4.  Variables
5.  Arrays
6.  Tuples
7.  Objects
8.  Functions
9.  Type Alias
10. Interface
11. Union
12. Intersection
13. Enum
14. Type Narrowing
15. Type Guards
16. Classes
17. OOP
18. Modules
19. Generics
20. Utility Types
21. Advanced Types
22. Declaration Files
23. tsconfig
24. Backend TypeScript
25. React TypeScript
26. Production Patterns
27. Interview Preparation
28. Best Practices
29. Hands-on Mini Projects
30. Real Company Architecture
