## Funktionen mit Parametern

Beim Aufruf von Funktionen kann wahlweise eine Liste von *Parametern* übergeben werden. Hierbei handelt es sich um Werte beliebigen Datentyps, die beim Aufruf mit Kommata getrennt in die Klammern geschrieben werden:

```python
# Funktionsaufruf
zeichne_kreuz(50, 60)
```

Hier wird eine Funktion mit Namen `zeichne_kreuz()` aufgerufen, der zwei Parameter vom Typ `integer` übergeben werden. In der Funktionsdefinition von `zeichne_kreuz()` wird festgelegt, wie diese Werte verarbeitet werden:

```python
def zeichne_kreuz(x, y):
    line(x-20, y, x+20, y)
    line(x, y-20, x, y+20)    
```

Die übergebenen Parameter werden in den lokalen Variablen `x` und `y` gespeichert.

Für die Arbeit mit Processing sind Funktionen dieser Art sehr hilfreich, da sie die Berechnung der Position von Objekten *relativ zu den Parametern* durchführen.