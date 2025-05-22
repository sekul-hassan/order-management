## Crate Next App
```jsx
npx create-next-app@lates
```

1. What is your project named? my-app
2. Would you like to use TypeScript? No / Yes
3. Would you like to use ESLint? No / Yes
4. Would you like to use Tailwind CSS? No / Yes
5. Would you like your code inside a `src/` directory? No / Yes
6. Would you like to use App Router? (recommended) No / Yes
7. Would you like to use Turbopack for `next dev`?  No / Yes
8. Would you like to customize the import alias (`@/*` by default)? No / Yes
9. What import alias would you like configured? @/*

``Next.js has in-built support for the "paths" and "baseUrl" options of tsconfig.json and jsconfig.json files.``

### Module Alias in Next.js (Path Aliases)

If you want to simplify your import paths (e.g., import Component from '../../components/Component' ➝ import Component from '@/components/Component'), you can set up path aliases. <br>

### Example
``` jsx
{
  "compilerOptions": {
    "baseUrl": ".",
    "paths": {
      "@/*": ["./*"]
    }
  }
}
```
```jsx
import Header from '@/components/Header'
```

### What is an "Alias" (in programming)?

<b>What is an "Alias" (in programming)?<b>

```jsx
alias gs="git status" // git alisa
import Header from '@/components/Header';// path alias
SELECT name AS employee_name FROM employees;// SQL alisa
import { Component as MyComponent } from 'library'; // Js Library alias
```

```jsx
npm run dev // run the development server
```
### Set up ESLint

```jsx
{
  "scripts": {
    "lint": "next lint"
  }
}
```