
# React und Next.js Schulung

## Einrichten von Visual Studio Code für React und Next.js – Das ideale Setup für effizientes Arbeiten

### 1. Installation von Visual Studio Code (VS Code)

Visual Studio Code ist ein kostenloser, leichtgewichtiger Code-Editor, der von Microsoft entwickelt wurde und plattformübergreifend funktioniert. Um VS Code zu installieren, besuchen Sie die [offizielle Website](https://code.visualstudio.com/) und laden Sie die Version für Ihr Betriebssystem herunter.

### 2. Installation von Node.js

Sowohl React als auch Next.js benötigen Node.js, um lokal betrieben zu werden. Stellen Sie sicher, dass Node.js auf Ihrem Computer installiert ist, indem Sie es von der [offiziellen Node.js-Website](https://nodejs.org/) herunterladen und installieren.

Überprüfen Sie die Installation mit:

```bash
node -v
npm -v
```

### 3. Installieren der VS Code-Erweiterungen

VS Code bietet viele Erweiterungen, die die Arbeit mit React und Next.js effizienter machen. Hier sind einige wichtige Erweiterungen:

- **ESLint**: Hilft, Fehler im Code zu finden und Best Practices zu verfolgen.
- **Prettier - Code formatter**: Automatisiert die Code-Formatierung.
- **JavaScript (ES6) code snippets**: Bietet Code-Snippets, um das Schreiben von React-Komponenten zu beschleunigen.
- **Path IntelliSense**: Verbessert die Autovervollständigung von Dateipfaden.
- **Bracket Pair Colorizer**: Farblich markierte Klammern für bessere Übersichtlichkeit.

Um Erweiterungen zu installieren, öffnen Sie den Erweiterungs-Tab in VS Code (Symbol links oder `Strg+Shift+X`), suchen Sie nach den genannten Erweiterungen und klicken Sie auf "Installieren".

### 4. Ein Projekt mit Create React App erstellen

Installieren Sie Create React App, um eine neue React-Anwendung zu erstellen:

```bash
npx create-react-app my-app
cd my-app
npm start
```

Mit diesem Befehl wird ein React-Projekt erstellt und der Entwicklungsserver gestartet. VS Code bietet integrierte Unterstützung für React, einschließlich JSX-Syntax-Highlighting und IntelliSense.

### 5. Next.js in VS Code einrichten

Next.js ist ein Framework für serverseitiges Rendering (SSR) und statische Webanwendungen, das auf React basiert. Um ein Next.js-Projekt zu starten, führen Sie Folgendes aus:

```bash
npx create-next-app@latest
cd my-next-app
npm run dev
```

Dieser Befehl erstellt ein Next.js-Projekt und startet einen Entwicklungsserver. Sie können jetzt mit der Entwicklung beginnen und die App lokal unter `http://localhost:3000` aufrufen.

### 6. VS Code-Settings für React und Next.js optimieren

Einige Einstellungen in VS Code können das Arbeiten mit React und Next.js noch effizienter machen. Öffnen Sie die Benutzereinstellungen in VS Code (`Strg+,`) und fügen Sie die folgenden Einstellungen hinzu:

```json
{
  "editor.formatOnSave": true,
  "files.autoSave": "onFocusChange",
  "editor.tabSize": 2,
  "javascript.updateImportsOnFileMove.enabled": "always",
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true
  }
}
```

Diese Einstellungen sorgen dafür, dass der Code bei jedem Speichern formatiert wird, Tabs auf zwei Leerzeichen gesetzt sind und ESLint-Fehler automatisch behoben werden.

### 7. Verwendung von Live Share

VS Code verfügt über eine Funktion namens Live Share, die es Entwicklern ermöglicht, Code in Echtzeit mit anderen zu teilen und gleichzeitig an einem Projekt zu arbeiten. Diese Erweiterung ist besonders nützlich für Remote-Teams und Code-Reviews.

Installieren Sie Live Share aus dem Erweiterungs-Tab und starten Sie eine Session direkt in VS Code.

## Fazit

Mit diesem Setup für Visual Studio Code sind Sie optimal gerüstet, um effizient mit React und Next.js zu arbeiten. Durch die Verwendung von Erweiterungen, ESLint und Prettier wird der Entwicklungsprozess beschleunigt und Sie können sich auf das Schreiben von sauberem, gut strukturiertem Code konzentrieren.
