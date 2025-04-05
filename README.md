# JavaScript Important Questions and Answers

## Table of Contents
1. [What is the difference between `var`, `let`, and `const`?](#1-what-is-the-difference-between-var-let-and-const)
2. [What are closures in JavaScript? Provide an example.](#2-what-are-closures-in-javascript-provide-an-example)
3. [Explain the concept of promises in JavaScript.](#3-explain-the-concept-of-promises-in-javascript)
4. [What is the event loop in JavaScript?](#4-what-is-the-event-loop-in-javascript)
5. [How does prototypal inheritance work in JavaScript?](#5-how-does-prototypal-inheritance-work-in-javascript)
6. [What are arrow functions, and how do they differ from regular functions?](#6-what-are-arrow-functions-and-how-do-they-differ-from-regular-functions)
7. [What is the difference between `==` and `===` in JavaScript?](#7-what-is-the-difference-between--and--in-javascript)
8. [What are JavaScript modules, and how do you use them?](#8-what-are-javascript-modules-and-how-do-you-use-them)
9. [Explain the `this` keyword in JavaScript.](#9-explain-the-this-keyword-in-javascript)
10. [What is the difference between `null` and `undefined` in JavaScript?](#10-what-is-the-difference-between-null-and-undefined-in-javascript)
11. [How do you optimize the performance of a JavaScript application?](#11-how-do-you-optimize-the-performance-of-a-javascript-application)
12. [Explain the concept of event delegation and its advantages.](#12-explain-the-concept-of-event-delegation-and-its-advantages)
13. [What are the different ways to handle asynchronous operations in JavaScript?](#13-what-are-the-different-ways-to-handle-asynchronous-operations-in-javascript)
14. [How would you implement a debounce function in JavaScript?](#14-how-would-you-implement-a-debounce-function-in-javascript)
15. [Explain the concept of memoization and how you would implement it in JavaScript.](#15-explain-the-concept-of-memoization-and-how-you-would-implement-it-in-javascript)
16. [How would you handle errors in JavaScript both synchronously and asynchronously?](#16-how-would-you-handle-errors-in-javascript-both-synchronously-and-asynchronously)
17. [What is the difference between `call`, `apply`, and `bind` methods in JavaScript?](#17-what-is-the-difference-between-call-apply-and-bind-methods-in-javascript)
18. [How would you implement a custom iterator in JavaScript?](#18-how-would-you-implement-a-custom-iterator-in-javascript)
19. [Explain the module pattern and its advantages.](#19-explain-the-module-pattern-and-its-advantages)
20. [How would you handle large datasets in a JavaScript application?](#20-how-would-you-handle-large-datasets-in-a-javascript-application)
21. [How would you implement a deep clone of an object in JavaScript?](#21-how-would-you-implement-a-deep-clone-of-an-object-in-javascript)
22. [Explain the concept of functional programming and its benefits in JavaScript.](#22-explain-the-concept-of-functional-programming-and-its-benefits-in-javascript)
23. [How would you implement a singleton pattern in JavaScript?](#23-how-would-you-implement-a-singleton-pattern-in-javascript)
24. [Explain the difference between synchronous and asynchronous code execution in JavaScript.](#24-explain-the-difference-between-synchronous-and-asynchronous-code-execution-in-javascript)
25. [How would you implement a pub/sub (publish/subscribe) pattern in JavaScript?](#25-how-would-you-implement-a-pubsub-publishsubscribe-pattern-in-javascript)
26. [What are generators in JavaScript, and how do they work? Provide an example.](#26-what-are-generators-in-javascript-and-how-do-they-work-provide-an-example)
27. [How would you implement a binary search algorithm in JavaScript?](#27-how-would-you-implement-a-binary-search-algorithm-in-javascript)
28. [Explain the concept of currying in JavaScript and provide an example.](#28-explain-the-concept-of-currying-in-javascript-and-provide-an-example)
29. [How do you handle memory leaks in JavaScript applications?](#29-how-do-you-handle-memory-leaks-in-javascript-applications)
30. [How would you implement a priority queue in JavaScript?](#30-how-would-you-implement-a-priority-queue-in-javascript)

## 1. What is the difference between `var`, `let`, and `const`?
- `var`: Function-scoped, hoisted to the top of the scope. It can be redeclared and updated.
- `let`: Block-scoped, not hoisted to the top of the scope. It can be updated but not redeclared in the same scope.
- `const`: Block-scoped, not hoisted to the top of the scope. It cannot be updated or redeclared.

## 2. What are closures in JavaScript? Provide an example.
- Closures are functions that have access to the parent scope, even after the parent function has closed.
- Example:
```javascript
function outerFunction() {
    let outerVariable = "I am outside!";
    function innerFunction() {
        console.log(outerVariable); // Can access outerVariable
    }
    return innerFunction;
}
const myClosure = outerFunction();
myClosure(); // Outputs: I am outside!
```

## 3. Explain the concept of promises in JavaScript.
- Promises are objects representing the eventual completion or failure of an asynchronous operation.
- They have three states: pending, resolved, and rejected.
- Example:
```javascript
let promise = new Promise((resolve, reject) => {
    setTimeout(() => resolve("Done!"), 1000);
});
promise.then(result => console.log(result)); // Outputs: Done!
```

## 4. What is the event loop in JavaScript?
- The event loop is a mechanism that allows JavaScript to perform non-blocking operations by offloading operations to the system kernel when possible.
- It continuously checks the call stack and the callback queue, executing tasks in the call stack and moving tasks from the callback queue to the call stack when the call stack is empty.

## 5. How does prototypal inheritance work in JavaScript?
- Prototypal inheritance is a feature where objects can inherit properties and methods from other objects.
- Every object in JavaScript has a prototype, and objects inherit from other objects via this prototype chain.

## 6. What are arrow functions, and how do they differ from regular functions?
- Arrow functions are a concise syntax for writing functions using the `=>` syntax.
- They do not have their own `this`, arguments, super, or new.target bindings.
- They are not suitable for methods or constructors.
- Example:
```javascript
const add = (a, b) => a + b;
console.log(add(2, 3)); // Outputs: 5
```

## 7. What is the difference between `==` and `===` in JavaScript?
- `==`: Checks for equality with type coercion.
- `===`: Checks for equality without type coercion (strict equality).

## 8. What are JavaScript modules, and how do you use them?
- JavaScript modules are reusable pieces of code that can be imported and exported between files.
- They help in organizing code and avoiding global scope pollution.
- Example:
```javascript
// In math.js
export function add(a, b) {
    return a + b;
}
// In main.js
import { add } from './math.js';
console.log(add(2, 3)); // Outputs: 5
```

## 9. Explain the `this` keyword in JavaScript.
- The `this` keyword refers to the context in which a function is called.
- It can refer to different objects depending on how the function is called (e.g., as a method, as a constructor, etc.).

## 10. What is the difference between `null` and `undefined` in JavaScript?
- `null`: Represents the intentional absence of any object value. It must be assigned.
- `undefined`: Represents a variable that has been declared but not yet assigned a value.

## 11. How do you optimize the performance of a JavaScript application?
- Optimize by minimizing DOM access, using efficient algorithms, lazy loading resources, debouncing/throttling events, and optimizing memory usage.
- Tools like Lighthouse, Webpack, and profiling in browser dev tools can help identify performance bottlenecks.

## 12. Explain the concept of event delegation and its advantages.
- Event delegation is a technique where a single event listener is added to a parent element to manage events for multiple child elements.
- It reduces memory usage and improves performance by limiting the number of event listeners.
- Example:
```javascript
document.getElementById('parent').addEventListener('click', function(event) {
    if (event.target && event.target.matches('button.className')) {
        console.log('Button clicked!');
    }
});
```

## 13. What are the different ways to handle asynchronous operations in JavaScript?
- Callbacks, Promises, and Async/Await.

## 14. How would you implement a debounce function in JavaScript?
- A debounce function delays the processing of the input until after a specified time has passed since the last input.
- Example:
```javascript
function debounce(func, delay) {
    let debounceTimer;
    return function() {
        const context = this;
        const args = arguments;
        clearTimeout(debounceTimer);
        debounceTimer = setTimeout(() => func.apply(context, args), delay);
    };
}
```

## 15. Explain the concept of memoization and how you would implement it in JavaScript.
- Memoization is an optimization technique to speed up function calls by caching the results of expensive function calls.
- Example:
```javascript
function memoize(func) {
    const cache = {};
    return function(...args) {
        const key = JSON.stringify(args);
        if (!cache[key]) {
            cache[key] = func.apply(this, args);
        }
        return cache[key];
    };
}
```

## 16. How would you handle errors in JavaScript both synchronously and asynchronously?
- Synchronously: Use `try...catch` blocks.
- Asynchronously: Use `catch` method for Promises, and try...catch with Async/Await.
- Example:
```javascript
try {
    // Synchronous code
} catch (error) {
    console.error(error);
}
async function asyncFunction() {
    try {
        await someAsyncOperation();
    } catch (error) {
        console.error(error);
    }
}
```

## 17. What is the difference between `call`, `apply`, and `bind` methods in JavaScript?
- `call`: Invokes a function with a given `this` value and arguments provided individually.
- `apply`: Invokes a function with a given `this` value and arguments provided as an array.
- `bind`: Creates a new function that, when called, has its `this` value set to the provided value, with a given sequence of arguments.

## 18. How would you implement a custom iterator in JavaScript?
- Example:
```javascript
const myIterable = {
    *[Symbol.iterator]() {
        yield 1;
        yield 2;
        yield 3;
    }
};
for (const value of myIterable) {
    console.log(value); // Outputs: 1, 2, 3
}
```

## 19. Explain the module pattern and its advantages.
- The module pattern encapsulates private and public variables and methods using closures.
- It helps in organizing code, avoiding global scope pollution, and creating reusable modules.
- Example:
```javascript
const module = (function() {
    let privateVar = 'I am private';
    function privateMethod() {
        console.log(privateVar);
    }
    return {
        publicMethod: function() {
            privateMethod();
        }
    };
})();
module.publicMethod(); // Outputs: I am private
```

## 20. How would you handle large datasets in a JavaScript application?
- Use techniques like pagination, lazy loading, web workers, and virtual scrolling to manage large datasets efficiently.

## 21. How would you implement a deep clone of an object in JavaScript?
- Example:
```javascript
function deepClone(obj) {
    if (obj === null || typeof obj !== 'object') {
        return obj;
    }
    if (obj instanceof Date) {
        return new Date(obj.getTime());
    }
    if (obj instanceof Array) {
        const arrCopy = [];
        obj.forEach((item, index) => {
            arrCopy[index] = deepClone(item);
        });
        return arrCopy;
    }
    if (obj instanceof Object) {
        const objCopy = {};
        Object.keys(obj).forEach(key => {
            objCopy[key] = deepClone(obj[key]);
        });
        return objCopy;
    }
    throw new Error('Unable to copy object!');
}
```

## 22. Explain the concept of functional programming and its benefits in JavaScript.
- Functional programming is a paradigm where functions are treated as first-class citizens and emphasize immutability, pure functions, and higher-order functions.
- Benefits include easier debugging, predictable code, and improved readability.

## 23. How would you implement a singleton pattern in JavaScript?
- Example:
```javascript
const Singleton = (function() {
    let instance;
    function createInstance() {
        const object = new Object('I am the instance');
        return object;
    }
    return {
        getInstance: function() {
            if (!instance) {
                instance = createInstance();
            }
            return instance;
        }
    };
})();
const instance1 = Singleton.getInstance();
const instance2 = Singleton.getInstance();
console.log(instance1 === instance2); // Outputs: true
```

## 24. Explain the difference between synchronous and asynchronous code execution in JavaScript.
- Synchronous code is executed sequentially, one line at a time, blocking the execution of subsequent code until the current operation completes.
- Asynchronous code allows other code to run while waiting for an operation to complete, using callbacks, promises, or async/await.

## 25. How would you implement a pub/sub (publish/subscribe) pattern in JavaScript?
- Example:
```javascript
const pubSub = {
    events: {},
    subscribe: function(event, listener) {
        if (!this.events[event]) {
            this.events[event] = [];
        }
        this.events[event].push(listener);
    },
    publish: function(event, data) {
        if (this.events[event]) {
            this.events[event].forEach(listener => listener(data));
        }
    }
};
pubSub.subscribe('event1', data => console.log(`Event 1 received with data: ${data}`));
pubSub.publish('event1', 'some data'); // Outputs: Event 1 received with data: some data
```

## 26. What are generators in JavaScript, and how do they work? Provide an example.
- Generators are functions that can be paused and resumed, allowing them to yield multiple values over time.
- Example:
```javascript
function* generatorFunction() {
    yield 1;
    yield 2;
    yield 3;
}
const generator = generatorFunction();
console.log(generator.next().value); // Outputs: 1
console.log(generator.next().value); // Outputs: 2
console.log(generator.next().value); // Outputs: 3
```

## 27. How would you implement a binary search algorithm in JavaScript?
- Example:
```javascript
function binarySearch(array, target) {
    let left = 0;
    let right = array.length - 1;
    while (left <= right) {
        const mid = Math.floor((left + right) / 2);
        if (array[mid] === target) {
            return mid;
        } else if (array[mid] < target) {
            left = mid + 1;
        } else {
            right = mid - 1;
        }
    }
    return -1;
}
```

## 28. Explain the concept of currying in JavaScript and provide an example.
- Currying is a technique of transforming a function with multiple arguments into a sequence of functions, each with a single argument.
- Example:
```javascript
function curry(func) {
    return function curried(...args) {
        if (args.length >= func.length) {
            return func.apply(this, args);
        } else {
            return function(...args2) {
                return curried.apply(this, args.concat(args2));
            };
        }
    };
}
function sum(a, b, c) {
    return a + b + c;
}
const curriedSum = curry(sum);
console.log(curriedSum(1)(2)(3)); // Outputs: 6
```

## 29. How do you handle memory leaks in JavaScript applications?
- Identify leaks using browser developer tools, avoid global variables, clean up DOM elements, use weak references, and optimize event listeners.

## 30. How would you implement a priority queue in JavaScript?
- Example:
```javascript
class PriorityQueue {
    constructor() {
        this.queue = [];
    }
    enqueue(element, priority) {
        const queueElement = { element, priority };
        let added = false;
        for (let i = 0; i < this.queue.length; i++) {
            if (queueElement.priority < this.queue[i].priority) {
                this.queue.splice(i, 0, queueElement);
                added = true;
                break;
            }
        }
        if (!added) {
            this.queue.push(queueElement);
        }
    }
    dequeue() {
        return this.queue.shift();
    }
    isEmpty() {
        return this.queue.length === 0;
    }
}
const pq = new PriorityQueue();
pq.enqueue('low', 2);
pq.enqueue('high', 1);
console.log(pq.dequeue().element); // Outputs: high
```
