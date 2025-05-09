# Wettervorhersage-Block

Ein WordPress-Plugin, das einen Wettervorhersage-Block für den Gutenberg-Editor bereitstellt. Es verwendet die OpenWeatherMap-API, um aktuelle Wetterdaten sowie eine 5-Tage-Vorhersage für einen angegebenen Standort anzuzeigen.

## Funktionen

- **Aktuelles Wetter**: Zeigt die aktuelle Temperatur, gefühlte Temperatur und Wetterbeschreibung an (approximiert aus der frühesten Vorhersage).
- **5-Tage-Vorhersage**: Liefert Tageshöchst- und -tiefsttemperaturen, Niederschlagswahrscheinlichkeit und Wettericons für bis zu 5 Tage.
- **Anpassbar**: Standort und API-Schlüssel können direkt in den Blockeinstellungen im Gutenberg-Editor angepasst werden.
- **Caching**: Wetterdaten werden für eine Stunde zwischengespeichert, um API-Aufrufe zu minimieren.
- **Deutsche Lokalisierung**: Wetterbeschreibungen und Tagesnamen werden auf Deutsch angezeigt.

## Voraussetzungen

- WordPress 5.0 oder höher (für Gutenberg-Unterstützung)
- Ein gültiger [OpenWeatherMap-API-Schlüssel](https://openweathermap.org/api) (kostenlos für Basisnutzung verfügbar)

## Installation

1. Lade das Plugin als ZIP-Datei herunter oder klone das Repository:
   ```
   git clone https://github.com/ffabbr/weather-block.git
   ```
2. Kopiere den Ordner `weather-forcast-block` in das Verzeichnis `wp-content/plugins/` deiner WordPress-Installation.
3. Aktiviere das Plugin im WordPress-Adminbereich unter **Plugins**.
4. Füge den „Wettervorhersage-Block“ in einem Beitrag oder einer Seite über den Gutenberg-Editor hinzu.
5. Gib deinen OpenWeatherMap-API-Schlüssel und den gewünschten Standort in den Blockeinstellungen ein.

## Konfiguration

- **Standort**: Standardmäßig auf „London“ gesetzt. Du kannst entweder einen Städtenamen (z. B. „Berlin“) oder eine OpenWeatherMap-Stadt-ID verwenden und diese einfach im Block Editor in der Sidebar des Wetter-Blocks eingeben.
- **API-Schlüssel**: Erforderlich für API-Aufrufe. Ohne gültigen Schlüssel wird eine Fehlermeldung angezeigt.

## Dateistruktur

- `main.php`: Hauptdatei des Plugins mit PHP-Logik und Serverseitigem Rendering.
- `block.js`: JavaScript für den Block-Editor.
- `style.css`: CSS-Styling für Frontend und Editor.
- `icons/`: Verzeichnis mit SVG-Wettericons (z. B. `01.svg`, `02.svg`).

## Entwicklung

### Block-Attribute

- `location` (string): Der Standort für die Wetterdaten (Standard: „London“).
- `apiKey` (string): Der OpenWeatherMap-API-Schlüssel (Standard: leer).

### API-Aufrufe

Das Plugin verwendet die [OpenWeatherMap 5-Tage-Vorhersage-API](https://openweathermap.org/forecast5). Daten werden in metrischen Einheiten (Celsius) und auf Deutsch abgerufen.

### Anpassen

- **Icons**: Füge eigene SVG-Icons im Ordner `icons/` hinzu, passend zu den OpenWeatherMap-Icon-Codes (z. B. `10d.svg`).
- **Styling**: Bearbeite `style.css`, um das Erscheinungsbild anzupassen.

## Fehlerbehebung

- **„Ungültiger API-Schlüssel“**: Überprüfe deinen API-Schlüssel in den Blockeinstellungen.
- **„Keine Wetterdaten verfügbar“**: Stelle sicher, dass der Standort korrekt ist und die API erreichbar ist.
- **Debugging**: Entkommentiere die Debugging-Ausgabe in `main.php`, um API-URLs und Rohdaten anzuzeigen (nur für Administratoren sichtbar).

## Lizenz

Dieses Projekt ist unter der [GPLv2 oder höher](https://www.gnu.org/licenses/gpl-2.0.html) lizenziert, wie es für WordPress-Plugins üblich ist.

## Mitwirken

Beiträge sind willkommen! Erstelle einen Fork, bearbeite den Code und reiche einen Pull Request ein. Issues können im GitHub-Issue-Tracker gemeldet werden.

## Autor

Entwickelt von CEATE.
