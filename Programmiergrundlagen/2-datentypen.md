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

Dem Datentyp *list* soll an dieser Stelle besondere Aufmerksamkeit geschenkt werden, da er für die Arbeit mit Processing viele interessante Möglichkeiten eröffnet.

Eine Liste in Python kann leer sein oder beliebig viele Objekte beinhalten.

```python
lottozahlen = [3, 5, 8, 13, 22, 31]
```

Hier wird unter dem Namen `lottozahlen` eine Reihe von Ganzzahlen gespeichert. Es ist ratsam, den Namen der Variablen, die die Liste speichert, im Plural zu wählen. So sieht man ihr im ganzen Programm an, dass sie mehrere Werte speichert oder speichern soll.

Python stellt eine praktische Funktion zur Verfügung, mit der sich der Datentyp einer Variablen ermitteln lässt: `type()`. In der Processing-IDE können wir sie folgendermaßen einsetzen:

```python
lottozahlen = [3, 5, 8, 13, 22, 31]
print(type(lottozahlen)) # Ausgabe: <type 'list'>
```

Auf die einzelnen *Elemente* der Liste kann mit dem Index-Operator zugegriffen werden:

```python
lottozahlen = [3, 5, 8, 13, 22, 31]
text(lottozahlen[0], width/2, height/2)
```

Die Leinwand sollte in der Mitte eine "3" zeigen, und das Prinzip des Index-Operators wird deutlich:

<div class="box">
Die Zählung der Elemente in einer Liste beginnt bei 0.
</div>

In der Liste `lottozahlen` befinden sich folglich sechs Elemente, deren Positionen in der Liste mit *0, 1, 2, 3, 4 und 5* angegeben werden können.

Wollen wir Python herausfinden lassen, wieviele Elemente sich in einer Liste befinden, können wir die Funktion `len()` verwenden:

```python
lottozahlen = [3, 5, 8, 13, 22, 31]
print(len(lottozahlen)) # Ausgabe: 6
```



```python
size(150, 150)
lottozahlen = [3, 5, 8, 13, 22, 31]
text("Es sind " + str(len(lottozahlen)) + " Lose im Hut.", 10, height/2)
```

Der Ausdruck in Zeile 3 gibt einen String als Text auf der Leinwand aus. Dieser wird aus festen und variablen Bestandteilen zusammengesetzt. Der Ausdruck `str(len(lottozahlen))` wird von innen nach außen abgearbeitet: Zunächst wird mit `len(lottozahlen)` die *Anzahl* der Elemente in der Liste ermittelt, anschließend wird mit `str()` der Datentyp von *int* zu *str* konvertiert, also umgewandelt. Wenn wir den Datentyp des Rückgabewerts (vgl. Kapitel Funktionen mit Rückgabewert) ermitteln, 

```python
print(type(len(lottozahlen))) # Ausgabe: <type 'int'>
```

stellen wir fest, dass es sich um eine Ganzzahl handelt. Ein Test 
