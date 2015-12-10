## Warteschleifen und Timer

Komplexere Animationen und Visualisierungen erfordern häufig eine genaue zeitliche Abstimmung ihrer Komponenten aufeinander. Das heißt, dass manchmal gewartet werden muss, bis etwas passiert oder passieren darf. Um in Processing "zu warten" gibt es eine Möglichkeit, die im folgenden vorgestellt werden soll.

### Die Zeit messen mit Processing

Processing kennt eine Funktion `millis()`, die die vergangenen Millisekunden seit dem Start des Sketches zählt. Zur Erinnerung: 1000 Millisekunden sind 1 Sekunde.

Das folgende Programm gibt diesen Wert fortlaufen aus. Dabei ist es mit der Ausgabe nicht so schnell, dass alle Werte erscheinen würden:

```python
def draw():
    print(millis())
```

Das liegt daran, dass die Wiederholfrequenz der `draw()`-Schleife auf eine bestimmte Rate eingestellt ist: 60 fps (vgl. https://processing.org/reference/frameRate_.html). Eine Erweiterung unseres Programmbeispiels fördert in der Folge eine andere Ausgabe zu Tage:

```python
def setup():
    # Wiederholfrequenz der draw()-Schleife 1 Sekunde
    frameRate(1)

def draw():
    print(millis())
```

Die Verringerung der Wiederholfrequenz durch `frameRate()` bringt in der Regel nicht viel für die zeitliche Kontrolle eines Sketches, da der **gesamte** Ablauf beeinflusst wird. Eine andere Lösung muss her, die sich `millis()` zunutze macht.

### Einen Timer bauen

Ausgehen von den Eigenschaften von `millis()` können wir einen Timer bauen, der zwei Möglichkeiten bietet:

- ein Ereignis tritt **einmalig** nach einer bestimmten Zeit ein
- ein Ereignis tritt **wiederholt** nach einer bestimmten Zeit ein

Zunächst etwas zur Logik des Timers. Wenn wir durch `millis()` jederzeit wissen, wie lange der Sketch schon läuft, dann können wir auch immer sagen, wieviel Zeit seit einem bestimmten Zeitpunkt vergangen ist.

Ein Beispiel: t0 = 

