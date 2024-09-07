
# React und Next.js Schulung

## Vor-Rendern dynamischer Routen und Abfragen während des Pre-Renderings

Next.js ist ein Framework, das auf React aufbaut und das Erstellen von serverseitig gerenderten (SSR) und statischen Webseiten (SSG) erleichtert. Eine der Hauptfunktionen von Next.js ist die Fähigkeit, Seiten vor dem Rendern vorzubereiten, insbesondere bei dynamischen Routen.

### Dynamische Routen in Next.js

Next.js ermöglicht es, dynamische Routen zu erstellen, indem man eckige Klammern in den Dateinamen verwendet. Zum Beispiel könnte eine Datei in `/pages/[id].js` eine Seite darstellen, die von einem bestimmten `id`-Parameter abhängt.

```javascript
import { useRouter } from 'next/router';

const Post = () => {
  const router = useRouter();
  const { id } = router.query;

  return <p>Post: {id}</p>;
};

export default Post;
```

In diesem Beispiel kann die Seite unter `/posts/1`, `/posts/2`, usw. aufgerufen werden, wobei `id` dynamisch ersetzt wird.

### Vor-Rendern dynamischer Routen

Mit `getStaticPaths` und `getStaticProps` können dynamische Seiten vor dem Rendern erzeugt werden, um statische Dateien zu generieren. Das verbessert die Performance, da die Seiten bereits bei der Build-Zeit generiert werden.

```javascript
export async function getStaticPaths() {
  const paths = [{ params: { id: '1' } }, { params: { id: '2' } }];
  return { paths, fallback: false };
}

export async function getStaticProps({ params }) {
  const post = await getPostData(params.id);
  return { props: { post } };
}

const Post = ({ post }) => {
  return <div>{post.title}</div>;
};

export default Post;
```

In diesem Beispiel wird für jede ID eine statische Seite erzeugt, und die Daten werden während des Builds abgerufen.

### Abfragen während des Pre-Renderings

Next.js ermöglicht es, API-Abfragen während des Pre-Renderings durchzuführen. Mit `getServerSideProps` können Daten bei jeder Anfrage auf dem Server geladen und dann an die Seite weitergegeben werden.

```javascript
export async function getServerSideProps(context) {
  const res = await fetch(`https://jsonplaceholder.typicode.com/posts/${context.params.id}`);
  const post = await res.json();

  return {
    props: { post }, // wird als Prop an die Seite übergeben
  };
}

const Post = ({ post }) => {
  return <div>{post.title}</div>;
};

export default Post;
```

Mit `getServerSideProps` wird die Seite bei jeder Anfrage neu generiert, was besonders nützlich ist, wenn die Daten oft aktualisiert werden müssen.

## Performance-Optimierungen in Next.js

### Statische Optimierung

Statische Seiten in Next.js werden einmal zur Build-Zeit erstellt und sind extrem performant, da sie als einfache HTML-Dateien ausgeliefert werden.

### Lazy Loading von Komponenten

Lazy Loading oder das Laden von Komponenten bei Bedarf ist eine Technik, um die anfängliche Ladezeit zu reduzieren. Dies kann mit Reacts `React.lazy` und `Suspense` erreicht werden.

```javascript
import React, { Suspense, lazy } from 'react';

const LazyComponent = lazy(() => import('../components/LazyComponent'));

const Page = () => (
  <Suspense fallback={<div>Loading...</div>}>
    <LazyComponent />
  </Suspense>
);

export default Page;
```

### Bildoptimierung

Next.js bietet eine integrierte Bildoptimierung mit dem `<Image>`-Component, die Bilder basierend auf dem Viewport und der Gerätedichte automatisch optimiert.

```javascript
import Image from 'next/image';

const MyImage = () => (
  <Image
    src="/me.png"
    alt="Picture of me"
    width={500}
    height={500}
  />
);
```

### Incremental Static Regeneration (ISR)

ISR ermöglicht es, einzelne Seiten nach der ersten Bereitstellung zu aktualisieren, ohne die gesamte Seite neu zu bauen. Das hilft bei der Kombination von statischen Seiten und dynamischen Inhalten.

```javascript
export async function getStaticProps() {
  const res = await fetch('https://api.example.com/data');
  const data = await res.json();

  return {
    props: { data },
    revalidate: 10, // ISR: Seite wird alle 10 Sekunden neu generiert
  };
}
```

## Fazit

Next.js bietet leistungsstarke Techniken für das Vor-Rendern von Seiten und das Abrufen von Daten während des Pre-Renderings. Durch diese Methoden können Entwickler Anwendungen erstellen, die schnell laden und dynamische Inhalte effizient verwalten.
