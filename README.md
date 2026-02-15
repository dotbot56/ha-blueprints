# 🏠 Home Assistant Blueprints – dotbot  
Modulare, skalierbare und wiederverwendbare Blueprints für Home Assistant  
→ Automationen & Scripts nach einem sauberen Klassifizierungssystem

Dieses Repository enthält eine vollständige Sammlung strukturierter **Automation-Blueprints** und **Script-Blueprints**, basierend auf einer realen, produktiven Home-Assistant-Installation.  
Alle Blueprints sind vollständig modularisiert und durch Inputs konfigurierbar.

---

# 📁 Verzeichnisstruktur

```text
ha-blueprints-dotbot/
├── README.md
├── blueprints/
│   ├── automation/
│   │   └── dotbot/
│   │       ├── m1_motion_light_basic.yaml
│   │       ├── m2_motion_light_sleepmode.yaml
│   │       ├── c1_contact_light_autooff.yaml
│   │       ├── b1_button_toggle_target.yaml
│   │       ├── b2_button_call_script.yaml
│   │       ├── b3_ts0042_scene_switch.yaml
│   │       ├── l1_illuminance_automation_manager.yaml
│   ├── script/
│   │   └── dotbot/
│   │       ├── sb_sleep_time.yaml
│   │       ├── sb_auto_backup_full.yaml
│   │       ├── sb_cinema_mode.yaml
│   │       ├── sb_controller_charging.yaml
│   │       ├── sb_sexy_time.yaml
│   │       ├── sb_guest_visiting.yaml
│   │       ├── sb_guest_overnight.yaml
│   │       ├── sb_cleaning_routine.yaml
│   │       ├── sb_all_lights_off.yaml
└── examples/
    └── .gitkeep
````

---

# 🚀 Importieren eines Blueprints in Home Assistant

**Pfad:**
*Einstellungen → Automationen & Szenen → Blueprints → Importieren*

**Beispiel-URL:**
(ersetze `<username>` durch deinen GitHub-Namen)

```
https://raw.githubusercontent.com/<username>/ha-blueprints-dotbot/main/blueprints/automation/dotbot/m1_motion_light_basic.yaml
```

Das gilt für *alle* Blueprints im Repo.

---

# 🔷 **Automation Blueprint Kategorien**

## 🟦 M1 – Motion → Light (Basic)

**Datei:** `m1_motion_light_basic.yaml`
Bewegungsmelder schaltet Licht ein und verzögert wieder aus.

* Unterstützt motion / occupancy / presence
* Konfigurierbare Ausschaltverzögerung
* Ziel: Entity / Device / Area

---

## 🟪 M2 – Motion → Light (Sleep Mode aware)

**Datei:** `m2_motion_light_sleepmode.yaml`
Schaltet je nach Sleep-Mode verschiedenes Licht.

* Normales Licht vs. Sleep-Licht
* Sleep-Mode wird automatisch berücksichtigt

---

## 🟫 C1 – Contact → Light Auto-Off

**Datei:** `c1_contact_light_autooff.yaml`
Kontakt-Sensor öffnet → Licht an
Kontakt schliesst oder Timeout → Licht aus

---

## 🟧 B1 – Button → Toggle Target

**Datei:** `b1_button_toggle_target.yaml`
Buttons lösen `light.toggle`, `switch.toggle` etc. aus.

* Unterstützt MQTT & Zigbee Buttons
* Jeder `action_subtype` (single, double, hold, …)

---

## 🟥 B2 – Button → Script/Scene Trigger

**Datei:** `b2_button_call_script.yaml`
Buttons starten Scripts oder Szenen wie:

* Sleep-Time
* Cinema Mode
* Sexy Time

---

## 🟥 B3 – TS0042 Scene Switch (Z2M)

**Datei:** `b3_ts0042_scene_switch.yaml`
Mapping für 2 Buttons × (Single/Double/Hold), frei belegbar mit Aktionen.

---

## 🟩 L1 – Illuminance Automation Manager

**Datei:** `l1_illuminance_automation_manager.yaml`
Skeleton für spätere komplexe Licht-/Lux-basierte Automationen.

---

# 🟦 **Script Blueprint Kategorien (SB*)**

Script-Blueprints ermöglichen, dass komplexe Abläufe
→ **beliebig wiederverwendbar**
→ **parameterisierbar**
→ **versionskontrolliert**
werden.

---

## 🌙 SB1 – Sleep Time Routine

**Datei:** `sb_sleep_time.yaml`

Automatisierte Abend-/Schlafroutine:

* Lichtdimmung
* Sleep-Mode aktivieren
* Medien pausieren
* Wohnung in „Ruhe“-Zustand versetzen

---

## 💾 SB2 – Auto Backup Full

**Datei:** `sb_auto_backup_full.yaml`

Führt ein vollständiges Backup aus inkl.:

* Kompression
* Aufbewahrungsdauer
* Benachrichtigung

---

## 🎬 SB3 – Cinema Mode

**Datei:** `sb_cinema_mode.yaml`

TV einschalten →
Automationen deaktivieren →
Plex-App starten →
Cinema-Lighting aktivieren

---

## 🎮 SB4 – Controller Charging

**Datei:** `sb_controller_charging.yaml`

Steckdose aktivieren →
Timer →
Automatisches Abschalten

Perfekt für Controller, Akkus & Ladegeräte.

---

## 🔥 SB5 – Sexy Time

**Datei:** `sb_sexy_time.yaml`

Dynamische Szenenlogik:

* Medien stoppen oder starten
* Adaptive Lighting togglen
* Lichtstimmungen setzen
* Musik & Lautstärke anpassen

---

## 👤 SB6 – Guest Visiting

**Datei:** `sb_guest_visiting.yaml`

Aktiviert „Gastbesuch“-Profil:

* ausgewählte Lichter an
* bestimmte Automationen deaktivieren
* Gast-Automation einschalten

---

## 🛏️ SB7 – Guest Overnight

**Datei:** `sb_guest_overnight.yaml`

Setzt das System über Nacht in „Gast-Schlafmodus“.

---

## 🤖 SB8 – Cleaning Routine (Roborock)

**Datei:** `sb_cleaning_routine.yaml`

Startet spezielle Reinigungsprogramme:

* Küche
* Gästezone
* Eingangsbereich
* Badezimmer

Inklusive Mop-Einstellungen & Segment-Cleaning.

---

## 💡 SB9 – All Lights Off

**Datei:** `sb_all_lights_off.yaml`

Schaltet definierte Bereiche vollständig aus.

---

# 🧩 Architektur & Namensschema

| Kategorie | Typ        | Bedeutung                               |
| --------- | ---------- | --------------------------------------- |
| **M***    | Automation | Motion/Presence-basierte Logik          |
| **C***    | Automation | Contact-Sensor Logik                    |
| **B***    | Automation | Button-/Remote-Steuerung                |
| **L***    | Automation | Lux-/Modus-basierte Steuerung           |
| **SB***   | Script     | komplexe Abläufe (Sequenzen & Routinen) |

Namensschema gewährleistet:

* Skalierbarkeit
* Systematische Erweiterung
* Einfache Wiedererkennung

---

# 🧪 Qualität & Standards

Alle Blueprints:

* folgen strengem 2-Leerzeichen-YAML-Standard
* sind *raw-import-kompatibel*
* nutzen Home Assistant Selector-Standards
* funktionieren ohne weitere Anpassungen

---

# 📜 Lizenz

MIT License

---

# 🙌 Feedback & Beiträge

Verbesserungen oder Erweiterungen willkommen!
→ Erstelle ein Issue oder öffne einen Pull Request.

```

---

# 🎉 Bereit für GitHub!

Wenn du willst, kann ich:

✅ alle Script-Blueprint-Dateien sofort generieren  
✅ ein automatisches JSON-Indexfile erzeugen  
✅ eine Versionierung (semantic versioning) vorbereiten  
✅ ein GitHub Actions YAML für YAML-Linting hinzufügen  

Sag einfach: **„Bitte alle Script-Blueprints generieren“**.
