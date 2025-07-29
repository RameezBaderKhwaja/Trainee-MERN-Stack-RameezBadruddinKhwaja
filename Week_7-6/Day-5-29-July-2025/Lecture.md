# TypeScript Notes

# 1. Introduction to TypeScript
TypeScript is a typed superset of JavaScript that compiles to plain JavaScript. It adds static typing, classes, and interfaces.

# Example:
```typescript
let message: string = "Hello, TypeScript!";
console.log(message);
```

# 2. Basic Types
```typescript
Number, String, Boolean, Array, Tuple, Enum, Any, Void, Null, Undefined

let isDone: boolean = true;
let age: number = 25;
let userName: string = "Alice";
let list: number[] = [1, 2, 3];
let tuple: [string, number] = ["hello", 10];
enum Color {Red, Green, Blue}
let c: Color = Color.Green;
let notSure: any = 4;
function warnUser(): void {
    console.log("This is a warning message");
}

```

# 3. Functions
```typescript
Function with types, optional and default parameters

function add(x: number, y: number = 10): number {
    return x + y;
}
console.log(add(5));

```

# 4. Interfaces
```typescript
interface Person {
    firstName: string;
    lastName: string;
}

function greet(person: Person) {
    return "Hello, " + person.firstName + " " + person.lastName;
}

console.log(greet({ firstName: "John", lastName: "Doe" }));
```
# 5. Classes
```typescript
class Animal {
    name: string;
    constructor(name: string) {
        this.name = name;
    }
    move(distanceInMeters: number = 0) {
        console.log(`${this.name} moved ${distanceInMeters}m.`);
    }
}

let dog = new Animal("Dog");
dog.move(10);
```

# 6. Inheritance
```typescript
class Dog extends Animal {
    bark() {
        console.log("Woof! Woof!");
    }
}

let puppy = new Dog("Puppy");
puppy.bark();
puppy.move(5);
```

# 7. Generics
```typescript
function identity<T>(arg: T): T {
    return arg;
}

let output = identity<string>("myString");
console.log(output);
```

# 8. Type Aliases and Union Types
```typescript
type StringOrNumber = string | number;

function printId(id: StringOrNumber) {
    console.log("Your ID is: " + id);
}

printId(101);
printId("202");
```

# 9. Type Assertions
```typescript
let someValue: any = "this is a string";
let strLength: number = (someValue as string).length;
console.log(strLength);
```

# 10. Modules Exporting and Importing
```typescript
// in file: math.ts
export function add(x: number, y: number): number {
    return x + y;
}

// in another file
import { add } from "./math";
console.log(add(2, 3));
```

# 11. Namespaces
```typescript
namespace Geometry {
    export function square(x: number): number {
        return x * x;
    }
}

console.log(Geometry.square(5));
```

# 12. Decorators (Experimental)
```typescript
function sealed(constructor: Function) {
    Object.seal(constructor);
    Object.seal(constructor.prototype);
}

@sealed
class Greeter {
    greeting: string;
    constructor(message: string) {
        this.greeting = message;
    }
    greet() {
        return "Hello, " + this.greeting;
    }
}
```

# 13. Utility Types
```typescript
interface Todo {
    title: string;
    description: string;
}

let todo: Partial<Todo> = {
    title: "Clean room"
};

let readonlyTodo: Readonly<Todo> = {
    title: "Clean room",
    description: "Remove dust and vacuum"
};
// readonlyTodo.title = "Edit title"; // Error: cannot assign to 'title'
```

# 14. Type Narrowing
```typescript
function padLeft(value: string, padding: string | number) {
    if (typeof padding === "number") {
        return Array(padding + 1).join(" ") + value;
    }
    if (typeof padding === "string") {
        return padding + value;
    }
    throw new Error(`Expected string or number, got '${typeof padding}'.`);
}

console.log(padLeft("Hello", 4));
```

# 15. Type Guards
```typescript
function isNumber(x: any): x is number {
    return typeof x === "number";
}

function doSomething(x: number | string) {
    if (isNumber(x)) {
        console.log(x.toFixed(2));
    } else {
        console.log(x.toUpperCase());
    }
}
```

# 16. Intersection Types
```typescript
interface BusinessPartner {
    name: string;
    credit: number;
}

interface Identity {
    id: number;
    name: string;
}

type Employee = BusinessPartner & Identity;

let e: Employee = {
    id: 1,
    name: "Alice",
    credit: 200
};
```

# 17. keyof and typeof
```typescript
type Point = { x: number; y: number };
type P = keyof Point; // "x" | "y"

const pt = { x: 1, y: 2 };
type T = typeof pt; // same as Point
```

# 18. Mapped Types
```typescript
type Keys = "option1" | "option2";
type Flags = { [K in Keys]: boolean };

let settings: Flags = {
    option1: true,
    option2: false
};
```

