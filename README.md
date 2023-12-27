# JavaScript-cheat-sheet

# JavaScript Cheat Sheet

In the fast-paced world of tech, interviews often focus on both theoretical knowledge and practical skills. Here's a cheat sheet that covers essential JavaScript concepts and coding challenges, providing both code snippets and explanations.

This guide is designed to help you swiftly review and understand common topics that you're likely to encounter during technical interviews for a developer position. It spans a range of subjects from basic programming constructs and DOM manipulation to advanced topics like asynchronous programming and error handling, equipping you with the insights to tackle front-end development questions with confidence.

### 1. **Basic Understanding**:

- **What are primitive data types in JavaScript?**
    - **Answer**: The primitive data types in JavaScript are Undefined, Null, Boolean, Number, BigInt, String, and Symbol.

- **How do you define variables?**

```jsx
  var x = 10;
  let y = 20;
  const z = 30;

```

- **Answer**: Variables can be defined using the `var`, `let`, or `const` keywords. `var` is function-scoped, `let` and `const` are block-scoped. `const` is used for variables whose values should not be reassigned after their initial assignment.

- **Can you explain the difference between `let`, `const`, and `var`?**

```jsx
  var x = 10;  // function-scoped, re-assignable
  let y = 20;  // block-scoped, re-assignable
  const z = 30;  // block-scoped, not re-assignable

```

- **Answer**: `var` is function-scoped and can be reassigned. `let` and `const` are block-scoped. `let` can be reassigned while `const` cannot be reassigned after the initial assignment.

### 2. **Functions and Scope**:

- **How do you declare a function?**
    - **Answer**: Functions are declared using the `function` keyword, followed by the function name, parameters within parentheses, and the function body within curly braces.

```jsx
  function myFunction(parameters) {
    // function body
  }

```

- **What is the difference between function expressions and function declarations?**
    - **Answer**: Function declarations are hoisted to the top of their scope with the function body, allowing them to be used before they're defined. Function expressions are not hoisted, and can only be used after they're defined. The variable holding the function expression is hoisted but assigned `undefined` initially.

```jsx
  // Function Expression:
  const myFunction = function(parameters) {
    // function body
  };

  // Function Declaration:
  function myFunction(parameters) {
    // function body
  }

```

- **Can you explain what lexical scope is?**
    - **Answer**: Lexical scope refers to the accessibility of variables based on their physical location in the code. Variables defined in an outer scope are accessible in an inner scope, but not vice versa.

```jsx
  let x = 10;  // outer scope

  function myFunction() {
    let y = 20;  // inner scope
    console.log(x);  // Accessible as it's in the outer scope
    console.log(y);  // Accessible as it's in the current scope
  }

  myFunction();
  console.log(x);  // Accessible as it's in the current scope
  console.log(y);  // Error as y is not accessible in the outer scope

```

### 3. **Objects and Arrays**:

- **How do you create an object?**
    - **Answer**: Objects are created using curly braces `{}`.

```jsx
  const myObject = {};

```

- **How do you access and modify properties of an object?**
    - **Answer**: Properties can be accessed and modified using dot notation or bracket notation.

```jsx
  myObject.propertyName = 'value';  // dot notation
  myObject['propertyName'] = 'value';  // bracket notation

```

- **What are some methods you can use with arrays?**
    - **Answer**: Some common array methods include `push` (adds elements to the end), `pop` (removes the last element), `shift` (removes the first element), and `unshift` (adds elements to the beginning).

```jsx
  const arr = [1, 2, 3, 4];
  arr.push(5);  // Adds 5 at the end, arr is now [1, 2, 3, 4, 5]
  arr.pop();  // Removes the last element, arr is now [1, 2, 3, 4]
  arr.shift();  // Removes the first element, arr is now [2, 3, 4]
  arr.unshift(1);  // Adds 1 at the beginning, arr is now [1, 2, 3, 4]

```

### 4. **DOM Manipulation**:

- Ho**w do you select DOM elements?**
    - Answer: DOM elements can be selected using `document.querySelector(selector)` or `document.getElementById(id)`.

```jsx
  const element = document.querySelector('.my-class');

```

- **How do you add or remove classes from a DOM element?**
    - **Answer**: Classes can be added or removed using `element.classList.add('class')` or `element.classList.remove('class')`.

```jsx
  element.classList.add('new-class');  // Adds 'new-class' to element
  element.classList.remove('my-class');  // Removes 'my-class' from element

```

- How would you **handle events like clicks or form submissions?**
    - **Answer**: Events are handled using `element.addEventListener('event', function)`.

```jsx
  element.addEventListener('click', function() {
    // Handle click
  });

```

### 5. **Asynchronous JavaScript**:

- **What is the event loop?**
    - **Answer**: The event loop is a mechanism that checks the call stack and executes tasks from the callback queue when the stack is empty, ensuring JavaScript's single-threaded, non-blocking nature.

```jsx
  // The event loop checks the call stack and executes tasks from the callback queue when the stack is empty.

```

- **Can you explain what promises are and how they are used?**
    - **Answer**: Promises are objects representing the eventual completion or failure of an asynchronous operation. They have `then` and `catch` methods for handling success and failure, respectively.

```jsx
  const myPromise = new Promise((resolve, reject) => {
    // Some asynchronous operation
    if (/* success */) {
      resolve('Success!');
    } else {
      reject('Failure!');
    }
  });

  myPromise.then((message) => {
    console.log(message);  // Success!
  }).catch((message) => {
    console.error(message);  // Failure!
  });

```

