
# React & Next.js Schulung

## Classes, Functions und Objects – JavaScript-Grundlagen für React verstehen

In dieser Schulung lernst du die Grundlagen von JavaScript, die für die Arbeit mit React und Next.js besonders wichtig sind. Der Fokus liegt auf den Konzepten von Klassen, Funktionen und Objekten, die für das Verständnis und die effiziente Entwicklung in React und Next.js entscheidend sind.

## Classes

In JavaScript ermöglichen Klassen das Erstellen von Objekten mit spezifischen Eigenschaften und Methoden. In React werden Klassenkomponenten verwendet, um komplexe Benutzeroberflächen zu erstellen.

### Beispiel einer Klasse:

```javascript
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  greet() {
    console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
  }
}

const person1 = new Person('Alice', 30);
person1.greet(); // "Hello, my name is Alice and I am 30 years old."
```

### Klassenkomponenten in React:

```javascript
import React, { Component } from 'react';

class Welcome extends Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}

export default Welcome;
```

## Functions

Funktionen sind grundlegende Bausteine in JavaScript und werden in React zur Definition von Funktionalen Komponenten verwendet. Sie sind oft einfacher und flexibler als Klassenkomponenten.

### Beispiel einer Funktion:

```javascript
function greet(name) {
  return `Hello, ${name}!`;
}

console.log(greet('Alice')); // "Hello, Alice!"
```

### Funktionale Komponenten in React:

```javascript
import React from 'react';

const Welcome = (props) => {
  return <h1>Hello, {props.name}</h1>;
};

export default Welcome;
```

## Objects

Objekte sind Sammlungen von Schlüssel-Wert-Paaren und sind ein zentrales Konzept in JavaScript. Sie ermöglichen die Organisation von Daten und die Erstellung komplexer Strukturen.

### Beispiel eines Objekts:

```javascript
const person = {
  name: 'Alice',
  age: 30,
  greet: function() {
    console.log(`Hello, my name is ${this.name}`);
  },
};

person.greet(); // "Hello, my name is Alice"
```

### Verwendung von Objekten in React:

Objekte können in React als Zustand (State) verwendet werden, um Daten zu speichern, die sich ändern können. Dies ist besonders in Klassen- und funktionalen Komponenten wichtig.

```javascript
import React, { useState } from 'react';

const UserProfile = () => {
  const [user, setUser] = useState({
    name: 'Alice',
    age: 30,
  });

  return (
    <div>
      <h1>{user.name}</h1>
      <p>Age: {user.age}</p>
    </div>
  );
};

export default UserProfile;
```

## Praktische Anwendung in Next.js

Next.js baut auf React auf und bietet zusätzliche Funktionen wie serverseitiges Rendering (SSR) und statische Seitengenerierung (SSG). Hier ein einfaches Beispiel einer Next.js-Seite, die Klassen und Funktionen verwendet:

```javascript
// pages/index.js
import React from 'react';

class Home extends React.Component {
  static async getInitialProps() {
    return { name: 'Next.js Developer' };
  }

  render() {
    return <h1>Welcome, {this.props.name}</h1>;
  }
}

export default Home;
```

## Fazit

Das Verständnis von Klassen, Funktionen und Objekten in JavaScript ist der Schlüssel zu effizientem Arbeiten mit React und Next.js. Diese Grundlagen bilden die Basis für den Aufbau skalierbarer und performanter Webanwendungen.