# 19. Conditional Types
```typescript
type IsString<T> = T extends string ? "Yes" : "No";
type A = IsString<string>;  // "Yes"
type B = IsString<number>;  // "No"
```

# 20. Never and Unknown Types
```typescript



function fail(message: string): never {
    throw new Error(message);
}

function process(value: unknown) {
    if (typeof value === "string") {
        console.log(value.toUpperCase());
    }
}
```

# Next.js Notes

# 1. Introduction to Next.js

Next.js is a React framework for building fast, user-friendly web applications. It supports features like:

- File-based routing
- Server-side rendering (SSR)
- Static site generation (SSG)
- API routes
- Image optimization
- Middleware
- Incremental Static Regeneration (ISR)


# 2. Installation

```bash
npx create-next-app@latest my-app
cd my-app
npm run dev
```


# 3. Pages and Routing

Next.js uses the `pages/` directory for routing. Each `.tsx` file becomes a route.

```tsx
// pages/index.tsx
export default function Home() {
  return <h1>Home Page</h1>;
}

// pages/about.tsx
export default function About() {
  return <h1>About Page</h1>;
}
```


# 4. Linking Between Pages

Use the built-in `Link` component:

```tsx
import Link from 'next/link';

export default function Home() {
  return (
    <div>
      <h1>Home</h1>
      <Link href="/about">Go to About</Link>
    </div>
  );
}
```


# 5. Dynamic Routes

```tsx
// pages/posts/[id].tsx
import { useRouter } from 'next/router';

export default function Post() {
  const router = useRouter();
  const { id } = router.query;

  return <p>Post ID: {id}</p>;
}
```


# 6. API Routes

```ts
// pages/api/hello.ts
export default function handler(req, res) {
  res.status(200).json({ message: "Hello from API" });
}
```

Access via `/api/hello`.


# 7. Static Generation (getStaticProps)

```tsx
export async function getStaticProps() {
  return {
    props: {
      message: "This is pre-rendered at build time",
    },
  };
}

export default function Page({ message }) {
  return <h1>{message}</h1>;
}
```


# 8. Static Paths (getStaticPaths)

```tsx
export async function getStaticPaths() {
  return {
    paths: [{ params: { id: '1' } }, { params: { id: '2' } }],
    fallback: false,
  };
}

export async function getStaticProps({ params }) {
  return { props: { id: params.id } };
}

export default function Page({ id }) {
  return <h1>Post ID: {id}</h1>;
}
```


# 9. Server-side Rendering (getServerSideProps)

```tsx
export async function getServerSideProps() {
  return {
    props: { timestamp: new Date().toISOString() },
  };
}

export default function Page({ timestamp }) {
  return <h1>Time: {timestamp}</h1>;
}
```


# 10. API Integration with SWR

```tsx
import useSWR from 'swr';

const fetcher = (url: string) => fetch(url).then(res => res.json());

export default function Profile() {
  const { data, error } = useSWR('/api/hello', fetcher);

  if (error) return <div>Failed to load</div>;
  if (!data) return <div>Loading...</div>;

  return <div>{data.message}</div>;
}
```


# 11. Custom App Component

```tsx
// pages/_app.tsx
import '../styles/globals.css';

export default function MyApp({ Component, pageProps }) {
  return <Component {...pageProps} />;
}
```


# 12. Custom Document

```tsx
// pages/_document.tsx
import Document, { Html, Head, Main, NextScript } from 'next/document';

export default class MyDocument extends Document {
  render() {
    return (
      <Html>
        <Head />
        <body>
          <Main />
          <NextScript />
        </body>
      </Html>
    );
  }
}
```


# 13. Image Optimization

```tsx
import Image from 'next/image';
import profilePic from '../public/me.jpg';

export default function Avatar() {
  return <Image src={profilePic} alt="Me" width={200} height={200} />;
}
```


# 14. Middleware

```ts
// middleware.ts
import { NextResponse } from 'next/server';

export function middleware(request) {
  console.log("Middleware running...");
  return NextResponse.next();
}
```


# 15. Environment Variables

In `.env.local`:

```tsx
NEXT_PUBLIC_API_URL=https://api.example.com
```

Usage:

```ts
console.log(process.env.NEXT_PUBLIC_API_URL);
```


# 16. Deploying

# Using Vercel

```bash
npx vercel
```

# Static Export (Limited)

```bash
npm run build
npm run export
```


# 17. App Router (Next.js 13+)

```tsx
// app/page.tsx
export default function HomePage() {
  return <h1>Welcome to the App Router!</h1>;
}
```

# Layouts

```tsx
// app/layout.tsx
export default function RootLayout({ children }) {
  return (
    <html>
      <body>{children}</body>
    </html>
  );
}
```


