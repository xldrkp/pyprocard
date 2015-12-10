## Bibliotheken einbinden und verwenden

Der Funktionsumfang von Processing kann durch [eine Reihe verschiedener Bibliotheken](https://processing.org/reference/libraries/) (engl.: libraries) erweitert werden. Eine Bibliothek ist eine Sammlung von Funktionen oder Klassen, die eine Programmiersprache um weitere Befehle erweitert.

Bei Python spricht man von Modulen statt von Bibliotheken, das Prinzip ist aber dasselbe. Das Einbinden von Python-Modulen werden wir noch an anderer Stelle besprechen.

### Eine Bibliothek in einen Processing-Sketch einbinden

Am Beispiel der *minim*-Bibliothek wollen wir herausfinden, wie man eine Bibliothek in Processing einbindet und wie man mit ihr programmiert. Sie ist eine umfangreiche und altbewährte Sammlung von Klassen und Methoden zur Klangerzeugung und -manipulation.

Damit die Funktionen der Bibliothek in unserem Sketch bekannt sind und verwendet werden können, muss die Bibliothek zunächst importiert werden. Das bedeutet, dass wir eine Zeile Code schreiben müssen, die die Datei mit den Klassen- und Funktionsdefinitionen unserem Sketch hinzufügt. Einige Bibliotheken werden schon mit Processing ausgeliefert (DXF Export, Networt etc.) und können direkt über das Kontextmenü (s. Abbildung) importiert werden, weitere sind aus der IDE heraus herunterzuladen. Die folgende Abbildung zeigt, dass die *minim*-Bibliothek noch nicht in Processing bekannt ist. Wir laden sie also herunter:

![Library einbinden](../images/lib-library-hinzufuegen.png)

Die Eingabe von *minim* in das Filtereingabefeld oben links zeigt die gewünschte Bibliothek an:

![Libraries laden](../images/lib-libraries-laden.png)

Mit der Schaltfläche *Install* wird die Bibliothek heruntergeladen und in der IDE installiert. Dieser Vorgang muss für weitere Sketches nicht wiederholt werden. Es kann sein, dass einige Bibliotheken, die im Java-Mode von Processing funktionieren, nicht mit dem Python-Mode kompatibel sind.

Anschließend kann über *Sketch->Library importieren* die Bibliothek *minim* ausgewählt werden. Die folgende Abbildung zeigt die entsprechende Codezeile:

![Library importiert](../images/lib-importiert.png)

Wenn wir nun unseren Sketch laufen lassen, wird der Code in der externen Bibliothek durch den Compiler in unser Programm einbezogen.

### Die Referenz der Bibliothek finden und lesen

Zu jeder Bibliothek gehört eine Referenz, die dokumentiert, wie sie zu installieren ist und welche Schnittstelle sie bietet. Im Englischen spricht man auch von *Application Programming Interface (API)*. Hiermit sind alle Funktionen gemeint, die die Bibliothek zum Programmieren zur Verfügung stellt. Die [*minim*-Referenz](http://code.compartmental.net/minim/) ist nicht über die Website von Processing, jedoch leicht über eine Suchmaschine zu finden. 

Nahezu alle Referenzen von Bibliotheken enthalten Beispiele in der Java-Syntax, sodass für die Anwendung im Python-Mode die entsprechende Anpassung vorgenommen werden muss.

Durch das Hinzufügen von Bibliotheken aus dem Netz wird auch die Liste der Beispiele in der Processing-IDE erweitert *(Datei -> Beispiele)* - allerdings auch nur in Java-Syntax.

### Eine Sounddatei mit minim abspielen

