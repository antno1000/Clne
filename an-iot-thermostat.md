---
description: >-
  Applying the hard-earned knowledge so far, let us build a simple IoT gadget
  that monitors the surrounding temperature.
---

# An IoT thermostat

## Components required

* Analog Temperature Sensor - 1
* NodeMCU - 1
* Jumpers 

## Getting Temperature values

In order to read temperature values from LM35 temperature sensor, do this:

```python
from machine import ADC        # imports the Pin and ADC class from the machine module
import time

temp = ADC(0)                  # creates a temp object to read
while True:                    # repeats the statements within forever
    tempSense = temp.read()    # reads the 10-bit analog value from LM35
    print(tempSense)           # prints the tempSense value on the monitor
    time.sleep_ms(100)         # wait for 1/10th of a second before reading the next value
```

## Publishing messages to a Adafruit.io

In order to publish messages to an MQTT broker, we only need to import the MQTT client _class_ from the `umqtt.simple` module available to us in the MicroPython firmware. 

To do so, add the following statements to your previous code:

{% code-tabs %}
{% code-tabs-item title="publishTemp.py" %}
```python
from machine import ADC
import time
from umqtt.simple import MQTTClient
broker = 'io.adafruit.com'
user = 'icreate'
topic = b'icreate/f/pot'
key = '697847b8dfbb4b43b8f06bf7ed037887'
myClient = MQTTClient('nodeMCU', broker, 1883, user, key)
myClient.connect()
while True:
    myClient.publish(topic,str(ADC(0).read()))
    time.sleep(1)
myClient.disconnect()
```
{% endcode-tabs-item %}
{% endcode-tabs %}

{% code-tabs %}
{% code-tabs-item title="knobDegree.py" %}
```python
from machine import ADC
import time

def knobToDegrees(maxVolt=3.3):
    knobVal = 0
    knobVal = ADC(0).read()
    knobVolt = knobVal * (3.3/1024)
    print("Voltage at Pin A0 of NodeMCU",end='- ')
    print(knobVolt, end=' Volts\n') 
    knobRotation = knobVolt * (270/3.3)
    print("Knob Rotation",end='- ')
    print(knobRotation, end=' degrees\n')
    
knobToDegrees()    
```
{% endcode-tabs-item %}
{% endcode-tabs %}



