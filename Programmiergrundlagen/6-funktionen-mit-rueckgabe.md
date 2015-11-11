## Funktionen mit Rückgabewert

Funktionen können auch das Ergebnis ihrer Arbeit zurückgeben. Ein Beispiel:

```python
def setup():
    size(100, 200)

def draw():
    if check_mouse_position():
        print("Getroffen!")
    else:
        print("")

def check_mouse_position():
    if mouseX > 50:
        return True
    else:
        return False
```

Die Funktion `check_mouse_position()` fungiert als Helferin. Sie prüft, ob eine Bedingung erfüllt ist oder nicht. Entsprechend liefert sie einen Wahrheitswert zurück. In der `draw()` wird davon Gebrauch gemacht: Sofern `check_mouse_position()` den Wahrheitswert `True` zurückliefert, wird "Getroffen!" auf der Konsole ausgegeben. 

Zugegeben, die Funktion ist nicht sonderlich hilfreich in diesem Moment. Man hätte auch direkt die Überprüfung der Mausposition in der `draw()` auswerten können. Aber da Programme in der Regel wachsen und langsam komplexer werden, ist es klug, von vornherein eine Funktion vorzubereiten, deren Inhalt mitwachsen kann.

### Funktionen mit Parameterübergabe und Rückgabewert

Selbstverständlich können Funktionen auch einen Wert zurückgeben, der aus übergebenen Parametern resultiert. Dieser Fall kommt häufig vor. Ein Beispiel:

```python
def berechne_bildpunkte(w, h):
    return w * h

result = berechne_bildpunkte(300, 300)
print(result)
```

Die Funktion nimmt zwei Parameter an, deren Produkt gebildet wird. Das Ergebnis wird zurückgegeben. Dort, wo die Funktion aufgerufen wurde, kommt nun dieses Ergebnis an und wird der Variablen `result` zugewiesen. Im weiteren Verlauf des Programms kann `result` dann verwendet werden.
