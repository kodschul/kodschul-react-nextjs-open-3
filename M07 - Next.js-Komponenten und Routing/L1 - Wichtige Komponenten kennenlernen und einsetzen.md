
# React und Next.js Schulung

## Wichtige Next.js-Komponenten kennenlernen und einsetzen

In dieser Schulung werden die Kernkomponenten von Next.js erklärt, darunter `Link`, `Image`, `Head`, `Script` und andere. Diese Komponenten sind essenziell, um performante, SEO-freundliche und dynamische Webseiten zu erstellen.

## 1. Link-Komponente

Die `Link`-Komponente von Next.js ersetzt herkömmliche `<a>`-Tags und bietet eine clientseitige Navigation, die eine schnelle und flüssige Benutzererfahrung ermöglicht.

```javascript
import Link from 'next/link';

const Home = () => (
  <div>
    <h1>Willkommen auf meiner Seite</h1>
    <Link href="/about">
      <a>Über uns</a>
    </Link>
  </div>
);
```

### Vorteile:
- Clientseitiges Laden ohne Seitenneuladen
- Optimierung für SEO durch `prefetching`

## 2. Image-Komponente

Die `Image`-Komponente bietet eine optimierte Bilddarstellung, einschließlich automatischer Größenanpassung und Lazy Loading.

```javascript
import Image from 'next/image';

const Profile = () => (
  <div>
    <h1>Mein Profil</h1>
    <Image
      src="/me.jpg"
      alt="Bild von mir"
      width={500}
      height={500}
    />
  </div>
);
```

### Vorteile:
- Automatische Optimierung und Komprimierung
- Unterstützung von modernen Bildformaten wie WebP
- Lazy Loading für bessere Performance

## 3. Head-Komponente

Die `Head`-Komponente ermöglicht es, Metadaten zur Seite hinzuzufügen, wie Titel, Meta-Beschreibungen oder Stylesheets. Diese Komponente wird hauptsächlich für SEO und das Hinzufügen von externen Ressourcen genutzt.

```javascript
import Head from 'next/head';

const About = () => (
  <div>
    <Head>
      <title>Über uns</title>
      <meta name="description" content="Erfahre mehr über uns." />
    </Head>
    <h1>Über uns</h1>
  </div>
);
```

### Vorteile:
- Optimierung für SEO
- Möglichkeit, dynamische Titel und Meta-Daten hinzuzufügen

## 4. Script-Komponente

Mit der `Script`-Komponente kann man externe Skripte wie Google Analytics oder andere Drittanbieter-Tools laden. Next.js optimiert die Reihenfolge und Art des Skriptladens.

```javascript
import Script from 'next/script';

const Home = () => (
  <div>
    <h1>Willkommen auf meiner Seite</h1>
    <Script
      src="https://www.google-analytics.com/analytics.js"
      strategy="lazyOnload"
    />
  </div>
);
```

### Vorteile:
- Steuerung über das Ladeverhalten (z.B. `lazyOnload`, `afterInteractive`)
- Bessere Kontrolle über externe Skripte

## Weitere nützliche Komponenten

### `next/router`

Mit `useRouter` bietet Next.js eine leistungsfähige Möglichkeit, den Router zu verwenden, um programmgesteuerte Navigation durchzuführen.

```javascript
import { useRouter } from 'next/router';

const NavigateButton = () => {
  const router = useRouter();

  return (
    <button onClick={() => router.push('/about')}>
      Zur Über uns Seite
    </button>
  );
};
```

## Fazit

Die vorgestellten Next.js-Komponenten bieten Entwicklern eine strukturierte Möglichkeit, performante, interaktive und SEO-freundliche Webanwendungen zu erstellen. Durch den Einsatz von `Link`, `Image`, `Head` und `Script` lassen sich Anwendungen effizient und benutzerfreundlich gestalten.
