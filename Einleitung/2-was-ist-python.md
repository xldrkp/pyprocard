## Was ist Python?

[Python](https://de.wikipedia.org/wiki/Python_%28Programmiersprache%29) ist eine universelle Programmiersprache, mit der sich Probleme und Aufgaben aus unterschiedlichsten Bereichen lösen lassen. Python setzt den Schwerpunkt auf Lesbarkeit und Einfachheit und verzichtet weitestgehend auf Klammern und das obligatorische Semikolon am Ende einer Zeile. Stattdessen ist penibel auf die korrekte Einrückung von Codezeilen und -blöcken zu achten. Ein Vergleich der Java-Syntax aus dem vorgegangenen Kapitel mit der Schreibweise in Python soll den Unterschied zeigen:

Das Beispiel in Java-Syntax:

```java
void draw() {
  ellipse(mouseX, mouseY, 20, 20);
}
```

In Processing bzw. Java ist die Einrückung in Zeile 2 optional. Das Semikolon darf nicht fehlen, damit der [Compiler](https://de.wikipedia.org/wiki/Compiler), der das Processing-Programm übersetzt, weiß, wo eine Zeile zuende ist.

In Python müssen Zeilen, die zu einem Block gehören, zwingend eingerückt werden, damit der [Interpreter](https://de.wikipedia.org/wiki/Interpreter) die Struktur des Programms korrekt erfassen kann.

```python
def draw():
  ellipse(mouseX, mouseY, 20, 20)
```

Die Erfahrung aus der Lehre zeigt, dass dieser Zwang zur übersichtlichen Formatierung das Verständnis fördert. Einrückungen sollten konsequent mit der Tabulatortaste vorgenommen werden, eine Mischung mit Leerzeichen kann zu Problemen führen. Das Semikolon am Ende der Zeile ist in Python nicht vorgesehen und führt zu Fehlern bei der Ausführung des Programms. Ein weiteres Beispiel sowie weitergehende Ausführung zur Syntax von Python finden sich [in der Wikpedia](https://de.wikipedia.org/wiki/Python_%28Programmiersprache%29#Syntax).

Der Zugang zu Python ist ebenfalls sehr einfach, da sich auch hier schon mit wenigen Zeilen Code erste Ergebnisse erzielen lassen. Allerdings fällt das visuelle Feedback hier eher spärlich aus, denn die ersten Schritte mit Python machen die meisten Lehrbücher auf der Kommandozeile.

![Addition zweier Zahlen mit Python. Ein- und Ausgabe erfolgen auf der Kommandozeile.](images/commandline.png)

Dieser Ansatz, ins Programmieren von Computern einzusteigen, ruft in der Regel nicht bei allen Beteiligten Begeisterung hervor.

Nun bietet auch Python einen eigenen Zugang zur Erstellung von Programmen, die eher graphisch orientiert sind. Zu nennen wären hier [Pygame](http://www.pygame.org/hifi.html) oder auch [Turtle](http://pythonturtle.org/). Aber auch hierbei sind schon einige Zeilen Code zu schreiben, bis sich erste Erfolgserlebnisse einstellen, und die begrenzte Erweiterungsmöglichkeit setzt der Phantasie schnell Grenzen.

Das Potenzial von Processing gepaart mit Python ermöglichen einen Einstieg in die Programmierung, der viele Türen öffnet und eine flache Lernkurve verspricht.
