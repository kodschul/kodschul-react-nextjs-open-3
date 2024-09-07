
# Code Examples from React and Next.js Course

## Example 1: HelloWorld Component

```jsx
import React from 'react';

function HelloWorld() {
  return <h1>Hello World!</h1>;
}

export default HelloWorld;
```

## Example 2: Greeting Component

```jsx
import React from 'react';

function Greeting() {
  return <h1>Welcome to React Course</h1>;
}

export default Greeting;
```

## Example 3: Simple Addition Function

```js
export function add(a, b) {
  return a + b;
}
```

## Example 4: Using the add function

```jsx
import React from 'react';
import { add } from './mathUtils';

function App() {
  const result = add(2, 3);

  return <div>The result is {result}</div>;
}

export default App;
```

## Example 5: Arrow Function with Destructuring

```js
const cart = [
  { name: "Apple", price: 1.5 },
  { name: "Orange", price: 2 }
];

const showCart = (items) => {
  items.forEach(({ name, price }) => {
    console.log(`Item: ${name}, Price: ${price}`);
  });
};

showCart(cart);
```

## Example 6: Merging Arrays using Spread Operator

```js
const favoriteMovies1 = ["Inception", "The Dark Knight"];
const favoriteMovies2 = ["Interstellar", "Memento"];

const allFavoriteMovies = [...favoriteMovies1, ...favoriteMovies2];
console.log(allFavoriteMovies);
```

## Example 7: Simple Component using Props

```jsx
import React from 'react';

function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}

export default Welcome;
```

## Example 8: Using Hooks in React

```jsx
import React, { useState } from 'react';

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}

export default Counter;
```
