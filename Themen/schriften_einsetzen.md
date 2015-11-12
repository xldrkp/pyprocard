## Schriften einsetzen

Processing wurde als Entwicklungsumgebung besonders für den Einsatz in der Kunst geschaffen. Daher sollen in diesem Abschnitt die Möglichkeiten für die Arbeit mit Typographie ausgelotet werden.

### Mit Typographie spielen

Ein erstes Beispiel soll zeigen, wie man Typographie in eigenen Programmen einsetzen kann:

```python
letter = "A"

def setup():
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
```
***Listing:*** *Zeichnen mit Buchstaben. Das Beispiel ist dem großartigen Buch "Generative Gestaltung" entnommen[^1].*

### Unterschiede zwischen `loadFont()` und `createFont()`

---

[^1]: Bohnacker, H., Gross, B., Laub, J., & Lazzeroni, C. (2009). Generative Gestaltung: entwerfen, programmieren, visualisieren. Mainz: Schmidt., S. 258
