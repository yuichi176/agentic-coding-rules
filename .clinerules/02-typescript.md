# TypeScript Rules

These rules define best practices and required conventions for TypeScript development in this project. These rules are mandatory for all TypeScript code in this repository.  

## 1. Type Annotations

- All exported functions, variables, and components **must** have explicit type annotations.
- Avoid using `any` unless absolutely necessary and justified with a comment.
- Use `unknown` instead of `any` when the type is not known at compile time.

## 2. Interfaces and Types

- Prefer `interface` over `type` for object shapes and public APIs.
- Use `type` for unions, intersections, and utility types.
- Extend interfaces for shared structures instead of duplicating properties.

## 3. Strictness

- The project must enable strict mode in `tsconfig.json`:
```json
{
    "compilerOptions": {
        "strict": true
    }
}
```
- No disabling of strict options unless discussed and documented.

## 4. Utility Types

- Use built-in utility types (`Partial`, `Pick`, `Omit`, `Record`, etc.) for type transformations.
- Prefer `Readonly` and `ReadonlyArray` for immutable data structures.

## 5. Enum Usage

- Avoid using `enum` unless interoperability with other systems or libraries requires it.
- Prefer union string literal types for simple cases:
```typescript
type ButtonVariant = 'primary' | 'secondary' | 'danger';
```

## 6. Type Inference

- Leverage TypeScript's type inference for local variables where the type is obvious.
- For function parameters and return types, always specify types explicitly.

## 7. Third-Party Types

- Always install and use type definitions for third-party libraries (`@types/*`).
- Do not use untyped libraries unless absolutely necessary and with team approval.

## 8. File Naming and Structure

- Use `.ts` for TypeScript files and `.tsx` for files containing JSX/TSX.
- File and folder names should be in kebab-case.
- Group types and interfaces in a dedicated `types/` directory if shared across modules.

## 9. Error Handling

- Always handle possible `null` and `undefined` values explicitly.
- Use `Optional Chaining (?.)` and `Nullish Coalescing (??)` where appropriate.

## 10. Linting and Formatting

- Follow the project's ESLint and Prettier configurations.
- No unused variables or imports.
- No implicit `any`.
