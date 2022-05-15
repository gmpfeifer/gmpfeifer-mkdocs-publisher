---
share: True
description: Großes Projekt in Mobile Computing Vorlesung
category: Obsidian Notizen/FH 🏫/MobCo/Großes Projekt
---
# Flashen des eMMC Moduls
## IO Board für Mount auf PC vorbereiten
Um das Raspberry Pi Compute Modul 4 verwenden zu können musste zu Beginn ein Betriebssystem auf das eMMC Modul geflasht werden. 
Zuerst wurde das CM4 auf das IO Board platziert. Auf dem nachfolgenden Foto ist außerdem bereits zu sehen, wie die externe Stromversorgung (liegender Stecker), der Lüfter für das Gehäuse (stehender 3-Pin Stecker) und ein LAN-Kabel verbunden wurde.

![[compute-module-io-board.jpg]]

Dann musste am 'J2' Jumper auf dem IO Board auf das erste Paar von links ein Jumper gesetzt werden. Da ich keinen richtigen Jumper hatte, aber schon unbedingt das Compute Modul booten wollte, habe ich eine zurechtgebogene Büroklammer verwendet.
![[IMG_0106.jpg]]

Danach konnte ein Micro-USB Kabel - mit dem USB-Slave Port auf dem IO Board auf der einen Seite und einem Computer auf der anderen Seite - verbunden werden.
![[MicroUSB.jpg]]

Als letztes wurde eine Stromversorgung verbunden. Am Board get die rote "D1" LED an, aber das Compute Modul bootet nicht. Das eMMC Modul sollte für den nächsten Schritt bereit sein.

## Mit usbboot den eMMC Speicher mounten
In diesem Schritt wurde der eMMC Speicher nun wirklich gemountet. Die Schritte wurden auf einem Mac in der Shell durchgeführt und funktionieren unter Windows vermutlich ähnlich. 

Als erstes wurde versichert, dass libusb installiert ist:
- Auf einem Mac auf dem Homebrew installiert ist, kann folgendes ausgeführt werden: `brew install pkgconfig libusb`
- Auf Linux kann folgendes ausgeführt werden: `sudo apt install libusb-1.0-0-dev`

Als nächstes wurde das folgende GitHub Repository geklont:
```bash
git clone --depth=1 https://github.com/raspberrypi/usbboot
```


Als nächstes wurde in den neuen Ordner gewechselt und mit `make` das Tool gebaut.
```bash
cd usbboot
make
```


In diesem Ordner sollte eine ausführbare Datei `rpiboot` sein. Um den eMMC zu mounten wurde es ausgeführt:
```bash
sudo ./rpiboot
```


Während des Vorgangs blinkte die D2 LED und nachdem das Skript seinen Vorgang abgeschlossen hatte, erschien die `boot` Partition im Raspberry Pi Imager.

## Raspberry Pi OS auf eMMC flashen
Der eMMC Speicher verhält sich jetzt wie eine MicroSD-Karte oder ein USB-Stick auf den man einfach ein beliebiges Image mit dem Raspberry Pi Imager oder anderen Tools schreiben kann: 
![[select-sd-card-raspberry-pi-imager.png]]

Es wurde Raspberry Pi OS 64-bit auf das Modul geschreiben, wobei hier in den Einstellungen des Raspberry Pi Imagers noch die ssh-Verbindung aktiviert wurde, um beim ersten Bootvorgang keinen Bildschirm anschließen zu müssen.

Am Schluss wurde die Stromverbindung getrennt, der Jumper entfernt und danach eine LAN-Verbindung angeschlossen und der Strom wieder angeschlossen und danach auf das Abschließen des Bootvorgangs gewartet.