# Frisörsalon Wenzel – Demo-Website

Zweites Referenzprojekt fürs Portfolio. Gegenstück zur ersten Demo („HAARSCHARF.“):
Diese Seite zeigt nicht, was maximal geht, sondern was ein normaler Familienbetrieb
wirklich braucht – schnell, vertrauenswürdig und selbst pflegbar.

**Alle Inhalte sind frei erfunden.** Der Betrieb, die Adresse, die Telefonnummer,
die Preise und die Bewertungen existieren nicht.

## Was drin ist

- Ein-Seiten-Website (`index.html`) mit Hero, Über uns, Preisen, Team, Galerie,
  Bewertungen, Termin & Kontakt und Footer
- „Geöffnet / Geschlossen“-Anzeige, die live aus den Öffnungszeiten berechnet wird
- WhatsApp als gleichwertiger Weg neben Anruf und Buchungstool
- Platzhalter für das Fresha-Buchungswidget statt eines nachgebauten Buchungsflows
- Impressum und Datenschutz als klar gekennzeichnete Platzhalterseiten

## Technik

Reines HTML, CSS und Vanilla JavaScript. Kein Framework, kein Build-Schritt:
Dateien auf den Webspace kopieren, fertig.

| Datei | Zweck |
|---|---|
| `index.html` | die gesamte Seite |
| `styles.css` | Design-Tokens und Layout |
| `script.js` | Navigation, Öffnungsstatus, Scroll-Reveal, Formularprüfung |
| `assets/images/` | Foto-Platzhalter als WebP, zugeschnitten und warm angeglichen |
| `assets/fonts/` | selbst gehostete Schrift Nunito (SIL OFL, siehe `OFL.txt`) |

Erster Seitenaufbau: rund 210 KB bei 6 Requests. Die übrigen Fotos werden erst beim
Scrollen nachgeladen (zusammen ca. 530 KB für die komplette Seite). Keine externen
Aufrufe, keine Cookies, kein Tracking.

Die Fotos liegen nur als WebP vor. Das versteht jeder Browser ab 2020 (Safari 14,
iOS 14). Wer noch ältere Geräte bedienen muss, ergänzt ein `<picture>` mit JPEG.

## Selbst ändern

**Preise** – in `index.html` im Abschnitt `<section id="leistungen">`. Jede Zeile
sieht so aus; nur den Text zwischen den Zeichen ändern:

```html
<li><span class="price-list__name">Waschen, Schneiden, Föhnen</span><span class="price-list__value">ab 42&nbsp;€</span></li>
```

**Urlaub / Hinweise** – in `index.html` im Abschnitt „Öffnungszeiten“, im Absatz
mit `<strong>Urlaub:</strong>`.

**Öffnungszeiten** – an zwei Stellen, die zusammenpassen müssen:

1. `index.html`, Tabelle `id="hours-table"` (das, was Besucher lesen)
2. `script.js`, ganz oben in `OEFFNUNGSZEITEN` (die Grundlage für die
   Geöffnet-Anzeige). Zeiten dort in Stunden × 60, `null` heißt geschlossen.

**Telefon und WhatsApp** – die Nummer steht in `index.html` mehrfach als
`https://wa.me/…` und `tel:…`. Am einfachsten mit Suchen & Ersetzen austauschen.

## Vor einem echten Livegang

- Impressum und Datenschutz mit echten Angaben füllen und rechtlich prüfen lassen
- Eigene Fotos von Salon und Team statt der Stockfotos einsetzen. Für die Team-Sektion
  ist das keine Kür: Stockfotos fremder Personen als eigenes Team auszugeben, deckt die
  Pexels-Lizenz nicht ab. Von eigenen Mitarbeitenden vorher schriftlich einwilligen lassen.
- Fresha-Widget einbinden; falls es Cookies setzt, erst nach Einwilligung laden
- Karte, falls gewünscht, ebenfalls erst nach Einwilligung nachladen

Die Hinweise auf den beiden Rechtstext-Seiten sind eine Checkliste, keine
Rechtsberatung.
