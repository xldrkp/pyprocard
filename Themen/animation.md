## Das Wesen der Animation

Die Stärke von Processing liegt darin, dass Grafiken einfach animiert werden können. Entweder geschieht dies durch den Einsatz von Zufallsfunktionen wie `random()` oder `noise()` oder durch Interaktion des Users mit dem Programm.

Die einfachste Animation besteht in der Veränderung der Koordinaten eines Objekts auf der Leinwand. Das kann ein Punkt sein, eine Linie oder auch eine dreidimensionale Figur. Die Mathematik dahinter ist einfach:

```python
x = x + 1
```

Auch wenn der Ausdruck trivial erscheint, liegt darin doch eine Hürde für viele Einsteigerinnen und Einsteiger. Was aber hat diese einfache Rechnung mit Animationen zu tun?

```python

x = 0;

def draw():
    global x
    background(255)
    ellipse(x, 50, 10, 10)
    if x < width: 
        x = x + 1
```
