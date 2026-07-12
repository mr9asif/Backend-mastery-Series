# 🚀 NPM Mastery Roadmap (Senior Backend Engineer Level)

> **Goal:** Master **npm** from beginner to senior level by understanding not only **how** to use it, but also **why**, **when**, and **how it works internally**.

---

# 📚 Table of Contents

- Chapter 01 - JavaScript Ecosystem & npm Fundamentals
- Chapter 02 - npm CLI Commands
- Chapter 03 - package.json Deep Dive
- Chapter 04 - package-lock.json Deep Dive
- Chapter 05 - node_modules Deep Dive
- Chapter 06 - Dependency Management
- Chapter 07 - Semantic Versioning (SemVer)
- Chapter 08 - npm Scripts
- Chapter 09 - npm Cache
- Chapter 10 - npm Configuration (.npmrc)
- Chapter 11 - npm Registry
- Chapter 12 - npx
- Chapter 13 - npm Security
- Chapter 14 - Real Company Workflow
- Chapter 15 - npm Best Practices
- Chapter 16 - Interview Preparation
- Chapter 17 - Hands-on Practice Projects

---

# Chapter 01 — JavaScript Ecosystem & npm Fundamentals

## Goal

Understand why npm exists before learning how to use it.

### Topics

- What is JavaScript Ecosystem?
- What is Node.js?
- Runtime vs Package Manager
- What is npm?
- What is a Package?
- What is a Module?
- What is a Package Manager?
- npm Registry
- Local vs Global Packages
- npm Architecture
- npm Installation
- How npm works internally
- What happens after running `npm install`
- npm CLI Overview
- npm Folder Structure

### Outcome

After this chapter you should be able to explain exactly why npm exists.

---

# Chapter 02 — npm CLI Commands

## Basic Commands

```bash
npm init
npm install
npm uninstall
npm update
npm list
npm outdated
npm version
npm audit
npm doctor
npm cache
npm config
npm login
npm logout
npm whoami
npm publish
npm root
npm prefix
```

## Topics

- Initialization
- Installing Packages
- Removing Packages
- Updating Packages
- Listing Packages
- Searching Packages
- Auditing Packages
- Version Management
- Publishing Packages

### Outcome

Become comfortable using npm from the command line.

---

# Chapter 03 — package.json Deep Dive

## Topics

### Project Metadata

- name
- version
- description
- author
- keywords
- homepage
- repository
- bugs
- license

### Runtime Configuration

- type
- main
- exports
- files

### Dependency Management

- dependencies
- devDependencies
- peerDependencies
- optionalDependencies
- bundledDependencies

### Scripts

- scripts
- pre/post scripts
- lifecycle scripts

### Engine Requirements

- engines
- packageManager

### Publishing

- private
- publishConfig

### Outcome

Master every important field inside package.json.

---

# Chapter 04 — package-lock.json

## Topics

- Why Lock File Exists
- Deterministic Installation
- Dependency Tree
- Version Resolution
- Integrity Hash
- Reproducible Builds
- Git Best Practices
- Delete vs Keep
- Lock File Conflicts
- npm install vs npm ci

### Outcome

Understand why lock files are critical in production.

---

# Chapter 05 — node_modules Deep Dive

## Topics

- Folder Structure
- Dependency Tree
- Nested Dependencies
- Flat Dependencies
- Hoisting
- Binary Files
- .bin Folder
- Symlinks
- Package Resolution
- Disk Usage
- Why node_modules is huge
- Why node_modules isn't committed to Git

### Outcome

Understand exactly how Node resolves packages.

---

# Chapter 06 — Dependency Management

## Types of Dependencies

- dependencies
- devDependencies
- peerDependencies
- optionalDependencies
- bundledDependencies

## Topics

- Local Installation
- Global Installation
- Version Pinning
- Updating Packages
- Removing Packages
- Package Deduplication

### Outcome

Know exactly when to use each dependency type.

---

# Chapter 07 — Semantic Versioning (SemVer)

## Topics

- Major
- Minor
- Patch

### Version Operators

```
^

~

>

<

>=

<=

latest

next

*
```

### Topics

- Version Ranges
- Breaking Changes
- Upgrade Strategy
- Dependency Compatibility

