
# React & Next.js Schulung

## Einführung

In dieser Schulung geht es darum, eine vollständige Anwendung mit React und Next.js zu erstellen. Der Fokus liegt auf der Erstellung einer Basis-App, dem Verwenden von Templates und Komponenten sowie dem Aufbau einer vollständigen Anwendung.


## Basis-App erstellen

Mit Next.js können Sie schnell eine Basis-App erstellen, indem Sie die Standard-Verzeichnisstruktur verwenden und einfache Seiten mit React-Komponenten erstellen.

### Beispiel: Erstellen einer neuen Next.js App

```bash
npx create-next-app@latest my-next-app
cd my-next-app
npm run dev
```

Dieser Befehl erstellt eine neue Next.js-Anwendung und startet den Entwicklungsserver.

## Komponenten erstellen

In React und Next.js werden Komponenten verwendet, um wiederverwendbare Teile der Benutzeroberfläche zu erstellen. Jede Komponente kann Zustandsverwaltung und UI-Logik enthalten.

### Beispiel: Erstellen einer einfachen Komponente

```javascript
const Greeting = ({ name }) => {
  return <h1>Hello, {name}!</h1>;
};

export default Greeting;
```

### Verwendung in einer Next.js-Seite

```javascript
import Greeting from '../components/Greeting';

const HomePage = () => (
  <div>
    <Greeting name="World" />
  </div>
);

export default HomePage;
```

## Templates verwenden

Mit Next.js können Sie Vorlagen (Templates) verwenden, um ähnliche Seitenstrukturen wiederzuverwenden. Zum Beispiel kann ein Layout für mehrere Seiten verwendet werden.

### Beispiel: Layout-Komponente

```javascript
const Layout = ({ children }) => {
  return (
    <div>
      <header>Header Content</header>
      <main>{children}</main>
      <footer>Footer Content</footer>
    </div>
  );
};

export default Layout;
```

### Verwendung eines Layouts in einer Seite

```javascript
import Layout from '../components/Layout';

const AboutPage = () => (
  <Layout>
    <h1>About Us</h1>
    <p>This is the about page.</p>
  </Layout>
);

export default AboutPage;
```

## Eine komplette Anwendung aufbauen

In dieser Schulung werden Sie lernen, wie man eine komplette Anwendung mit Next.js erstellt, einschließlich:

- **Routen:** Next.js verwendet Dateinamen in der `pages`-Struktur, um Routen zu erstellen.
- **API-Routen:** Erstellen Sie serverseitige Endpunkte direkt innerhalb der Anwendung.
- **Datenabruf:** Verwenden Sie `getStaticProps` oder `getServerSideProps`, um Daten während der Build-Zeit oder zur Laufzeit abzurufen.

### Beispiel: Serverseitiges Rendering mit getServerSideProps

```javascript
export async function getServerSideProps() {
  const res = await fetch('https://api.example.com/data');
  const data = await res.json();

  return {
    props: { data },
  };
}

const DataPage = ({ data }) => (
  <div>
    <h1>Data from Server</h1>
    <pre>{JSON.stringify(data, null, 2)}</pre>
  </div>
);

export default DataPage;
```

## Fazit

React und Next.js sind mächtige Werkzeuge, um moderne Webanwendungen zu erstellen. In dieser Schulung haben Sie gelernt, wie man eine Basis-App aufbaut, Komponenten erstellt und Templates verwendet, um eine vollständige Anwendung zu entwickeln. Durch die serverseitigen Features von Next.js können Sie performante und SEO-optimierte Anwendungen erstellen.
