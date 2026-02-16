# Software Engineering – Program Design (DHBW)

**Gruppe:** Die Drei Muskeltiere

Dieses Repository enthält unsere Ausarbeitung zum *Program Design* im Modul **Software Engineering** (DHBW Ravensburg, Campus Friedrichshafen). Ziel ist ein **System Design Document (PDF)**, das die **Software-Architektur** des Truck-Systems dokumentiert, sowie ein **detailliertes UML-Design** für das Teil-System **Emergency Stop**.

## Scope (Kurzüberblick)

- Fokus auf der **Software im Truck** (die PC-Anwendung ist explizit out of scope).
- Schwerpunkt in der Modellierung: **Emergency Stop** nahe an der Motor-/Drive-Control.
- Vereinfachte Annahmen aus der Vorlesung/Übung:
  - Kein ROS/WLAN-Fokus; Sensor-Fusion ist als Blackbox betrachtet.
  - LiDAR liefert direkt die relevanten Distanzinformationen zum nächstliegenden Objekt.

## Inhalte / Erwartete Ergebnisse

Im System Design Document werden u.a. folgende Aspekte abgedeckt:

- **Architektur-Übersicht** (z.B. Context Diagram + Subsystem-Zerlegung)
- **Subsystem-Verantwortlichkeiten** (Class Diagrams mit Attributen und Public Operations)
- **Hardware/Software-Mapping** (Deployment Diagram)
- **Global Software Control** (Sequence Diagrams; Interaktion mit Emergency Stop)
- **Boundary Conditions** (Sequence Diagrams für Start-up, Shutdown, Error Scenario)
- **Detailed Design** für die zentrale Emergency-Stop-Klasse
  - Private Methoden
  - Sequenzdiagramm (externe Interfaces + interne Calls)
  - State-Machine- oder Activity-Diagramme pro Methode (mit Notes/Comments)

Inhaltlich unterscheiden wir grob zwischen:

- **Normal Operation** (Gelb/Grün): TTC-Observer überwacht und erlaubt Auto-Recovery.
- **Safety-Zone / Emergency Stop** (Rot): Emergency Stop übernimmt und blockiert, bis eine Freigabe über Button erfolgt.

Optional (wenn sinnvoll im Modell): **Error Logging** inkl. Zeitstempel/Level (Error/Warning/Info), z.B. auch als Event bei ES-Auslösung oder fehlenden Sensordaten.


## Hinweise

- Das **Enterprise-Architect-Projekt** dient als Supplement; bewertet wird der Inhalt im **System Design Document (PDF)**.
- Die Dokumentation enthält außerdem eine kurze **Begründung der Architektur- und Sprachwahl (C vs. C++)** inkl. Alternativen.
