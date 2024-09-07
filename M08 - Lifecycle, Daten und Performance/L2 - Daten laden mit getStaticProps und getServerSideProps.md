
# React und Next.js Schulung

## Daten laden mit `getStaticProps` und `getServerSideProps`

In Next.js gibt es zwei Hauptmethoden, um Daten während des Renderns abzurufen: `getStaticProps` und `getServerSideProps`. Diese Methoden ermöglichen es, Daten auf verschiedene Weise in eine Seite zu integrieren, je nach Bedarf der Anwendung.

## `getStaticProps`

`getStaticProps` wird verwendet, um statische Inhalte während der Build-Zeit zu generieren. Dies ist nützlich, wenn die Daten vor der Bereitstellung der Seite bekannt sind und sich nicht häufig ändern.

### Beispiel

```javascript
// pages/index.js
export async function getStaticProps() {
  const res = await fetch('https://api.example.com/data');
  const data = await res.json();

  return {
    props: {
      data,
    },
  };
}

const HomePage = ({ data }) => (
  <div>
    <h1>Statically Generated Data</h1>
    <pre>{JSON.stringify(data, null, 2)}</pre>
  </div>
);

export default HomePage;
```

- In diesem Beispiel wird `getStaticProps` verwendet, um während der Build-Zeit Daten von einer API abzurufen. Diese Daten werden dann als `props` an die Seite übergeben.

### Wann verwenden?
- Für Inhalte, die sich selten ändern
- Für bessere Leistung durch statisches Rendering
- Bei Content Management Systemen (CMS), wo der Inhalt vorab generiert wird

## `getServerSideProps`

`getServerSideProps` wird verwendet, um Daten bei jeder Anfrage zu laden. Diese Methode ist nützlich, wenn sich die Daten dynamisch ändern und auf aktuelle Benutzerinteraktionen oder externe Datenquellen reagieren müssen.

### Beispiel

```javascript
// pages/index.js
export async function getServerSideProps() {
  const res = await fetch('https://api.example.com/data');
  const data = await res.json();

  return {
    props: {
      data,
    },
  };
}

const HomePage = ({ data }) => (
  <div>
    <h1>Server-side Rendered Data</h1>
    <pre>{JSON.stringify(data, null, 2)}</pre>
  </div>
);

export default HomePage;
```

- In diesem Beispiel wird `getServerSideProps` verwendet, um bei jeder Anfrage die neuesten Daten von einer API abzurufen.

### Wann verwenden?
- Für Daten, die sich häufig ändern oder auf Benutzerinteraktionen reagieren müssen
- Wenn die Daten sicherheitsrelevant sind und auf dem Server verarbeitet werden müssen
- Bei datenintensiven Anwendungen wie Dashboards oder Echtzeitanwendungen

## Unterschiede zwischen `getStaticProps` und `getServerSideProps`

| Merkmal                | `getStaticProps`                         | `getServerSideProps`                     |
|------------------------|------------------------------------------|------------------------------------------|
| Zeitpunkt der Ausführung| Während der Build-Zeit                   | Bei jeder Anfrage                       |
| Anwendungsfall         | Statische Inhalte, die sich selten ändern| Dynamische Inhalte, die sich oft ändern  |
| Performance            | Sehr schnell, da die Seite bereits statisch ist | Etwas langsamer, da bei jeder Anfrage gerendert wird |

## Fazit

Durch die Nutzung von `getStaticProps` und `getServerSideProps` bietet Next.js eine flexible Möglichkeit, Daten in Anwendungen zu integrieren, abhängig von den Anforderungen. Für statische Inhalte, die sich selten ändern, ist `getStaticProps` ideal, während `getServerSideProps` für dynamische Inhalte genutzt wird, die häufig aktualisiert werden müssen.
