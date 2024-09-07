
# React und Next.js Schulung

## Lifecycle und useEffect für HTTP-Requests

In dieser Schulung konzentrieren wir uns darauf, den Lebenszyklus von React-Komponenten zu verstehen und wie man mit dem `useEffect`-Hook in React HTTP-Anfragen effizient ausführt.

### Der Lebenszyklus einer React-Komponente

React-Komponenten haben einen Lebenszyklus, der durch drei Hauptphasen gekennzeichnet ist:

1. **Mounting**: Die Komponente wird zum ersten Mal in die DOM-Struktur eingefügt.
2. **Updating**: Die Komponente wird aktualisiert, wenn sich die `props` oder der `state` ändern.
3. **Unmounting**: Die Komponente wird aus dem DOM entfernt.

Die `useEffect`-Methode ist ein Hook, der es uns ermöglicht, auf diese Phasen zu reagieren, insbesondere während des **Mounting** und **Updating**.

### useEffect Hook

Der `useEffect`-Hook führt Nebeneffekte in Funktionalen Komponenten aus, wie z. B. das Abrufen von Daten oder das Interagieren mit dem Browser.

```javascript
import { useEffect, useState } from 'react';

const DataFetcher = () => {
  const [data, setData] = useState(null);

  useEffect(() => {
    // HTTP-Request ausführen, sobald die Komponente gemountet wird
    fetch('https://jsonplaceholder.typicode.com/posts')
      .then((response) => response.json())
      .then((json) => setData(json));
  }, []); // Das leere Array sorgt dafür, dass der Effekt nur einmal ausgeführt wird, beim Mounting.

  return (
    <div>
      <h1>Daten</h1>
      {data ? data.map((item) => <p key={item.id}>{item.title}</p>) : <p>Laden...</p>}
    </div>
  );
};

export default DataFetcher;
```

### Cleanup in useEffect

Es ist wichtig, das Aufräumen in `useEffect` zu verstehen, insbesondere wenn wir HTTP-Anfragen oder andere Nebenwirkungen haben, die gestoppt werden müssen, wenn die Komponente aus dem DOM entfernt wird.

```javascript
useEffect(() => {
  const controller = new AbortController(); // Controller für die HTTP-Anfrage

  fetch('https://jsonplaceholder.typicode.com/posts', { signal: controller.signal })
    .then((response) => response.json())
    .then((json) => setData(json))
    .catch((error) => {
      if (error.name === 'AbortError') {
        console.log('Request abgebrochen');
      } else {
        console.error(error);
      }
    });

  return () => controller.abort(); // Cleanup: HTTP-Request wird abgebrochen, wenn die Komponente unmountet.
}, []);
```

### Beispiel in Next.js

Next.js ermöglicht es uns, React zu verwenden, aber bietet zusätzlich serverseitiges Rendering (SSR). Hier ein Beispiel, wie `useEffect` in einer Next.js-Seite verwendet wird, um Daten von einem externen API-Endpunkt abzurufen.

```javascript
import { useEffect, useState } from 'react';

const NextPage = () => {
  const [data, setData] = useState(null);

  useEffect(() => {
    async function fetchData() {
      const res = await fetch('https://jsonplaceholder.typicode.com/posts');
      const json = await res.json();
      setData(json);
    }

    fetchData();
  }, []);

  return (
    <div>
      <h1>Daten von der API</h1>
      {data ? data.map((item) => <p key={item.id}>{item.title}</p>) : <p>Laden...</p>}
    </div>
  );
};

export default NextPage;
```

## Fazit

Das Verständnis des Komponentens-Lebenszyklus und die korrekte Verwendung von `useEffect` sind essenziell für eine effiziente Datenverarbeitung in React und Next.js. Durch das Einfügen von HTTP-Requests und das Aufräumen von Ressourcen wird sichergestellt, dass die Anwendung gut performt und keine unnötigen Ressourcen verschwendet.
