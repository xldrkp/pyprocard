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

## Hello World!

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

Im Ergebnis sollte jetzt die kleine viereckige LED auf dem Board blinken. Hello World!

## Kompilieren und Hochladen

Um das Programm zu kompilieren, genügt ein Klick auf den Haken oben links in der IDE. Der geschriebene Code wird nun mithilfe des GCC-Compilers in Maschinencode umgewandelt, den der Microcontrollerchip auf dem Board verarbeiten kann. Das Gelingen oder Misslingen des Vorgangs meldet die IDE zurück.

Nun muss der Maschinencode noch auf den Controller geladen werden. Dies geschieht mit einem Klick auf den Pfeil neben dem Haken. Sofern Board und Port korrekt eingestellt sind und eine funktionierende USB-Verbindung zwischen Board und PC existiert, wird der Maschinencode nun über die serielle Schnittstelle auf den Arduino kopiert und kommt dort direkt zur Ausführung. Es kann immer nur ein Programm zur Zeit von dem Microcontroller ausgeführt werden. Sobald und solange der Arduino mit genügend Spannung versorgt wird, läuft das Programm in einer Endlosschleife. Um es zu stoppen, genügt es, den Arduino von der Stromquelle zu trennen. Er muss nicht heruntergefahren werden.

Der Vorgang des Kompilierens und Hochladens kann auch durch einen Klick auf den Pfeil zusammen erfolgen.

## Kein Python???

Die Syntax ist anders als bei den bisherigen Python-Beispielen. Da die Arduino-IDE aus der Processing-IDE entstanden ist, handelt es sich auch hier um Java-Code. Er wird beim Upload auf das Board umgewandelt und kompiliert. Einen Python-Mode für die Arduino-IDE gibt es nicht. Entwicklungsgeschichte und technische Hintergründe werden in der [deutschen](https://de.wikipedia.org/wiki/Arduino_%28Plattform%29)
und [englischen](https://en.wikipedia.org/wiki/Arduino) Wikipedia genauer erläutert.

An dieser Stelle gilt es, eine Entscheidung zu treffen: Weiter mit Python oder weiter mit Java? 

## Weiter mit Java?

Alle Beispiele in der Arduino-IDE (Menü Datei -> Beispiele) sind in der Java-Syntax verfasst. Sie sind sehr gut dokumentiert und spiegeln die vielfältigen Einsatzmöglichkeiten der Entwicklungsumgebung. Jedes Beispiel ist auf der Arduino-Homepage ausführlich dokumentiert, notwendige Bauteile und Schaltpläne anbeigestellt (vgl. exemplarisch das [Blink-Beispiel](https://www.arduino.cc/en/Tutorial/Blink)
). Es gibt eine große Zahl deutsch- und englischsprachiger Bücher zu unterschiedlichsten Themen, die das Potenzial der offenen Hard- und Software beleuchten (s. Anhang). Daher spricht grundsätzlich gar nichts dagegen, sich von dieser Seite dem Arduino zu nähern und voll in das hardwarenahe Programmieren über die Arduino-IDE einzusteigen.

## Weiter mit Python!

Da wir nun aber aus guten Gründen mit Python und nicht mit Java angefangen haben, setzen wir diesen Weg auch konsequent an dieser Stelle fort: Weiter mit Python!




