# Understanding `useState`

## Summary/Motivation
* Students struggle with the concept of useState for data that persists between function calls. Also, there may be some confusion around the array destructuring of useState's return value.

## Script/Outline
* Functions create and destroy all their local variables on each function call
* Therefore, we can't store data between function calls
* Demo simple counter that defines, increments, and console.logs a counter

```js
const simpleCounter = () => {
  let counter = 0;
  counter++;
  console.log(counter);
};

simpleCounter(); // 1
simpleCounter(); // 1
simpleCounter(); // 1
simpleCounter(); // 1
```

* Show how the counter never goes above 1
* The solution is to use a closure (move the counter declaration outside the function)

```js
let counter = 0;

const simpleCounter = () => {
  counter++;
  console.log(counter);
};

simpleCounter(); // 1
simpleCounter(); // 2
simpleCounter(); // 3
simpleCounter(); // 4
```

* Switch over to a React component
* Demonstrate that the same thing happens inside the React function

```jsx
const Counter = () => {
  let counter = 0;

  const incrementCount = () => {
    counter++;
    console.log(counter); // number increments in console, but does not affect the DOM
  };

  return (
    <div>
      <h2>Counter: {counter}</h2>
      <button onClick={incrementCount}>Plus One</button>
    </div>
  );
};

export default Counter;
```

* This appears to work, but our component is never actually called again
* Add a simple input field with a useState to force component re-render

```jsx
import { useState } from 'react';

const Counter = () => {
  const [title, setTitle] = useState('');

  let counter = 0;

  const incrementCount = () => {
    counter++;
    console.log(counter);
  };

  return (
    <div>
      <h2>Counter: {counter}</h2>
      <button onClick={incrementCount}>Plus One</button>
      <input type="text" value={title} onChange={e => setTitle(e.target.value)} />
    </div>
  );
};

export default Counter;
```

* The `counter` variable now resets every time the function gets called
* Creating our own closure solves this problem, but the DOM only updates sporadically
* The correct answer is a closure, but we need to give our data to React so it knows to update the DOM

```jsx
import { useState } from 'react';

const Counter = () => {
  const [title, setTitle] = useState('');
  const [counter, setCounter] = useState(0);

  const incrementCount = () => {
    setCounter(counter + 1);
    console.log(counter);
  };

  return (
    <div>
      <h2>Counter: {counter}</h2>
      <button onClick={incrementCount}>Plus One</button>
      <input type="text" value={title} onChange={e => setTitle(e.target.value)} />
    </div>
  );
};

export default Counter;
```

* Now the DOM refreshes when the counter changes AND the value persists between function calls

## Learning Outcomes
* A better understanding of useState
* Understanding that we could achieve the same result by explicitly using closures, but then React wouldn't know about the value (or it changing)

## Prerequisites
* Basic understanding of React
* Experience with useState

## Position in Curriculum
* W7D1
