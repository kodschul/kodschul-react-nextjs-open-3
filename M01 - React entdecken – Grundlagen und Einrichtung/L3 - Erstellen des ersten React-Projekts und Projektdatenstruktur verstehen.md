
# React und Next.js Schulung

## Einrichten eines React-Projektes

In dieser Schulung lernst du, wie du ein React-Projekt einrichtest und die Projektdatenstruktur verstehst. React ist eine JavaScript-Bibliothek zur Erstellung von Benutzeroberflächen, während Next.js ein React-Framework ist, das serverseitiges Rendering und statische Webseiten unterstützt.

### Voraussetzungen

Bevor wir beginnen, stelle sicher, dass Node.js und npm (Node Package Manager) auf deinem System installiert sind.

## Erstellen des ersten React-Projekts

### Schritt 1: Initialisiere ein neues React-Projekt

Das Erstellen eines neuen React-Projekts ist mit dem Befehl `npx create-react-app` einfach. Führe folgenden Befehl im Terminal aus:

```bash
npx create-react-app my-first-react-app
```

Dieser Befehl installiert und initialisiert ein neues React-Projekt in einem Ordner mit dem Namen `my-first-react-app`.

### Schritt 2: Navigiere zum Projektordner

```bash
cd my-first-react-app
```

### Schritt 3: Starte das Projekt

Du kannst das React-Projekt lokal starten, indem du folgenden Befehl ausführst:

```bash
npm start
```

Dein erstes React-Projekt wird nun auf `http://localhost:3000` laufen und die standardmäßige React-Begrüßungsseite anzeigen.

## Projektdatenstruktur verstehen

Nachdem das Projekt erstellt wurde, siehst du folgende Struktur:

```
my-first-react-app/
├── node_modules/
├── public/
├── src/
│   ├── App.css
│   ├── App.js
│   ├── App.test.js
│   ├── index.css
│   ├── index.js
│   └── logo.svg
├── .gitignore
├── package.json
├── README.md
└── yarn.lock
```

### Wichtige Verzeichnisse und Dateien:

- **public/**: Enthält statische Dateien wie das `index.html`. Der Inhalt in diesem Ordner wird nicht von React verarbeitet.
- **src/**: Hier befindet sich der Hauptcode der Anwendung.
    - `App.js`: Die Hauptkomponente der App.
    - `index.js`: Der Einstiegspunkt der React-App. Hier wird die App-Komponente in den DOM gerendert.

### Beispiel: Bearbeiten von `App.js`

```javascript
import React from 'react';

function App() {
  return (
    <div className="App">
      <header className="App-header">
        <h1>Willkommen zu deinem ersten React-Projekt!</h1>
      </header>
    </div>
  );
}

export default App;
```

## Einrichten eines Next.js-Projekts

Next.js erleichtert den Einstieg in serverseitiges Rendering und statische Webseiten. Hier ist, wie du ein neues Next.js-Projekt erstellst.

### Schritt 1: Initialisiere ein neues Next.js-Projekt

```bash
npx create-next-app my-first-nextjs-app
```

### Schritt 2: Navigiere zum Projektordner

```bash
cd my-first-nextjs-app
```

### Schritt 3: Starte das Next.js-Projekt

```bash
npm run dev
```

Das Projekt wird auf `http://localhost:3000` gestartet.

## Projektdatenstruktur in Next.js

```
my-first-nextjs-app/
├── node_modules/
├── pages/
│   ├── _app.js
│   ├── index.js
├── public/
├── styles/
├── .gitignore
├── package.json
└── README.md
```

### Wichtige Verzeichnisse und Dateien in Next.js:

- **pages/**: Enthält die Seiten der Anwendung. Jede Datei in diesem Ordner repräsentiert eine Route.
    - `index.js`: Die Hauptseite deiner Anwendung, erreichbar unter `/`.
    - `_app.js`: Hier kannst du die App-Komponente anpassen.
- **public/**: Statische Dateien wie Bilder und andere Medien.
- **styles/**: Hier liegen die CSS-Dateien für die Anwendung.

### Beispiel: Bearbeiten von `index.js`

```javascript
import React from 'react';

export default function Home() {
  return (
    <div>
      <h1>Willkommen zu deinem ersten Next.js-Projekt!</h1>
    </div>
  );
}
```

## Fazit

Mit diesen Schritten hast du erfolgreich dein erstes React- und Next.js-Projekt erstellt und eine grundlegende Projektdatenstruktur verstanden. Beide Tools bieten eine flexible und effiziente Möglichkeit, moderne Webanwendungen zu erstellen.
