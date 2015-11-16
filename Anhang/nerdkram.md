## Nerdkram

### Sketche mit Atom schreiben

[Atom](https://atom.io/) ist ein feiner Editor, der plattformübergreifend für verschiedenste Zwecke genutzt werden kann. Für das Schreiben von Processingsketchen liegen schon einige Packages vor, die jedoch nur für die Java-Variante taugen. Das Package [processing](https://github.com/bleikamp/processing) von [bleikamp](https://github.com/bleikamp) dient als Grundlage für die folgenden Arbeitsschritte, da es leicht angepasst werden kann.

### Processing.py installieren

Processing.py-Sketche werden aus Atom über die Kommandozeile gestartet. Dazu muss der Python-Mode heruntergeladen werden. Das entsprechende Repo findet sich bei [Github](https://github.com/jdf/processing.py).

### Package anpassen

Die folgende Zeile in `lib/processing.coffee` muss verändert werden:

```coffee
args = ["--force", "--sketch=#{folder}", "--output=#{build_dir}", "--run"]
```

wird zu

```coffee
args = ["#{file.path}"]
```

### Processing von der Kommandozeile ausführbar machen

In den Einstellungen des Packages ist nun noch der Pfad zum Shellskript zu hinterlegen, das Processing.py auf der Kommandozeile ausführbar macht. (Linux).

```
processing-py.sh
```

### Syntax Highlighting für .pyde

Um in Atom das Syntax Highlighting für `.pyde`-Dateien einzustellen, muss ein knapper Eintrag in der `config.json` ergänzt werden:

```
# Atom's config.json

"*":
  core:
    customFileTypes:
      "source.python": [
        "pyde"
      ]
```

Anschließend muss Atom neu geladen werden.