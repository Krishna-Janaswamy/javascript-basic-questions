# javascript-basic-questions

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

---

## 21. How would you implement a deep clone of an object in JavaScript?
### Explanation:
A deep clone creates a copy of an object along with its nested objects. This can be achieved using recursion, structured cloning, or libraries like Lodash.

### Example Code:
```javascript
function deepClone(obj) {
  if (obj === null || typeof obj !== 'object') {
    return obj;
  }

  if (Array.isArray(obj)) {
    return obj.map(deepClone);
  }

  const clonedObj = {};
  for (const key in obj) {
    if (obj.hasOwnProperty(key)) {
      clonedObj[key] = deepClone(obj[key]);
    }
  }
  return clonedObj;
}

const original = { a: 1, b: { c: 2 } };
const copy = deepClone(original);
console.log(copy); // { a: 1, b: { c: 2 } }
```

---

## 22. Explain the concept of functional programming and its benefits in JavaScript.
### Explanation:
Functional programming is a programming paradigm that treats computation as the evaluation of mathematical functions and avoids changing state and mutable data. Benefits include improved code readability, easier debugging, and better modularity.

### Example Code:
```javascript
const numbers = [1, 2, 3, 4, 5];

// Pure function
const double = (n) => n * 2;

// Higher-order function
const map = (fn, arr) => arr.map(fn);

const doubledNumbers = map(double, numbers);
console.log(doubledNumbers); // [2, 4, 6, 8, 10]
```

---

## 23. How would you implement a singleton pattern in JavaScript?
### Explanation:
The singleton pattern ensures that a class has only one instance and provides a global point of access to it. This can be implemented using closures or ES6 classes.

### Example Code:
```javascript
class Singleton {
  constructor() {
    if (Singleton.instance) {
      return Singleton.instance;
    }
    this.value = Math.random();
    Singleton.instance = this;
    return this;
  }
}

const instance1 = new Singleton();
const instance2 = new Singleton();
console.log(instance1 === instance2); // true
```

---

## 24. Explain the difference between synchronous and asynchronous code execution in JavaScript.
### Explanation:
Synchronous code is executed sequentially, blocking the execution of subsequent code until the current operation completes. Asynchronous code allows other code to run while waiting for an operation to complete, enabling non-blocking execution.

### Example Code:
```javascript
// Synchronous
console.log('Synchronous 1');
console.log('Synchronous 2');

// Asynchronous
console.log('Asynchronous 1');
setTimeout(() => {
  console.log('Asynchronous 2');
}, 1000);
console.log('Asynchronous 3');

// Output:
// Synchronous 1
// Synchronous 2
// Asynchronous 1
// Asynchronous 3
// Asynchronous 2
```

---

## 25. How would you implement a pub/sub (publish/subscribe) pattern in JavaScript?
### Explanation:
The pub/sub pattern allows for decoupling of components by having publishers emit events and subscribers listen for those events.

### Example Code:
```javascript
class PubSub {
  constructor() {
    this.events = {};
  }

  subscribe(event, listener) {
    if (!this.events[event]) {
      this.events[event] = [];
    }
    this.events[event].push(listener);
  }

  publish(event, data) {
    if (this.events[event]) {
      this.events[event].forEach((listener) => listener(data));
    }
  }
}

const pubSub = new PubSub();

pubSub.subscribe('event1', (data) => console.log(`Event 1 received with data: ${data}`));
pubSub.publish('event1', 'Hello, World!');
```

---

## 26. What are generators in JavaScript, and how do they work? Provide an example.
### Explanation:
Generators are functions that can be paused and resumed, allowing for lazy evaluation. They are defined using the `function*` syntax and use the `yield` keyword.

### Example Code:
```javascript
function* generatorFunction() {
  yield 1;
  yield 2;
  yield 3;
}

const generator = generatorFunction();

console.log(generator.next()); // { value: 1, done: false }
console.log(generator.next()); // { value: 2, done: false }
console.log(generator.next()); // { value: 3, done: false }
console.log(generator.next()); // { value: undefined, done: true }
```

---

## 27. How would you implement a binary search algorithm in JavaScript?
### Explanation:
Binary search is an efficient algorithm for finding a target value within a sorted array. It works by repeatedly dividing the search interval in half.

### Example Code:
```javascript
function binarySearch(arr, target) {
  let left = 0;
  let right = arr.length - 1;

  while (left <= right) {
    const mid = Math.floor((left + right) / 2);
    if (arr[mid] === target) {
      return mid;
    }
    if (arr[mid] < target) {
      left = mid + 1;
    } else {
      right = mid - 1;
    }
  }
  return -1;
}

const sortedArray = [1, 2, 3, 4, 5];
console.log(binarySearch(sortedArray, 3)); // 2
console.log(binarySearch(sortedArray, 6)); // -1
```

---

## 28. Explain the concept of currying in JavaScript and provide an example.
### Explanation:
Currying is a technique of transforming a function that takes multiple arguments into a sequence of functions that each take a single argument.

### Example Code:
```javascript
function curry(fn) {
  return function curried(...args) {
    if (args.length >= fn.length) {
      return fn.apply(this, args);
    } else {
      return function(...nextArgs) {
        return curried.apply(this, args.concat(nextArgs));
      };
    }
  };
}

function add(a, b, c) {
  return a + b + c;
}

const curriedAdd = curry(add);
console.log(curriedAdd(1)(2)(3)); // 6
```

---

## 29. How do you handle memory leaks in JavaScript applications?
### Explanation:
Memory leaks occur when memory that is no longer needed is not released. To handle memory leaks, use the following techniques:
- Avoid global variables.
- Clean up event listeners.
- Manage DOM references carefully.
- Use profiling tools to identify and fix leaks.

### Example Code:
```javascript
// Example of cleaning up event listeners
function setup() {
  const button = document.getElementById('myButton');
  function handleClick() {
    console.log('Button clicked');
  }
  button.addEventListener('click', handleClick);

  // Clean up event listener
  return function cleanup() {
    button.removeEventListener('click', handleClick);
  };
}

const cleanupFunction = setup();
// Call cleanupFunction() when the event listener is no longer needed
```

---

## 30. How would you implement a priority queue in JavaScript?
### Explanation:
A priority queue is a data structure where elements are removed based on priority. Elements with higher priority are dequeued before elements with lower priority.

### Example Code:
```javascript
class PriorityQueue {
  constructor() {
    this.queue = [];
  }

  enqueue(element, priority) {
    const queueElement = { element, priority };
    if (this.isEmpty()) {
      this.queue.push(queueElement);
    } else {
      let added = false;
      for (let i = 0; i < this.queue.length; i++) {
        if (queueElement.priority < this.queue[i].priority) {
          this.queue.splice(i, 1, queueElement);
          added = true;
          break;
        }
      }
      if (!added) {
        this.queue.push(queueElement);
      }
    }
  }

  dequeue() {
    return this.queue.shift().element;
  }

  isEmpty() {
    return this.queue.length === 0;
  }
}

const pq = new PriorityQueue();
pq.enqueue('Task 1', 2);
pq.enqueue('Task 2', 1);
pq.enqueue('Task 3', 3);

console.log(pq.dequeue()); // 'Task 2'
console.log(pq.dequeue()); // 'Task 1'
console.log(pq.dequeue()); // 'Task 3'
```

---
