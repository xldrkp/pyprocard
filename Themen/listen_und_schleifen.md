## Listen und Schleifen

Der Datentyp *list* wird im Kapitel [Datentypen](../Programmiergrundlagen/2-datentypen.html) schon vorgestellt. Im folgenden Abschnitt sollen die Möglichkeiten von Listen für Processing behandelt werden.

### Beispiel: Farbthema - Werte einer Liste auslesen

Inspiriert vom Farbentool [Adobe Color CC](https://color.adobe.com/de/create/color-wheel/) wollen wir analog ein Farbthema mit Processing visualisieren.


```python
# Farbthema "Backstein" von claudia
# https://color.adobe.com/de/Backstein-color-theme-7211262/?showPublished=true

def setup():
    size(500, 350)
    noStroke()
    # Die hexadezimalen Farbwerte von "Backstein"
    # als Strings in einer Liste.
    # Siehe hierzu das Beispiel in der IDE
    # "Python Mode Differences -> LiteralColors"
    farben = ["#B01E1F", 
            "#E82407", 
            "#FF5214", 
            "#E86007", 
            "#FFAA4A"]
    
    anzahl_farben = len(farben)
    
    # x-Koordinate für farbige Rechtecke
    rect_pos_x = 0
    
    # Die Breite und damit die gleichmäßige Verteilung
    # der Rechtecke wird aus der Breite der Leinwand
    # und der Anzahl der Farben errechnet.
    breite = width / anzahl_farben
    
    # Mit einer Schleife iterieren wir über die Liste.
    # Bei jedem Durchlauf enthält farbe einen anderen
    # Wert aus der Liste.
    for farbe in farben:
        # Füllfarbe ändern
        fill(farbe)
        # Rechteck zeichnen
        rect(rect_pos_x, 0, breite, height)
        # Position fürs nächste Rechteck errechnen
        rect_pos_x += breite
```

Das Ergebnis ähnelt start der Ansicht aus dem [Browsertool](https://color.adobe.com/de/Backstein-color-theme-7211262/?showPublished=true)
.

![Farbthema "Backstein"](../images/backstein.png)

### Beispiel: Eine Liste mit zufälligen Werten füllen

In der Datenverarbeitung muss man häufig eine Reihe von Werten zwischenspeichern, um später mit ihnen weiterzuarbeiten. Wir konstruieren einen solchen Fall mit der Auslosung der Lottozahlen:

```python
def setup():

    # Leere Liste erzeugen
    lottozahlen = []
    
    # 6 Zufallszahlen ...
    for i in range(6):
        
        # ... aus 49 erzeugen
        zufallszahl = random(0,49)
        aufgerundet = ceil(zufallszahl)
        
        # Bei jedem Durchlauf die neue Zahl
        # an die Liste dranhängen (append)
        lottozahlen.append(aufgerundet)
    
    # Am Ende die Liste sortieren    
    lottozahlen.sort()
    print(lottozahlen)
```

Neu sind hier zwei *Methoden* des Listenobjekts `lottozahlen`. `append()` und `sort()` sind **Methoden der Klasse *list*** und werden daher mit dem *Punktoperator* direkt mit dem Objekt verbunden. Weitere Details zu diesem Konzept finden sich im Kapitel [Objektorientierte Programmierung](../Programmiergrundlagen/10-oop.html). Die Referenz von
[Processing.py](http://py.processing.org/reference/)
erklärt weitere Methoden des Listenobjekts und sollte in diesem Zusammenhang studiert werden.

### Lernvorschläge

* Wandele das Programm "Farbthema" so ab, dass es durch Tasten- oder Mausinteraktion immer neue, zufällige Farbthemen erzeugt.

