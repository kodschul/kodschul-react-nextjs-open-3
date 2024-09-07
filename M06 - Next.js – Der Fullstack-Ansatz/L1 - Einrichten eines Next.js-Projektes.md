
# React und Next.js Schulung

## Einrichten eines Next.js-Projektes – Schnellstart mit Next.js

Next.js ist ein leistungsstarkes Framework, das auf React aufbaut und serverseitiges Rendering sowie die Generierung statischer Webseiten unterstützt. Es ermöglicht Entwicklern, performante Webanwendungen mit minimaler Konfiguration zu erstellen.

## Schnellstart mit Next.js

### Voraussetzungen

Um mit Next.js zu starten, benötigst du Node.js und npm (oder yarn), welche die Basis für die Installation und Ausführung der Tools darstellen.

1. Installiere Node.js von [nodejs.org](https://nodejs.org/)
2. Erstelle ein neues Next.js-Projekt:

```bash
npx create-next-app@latest my-nextjs-app
cd my-nextjs-app
npm run dev
```

Das Projekt wird standardmäßig unter `localhost:3000` laufen.

### Ordnerstruktur

Ein neu erstelltes Next.js-Projekt hat eine klar strukturierte Ordnerstruktur:

- `pages/`: Alle Dateien in diesem Ordner repräsentieren Routen der App.
- `public/`: Statische Dateien wie Bilder und CSS-Dateien werden hier abgelegt.
- `styles/`: Stile für die Anwendung, basierend auf CSS oder SCSS.

### Beispiel-Komponente

Next.js verwendet React-Komponenten, um Benutzeroberflächen zu erstellen. Hier ist ein einfaches Beispiel für eine React-Komponente:

```javascript
import React from 'react';

const HomePage = () => {
  return (
    <div>
      <h1>Willkommen zu Next.js!</h1>
    </div>
  );
};

export default HomePage;
```

### Server-seitiges Rendering (SSR)

Einer der Hauptvorteile von Next.js ist die Möglichkeit, Inhalte serverseitig zu rendern, bevor sie an den Client gesendet werden. Dies verbessert die Leistung und SEO.

```javascript
export async function getServerSideProps() {
  return {
    props: {
      message: "Dies ist serverseitig gerendert",
    },
  };
}

const SSRPage = ({ message }) => {
  return <h1>{message}</h1>;
};

export default SSRPage;
```

### Statische Seitengenerierung (SSG)

Next.js unterstützt auch die statische Generierung von Seiten während des Build-Prozesses. Seiten können im Voraus gerendert und als HTML-Dateien bereitgestellt werden.

```javascript
export async function getStaticProps() {
  return {
    props: {
      message: "Dies ist statisch generiert",
    },
  };
}

const SSGPage = ({ message }) => {
  return <h1>{message}</h1>;
};

export default SSGPage;
```

### Link-Navigation

In Next.js wird für die Navigation zwischen den Seiten die `<Link>`-Komponente verwendet, die von Next.js bereitgestellt wird. Dies ermöglicht schnelle, clientseitige Übergänge zwischen den Seiten.

```javascript
import Link from 'next/link';

const Navigation = () => {
  return (
    <nav>
      <ul>
        <li><Link href="/">Home</Link></li>
        <li><Link href="/about">About</Link></li>
      </ul>
    </nav>
  );
};

export default Navigation;
```

## Fazit

Next.js bietet eine umfangreiche Sammlung von Werkzeugen und Funktionen, die es Entwicklern ermöglichen, hochperformante und SEO-freundliche Webanwendungen zu erstellen. Durch die einfache Konfiguration und Nutzung von serverseitigem Rendering sowie statischer Generierung eignet sich Next.js ideal für moderne Webprojekte.
