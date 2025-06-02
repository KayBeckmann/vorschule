# Modul: Lesenlernen

Dieses Modul ist das Kernstück der ersten Version der App und zielt darauf ab, Kindern spielerisch erste Lesekompetenzen zu vermitteln.

## Lernziele

- Erkennen und Benennen von Groß- und Kleinbuchstaben.
- Verknüpfung von Buchstaben mit den entsprechenden Lauten.
- Zusammensetzen von Buchstaben zu einfachen Silben.
- Lesen und Verstehen erster einfacher Wörter (z.B. Nomen mit Bildunterstützung).
- (Optional für fortgeschrittenere Stufen) Lesen und Verstehen einfacher Sätze.

## Geplante Features & Übungsformen

1.  **Buchstaben kennenlernen:**
    - Visuelle Darstellung jedes Buchstabens.
    - Auditive Wiedergabe des Buchstabens und des Lautes.
    - Interaktive Übung: "Finde den Buchstaben X".
2.  **Laute zuordnen:**
    - Spiel: "Welches Wort beginnt mit dem Laut /a/?" (mit Bildern).
    - Memory-Spiel: Buchstaben und passende Anlautbilder.
3.  **Silben bilden und lesen:**
    - Visuelle Hilfe zum Zusammensetzen von Buchstaben zu Silben (z.B. Silbenteppich-Ansatz).
    - Übung: Silbenpuzzle.
    - Lesen von einfachen, lautgetreuen Silben.
4.  **Wörter lesen:**
    - Darstellung von einfachen Wörtern mit passenden Bildern.
    - Vorlesefunktion für Wörter.
    - Wortbildungsspiele: Buchstaben an die richtige Stelle ziehen, um ein Wort zu bilden.
    - Lückentexte auf Wortebene (Bild wird gezeigt, Wort muss zugeordnet werden).
5.  **Belohnungssystem:**
    - Sammeln von Sternen/Punkten für korrekt gelöste Aufgaben.
    - Freischalten von kleinen Animationen oder Abzeichen bei Erreichen bestimmter Meilensteine.

## Technische Umsetzung im Modul

- Eigene Vue-Komponenten für jede Übungsform.
- Verwaltung der spezifischen Lerninhalte (Buchstaben, Wörter, Bilder, Audio-Dateien) – ggf. Strukturierung in JSON-Dateien oder direkt in Dexie.js.
- Speicherung des individuellen Fortschritts innerhalb des Lesemoduls in der Dexie.js Datenbank (z.B. welche Buchstaben/Wörter wurden schon geübt/gemeistert).