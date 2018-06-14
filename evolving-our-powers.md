---
description: >-
  In the following lesson, the learner will begin to control the surrounding
  world using simple actuators like LEDs and also sense the environment using
  various sensors available at our disposal.
---

# Controlling things

## Let's Toggle!

Now is the perfect time to begin programming our ESP module and do something FUN and engaging. The on-board LED will be our first example but in upcoming lessons we will see how to control stuff that runs on AC power like Lights, Fans, Refrigerators and any n

### Toggling the on-board LED

Within the REPL itself, type the following:

{% code-tabs %}
{% code-tabs-item title="ledToggle" %}
```python
import machine
myPin = machine.Pin(2, machine.Pin.OUT, machine.Pin.value = 1)
myPin.value(0)
myPin.value(1)
myPin.off()
myPin.on()     
```
{% endcode-tabs-item %}
{% endcode-tabs %}

### Decoding our code

{% tabs %}
{% tab title="Line 1" %}
#### Imports the _machine_ module

It tells the Interpreter that we want to import the `machine` module from the MicroPython Firmware in the flash storage\(4 MB\). 

{% hint style="info" %}
This specific  `machine` module allows us to interact with the ESP module's hardware parts like all of it's I/O pins and other peripherals.
{% endhint %}
{% endtab %}

{% tab title="Line 2" %}
#### Creates an _**object**_

The line creates a Pin object `myPin` which _behaves_ as an OUTPUT whose state is 1\(HIGH\).   __

{% hint style="info" %}
All these _objects_ have a _"state"_ and a  _"behavior"_                             
{% endhint %}
{% endtab %}

{% tab title="Line 3" %}
#### Using the _object_

Here, we call our recently created object `myPin` and change its _value/state_ from HIGH to LOW i.e., from 1 to 0 in order to turn ON the on-board LED of our NodeMCU.

{% hint style="info" %}
Observe here that the on-board LED turns ON when it's state is 1\(LOW\). In other words the LED gets activated whenever a LOW signal is given to it. In digital terms, it is an active-low LED.
{% endhint %}
{% endtab %}
{% endtabs %}

{% hint style="success" %}
### How it works?

The reason why it behaves this way is because this LED's positive terminal is directly pulled-up to 3.3V internally. Thus, in order to allow the current to pass through the on-board LED, we need to create a potential difference by passing a LOW signal at the LED's negative terminal
{% endhint %}

## 

