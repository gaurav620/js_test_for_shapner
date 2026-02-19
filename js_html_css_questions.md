# JavaScript / HTML / CSS - Technical Interview Questions

## 🟡 JavaScript (Most Asked)

### Q1: What is the difference between `==` and `===`?

**Answer**: `==` checks value equality with **type coercion** (e.g., `"5" == 5` is `true`). `===` checks both **value and type** without coercion (e.g., `"5" === 5` is `false`). Always prefer `===` for predictable behavior.

### Q2: Explain Hoisting in JavaScript

**Answer**: Hoisting is JavaScript's default behavior of moving **declarations** to the top of their scope before execution.

- `var` → hoisted and initialized as `undefined`
- `let` / `const` → hoisted but NOT initialized (Temporal Dead Zone)
- Functions declared with `function` keyword → fully hoisted (can be called before declaration)

### Q3: What are Closures?

**Answer**: A closure is a function that **remembers** the variables from its outer (enclosing) scope even after the outer function has returned.

```javascript
function outer() {
  let count = 0;
  return function inner() {
    count++;
    return count;
  };
}
const counter = outer();
counter(); // 1
counter(); // 2
```

**Use case**: Data privacy, event handlers, callbacks.

### Q4: Explain `this` keyword in JavaScript

**Answer**:

- **Global scope**: `this` refers to `window` (browser) or `global` (Node.js)
- **Object method**: `this` refers to the **object** calling the method
- **Arrow function**: `this` is **lexically bound** (inherits from parent scope)
- **Constructor**: `this` refers to the **newly created object**

### Q5: What is Event Bubbling vs Event Capturing?

**Answer**:

- **Bubbling** (default): Event fires on the target element first, then **bubbles up** to parent elements.
- **Capturing**: Event fires from the **outermost parent down** to the target.
- Use `addEventListener('click', fn, true)` for capturing.
- `event.stopPropagation()` stops bubbling/capturing.

### Q6: Difference between `null` and `undefined`?

**Answer**:

- `undefined` → variable declared but **not assigned** a value
- `null` → intentionally assigned to represent **"no value"**
- `typeof undefined` → `"undefined"`, `typeof null` → `"object"` (JS quirk)

### Q7: What is the DOM?

**Answer**: DOM = **Document Object Model**. It represents the HTML page as a **tree of nodes/objects** that JavaScript can interact with. Methods: `getElementById()`, `querySelector()`, `createElement()`, `addEventListener()`.

### Q8: Explain `let`, `var`, `const` differences

**Answer**:

| Feature | `var` | `let` | `const` |
|---------|-------|-------|---------|
| Scope | Function | Block | Block |
| Hoisting | Yes (undefined) | Yes (TDZ) | Yes (TDZ) |
| Re-declare | Yes | No | No |
| Re-assign | Yes | Yes | No |

---

## 🟢 HTML

### Q1: What are Semantic HTML tags?

**Answer**: Tags that clearly describe their **meaning** to both the browser and developer. Examples: `<header>`, `<nav>`, `<main>`, `<article>`, `<section>`, `<footer>`. Non-semantic: `<div>`, `<span>`. Semantic HTML improves **accessibility** and **SEO**.

### Q2: Difference between Local Storage, Session Storage, and Cookies?

**Answer**:

| Feature | Local Storage | Session Storage | Cookies |
|---------|--------------|-----------------|---------|
| Capacity | ~5MB | ~5MB | ~4KB |
| Expiry | Never | Tab close | Can set expiry |
| Sent to server | No | No | Yes (every HTTP request) |

### Q3: What is the `<meta>` tag used for?

**Answer**: Provides **metadata** about the HTML document. Common uses:

- `<meta charset="UTF-8">` → character encoding
- `<meta name="viewport" ...>` → responsive design
- `<meta name="description" ...>` → SEO description

---

## 🔵 CSS

### Q1: Explain the CSS Box Model

**Answer**: Every HTML element is a rectangular box with 4 layers:

1. **Content** → text/image inside
2. **Padding** → space between content and border
3. **Border** → surrounds padding
4. **Margin** → space outside the border

`box-sizing: border-box` makes width/height include padding and border.

### Q2: How to center a div vertically and horizontally?

**Answer** (Modern approach):

```css
.parent {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}
```

### Q3: What is Flexbox vs Grid?

**Answer**:

- **Flexbox** → **1-dimensional** layout (row OR column). Best for component layouts.
- **Grid** → **2-dimensional** layout (rows AND columns). Best for page layouts.

### Q4: What is `position: absolute`?

**Answer**: Element is removed from normal document flow and positioned **relative to its nearest positioned ancestor** (parent with `position: relative/absolute/fixed`). If none exists, it's positioned relative to `<html>`.

### Q5: What are CSS Media Queries?

**Answer**: Used for **responsive design** to apply styles based on device characteristics:

```css
@media (max-width: 768px) {
  .sidebar { display: none; }
}
```
