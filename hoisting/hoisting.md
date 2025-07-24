
# JavaScript Hoisting

Hoisting is one of those JavaScript concepts that can feel a bit confusing at first, but once you get it, everything clicks. Simply put, **hoisting means that variable and function declarations are moved to the top of their scope** before the code is executed.

But this doesn’t mean the *values* are hoisted — just the declarations.

---

## What Gets Hoisted?

In JavaScript:

- **Function declarations** are fully hoisted (both name and body).
- **Variables declared with `var`** are hoisted, but only their *declaration* — not their assignment.
- **Variables declared with `let` and `const`** are also hoisted, but they are not accessible until they are initialized (they are in a “temporal dead zone”).

---

## Let’s See an Example:

```javascript
console.log(name); // undefined
var name = "Ozgur";

// Behind the scenes, JS treats it like this:
var name;
console.log(name); // undefined
name = "Ozgur";
```

As you can see, the variable declaration `var name` is hoisted to the top, but the value assignment happens later.

---

### Hoisting with `let` and `const`

```javascript
console.log(age); // ReferenceError!
let age = 30;
```

Here, `let` is hoisted too, but it stays in the **temporal dead zone** until it’s initialized. That’s why accessing it early throws a `ReferenceError`.

---

### Function Hoisting

```javascript
greet(); // "Hello!"

function greet() {
  console.log("Hello!");
}
```

This works because **function declarations are fully hoisted**. But this is not the case with function expressions:

```javascript
sayHi(); // TypeError: sayHi is not a function

var sayHi = function() {
  console.log("Hi!");
};
```

In this case, `sayHi` is hoisted as a `var`, so it's initialized as `undefined` at the top — and calling it as a function gives an error.

---

## ✅ Summary

- **Declarations** are hoisted, **assignments are not**.
- Use `let` and `const` to avoid confusion — they behave more predictably than `var`.
- Function **declarations** are hoisted, but **function expressions** are not.
- Understanding hoisting helps avoid bugs and makes it easier to read and debug your code.

---

## 💡 Next Steps

- 🔄 [The this Keyword](../thiskeyword/thiskeyword.md)

---