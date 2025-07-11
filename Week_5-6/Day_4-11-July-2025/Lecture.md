# Formik Overview

- Formik simplifies form handling in React.
- Manages state, validation, and submission.
- Works with or without libraries like Yup.

# Basic Setup

```bash
npm install formik
````

```jsx
import { Formik, Form, Field, ErrorMessage } from 'formik';

<Formik
  initialValues={{ email: '' }}
  validate={values => {
    const errors = {};
    if (!values.email) errors.email = 'Required';
    return errors;
  }}
  onSubmit={(values) => console.log(values)}
>
  <Form>
    <Field name="email" />
    <ErrorMessage name="email" component="div" />
    <button type="submit">Submit</button>
  </Form>
</Formik>
```

---

# Zustand Overview

* Lightweight state management library for React.
* No context/provider setup needed.
* State is updated and selected via hooks.

# Basic Usage

```js
import { create } from 'zustand';

const useStore = create(set => ({
  count: 0,
  increment: () => set(state => ({ count: state.count + 1 }))
}));
```

# Middleware & Async

```js
import { persist } from 'zustand/middleware';

const useCart = create(
  persist(set => ({
    items: [],
    add: item => set(state => ({ items: [...state.items, item] }))
  }), { name: 'cart' })
);
```

---

# Shadcn UI

* UI component library built with Radix UI and Tailwind CSS.
* Works well with Vite, Next.js, TypeScript.

# Installation (Vite + React + TS)

```bash
npx create-vite
cd project-name
npx shadcn-ui@latest init
```

* Follow CLI prompts to configure paths and styling.
* Add components:

  ```bash
  npx shadcn-ui@latest add button
  ```

# Usage

```tsx
import { Button } from "@/components/ui/button";
<Button>Click Me</Button>
```

# Dark Mode Setup

* Add `theme-provider.tsx` and wrap app in `ThemeProvider`.
* Add `mode-toggle.tsx` for theme switch button.

---

# Styling Methods in React

# Normal CSS

* Create and import a `.css` file.

```jsx
import './App.css';
<div className="box">Hello</div>
```

# Inline Styles

```jsx
<div style={{ backgroundColor: 'blue' }}>Blue Box</div>
```

# CSS Modules

```css
/* custom.module.css */
.title { color: red; }
```

```js
import styles from './custom.module.css';
<div className={styles.title}>Styled Text</div>
```

```
