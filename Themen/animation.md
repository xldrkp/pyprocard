## Das Wesen der Animation

Die Stärke von Processing liegt darin, dass Grafiken einfach animiert werden können. Entweder geschieht dies durch den Einsatz von Zufallsfunktionen wie `random()` oder `noise()` oder durch Interaktion des Users mit dem Programm.

Die einfachste Animation besteht in der Veränderung der Koordinaten eines Objekts auf der Leinwand. Das kann ein Punkt sein, eine Linie oder auch eine dreidimensionale Figur. Die Mathematik dahinter ist einfach:

```python
x = x + 1
```

Auch wenn der Ausdruck trivial erscheint, liegt darin doch eine Hürde für viele Einsteigerinnen und Einsteiger. Was aber hat diese einfache Rechnung mit Animationen zu tun?

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
