# Technische Architektur

Dieses Dokument beschreibt die geplante technische Architektur der Lern-App.

## Kerntechnologien

- **Frontend-Framework:** [Vue 3](https://vuejs.org/)
  - **Composition API:** Für eine bessere Organisation und Wiederverwendbarkeit von Code.
  - **Vite:** Als schnelles Build-Tool und Entwicklungsserver.
- **Progressive Web App (PWA):**
  - **Service Worker:** Für Caching-Strategien und Offline-Fähigkeit.
  - **Web App Manifest:** Für die Installation auf dem Homescreen und App-ähnliches Verhalten.
- **Lokale Datenbank:** [Dexie.js](https://dexie.org/)
  - Ein benutzerfreundlicher Wrapper für IndexedDB.
  - Speicherung von Lerninhalten (z.B. Wortlisten, Übungen), Benutzerfortschritten und Einstellungen direkt im Browser des Nutzers.
- **Programmiersprache:** JavaScript (oder TypeScript, falls für das Projekt entschieden).

## Modulstruktur

Die App wird von Grund auf modular gestaltet, um eine einfache Wartung und Erweiterung zu ermöglichen. Jedes Lernfach (Lesen, Mathe, etc.) wird als separates Modul entwickelt.

### Beispielhafte Modulstruktur (Verzeichnisstruktur angedacht):

src/
├── App.vue
├── main.js (oder main.ts)
├── assets/
├── components/ (globale, wiederverwendbare UI-Komponenten)
├── core/ (Kernfunktionalitäten der PWA, Dexie-Setup, Routing)
│ ├── db.js (Dexie Datenbank Initialisierung und Schemata)
│ ├── pwa.js (Service Worker Registrierung etc.)
│ └── router.js (Vue Router Konfiguration)
├── modules/
│ ├── reading/ (Modul für Lesenlernen)
│ │ ├── components/ (spezifische UI-Komponenten für dieses Modul)
│ │ ├── views/ (Seiten/Ansichten des Lesemoduls)
│ │ ├── store/ (Pinia Store für das Lesemodul, optional)
│ │ └── routes.js (spezifische Routen für dieses Modul)
│ ├── math/ (Platzhalter für zukünftiges Mathe-Modul)
│ │ └── ...
│ └── english/ (Platzhalter für zukünftiges Englisch-Modul)
│ └── ...
├── store/ (globaler Pinia Store, falls benötigt)
└── views/ (globale Ansichten wie Home, About etc.)

### Datenfluss

1.  **Lerninhalte:** Können initial mit der App ausgeliefert oder später dynamisch geladen und in Dexie.js gespeichert werden.
2.  **Benutzerinteraktion:** Aktionen des Nutzers (z.B. Lösen einer Übung) werden von Vue-Komponenten verarbeitet.
3.  **Statusmanagement:** (Optional) [Pinia](https://pinia.vuejs.org/) kann für das State Management innerhalb der Module oder global eingesetzt werden.
4.  **Datenspeicherung:** Lernfortschritte und -einstellungen werden über Dexie.js in der IndexedDB des Browsers gespeichert.
5.  **Offline-Zugriff:** Der Service Worker stellt sicher, dass bereits geladene Inhalte und die App-Shell auch offline verfügbar sind. Dexie.js ermöglicht den Zugriff auf lokal gespeicherte Daten.

## Styling

- Entweder Scoped CSS in Vue-Komponenten, CSS Modules oder ein Utility-First Framework wie [Tailwind CSS](https://tailwindcss.com/). Die Entscheidung hierfür wird noch getroffen.
- Fokus auf responsives Design für verschiedene Bildschirmgrößen (Desktop, Tablet, Smartphone).
