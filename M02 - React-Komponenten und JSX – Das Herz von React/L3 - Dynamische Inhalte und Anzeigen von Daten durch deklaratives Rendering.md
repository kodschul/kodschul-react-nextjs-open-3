
# React und Next.js Schulung

## Deklaratives Rendering – Erstellen dynamischer Inhalte und Anzeigen von Daten in React

Deklaratives Rendering ist ein Konzept in React, bei dem die UI-Komponenten auf Basis der Daten, die ihnen zur Verfügung stehen, gerendert werden. React ermöglicht es, dynamische Inhalte basierend auf dem aktuellen Zustand (state) und den Eigenschaften (props) zu erstellen und automatisch zu aktualisieren.

## Deklaratives Rendering in React

In React ist die Benutzeroberfläche (UI) eine Funktion der Daten. Das bedeutet, dass der UI-Code (JSX) direkt den Zustand und die Eigenschaften einer Komponente reflektiert. Dies ermöglicht eine klare Trennung zwischen dem Zustand der App und deren Darstellung.

### Beispiel: Bedingtes Rendering

Das folgende Beispiel zeigt, wie deklaratives Rendering in React verwendet wird, um dynamische Inhalte anzuzeigen:

```javascript
import React, { useState } from 'react';

const Greeting = () => {
  const [isLoggedIn, setIsLoggedIn] = useState(false);

  return (
    <div>
      {isLoggedIn ? <h1>Willkommen zurück!</h1> : <h1>Bitte loggen Sie sich ein.</h1>}
      <button onClick={() => setIsLoggedIn(!isLoggedIn)}>
        {isLoggedIn ? 'Ausloggen' : 'Einloggen'}
      </button>
    </div>
  );
};

export default Greeting;
```

### Beispiel: Anzeigen von Datenlisten

Ein weiteres Beispiel ist die Anzeige von dynamischen Daten in einer Liste. In React können Arrays direkt in der UI-Komponente gerendert werden:

```javascript
const users = ['Anna', 'Ben', 'Clara'];

const UserList = () => (
  <ul>
    {users.map((user, index) => (
      <li key={index}>{user}</li>
    ))}
  </ul>
);
```

## Deklaratives Rendering in Next.js

Next.js erweitert React um serverseitiges Rendering (SSR) und statische Seitengenerierung. Damit können Daten bereits auf dem Server abgefragt und zur Laufzeit in die Benutzeroberfläche eingebunden werden. Dies ermöglicht es, dynamische Inhalte sehr effizient zu laden.

### Beispiel: Daten vorab abrufen (getServerSideProps)

In Next.js kann mit der Funktion `getServerSideProps` serverseitig Daten abgerufen werden, bevor die Seite gerendert wird:

```javascript
export async function getServerSideProps() {
  const res = await fetch('https://jsonplaceholder.typicode.com/posts');
  const posts = await res.json();

  return {
    props: { posts },
  };
}

const Posts = ({ posts }) => (
  <div>
    <h1>Blog Posts</h1>
    <ul>
      {posts.map(post => (
        <li key={post.id}>{post.title}</li>
      ))}
    </ul>
  </div>
);

export default Posts;
```

In diesem Beispiel werden die Daten vor dem Rendern der Seite abgerufen, sodass der Benutzer sofort eine vorgerenderte Liste von Blog-Beiträgen sieht.

## Fazit

Deklaratives Rendering in React und Next.js ermöglicht eine effiziente Erstellung dynamischer Inhalte und eine klare Trennung von Daten und UI. Durch die Kombination von Reacts Komponentenstruktur und Next.js' serverseitigem Rendering lassen sich leistungsstarke, dynamische Webanwendungen erstellen.
