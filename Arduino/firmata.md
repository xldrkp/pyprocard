# Firmata

Der einfachste Zugang zur Programmierung des Arduino mit Python erfolgt mithilfe der so genannten StandardFirmata. Dabei handelt es sich um eine spezielle Version der [Firmata](https://github.com/firmata/protocol)
für Arduino-Boards. Wir setzen sie ein, um von Processing aus unser Arduino-Board steuern zu können - mit Python! Dabei ist eine Sache für das Verständnis des komplexen Aufbaus am Wichtigsten: 

Die StandardFirmate wird **einmalig** auf das Arduino-Board geladen. Anschließend erfolgt die Programmierung in der Processing-IDE nur noch in Python!

Das folgende Schaubild zeigt diesen Sachverhalt.

![](../iimages/workflow.png)

**Abbildung**: Grundsätzliche Arbeitsweise mit der StandardFirmata

Schreiten wir zu Tat und stellen die notwendigen Bedingungen für die Weiterarbeit her!

## Hello World! Again.

Nachdem wir mit der Arduino-IDE "Hello World!" geblinkt haben, wollen wir einen ähnlich einfachen Versuch aufbauen: Wir schreiben einen Processing-Sketch, der eine LED blinken lässt!

### Vorbereitung

Damit wir mit Processing das Arduino-Board steuern können, müssen wir einige vorbereitende Schritte erledigen:

### Mit der Arduino-IDE

1. Installation der StandardFirmata auf dem Arduino Uno.

### Mit der Processing-IDE

1. Installation und Import der Bibliothek *Arduino (Firmata)*.
2. Import der Bibliothek *serial*
3. Erstellung einer Klasse *LED* und des Hauptprogramms

## Installation der StandardFirmata

Dieser Schritt ist denkbar einfach zu erledigen, da die StandardFirmata wie jeder andere Arduino-Sketch auf das Board geladen wird. Zunächst muss die StandardFirmata in der Arduino-IDE aus den Beispielen geöffnet werden (Menü Datei -> Beispiele -> Firmata -> StandardFirmata).

Mit dem Upload-Pfeil unter der Menüleiste der Arduino-IDE wird anschließend das Programm kompiliert und auf den Microcontroller hochgeladen. Geht alles korrekt vonstatten, steht folglich eine Softwareschnittstelle auf dem Arduino zur Verfügung, die sich aus Processing heraus ansprechen lässt.

Falls die On-Board-LED infolge des vorangegangenen Beispiels noch geblinkt haben sollte, hat sie nach diesem Vorgang damit aufgehört, da die StandardFirmata das Blink-Programm überschrieben hat. Dass die StandardFirmata nun in einer Endlosschleife auf dem Arduino läuft, ist von außen nicht zu erkennen.

## Installation und Import der Bibliothek *Arduino (Firmata)*

In der Processing-IDE erstellen wir nun ein erstes Programm:

```python
add_library('serial')
add_library('arduino')

def setup():
    pass
    
def draw():
    pass

```

Lassen wir es laufen, könnte es sich mit einem Fehler melden: 