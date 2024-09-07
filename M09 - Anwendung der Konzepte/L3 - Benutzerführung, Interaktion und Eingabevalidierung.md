
# React und Next.js Schulung

## Navigation, Routing und Formularvalidierung mit Formik

Diese Schulung konzentriert sich auf die Grundlagen der Navigation und des Routings in React und Next.js sowie auf die Formularvalidierung mit dem beliebten Formik-Bibliothek. Ziel ist es, Ihnen zu zeigen, wie Sie eine effiziente Benutzerführung, Interaktionen und Eingabevalidierung in Ihren Anwendungen implementieren können.

### 1. Navigation in React und Next.js

In React und Next.js wird die Navigation durch Link-Komponenten gesteuert. In Next.js ist der `next/link` eine wichtige Methode, um zwischen Seiten zu wechseln.

```javascript
import Link from 'next/link';

const NavigationExample = () => (
  <nav>
    <ul>
      <li>
        <Link href="/">
          <a>Home</a>
        </Link>
      </li>
      <li>
        <Link href="/about">
          <a>About</a>
        </Link>
      </li>
    </ul>
  </nav>
);
```

### 2. Routing in Next.js

Next.js verwendet ein Dateibasiertes Routing-System, bei dem jede Datei in dem `pages`-Ordner als eine Route betrachtet wird. Beispielsweise wird die Datei `pages/about.js` zur Route `/about`.

#### Dynamische Routen

Next.js unterstützt auch dynamische Routen, die durch Dateinamen in eckigen Klammern definiert werden.

```javascript
// pages/blog/[id].js
import { useRouter } from 'next/router';

const BlogPost = () => {
  const router = useRouter();
  const { id } = router.query;

  return <p>Post: {id}</p>;
};

export default BlogPost;
```

### 3. Formularvalidierung mit Formik

Formik ist eine leistungsstarke Bibliothek, die die Handhabung von Formularen und Validierung vereinfacht. Sie erlaubt eine einfache Verwaltung von Formularzustand, Validierung und Fehlerbehandlung.

#### Beispiel: Einfaches Formular mit Validierung

In diesem Beispiel erstellen wir ein einfaches Login-Formular, das mit Formik verwaltet wird und eine Validierung durchführt.

```javascript
import React from 'react';
import { Formik, Field, Form, ErrorMessage } from 'formik';
import * as Yup from 'yup';

const LoginForm = () => {
  return (
    <Formik
      initialValues={{ email: '', password: '' }}
      validationSchema={Yup.object({
        email: Yup.string().email('Ungültige E-Mail-Adresse').required('Erforderlich'),
        password: Yup.string().min(6, 'Muss mindestens 6 Zeichen lang sein').required('Erforderlich'),
      })}
      onSubmit={(values, { setSubmitting }) => {
        setTimeout(() => {
          console.log(JSON.stringify(values, null, 2));
          setSubmitting(false);
        }, 400);
      }}
    >
      <Form>
        <label htmlFor="email">Email</label>
        <Field name="email" type="email" />
        <ErrorMessage name="email" />

        <label htmlFor="password">Passwort</label>
        <Field name="password" type="password" />
        <ErrorMessage name="password" />

        <button type="submit">Einloggen</button>
      </Form>
    </Formik>
  );
};

export default LoginForm;
```

### 4. Benutzerführung und Interaktion

Eine reibungslose Benutzerführung ist entscheidend für die Benutzererfahrung. Hier sind einige bewährte Praktiken:
- Klare und konsistente Navigation
- Informative Feedbackmechanismen (Ladeanimationen, Bestätigungsnachrichten)
- Effiziente Formularvalidierung und hilfreiche Fehlermeldungen

## Fazit

In dieser Schulung haben wir die wesentlichen Techniken zur Navigation und Routing in React und Next.js behandelt sowie ein Beispiel für Formularvalidierung mit Formik gezeigt. Diese Tools sind unerlässlich für eine moderne und benutzerfreundliche Webanwendung.
