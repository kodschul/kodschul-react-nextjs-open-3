
# React und NextJS Schulung

## CSS-Module und CSS-in-JS – Vergleich von Libraries

In modernen React- und NextJS-Anwendungen gibt es verschiedene Ansätze, um Stile zu definieren und zu verwalten. In dieser Schulung konzentrieren wir uns auf CSS-Module und CSS-in-JS, und wir vergleichen verschiedene Libraries wie **styled-components**, **emotion**, und **styled-jsx**.

### CSS-Module

CSS-Module ermöglichen die Verwendung von lokalisierten Stilen, sodass CSS-Klassen nur innerhalb einer spezifischen Komponente wirksam sind. Dies verhindert Klassennamenskonflikte und sorgt für saubere und wartbare Stylesheets.

#### Beispiel:

```css
/* Button.module.css */
.button {
  background-color: blue;
  color: white;
}
```

```javascript
import styles from './Button.module.css';

const Button = () => (
  <button className={styles.button}>Click me</button>
);
```

### CSS-in-JS

CSS-in-JS ermöglicht das Schreiben von CSS direkt in JavaScript-Dateien. Dieser Ansatz bietet mehr Flexibilität und Dynamik beim Styling von Komponenten.

#### Vergleich von Libraries:

1. **styled-components**

`styled-components` ist eine beliebte Library für das Schreiben von CSS-in-JS. Sie ermöglicht es Entwicklern, echte CSS-Syntax zu verwenden, um Komponenten zu stylen, und bietet Vorteile wie das automatische Scoping und die Unterstützung von Themen.

```javascript
import styled from 'styled-components';

const Button = styled.button`
  background-color: blue;
  color: white;
  padding: 10px;
`;

const App = () => <Button>Click me</Button>;
```

2. **emotion**

`emotion` ist eine weitere beliebte CSS-in-JS-Bibliothek. Sie bietet eine ähnliche API wie `styled-components`, aber zusätzlich die Möglichkeit, die Leistung durch die Optimierung kritischer CSS-Pfade zu verbessern.

```javascript
/** @jsxImportSource @emotion/react */
import { css } from '@emotion/react';

const buttonStyle = css`
  background-color: blue;
  color: white;
  padding: 10px;
`;

const App = () => <button css={buttonStyle}>Click me</button>;
```

3. **styled-jsx**

`styled-jsx` wird von Next.js nativ unterstützt und ist eine einfache Möglichkeit, Stile zu lokalen Komponenten zu kapseln, ohne eine zusätzliche Bibliothek zu installieren.

```javascript
const Button = () => (
  <>
    <button>Click me</button>
    <style jsx>{`
      button {
        background-color: blue;
        color: white;
        padding: 10px;
      }
    `}</style>
  </>
);
```

### Vergleich und Einsatzmöglichkeiten

| Library             | Vorteile                                  | Nachteile                                 |
|---------------------|-------------------------------------------|-------------------------------------------|
| **styled-components** | - Populär und weit verbreitet <br> - Echte CSS-Syntax  | - Größere Bundle-Größe |
| **emotion**          | - Flexibilität und Performance <br> - Gute Integration | - Komplexere Konfiguration |
| **styled-jsx**       | - Native Unterstützung in Next.js <br> - Einfach zu verwenden | - Weniger Funktionen im Vergleich |

### Fazit

CSS-Module und CSS-in-JS haben ihre jeweiligen Stärken und Schwächen. Für größere Projekte, bei denen Komponenten oft wiederverwendet werden, können CSS-in-JS-Lösungen wie `styled-components` oder `emotion` hilfreich sein. Für kleinere Anwendungen oder spezifische Projekte bietet `styled-jsx` in Kombination mit Next.js eine einfache und effiziente Lösung.

