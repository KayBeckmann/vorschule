# Projektplan: Lern-App für Kinder

**Version:** 1.0
**Datum:** 01.06.2025
**Status:** In Planung

## 1. Zielsetzung

Ziel dieses Plans ist es, die Entwicklung der Lern-App für Kinder von der initialen Projekt-Einrichtung bis zur Fertigstellung des ersten funktionsfähigen Moduls ("Lesenlernen - Grundlagen") strukturiert darzustellen.

## 2. Wichtige Dokumente und Referenzen

- Product Requirement Document (PRD)
- README.md (für Setup und allgemeine Infos)
- GitHub Wiki:
  - [[Project-Vision-and-Goals]]
  - [[Technical-Architecture]]
  - [[Module-Reading-Literacy]]

## 3. Phasen und Schritte

### Phase 0: Projekt-Setup und Grundlagen (Woche 1)

- **[ ] Schritt 0.1: Entwicklungsumgebung einrichten**
  - [ ] Node.js (aktuelle LTS-Version) und npm/yarn installieren/prüfen.
  - [ ] Git installieren/prüfen.
  - [ ] Code-Editor (z.B. VS Code) mit empfohlenen Vue/ESLint Extensions einrichten.
- **[ ] Schritt 0.2: Vue 3 Projekt initialisieren**
  - [ ] Neues Vue 3 Projekt mit Vite erstellen (`npm create vue@latest` oder `yarn create vue`).
  - [ ] TypeScript oder JavaScript als Sprache auswählen (gemäß Entscheidung).
  - [ ] ESLint und Prettier für Code-Qualität und Formatierung einrichten.
- **[ ] Schritt 0.3: Git-Repository einrichten**
  - [ ] Lokales Git-Repository initialisieren (`git init`).
  - [ ] GitHub-Repository erstellen (privat oder öffentlich).
  - [ ] Lokales Repository mit GitHub verbinden und ersten Commit pushen.
  - [ ] `README.md` (aus Vorlage) und `LICENSE.md` hinzufügen und committen.
  - [ ] `.gitignore` Datei anpassen (Standard von Vite ist meist gut, ggf. `.env` etc. hinzufügen).
- **[ ] Schritt 0.4: Grundlegende PWA-Features vorbereiten**
  - [ ] Web App Manifest (`manifest.json` oder `manifest.webmanifest`) erstellen und konfigurieren (App-Name, Icons, Start-URL, Display-Mode).
  - [ ] Einfachen Service Worker für Caching der App-Shell erstellen und registrieren (z.B. mit Vite PWA Plugin oder manuell).
  - [ ] Platzhalter-Icons für die PWA erstellen und einbinden.
- **[ ] Schritt 0.5: Dexie.js integrieren**
  - [ ] Dexie.js als Abhängigkeit hinzufügen (`npm install dexie` oder `yarn add dexie`).
  - [ ] Eine erste Datenbank-Struktur (`db.js` oder `db.ts`) definieren (z.B. eine einfache Tabelle für Benutzereinstellungen oder erste Lerninhalte).
  - [ ] Testweise Daten schreiben und lesen, um die Integration zu verifizieren.

### Phase 1: Entwicklung der Kern-App-Struktur (Woche 2-3)

- **[ ] Schritt 1.1: Grundlegendes Layout und UI-Komponenten definieren**
  - [ ] Haupt-Layout-Komponente erstellen (`App.vue` überarbeiten, ggf. `DefaultLayout.vue`).
  - [ ] Platzhalter für Header, Hauptinhaltsbereich und ggf. Footer/Navigation erstellen.
  - [ ] Entscheidung für ein UI-Framework (z.B. Vuetify, Quasar, Tailwind CSS) treffen oder eigene Basis-Komponenten planen.
  - [ ] Erste wiederverwendbare UI-Komponenten erstellen (z.B. `BaseButton.vue`, `Card.vue`).
- **[ ] Schritt 1.2: Routing einrichten**
  - [ ] Vue Router installieren und konfigurieren.
  - [ ] Erste Routen definieren (z.B. Startseite, Lernmodul-Übersicht (Platzhalter), Einstellungen (Platzhalter)).
- **[ ] Schritt 1.3: Modulare Architektur vorbereiten**
  - [ ] Verzeichnisstruktur für Module anlegen (z.B. `src/modules/`) gemäß [[Technical-Architecture]].
  - [ ] Überlegen, wie Module dynamisch geladen oder registriert werden können (für spätere Erweiterungen).
  - [ ] Routen-Konfiguration so gestalten, dass Modul-Routen einfach hinzugefügt werden können.
- **[ ] Schritt 1.4: Einfache Navigation implementieren**
  - [ ] Navigation zwischen den Hauptbereichen der App ermöglichen (auch wenn diese noch Platzhalter sind).

### Phase 2: Entwicklung des Leselernmoduls - Teil 1 (Buchstaben & Laute) (Woche 4-6)

- **[ ] Schritt 2.1: Datenmodell für Buchstaben und Laute entwerfen**
  - [ ] Struktur für die Speicherung von Buchstaben (Groß-/Kleinbuchstaben, Graphem), zugehörigen Lauten (Phonem, Audio-Referenz) und Beispielbildern definieren.
  - [ ] Erste Beispieldaten für Buchstaben (z.B. A-E) erstellen (ggf. in JSON-Dateien oder direkt in Dexie-Schema).
  - [ ] Dexie.js Schema für Buchstaben, Laute und ggf. Bilder erweitern.
