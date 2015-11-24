## Mehr Eigenschaften

Nachdem wir die grundlegenden Konzepte von Klassen hergeleitet haben, wollen wir dem Smiley nun mehr Gestalt geben. Dafür erweitern wir zunächst die Klassendefinition.

```python
class Smiley:    
    
    def say_something(self, something):
        print(something)
        
    def paint(self, x_pos, y_pos, size_xy):
        """ Malt einen Smiley auf Basis der übergebenen
        Argumente. Positionen von Augen und Mund werden
        aus den Parametern errechnet.
        """ 
        ellipseMode(CENTER)
        # Körper
        ellipse(x_pos, y_pos, size_xy, size_xy)
        # Auge links
        ellipse(x_pos - size_xy * .2, y_pos - size_xy * .12, size_xy * .2, size_xy * .2)
        # Auge rechts
        ellipse(x_pos + size_xy * .2, y_pos - size_xy * .12, size_xy * .2, size_xy * .2)
```

