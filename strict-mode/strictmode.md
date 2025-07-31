# JavaScript Strict Mode

Understanding **Strict Mode** in JavaScript is fundamental to writing safer and more predictable code. It helps you catch common mistakes and enforce a cleaner coding style.

---

## What is Strict Mode?

- Strict Mode is a way to opt in to a restricted variant of JavaScript.
- It prevents certain actions and throws more exceptions.
- It eliminates some silent JavaScript errors by changing them to throw errors.
- It makes it easier to write “secure” JavaScript.

---

### Enabling Strict Mode:

You enable strict mode by adding `'use strict';` at the beginning of a script or a function.

```js
'use strict';

x = 5; // ❌ Error: x is not defined

```

In this example, assigning a value to an undeclared variable results in an error.


### Why Use Strict Mode?

- Avoids accidental global variables

- Makes debugging easier

- Disallows duplicate parameter names

- Blocks usage of deprecated or error-prone features

- Helps in writing cleaner and more secure code

### Function-Level Strict Mode:

```js

function test() {
  'use strict';
  y = 10; // ❌ Error: y is not defined
}

```

Strict Mode can be applied only within a function if needed.

### Common Restrictions in Strict Mode

- Cannot use undeclared variables.

- `delete` cannot be used on variables or functions.

- Duplicate parameter names are not allowed.

- Some keywords like `eval` and `arguments` are restricted.

- `this` is `undefined` in functions (not the global object).

## ✅ Summary

- Strict Mode: A way to write better, safer JavaScript.

- Helps avoid hidden bugs and bad practices.

- Use `'use strict'`; at the top of your scripts or functions.

- It’s a basic yet essential concept for every JavaScript developer.

## 💡 Next Steps

- [Callback Fuction](../callback-functions/callback.md)
