# API (Application Programming Interface) der Arduino-Klasse

* ***list()*** - `print(Arduino.list())` gibt eine Liste aller seriellen Geräte aus. Wenn das Board korrekt am Rechner angeschlossen ist, steht der zugehörige serielle Anschluss in der Liste und kann an den Konstruktor übergeben werden.
* ***pinMode(pin, mode)*** - legt den Modus eines Pins fest. Möglich sind INPUT, OUTPUT und SERVO
* ***digitalRead(pin)*** - Sofern der Pin als INPUT gesetzt ist, liefert die Methode `Arduino.HIGH` oder `Arduino.LOW` bzw. `1` und `0` zurück.
* ***digitalWrite(pin, value)*** - schreibt Arduino.HIGH oder Arduino.LOW auf einen digitalen Pin. Pin 13 ist ein digitaler. HIGH bedeutet, dass 5 V an diesem Pin anliegen, LOW steht für 0 V.
* ***analogRead(pin)*** - liefert den Wert eines analogen Eingangs im Wertebereich von `0` bis `1023` zurück (10 Bit).
* ***analogWrite(pin, value)*** - schreibt einen analogen Wert im Bereich `0` bis `255` auf einen digitalen Pin, der dies unterstützt. Die entsprechenden Pins sind beim Arduino Uno die 3, 5, 6, 9, 10 und 11. Sie sind auf dem Board auch mit einer `~` gekennzeichnet.
* ***servoWrite(pin, value)*** - schreibt einen analogen Wert im Bereich `0` bis `180` auf einen digitalen Pin, an den ein Servo-Motor angeschlossen ist. Die Pins, die hierzu verwendet werden können, sind ebenfalls die 3, 5, 6, 9, 10 und 11.