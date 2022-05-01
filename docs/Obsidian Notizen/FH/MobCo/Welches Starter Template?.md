---
share: True
description: "Welche 11ty starter page? Tests dazu hier"
category: Obsidian Notizen/FH/MobCo
---
# Which eleventy starter page for a blog?

Related: [[11ty Grundinstallation]]

### Tests + Links
1. **Eleventy Garden:** Github Repo [Eleventy-Garden](https://github.com/binyamin/eleventy-garden) 
2. **Eleventy Duo:** Github Repo [Eleventy-Duo](https://github.com/yinkakun/eleventy-duo)


In einem eigenen Ordner im Home-Directory wurden die Tests abgespeichert
```

mkdir 11ty
```



### 1. Eleventy Garden

In den Test-Ordner wechseln, falls noch nicht passiert:
```

cd 11ty
```


Repo klonen:
```

git clone https://github.com/binyamin/eleventy-garden
```


Site installieren und den initialen Build ausführen:
```

cd eleventy-garden
npm install
npm run build
```


Die Site starten
```

npm run start
```



Nun kann das Template betrachtet werden & man kann an der Seite mit **Hot Reloads** gearbeiter werden.
Das bedeutet, dass Änderungen von Files automatisch aktualisiert werden und im Browser betrachtet werden können.


### 2. Eleventy + Ghost
Leider nicht sinnvol für diese Anwendung, weil man den Content über Ghost zur Verfügung stellen muss...





#### später (Für Wiki/Doku oder auch Digital Garden)

MKDocs: https://github.com/jobindj/obsidian-publish-mkdocs
→ angewendet auf  https://lyz-code.github.io/blue-book/

~~==oder lieber Spacebook:==~~ https://spacebook.app
Spacebook nicht perfekt, da nicht einfach mit Obsidian kompatibel