
# React und Next.js Schulung

## React-Workshop zur Einführung – Was ist React und warum wird es so häufig verwendet?

React ist eine JavaScript-Bibliothek zur Erstellung von Benutzeroberflächen, die ursprünglich von Facebook entwickelt wurde. React erleichtert die Entwicklung von wiederverwendbaren UI-Komponenten, die dynamische und interaktive Benutzeroberflächen erzeugen. Es wird in der Webentwicklung sehr häufig eingesetzt, da es Entwicklern ermöglicht, effizient skalierbare Anwendungen zu bauen.

## Warum React verwenden?

- **Komponentenbasiert:** React bricht Benutzeroberflächen in kleine, wiederverwendbare Teile, sogenannte Komponenten, auf.
- **Virtueller DOM:** React verwendet einen virtuellen DOM (Document Object Model), der Änderungen im echten DOM effizienter macht und die Leistung verbessert.
- **Unidirektionaler Datenfluss:** Der Datenfluss in React erfolgt in eine Richtung, was die Fehlerbehebung erleichtert und die Struktur der Anwendung vereinfacht.

## Kernkonzepte

### Komponenten

Eine React-Komponente kann entweder eine Funktion oder eine Klasse sein, die eine UI beschreibt.

```javascript
import React from 'react';

const HelloWorld = () => {
  return <h1>Hello, World!</h1>;
};
```

### JSX (JavaScript XML)

JSX ermöglicht es Entwicklern, HTML-ähnlichen Code direkt in JavaScript zu schreiben. Dieser wird von React in reguläres JavaScript umgewandelt.

```javascript
const element = <h1>Hello, JSX!</h1>;
```

### Props und State

- **Props**: Kurz für „Properties“, werden genutzt, um Daten von einem Elternteil zu einem Kind in der Komponenten-Hierarchie weiterzugeben.
- **State**: Der State speichert dynamische Werte, die sich im Laufe der Zeit ändern können, und wird innerhalb einer Komponente verwaltet.

```javascript
import React, { useState } from 'react';

const Counter = () => {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>{count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
};
```

## Einführung in Next.js

Next.js ist ein Framework, das auf React aufbaut und viele nützliche Features für die Entwicklung von modernen Webanwendungen bietet. Es erleichtert das Server-Side Rendering (SSR) und die statische Generierung, was die SEO-Performance und Ladezeiten verbessert.

### Vorteile von Next.js

- **Server-Side Rendering (SSR)**: Inhalte werden auf dem Server gerendert, bevor sie an den Client geschickt werden, was eine bessere SEO und schnellere Ladezeiten ermöglicht.
- **File-based Routing**: Mit Next.js kann die Dateistruktur im Projekt direkt die Routen für die Anwendung bestimmen.
- **API-Routen**: Next.js ermöglicht es Entwicklern, einfache API-Endpunkte in derselben Anwendung zu erstellen.

### Beispiel für eine Next.js Seite

```javascript
import React from 'react';

const Home = () => {
  return (
    <div>
      <h1>Welcome to Next.js!</h1>
    </div>
  );
};

export default Home;
```

## Praktische Anwendung

Während dieser Schulung werden Sie eine einfache Next.js-App erstellen, die dynamische Inhalte anzeigt, Daten über API-Routen abruft und mit React-Komponenten interagiert.

### Beispielprojekt: Blog-App

- **React-Komponenten**: Wiederverwendbare UI-Komponenten wie Header, Footer und Artikel.
- **Next.js-Routing**: Dynamisches Routing basierend auf Dateistrukturen.
- **API-Interaktionen**: Abrufen und Anzeigen von Blog-Artikeln von einer externen API.

## Fazit

React und Next.js bieten zusammen eine leistungsstarke Grundlage für die moderne Webentwicklung. Während React Ihnen ermöglicht, hochgradig interaktive und dynamische Benutzeroberflächen zu erstellen, bietet Next.js die Tools, um diese Anwendungen schnell, SEO-freundlich und leicht wartbar zu machen.
