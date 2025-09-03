# JavaScript Promises

A **Promise** is an object that represents the eventual completion (or failure) of an asynchronous operation and its resulting value.

---

## What is a Promise?

- It’s like a *placeholder* for a value that isn’t available yet but will be resolved in the future.  
- Promises help handle **asynchronous operations** more cleanly than callbacks.  
- They can be in one of three states:  
  - **pending** → still waiting  
  - **fulfilled** → completed successfully  
  - **rejected** → failed with an error  

---

## Example

```js
const promise = new Promise((resolve, reject) => {
  const success = true;

  if (success) {
    resolve("Task completed successfully!");
  } else {
    reject("Something went wrong.");
  }
});

promise
  .then(result => console.log(result))   // if fulfilled
  .catch(error => console.log(error))    // if rejected
  .finally(() => console.log("Done!"));

```

### Possible Output

```js
Task completed successfully!
Done!
```
## Why Use Promises?

- To avoid **callback hell** (deeply nested callbacks).  
- To write more **readable** asynchronous code.  
- To chain multiple async tasks in sequence.  
- To handle success and errors in a structured way.  

---

## Real-World Example: Fetching Data with `fetch` (Promise-based)

```js
fetch("https://jsonplaceholder.typicode.com/posts/1")
  .then(response => response.json())        // Convert the response stream to JSON (returns another Promise)
  .then(data => {
    console.log("Post title:", data.title); // Use the final resolved value
  })
  .catch(error => {
    console.error("Network or parsing error:", error); // Handle any error in the chain
  })
  .finally(() => {
    console.log("Request completed (success or failure)."); // Cleanup / always run
  });
```

## Explanation (step-by-step)

1. `fetch(url)` immediately returns a **Promise** (the request is in progress → **pending**).  
2. When the HTTP request succeeds, the Promise becomes **fulfilled** with a `Response` object.  
3. `response.json()` also returns a **Promise** because parsing the body is asynchronous.  
4. The next `.then` receives the parsed **data** (final resolved value).  
5. `.catch` handles **any error** from any previous step (network issues, JSON errors, etc.).  
6. `.finally` runs regardless of success or failure—useful for cleanup (e.g., hide a loader).  

---

## ✅ Summary

- A Promise represents a **future value**.  
- Use `.then()` for success, `.catch()` for errors, and `.finally()` for cleanup.  
- Built-in web APIs like `fetch` already return Promises, so you use them all the time when making network requests.  

---

## 💡 Next Steps


