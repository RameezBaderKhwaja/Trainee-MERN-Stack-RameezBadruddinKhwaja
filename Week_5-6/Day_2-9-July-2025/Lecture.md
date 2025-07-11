# Introduction

```bash
npx create-react-app my-app
cd my-app
npm start
````

Folder structure includes `src/`, `public/`, `App.js`, and `index.js`.

## Creating a React Application

start the app with Create React App and render the `App` component in `index.js`.

## Components & Templates

Components are reusable parts of the UI. Templates use HTML tags like `<div>` and `<h1>`.

```js
function Header() {
  return <h1>My App</h1>;
}
```

# Dynamic Values in Templates

Use `{}` to insert JavaScript values in JSX.

```js
const name = 'Net Ninja';
<h1>Hello, {name}!</h1>;
```

# Multiple Components

Use different files for components and include them in `App.js`.

```js
import Navbar from './Navbar';
import Home from './Home';

function App() {
  return (
    <>
      <Navbar />
      <Home />
    </>
  );
}
```

# Adding Styles

Apply CSS via class names or inline styles:

```js
<h1 style={{ color: 'blue' }}>Hello</h1>;
```

# Click Events

Attach event handlers like `onClick` to elements.

```js
<button onClick={() => alert('Clicked!')}>Click me</button>;
```

# Using State (useState)

Manage data inside components that can change.

```js
const [count, setCount] = useState(0);
```

# Intro to React Dev Tools

Use a browser extension to inspect components, props, and state.

# Outputting Lists

Show lists using `.map()` and assign a `key` to each item.

```js
numbers.map(n => <li key={n}>{n}</li>);
```

# Props

Pass information into components.

```js
<Greeting name="Shaun" />;
```

# Reusing Components

Use the same component with different props to reuse it.

# Functions as Props

Give child components functions from the parent to use.

# useEffect Hook (Basics)

Run code after the component renders.

```js
useEffect(() => {
  console.log('Mounted');
}, []);
```

# useEffect Dependencies

Limit updates by including dependencies.

```js
useEffect(() => {
  console.log(count);
}, [count]);
```

# Using JSON Server

Set up a mock REST API for development.

# Fetching Data with useEffect

Load data when the component first shows.

```js
useEffect(() => {
  fetch('/blogs')
    .then(res => res.json())
    .then(data => setBlogs(data));
}, []);
```

# Conditional Loading Message

Show messages while data is loading.

```js
{isLoading ? 'Loading...' : <BlogList blogs={blogs} />}
```

# Handling Fetch Errors

Catch errors during fetch and show a message.

```js
fetch('/blogs')
  .then(res => res.json())
  .then(setBlogs)
  .catch(err => setError(err.message));
```

# Making a Custom Hook

Move shared logic into a reusable hook.

```js
function useFetch(url) {
  const [data, setData] = useState(null);
  useEffect(() => {
    fetch(url)
      .then(r => r.json())
      .then(setData);
  }, [url]);
  return data;
}
```

# The React Router

Set up routes for different components.

```js
<BrowserRouter>
  <Routes>
    <Route path="/" element={<Home />} />
  </Routes>
</BrowserRouter>
```

# Exact Match Routes

Ensure each route only matches the exact path.

```js
<Route path="/" element={<Home />} />
```

# Router Links

Navigate between pages using `<Link>` instead of `<a>`.

```js
<Link to="/create">Create Blog</Link>;
```

# useEffect Cleanup

Clean up side effects (like timers) on unmount.

```js
useEffect(() => {
  const timer = setTimeout(() => {}, 1000);
  return () => clearTimeout(timer);
}, []);
```

# Route Parameters

Get dynamic parts of the URL.

```js
const { id } = useParams();
```

# Reusing Custom Hooks

Use the same custom hook in different parts of your app.

```js
const blogs = useFetch('/blogs');
```

# Controlled Inputs (forms)

Link form fields to state variables.

```js
<input value={title} onChange={e => setTitle(e.target.value)} />;
```

# Submit Events

Handle form submission and prevent default reload.

```js
function handleSubmit(e) {
  e.preventDefault();
}
```

# Making a POST Request

Send new data to the server.

```js
fetch('/blogs', {
  method: 'POST',
  headers: { 'Content-Type': 'application/json' },
  body: JSON.stringify(blog),
});
```

# Programmatic Redirects

Change routes after an action using `useNavigate()`.

```js
const navigate = useNavigate();
navigate('/');
```

# Deleting Blogs

Remove items by calling DELETE on the server.

```js
fetch(`/blogs/${id}`, { method: 'DELETE' });
```

# 404 Pages & Next Steps

Show a NotFound page when no routes match:

```js
<Route path="*" element={<NotFound />} />;
```

