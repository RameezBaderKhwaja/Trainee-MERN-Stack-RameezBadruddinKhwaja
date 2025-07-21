# SWR Intro
- React library for client-side data fetching.
- Handles caching, revalidation, performance.
- Based on stale-while-revalidate.

# Setup
- Create project, install `axios` + `swr`.
- Add `fetcher.ts`: export Axios GET request.
- Add `providers.tsx`: wrap app in `SWRConfig` with fetcher.
- Global options: `refreshInterval`, `revalidateIfStale`, etc.

# Custom Hooks
- Create hooks like `useUser`, `useCart`.
- Use `useSWR(endpoint, fetcher)`.

# Dependent Queries
- One hook depends on another.
- Return `null` to delay fetch until data is ready.

# Mutations
- Use `useSWRMutation` for update/create/delete.
- Trigger with `trigger()`.
- Use `onSuccess`, `optimisticData`, `rollbackOnError`.

# Optimistic UI
- Update UI before server confirms.
- Revert on error with `rollbackOnError`.
- Disable buttons during mutation.

# Middlewares
- Wrap fetcher logic (e.g., logging).
- Use with `hook.use(middleware)`.

# Pagination
- Use `pageIndex` state.
- Add to fetch key: `/posts?page=${pageIndex}`.
- Prefetch next page.

# Infinite Scroll
- Use `useSWRInfinite`.
- Provide `getKey()` function.
- Call `setSize(size + 1)` to load more.

---

# React Core

# Components & JSX
- JSX = HTML-like syntax.
- One parent element per component.
- Use `<>...</>` instead of extra `<div>`.

# Props & Context
- Props = data from parent.
- `children` = nested content.
- `key` = unique identifier.
- Context shares data globally.

# State & Effects
- `useState` for data + re-render.
- Controlled form = form bound to state.
- `useEffect` for side effects.

# Rendering
- Uses Virtual DOM.
- Only changed parts update real DOM.
- Avoid bad state logic (infinite loops).

# Common Hooks
- `useState` – local state.
- `useEffect` – side effects.
- `useRef` – DOM refs.

# Best Practices
- Pure functions: same input = same output.
- Use `StrictMode` to detect issues.
- `createPortal` – render outside DOM tree.
- `Suspense` – loading fallback.
- Error Boundaries – catch render errors.

