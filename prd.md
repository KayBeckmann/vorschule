# Product Requirement Document: Lern-App für Kinder

**Version:** 0.1
**Datum:** 01.06.2025
**Autor:** Kay Beckmann

---

## 1. Einleitung und Zweck 🎯

Diese App soll Kindern im Kindergartenalter und Schulanfängern den Übergang in die Schule erleichtern und sie spielerisch an das Lesen heranführen. Es handelt sich um eine Progressive Web App (PWA) entwickelt mit VUE3 und einer lokalen Dexie.js Datenbank, um eine offline-fähige und ansprechende Lernerfahrung zu ermöglichen. Das Projekt ist modular aufgebaut, sodass es in Zukunft einfach um weitere Lerninhalte und Fächer (z.B. Mathematik, Englisch) erweitert werden kann.

---

## 2. Ziele 🥅

- Kindern eine motivierende und kindgerechte Lernumgebung bieten.
- Grundlegende Lesefähigkeiten auf spielerische Weise vermitteln.
- Den Wortschatz erweitern und das Textverständnis fördern.
- Eine Plattform schaffen, die leicht mit neuen Lernmodulen für verschiedene Fächer erweiterbar ist.
- Eine hohe Benutzerfreundlichkeit und Zugänglichkeit sicherstellen, auch offline.

---

## 3. Zielgruppe 👧👦

- **Primäre Zielgruppe:** Kinder im Alter von 4-7 Jahren (Vorschule und erste Grundschuljahre).
- **Sekundäre Zielgruppe:** Eltern und Erzieher, die nach unterstützenden Lernwerkzeugen suchen.

---

## 4. Anforderungen und Features 🧩

### 4.1. Allgemeine App-Features

- **PWA (Progressive Web App):**
  - Offline-Fähigkeit: Inhalte und Lernfortschritte sollen auch ohne Internetverbindung verfügbar sein.
  - Installierbar auf verschiedenen Geräten (Desktop, Tablet, Smartphone).
  - Performance-Optimierung für schnelle Ladezeiten.
- **Benutzerverwaltung (optional für spätere Phasen):**
  - Möglichkeit, Profile für mehrere Kinder anzulegen.
  - Speicherung des individuellen Lernfortschritts.
- **Kindgerechtes Design:**
  - Intuitive und einfache Navigation.
  - Ansprechende Grafiken, Animationen und Soundeffekte.
- **Einstellungen:**
  - Lautstärkeregelung.
  - (Optional) Sprachauswahl für die Benutzeroberfläche.

### 4.2. Kernmodul: Lesen lernen 📚

- **Buchstaben und Laute:**
  - Interaktive Einführung von Buchstaben und den dazugehörigen Lauten.
  - Spiele zur Buchstaben- und Lauterkennung (z.B. "Welcher Gegenstand beginnt mit A?", Zuordnungsspiele).
- **Silben:**
  - Übungen zum Zusammensetzen von Buchstaben zu Silben.
  - Spiele zur Silbenerkennung.
- **Erste Wörter:**
  - Visuelle Darstellung von Wörtern mit passenden Bildern.
  - Vorlesefunktion für Wörter.
  - Einfache Wortbildungsspiele (z.B. Buchstaben zu Wörtern zusammensetzen).
- **Einfache Sätze:**
  - Kurze, verständliche Sätze mit Bildunterstützung.
  - Lückentexte oder Satzbauspiele.
- **Mini-Geschichten:**
  - Sehr kurze Geschichten zum Mitlesen oder Anhören.
- **Belohnungssystem:**
  - Visuelle Belohnungen (Sterne, Abzeichen, etc.) für abgeschlossene Übungen und erreichte Lernziele.

### 4.3. Technische Anforderungen

- **Frontend:** VUE3 Framework.
- **Datenbank:** Dexie.js für die lokale Speicherung von Lerninhalten und Fortschritt.
- **Modularer Aufbau:** Klare Trennung der einzelnen Lernmodule (Lesen, Mathe, etc.) für einfache Erweiterbarkeit.
- **Responsives Design:** Anpassung an verschiedene Bildschirmgrößen.

### 4.4. Zukünftige Erweiterungsmodule (Beispiele)

- **Mathematik:**
  - Zahlen lernen (1-10, 1-20).
  - Einfache Addition und Subtraktion.
  - Formen erkennen.
- **Englisch (oder andere Sprachen):**
  - Einfache Vokabeln (Farben, Tiere, Zahlen).
  - Kurze Sätze und Phrasen.
- **Weitere Fächer:** Sachkunde, Logikspiele, etc.

---

## 5. Design und UX Überlegungen 🎨🖌️

- **Farbgebung:** Hell, freundlich und ansprechend für Kinder. Kontrastreich für gute Lesbarkeit.
- **Typografie:** Große, klare und gut lesbare Schriftarten.
- **Interaktion:** Einfache Touch-Gesten (Tippen, Ziehen). Akustisches und visuelles Feedback bei Interaktionen.
- **Charaktere/Avatare (optional):** Ein freundlicher Charakter könnte durch die App führen und motivieren.
- **Vermeidung von Frustration:** Fehlertolerantes Design, klare Anweisungen, Möglichkeit Übungen zu wiederholen.

---

## 6. Erfolgsmetriken 📊

- Anzahl der Downloads/Installationen.
- Aktive Nutzer pro Tag/Woche/Monat.
- Durchschnittliche Nutzungsdauer.
- Abschlussrate der Lernmodule/-übungen.
- Positives Feedback von Eltern und Kindern.

---

## 7. Zukünftige Überlegungen und Skalierbarkeit 🚀

- **Mehrsprachigkeit:** Unterstützung weiterer Sprachen für Inhalte und Benutzeroberfläche.
- **Content Management System (CMS):** Für einfache Verwaltung und Erweiterung der Lerninhalte durch Nicht-Entwickler (z.B. Pädagogen).
- **Community-Features (optional):** Möglichkeit zum Austausch für Eltern oder das Teilen von anonymisierten Lernerfolgen.
- **Anpassbare Schwierigkeitsgrade:** Automatische Anpassung oder manuelle Auswahl des Schwierigkeitslevels.

---

## 8. Offene Fragen 🤔

- Sollen spezifische pädagogische Konzepte (z.B. Montessori, o.ä.) berücksichtigt werden?
- Gibt es bereits konkrete Ideen für die grafische Gestaltung oder Charaktere?
- Welche ersten Leseübungen sind am wichtigsten?
- Wie detailliert soll der Lernfortschritt getrackt werden?
