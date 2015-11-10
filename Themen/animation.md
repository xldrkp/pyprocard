## Das Wesen der Animation

Die Stärke von Processing liegt darin, dass Grafiken einfach animiert werden können. Entweder geschieht dies durch den Einsatz von Zufallsfunktionen wie `random()` oder `noise()` oder durch Interaktion des Users mit dem Programm.

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

Die letzte Zeile des kleinen Programms ist für die Bewegung des Balls verantwortlich: Zum augenblicklichen Wert der Variablen `x` wird `1` hinzuaddiert und das Ergebnis wiederum `x` zugewiesen. So wächst der Wert von `x` bei jedem Durchlauf der Endlosschleife `draw()` um `1`. Der Ball bleibt stehen, wenn `x` die Breite der Leinwand erreicht hat.