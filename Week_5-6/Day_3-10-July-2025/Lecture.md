# Lifecycle of Reactive Effects

- Effects in React run after rendering and can clean up before next run.
- Useful for syncing with external systems (e.g., APIs, subscriptions).
- Use `useEffect(() => { setup; return cleanup }, [dependencies])`.
- Avoid using effects for rendering logic or user events.
- Use event handlers for actions triggered by user.
- Always include all dependencies used inside the effect.

# Rendering Lists and Keys

- Use `.map()` to render arrays:
  ```js
  items.map(item => <li key={item.id}>{item.name}</li>);
``

* Always use a unique, stable `key` (like `item.id`).
* Avoid using array indexes or random values as keys.
* `key` helps React track, add, remove, or reorder items efficiently.

# Core Hooks Summary

# useState

* For state management in components.
* Returns `[value, setValue]`.

# useEffect

* Runs after render.
* Use for side effects like fetching data or subscribing to services.

# useMemo

* Caches expensive calculations.

  ```js
  const result = useMemo(() => expensiveFn(a, b), [a, b]);
  ```

# useCallback

* Caches function references to prevent unnecessary re-renders.

  ```js
  const handleClick = useCallback(() => { ... }, [deps]);
  ```

# useRef

* Stores mutable value that doesn't trigger re-render.
* Commonly used for DOM refs or timers.

# Reusing Logic with Custom Hooks

* Custom hooks start with `use` and use other hooks inside.
* Example:

  ```js
  function useOnlineStatus() {
    const [isOnline, setIsOnline] = useState(true);
    useEffect(() => {
      const online = () => setIsOnline(true);
      const offline = () => setIsOnline(false);
      window.addEventListener('online', online);
      window.addEventListener('offline', offline);
      return () => {
        window.removeEventListener('online', online);
        window.removeEventListener('offline', offline);
      };
    }, []);
    return isOnline;
  }
  ```
* Custom hooks improve reusability and keep components clean.
* Use when logic is reused or separated from rendering.

# React Router v6

# Setup

* Install: `npm add react-router-dom@6`
* Wrap app in `<BrowserRouter>`
* Use `<Routes>` instead of `<Switch>`
* Use `element` prop in `<Route>`

# Navigation

* Use `<Link>` or `<NavLink>` to navigate.
* Use `useNavigate()` for programmatic navigation.

  ```js
  const navigate = useNavigate();
  navigate("/home", { state: { user: "test" } });
  ```

# Redirection

* Use `<Navigate to="/path" />`
* Add `replace` for history overwrite

# Nested Routes

* Use nested `<Route>` inside a parent `<Route>`
* Use `<Outlet />` in parent to render child content

# URL Params and State

* Use `:id` in path to define dynamic segments
* Get params with `useParams()`
* Get navigation state with `useLocation()`



```