---
share: True
description: Testnotiz
category: Obsidian Notizen
---
# Testnotiz von gmpfeifer

~~Test Test~~
==Hallo Hallo?==
**Ist da wer?**


### "Ergebniskästchen"
Das folgende "Ergebniskästchen" wurde mit einer Anpassung verwirklicht:

``` markdown title="Keyboard keys"
++ctrl+alt+del++
```


<div class="result" markdown>

++ctrl+alt+del++

</div>

#### In Obsidian folgendes einfügen
````markdown title="Keyboard keys"
	``` markdown title="Keyboard keys"
	++ctrl+alt+del++
	```
	
	<div class="result" markdown>
	++ctrl+alt+del++
	</div>
````

#### In der mkdocs.yml
``` yaml
	markdown_extensions:
		- md_in_html
```



Graph Test
``` mermaid
graph LR
  A[Start] --> B{Error?};
  B -->|Yes| C[Hmm...];
  C --> D[Debug];
  D --> B;
  B ---->|No| E[Yay!];
```

!!! INFO
	Test eines Obsidian Callouts

!!! BUG
	Test eines Obsidian Callouts

!!! Warning
	Test eines Obsidian Callouts