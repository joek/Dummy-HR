---
title: Blinkende LED
number: 3.1
---
#### Zielgruppe:
Pfadfinderinnen- und Pfadfinderstufe

#### Zielsetzung:


#### Dauer:
ca. 30 Minuten

#### Material:
- Raspberry Pi
- 1 LED (5 mm)
- 1 Widerstand ( Ohm)

> Das Modul funktioniert mit den Raspberry Pi Modellen A+, B+ und Pi 2.

##### [Abb: Schaltplan für Raspberry Modell B+ und Modell Pi 2]
![Schaltplan LED & Raspberry Modell Pi 2](images/fritzing/blinking_Steckplatine.png)

##### [Abb: Schaltplan für Raspberry Modell Pi A+]
![Schaltplan LED & Raspberry Modell Pi A+](images/fritzing/blinking_Modell_B_Steckplatine.png)

Kopiere den unten stehenden Code in die Zwischenablage und füge diesen in den _Import Nodes Dialog_ ein (Import From - Clipboard im dropdown menu, or Ctrl-I). Den Import mit Okay bestätigen. Verschiebe jetzt noch den neuen Flow ein wenig.

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

Klick auf den "**_deploy button_**" und der flow sollte starten.
Die LED sollte dann, nach dem erflogreichen Start, für im Wechsel von einer Sekunden ein und ausgeschaltet werden.
