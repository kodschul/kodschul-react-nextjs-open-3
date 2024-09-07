
# React und Next.js Schulung

## Was sind React-Komponenten?

React-Komponenten sind die Grundbausteine einer React-Anwendung. Eine Komponente ist eine eigenständige Einheit, die Logik und Darstellung kapselt und wiederverwendet werden kann. Es gibt zwei Hauptarten von Komponenten in React: **funktionale Komponenten** und **Klassenkomponenten**.

### Funktionale Komponenten

Funktionale Komponenten sind die bevorzugte Methode in modernen React-Anwendungen. Sie werden als einfache JavaScript-Funktionen geschrieben und geben JSX zurück, das die Benutzeroberfläche beschreibt.

```javascript
import React from 'react';

const Greeting = () => {
  return <h1>Hello, World!</h1>;
};

export default Greeting;
```

### Klassenkomponenten

Klassenkomponenten waren früher der Standard in React, werden aber zunehmend durch funktionale Komponenten mit Hooks ersetzt. Sie basieren auf JavaScript-Klassen und haben einen eigenen Zustand und Lebenszyklusmethoden.

```javascript
import React, { Component } from 'react';

class Greeting extends Component {
  render() {
    return <h1>Hello, World!</h1>;
  }
}

export default Greeting;
```

## Aufbau und Struktur von Komponenten

Eine React-Komponente hat typischerweise eine klare Struktur, die Folgendes umfasst:

1. **Import von Abhängigkeiten**: Komponenten beginnen in der Regel mit dem Import der notwendigen Bibliotheken und anderen Komponenten.
2. **Komponentendefinition**: Die Funktion oder Klasse, die die Komponente definiert, folgt als Nächstes.
3. **Render-Methode**: Die `render`-Methode (bei Klassenkomponenten) oder der Rückgabewert (bei funktionalen Komponenten) beschreibt, was die Komponente anzeigt.
4. **JSX**: JSX (JavaScript XML) ist die Syntaxerweiterung, die es ermöglicht, HTML-ähnlichen Code in React zu schreiben.

### Beispiel einer strukturierten Komponente

```javascript
import React from 'react';

const UserCard = ({ name, age }) => {
  return (
    <div className="user-card">
      <h2>{name}</h2>
      <p>Age: {age}</p>
    </div>
  );
};

export default UserCard;
```

## Next.js und serverseitiges Rendern

Next.js ist ein React-Framework, das die Entwicklung von serverseitig gerenderten (SSR) und statisch generierten Webseiten vereinfacht. Es fügt React einige zusätzliche Funktionen hinzu, wie z.B. Routing, serverseitiges Rendering und API-Routen.

### Aufbau von Next.js-Komponenten

In Next.js werden Seiten in einem speziellen Ordner namens `pages` gespeichert. Jede Datei in diesem Ordner wird automatisch als Route in der Anwendung verfügbar gemacht.

```javascript
// pages/index.js
import React from 'react';

const HomePage = () => {
  return <h1>Welcome to the Home Page!</h1>;
};

export default HomePage;
```

## Fazit

React-Komponenten sind der Schlüssel zur Entwicklung wiederverwendbarer, modularer und wartbarer Benutzeroberflächen. Next.js erweitert diese Funktionalitäten, indem es serverseitiges Rendering, Routing und viele weitere nützliche Tools zur Verfügung stellt, die die Entwicklung von Webanwendungen effizienter machen.
