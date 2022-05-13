---
share: True
description: Großes Projekt in Mobile Computing Vorlesung
category: Obsidian Notizen/FH/MobCo
---
# Großes Projekt - Raspberry Pi NAS mit SATA über PCIe

## Hardware-Beschaffung
### Compute Module 4
Da Compute Module zum Zeitpunkt des Projektstarts schwer erhältlich waren, wurde ein gebrauchtes Compute Module 4 (CM4) mit 4GB RAM und 8GB eMMC von ebay.de aus Deutschland bestellt.

![[Pasted image 20220513165329.png]]



### Compute Module 4 IO Carrier Board
Das offizielle IO Board für das CM4 war glücklicherweise gut erhältlich und konnte sogar in Österreich bei semaf-electronics bestellt werden. https://electronics.semaf.at/Raspberry-Pi-Compute-Module-4-IO-Board

![[raspberry-pi-compute-module-4-io-board.jpg.webp]]


### PCIe zu 6x SATA HBA
Um am CM4 Festplatten verwenden zu können, wurde ein Adapter/Board für den PCIe-Slot bestellt, der 6 SATA Ports hat. Das Board wurde von Amazon.de bestellt. https://www.amazon.de/gp/product/B097RBLM9G/ref=ppx_yo_dt_b_asin_title_o00_s02?ie=UTF8&th=1

![[715q7Jg5RvL._AC_SL1500_.jpg]]

### Thermaltake ATX Power Supply & Thermaltake ITX Gehäuse
Um die Festplatten mit Strom versorgen zu können wurde eine PC Netzteil bestellt. Das Netzteil hat zwar eine völlig überdimensionierte Ausgangsleistung, jedoch ist das Netzteil schon in Vorraussicht für ein anderes Projekt eingeplant worden. https://www.amazon.de/gp/product/B01K7VLNWA/ref=ppx_yo_dt_b_asin_image_o00_s00?ie=UTF8&th=1

![[71gWZ2-mD-L._AC_SL1500_.jpg]]


Aus dem selben Grund wurde ein - für den Raspberry Pi viel zu großes - Thermaltake Gehäuse bestellt.
https://www.amazon.de/gp/product/B015UDUAKG/ref=ppx_yo_dt_b_asin_title_o00_s01?ie=UTF8&th=1

![[91cm6Y6DenL._AC_SL1500_.jpg]]


## Flashen des eMMC Moduls
Um das Raspberry Pi Compute Modul 4 verwenden zu können musste zu Beginn ein Betriebssystem auf das eMMC Modul geflasht werden. 
Zuerst wurde das CM4 auf das IO Board platziert. Auf dem nachfolgenden Foto ist außerdem bereits zu sehen, wie die externe Stromversorgung (liegender Stecker), der Lüfter für das Gehäuse (stehender 3-Pin Stecker) und ein LAN-Kabel verbunden wurde.

![[compute-module-io.png]]

Dann muss am 'J2' Jumper auf dem IO Board auf das erste Paar von links ein Jumper gesetzt werden