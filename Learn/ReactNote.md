## React Note For Unkown
### Suspense

| Feature       | Description                                          |
| ------------- | ---------------------------------------------------- |
| Purpose       | Delay rendering until something is ready (code/data) |
| Works with    | `React.lazy()`, some data libraries, Next.js         |
| fallback prop | UI to show while loading                             |
| Benefit       | Clean, declarative loading states                    |

### Example
```jsx
import React, { Suspense, lazy } from 'react';

const LazyComponent = lazy(() => import('./MyComponent'));

function App() {
  return (
    <div>
      <h1>My App</h1>
      <Suspense fallback={<div>Loading...</div>}>
        <LazyComponent />
      </Suspense>
    </div>
  );
}
```
### 📦 What Can Suspense Be Used With?

✅ React.lazy() – for code-splitting/lazy loading components

✅ Libraries like React Query, Relay, or Next.js App Router that support data fetching with Suspense

## useRef : A Mutable Reference

### Use it for : A Mutable Reference That Survives Renders
### We can change the value without causing the component to re-render.
- **Accessing DOM elements directly** 
- **Storing mutable values that don't trigger**

```jsx
import { useRef } from 'react';

function FocusInput() {
  const inputRef = useRef(null);

  const handleClick = () => {
    inputRef.current.focus();
  };

  return (
    <>
      <input ref={inputRef} />
      <button onClick={handleClick}>Focus</button>
    </>
  );
}
```

```jsx
const countRef = useRef(0);
countRef.current += 1;
console.log(countRef.current); // persists across renders but won't cause re-render
```
## useReducer : 




























