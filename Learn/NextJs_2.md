## Next Js and Gatsby Both Frameworks are based on React Js Library.

## Server Components

A Server Component in React is a component that runs only on the server. It never gets sent to the client. It's rendered on the server, and the result (HTML + data) is sent to the browser. <br>
| Feature                                       | Server Component                              |
| --------------------------------------------- | --------------------------------------------- |
| **Rendering**                                 | Done on the server                            |
| **Bundled in client JS?**                     | ❌ No                                          |
| **Access to server-only code (DB, secrets)?** | ✅ Yes                                         |
| **Interactivity (useState, useEffect)?**      | ❌ No                                          |
| **Use case**                                  | Fetch data, render static content efficiently |

### 🚀 Benefits: <br>
**Performance:** Reduces JavaScript sent to the client.

**Security:** Safe access to secrets and server-side resources.

**Scalability:** Offloads heavy rendering from the browser to the server.

### Example

```jsx
import db from '../lib/db'; // Hypothetical database utility

// This is a server component because of the `.server.jsx` file naming convention
export default async function UserList() {
  const users = await db.getUsers(); // Fetching data directly from the server

  return (
    <ul>
      {users.map(user => (
        <li key={user.id}>
          {user.name} ({user.email})
        </li>
      ))}
    </ul>
  );
}
```

## Client Components

A Client Component is rendered on the client (in the browser), and it can use React hooks like useState, useEffect, and interact with browser APIs (e.g. window, localStorage). <br>
| Feature                                       | Client Component                 |
| --------------------------------------------- | -------------------------------- |
| **Rendering**                                 | Done in the browser              |
| **Bundled in client JS?**                     | ✅ Yes                            |
| **Access to server-only code (DB, secrets)?** | ❌ No                             |
| **Interactivity (useState, useEffect)?**      | ✅ Yes                            |
| **Use case**                                  | Forms, buttons, dynamic behavior |

### 🚀 Benefits:
**Dynamic behavior:** Interactivity via hooks and event handlers.

**Direct browser access:** Can use window, document, cookies, etc.

### Example 
```jsx
'use client'; // Required directive to mark this as a Client Component

import { useState } from 'react';

export default function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>Current count: {count}</p>
      <button onClick={() => setCount(count + 1)}>
        Increment
      </button>
    </div>
  );
}
```

| Use Case                               | Component Type   |
| -------------------------------------- | ---------------- |
| Fetching data, no interactivity        | Server Component |
| User input, event handlers, animations | Client Component |
| Static content that changes rarely     | Server Component |
| Forms, modals, buttons, toggles        | Client Component |

### We can use Server Components as the parent of Client Components

By default, layouts and pages are Server Components, which lets you fetch data and render parts of your UI on the server, optionally cache the result, and stream it to the client. When you need interactivity or browser APIs, you can use Client Components to layer in functionality.

### What is hydration?

Hydration is React's process for attaching event handlers to the DOM, to make the static HTML interactive. 

### What is Event Handler?

Event handlers are your own functions that will be triggered in response to interactions like clicking, hovering, focusing form inputs, and so on. 

### On the client (first load)

1. HTML is used to immediately show a fast non-interactive preview of the route to the user.
2. RSC Payload is used to reconcile the Client and Server Component trees.
3. JavaScript is used to hydrate Client Components and make the application interactive.




