# Wie du beitragen kannst (Contributing Guidelines)

Wir freuen uns sehr über dein Interesse, an der Lern-App für Kinder mitzuwirken! Jede Hilfe ist willkommen, sei es durch Code, Dokumentation, Bug Reports oder Feature-Vorschläge.

## Melden von Fehlern (Bug Reports)

- **Überprüfe existierende Issues:** Bevor du einen neuen Fehler meldest, schaue bitte in den [GitHub Issues](https://github.com/KayBeckmann/vorschule/issues), ob der Fehler bereits gemeldet wurde.
- **Sei genau:** Beschreibe den Fehler so detailliert wie möglich. Was hast du gemacht? Was ist passiert? Was hättest du erwartet?
- **Füge hinzu:**
  - Schritte zur Reproduktion des Fehlers.
  - Screenshots oder kurze Videos sind oft sehr hilfreich.
  - Informationen zu deinem System (Browser, Betriebssystem).
- Erstelle ein neues [Issue](https://github.com/KayBeckmann/vorschule/issues/new/choose).

## Vorschlagen von Features oder Verbesserungen

- Wenn du eine Idee für ein neues Feature oder eine Verbesserung hast, erstelle bitte ebenfalls ein [Issue](https://github.com/KayBeckmann/vorschule/issues/new/choose).
- Beschreibe deine Idee klar und warum du denkst, dass sie nützlich für die App wäre.

## Mitwirken am Code

1.  **Forke das Repository:** Erstelle eine eigene Kopie des Projekts auf GitHub (`https://github.com/KayBeckmann/vorschule`).
2.  **Klone deinen Fork:**
    ```bash
    git clone https://github.com/KayBeckmann/vorschule.git
    cd vorschule
    ```
3.  **Erstelle einen neuen Branch:** Arbeite immer in einem separaten Branch für dein Feature oder deine Fehlerbehebung.
    ```bash
    git checkout -b feature/dein-neues-feature # oder fix/fehlerbeschreibung
    ```
4.  **Nimm deine Änderungen vor.**
5.  **Teste deine Änderungen gründlich.**
6.  **Commite deine Änderungen:** Schreibe klare und aussagekräftige Commit-Nachrichten.
    ```bash
    git add .
    git commit -m "feat: Füge neues Feature X hinzu"
    # oder
    # git commit -m "fix: Behebe Fehler Y in Komponente Z"
    # (siehe Conventional Commits: [https://www.conventionalcommits.org/](https://www.conventionalcommits.org/))
    ```
7.  **Pushe deine Änderungen in deinen Fork:**
    ```bash
    git push origin feature/dein-neues-feature
    ```
8.  **Erstelle einen Pull Request (PR):**
    - Gehe zu deinem Fork auf GitHub und klicke auf "New Pull Request".
    - Wähle deinen Branch aus und vergleiche ihn mit dem `master`-Branch (oder `main`, je nachdem was euer Hauptbranch ist) des `KayBeckmann/vorschule`-Repositorys.
    - Gib deinem PR einen aussagekräftigen Titel und eine Beschreibung deiner Änderungen.
    - Verlinke ggf. das zugehörige Issue.

## Code Style und Konventionen

- Bitte halte dich an den bestehenden Code-Stil. ESLint (`eslint.config.ts`) und Prettier (`.prettierrc.json`) sind im Projekt konfiguriert und helfen dabei.
- Stelle sicher, dass dein Code die ESLint-Prüfungen besteht, bevor du einen PR erstellst.
- Kommentiere deinen Code, wo es sinnvoll ist, um die Verständlichkeit zu erhöhen.

## Fragen?

Wenn du Fragen hast, zögere nicht, ein Issue zu erstellen oder dich an die Maintainer zu wenden.

Vielen Dank für deine Mithilfe!