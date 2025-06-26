# React Rules

These rules define best practices and conventions for React development in this project. These rules are mandatory for all React code in this repository.  

## 1. Component Structure

- Use functional components with hooks. Avoid class components unless there is a strong justification.
- Each component should have a single responsibility.

## 2. State Management

- Use React's built-in hooks (`useState`, `useReducer`, `useContext`) for local state.
- Use [jotai](https://jotai.org/) for global state.
- Avoid prop drilling by using context or global state where appropriate.

## 3. Props and Types

- Define prop types using TypeScript interfaces.
- All props must be explicitly typed.
- Use default values for optional props where appropriate.

## 4. Side Effects

- Use `useEffect` for side effects. Clean up effects when necessary to prevent memory leaks.
- Avoid unnecessary dependencies in effect dependency arrays.

## 5. Performance Optimization

- Use `React.memo` to prevent unnecessary re-renders of pure components.
- Use `useCallback` and `useMemo` to memoize functions and values passed as props.
- Split large components into smaller, reusable components.

## 6. JSX and Styling

- Use JSX syntax in `.tsx` files only.
- Use TailwindCSS utility classes for styling.
- Use `clsx` as composition utilities for conditional class names.

## 7. File and Folder Structure

- Name files and folders in kebab-case.
- Place each component in its own folder with related files (component, styles, tests).
- Group shared components in a `components/` directory.

## 8. Accessibility

- Ensure all interactive elements are accessible (e.g., proper roles, aria attributes).
- Use semantic HTML wherever possible.

## 9. Linting and Formatting

- Follow the project's ESLint and Prettier configurations.
- No unused variables, imports, or props.
- No inline styles unless absolutely necessary.
