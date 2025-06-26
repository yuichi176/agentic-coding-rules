# Vue Rules

These rules define best practices and conventions for Vue development in this project. These rules are mandatory for all Vue code in this repository.

## 1. Component Structure

- Use the Composition API for new components. Prefer `<script setup>` syntax for simplicity and clarity.
- Each component should have a single responsibility and be as modular as possible.

## 2. State Management

- Use the Vue `ref` and `reactive` APIs for local state within components.
- For global state, use [Pinia](https://pinia.vuejs.org/) as the state management library.
- Avoid prop drilling by using provide/inject or global state where appropriate.

## 3. Props and Types

- Define prop types and default values using the `defineProps` and `withDefaults` macros in `<script setup>`.
- All props must be explicitly typed using TypeScript.
- Use default values for optional props where appropriate.

## 4. Side Effects

- Use the `watch` and `watchEffect` APIs for side effects and reactive logic.
- Clean up effects when necessary to prevent memory leaks (e.g., using `onUnmounted`).
- Avoid unnecessary watchers or complex dependency arrays.

## 5. Performance Optimization

- Use computed properties for derived state to avoid unnecessary recalculations.
- Use the `defineAsyncComponent` API for code-splitting and lazy loading large components.
- Split large components into smaller, reusable components.

## 6. Templates and Styling

- Use single-file components (`.vue` files) with `<template>`, `<script setup>`, and `<style>` sections.
- Use TailwindCSS utility classes for styling.
- Use [clsx](https://github.com/lukeed/clsx) or similar utilities for conditional class names in templates.

## 7. File and Folder Structure

- Name files and folders in kebab-case.
- Place each component in its own folder with related files (component, styles, tests).
- Group shared components in a `components/` directory.

## 8. Accessibility

- Ensure all interactive elements are accessible (e.g., proper roles, aria attributes).
- Use semantic HTML wherever possible in templates.

## 9. Linting and Formatting

- Follow the project's ESLint and Prettier configurations.
- No unused variables, imports, or props.
- Avoid inline styles unless absolutely necessary.
