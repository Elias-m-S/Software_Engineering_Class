# Software_Engineering_Class

## Gruppe

- **Gruppenname:** Die Drei Muskeltiere

## Ziel / Deliverable

- **Ziel:** Eine **leserliche PDF**, die **alle Inhalte und alle Diagramme** enthält.

## Bewertung / Schwerpunkte

- **75%** Document Architecture
- **25%** Detailed Design

## Grundlegende Entscheidungen (laut Aufgabenstellung)

- **Programmiersprache auswählen** (C oder C++) und **begründet abwägen**, warum diese Wahl getroffen wurde.
- **Architektur dokumentieren** und die **Rationale** für die Entscheidung festhalten.

## Benötigte Diagramme / Artefakte (Fokus in der Bearbeitung)

- **Deployment** (Hardware/Software-Mapping; „Deployment Program“).
- **Sequence Diagramme**
	- Auf die **Punkteverteilung** achten, um den erwarteten **Umfang** zu verstehen.
	- **Stimac wichtig:** die **dynamische Geschichte** des Systems modellieren (Interaktionen/Sequenzen).
- **Klassendiagramme**
	- Für **Detailed Design** insbesondere: **Klassendiagramme** und **Funktionen ausführlich** spezifizieren.

## Scope / Vereinfachungen (für unser Modell)

- System vereinfachen: **ohne ROS**.
- **Kamera fusioniert mit LiDAR** und liefert Daten (Sensor-Fusion wird als gegeben betrachtet).
- **LiDAR-Daten filtern** müssen wir nicht: wir bekommen **direkt die Distanz zum nächstliegenden Objekt**.
- **WLAN usw. ignorieren**: Fokus nur auf **Emergency Stop (ES)**.
- **Component Overview beachten**.

## Hardware-/Komponentenannahmen

- **Arduino Slave:** CAN-Pakete kommen rein, gibt Werte raus.
- **Emergency Stop** möglichst **nah an der Motorsteuerung**.
- Es sollte **eindeutig** sein, **worauf ES läuft**; er wollte es nicht verraten.
	- **Erste Vermutung:** ES läuft auf dem **Arduino Slave**.

## Verhalten: Operation Zones / ES vs. Normal Operation

- **Notbremse bei ROT**.
- **TTC** bei **Gelb und Grün** → **automatisiert weiterfahren**.
- **ES nur** bei:
	- **ROT**
	- **Pilzknopf** (Emergency-Button)
	- **Taster vorne**
- **TTC gehört nicht** zu ES, sondern zu **Normal Operation**.
- **„Normal Operation“** ist **Gelb und Grün**.
- Sobald ein Objekt in **Rot** ist: **ES übernimmt** und **blockiert alles**, bis der **Taster wieder freigibt**.

## Logging / Error Handling (nice-to-have, aber gern gesehen)

- Gerne gesehen: **Funktionalität zum Error-Loggen**.
	- Eine **Klasse**, die Informationen bereitstellt und weitergibt.
	- **Nicht Pflicht** (optional).
	- Selbst ausarbeiten: andere Systeme sind **Blackbox**, daher nur **Error Logging** modellieren.
	- Beispiel: verschiedene Level (**error**, **warning**, **info**) mit **Zeitstempel**.
	- Error Logging auch als Event bei **ES-Auslösung**.
- **Keine Sensordaten** → **Stopp + Logging**.

## Modellierungs-/Designhinweise

- **Klasse für CAN-Daten** (wegen OOP).
- **Interfaces** gerne **ausgearbeitet**, nicht nur eine einzelne Funktion; ebenso beim Logging.
- **Stimac nicht wichtig / out of scope:** Wie genau ein **CAN-Paket reinkommt** usw. (außerhalb des Scopes).

