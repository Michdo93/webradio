# 📻 WebRadio

Ein minimalistisches, modernes und ressourcenschonendes Webradio, das komplett als statische Seite über **GitHub Pages** läuft. Das Besondere: Die Senderliste wird aus einer separaten JSON-Datei geladen. Wenn du neue Sender hinzufügen oder bestehende URLs ändern möchtest, musst du nur die `stations.json` anpassen und committen – GitHub Pages aktualisiert deine App automatisch!

## ✨ Features

- **Einfache Verwaltung:** Sender werden zentral in einer simplen JSON-Datei verwaltet.
- **Modernes Design:** Schicker Dark-Mode im Musik-Streaming-Stil (responsive für Smartphones & Desktops).
- **Vollständige Audio-Kontrolle:** Play/Pause, Mute/Unmute und stufenlose Lautstärkeregelung.
- **Live-Sync:** Beim Klick auf "Play" wird der Live-Stream frisch geladen, um Puffer-Verzögerungen zu minimieren.
- **Serverlos & Kostenlos:** Gehostet auf GitHub Pages, keine Datenbank oder eigener Server notwendig.

---

## 📂 Dateistruktur

Dein Repository benötigt lediglich zwei Kern-Dateien im Hauptverzeichnis (Root):

```text
├── index.html       # Das Frontend, Styling und die Player-Logik (JavaScript)
├── stations.json    # Deine persönliche Senderliste mit Namen und Stream-URLs
└── README.md        # Diese Dokumentation

```

---

## 🛠️ Konfiguration: Sender bearbeiten (`stations.json`)

Die Datei `stations.json` enthält ein Array aus Objekten. Jedes Objekt repräsentiert einen Radiosender. Du kannst beliebig viele Sender hinzufügen, entfernen oder die Reihenfolge ändern.

### Beispiel-Aufbau:

```json
[
  {
    "name": "Deutschlandfunk",
    "url": "[https://st01.sslstream.dlf.de/dlf/01/128/mp3/stream.mp3](https://st01.sslstream.dlf.de/dlf/01/128/mp3/stream.mp3)"
  },
  {
    "name": "Antenne Bayern",
    "url": "[https://stream.antenne.de/antenne-bayern/stream/mp3](https://stream.antenne.de/antenne-bayern/stream/mp3)"
  },
  {
    "name": "SWR3",
    "url": "[https://swr-swr3-live.cast.addradio.de/swr/swr3/live/mp3/128/stream.mp3](https://swr-swr3-live.cast.addradio.de/swr/swr3/live/mp3/128/stream.mp3)"
  }
]

```

> **Wichtig bei den URLs:** Achte darauf, dass die Stream-URLs mit `https://` beginnen. Viele moderne Browser blockieren unverschlüsselte `http://`-Audiostreams auf einer verschlüsselten GitHub Pages Seite (Mixed Content Policy).

---

## 🚀 Anleitung: In 2 Minuten online bringen

Folge diesen einfachen Schritten, um dein eigenes Webradio zu starten:

1. **Repository erstellen:** Erstelle ein neues, öffentliches Repository auf GitHub (z. B. mit dem Namen `mein-webradio`).
2. **Dateien hochladen:** Erstelle oder kopiere die `index.html` und deine angepasste `stations.json` direkt in das Hauptverzeichnis (`/`) dieses Repositories.
3. **GitHub Pages aktivieren:**
* Gehe in deinem Repository auf den Reiter **Settings** (Einstellungen).
* Klicke in der linken Navigationsleiste auf **Pages**.
* Wähle unter *Build and deployment* -> *Source* die Option **Deploy from a branch**.
* Wähle als Branch `main` (oder `master`) und als Ordner `/ (root)`.
* Klicke auf **Save** (Speichern).


4. **Fertig!** Nach etwa 1–2 Minuten generiert GitHub deine Seite. Deine URL lautet dann:
`https://dein-github-benutzername.github.io/mein-webradio/`

---

## 🔄 Updates & Wartung

Wenn du einen neuen Sender hinzufügen möchtest:

1. Öffne die `stations.json` direkt auf GitHub oder lokal in deinem Editor.
2. Füge den neuen Block hinzu (Komma beim vorherigen Element nicht vergessen!).
3. Committe die Änderung (`Commit changes`).
4. **Das war's!** GitHub Pages baut die Seite im Hintergrund neu. Sobald du deine Webradio-URL neu lädst, ist der neue Sender in deiner Liste verfügbar.

---

## 💡 Technische Hinweise

* **Autoplay-Richtlinien:** Die meisten Browser erlauben es Webseiten nicht, Sound direkt beim Laden ohne Benutzerinteraktion abzuspielen. Daher ist beim Aufrufen der Seite standardmäßig der erste Sender ausgewählt, aber pausiert. Ein Klick auf "Play" startet den Stream.
* **Stream-Formate:** Die meisten gängigen Web-Streams nutzen MP3 oder AAC/M4A. Diese werden vom integrierten HTML5 `<audio>`-Element nativ in allen modernen Browsern (Chrome, Firefox, Safari, Edge) unterstützt.

```
