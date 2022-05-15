---
share: True
description: 11ty Grundinstallation auf Raspberry
category: "Obsidian Notizen/FH 🏫/MobCo/Ideen & Experimente"
---
# 11ty Grundinstallation

## Betriebssytem und erster Zugriff
Für dieses Projekt wurde **Raspberry Pi OS Lite 64bit** gewählt.

Es wurde mit dem Raspberry Pi-Imager auf einen USB-Stick installiert und direkt im Imager wurde SSH aktiviert.

Um den Raspberry Pi im Netzwerk zu finden, kann man entweder einen Netzwerk-Scanner verwenden oder auf dem heimischen DHCP-Server nachsehen und so die IP-Adresser herausfinden.

### Installation und Vorbereitungen
1. Den Raspberry updaten
	```
	sudo apt update && sudo apt upgrade -y
	```

2. Das Paket npm installieren   
	```
	sudo apt install npm
	```

3. 11ty über npm installieren   
   ```
   npm install --save-dev @11ty/eleventy
   ```

Nun können Beliebige Starter Projects geklont werden, oder eigene Projekte erstellt werden.