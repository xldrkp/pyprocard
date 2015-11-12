## Schriften einsetzen

Processing wurde als Entwicklungsumgebung besonders für den Einsatz in der Kunst geschaffen. Daher sollen in diesem Abschnitt die Möglichkeiten für die Arbeit mit Typographie ausgelotet werden.

### Mit Typographie spielen

Ein erstes Beispiel soll zeigen, wie man Typographie in eigenen Programmen einsetzen kann:

```python
letter = "A"

def setup():
    # Einkommentieren, um Liste aller verfügbaren Fonts auszugeben
    # print(PFont.list())
    size(800, 800)
    background(255)
    fill(0)
    font = createFont("Arial", 12)
    textFont(font)
    textAlign(CENTER, CENTER)
    

def draw():
    pass
    
    
def mouseMoved():
    background(255)
    textSize((mouseX-width/2)*5+1)
    text(letter, width/2, mouseY)
    
    
def mouseDragged():
    textSize((mouseX-width/2)*5+1)
    text(letter, width/2, mouseY)
 
   
def keyReleased():
    global letter
    if key != CODED:
        letter = key

```
***Listing:*** *Zeichnen mit Buchstaben. Das Beispiel ist dem großartigen Buch "Generative Gestaltung" entnommen und für Python angepasst[^1].*

Mit `createFont()` wird ein vektorbasierter Zeichensatz generiert, mit dem im Anschluss gezeichnet werden kann. Vektorbasiert heißt hier, dass keine Kanten entstehen, wenn Buchstaben vergrößert und verkleinert dargestellt werden.

Die Funktion `textFont()` wählt den Font aus, der zuvor erzeugt wurde. `textAlign()` positioniert Text im Bezug auf die Parameter von `text()`. Zu allen drei Funktionen empfiehlt es sich, die Dokumentationsseiten aus der Processing-Referenz zu lesen - in der Java-Version, denn in der Processing.py-Version fehlen die Erklärungen.

Die Funktion `draw()` hält das Programm am Laufen, was für die permanente Abfrage von Tastatur und Maus notwendig ist. Die Anweisung `pass` darf nicht fehlen, weil Python eine leere Funktion nicht erlaubt.

Das Verhalten des Programms liegt in den Systemfunktionen `mouseMoved()`, `mouseDragged()` und `keyReleased()`. In `mouseMoved()` wird die Leinwand zunächst gelöscht und anschließend mit `textSize()` die größe des Buchstabens aus der Breite der Leinwand und der Mausposition errechnet. Anschließend wird der aktuelle Buchstabe in `letter` in die Mitte der Leinwand auf Höhe der y-Koordinate der Maus gezeichnet.

Die Funktion `mouseDragged()` tut dasselbe wie `mouseMoved()`, ohne aber den Hintergrund zuvor zu löschen.

Die Funktion `keyReleased()` fragt die Tastatur ab und ändert den Wert der Variablen `letter`, sobald eine Taste losgelassen wird.

### Besondere Fonts verwenden

Mit der Anweisung `print(PFont.list())` lässt sich eine Liste aller auf dem aktuellen Computer verfügbaren Schriftarten ausgeben. Reichen diese nicht aus, sind [Google Webfonts](http://www.google.com/webfonts) eine unerschöpfliche Anlaufstelle für Schriftarten jeder Art.



---

[^1]: Bohnacker, H., Gross, B., Laub, J., & Lazzeroni, C. (2009). Generative Gestaltung: entwerfen, programmieren, visualisieren. Mainz: Schmidt, S. 258. Sämtlicher Quellcode des Buchs steht auf der Webseite des Projekts auch als Ausgangsbasis für eigene Ideen zur Verfügung. Allerdings ist der Code dort in Java-Sytax zu finden. Er müsste also für den Kontext "Python mit Processing" angepasst werden.
