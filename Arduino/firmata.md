# Firmata

Der einfachste Zugang zur Programmierung des Arduino mit Python erfolgt mithilfe der so genannten StandardFirmata. Dabei handelt es sich um eine spezielle Version der [Firmata](https://github.com/firmata/protocol)
für Arduino-Boards. Wir setzen sie ein, um von Processing aus unser Arduino-Board steuern zu können - mit Python! Dabei ist eine Sache für das Verständnis des komplexen Aufbaus am Wichtigsten: 

Die StandardFirmate wird **einmalig** auf das Arduino-Board geladen. Anschließend erfolgt die Programmierung in der Processing-IDE nur noch in Python!

Das folgende Schaubild zeigt diesen Sachverhalt.

![](../images/workflow.png)

**Abbildung**: Grundsätzliche Arbeitsweise mit der StandardFirmata

Schreiten wir zu Tat und stellen die notwendigen Bedingungen für die Weiterarbeit her!

## Hello World! Again.



