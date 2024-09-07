
# React und Next.js Schulung

## Eventhandler und Zustandsänderungen – Nutzerinteraktionen steuern und verwalten

In React und Next.js spielt die Verwaltung von Nutzerinteraktionen und Zustandsänderungen eine zentrale Rolle bei der Entwicklung interaktiver und dynamischer Webanwendungen. Dieser Abschnitt konzentriert sich auf die praktischen Techniken, um Ereignisse zu behandeln und den Zustand in React-Komponenten zu verwalten.

## Eventhandler in React

In React können Ereignisse wie Klicks, Tastendrücke oder Formulareingaben einfach mit Eventhandlern verwaltet werden. Ein Eventhandler ist eine Funktion, die in einem JSX-Element aufgerufen wird, wenn eine Benutzerinteraktion auftritt.

### Beispiel: Klick-Event

```javascript
import React from 'react';

const ButtonClick = () => {
  const handleClick = () => {
    alert('Button was clicked!');
  };

  return <button onClick={handleClick}>Click me!</button>;
};

export default ButtonClick;
```

Im obigen Beispiel wird bei einem Klick auf den Button die `handleClick`-Funktion aufgerufen, die eine Benachrichtigung anzeigt.

## Zustandsänderungen in React

React verwendet `useState`, um den Zustand in funktionalen Komponenten zu verwalten. Der Zustand ermöglicht es einer Komponente, Werte über die Zeit zu verfolgen und Änderungen entsprechend darzustellen.

### Beispiel: Zähler mit Zustand

```javascript
import React, { useState } from 'react';

const Counter = () => {
  const [count, setCount] = useState(0);

  const increment = () => {
    setCount(count + 1);
  };

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={increment}>Increment</button>
    </div>
  );
};

export default Counter;
```

In diesem Beispiel erhöht der Zähler seinen Wert jedes Mal, wenn der Button geklickt wird. Der Zustand `count` wird mit der Funktion `setCount` aktualisiert.

## Eventhandling und Zustand in Next.js

Next.js ist ein Framework, das auf React basiert. Es erweitert React um serverseitige Rendering-Funktionen und statische Website-Generierung. Eventhandler und Zustandsänderungen funktionieren in Next.js genauso wie in React, jedoch in einem Umgebungskontext, der auch Serverfunktionen unterstützt.

### Beispiel: Formulareingabe mit Zustand in Next.js

```javascript
import { useState } from 'react';

const Form = () => {
  const [inputValue, setInputValue] = useState('');

  const handleInputChange = (e) => {
    setInputValue(e.target.value);
  };

  const handleSubmit = (e) => {
    e.preventDefault();
    alert(`Submitted: ${inputValue}`);
  };

  return (
    <form onSubmit={handleSubmit}>
      <input type="text" value={inputValue} onChange={handleInputChange} />
      <button type="submit">Submit</button>
    </form>
  );
};

export default Form;
```

Hier wird das Eingabefeld durch den Zustand `inputValue` gesteuert, und bei der Übermittlung des Formulars wird eine Benachrichtigung angezeigt.

## Fazit

Eventhandling und Zustandsverwaltung sind wesentliche Bausteine interaktiver Anwendungen in React und Next.js. Durch das Erlernen der effizienten Verwaltung von Benutzerinteraktionen und Zustandsänderungen kannst du dynamische, benutzerfreundliche Anwendungen erstellen, die auf die Bedürfnisse der Benutzer reagieren.