- **[ ] Schritt 2.2: UI für Buchstaben-Anzeige erstellen**
  - [ ] Komponente zur Darstellung eines einzelnen Buchstabens (visuell).
  - [ ] Ansicht/Seite zur Auflistung/Durchblättern der Buchstaben erstellen.
- **[ ] Schritt 2.3: Audio-Integration für Laute**
  - [ ] Audio-Dateien für die Laute der ersten Buchstaben aufnehmen oder beschaffen.
  - [ ] Funktionalität zum Abspielen der Laute beim Anzeigen/Anklicken eines Buchstabens implementieren.
- **[ ] Schritt 2.4: Erste Interaktion: Buchstaben/Laute lernen**
  - [ ] Konzeption einer einfachen Übung, bei der ein Buchstabe gezeigt und der Laut vorgespielt wird.
  - [ ] Ggf. eine "Hör genau hin"-Funktion.

### Phase 3: Entwicklung des Leselernmoduls - Teil 2 (Erste Übungen & Interaktion) (Woche 7-9)

- **[ ] Schritt 3.1: Design und Implementierung: "Finde den Buchstaben"-Spiel**
  - [ ] Konzept: Ein Laut wird vorgespielt oder ein Buchstabe genannt, Kind muss den passenden Buchstaben aus einer Auswahl anklicken.
  - [ ] UI für die Spielansicht entwerfen.
  - [ ] Logik für die Auswahl der Buchstaben, Erfolgs-/Fehlerfeedback implementieren.
- **[ ] Schritt 3.2: Design und Implementierung: "Welcher Gegenstand beginnt mit...?"-Spiel**
  - [ ] Konzept: Ein Laut wird vorgespielt, Kind muss das passende Bild aus einer Auswahl anklicken (Bilder, deren Namen mit dem Laut beginnen).
  - [ ] Benötigte Bildmaterialien erstellen/beschaffen.
  - [ ] Dexie.js Schema erweitern, um Wörter mit Bildern und Anlauten zu speichern.
  - [ ] UI und Logik für dieses Spiel implementieren.
- **[ ] Schritt 3.3: Einfaches Belohnungssystem implementieren**
  - [ ] Konzept: Visuelles Feedback (Sterne, lachendes Gesicht) für richtig gelöste Aufgaben.
  - [ ] (Optional) Einfache Zählfunktion für gesammelte Sterne/Punkte in Dexie.js speichern.
  - [ ] UI-Elemente für Belohnungen erstellen und integrieren.
- **[ ] Schritt 3.4: Lernfortschritt (sehr einfach) speichern**
  - [ ] In Dexie.js speichern, welche Buchstaben/Übungen bereits erfolgreich absolviert wurden (z.B. einfacher Flag pro Buchstabe/Übungstyp).
  - [ ] (Keine komplexe Analyse, nur um Wiederholungen zu vermeiden oder den Fortschritt grob anzuzeigen).

### Phase 4: Fertigstellung des ersten Moduls & Tests (Woche 10-11)

- **[ ] Schritt 4.1: Integration und Feinschliff des Leselernmoduls**
  - [ ] Alle Komponenten des Leselernmoduls verbinden und für einen flüssigen Ablauf sorgen.
  - [ ] Übergänge und Animationen (dezent) hinzufügen, um die Nutzererfahrung zu verbessern.
  - [ ] Fehlerbehandlung und Randfälle bedenken.
- **[ ] Schritt 4.2: Kindgerechtes Design finalisieren (für das erste Modul)**
  - [ ] Überprüfung aller UI-Elemente auf Kindgerechtigkeit (Farben, Schriftgrößen, Verständlichkeit der Icons).
  - [ ] Soundeffekte für Interaktionen (Klicks, Erfolg, Fehler) hinzufügen.
- **[ ] Schritt 4.3: Interne Tests**
  - [ ] Ausführliche Tests aller Funktionen des Leselernmoduls auf verschiedenen Geräten/Browsern (soweit möglich).
  - [ ] PWA-Funktionalität testen (Installation, Offline-Fähigkeit der bereits geladenen Teile).
- **[ ] Schritt 4.4: (Optional) Erste Benutzertests mit der Zielgruppe**
  - [ ] Wenn möglich, das Modul von einigen Kindern im Zielalter testen lassen.
  - [ ] Feedback sammeln und ggf. kleinere Anpassungen vornehmen.
- **[ ] Schritt 4.5: Dokumentation aktualisieren**
  - [ ] GitHub Wiki-Seiten (besonders [[Module-Reading-Literacy]] und [[Technical-Architecture]]) mit den finalen Implementierungsdetails aktualisieren.
  - [ ] Code-Kommentare überprüfen und vervollständigen.
- **[ ] Schritt 4.6: GitHub Actions Workflow einrichten/verfeinern**
  - [ ] Sicherstellen, dass der Build-Prozess reibungslos durchläuft.
  - [ ] (Optional) Linter und Tests in den Workflow integrieren.

### Meilenstein 1: Erstes Modul "Lesenlernen - Grundlagen" ist fertiggestellt und testbar. 🎉

---

## Nächste Schritte (nach Meilenstein 1)

- Planung Phase 5: Erweiterung des Leselernmoduls (z.B. Silben, erste Wörter schreiben).
- Planung Phase 6: Konzeption und Entwicklung des nächsten Moduls (z.B. Mathe Grundlagen).
- Kontinuierliche Verbesserung und Fehlerbehebung.

Dieser Plan ist ein lebendes Dokument und kann bei Bedarf angepasst werden. Wichtig ist, realistische Ziele für die jeweiligen Zeiträume zu setzen und regelmäßig den Fortschritt zu überprüfen. Viel Erfolg!
