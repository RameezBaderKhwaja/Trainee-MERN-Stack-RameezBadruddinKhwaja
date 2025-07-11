#### **1. Chrome DevTools**

* Built-in browser tools for inspecting and debugging.
* Panels include **Elements** (edit HTML/CSS), **Console** (JS logs), **Sources** (JS debugging), **Network** (request analysis), **Performance** (page profiling), **Application**, and **Lighthouse** 
* Helpful shortcuts:

  * `Ctrl+Shift+C`: inspect element
  * `Ctrl+Shift+M`: responsive device mode
  * `Ctrl+Shift+P`: command menu 
* Tips: pretty-print minified code, breakpoints, multi-cursor editing, color format switching, toggle pseudo-classes, network filmstrip, capture performance screenshots & screen freezes 


#### **2. CSS Flexbox & Grid**

* **Flexbox**: one-dimensional layout system. Use `display: flex`, `flex-direction`, `justify-content`, `align-items`; item-level controls via `flex`, `order`, `align-self`
* **CSS Grid**: two-dimensional layout. Use `display: grid`, `grid-template-columns/rows`, `gap`, item placement with `grid-column` & `grid-row` 
* Flexbox is content-driven; Grid is layout-driven — choose based on need .


#### **3. Modern JavaScript for Beginners**

* Key topics:

  * Setup JS via `<script>` or modules (`import`/`export`)
  * Data types (`string`, `number`, `boolean`, `null`, `undefined`)
  * Variables: `let`, `const`, `var`
  * Control flow: `if`, `switch`, loops
  * Operators: arithmetic, comparison, logical
  * Functions: declarations, arrow functions
  * DOM manipulation: `querySelector`, `addEventListener`, modify content/styles
  * ES6+: template literals, destructuring, modules
  * Async: `fetch`, Promises, `async/await`

#### **4. Backend Fundamentals & APIs**

* Backend processes client requests, stores data, sends responses.
* Languages: Node.js, Python, Ruby, Java.
* Frameworks: Express (JS), Django (Python), Rails (Ruby), Spring (Java).
* Package managers: npm, pip, Bundler, Maven.
* Databases: MySQL, PostgreSQL, MongoDB.
* Request-response loop:

  1. Frontend sends request
  2. Backend handles logic, updates DB
  3. Response sent with data or status
* APIs define endpoints and methods (GET, POST, DELETE).

  * REST is common; GraphQL and RPC are alternatives.


#### **5. Cloud & Deployment**

* **IaaS**: rent VMs (AWS, GCP, Azure)
* **PaaS**: deploy code with managed environments (Elastic Beanstalk, App Engine)
* **SaaS**: use services via APIs (e.g., Twilio)
* **Load balancers** distribute traffic
* **Microservices**: split backend into focused services.
* Tools: Docker containers, SQL/NoSQL databases, blob storage (S3), caching (Redis), search (ElasticSearch), analytics (Snowflake).


#### **6. CSS Sizing & Styling (from web.dev)**

* Units: unitless for line-height; `%`, `px`, viewport units (`vw`, `vh`), character units (`ch`)
* Borders: style, radius, border-image.
* CSS functions: selectors (`:is()`), variables (`--var`), math functions (`calc()`, `clamp()`, `min()`, `max()`).
* Backgrounds: colors, images, gradients, including radial/conic.
* Container queries: `container-type` + `@container` rules.


### **Tooling & Workflow**

* Use **DevTools** for live editing, debugging, profiling.
* Use **Flexbox/Grid** for responsive layouts.
* Write interactive and modular **JavaScript**; enhance with modern syntax.
* Build robust **backend APIs**, deploy via **cloud services**, optimize storage & performance.
