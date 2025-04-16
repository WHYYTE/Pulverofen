# 🔥 ESP32-gesteuerter Pulverbeschichtungs-Ofen

![Build](https://img.shields.io/badge/status-active-brightgreen)
[![Made with Arduino](https://img.shields.io/badge/built%20with-arduino-00979D.svg?style=flat-square&logo=arduino)](https://www.arduino.cc)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Ein smartes Webinterface zur Temperaturregelung für einen umgebauten Elektro-Ofen – ideal zum Pulverbeschichten, Tempern von Carbon oder ähnliche Hochtemperaturprozesse.

---

## 📦 Funktionen

- Live-Temperaturanzeige im Browser (mit Chart)
- PID-Regelung mit Auto-Tuning
- Temperaturprofile erstellen und ausführen
- Webinterface mit HTML5 + Chart.js
- WLAN-fähig (ESP32)
- Profile dauerhaft speicherbar & löschbar (SPIFFS)

---

## 🔧 Benötigte Hardware

| Bauteil                     | Beschreibung                                               |
|-----------------------------|------------------------------------------------------------|
| ESP32 DevKitC               | Mikrocontroller mit Wi-Fi & PWM                            |
| MAX31855 Breakout           | Thermoelement-Verstärker für Typ K                         |
| Typ-K Thermoelement         | Hochtemperaturfühler (bis ~1100 °C)                        |
| SSR (5V oder 3–32 V DC)     | Solid State Relais zum Schalten der Ofenheizung           |
| 230 V Heizofen (umgebaut)   | Elektro-Ofen, mechanischer Thermostat deaktiviert         |
| Netzteil (z. B. 5V oder 12V) | Stromversorgung für Logik und Relais                      |
| Optional: Kühlkörper für SSR | Für Dauerbetrieb empfohlen                                 |

---

## 🔌 Verdrahtung (Wiring)

```text
ESP32              SSR / MAX31855 / Ofen
┌──────────────┬────────────────────────────┐
│ GPIO 5       │ SSR IN (Heizung schalten) │
│ GPIO 13      │ MAX31855 CLK              │
│ GPIO 14      │ MAX31855 CS               │
│ GPIO 12      │ MAX31855 DO               │
│ GND          │ Gemeinsame Masse          │
│ 3.3V oder 5V │ VCC je nach Modul         │
└──────────────┴────────────────────────────┘
```

---

## 🌐 Webinterface (SPIFFS)

- Lade die Datei `index.html` ins Verzeichnis `/data/`
- Hochladen via: **ESP32 Sketch Data Upload** Plugin (Arduino IDE)

---

## 🧪 Software

- Framework: **Arduino**
- Benötigte Libraries:
  ```cpp
  ESPAsyncWebServer
  AsyncTCP
  SPIFFS
  Adafruit_MAX31855
  PID
  PID_AutoTune_v0
  ArduinoJson
  ```

---

## 🚀 Start

```bash
# 1. SPIFFS hochladen
Werkzeuge → ESP32 Sketch Data Upload

# 2. Firmware flashen
Sketch → Hochladen (Strg+U)

# 3. IP im Seriellen Monitor anzeigen

# 4. Browser öffnen
http://<ESP_IP>
```

---

## 📂 Verzeichnisstruktur

```text
project_root/
├── data/
│   └── index.html             # Webinterface für SPIFFS
├── pulverofen_firmware.ino   # Firmware-Sketch für ESP32
├── README.md                 # Dieses Dokument
```

---

## 🧩 Lizenz

MIT License – feel free to use & modify!

---

## 💬 Mitmachen?
Pull Requests & Ideen willkommen! 😄

---

Letztes Update: April 2025

