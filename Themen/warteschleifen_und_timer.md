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

Ausgehend von den Eigenschaften von `millis()` können wir Timer bauen, die zwei Möglichkeiten bieten:

- ein Ereignis tritt **einmalig** nach einer bestimmten Zeit ein
- ein Ereignis tritt **wiederholt** nach einer bestimmten Zeit ein

Zunächst etwas zur Logik des Timers. Wenn wir durch `millis()` jederzeit wissen, wie lange der Sketch schon läuft, dann können wir auch immer sagen, wieviel Zeit seit einem bestimmten Zeitpunkt vergangen ist.

```python
t0 = 876234  # "eben" in Millisekunden
t1 = 1032847 # "jetzt" in Millisekunden

diff = t1 - t0 # Ergebnis: 156613 Millisekunden
```

Wenn wir also die Differenz zwischen "eben" und "jetzt" errechnen, können wir auch sagen, ob das für unsere Zwecke schon genug vergangene Zeit ist. Gemäß unserem Beispiel wäre erst "genug Zeit" vergangen, wenn `diff` größer oder gleich 200000 ist. Prüfen wir `diff` fortlaufend in der `draw()`, kommt irgendwann der Zeitpunkt, der unser Kriterium erfüllt. In Code können wir diese Gedanken wie folgt abbilden:

```python
wartezeit = 2000 # 2 Sekunden
    
def draw():
    if (millis() > wartezeit):
        # Ereignis, das erst stattfindet, wenn die 
        # Wartezeit rum ist
        ellipse(10,10,10,10)
```

Mit dieser Lösung können wir Ereignisse nach dem Start des Programms einmal eintreten lassen. Wie können wir aber **wiederholt** etwas in einem bestimmten zeitlichen Abstand eintreten lassen?

```python
wartezeit = 1000
# Variable, die immer die Millisekunden des aktuellen Beobachtungszeitpunkts speichert
lastMillis = 0



def draw():
    # Das folgende nur ausführen, wenn der Rückgabewert
    # von wait() True ist
    if wait():
        ellipse(random(width), random(height), 10, 10)

def wait():
    global lastMillis
    if ((millis() - lastMillis) > wartezeit): # [1]
        # Den Beobachtungszeitpunkt neu setzen
        lastMillis = millis() # [2]
        return True
```

Wenngleich die Menge an Code auch mehr geworden ist, so ist die Idee hinter der Lösung dieselbe wie eben: 

In der Funktion `wait()` wird eine Bedingung formuliert (vgl. Kommentar [1]), die vom augenblicklichen Millisekundenwert `millis()` den letzten, also `lastMillis` subtrahiert. 

Am Anfang ist `lastMillis = 0`. Das heißt, das erste Ereignis tritt erst ein, wenn `millis()` größer ist als `wartezeit`. Anschließend wird `lastMillis` auf den Wert von `millis()` gesetzt und damit quasi eingefroren (vgl. Kommentar [2]). Die Uhr läuft aber weiter, sodass nun der gespeicherte Wert `lastMillis` von `millis()` substrahiert wird, bis das Ergebnis wieder `wartezeit` überschreitet. Und so fort. Die Folge ist jede Sekunde ein neuer Kreis auf der Leinwand.


