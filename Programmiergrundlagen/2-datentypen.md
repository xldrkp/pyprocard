## Datentypen

Der Sinn und Zweck, Programme für einen Computer zu schreiben, liegt in der Datenverarbeitung, die dieser viel besser und schneller erledigen kann als der Mensch. Das Prinzip, das dahinter steckt, kennzeichnet das Verhältnis von Mensch und Maschine. Es nennt sich *EVA-Prinzip*:

**E** Eingabe  
**V** Verarbeitung  
**A** Ausgabe

Der Mensch gibt Daten in die Maschine ein, diese verarbeitet sie und gibt sie am Ende der Verarbeitung als Ergebnis aus.

Daten, die in einem Programm verarbeitet werden sollen, können unterschiedlicher Natur sein: Zahlen, Zeichenketten, Listen von Daten etc. In fast jeder Programmiersprache wird diese Vielfalt in *Datentypen* abgebildet. In Python ist das nicht anders. **Alles in Python ist ein Objekt**, was die Arbeit mit Daten am Ende sehr einfach verständlich macht. Mehr dazu in einem späteren Kapitel.

Für den Anfang sind zunächst die folgenden Datentypen aus Python relevant:

**Numbers** `1234, 3.1415`

**Strings** `'Hund'`

**Booleans** `True, False`

**Lists** `[1, 'drei', 4.5]`

Der Datentyp *Numbers* meint Zahlen allgemein. Die beiden wichtigsten Zahlentypen, die zu Beginn vorkommen, sind Ganzzahlen *(integer)* wie `1234` und Gleitkommazahlen *(float)* wie `3.1415`.

Zeichenketten heißen auf Englisch *Strings*. Sie werden mit einem einfachen oder doppelten Anführungszeichen eingeschlossen und können beliebige Zeichen enthalten.

Die Booleschen Werte *True* und *False* werden auch *Wahrheitswerte* genannt und fungieren oft als Schalter: An (`True`) und Aus (`False`).

*Listen* stellen einen Sammeldatentyp dar. In einer Liste können Werte ganz unterschiedlichen Typs enthalten sein. Kennzeichnend für eine Liste sind die eckigen Klammern, Elemente der Liste werden mit Kommata getrennt.

Python kennt noch eine Zahl weiterer Datentypen, die aber für den Einstieg mit Processing zunächst nicht relevant sind. Weiterführende Informationen finden sich in der [Python-Referenz](https://docs.python.org/2.7/library/stdtypes.html).

### Der Datentyp *list*

Dem Datentyp *list* soll an dieser Stelle besondere Aufmerksamkeit geschenkt werden, da er für die Arbeit mit Processing viele interessante Möglichkeiten eröffnet. In anderen Programmiersprachen erfüllt der Datentyp *array* ähnliche Zwecke.

Für Listen lassen sich folgende Eigenschaften angeben:

* Eine Liste kann leer sein, beliebig viele gleiche oder unterschiedliche Objekte enthalten (z.B. Strings, Booleans, Numbers)
* Man kann Listen auch als *Gruppen* denken. 
* Die Elemente in Listen sind von links nach rechts geordnet, sodass die Elemente durch Angabe ihrer Position angesprochen werden können.
* Listen sind beliebig verschachtelbar. Das heißt, dass Listen wiederum Listen als Elemente enthalten können.
*  Listen können zur Laufzeit des Programms wachsen, schrumpfen.

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
Die Zählung der Elemente in einer Liste beginnt bei 0. Die Position in einer Liste wird in der englischen Literatur auch als *offset* bezeichnet.
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

### Lernvideos zum Thema

Diese und weitere Möglichkeiten zur Arbeit mit Listen werden in der Screencastreihe von [openscreencast](https://www.youtube.com/channel/UC_oJHQiMx9dNkbt2Wz9nicQ) erklärt:


{% youtube %}https://youtu.be/Z-folPNH6ro?list=PLD20BEE125C1FC7B1{% endyoutube %}

_**Video**: "[Python-Programmierung - Listen](https://youtu.be/Z-folPNH6ro?list=PLD20BEE125C1FC7B1)
" von [openscreencast](https://www.youtube.com/channel/UC_oJHQiMx9dNkbt2Wz9nicQ) [CC-BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/)_

{% youtube %}https://youtu.be/CSkrKxMOv10?list=PLD20BEE125C1FC7B1{% endyoutube %}

_**Video**: "[Python-Programmierung - Listen (Teil 2)](https://youtu.be/CSkrKxMOv10?list=PLD20BEE125C1FC7B1)
" von [openscreencast](https://www.youtube.com/channel/UC_oJHQiMx9dNkbt2Wz9nicQ) [CC-BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/)_

{% youtube %}https://youtu.be/Z-folPNH6ro?list=PLD20BEE125C1FC7B1{% endyoutube %}

_**Video**: "[Python-Programmierung - weitere Listen-Methoden ](https://youtu.be/Ou9EgFglk5k?list=PLD20BEE125C1FC7B1)
" von [openscreencast](https://www.youtube.com/channel/UC_oJHQiMx9dNkbt2Wz9nicQ) [CC-BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/)_
### Lernvorschläge

{% youtube %}https://youtu.be/vw3-jMTAaHQ?list=PLD20BEE125C1FC7B1{% endyoutube %}

_**Video**: "[Python-Programmierung - Listen-Index](https://youtu.be/vw3-jMTAaHQ?list=PLD20BEE125C1FC7B1)
" von [openscreencast](https://www.youtube.com/channel/UC_oJHQiMx9dNkbt2Wz9nicQ) [CC-BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/)_

Im Channel von *openscreencast* folgen noch weitere Videos zum Thema, die ebenfalls sehenswert sind. Es wird darin das Thema *Slicing* behandelt.

### Lernvorschläge


*  Das Kapitel bei Lutz (2013, S. 239 ff.) ist sehr empfehlenswert, um alle weiteren Eigenschaften und Möglichkeiten von Listen genauer zu studieren. Die [Python-Referenz](https://docs.python.org/2.7/library/stdtypes.html#sequence-types-str-unicode-list-tuple-bytearray-buffer-xrange) führt auch ins Thema Listen ein.