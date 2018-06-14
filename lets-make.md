---
description: >-
  Everything we learned so far was really informative but its time now, to
  actually make something out of it.
---

# Let's FLASH!

## Flashing an SOS signal  `... --- ...`      

Now, let us move a little  ahead and do something which is a little more fun.   
  
In the previous activity, we tried to toggle the LED manually by changing its `value` from `1` to `0` . This time we will flash the LED continuously according to the SOS distress-signal. It is an Internationally recognized Morse code signal that people use in order to seek help in case of any sort of emergency. 

{% hint style="warning" %}
### A spotlight on Morse code

The Morse Code is an Internationally recognized method of transmitting text information as a series of on-off tones, lights or clicks that can be directly understood by a skilled observer or listener without using any special equipment. 
{% endhint %}

Here is an elaborated list of different letters and symbols that we may transmit using Morse code.  
  
Carefully read the 5 important things mentioned at the top of the image given below -

![](.gitbook/assets/1200px-international_morse_code.svg%20%281%29.png)

### Setting up the Pin

Just like we did before, at first, import the `machine` module and create a Pin _object_ at GPIO2 --&gt; D4 of the NodeMCU dev board

```text
>>> import machine
>>> ledPin = machine.Pin(2, machine.Pin.OUT, value=1)
```

But don't you think the above code includes a lot of `machine` keywords?  
  
Here is an alternative program

```text
>>> from machine import Pin
>>> ledPin = Pin(2, Pin.OUT, value=1)
```

Simple and much easier to understand. That's the beauty of Python language which MicroPython inherits in itself.

{% hint style="success" %}
### How it works?

What we did here is allowed the `Pin` _class_ to be accessed directly without going into the `machine` module first.
{% endhint %}

### What needs to be done

### Defining functions

Now, comes the FUN __part where we will create our own functions for the SOS signals.   
  
Functions are required in every language to structure our code into _blocks of statements_ which together performs a specific _function_. Observe the code below that defines a _function_ to flash an LED connected at D2 for half-a-second with a time interval of one full second.

{% hint style="info" %}
Note here that Pin D2 of the NodeMCU development board is internally connected with GPIO2 of the ESP module.
{% endhint %}

{% code-tabs %}
{% code-tabs-item title="function.py" %}
```python
from machine import Pin
import time

ledPin = Pin(4, Pin.OUT, value=1)        # creates a Pin object at GPIO4(ESP) -> D2(NodeMCU)

def flash():             # defines a function named blinky
    ledPin.on()          # turns ON the LED 
    time.sleep(0.5)      # waits for 1 second
    ledPin.off()         # turns OFF the LED
    time.sleep(1)        # waits for another second

flash()             # executes the flash function
flash()             # 2nd flash
flash()             # 3rd flash
```
{% endcode-tabs-item %}
{% endcode-tabs %}

The above Python code simply defines a _function_ named `flash()` which performs one specific task i.e., flashes an LED connected at GPIO4\(D2\) for half-a-second and then sleeps off for a full second.  
  
Similarly, we need to define functions for the **S** Morse-code `...` and the **O** Morse-code `---`

{% hint style="warning" %}
###             
{% endhint %}

Let us consider one dot as a 200 milliseconds long flash and we have to make 3 such flashes.

### Repeating tasks

When such situations arise where repetition of some task is required _for a specific number of times_, we implement the `for()` loop.  
  
Consider the code below

```text
for i in range(1,4):
    do this
    do that
```

The above `for()` loop is intended to run 3 times, as long as `i` is in the range specified i.e., starting from 1 up to 3, but not including 4.  
  
Now take a look at this code-snippet

{% code-tabs %}
{% code-tabs-item title="forLOOP.py" %}
```python
def flash():                 # defines a function named blinky
    for i in range(1,4):     # Repeats the statements within 3 times
        ledPin.off()         # turns ON the LED 
        time.sleep(1)        # waits for 1 second
        ledPin.on()          # turns OFF the LED
        time.sleep(1)        # waits for another second
        
flash()                      # flashes the LED 3 times
```
{% endcode-tabs-item %}
{% endcode-tabs %}

This is the same `flash()` function that we wrote above to blink an LED.  
But, this time the function also performs a 3x repetition of the instructions within the `for()` loop. 

{% code-tabs %}
{% code-tabs-item title="flashOnce\_SOS.py" %}
```python
from machine import Pin
import time

ledPin = Pin(2,Pin.OUT,value=1)

def S():
    for i in range(1,4):
        ledPin.off()
        time.sleep_ms(200)
        ledPin.on()
        time.sleep_ms(200)

def O():
    for i in range(1,4):
        ledPin.off()
        time.sleep_ms(600)
        ledPin.on()
        time.sleep_ms(200)

# Flashing the SOS signal continuously
while True:        
    S()
    time.sleep_ms(400)
    
    O()
    time.sleep_ms(400)
    
    S()
    time.sleep_ms(1400)
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Here, we see that the above Python code flashes the SOS signal only once  **...---...**

In order to loop over tasks, we need loops that are provided by every programming language to repeat certain instructions over and over again.   
  




