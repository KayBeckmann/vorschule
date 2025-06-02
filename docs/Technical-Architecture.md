# Technische Architektur

Dieses Dokument beschreibt die technische Architektur der Lern-App.

## Kerntechnologien

- **Frontend-Framework:** [Vue 3](https://vuejs.org/)
  - **Composition API:** Für eine bessere Organisation und Wiederverwendbarkeit von Code.
  - **Vite:** Als schnelles Build-Tool und Entwicklungsserver.
- **Progressive Web App (PWA):**
  - **`vite-plugin-pwa`:** Wurde als Abhängigkeit hinzugefügt und wird für die PWA-Funktionalitäten konfiguriert. Dies beinhaltet:
    - **Service Worker:** Für Caching-Strategien und Offline-Fähigkeit.
    - **Web App Manifest:** Für die Installation auf dem Homescreen und App-ähnliches Verhalten (Konfiguration in `vite.config.ts` und ggf. eine `manifest.json`-Datei im `public/` Ordner oder generiert durch das Plugin).
- **Lokale Datenbank:** [Dexie.js](https://dexie.org/)
  - Ein benutzerfreundlicher Wrapper für IndexedDB.
  - Speicherung von Lerninhalten (z.B. Wortlisten, Übungen), Benutzerfortschritten und Einstellungen direkt im Browser des Nutzers.
- **Programmiersprache:** TypeScript (Projekt wurde mit TypeScript initialisiert).
- **Routing:** Vue Router ist installiert und konfiguriert.
- **State Management:** Pinia ist installiert und wird für das State Management eingesetzt.
- **Code Qualität:**
    - ESLint ist konfiguriert (`eslint.config.ts`).
    - Prettier ist konfiguriert (`.prettierrc.json`).

## Modulstruktur

Die App wird von Grund auf modular gestaltet, um eine einfache Wartung und Erweiterung zu ermöglichen. Jedes Lernfach (Lesen, Mathe, etc.) wird als separates Modul entwickelt.

Die von Vite initialisierte `src/` Struktur bildet die Basis:

```
src/
├── App.vue                   # Haupt-Vue-Komponente
├── main.ts                   # Einstiegspunkt der Anwendung, initialisiert Vue, Router, Pinia
├── assets/                   # Statische Assets wie CSS, Bilder (Basis-CSS vorhanden)
├── components/               # Globale, wiederverwendbare UI-Komponenten (aktuell Vite-Demokomponenten)
├── router/                   # Vue Router Konfiguration (index.ts vorhanden)
├── stores/                   # Pinia Stores (Beispiel counter.ts vorhanden)
├── views/                    # Ansichten/Seiten der App (HomeView.vue, AboutView.vue vorhanden)
│
├── core/                     # NEU (geplant): Kernfunktionalitäten der App
│   ├── db.ts                 #   Dexie Datenbank Initialisierung und Schemata
│   └── pwa/                  #   NEU (geplant): PWA spezifische Logik, falls nicht alles in vite.config.ts landet
│       ├── service-worker.ts #     (Beispiel, falls manueller Service Worker nötig)
│       └── manifest.ts       #     (Beispiel, für dynamische Manifest-Teile)
│
└── modules/                  # NEU (geplant): Einzelne Lernmodule
├── reading/              #   Modul für Lesenlernen
│   ├── components/       #     Spezifische UI-Komponenten für dieses Modul
│   ├── views/            #     Seiten/Ansichten des Lesemoduls
│   ├── store/            #     Pinia Store für das Lesemodul (optional)
│   └── routes.ts         #     Spezifische Routen für dieses Modul
├── math/                 #   Platzhalter für zukünftiges Mathe-Modul
│   └── ...
└── english/              #   Platzhalter für zukünftiges Englisch-Modul
└── ...
```

Die Konfiguration für PWA-Features (Service Worker, Manifest) erfolgt primär über `vite-plugin-pwa` in der `vite.config.ts`. Eine `manifest.webmanifest` oder ähnliches kann im `public/` Ordner abgelegt oder durch das Plugin generiert werden.

### Datenfluss

1.  **Lerninhalte:** Können initial mit der App ausgeliefert oder später dynamisch geladen und in Dexie.js gespeichert werden.
2.  **Benutzerinteraktion:** Aktionen des Nutzers (z.B. Lösen einer Übung) werden von Vue-Komponenten verarbeitet.
3.  **Statusmanagement:** Pinia wird für das State Management innerhalb der Module oder global eingesetzt.
4.  **Datenspeicherung:** Lernfortschritte und -einstellungen werden über Dexie.js (`src/core/db.ts`) in der IndexedDB des Browsers gespeichert.
5.  **Offline-Zugriff:** Der durch `vite-plugin-pwa` generierte Service Worker stellt sicher, dass bereits geladene Inhalte und die App-Shell auch offline verfügbar sind. Dexie.js ermöglicht den Zugriff auf lokal gespeicherte Daten.

## Styling

- Basis-Styling ist in `src/assets/main.css` und `src/assets/base.css` vorhanden.
- Die Entscheidung für ein umfassendes UI-Framework (z.B. Tailwind CSS) oder die konsequente Nutzung von Scoped CSS in Vue-Komponenten für eigene Basis-Komponenten steht noch aus.
- Fokus auf responsives Design für verschiedene Bildschirmgrößen (Desktop, Tablet, Smartphone).

## Build-Prozess & Dev Tools

- **Vite:** Dient als Build-Tool und Entwicklungsserver.
- **Vue DevTools:** Das `vite-plugin-vue-devtools` ist integriert für eine verbesserte Entwicklungserfahrung.
- **TypeScript Überprüfung:** `vue-tsc` wird für die Typüberprüfung eingesetzt.