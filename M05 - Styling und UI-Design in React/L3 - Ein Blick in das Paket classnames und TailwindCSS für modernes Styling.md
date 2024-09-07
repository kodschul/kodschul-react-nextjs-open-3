
# React und Next.js Schulung

## Ein Blick in das Paket "classnames" und TailwindCSS für Komponentenstyling

In dieser Schulung werfen wir einen Blick auf das Paket `classnames` und die Integration von TailwindCSS, um CSS-Klassen in React und Next.js effizient zu verwalten und moderne Styling-Methoden anzuwenden.

### Was ist `classnames`?

`classnames` ist ein kleines JavaScript-Tool, das die bedingte Verwaltung von CSS-Klassen vereinfacht. Es erlaubt es, dynamisch Klassen basierend auf bestimmten Bedingungen zu setzen, was besonders bei größeren Projekten nützlich ist.

#### Beispiel:

```javascript
import classNames from 'classnames';

const Button = ({ isPrimary }) => {
  const buttonClass = classNames({
    'btn': true,
    'btn-primary': isPrimary,
    'btn-secondary': !isPrimary,
  });

  return <button className={buttonClass}>Click me</button>;
};
```

In diesem Beispiel wird die CSS-Klasse dynamisch zwischen `btn-primary` und `btn-secondary` geändert, abhängig von der `isPrimary`-Prop.

### Was ist TailwindCSS?

TailwindCSS ist ein modernes Utility-First CSS-Framework, das vordefinierte CSS-Klassen zur Verfügung stellt, um benutzerdefinierte Designs schnell und effizient umzusetzen. Es ist besonders beliebt für die Entwicklung von Komponenten in React und Next.js, da es eine hohe Flexibilität und Wiederverwendbarkeit bietet.

#### Beispiel:

```javascript
const Header = () => {
  return (
    <header className="bg-blue-500 text-white p-4">
      <h1 className="text-xl font-bold">Willkommen bei meiner App</h1>
    </header>
  );
};
```

In diesem Beispiel verwenden wir TailwindCSS-Klassen wie `bg-blue-500` für den Hintergrund und `text-white` für die Textfarbe, um das Styling der Komponente zu definieren.

### Kombination von `classnames` und TailwindCSS

Eine häufige Kombination in React- und Next.js-Projekten ist die Verwendung von `classnames` zusammen mit TailwindCSS, um bedingte Klassen in einer kompakten Weise zu verwalten.

#### Beispiel:

```javascript
import classNames from 'classnames';

const Button = ({ isDisabled }) => {
  const buttonClass = classNames(
    'bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded',
    {
      'opacity-50 cursor-not-allowed': isDisabled,
    }
  );

  return <button className={buttonClass} disabled={isDisabled}>Submit</button>;
};
```

Hier sehen wir, wie `classnames` verwendet wird, um bedingt TailwindCSS-Klassen wie `opacity-50` und `cursor-not-allowed` basierend auf dem `isDisabled`-Zustand hinzuzufügen.

## Praktische Anwendung

Die effiziente Nutzung von `classnames` und TailwindCSS ermöglicht es Entwicklern, konsistentes und wiederverwendbares Styling für Komponenten zu erstellen. In der Praxis kann dies dazu beitragen, komplexe Benutzeroberflächen sauber und strukturiert zu gestalten.

### Beispielprojekt: Portfolio-Seite

- **Komponenten-Styling:** Verwendung von TailwindCSS für Layout und Komponenten
- **Dynamische Klassenverwaltung:** Einsatz von `classnames` für bedingte Stile
- **Responsivität:** TailwindCSS bietet viele eingebaute Klassen für responsives Design.

## Fazit

Mit der Kombination von `classnames` und TailwindCSS haben Entwickler leistungsstarke Werkzeuge zur Hand, um das Styling von React- und Next.js-Komponenten zu optimieren. Diese Tools bieten Flexibilität und Effizienz, besonders wenn es um bedingte Stile und moderne Designansätze geht.
