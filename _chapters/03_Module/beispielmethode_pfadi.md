---
title: Blinkende LED
number: 3.2.1
---
> Das Modul funktioniert mit den Raspberry Pi Modellen A+, B+, Pi 2  und Pi 3.

#### Zielgruppe:
Pfadfinderinnen- und Pfadfinderstufe

#### Zielsetzung:
einfache elektronische Scahltung, erste Schritte mit dem Wiring-Tool

#### Dauer:
ca. 30 Minuten

#### Material:
- 1 Raspberry Pi (Modell A+, B+, Pi 2 oder Pi 3)
- 1 LED (5 mm)
- 1 Widerstand (220 &#8486;)
- 2 Kabel (female auf male)
- Steckbrett (Breadboard)

##### Abb: Schaltplan für Raspberry Modell B+ und Modell Pi 2
![Schaltplan LED & Raspberry Modell Pi 2](images/fritzing/blinking_Steckplatine.png)

##### Abb: Schaltplan für Raspberry Modell Pi A+
![Schaltplan LED & Raspberry Modell Pi A+](images/fritzing/blinking_Modell_B_Steckplatine.png)

Kopiere den unten stehenden Code in die Zwischenablage deines Rechners. Füge dann den Code über den _Import Nodes Dialog_ ein ( Import From - Clipboard in der Dropdown-Navigation, or Ctrl-I ). Den Import mit _Okay_ bestätigen. Verschiebe jetzt noch den neuen Flow ein wenig.

Klick dann auf den "**_deploy button_**" und der Flow sollte starten.
Nach erflogreichem Start sollte die LED im Wechsel von einer Sekunden ein- und ausgeschaltet werden.

<video controls="controls">
  <source type="video/mp4" src="videos/nodered_import.mp4"></source>
  <source type="video/webm" src="videos/nodered_import.webm"></source>
  <p>Your browser does not support the video element.</p>
</video>

```
[{"id":"b97752d2.e8ff","type":"function","z":"e3d3386.3d87dc8","name":
"Toggle 0/1 on input","func":"\ncontext.state = context.state
|| 0;\n\n(context.state === 0) ? context.state = 1 :
context.state = 0;\nmsg.payload = context.state;\n\nreturn msg;",
"outputs":1,"noerr":0,"x":403,"y":177,
"wires":[["50192b0a.c61af4"]]},
{"id":"6dec1b33.7a8734","type":"inject","z":"e3d3386.3d87dc8",
"name":"","topic":"","payload":"","payloadType":"date",
"repeat":"1","crontab":"","once":false,"x":141,"y"
:99,"wires":[["b97752d2.e8ff"]]},
{"id":"50192b0a.c61af4","type":"rpi-gpio out",
"z":"e3d3386.3d87dc8",
"name":"","pin":"7","set":"","level":"0",
"out":"out","x":682,"y":102,"wires":[]}]
```
