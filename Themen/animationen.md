## Animationen

Die Stärke von Processing liegt darin, dass Grafiken einfach animiert werden können. Entweder geschieht dies durch den Einsatz von Funktionen wie `random()`, `noise()` und anderen Arten der Berechnung, durch Interaktion des Users mit dem Programm oder durch die Abfrage von Sensoren (vgl. den [Abschnitt zum Arduino](../Arduino/0-einleitung.md)).

Die einfachste Animation besteht in der Veränderung der Koordinaten eines Objekts auf der Leinwand. Das kann ein Punkt sein, eine Linie oder auch eine dreidimensionale Figur. Die Mathematik dahinter ist einfach:

```python
x = x + 1
```

Auch wenn der Ausdruck trivial erscheint, liegt darin doch eine Hürde für viele Einsteigerinnen und Einsteiger. Was aber hat diese einfache Rechnung mit Animationen zu tun? Ein Beispiel:

```python
# Bewegung eines Balls von links nach rechts

# Startwert auf der x-Achse
x = 0;

def draw():
    # Schreibenden Zugriff auf die Variable x
    # außerhalb der Funktion
    global x
    # Löschen des Hintergrunds
    background(255)
    # Zeichnen des Balls
    ellipse(x, 50, 10, 10)
    # Prüfen, ob der Ball schon den rechten Rand
    # der Leinwand erreicht hat
    if x < width: 
        # Sonst inkrementieren
        x = x + 1
```

Das Konzept des Ausdrucks `global x` kann im Kapitel [
Variablen](../Programmiergrundlagen/variablen.md) vertieft werden.

Die letzte Zeile des kleinen Programms ist für die Bewegung des Balls verantwortlich: Zum augenblicklichen Wert der Variablen `x` wird immer `1` hinzuaddiert und das Ergebnis anschließend `x` zugewiesen. So wächst der Wert von `x` bei jedem Durchlauf der Endlosschleife `draw()` um `1`. Der Ball bleibt stehen, wenn `x` die Breite der Leinwand erreicht hat.

### Geschwindigkeit

Das Inkrementieren von `x` bringt eine gleichbleibende Geschwindigkeit des Balls mit sich. Will man hier mehr Flexibilität, muss auch der Wert, um den `x` erhöht wird, variabel sein:

```python
# Bewegung eines Balls von links nach rechts

# Startwert auf der x-Achse
x = 0;
# Geschwindigkeit des Balls
speed_x = 2

def draw():
    # Schreibenden Zugriff auf die Variablen
    # außerhalb der Funktion
    global x, speed_x
    # Löschen des Hintergrunds
    background(255)
    # Zeichnen des Balls
    ellipse(x, 50, 10, 10)
    # Prüfen, ob der Ball schon den rechten Rand
    # der Leinwand erreicht hat
    if x < width: 
        # Sonst um den Wert von speed_x erhöhen
        x = x + speed_x
```
Natürlich kann die Geschwindigkeit auch von anderen Faktoren abhängig gemacht werden, bspw. von `random()`, Sensorwerten eines Arduino oder von Berechnungen ganz anderer Art.

### Bewegungsumkehr

In unserem Beispiel stoppt der Ball, sobald er den rechten Rand erreicht hat. Will man, dass er dann wieder umkehrt, ist ein anderes einfaches Prinzip anzuwenden: Es muss der Wert für die Geschwindigkeit nicht mehr addiert, sondern subtrahiert werden:

```python
x = x - 1
```

Erweitern wir den letzten Stand unseres Beispiels:

```python
# Bewegung eines Balls von links nach rechts

x = 0;
speed_x = 2

def draw():
    global x, speed_x
    background(255)
    ellipse(x, 50, 10, 10)
    # Prüfen, ob der Ball schon den rechten oder
    # linken Rand der Leinwand erreicht hat 
    if x > width or x < 0: 
        # Sonst das Vorzeichen von speed_x durch die
        # Multiplikation mit -1 umkehren
        speed_x = speed_x * -1
    # Unterschied zu vorher! Die Addition, die x verändert,
    # wird in jedem Fall ausgeführt. Ob es sich um eine 
    # Verringerung oder Erhöhung von x handelt, hängt vom 
    # Vorzeichen von speed_x ab.
    x = x + speed_x
```

Wir sehen nun einen Ball auf der x-Achse pendeln.

### Lernvorschläge

1. Sorge dafür, dass der Ball auch auf der y-Achse bewegt wird.
2. Lies das Kapitel [Vectors](http://natureofcode.com/book/chapter-1-vectors/) in Daniel Shiffmans Buch "The Nature of Code" (Shiffman, 2012). Beachte dabei, dass alle Beispiele die Java-Syntax verwenden!

