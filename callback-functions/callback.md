# JavaScript Callbacks

A **callback** is a function passed as an argument to another function, which is then invoked inside that function to complete some kind of action.

---

## What is a Callback?

- It’s a way to make sure certain code runs **after** another function finishes.
- Commonly used in asynchronous operations (like fetching data, timers, or events).

---

### Example:

```js
function greet(name, callback) {
  console.log("Hello, " + name);
  callback();
}

function sayGoodbye() {
  console.log("Goodbye!");
}

greet("Alice", sayGoodbye);

```

### Output:

``` js
Hello, Alice
Goodbye!
```

- Here, `sayGoodbye` is the callback function that runs after `greet` finishes its work.

## Why Use Callbacks?

- To control the order of execution.
- To handle asynchronous tasks without blocking the program.
- To respond to events like user actions or data loading.

---

## ✅ Summary

- A callback is a function passed into another function.

- It lets you run code after a task is done.

- Callbacks are fundamental in JavaScript, especially for async programming.

## 💡 Next Steps

- 🔄 [Promises](../promises/promises.md)
