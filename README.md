# EXP 10 – React Strict Mode

**NAME:** Nithya T  
**REG NO:** 23050010123

## Aim

To create a React application using Strict Mode and understand how it helps identify potential problems and unexpected side effects during development.

## Objectives

- To understand React Strict Mode.
- To enable Strict Mode in a React application.
- To observe the additional development-time checks.
- To understand the use of useEffect() and cleanup functions.

## Program

### Step 1: Create a React Project

```bash
npm create vite@latest react-strict-mode
cd react-strict-mode
npm install
npm run dev
```

Select React as the framework and JavaScript as the variant.

### Step 2: main.jsx

```jsx
import { StrictMode } from "react";
import { createRoot } from "react-dom/client";
import App from "./App.jsx";

createRoot(document.getElementById("root")).render(
  <StrictMode>
    <App />
  </StrictMode>
);
```

### Step 3: App.jsx

```jsx
import { useEffect, useState } from "react";

function App() {
  const [count, setCount] = useState(0);

  useEffect(() => {
    console.log("Effect started");

    return () => {
      console.log("Effect cleanup");
    };
  }, []);

  return (
    <div>
      <h1>React Strict Mode</h1>

      <h2>Count: {count}</h2>

      <button onClick={() => setCount(count + 1)}>
        Increase
      </button>
    </div>
  );
}

export default App;
```

## Output

### 1. React Strict Mode Application

<img width="1228" height="667" alt="image" src="https://github.com/user-attachments/assets/f0e2c20e-b856-40ad-8cff-31178dfcafb5" />

### 2. Browser Console Output

<img width="1137" height="172" alt="image" src="https://github.com/user-attachments/assets/253a3db4-77c0-4375-aabd-db7a298618c2" />


## Result

Thus, the React application was successfully executed using Strict Mode. Its development-time checks and the use of useEffect() cleanup were studied.
