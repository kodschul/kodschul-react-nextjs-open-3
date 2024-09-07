
# Code Examples from React and Next.js Course - Day 2

## Example 1: Parent and Child Component with Props

```jsx
import React from 'react';

function ChildComponent({ message }) {
  return <p>{message}</p>;
}

function ParentComponent() {
  return <ChildComponent message="Hello from Parent!" />;
}

export default ParentComponent;
```

## Example 2: Counter Component using useState Hook

```jsx
import React, { useState } from 'react';

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increase</button>
    </div>
  );
}

export default Counter;
```

## Example 3: ColorChanger Component

```jsx
import React, { useState } from 'react';

function getRandomColor() {
  const colors = ['red', 'green', 'blue', 'yellow', 'purple'];
  return colors[Math.floor(Math.random() * colors.length)];
}

function ColorChanger() {
  const [color, setColor] = useState('white');

  return (
    <div style={{ backgroundColor: color, height: '100px', width: '100px' }}>
      <button onClick={() => setColor(getRandomColor())}>Change Color</button>
    </div>
  );
}

export default ColorChanger;
```

## Example 4: Styling with CSS Modules

```jsx
import React from 'react';
import styles from './Greeting.module.css';

function Greeting() {
  return <h1 className={styles.title}>Welcome to the Course!</h1>;
}

export default Greeting;
```

## Example 5: Dynamic Button using styled-components

```jsx
import styled from 'styled-components';

const DynamicButton = styled.button`
  background-color: ${(props) => (props.primary ? 'blue' : 'gray')};
  color: white;
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
`;

export default DynamicButton;
```

## Example 6: Using TailwindCSS with React

```jsx
import React from 'react';

function ResponsiveCard() {
  return (
    <div className="bg-white p-6 rounded-lg shadow-lg max-w-sm">
      <h2 className="text-lg font-bold">Responsive Card</h2>
      <p>This is a responsive card using TailwindCSS classes.</p>
    </div>
  );
}

export default ResponsiveCard;
```

## Example 7: ToggleSwitch Component with TailwindCSS and classnames

```jsx
import React, { useState } from 'react';
import classNames from 'classnames';

function ToggleSwitch() {
  const [isOn, setIsOn] = useState(false);

  return (
    <div className="p-4">
      <button
        onClick={() => setIsOn(!isOn)}
        className={classNames('p-2', 'rounded', { 'bg-green-500': isOn, 'bg-red-500': !isOn })}
      >
        {isOn ? 'ON' : 'OFF'}
      </button>
    </div>
  );
}

export default ToggleSwitch;
```

## Example 8: Next.js Static Site Generation (SSG)

```jsx
export async function getStaticProps() {
  return {
    props: {
      message: "This page is statically generated",
    },
  };
}

function HomePage({ message }) {
  return <h1>{message}</h1>;
}

export default HomePage;
```

