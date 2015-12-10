## Bibliotheken einbinden und verwenden

Der Funktionsumfang von Processing kann durch [eine Reihe verschiedener Bibliotheken](https://processing.org/reference/libraries/) (engl.: libraries) erweitert werden. Eine Bibliothek ist eine Sammlung von Funktionen oder Klassen, die eine Programmiersprache um weitere Befehle erweitert.

Bei Python spricht man von Modulen statt von Bibliotheken, das Prinzip ist aber dasselbe. Das Einbinden von Python-Modulen werden wir noch an anderer Stelle besprechen.

### Eine Bibliothek in einen Processing-Sketch einbinden

Am Beispiel der *minim*-Bibliothek wollen wir herausfinden, wie man eine Bibliothek in Processing einbindet und wie man mit ihr programmiert.

Damit die Funktionen der Bibliothek in unserem Sketch bekannt sind und verwendet werden können, muss die Bibliothek zunächst importiert werden. Einige Bibliotheken werden schon mit Processing ausgeliefert (DXF Export, Networt etc.), weitere können aus der IDE heraus heruntergeladen werden. Die folgende Abbildung zeigt, dass die *minim*-Bibliothek noch nicht in Processing bekannt ist. Wir laden sie also herunter:

![Library einbinden](../images/lib-library-hinzufuegen.png)

Die Eingabe von *minim* in das Filtereingabefeld oben links zeigt die gewünschte Bibliothek an:

![Libraries laden](../images/lib-libraries-laden.png)

Mit der Schaltfläche *Install* wird die Bibliothek heruntergeladen und in der IDE installiert. Dieser Vorgang muss für weitere Sketches nicht wiederholt werden.

Anschließend kann über *Sketch->Library importieren* *minim* ausgewählt werden. Die folgende Abbildung zeigt die entsprechende Codezeile:

![Library importiert](../images/lib-importiert.png)

### Die Referenz der Bibliothek finden und lesen

Zu jeder Bibliothek gehört eine Referenz, die dokumentiert, wie sie zu installieren ist und welche Schnittstelle sie bietet. Im Englischen spricht man auch von *Application Programming Interface (API)*. Hiermit sind alle Funktionen gemeint, die die Bibliothek zum Programmieren zur Verfügung stellt. Die [*minim*-Referenz](http://code.compartmental.net/minim/) ist nicht über die Website von Processing zu finden, jedoch leicht über eine Suchmaschine zu finden.

### Eine Sounddatei mit minim abspielen

