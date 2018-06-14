---
description: >-
  In this lesson, we will learn how to connect our ESP module with the Internet
  and configure it in such a way which makes it connect to the Web automatically
  whenever it boots up.
---

# Connecting with the World

## Connecting with a WiFi network

Connecting to a nearby WiFi access point is pretty straight-forward.

### Creating a Station Interface

In order to create a _station_ _interface_ on our ESP module, we first need to _import_ the `WLAN` and `STA_IF` _classes_ from the `network` module.

{% code-tabs %}
{% code-tabs-item title="importingNetwork.py" %}
```python
fron network import WLAN, STA_IF
```
{% endcode-tabs-item %}
{% endcode-tabs %}

A _station_ interface actually makes our NodeMCU to act as a _client_ so that it can connect with a nearby WiFi network or _access-point._

{% code-tabs %}
{% code-tabs-item title="stationInterface.py" %}
```python
from network import WLAN,STA_IF

myFi = WLAN(STA_IF)        # creates a station object
myFi.active(True)          # activates the myFi station we just created
```
{% endcode-tabs-item %}
{% endcode-tabs %}

The above 3- line Python code actually makes our ESP module, a WiFi client just as our other Gadgets like Smartphones/Tablets, Smart TVs, Laptops, etc.

###  Connecting to a network

To connect with a WiFi network, we simply call the _connect_ method from our `myFi` _object_ and pass the _network-name_ and it's _password_ as an input to the _connect_ method. 

Take a look at line 5 in the code below to have a clear understanding:

```python
from network import WLAN,STA_IF

myFi = WLAN(STA_IF)        # creates a station object
myFi.active(True)          # activates the myFi station we just created
myFi.connect('<network-name>','<network-password>')        # connect with <network-name>
myFi.isconnected()         # checks whether myFi is connected to <network-name> or not
myFi.ifconfig()            # prints myFi configuration like IP addr and other network details
```

We see how easy it is to connect with a WiFi network in Python. This gives us the _freedom_ to monitor and control our Gadgets from the Web anywhere around the globe.

If we see the potential of such gadgets, it's HUGE! Since such ESP-like modules are very inexpensive, compact and reliable at the same time, they can be embedded in almost anything which will eventually create a Web of Objects and Things which are inter-connected, conveying information between people, objects and processes.

### `letsConnect()`

Here is a handy function that you may use in order to connect with a WiFi network right away - 

{% code-tabs %}
{% code-tabs-item title="letsConnect.py" %}
```python
def letsConnect():
    from network import WLAN, STA_IF    
    myFi = WLAN(STA_IF)                                     
    if myFi.isconnected() == False:        	# if wifi is not connected, execute the statements below:
        myFi.active(True)
        print('Connecting to the network...')
        myFi.connect('AndroidAPpp','')  
        while myFi.isconnected() == False:    	# do nothing until we are connected to the network 
            pass
    print("Network configuration:", myFi.ifconfig())		# print the network configuration once we are connected	

letsConnect()		# execute the letsConnect function
```
{% endcode-tabs-item %}
{% endcode-tabs %}

###  



