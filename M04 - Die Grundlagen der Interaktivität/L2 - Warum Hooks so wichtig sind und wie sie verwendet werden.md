
# React und Next.js Schulung

## React Hooks – Warum sind Hooks so wichtig und wie werden sie verwendet?

React Hooks wurden in der Version 16.8 eingeführt und ermöglichen es Entwicklern, den Zustand (State) und andere React-Funktionen in funktionalen Komponenten zu verwenden. Vor Hooks waren Klassenkomponenten notwendig, um solche Funktionen zu verwenden, was zu mehr Komplexität führte. Hooks bieten eine klarere und einfachere Möglichkeit, diese Konzepte in React zu implementieren.

### Wichtige Hooks

#### useState

Der `useState` Hook ermöglicht es, den Zustand in einer funktionalen Komponente zu speichern und zu aktualisieren. Es ist der am häufigsten verwendete Hook, der die Verwaltung des internen Zustands einer Komponente ermöglicht.

```javascript
import React, { useState } from 'react';

const Counter = () => {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
};
```

#### useEffect

Der `useEffect` Hook ermöglicht es, Nebenwirkungen in funktionalen Komponenten zu behandeln, wie z.B. Datenabrufe, direkte DOM-Manipulation oder das Setzen von Timern. Es ist ein Ersatz für die Lifecycle-Methoden wie `componentDidMount`, `componentDidUpdate` und `componentWillUnmount`.

```javascript
import React, { useState, useEffect } from 'react';

const DataFetcher = () => {
  const [data, setData] = useState(null);

  useEffect(() => {
    fetch('https://api.example.com/data')
      .then(response => response.json())
      .then(data => setData(data));
  }, []); // Leeres Array sorgt dafür, dass der Effekt nur einmal ausgeführt wird

  return (
    <div>
      {data ? <p>Data: {JSON.stringify(data)}</p> : <p>Loading...</p>}
    </div>
  );
};
```

#### useContext

Der `useContext` Hook ermöglicht es, auf den globalen Zustand zuzugreifen, der durch einen `Context` in React bereitgestellt wird. Dies ist eine einfache Möglichkeit, Daten durch mehrere Komponenten zu teilen, ohne explizit Props weiterzugeben.

```javascript
import React, { useContext } from 'react';

const ThemeContext = React.createContext('light');

const ThemedComponent = () => {
  const theme = useContext(ThemeContext);

  return <p>Aktuelles Theme: {theme}</p>;
};
```

## Warum sind Hooks so wichtig?

- **Funktionale Komponenten:** Hooks ermöglichen es, Funktionen als Komponenten zu verwenden, ohne dass Klassenkomponenten erforderlich sind, was den Code weniger komplex macht.
- **Code-Wiederverwendbarkeit:** Hooks können leicht extrahiert und wiederverwendet werden, was die Modularität und Wartbarkeit des Codes verbessert.
- **Vereinfachung von Side-Effects:** Hooks wie `useEffect` vereinfachen die Verwaltung von Nebenwirkungen und ermöglichen es Entwicklern, klarer und expliziter mit der Lebenszykluslogik umzugehen.

### Verwendung von Hooks in Next.js

Next.js, ein React-basiertes Framework für serverseitiges Rendering und statische Webseiten, verwendet Hooks auf die gleiche Weise wie React. Die Hooks lassen sich problemlos in Next.js-Seiten und -Komponenten integrieren.

#### Beispiel: Fetching von Daten in einer Next.js-Seite mit `useEffect`

```javascript
import { useState, useEffect } from 'react';

const HomePage = () => {
  const [data, setData] = useState(null);

  useEffect(() => {
    fetch('/api/data')
      .then(response => response.json())
      .then(data => setData(data));
  }, []);

  return (
    <div>
      <h1>Home Page</h1>
      {data ? <p>Data: {JSON.stringify(data)}</p> : <p>Loading...</p>}
    </div>
  );
};

export default HomePage;
```

## Fazit

React Hooks bieten eine moderne und effiziente Möglichkeit, Zustand und andere Funktionen in funktionalen Komponenten zu verwalten. In Kombination mit Next.js ermöglichen Hooks eine performante und einfache Entwicklung von Web-Anwendungen mit serverseitigem Rendering.
