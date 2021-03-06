## Der Datentyp *list*

Dem Datentyp *list* soll an dieser Stelle besondere Aufmerksamkeit geschenkt werden, da er für die Arbeit mit Processing und Python viele interessante Möglichkeiten eröffnet. In anderen Programmiersprachen erfüllt der Datentyp *array* ähnliche Zwecke.

Für Listen lassen sich folgende Eigenschaften angeben:

* Eine Liste kann leer sein, beliebig viele gleiche oder unterschiedliche Objekte enthalten (z.B. Strings, Booleans, Numbers)
* Man kann Listen auch als *Gruppen* denken. 
* Die Elemente in Listen sind von links nach rechts geordnet, sodass die Elemente durch Angabe ihrer Position angesprochen werden können.
* Listen sind beliebig verschachtelbar. Das heißt, dass Listen wiederum Listen als Elemente enthalten können.
*  Listen können zur Laufzeit des Programms wachsen, schrumpfen.

### Beispiel: Lottozahlen

```python
lottozahlen = [3, 5, 8, 13, 22, 31]
```

Hier wird unter dem Namen `lottozahlen` eine Liste von Ganzzahlen gespeichert. Es ist ratsam, den Namen der Variablen, die die Liste speichert, im Plural zu wählen. So sieht man ihr im ganzen Programm an, dass sie mehrere Werte speichert oder speichern soll.

Python stellt eine praktische Funktion zur Verfügung, mit der sich der Datentyp einer Variablen ermitteln lässt: `type()`. In der Processing-IDE können wir sie folgendermaßen einsetzen:

```python
lottozahlen = [3, 5, 8, 13, 22, 31]
print(type(lottozahlen)) # Ausgabe: <type 'list'>
```

So lässt sich der Typ eines jeden Objekts feststellen.

Auf die einzelnen *Elemente* der Liste kann mit dem *Index-Operator* zugegriffen werden:

```python
lottozahlen = [3, 5, 8, 13, 22, 31]
text(lottozahlen[0], width/2, height/2)
```

Die Leinwand sollte in der Mitte eine "3" zeigen, und das Prinzip des Index-Operators wird deutlich:

<div class="box">
Die Zählung der Elemente in einer Liste beginnt bei 0. Die Position in einer Liste wird in der englischen Literatur auch als <em>offset</em> bezeichnet.
</div>

Der Index-Operator eignet sich nicht nur zum Auslesen von Werten, sondern auch zum Ändern von Elementen in der Liste:

```python
lottozahlen = [3, 5, 8, 13, 22, 31]

# Ändern des Elements an fünfter(!) Stelle
lottozahlen[4] = 99

print(lottozahlen) #  Ausgabe: [3, 5, 8, 13, 99, 31]
```

In der Liste `lottozahlen` befinden sich folglich sechs Elemente, deren Positionen in der Liste mit *0, 1, 2, 3, 4 und 5* angegeben werden können.

Wollen wir Python herausfinden lassen, wieviele Elemente sich in einer Liste befinden, können wir die Funktion `len()` verwenden:

```python
lottozahlen = [3, 5, 8, 13, 22, 31]
print(len(lottozahlen)) # Ausgabe: 6
```

Listen in Python sind ganz wesentlich für die Bewältigung alltäglicher Programmierprobleme. Daher sind sie an anderer Stelle (s. [
Literaturverzeichnis](../Anhang/99-literatur.html)) ausführlich dokumentiert. In diesem Skript widmet sich das Kapitel [
Listen und Schleifen](../Themen/listen_und_schleifen.html) den Möglichkeiten von Listen im Zusammenhang mit Processing.

### Lernvideos zum Thema *Listen*

Diese und weitere Möglichkeiten zur Arbeit mit Listen werden in der Screencastreihe von [openscreencast](https://www.youtube.com/channel/UC_oJHQiMx9dNkbt2Wz9nicQ) erklärt:


{% youtube %}https://youtu.be/Z-folPNH6ro?list=PLD20BEE125C1FC7B1{% endyoutube %}

_**Video**: "[Python-Programmierung - Listen](https://youtu.be/Z-folPNH6ro?list=PLD20BEE125C1FC7B1)
" von [openscreencast](https://www.youtube.com/channel/UC_oJHQiMx9dNkbt2Wz9nicQ) [CC-BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/)_

{% youtube %}https://youtu.be/CSkrKxMOv10?list=PLD20BEE125C1FC7B1{% endyoutube %}

_**Video**: "[Python-Programmierung - Listen (Teil 2)](https://youtu.be/CSkrKxMOv10?list=PLD20BEE125C1FC7B1)
" von [openscreencast](https://www.youtube.com/channel/UC_oJHQiMx9dNkbt2Wz9nicQ) [CC-BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/)_

{% youtube %}https://youtu.be/Ou9EgFglk5k?list=PLD20BEE125C1FC7B1{% endyoutube %}

_**Video**: "[Python-Programmierung - weitere Listen-Methoden ](https://youtu.be/Ou9EgFglk5k?list=PLD20BEE125C1FC7B1)
" von [openscreencast](https://www.youtube.com/channel/UC_oJHQiMx9dNkbt2Wz9nicQ) [CC-BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/)_

{% youtube %}https://youtu.be/vw3-jMTAaHQ?list=PLD20BEE125C1FC7B1{% endyoutube %}

_**Video**: "[Python-Programmierung - Listen-Index](https://youtu.be/vw3-jMTAaHQ?list=PLD20BEE125C1FC7B1)
" von [openscreencast](https://www.youtube.com/channel/UC_oJHQiMx9dNkbt2Wz9nicQ) [CC-BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/)_

Im Channel von *openscreencast* folgen noch weitere Videos zum Thema, die ebenfalls sehenswert sind. Es wird darin das Thema *Slicing* behandelt.

### Lernvorschläge

*  Das Kapitel bei Lutz (2013, S. 239 ff.) ist sehr empfehlenswert, um alle weiteren Eigenschaften und Möglichkeiten von Listen genauer zu studieren. Die [Python-Referenz](https://docs.python.org/2.7/library/stdtypes.html#sequence-types-str-unicode-list-tuple-bytearray-buffer-xrange) führt auch ins Thema Listen ein.