# ESPHome LMS Display – VIEWESMART UEDX48480021-MD80ESP32

**Display:** [VIEWESMART UEDX48480021-MD80ESP32 – 2,1" Round Touch Knob Display](https://github.com/VIEWESMART/UEDX48480021-MD80ESP32-2.1inch-Touch-Knob-Display)

---

## Deutsch

### Beschreibung

ESPHome-Konfiguration für das runde VIEWESMART 2,1"-Touchdisplay (ESP32-S3, 480×480 px, MIPI-RGB, CST826 Touch, Drehencoder). Das Display dient als Steuereinheit für einen [Logitech Media Server (LMS)](https://lyrion.org/) und zeigt Wiedergabeinformationen aus Home Assistant an.

### Funktionen

- **Cover-Art** – Lädt das aktuelle Albumcover als Vollbild-Hintergrund vom LMS-Server
- **Titelanzeige** – Scrollender Songtitel und Interpret (LVGL SCROLL_CIRCULAR)
- **Lautstärke-Ring** – Grafische Lautstärkeanzeige als Bogen am Displayrand
- **Lautstärke-Drehregler** – Physischer Encoder stellt die Lautstärke des Schlafzimmer-Players
- **Stummschaltung** – Encoder-Taste schaltet den Ton ein/aus (Toggle)
- **Wischgesten** – Links/Rechts-Wischen wechselt zwischen vordefinierten LMS-Favoriten (6 Presets)
- **Home Assistant Integration** – Lautstärke, Titelinformationen und Steuerung über HA-Entitäten

### Anpassen

Folgende Werte müssen vor dem Flashen angepasst werden:

| Stelle in der YAML | Beschreibung |
|---|---|
| `!secret wifi_ssid` / `!secret wifi_password` | WLAN-Zugangsdaten in `secrets.yaml` |
| `media_player.schlafzimmer` | HA-Entität des LMS-Players (alle Vorkommen ersetzen) |
| `38:18:2b:72:85:cc` | MAC-Adresse des LMS-Spielers in der Cover-Art-URL |
| `button.none_voreinstellung_1` … `_6` | HA-Entitäten der LMS-Favoriten-Buttons |
| `api.encryption.key` | Eigenen API-Key generieren (`esphome generate-key`) |
| `ota.password` | Eigenes OTA-Passwort setzen |

### Voraussetzungen

- Home Assistant mit ESPHome Add-on
- Logitech Media Server (LMS / Lyrion Music Server)
- LMS-Integration in Home Assistant (`media_player`-Entität)
- Schriftart `fonts/NotoSans-Regular.ttf` im ESPHome-Konfigurationsverzeichnis

---

## English

### Description

ESPHome configuration for the round VIEWESMART 2.1" touch display (ESP32-S3, 480×480 px, MIPI-RGB, CST826 touch, rotary encoder). The display acts as a controller for a [Logitech Media Server (LMS)](https://lyrion.org/) and shows playback information from Home Assistant.

### Features

- **Cover Art** – Downloads the current album cover as a full-screen background from the LMS server
- **Track Display** – Scrolling song title and artist name (LVGL SCROLL_CIRCULAR)
- **Volume Ring** – Graphical volume indicator as an arc around the display edge
- **Volume Encoder** – Physical rotary encoder controls the volume of the media player
- **Mute Toggle** – Encoder button toggles mute on/off
- **Swipe Gestures** – Left/right swipe switches between predefined LMS favourites (6 presets)
- **Home Assistant Integration** – Volume, track info and control via HA entities

### Customisation

The following values must be adjusted before flashing:

| Location in YAML | Description |
|---|---|
| `!secret wifi_ssid` / `!secret wifi_password` | Wi-Fi credentials in `secrets.yaml` |
| `media_player.schlafzimmer` | HA entity of your LMS media player (replace all occurrences) |
| `38:18:2b:72:85:cc` | MAC address of your LMS player in the cover art URL |
| `button.none_voreinstellung_1` … `_6` | HA entities of your LMS preset buttons |
| `api.encryption.key` | Generate your own key (`esphome generate-key`) |
| `ota.password` | Set your own OTA password |

### Requirements

- Home Assistant with ESPHome add-on
- Logitech Media Server (LMS / Lyrion Music Server)
- LMS integration in Home Assistant (`media_player` entity)
- Font file `fonts/NotoSans-Regular.ttf` in the ESPHome configuration directory
