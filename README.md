# Kettenwachs-Tracking

Ein kleiner Tracker für die Wachs-Wartung von Fahrradketten – mit getrennten Intervallen für
**Heißwachs** (die Basis) und **Flüssigwachs** (das Nachbessern dazwischen).

**→ [Tool öffnen](https://biemi-im-fokus.github.io/kettenwachs/)**

Eine einzelne HTML-Datei, kein Server, keine Anmeldung, keine Abhängigkeiten.
Alle Daten bleiben im Browser des jeweiligen Geräts.

---

## Wofür das gut ist

Wer seine Kette wachst statt ölt, hat zwei Wartungs-Rhythmen gleichzeitig laufen:

- **🔥 Heißwachs** – die Kette wird entfettet und im Wachsbad getränkt. Hält lange, ist aber Aufwand.
- **💧 Flüssigwachs** – schnell aufgetropft, frischt die Oberfläche auf. Kurzes Intervall.

Ein Heißwachs setzt **beide** Zähler zurück (frische Basis = auch frische Oberfläche).
Ein Flüssigwachs setzt **nur** den Auffrisch-Zähler zurück – die Basis altert im Hintergrund weiter.
Genau das bildet das Tool ab, statt nur „zuletzt gewachst am …" zu speichern.

## Funktionen

- **Eine oder zwei Ketten.** Bei Zwei-Ketten-Rotation ist immer genau eine montiert; gefahrene
  Kilometer zählen automatisch auf diese. Der Ein-Ketten-Modus zeigt stattdessen eine breite Karte.
- **Zwei Zähler pro Kette** – Ring = km seit letzter Auffrischung, Balken = km seit letztem Heißwachs.
- **Erinnerung** – Ampel (grün / ab 80 % gelb / rot) und Banner, sobald etwas fällig ist.
- **Fahrten erfassen** mit Datum, Kilometern und optionaler Notiz.
- **Verlauf**, nach Monaten gruppiert und einklappbar; jede Zeile lässt sich nachträglich bearbeiten.
- **Gesamt-Laufleistung** je Kette (inkl. Start-km für schon eingesetzte Ketten).
- **Export / Import als JSON** – für Backups und den Umzug auf ein anderes Gerät.
- **Eingebaute Anleitung** über das `?` in der Kopfzeile.
- **Als App nutzbar** – am iPhone in Safari über *Teilen → Zum Home-Bildschirm*: eigenes Icon,
  Vollbild, funktioniert danach auch offline.
- **Zweispaltiges Layout** am Desktop (Status links, Verlauf rechts), einspaltig am Handy.

## Daten und Privatsphäre

Das Tool hat **kein Backend**. Es gibt nichts, wo Daten gesammelt werden könnten:

- Alle Einträge liegen ausschließlich im **`localStorage` des jeweiligen Browsers**. Sie verlassen
  das Gerät nie – auch nicht zu GitHub.
- Eine **Content-Security-Policy** mit `connect-src 'none'` verbietet der Seite jede Netzwerk-
  verbindung. Sie *kann* technisch nichts senden – kein Tracking, keine Analyse, keine Fremd-Inhalte.
- Zusätzlich `noindex` (nicht in Suchmaschinen) und `no-referrer`.

Wer die Seite aufruft, sieht deshalb ein **leeres** Tool und kann es für sich selbst nutzen –
niemand sieht die Daten von jemand anderem.

**Backup:** Da alles lokal liegt, sind die Daten weg, wenn der Browser-Speicher gelöscht wird.
Deshalb gelegentlich **Einstellungen → Export (JSON)** nutzen und die Datei sichern.

## Technisches

- Eine `index.html` – HTML, CSS und JavaScript inline. Kein Build, kein Framework, keine externen
  Ressourcen (auch keine Schriften oder CDNs).
- Der Verlauf ist die einzige Datenquelle: Zählerstände werden bei jedem Rendern aus den Einträgen
  neu berechnet. Dadurch bleiben die Werte korrekt, wenn Einträge nachträglich geändert oder
  gelöscht werden.
- Läuft in aktuellen Browsern; getestet auf Bildschirmbreiten von 320 bis 1280 px, hell und dunkel.

## Hinweis

Privates Projekt für den Eigenbedarf, hier nur veröffentlicht, damit es sich vom Handy aus
aufrufen lässt. Keine Gewähr, kein Support – gerne benutzen, wenn es hilft.
