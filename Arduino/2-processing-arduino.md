## Processing und Arduino

~~~ {caption="Das Blink-Beispiel" .python .numberLines}
add_library('serial')
add_library('arduino')

import time

led_pin = 13
a = Arduino(this, '/dev/ttyACM1', 57600)


class Blink:

    def on(self):
        a.pinMode(led_pin, Arduino.HIGH)
        time.sleep(.2)

    def off(self):
        a.pinMode(led_pin, Arduino.LOW)
        time.sleep(.2)

def setup():
    a.pinMode(led_pin, Arduino.OUTPUT)
    b = Blink()

def draw():
    Blink.on()
    Blink.off()
~~~
