# Änderungen

Neueste Einträge oben. Datumsangaben beziehen sich auf die Veröffentlichung.

## 2026-07-18 – Erste dokumentierte Veröffentlichung

Stand der Funktionen zum Zeitpunkt dieser Veröffentlichung:

**Wachs-Logik**
- Getrennte Intervalle für Heißwachs (Basis, Standard 400 km) und Flüssigwachs
  (Auffrischung, Standard 150 km).
- Heißwachs setzt beide Zähler zurück, Flüssigwachs nur den Auffrisch-Zähler.
- Status-Ampel je Kette: grün / gelb ab 80 % / rot bei Überschreitung, plus Banner-Erinnerung.

**Ketten**
- Wahlweise eine oder zwei Ketten (umschaltbar in den Einstellungen).
- Bei zwei Ketten ist immer eine montiert; Fahrten zählen auf die montierte Kette.
  Das Umschalten auf eine Kette ist nicht-destruktiv – zurückschalten stellt die
  ursprüngliche Zuordnung wieder her.
- Frei benennbar, mit Start-Kilometern für bereits eingesetzte Ketten.

**Erfassung und Verlauf**
- Fahrten mit Datum, Kilometern und optionaler Notiz.
- Verlauf nach Monaten gruppiert und einklappbar, mit Monats-Zwischensumme.
- Einträge nachträglich bearbeiten oder löschen (auch Wachs-Art und Kette).
- Export und Import als JSON für Backup und Geräte-Umzug; importierte Dateien werden
  streng geprüft, fehlerhafte Einträge verworfen.

**Darstellung**
- Zweispaltiges Layout ab 900 px (Status links, Verlauf rechts), einspaltig am Handy.
- Als Web-App zum Home-Bildschirm hinzufügbar: eigenes Icon, Vollbild, offline nutzbar.
- Hell- und Dunkelmodus automatisch.

**Datensicherheit**
- Content-Security-Policy mit `connect-src 'none'` – die Seite kann keine Netzwerk-
  verbindung aufbauen.
- Alle Eingaben werden beim Anzeigen escaped.
- `noindex` und `no-referrer`; HTTPS erzwungen.

**Behobene Fehler aus der Vorbereitung dieser Veröffentlichung**
- Datumsberechnung lief über UTC – Einträge nach Mitternacht wurden auf den Vortag
  datiert. Jetzt Ortszeit.
- Beim Import konnten doppelte Einträge-IDs entstehen, wodurch Bearbeiten oder Löschen
  den falschen Eintrag traf. IDs werden jetzt eindeutig vergeben.
- Ein Intervall von 0 aus einer Importdatei führte zu einer Division durch null.
- Speichern brach bei vollem oder blockiertem Browser-Speicher stillschweigend ab;
  jetzt mit Hinweis auf den Export.
- Das Datumsfeld behielt nach dem Nachtragen einer älteren Fahrt das alte Datum,
  sodass die nächste Fahrt es unbemerkt übernahm.
