# Software_Engineering_Class

Gruppenname
Die Drei Muskeltiere
Ziel:
PDF mit allen Sachen alle Diagramme
PDF leserlich

75% Document Architecture
25% Detailed Design

Programmiersprache auswährlen, warum abwägen usw. Wahl für sprache

Deployment Program

Sequence Diagramme
(auf punkteverteilung achten um zu verstehen den Umfang)

Fokus aufemergency stop

Klassendiagramme zum detailed design

Vereinfachen das System ohne ROS, Kamera fusioniert mit LiDAR liefert daten.
Lidar daten filtern müssen wir nicht machen. wir bkeommen dirket daten zum nächstliegenden Objekt

Arduino slave
CAN Pakete kommen rein, gibt werte raus

emergency stop nah an Motorsteuerung

WLAN USW. ignorieren. Fikus nur auf ES.

Component Overview beacahten 

es sollte eindeutig sein, worauf ES läuft, verraten wollte er es aber nicht
(Erste Vermutung: Arduino Slave)

Notbremse bei ROT
TTC bei Gelb und Grün == automatisiiert weiterfahren

ES nur bei ROT und Pilzknopf und Taster vorne...

TTC gehört nicht zu ES sondern zu Normal Operation

"Normal Operation" ist gelb und grün

sobald einObjekt in rot == ES übernimmt und alles blockiert bis Taster wieder freigibt

gerne gesehen: funktionalität zum error loggen
Klasse die Informationen bereitstellt und weitergibt
== nicht pflicht 
selber assuchen, geht nur um möglichekeot, ansdere systeme sind blackbox
also nur error_logging
z.b verschiedene level: error, warning, info mit zeitstempel
Error Logging auch= ES auslösung 

keine sensordaten= stopp + logging


Klasse fpr CAN DAten, da OOP

Architketur dokumentieren, warum diese Entscheidung

