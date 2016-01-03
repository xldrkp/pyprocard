# Die Arduino-IDE

Arduino Uno und verwandte Boards sind im Netz bestens dokumentiert, sodass an dieser Stelle nur eine kurze Einführung erfolgt. Es wird davon ausgegangen, dass die Arduino-IDE auf dem eigenen Rechner installiert wurde.

Wie auf der Homepage des Projekts erklärt, wird der Arduino durch ein USB-Kabel mit einem Computer verbunden. Die Kommunikation über diesen Weg erfolgt *seriell*. Das ist wichtig im Kopf zu behalten, weil sich Begriffe, Konzepte und Namen von Bibliotheken immer wieder auf diese Art des Datenaustauschs beziehen werden.

Bevor wir uns fortgeschritteneren Programmen und Versuchen widmen, sollten wir die Welt darüber informieren, dass wir jetzt auch an Board sind: Es ist Zeit, *Hello World!* zu sagen. Da die Ausgabe von Texten auf dem Arduino nicht so einfach möglich ist - es gibt keinen Bildschirm und kein Display - lassen wir im folgenden eine LED blinken.

## Öffnen der IDE

Wir öffnen die Arduino-IDE, die standardmäßig das *bare minimum* als Grundgerüst anbietet:

```java
void setup() {
  // put your setup code here, to run once:

}

void loop() {
  // put your main code here, to run repeatedly:

}
```

Das sieht nicht aus wie Python. Ist es auch nicht. Dazu gleich mehr. 

Ein Programm, das eine LED blinken lässt, ist schnell geschrieben:

```java
// Zuweisung an eine Variable vom Typ byte:
// Es soll der PIN 13 verwendet werden.
byte led = 13;

void setup() {
  // Definition des PINs 13 als Ausgang
  pinMode(led, OUTPUT);
}

void loop() {
  // Setzen des Potenzials am Ausgang 13 auf 5V (an)
  digitalWrite(led, HIGH);  
  // Eine Sekunde warten
  delay(1000);         
  // Setzen des Potenzials am Ausgang 13 aus 0V (aus)
  digitalWrite(led, LOW);
  // Eine Sekunde warten    
  delay(1000);
}
```

