---
description: >-
  In this hands-on activity, we will MAKE a smart extension board of the 21st
  century which is capable of being controlled and monitored via the World Wide
  Web.
---

# Today's Extension Board

## Subscribing to messages

Subscribing to messages is a little more sophisticated than publishing messages as, while subscribing, we need to set a callback function to execute itself whenever a message is received. The same callback function can perform different tasks corresponding to the message received.

If we receive an 'ON' message, then we turn ON something

If we receive an 'OFF' message, then we turn OFF something

Similarily, if we subscribe to a Topic that publishes integers, then we need to amend our call back function accordingly to handle those numerical values appropriately. 

