## Bedingte Anweisungen und Verzweigungen

Man spricht von einer Fallunterscheidung oder **bedingten Anweisung**, wenn ein Codeblock an eine Bedingung geknüpft ist. Der Codeblock wird folglich nur ausgeführt, wenn die Bedingung erfüllt wird.

Eine bedingte Anweisung wird mit `if` formuliert:

```python
ecken = 3

if ecken == 4:
  rect(10, 10, 10, 10)
```

Hier wird mit dem Ausdruck `ecken == 4` gesagt, dass der Inhalt der Variablen `ecken` gleich mit dem Integer `4` sein muss. Darin besteht die Bedingung. Ist sie erfüllt, liefert der Ausdruck den Booleschen Wert `True`, sonst `False`. Da der folgende Codeblock nur ausgeführt wird, wenn die Bedingung `True` ist, und sie hier `False` ist, wird nichts gezeichnet.

Das doppelt Gleichheitszeichen nennt man *Gleichheitssoperator*. Der Gleichheitssoperator gehört zu den Vergleichsoperatoren.

Gibt es bei einer Fallunterscheidung mehrere Möglichkeiten, den Code abhängig von Bedingungen auszuführen, spricht man von einer **Verzweigung**.

```python
ecken = 3

if ecken == 4:
  rect(10, 10, 10, 10)
elif ecken == 3:
  triangle(50, 0, 100, 99, 0, 99)
```

Hier werden zwei verschiedene Bedingungen formuliert. Ist eine davon wahr, folgt das Programm dem zugehörigen Zweig. Mit `elif` lassen sich beliebig viele Fälle prüfen.

Soll auch Code ausgeführt werden, wenn keine der Bedingungen erfüllt ist, gibt es eine letzte Möglichkeit mit `else`:

```python
ecken = 0

if ecken == 4:
  rect(10, 10, 10, 10)
elif ecken == 3:
  triangle(50,0,100,99,0,99)
else:
  ellipse(50,50,50,50)
```

Zweige mit kann es beliebig viele geben, auch gar keinen. Es darf aber nur einen `else`-Zweig geben.

Folgendes Beispiel zeigt einen Fall ohne `elif`, dafür aber mit `else`:

```python
ecken = 3

if ecken == 4:
  rect(10, 10, 10, 10)
else:
  text("keine Form", 15, 50)
```
