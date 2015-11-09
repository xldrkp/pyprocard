## Funktionen

<!--{% youtube %}https://youtu.be/Uzb_ajpcMUo?list=PLD20BEE125C1FC7B1{% endyoutube %}-->

Funktionen machen es möglich, bestimmte Aktionen mit Daten auszuführen. Dieses Konzept ist nicht nur ein Merkmal von Python, auch in anderen Sprachen sind Funktionen zu finden.

### Eingebaute Funktionen

In den vorherigen Kapiteln sind schon einige Funktionen verwendet worden, die in Python eingebaut sind oder die von Processing für Python zur Verfügung gestellt werden.

```python
# Beispiele für Processing-Funktionen, die mit Python verwendet werden können.

size(200, 300) # Funktion für die Definition der Leinwandgröße
print(x) # Funktion zur Ausgabe von Daten auf der Konsole
```

Weitere Funktionen sind auf der Referenzseite von [Processing ](http://py.processing.org/reference) einzusehen.

Häufig ist es so, dass die Funktionen einer Programmiersprache zwar eine Reihe von Standardaufgaben abdecken, komplexere Programme aber individuelle Lösungen und damit auch neue, individuelle Funktionen benötigen. Daher ist es auch in Python möglich, eigene Funktionen zu definieren und ihnen das gewünschte Verhalten "einzubauen".


### Eigene Funktionen definieren

Die Definition von Funktionen in Python ist denkbar einfach. Genaugenommen haben wir das bisher schon oft getan:

```python
def setup():
    fullScreen()
    ellipseMode(CENTER)

def draw():
    ellipse(mouseX, mouseY, 50, 50)
```

Hierbei handelt es sich um zwei Funktionen, die, wenn sie vorhanden sind, beim Start eines Programms ausgeführt werden. Alle anderen Funktionen, die wir im defininieren, müssen ausdrücklich aufgerufen werden.

Mit dem Schlüsselwort `def` wird die *Definition* einer Funktion eingeleitet. Zusammen mit dem *Namen* der Funktion und möglichen Parametern (s.u.) bildet diese erste Zeile die *Funktionssignatur*. 

Eingerückt folgt dann der Code, der beim Aufruf der Funktion ausgeführt werden soll. Das können beliebig viele Zeilen sein. Eine goldene Regel lautet:

**Eine Funktion sollte genau eine Aufgabe erledigen.**

Da es möglich ist, beliebig viele Funktionen zu definieren, wächst die Anzahl der Funktionen in einem Programm, wenn dieses komplexer wird. Der Name der Funktion ist frei wählbar, solange er den Regeln des PEP 0008 folgt. Neben den syntaktischen Anforderungen ist eine Sache sicherlich am meisten hervorzuheben: Der Name der Funktion sollte aussagen, was die Aufgabe der Funktion ist.