- **How does `async/await` work and when would you use it?**
    - **Answer**: `async/await` is syntactic sugar for working with Promises, making asynchronous code look and behave a bit more like synchronous code. It's used for better readability and simpler error handling.

```jsx
  async function myFunction() {
    try {
      const result = await someAsyncFunction();
      console.log(result);
    } catch (error) {
      console.error(error);
    }
  }

```

### 6. **Error Handling**:

- **How do you handle errors in JavaScript?**
    - **Answer**: Errors are handled using `try/catch` blocks. The `try` block contains code that may throw an error, and the `catch` block contains code to handle the error.

```jsx
  try {
    // Some code that may throw an error
  } catch (error) {
    console.error(error);
  }

```

- **What is the difference between a `try/catch` block and throwing an error?**
    - **Answer**: `try/catch` blocks are used to handle errors, while `throw` is used to generate and throw errors.

```jsx
  try {
    throw new Error('This is an error');
  } catch (error) {
    console.error(error);  // Error: This is an error
  }

```

### 7. **Testing and Debugging**:

- **How do you debug JavaScript code?**
    - **Answer**: Debugging can be done using `console.log()` to output values to the console, or using the `debugger` statement to pause execution and inspect the code in browser DevTools.

```jsx
  console.log('Debug message');  // Outputs 'Debug message' to the console
  debugger;  // Pauses execution for debugging in browser DevTools

```

- **Are you familiar with any testing libraries/frameworks?**
    - **Answer**: Some common you should learn are: testing libraries/frameworks including Jest, Mocha, Chai, and Jasmine.
    

### 8. **ES6 and Beyond**:

- **Can you explain what arrow functions are and how they differ from regular functions?**
    - **Answer**: Arrow functions provide a shorter syntax for writing function expressions. They are anonymous and change the way `this` behaves.

```jsx
  const myFunction = () => {
    // function body
  }

```

- **What are template literals and how are they used?**
    - **Answer**: Template literals allow embedded expressions and multi-line strings. They are enclosed by back-ticks (\`\\`) instead of single or double quotes.

```jsx
  const myString = `Hello, ${name}!`;

```

- **What is destructuring and how can it be used to make code more readable?**
    - **Answer**: Destructuring allows unpacking values from arrays, or properties from objects, into distinct variables, which can make code more readable and less verbose.

```jsx
  const myObject = { a: 1, b: 2 };
  const { a, b } = myObject;

```

### 9. **Frameworks and Libraries**:

- **Have you worked with any JavaScript frameworks or libraries like React, Angular, or Vue.js?**
    - **Answer**: This would be subjective based on your personal experience. I’d personally focus on React or Vue over Angular.

- **Can you build a simple to-do list app using a framework of your choice?**
    - **Answer**: template included in section 11

### 10. **Coding Challenge**:

- **Can you solve the following coding challenge? Given an array of integers, find the highest product you can get from three of the integers.**

```jsx
  function maxProduct(arr) {
    arr.sort((a, b) => b - a);
    return arr[0] * arr[1] * arr[2];
  }

```

- **Answer**: The function `maxProduct` provided in the code snippet calculates the highest product of three integers in an array by sorting the array in descending order and then multiplying the first three elements. The assumption here is that the array contains at least three integers.
    - However, the function might not always give the correct answer because if there are negative numbers in the array, the product of two negative numbers (which becomes positive) and the largest positive number might be greater than the product of the three largest positive numbers.
        - A more accurate solution would consider both these possibilities:
            - The product of the three largest numbers.
            - The product of the two smallest (which would be the largest negatives) and the largest number.
- The code would look something like this:

```jsx
function maxProduct(arr) {
  arr.sort((a, b) => a - b);
  let n = arr.length;
  return Math.max(arr[0] * arr[1] * arr[n - 1], arr[n - 3] * arr[n - 2] * arr[n - 1]);
}

```

This modified function checks both conditions and returns the maximum of the two potential highest products.

## 11. Build a Simple To-Do List:

Each example demonstrates how to create a simple to-do list where users can enter a task, click an "Add" button to add the task to the list, and see the list of tasks. In the React and Svelte examples, the state is managed using a state variable for the task and an array for the list of tasks. In the Vanilla JavaScript example, the DOM is manipulated directly to update the list of tasks.

### 1. **React.js**:

```jsx
import React, { useState } from 'react';

function TodoList() {
  const [todos, setTodos] = useState([]);
  const [task, setTask] = useState('');

  const addTodo = () => {
    setTodos([...todos, task]);
    setTask('');
  };

  return (
    <div>
      <input type="text" value={task} onChange={(e) => setTask(e.target.value)} />
      <button onClick={addTodo}>Add</button>
      <ul>
        {todos.map((todo, index) => (
          <li key={index}>{todo}</li>
        ))}
      </ul>
    </div>
  );
}

export default TodoList;

```

### 2. **Vanilla JavaScript**:

```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Todo List</title>
</head>
<body>

<input type="text" id="task">
<button onclick="addTodo()">Add</button>
<ul id="todoList"></ul>

<script>
  function addTodo() {
    var task = document.getElementById('task').value;
    var li = document.createElement('li');
	    li.textContent = task;
	    document.getElementById('todoList').appendChild(li);
	    document.getElementById('task').value = '';
  }
</script>

</body>
</html>

```

### 3. **Svelte.js**:

```
<script>
  let todos = [];
  let task = '';

  function addTodo() {
    todos = [...todos, task];
    task = '';
  }
</script>

<input type="text" bind:value={task}>
<button on:click={addTodo}>Add</button>
<ul>
  {#each todos as todo, index}
    <li>{todo}</li>
  {/each}
</ul>

```
