
# React und NextJS Schulung

## Styling mit CSS, SASS – Verschiedene Ansätze für die Gestaltung von Komponenten

In dieser Schulung konzentrieren wir uns auf die unterschiedlichen Möglichkeiten, Komponenten in React und NextJS zu stylen. Dazu gehören:

- Klassisches CSS
- SASS (Syntactically Awesome Stylesheets)
- Modulbasierte und in-line Ansätze

### 1. Klassisches CSS

Das klassische Styling in React und NextJS kann mit externen CSS-Dateien durchgeführt werden. Diese CSS-Dateien werden in die jeweiligen Komponenten importiert.

```css
/* styles.css */
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: lightblue;
}

.text {
  color: darkblue;
  font-size: 20px;
}
```

```javascript
// Component.jsx
import './styles.css';

const MyComponent = () => (
  <div className="container">
    <p className="text">Hello, World!</p>
  </div>
);
```

### 2. CSS Module

CSS Module ist eine Technik, bei der CSS-Styles lokal auf eine bestimmte Komponente beschränkt werden, um Konflikte mit globalen Styles zu vermeiden.

```css
/* styles.module.css */
.container {
  background-color: lightcoral;
}

.text {
  color: white;
}
```

```javascript
// Component.jsx
import styles from './styles.module.css';

const MyComponent = () => (
  <div className={styles.container}>
    <p className={styles.text}>Hello, CSS Modules!</p>
  </div>
);
```

### 3. SASS

SASS ist eine Erweiterung von CSS, die es erlaubt, Variablen, verschachtelte Regeln und Mixins zu verwenden, um den Code besser zu organisieren.

```scss
/* styles.scss */
$primary-color: darkgreen;

.container {
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: lightyellow;

  .text {
    color: $primary-color;
    font-size: 18px;
  }
}
```

```javascript
// Component.jsx
import './styles.scss';

const MyComponent = () => (
  <div className="container">
    <p className="text">Hello, SASS!</p>
  </div>
);
```

### 4. Styled JSX (Next.js spezifisch)

Next.js bietet eine eigene Lösung für das Styling, die als Styled JSX bekannt ist. Sie ermöglicht es Entwicklern, CSS direkt in der Komponente zu schreiben, ohne globale Konflikte zu verursachen.

```javascript
const MyComponent = () => (
  <div className="container">
    <p className="text">Hello, Styled JSX!</p>
    <style jsx>{`
      .container {
        background-color: lightpink;
        padding: 20px;
      }
      .text {
        color: darkred;
      }
    `}</style>
  </div>
);
```

## Fazit

Die Gestaltung von Komponenten in React und NextJS bietet verschiedene Ansätze, die jeweils Vor- und Nachteile haben. Klassisches CSS, CSS-Module, SASS und Next.js spezifische Styled JSX bieten Flexibilität und Struktur, um skalierbare und wartbare Stile für Webanwendungen zu erstellen. Während CSS und SASS für größere Projekte nützlich sind, bietet Styled JSX eine starke Integration in Next.js, die es Entwicklern ermöglicht, Stile lokal zu halten.
