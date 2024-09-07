
# React und Next.js Schulung

## JSX: Die JavaScript-basierte Templatesprache

JSX (JavaScript XML) ist eine Syntaxerweiterung von JavaScript, die verwendet wird, um Strukturen in React zu beschreiben. JSX sieht ähnlich aus wie HTML, aber es handelt sich tatsächlich um JavaScript. Diese Syntax ermöglicht es Entwicklern, die Benutzeroberflächen direkt im JavaScript-Code zu definieren, was das Schreiben von Komponenten übersichtlicher und einfacher macht.

## Wie funktioniert JSX?

JSX erlaubt es, HTML-ähnliche Tags direkt im JavaScript-Code zu verwenden. Dies ist nicht nur syntaktischer Zucker, sondern wird letztendlich in normale JavaScript-Funktionen kompiliert, die React-Elemente erstellen.

```javascript
const element = <h1>Hello, world!</h1>;
```

Im Hintergrund wird dieses JSX-Snippet in folgendes JavaScript kompiliert:

```javascript
const element = React.createElement('h1', null, 'Hello, world!');
```

JSX bietet eine einfache und intuitive Möglichkeit, die Struktur von UI-Komponenten zu definieren.

### Unterschiede zwischen JSX und HTML

- **class vs className**: In JSX wird das HTML-Attribut `class` als `className` verwendet, da `class` ein reserviertes Wort in JavaScript ist.

  ```javascript
  <div className="container"></div>
  ```

- **Selbstschließende Tags**: In JSX müssen alle selbstschließenden Tags auch wirklich geschlossen werden.

  ```javascript
  <img src="image.png" />
  ```

- **JavaScript-Ausdrücke in JSX**: JSX ermöglicht es, JavaScript-Ausdrücke direkt innerhalb geschweifter Klammern zu verwenden.

  ```javascript
  const name = "John";
  const element = <h1>Hello, {name}!</h1>;
  ```

### JSX in Next.js

Next.js erweitert React um serverseitige Rendering-Funktionen und bietet auch für JSX eine nahtlose Integration. Bei Next.js Projekten wird JSX häufig verwendet, um dynamische Seiteninhalte zu erstellen, wobei die Vorteile des serverseitigen Renderings für Performance und SEO genutzt werden.

### Beispiel für eine Next.js Seite mit JSX

```javascript
import React from 'react';

const HomePage = () => {
  const greeting = "Welcome to my Next.js app!";

  return (
    <div>
      <h1>{greeting}</h1>
      <p>This is a simple page created with Next.js and JSX.</p>
    </div>
  );
};

export default HomePage;
```

## Fazit

JSX ist ein zentrales Konzept in React und Next.js, das Entwicklern ermöglicht, deklarative UI-Komponenten mit JavaScript zu schreiben. Es unterscheidet sich von HTML in einigen wichtigen Punkten, bietet aber eine einfachere Möglichkeit, JavaScript und UI-Elemente zu kombinieren.
