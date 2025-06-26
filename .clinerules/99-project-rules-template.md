# Directoru Structure
```
src
├─ components          # Shared components
├─ hooks               # Shared custom hooks
├─ pages               # Page components
│   └─ _components     # Page-specific components
├─ lib                 # Library functions
├─ routes              # routing configuration
├─ mocks               # Mock data for testing
└─ utils               # Utility functions
```

# Coding Conventions
| Category            | Rule                                                          |
|---------------------|---------------------------------------------------------------|
| Naming              | Use kebab-case for directory names.                           |
| Naming              | Use UpperCamelCase for component names.                       |
| Naming              | Add `Page` as a suffix to page component names.               |
| Naming              | CSS class name follows [BEM](https://getbem.com/).            |
| Directory Structure | Place shared components in `src/components`.                  |
| Directory Structure | Place shared custom hooks in `src/hooks`.                     |
| Directory Structure | Place page components in `src/pages`.                         |
| Directory Structure | Place page-specific components in `src/pages/../_components`. |
