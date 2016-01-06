# Firmata

Der einfachste Zugang zur Programmierung des Arduino mit Python erfolgt mithilfe der so genannten StandardFirmata. Dabei handelt es sich um eine spezielle Version der [Firmata](https://github.com/firmata/protocol)
für Arduino-Boards. Wir setzen sie ein, um von Processing aus unser Arduino-Board steuern zu können - mit Python! Dabei ist eine Sache für das Verständnis des komplexen Aufbaus am Wichtigsten: 

Die StandardFirmate wird **einmalig** auf das Arduino-Board geladen. Anschließend erfolgt die Programmierung in der Processing-IDE nur noch in Python!

Das folgende Schaubild zeigt diesen Sachverhalt.

![](../images/workflow.png)

**Abbildung**: Grundsätzliche Arbeitsweise mit der StandardFirmata

Schreiten wir zu Tat und stellen die notwendigen Bedingungen für die Weiterarbeit her!

## Hello World! Again.



## API (Application Programming Interface) der Arduino-Klasse

* ***list()*** - `print(Arduino.list())` gibt eine Liste aller seriellen Geräte aus. Wenn das Board korrekt am Rechner angeschlossen ist, steht der zugehörige serielle Anschluss in der Liste und kann an den Konstruktor übergeben werden.
* ***pinMode(pin, mode)*** - legt den Modus eines Pins fest. Möglich sind INPUT, OUTPUT und SERVO
* ***digitalRead(pin)*** - Sofern der Pin als INPUT gesetzt ist, liefert die Methode `Arduino.HIGH` oder `Arduino.LOW` bzw. `1` und `0` zurück.
* ***digitalWrite(pin, value)*** - schreibt Arduino.HIGH oder Arduino.LOW auf einen digitalen Pin. Pin 13 ist ein digitaler. HIGH bedeutet, dass 5 V an diesem Pin anliegen, LOW steht für 0 V.
* ***analogRead(pin)*** - liefert den Wert eines analogen Eingangs im Wertebereich von `0` bis `1023` zurück (10 Bit).
* ***analogWrite(pin, value)*** - schreibt einen analogen Wert im Bereich `0` bis `255` auf einen digitalen Pin, der dies unterstützt. Die entsprechenden Pins sind beim Arduino Uno die 3, 5, 6, 9, 10 und 11. Sie sind auf dem Board auch mit einer `~` gekennzeichnet.
* ***servoWrite(pin, value)*** - schreibt einen analogen Wert im Bereich `0` bis `180` auf einen digitalen Pin, an den ein Servo-Motor angeschlossen ist. Die Pins, die hierzu verwendet werden können, sind ebenfalls die 3, 5, 6, 9, 10 und 11.