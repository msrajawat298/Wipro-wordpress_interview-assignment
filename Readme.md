### Front-end Questions:

#### 1. What are semantic elements and their purpose in HTML?

Semantic elements in HTML clearly describe their meaning in a human- and machine-readable way. Examples include `<header>`, `<footer>`, `<article>`, and `<section>`. These elements help improve accessibility, SEO, and code readability by defining the structure and content more accurately.

##### Example Code:
1. [Question 1](Front-end-questions/1.html)


#### 2. Can you explain about CSS Grid, CSS Flex and CSS Animation with example Code ?

##### CSS Grid

CSS Grid is a powerful layout system that allows you to create complex, responsive web layouts by defining rows and columns. It provides more flexibility compared to older layout techniques like floats and tables.

##### CSS Flexbox: 

CSS Flexbox is a one-dimensional layout model that distributes space along a single axis (either horizontal or vertical). It is great for aligning items and controlling the space between them, making it easier to create dynamic and flexible layouts.

#### Example Code: 

1. [CSS Grid](Front-end-question/Grid.html)
2. [CSS Flexbox](Front-end-question/Flexbox.html)
2. [CSS Animation](Front-end-question/Animation.html)



#### CSS Animation

CSS Animations allow you to animate transitions between CSS property values over time. You define keyframes that describe the animation states and specify the duration, timing, and iteration.



### 3. What is the significance of promise, async and await in JavaScript? Can you explain with code? Screenshot is appreciated.

### Promises in JavaScript
A Promise in JavaScript represents the eventual completion (or failure) of an asynchronous operation. It allows you to handle asynchronous code in a cleaner and more manageable way compared to callbacks.

- A Promise can have three states:
  1. Pending: Initial state, neither fulfilled nor rejected.
  2. Fulfilled: The operation completed successfully.
  3. Rejected: The operation failed.

### Example of a Promise:

```javascript
const myPromise = new Promise((resolve, reject) => {
    const success = true; // Simulate an async operation result
    if (success) {
        resolve("Operation was successful!");
    } else {
        reject("Operation failed.");
    }
});

myPromise
    .then((message) => {
        console.log(message); // Output: "Operation was successful!"
    })
    .catch((error) => {
        console.error(error); // If rejected, this will be triggered
    });
```

In the example, the promise resolves with a success message. If it had failed, the `catch` block would handle the error.

---

### Async and Await
Async and Await are syntactic sugar built on top of Promises to make asynchronous code easier to read and write. They allow you to write asynchronous code that looks more like synchronous code.

- `async`: Declares a function that returns a Promise. Inside this function, you can use `await`.
- `await`: Pauses the execution of an async function and waits for the Promise to resolve or reject.

### Example using `async` and `await`:

```javascript
// Simulate an asynchronous operation using a Promise
function fetchData() {
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            const data = { name: "John Doe", age: 25 };
            resolve(data);
        }, 2000); // Simulates a 2-second delay
    });
}

async function getUserData() {
    try {
        console.log("Fetching data...");
        const user = await fetchData(); // Waits for the promise to resolve
        console.log("User Data:", user); // Output after 2 seconds: { name: "John Doe", age: 25 }
    } catch (error) {
        console.error("Error fetching data:", error);
    }
}

getUserData();
```

#### Key Points:
- `async` before the function means the function always returns a Promise.
- `await` makes the code wait for the Promise to resolve before continuing.
- If the promise is rejected, you can handle it using a `try-catch` block.

---

### Significance of Promises, Async, and Await
- Promises help avoid "callback hell" by providing a cleaner way to handle asynchronous operations.
- Async/await simplifies the syntax of promises, making asynchronous code easier to read and write as if it were synchronous.
- Both are essential for handling real-world operations like network requests, file I/O, timers, and other asynchronous tasks.