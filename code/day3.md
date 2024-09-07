
# Code Examples from React and Next.js Course - Day 3

## Example 1: Link Component for Navigation in Next.js

```jsx
import Link from 'next/link';

function HomePage() {
  return (
    <div>
      <h1>Welcome to the Café</h1>
      <Link href="/menu">Go to Menu</Link>
    </div>
  );
}

export default HomePage;
```

## Example 2: getStaticProps in Next.js

```jsx
export async function getStaticProps() {
  const res = await fetch('https://swapi.dev/api/people/1/');
  const character = await res.json();

  return {
    props: {
      character,
    },
  };
}

function StarWarsCharacter({ character }) {
  return (
    <div>
      <h1>{character.name}</h1>
      <p>Height: {character.height}</p>
    </div>
  );
}

export default StarWarsCharacter;
```

## Example 3: getServerSideProps in Next.js

```jsx
export async function getServerSideProps() {
  const res = await fetch('https://api.openweathermap.org/data/2.5/weather?q=London&appid=YOUR_API_KEY');
  const data = await res.json();

  return {
    props: {
      weather: data,
    },
  };
}

function WeatherPage({ weather }) {
  return (
    <div>
      <h1>Weather in {weather.name}</h1>
      <p>Temperature: {weather.main.temp}K</p>
      <p>Condition: {weather.weather[0].description}</p>
    </div>
  );
}

export default WeatherPage;
```

## Example 4: API Route in Next.js

```js
// pages/api/cookies.js
export default function handler(req, res) {
  res.status(200).json({
    cookies: ['Chocolate Chip', 'Oatmeal Raisin', 'Peanut Butter'],
  });
}
```

## Example 5: Fetching Data from API Route

```jsx
import { useState, useEffect } from 'react';

function CookiesComponent() {
  const [cookies, setCookies] = useState([]);

  useEffect(() => {
    fetch('/api/cookies')
      .then((res) => res.json())
      .then((data) => setCookies(data.cookies));
  }, []);

  return (
    <div>
      <h1>Available Cookies:</h1>
      <ul>
        {cookies.map((cookie, index) => (
          <li key={index}>{cookie}</li>
        ))}
      </ul>
    </div>
  );
}

export default CookiesComponent;
```

## Example 6: Lifecycle in React with useEffect

```jsx
import React, { useState, useEffect } from 'react';

function RandomCat() {
  const [cat, setCat] = useState(null);

  const fetchCat = async () => {
    const res = await fetch('https://api.thecatapi.com/v1/images/search');
    const data = await res.json();
    setCat(data[0].url);
  };

  useEffect(() => {
    fetchCat();
  }, []);

  return (
    <div>
      <h1>Random Cat Image</h1>
      {cat && <img src={cat} alt="Random Cat" />}
      <button onClick={fetchCat}>Fetch New Cat</button>
    </div>
  );
}

export default RandomCat;
```

## Example 7: Performance Optimization in Next.js with getStaticProps

```jsx
export async function getStaticProps() {
  const pizzas = [
    { type: 'Margherita', ingredients: ['Tomato', 'Mozzarella', 'Basil'] },
    { type: 'Pepperoni', ingredients: ['Pepperoni', 'Mozzarella'] },
  ];

  return {
    props: {
      pizzas,
    },
  };
}

function PizzaPage({ pizzas }) {
  return (
    <div>
      <h1>Pizzas:</h1>
      {pizzas.map((pizza, index) => (
        <div key={index}>
          <h2>{pizza.type}</h2>
          <p>Ingredients: {pizza.ingredients.join(', ')}</p>
        </div>
      ))}
    </div>
  );
}

export default PizzaPage;
```

