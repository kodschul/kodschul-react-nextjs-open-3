
# React und Next.js Schulung

## API-Routen definieren und HTTP-Requests senden

In dieser Schulung geht es darum, wie API-Routen in Next.js definiert werden und wie man HTTP-Requests zur Interaktion mit Backends sendet. Next.js bietet eine einfache Möglichkeit, API-Endpunkte innerhalb der Anwendung zu erstellen, was eine direkte Kommunikation zwischen Frontend und Backend ermöglicht.

## API-Routen in Next.js

In Next.js können API-Routen im `pages/api` Verzeichnis erstellt werden. Jede Datei innerhalb dieses Verzeichnisses wird automatisch als API-Endpunkt behandelt.

### Beispiel: Erstellen einer API-Route

```javascript
// pages/api/hello.js
export default function handler(req, res) {
  res.status(200).json({ message: 'Hello, API!' });
}
```

Die obige API-Route kann dann unter `http://localhost:3000/api/hello` aufgerufen werden. Sie sendet eine einfache JSON-Antwort zurück.

### Dynamische API-Routen

Next.js ermöglicht auch die Erstellung von dynamischen API-Routen, ähnlich wie dynamische Seitenrouten.

```javascript
// pages/api/[id].js
export default function handler(req, res) {
  const { id } = req.query;
  res.status(200).json({ message: `Received ID: ${id}` });
}
```

Diese Route reagiert auf Anfragen wie `http://localhost:3000/api/123`, wobei `123` als ID an den Endpunkt übergeben wird.

## HTTP-Requests in React und Next.js

Um HTTP-Anfragen an externe APIs oder eigene API-Routen zu senden, wird in React häufig `fetch` oder `axios` verwendet.

### Beispiel: Fetch-Request an eigene API-Routen

```javascript
import { useEffect, useState } from 'react';

export default function Home() {
  const [data, setData] = useState(null);

  useEffect(() => {
    fetch('/api/hello')
      .then((response) => response.json())
      .then((data) => setData(data));
  }, []);

  return (
    <div>
      <h1>API Response</h1>
      {data ? <p>{data.message}</p> : <p>Loading...</p>}
    </div>
  );
}
```

In diesem Beispiel wird ein HTTP-GET-Request an die `/api/hello` Route gesendet, die die Daten zurückgibt und im UI anzeigt.

## Interaktion mit externen Backends

Neben dem Erstellen eigener API-Routen ist es auch üblich, mit externen APIs zu interagieren, z.B. für Authentifizierung, Datenbankzugriffe oder externe Dienste.

### Beispiel: Fetch-Request an eine externe API

```javascript
import { useEffect, useState } from 'react';

export default function Weather() {
  const [weather, setWeather] = useState(null);

  useEffect(() => {
    fetch('https://api.openweathermap.org/data/2.5/weather?q=Berlin&appid=your_api_key')
      .then((response) => response.json())
      .then((data) => setWeather(data));
  }, []);

  return (
    <div>
      <h1>Weather Data</h1>
      {weather ? (
        <p>Temperature: {weather.main.temp}</p>
      ) : (
        <p>Loading...</p>
      )}
    </div>
  );
}
```

Hier wird ein Request an die OpenWeatherMap API gesendet, um Wetterdaten für Berlin abzurufen.

## Fazit

Next.js macht es einfach, API-Routen innerhalb einer Anwendung zu erstellen und zu verwalten. Zudem lassen sich HTTP-Requests sowohl an eigene Routen als auch an externe APIs leicht implementieren. Dies ermöglicht eine effiziente und flexible Interaktion zwischen Frontend und Backend.