### Outcome

Read and manage package versions confidently.

---

# Chapter 08 — npm Scripts

## Topics

- scripts
- npm run
- pre scripts
- post scripts
- lifecycle scripts
- Environment Variables
- Cross Platform Scripts
- Script Chaining
- Custom Scripts

### Common Scripts

```json
{
  "dev": "...",
  "build": "...",
  "start": "...",
  "lint": "...",
  "test": "...",
  "format": "...",
  "prepare": "...",
  "seed": "...",
  "generate": "..."
}
```

### Outcome

Automate development workflow like a professional.

---

# Chapter 09 — npm Cache

## Topics

- What is Cache?
- Cache Directory
- npm cache clean
- npm cache verify
- Cache Performance
- Cache Problems

### Outcome

Understand caching and troubleshooting.

---

# Chapter 10 — npm Configuration (.npmrc)

## Topics

- Local Config
- User Config
- Global Config
- Project Config
- Registry Configuration
- Authentication
- Proxy
- SSL
- Tokens

### Files

```
.npmrc
```

### Outcome

Configure npm for different environments.

---

# Chapter 11 — npm Registry

## Topics

- What is Registry?
- npm Registry Architecture
- Package Metadata
- Tarballs
- Publishing Flow
- Installing Flow
- Scoped Packages
- Private Registry
- Organization Packages

### Outcome

Understand where packages come from.

---

# Chapter 12 — npx

## Topics

- npm vs npx
- Temporary Package Execution
- Local Binaries
- Global Binaries
- One-Time Execution

### Common Examples

```bash
npx prisma

npx tsc

npx create-vite

npx create-next-app
```

### Outcome

Know when to use npm and when to use npx.

---

# Chapter 13 — npm Security

## Topics

- npm audit
- Vulnerabilities
- Supply Chain Attacks
- Malicious Packages
- Typosquatting
- Dependency Confusion
- Integrity Verification
- Security Best Practices

### Outcome

Write secure production applications.

---

# Chapter 14 — Real Company Workflow

## Topics

- Team Collaboration
- Git Workflow
- CI/CD
- Docker
- Production Build
- npm ci
- Version Locking
- Release Strategy
- Package Updates

### Outcome

Understand how npm is used in real software companies.

---

# Chapter 15 — npm Best Practices

## Topics

- Project Initialization
- Naming Conventions
- Version Strategy
- Script Organization
- Lock File Policy
- Dependency Policy
- Upgrade Strategy
- Security Checklist
- Performance Tips
- Git Ignore
- Production Installation
- Monorepo Basics

### Outcome

Develop professional npm habits.

---

# Chapter 16 — Interview Preparation

## Beginner Questions

- What is npm?
- What is a package?
- What is node_modules?

## Intermediate Questions

- package.json vs package-lock.json
- dependencies vs devDependencies
- npm vs npx
- npm install vs npm ci

## Advanced Questions

- How npm resolves dependencies
- How Node resolves modules
- Hoisting
- SemVer
- Lock Files
- Peer Dependencies
- npm Registry Architecture

---

# Chapter 17 — Hands-on Practice Projects

## Practice 01

Create your first npm package.

## Practice 02

Build a TypeScript backend project from scratch.

## Practice 03

Create reusable npm scripts.

## Practice 04

Publish a package to npm.

## Practice 05

Debug dependency conflicts.

## Practice 06

Create a CLI tool using npm.

## Practice 07

Analyze node_modules structure.

## Practice 08

Production-ready backend setup using npm.

---

# 🎯 Final Learning Outcome

After completing this roadmap, you will be able to:

- Understand the complete JavaScript package ecosystem.
- Explain how npm works internally.
- Master package.json and package-lock.json.
- Manage dependencies professionally.
- Build efficient development workflows.
- Configure npm for production environments.
- Secure your applications against dependency vulnerabilities.
- Work confidently in real company projects.
- Answer senior-level npm interview questions.
- Use npm like an experienced Backend Engineer.

---

# 📌 Next Roadmaps

- Yarn Mastery
- pnpm Mastery
- Package Manager Comparison (npm vs Yarn vs pnpm)
- Monorepo with Workspaces
- Publishing Professional npm Packages
- Building CLI Tools