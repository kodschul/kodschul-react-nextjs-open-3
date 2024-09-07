
# React & Next.js Schulung

## Routing und API-Routing in Next.js

Next.js ist ein React-Framework, das serverseitiges Rendering (SSR) und statische Seitengenerierung (SSG) unterstützt, was es ideal für leistungsstarke Webanwendungen macht. Ein wesentlicher Bestandteil von Next.js ist das Routing-System, das sich automatisch aus der Ordnerstruktur des Projekts ergibt.

### Statische und Dynamische Routen

#### Statische Routen

In Next.js werden Seiten durch das Erstellen von Dateien im Verzeichnis `pages/` definiert. Jede Datei innerhalb dieses Verzeichnisses wird automatisch als Route interpretiert.

```bash
/pages/index.js      -->  '/'
/pages/about.js      -->  '/about'
/pages/contact.js    -->  '/contact'
```

#### Dynamische Routen

Dynamische Routen werden durch eckige Klammern in der Dateibenennung erstellt, z. B. `[id].js`. Dies ermöglicht es, Routen zu erstellen, die auf Parametern basieren.

```bash
/pages/posts/[id].js  -->  '/posts/1', '/posts/2', etc.
```

Beispiel für eine dynamische Route:

```javascript
import { useRouter } from 'next/router';

const Post = () => {
  const router = useRouter();
  const { id } = router.query;

  return <p>Post: {id}</p>;
};

export default Post;
```

### API Routing in Next.js

Next.js ermöglicht das Erstellen von API-Routen innerhalb des `pages/api/` Verzeichnisses. Jede Datei im Verzeichnis `api` wird zu einem API-Endpunkt.

#### Beispiel einer API-Route

```bash
/pages/api/hello.js  -->  '/api/hello'
```

```javascript
export default function handler(req, res) {
  res.status(200).json({ message: 'Hello, world!' });
}
```

### Dynamische API-Routen

Ähnlich wie bei Seitenrouten können auch API-Routen dynamisch gestaltet werden.

```bash
/pages/api/users/[id].js  -->  '/api/users/1', '/api/users/2', etc.
```

Beispiel:

```javascript
export default function handler(req, res) {
  const { id } = req.query;
  res.status(200).json({ userId: id });
}
```

## Praktische Anwendung

Die praktische Anwendung von Routing und API-Routing in Next.js ermöglicht es Entwicklern, sowohl clientseitige als auch serverseitige Funktionalitäten in ihren Anwendungen zu integrieren. Hier einige Praxisbeispiele:

- **Statische Routen:** Erstellung von Seiten wie Home, About und Contact, die immer gleich sind.
- **Dynamische Routen:** Aufbau von Detailseiten für Blogs oder Produkte, die auf Parametern basieren.
- **API-Routen:** Bereitstellung von serverseitigen Endpunkten für den Abruf und die Verwaltung von Daten.

### Beispielprojekt: Blog-Plattform

- **Statische Seiten:** Home, About, und eine Liste von Blogeinträgen.
- **Dynamische Routen:** Detailseiten für jeden Blogeintrag basierend auf der Blog-ID.
- **API-Routen:** Backend-Endpunkte zum Abrufen von Blogdaten und für das User-Management.

## Fazit

Mit Next.js wird die Verwaltung von Routen, sowohl auf der Seite als auch im Backend, stark vereinfacht. Entwickler können dynamische Routen erstellen und API-Endpunkte integrieren, um komplexe und performante Webanwendungen zu erstellen.
