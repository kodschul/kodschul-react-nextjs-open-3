
# React und NextJS Schulung

## Module (import und export) – Wie man Module effizient nutzt

In JavaScript und speziell in React und NextJS spielen Module eine zentrale Rolle. Module ermöglichen es, Code in kleinere, wiederverwendbare Teile zu zerlegen, was die Wartbarkeit und Lesbarkeit von Projekten erheblich verbessert.

## Was sind Module?

Ein Modul ist eine Datei, die eine spezifische Funktionalität enthält und deren Code nach außen hin "exportiert" wird. Andere Module können dann diesen Code durch "Import" verwenden. Durch das Aufteilen von Code in Module wird der Entwicklungsprozess übersichtlicher und erleichtert das Wiederverwenden und Testen von Komponenten.

## Exportieren von Modulen

In React und NextJS können Module mit den Schlüsselwörtern `export` oder `export default` exportiert werden.

### Named Export

Beim Named Export können mehrere Dinge aus einem Modul exportiert werden.

```javascript
// utils.js
export const add = (a, b) => a + b;
export const subtract = (a, b) => a - b;
```

### Default Export

Beim Default Export wird eine Standardfunktion oder Komponente exportiert. Es kann nur ein Default Export pro Modul geben.

```javascript
// logger.js
const log = (message) => console.log(message);
export default log;
```

## Importieren von Modulen

Um den Code aus einem Modul zu verwenden, importieren wir ihn mit dem `import`-Schlüsselwort.

### Named Import

Für named Exports wird die Syntax `{}` verwendet.

```javascript
// app.js
import { add, subtract } from './utils';

console.log(add(2, 3)); // 5
console.log(subtract(5, 2)); // 3
```

### Default Import

Für default Exports kann man das importierte Modul ohne geschweifte Klammern nutzen.

```javascript
// app.js
import log from './logger';

log('Hello, World!'); // Hello, World!
```

## Effiziente Nutzung von Modulen

Die effiziente Nutzung von Modulen bedeutet, dass der Code so strukturiert wird, dass er leicht importiert und wiederverwendet werden kann. Hier einige Best Practices:

1. **Kleine, fokussierte Module erstellen**: Jedes Modul sollte sich auf eine spezifische Funktion oder Komponente konzentrieren, um den Code lesbarer und wiederverwendbarer zu machen.

2. **Klare Namenskonventionen**: Die Benennung von Modulen und ihren Exports sollte klar und beschreibend sein, um Missverständnisse zu vermeiden.

3. **Vermeide zyklische Abhängigkeiten**: Achte darauf, dass Module nicht gegenseitig voneinander abhängig sind, um unvorhergesehene Fehler zu verhindern.

## Beispiel: React-Komponenten als Module

In React und NextJS werden Komponenten häufig als Module exportiert und importiert, was die Strukturierung und Wiederverwendung von Code vereinfacht.

### Exportieren einer Komponente

```javascript
// Button.js
import React from 'react';

const Button = ({ label, onClick }) => (
  <button onClick={onClick}>{label}</button>
);

export default Button;
```

### Importieren und Nutzen der Komponente

```javascript
// App.js
import React from 'react';
import Button from './Button';

const App = () => {
  const handleClick = () => {
    alert('Button clicked!');
  };

  return (
    <div>
      <h1>Welcome to the App</h1>
      <Button label="Click Me" onClick={handleClick} />
    </div>
  );
};

export default App;
```

## Fazit

Das Verwenden von Modulen in React und NextJS ist ein essenzieller Bestandteil einer strukturierten und wartbaren Codebasis. Durch effizientes Importieren und Exportieren können Entwickler sauberen und wiederverwendbaren Code schreiben.
