# Hello World! Again.

Nachdem wir mit der Arduino-IDE "Hello World!" geblinkt haben, wollen wir einen ähnlich einfachen Versuch aufbauen: Wir schreiben einen Processing-Sketch, der eine LED blinken lässt - mit Python!

Damit wir mit Processing das Arduino-Board steuern können, müssen wir einige vorbereitende Schritte erledigen:

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

![](../images/missing-arduino-lib.png)

Es fehlt eine Bibliothek, die die Kommunikation mit der StandardFirmata auf dem Board ermöglicht. Wir installieren sie also nach (vgl. [Bibliotheken verwenden](../Themen/bibliotheken-verwenden.md)
). Die Bibliothek *serial* ist standardmäßig installiert. Sie dient der allgemeinen seriellen Kommunikation, worauf später noch genauer eingegangen werden soll.

## Instanziierung des Arduino-Objekts

```python
add_library('serial')
add_library('arduino')

def setup():
    a = Arduino(this, '/dev/ttyACM1', 57600)
    
def draw():
    pass
```

Die Arduino-Bibliothek bringt eine Klasse *Arduino* mit, von der wir hier ein Objekt erzeugen. Der Konstruktor empfängt den Kontext des aktuellen Programms sowie den Namen der seriellen Schnittstelle, an der das Arduino-Board angeschlossen ist. Als dritten Parameter übergeben wir die Baud-Rate. Diese **muss** für die Kommunikation mit der StandardFirmata 57600 betragen! Mehr zur Baud-Rate später, wenn wir uns genauer mit serieller Kommunikation beschäftigen.

Die Ausführung des aktuellen Programms bewirkt nicht viel: Es sollte sich die Processing-Leinwand öffnen, und auf dem Board flackern kurz die LEDs *TX* und *RX*. Sie zeigen an, dass eine serielle Übertragung stattfindet. *RX* steht für empfangen (receive), *TX* für senden (transmit).

## Lampe an!

Nun wollen wir den Code schreiben, der unsere LED auf Pin 13 einschaltet!

```python
add_library('serial')
add_library('arduino')

# Auch hier wird die On-Board-LED auf Pin 13 verwendet
led = 13

def setup():
    # Erzeugung eines Arduino-Objekts
    a = Arduino(this, '/dev/ttyACM1', 57600)
    # Pin 13 wird als Ausgang definiert
    a.pinMode(led, Arduino.OUTPUT)
    # Die LED wird angeschaltet
    a.digitalWrite(led, Arduino.HIGH)
    
def draw():
    pass
```

Die Ausführung mit *STRG+R* oder Klick auf die Playtaste bringt wieder *RX* und *TX* zum Flackern. Aber auch die LED flackert einige Male. Das gehört zum Initialisierungsvorgang der Kommunikation dazu. Daran anschließend sollte sie allerdings kontinuierlich leuchten, *RX* und *TX* flackern weiter. Das liegt daran, dass die Steuersignale für die LED immer wieder neu aus dem Processing-Sketch über das USB-Kabel geschickt werden.

Im Code ist zu sehen, dass die Arduino-Klasse aus der Bibliothek einige Methoden mitbringt. Die vollständige Referenz der Schnittstelle zeigt, dass es nicht viele sind. Ihr Potenzial ist allerdings groß.