#### Sizing Units

* **Numbers**: Unitless values for things like `opacity`, `line-height` (e.g., `line-height: 1.5` meaning 150%)
* **Percentages**: Relative to parent size, e.g., `width: 50%` 
* **Absolute Units**: `px`, `cm`, `in`, etc., useful for print .
* **Relative Units**:

  ```css
  p { max-width: 60ch; } /* width of 60 zero characters */
  div { width: 10vw; }   /* 10% of viewport width */
  ```

  .
* **Viewport/Container Units**: `vw`, `vh`, `cqw`, `cqh`, etc. 
---

#### Borders

* Set style, width, color:

  ```css
  .box { border: 2px solid red; border-radius: 1em; }
  .box { border-inline-end: 2px solid blue; }
  ```
* Border images:

  ```css
  .box {
    border-image: url(img.jpg) 10 fill stretch;
  }
  ```

  .

---

#### Grid Layout

* Define rows & columns; place items:

  ```css
  .grid {
    display: grid;
    grid-template-columns: 1fr 2fr;
    gap: 10px;
  }
  .grid-item { grid-column: 2; grid-row: 1 / 3; }
  ```

---

#### CSS Functions

* Functional selectors & variables:

  ```css
  .post :is(h1,h2,h3) { line-height:1.2; }
  :root { --base:#f0f; }
  .box { background: var(--base, hotpink); }
  ```
* Values: `attr()`, `url()` get attributes or URLs ([web.dev][3]).
* Math: `calc()`, `min()`, `max()`, `clamp()`:

  ```css
  .box { width: calc(100% - 2rem); }
  h1 { font-size: clamp(2rem,1rem+3vw,3rem); }
  ```

---

#### Backgrounds

* Set color/image:

  ```css
  .box { background-color: blue; }
  .box { background-image: url('pic.png'); }
  .box { background: linear-gradient(to right, red, yellow); }
  ```

---

#### Lists

* HTML lists:

  ```html
  <ul><li>Item</li></ul>
  <ol><li>A</li></ol>
  ```
* Style bullets:

  ```css
  ul { list-style: square inside url('bullet.png'); }
  li::marker { color: hotpink; }
  ```

  .

---

#### Spacing (Box Model)

* Use `margin` shorthand:

  ```css
  .box { margin: 10px 20px; /* top/bottom, left/right */ }
  ```


---

#### Color

* Use named, hex, rgb, hsl:

  ```css
  .text { color: hotpink; }
  .bg { background-color: rgb(183,21,64); }
  .bg2 { background-color: hsl(0, 100%, 50%); }
  .border { border-color: currentColor; }
  ```



#### Gradients

* Linear:

  ```css
  .bg { background: linear-gradient(black, white); }
  .bg2 { background: linear-gradient(45deg, darkred 30%, crimson); }
  ```
* Radial/conic:

  ```css
  .bg3 { background: radial-gradient(circle, white, black); }
  .bg4 { background: conic-gradient(from 45deg, white, black); }
  ```
* Repeating:

  ```css
  .bg5 { background: repeating-linear-gradient(45deg, red 0 30px, white 30px 60px); }
  ```


#### Container Queries

* Apply styles based on container size:
```css
  .container { container-type: inline-size; }
  @container (min-width:600px) {
    .item { font-size:1.5rem; }
  }
```


