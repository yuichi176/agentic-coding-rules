# Project Setup Workflow

## Purpose

Automate the initialization of a new web project with the following requirements:

- **Environment**: Node.js, pnpm
- **Tech Stack**: React, Vite, TypeScript, Vitest, React Testing Library
- **Linter**: ESLint, Prettier
- **Additional Tools**: Husky, lint-staged

## Steps

### 1. Initialize Project

**Action**: Create a new project directory and initialize with Vite (React + TypeScript template).

```bash
pnpm create vite@latest [project-name] -- --template react-ts
cd [project-name]
```

## 2. Install Dependencies

**Action**: Install required dependencies for the tech stack.

```bash
pnpm install
pnpm add -D vitest @testing-library/react @testing-library/jest-dom @testing-library/user-event
```

## 3. Set Up Linter and Formatter

**Action**: Install and configure ESLint and Prettier.

```bash
pnpm add -D eslint prettier eslint-config-prettier eslint-plugin-react-hooks
```

**Action**: Create `eslint.config.js` and `.prettierrc` files with recommended settings.

Use the following .prettierrc configuration:

```json
{
  "printWidth": 100,
  "semi": false,
  "singleQuote": true,
  "tabWidth": 2,
  "bracketSpacing": true,
  "endOfLine": "auto"
}
```

## 4. Add Additional Scripts

**Action**: Add scripts for testing, building, and linting in `package.json`:

```json
"scripts": {
    "dev": "vite",
    "build": "vite build",
    "preview": "vite preview",
    "test": "vitest run",
    "test:update:snapshot": "vitest run -u",
    "lint:typeCheck": "tsc --noEmit",
    "lint:eslint": "eslint 'src/**/*.{ts,tsx}'",
    "lint:ts": "pnpm run lint:typeCheck && pnpm run lint:eslint --fix",
    "format": "prettier 'src/**/*.{ts,tsx,css}' --write",
}
```

## 5. Set Up Husky and lint-staged

**Action**: Install Husky and lint-staged.

```bash
pnpm add -D husky lint-staged
pnpm exec husky init
```

**Action**: Add scripts for lint-staged in `package.json`:

```json
{
  "scripts": {
    "pre-commit": "lint-staged"
  },
  "lint-staged": {
    "*.{ts,tsx}": ["pnpm run lint:ts", "pnpm run format"]
  }
}
```

**Action**: Set up Husky pre-commit hook for lint-staged.

```bash
echo "pnpm run pre-commit" > .husky/pre-commit
```

## 6. Add README.md

**Action**: Create a README.md file in the project root with the following template:

```markdown
# App Name

## Overview
App description.

## Environment Requirements
- Node.js (>= 22.16.x)
- pnpm (>=10.12.x)

## Technology Stack
- React (19.1.0)
- Vite (6.3.5)
- TypeScript (>=5.8.3 <5.9.0)

## Install & Run
1. Install Node.js and pnpm if not already installed.
2. Install dependencies:
```bash
pnpm install
```
3. Set up environment variables:

Copy the `.env.local.example` file to `.env.local` and modify it as needed. If you are running an API server locally, you might set:
```env
VITE_API_BASE_URL=http://localhost:8000
```

4. Start the development server with the API server:
```bash
pnpm run dev:withApiServer
```
5. Open your browser and navigate to `http://localhost:5173` to view the application.
```
