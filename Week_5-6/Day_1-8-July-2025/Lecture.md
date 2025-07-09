
# Vite

- Vite is a fast tool to create frontend apps.
- It supports React, Vue, Svelte, and more.
- It uses **esbuild** for speed and **Rollup** for production builds.

### Why use Vite?
- Traditional tools like Webpack are slow on big apps.
- Vite starts fast and reloads quickly when you change code.

### How it works
- Pre-bundles libraries with esbuild.
- Loads only needed code using browser ES modules.
- Uses Rollup to bundle for production.

### Key Features
- Multi-page apps and library mode.
- Fast CSS loading and code splitting.
- Supports TypeScript, Sass, Less.
- Works well in mono repo.

### Create Project

```bash
npm create vite@latest
cd my-project
npm install
npm run dev
```

### Build and Preview

```bash
npm run build
npm run preview
```

---

# NPM

- NPM stands for Node Package Manager.
- It helps install JavaScript libraries like React, Bootstrap, etc.

### Setup
- Comes with Node.js.
- Check version:

```bash
npm -v
```

### Create package.json

```bash
npm init
# or skip questions
npm init -y
```

### Install Packages

```bash
npm install package-name --save
npm install lodash@4.17.3 --save
```

### Dev Dependencies

```bash
npm install gulp --save-dev
```

### Uninstall Packages

```bash
npm uninstall package-name
```

### Install All Packages (from package.json)

```bash
npm install
```

### Global Packages

```bash
npm install nodemon -g
```

### Scripts

```json
"scripts": {
  "start": "node index.js"
}
```

```bash
npm start
```

---

# React

- React is a JavaScript library to build UI.
- Made by Facebook, it uses components and JSX.

### Create App with Vite

```bash
npm create vite@latest
# choose React + TypeScript
cd project-name
npm install
npm run dev
```

### Component Example

```tsx
function Message() {
  return <h1>Hello</h1>;
}
export default Message;
```

### Props Example

```tsx
interface Props {
  text: string;
}
function Greet({ text }: Props) {
  return <p>{text}</p>;
}
```

### useState Example

```tsx
const [count, setCount] = useState(0);

<button onClick={() => setCount(count + 1)}>{count}</button>
```

### Event Handling

```tsx
function handleClick() {
  console.log('Clicked');
}
<button onClick={handleClick}>Click me</button>
```

### Children Prop

```tsx
function Box({ children }: { children: React.ReactNode }) {
  return <div>{children}</div>;
}
```
