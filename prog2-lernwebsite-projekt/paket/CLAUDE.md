# Projekt: Lernwebsite „Programmierung 2 – Teil 1" (Java)

## Kontext
Prüfungsvorbereitung für das Uni-Modul „Programmieren – Java fortgeschritten".
Die Datei `prog2-teil1-lernwebsite.html` ist eine Lernwebsite, deren Kapitel
schrittweise mit Zusammenfassungen aus dem Vorlesungsskript befüllt werden.

## Quellen
- Skript-Rohtexte liegen kapitelweise unter `skripte/teil1/` (siehe
  `skripte/teil1/INHALTSVERZEICHNIS.md` für die Zuordnung Kapitel ↔ Datei ↔ Seiten).
- Beim Befüllen eines Website-Kapitels NUR die zugehörige Kapiteldatei einlesen,
  nicht alle Dateien (Kontext klein halten).

## Regeln für Inhalte
1. Fachlich korrekt, Schritt für Schritt und anschaulich erklären.
2. JEDE Aussage mit Quellenangabe versehen: „Quelle: Skript Teil 1, S. X" –
   die Seitenzahlen stehen im Rohtext als Folien-Fußzeilen (z. B. „Prof. Dr. Ute Matecki 165").
3. Inhalte als eigenständige, kompakte Zusammenfassungen formulieren,
   nicht den Skripttext 1:1 kopieren.
4. Code-Beispiele aus dem Skript nachvollziehen, korrekt formatieren und kurz erklären.
5. Pro Kapitel: Zusammenfassungs-Box, Erklärungen je Unterkapitel,
   mindestens ein Code-Beispiel, Prüfungshinweise zu typischen Stolperfallen.

## Website-Konventionen (prog2-teil1-lernwebsite.html)
- Platzhalter sind als `<div class="placeholder">…</div>` markiert → durch echten Inhalt ersetzen.
- Vorhandene CSS-Klassen nutzen: `.summary` (Zusammenfassung), `.hint` (Prüfungshinweis),
  `pre.code` mit `.kw/.ty/.st/.cm` (Syntax-Farben), `code.inline`, `.src` (Quellenangabe).
- Design, Navigation und Struktur NICHT verändern, nur Inhalte einsetzen.
- Hinweis: Keine Nutzung von localStorage (Website soll überall lauffähig bleiben).

## Ergänzung: Teil 2
- Skript-Rohtexte zu Teil 2 liegen unter `skripte/teil2/` (Übersicht in
  `skripte/teil2/INHALTSVERZEICHNIS.md`).
- Das Generics-Kapitel ist in fünf Teildateien (03a–03e) zerlegt – jeweils
  einzeln einlesen.
- Für Teil 2 ggf. zuerst ein eigenes Website-Gerüst nach dem Muster von
  `prog2-teil1-lernwebsite.html` erstellen.
