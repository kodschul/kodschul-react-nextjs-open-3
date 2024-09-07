
# React & Next.js Schulung

## Pre-Rendering mit Next.js: Static Site Generation (SSG) und Server-Side Rendering (SSR)

Next.js ist ein React-Framework, das zwei wichtige Strategien zur Seitengenerierung unterstützt: **Static Site Generation (SSG)** und **Server-Side Rendering (SSR)**. Diese beiden Ansätze helfen, die Leistung und SEO-Fähigkeiten von Webseiten zu verbessern.

### Static Site Generation (SSG)

Static Site Generation generiert HTML-Dateien zur Build-Zeit. Diese HTML-Dateien werden dann bei jeder Anfrage direkt an den Benutzer ausgeliefert. SSG ist ideal für Seiten, die sich selten ändern und im Voraus generiert werden können.

#### Beispiel:

```javascript
// pages/index.js
import React from 'react';

const HomePage = ({ data }) => {
  return (
    <div>
      <h1>Welcome to the Home Page</h1>
      <p>Data fetched during build: {data}</p>
    </div>
  );
};

// getStaticProps wird während der Build-Zeit ausgeführt
export async function getStaticProps() {
  const data = "Static data during build time";

  return {
    props: {
      data,
    },
  };
}

export default HomePage;
```

### Server-Side Rendering (SSR)

Server-Side Rendering rendert HTML auf dem Server bei jeder Anfrage und sendet es dann an den Client. Dies ist nützlich, wenn die Seite bei jeder Anfrage aktuelle Daten anzeigen soll.

#### Beispiel:

```javascript
// pages/about.js
import React from 'react';

const AboutPage = ({ data }) => {
  return (
    <div>
      <h1>About Us</h1>
      <p>Data fetched on each request: {data}</p>
    </div>
  );
};

// getServerSideProps wird bei jeder Anfrage aufgerufen
export async function getServerSideProps() {
  const data = "Dynamic data fetched during request";

  return {
    props: {
      data,
    },
  };
}

export default AboutPage;
```

### Wann SSG und SSR verwenden?

- **SSG** eignet sich hervorragend für Seiten mit statischen Inhalten, wie Blogs oder Marketing-Seiten. Da die HTML-Seiten im Voraus generiert werden, können sie blitzschnell ausgeliefert werden.
- **SSR** wird verwendet, wenn Inhalte auf dem Server bei jeder Anfrage aktualisiert werden müssen, beispielsweise bei Benutzerprofilen oder Dashboards.

### Praktische Anwendung

Die Verwendung von SSG und SSR in Next.js ist eine Kernkompetenz bei der Entwicklung moderner Webanwendungen. Beide Techniken ermöglichen es Entwicklern, Seiten optimal für Benutzer und Suchmaschinen bereitzustellen.

### Beispielprojekt: Blog-Website

- **SSG**: Die Blogbeiträge können während der Build-Zeit generiert und als statische Seiten bereitgestellt werden.
- **SSR**: Die Kommentare oder Benutzerinteraktionen können bei jeder Anfrage serverseitig gerendert werden, um dynamische Inhalte anzuzeigen.

## Fazit

Next.js ermöglicht es Entwicklern, zwischen SSG und SSR zu wählen, um die beste Performance und Benutzererfahrung für ihre Anwendungen zu gewährleisten. Das Verständnis dieser beiden Techniken ist entscheidend, um mit Next.js leistungsstarke und skalierbare Anwendungen zu erstellen.
