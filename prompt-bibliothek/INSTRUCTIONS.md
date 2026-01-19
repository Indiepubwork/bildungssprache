# Promptbibliothek Webapp

Erstelle eine Single-Page Webapp für eine Promptbibliothek.

## Dateistruktur
- index.html (App mit eingebettetem CSS/JS)
- data/prompts.json (externe Datenquelle, bereits vorhanden)

## Daten laden
Die JSON wird beim Start per fetch() geladen:

fetch('data/prompts.json')
  .then(res => res.json())
  .then(data => initApp(data.prompts))

## JSON-Struktur (Beispiel)

{
  "id": 1,
  "titel": "Wörter im Kontext verstehen",
  "prompt": "Erkläre mir das Wort »subtil«...",
  "kategorie": "Bildungssprache",
  "artikel_id": 88251,
  "artikel_titel": "Bildungssprache lernen mit KI"
}

## Features
1. Suchfeld – filtert Titel + Prompt-Text live
2. Kategorie-Filter – Dropdown, Kategorien aus JSON extrahieren
3. Prompt-Karten – Titel, Kategorie-Badge, Vorschau (80 Zeichen)
4. Detail-Modal – Vollständiger Prompt, Quell-Artikel als Link
5. Copy-Button – Kopiert Prompt in Zwischenablage, kurzes Feedback
6. Anzahl-Anzeige – "X von Y Prompts"
7. Link zur Hauptseite – bildungssprache.net

## Links
- Quell-Artikel: https://bildungssprache.net/?p={artikel_id}
- Hauptseite (im Footer oder Header): https://bildungssprache.net

## Tech
- Vanilla JS, kein Framework
- CSS Grid/Flexbox für Karten-Layout
- Responsive (Mobile-first)

## Design
- Clean, modern, viel Weißraum
- Monospace-Font für Prompt-Text
- Kategorie-Badges farbig (je Kategorie eigene Farbe)
- Hover-Effekte auf Karten

## Analytics (vor </body>)

<script type="text/javascript">
var SlimStatParams = { ajaxurl: "https://bildungssprache.net/wp-admin/admin-ajax.php" };
</script>
<script src="https://cdn.jsdelivr.net/wp/wp-slimstat/trunk/wp-slimstat.min.js"></script>
