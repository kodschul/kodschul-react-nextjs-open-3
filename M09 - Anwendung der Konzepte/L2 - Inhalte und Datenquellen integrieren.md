
# React und Next.js Schulung

## Typische statische und dynamische Seiten – Inhalte und Datenquellen integrieren

Next.js ist ein Framework, das auf React aufbaut und serverseitiges Rendern sowie die Generierung von statischen Seiten ermöglicht. Es bietet Entwicklern die Möglichkeit, sowohl statische als auch dynamische Seiten zu erstellen und externe Datenquellen nahtlos in die Anwendung zu integrieren.

## Statische Seiten

Statische Seiten werden zur Build-Zeit generiert und sind optimal für Seiten, deren Inhalt sich selten ändert, wie zum Beispiel Blogs oder Produktseiten.

### Beispiel: Statische Seite mit Next.js

```javascript
import React from 'react';

const StaticPage = () => {
  return (
    <div>
      <h1>Willkommen auf der statischen Seite</h1>
      <p>Diese Seite wurde zur Build-Zeit generiert.</p>
    </div>
  );
};

export default StaticPage;
```

### getStaticProps

`getStaticProps` ist eine Next.js-Funktion, die es ermöglicht, Daten zur Build-Zeit abzurufen und in statische Seiten zu integrieren. Dies ist ideal für Seiten, die vorab generiert werden sollen.

```javascript
export async function getStaticProps() {
  const res = await fetch('https://api.example.com/data');
  const data = await res.json();

  return {
    props: {
      data,
    },
  };
}

const StaticPageWithProps = ({ data }) => (
  <div>
    <h1>Statische Seite mit Daten</h1>
    <p>{data.title}</p>
  </div>
);

export default StaticPageWithProps;
```

## Dynamische Seiten

Dynamische Seiten werden bei jeder Anfrage neu generiert und sind ideal für Inhalte, die sich häufig ändern oder personalisiert werden müssen.

### Beispiel: Dynamische Seite mit Next.js

```javascript
import { useRouter } from 'next/router';

const DynamicPage = () => {
  const router = useRouter();
  const { id } = router.query;

  return (
    <div>
      <h1>Willkommen auf der dynamischen Seite mit ID: {id}</h1>
      <p>Diese Seite wird bei jeder Anfrage generiert.</p>
    </div>
  );
};

export default DynamicPage;
```

### getServerSideProps

`getServerSideProps` ermöglicht das Abrufen von Daten bei jeder Anfrage. Diese Methode eignet sich für Seiten, die bei jedem Aufruf aktualisierte Daten benötigen.

```javascript
export async function getServerSideProps(context) {
  const res = await fetch(`https://api.example.com/data/${context.params.id}`);
  const data = await res.json();

  return {
    props: {
      data,
    },
  };
}

const DynamicPageWithServerSideProps = ({ data }) => (
  <div>
    <h1>Dynamische Seite mit Daten</h1>
    <p>{data.title}</p>
  </div>
);

export default DynamicPageWithServerSideProps;
```

## Integration von Datenquellen

Next.js erleichtert die Integration von Datenquellen wie APIs, Datenbanken oder CMS-Systemen durch seine flexiblen Methoden `getStaticProps`, `getServerSideProps` und `API routes`. Externe Datenquellen können sowohl statisch als auch dynamisch eingebunden werden.

### Beispiel: Abruf von Daten aus einer API

```javascript
import React, { useEffect, useState } from 'react';

const FetchData = () => {
  const [data, setData] = useState(null);

  useEffect(() => {
    fetch('https://api.example.com/data')
      .then((response) => response.json())
      .then((data) => setData(data));
  }, []);

  return (
    <div>
      <h1>API Daten</h1>
      {data ? <p>{data.title}</p> : <p>Lade Daten...</p>}
    </div>
  );
};

export default FetchData;
```

## Fazit

React und Next.js bieten flexible Möglichkeiten zur Erstellung statischer und dynamischer Seiten. Statische Seiten sind ideal für Inhalte, die selten aktualisiert werden, während dynamische Seiten sich für häufig aktualisierte oder personalisierte Inhalte eignen. Durch die Integration von externen Datenquellen können vielseitige und leistungsstarke Webanwendungen entwickelt werden.
