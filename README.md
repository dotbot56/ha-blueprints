# 🏠 Home Assistant Blueprints – Dotbot  
Professionelle, modulare und wiederverwendbare Automationsvorlagen  
nach dem Schema **M1, M2, C1, B1, B2, L1**

Dieses Repository enthält strukturierte, kategorisierte und erweiterbare  
Blueprints für Home Assistant.  
Alle Vorlagen basieren auf realen Automationen aus einer produktiven Installation.

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
│   │       ├── l1_illuminance_automation_manager.yaml
│   └── script/
│       └── dotbot/
│           └── .gitkeep
└── examples/
    └── .gitkeep
````

---

# 🚀 Import in Home Assistant

Du kannst jeden Blueprint direkt per **RAW-URL** importieren:

**Home Assistant → Einstellungen → Automationen & Szenen → Blueprints → Importieren**

Beispiel (ersetze `<username>` durch dein GitHub-Profil):

```
https://raw.githubusercontent.com/<username>/ha-blueprints-dotbot/main/blueprints/automation/dotbot/m1_motion_light_basic.yaml
```

---

# 🔥 Blueprint Kategorien (M1, M2, C1, B1, B2, L1)

Klare Struktur – leicht erweiterbar.

---

## 🟦 **M1 – Motion → Light (Basic)**

**Datei:** `m1_motion_light_basic.yaml`

Ein Motion/Presence-Sensor schaltet ein Licht an, und nach einer einstellbaren Zeit ohne Bewegung wieder aus.

**Funktionen:**

* Unterstützt `motion`, `occupancy`, `presence`
* Ein/Aus-Logik
* Auto-Off Delay (Standard 120s)
* Target kann Entity, Device oder Area sein

---

## 🟪 **M2 – Motion → Light (Sleep-Mode aware)**

**Datei:** `m2_motion_light_sleepmode.yaml`

Erweiterung von M1 mit Sleep-Modus–abhängiger Lichtwahl.

**Funktionen:**

* Normales Licht vs. Sleep-Licht
* Sleep-Mode Switch als zusätzliche Bedingung
* Auto-Off für beide Lichtziele

Perfekt für Badezimmer, Schlafzimmer, Gang etc.

---

## 🟫 **C1 – Contact → Light Auto-Off**

**Datei:** `c1_contact_light_autooff.yaml`

Ein Tür-/Fenster-/Schrankkontakt schaltet das Licht beim Öffnen ein
und beim Schliessen oder nach X Sekunden automatisch aus.

**Funktionen:**

* Sofortiges Ausschalten bei „contact = off“
* Optionale Timeout-Abschaltung

---

## 🟧 **B1 – Button → Toggle Target**

**Datei:** `b1_button_toggle_target.yaml`

Ein Zigbee/MQTT-Schalter löst ein frei definierbares Toggle aus.

**Funktionen:**

* Frei wählbarer Service (`light.toggle`, `switch.toggle`, …)
* Volle Target-Auswahl (Entity / Device / Area)
* Unterstützt alle Action-Subtypes (single, double, hold, …)

Ersetzt dutzende kleine Einzelautomationen.

---

## 🟥 **B2 – Button → Script/Scene Trigger**

**Datei:** `b2_button_call_script.yaml`

Ein Button startet ein Script oder eine Szene.

**Typische Anwendung:**

* Sleep-Time
* Sexy-Time
* Cinema-Mode
* Stimmungsszenen

---

## 🟩 **L1 – Illuminance Automation Manager**

**Datei:** `l1_illuminance_automation_manager.yaml`

Skeleton-Blueprint zur Steuerung von Räumen oder Automationen
basierend auf Helligkeitswerten.

**Geplant:**

* Tag / Dämmerung / Nacht Profile
* Automationen aktivieren/deaktivieren
* Lichtszenen abhängig vom Lux-Wert

---

# 🧩 Architektur & Philosophie

Dieses Repo folgt einem klaren, wartbaren Schema:

| Kategorie | Bedeutung                       | Beispiele                        |
| --------- | ------------------------------- | -------------------------------- |
| **M***    | Motion-/Presence-basierte Logik | Lichtsteuerung, Sleep-Mode       |
| **C***    | Contact-Sensor Logik            | Schranklicht, Tür-Licht          |
| **B***    | Button-/Remote-Steuerung        | Toggle, Szenen, Scripts          |
| **L***    | Licht-/Lux-/Modus-Manager       | Tag/Nacht, Automationsverwaltung |

Jede Kategorie ist:

* modular
* austauschbar
* unabhängig versionierbar
* kompatibel mit GitHub Blueprints Import

---

# 🔧 Anforderungen & Hinweise

* YAML-Includes sind **raw-kompatibel**
* keine Tabs, nur **2 Leerzeichen**
* Entity-Selectors folgen Home-Assistant-Standards
* Jede Datei ist sofort importierbar

---

# 📝 Lizenz

Optional MIT, Apache 2.0 oder dein eigener Hinweis.

---

# 🙌 Kontakt & Support

Verbesserungen, Fragen oder Funktionswünsche?
→ Einfach ein GitHub Issue eröffnen!

---

# 🎉 Fertig!

Wenn du möchtest, kann ich zusätzlich:  
✅ eine automatisierte GitHub-*Release-Struktur* erzeugen  
✅ ein *Update-Skript* für Blueprints generieren  
✅ import-fertige *raw URLs* mit deinem GitHub-Namen einsetzen  
✅ CI/CD für YAML-Linting hinzufügen  

Sag einfach, was du brauchst.
