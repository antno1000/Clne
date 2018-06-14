# Setting up our PC

## Preparing our ESP8266  {#preparing-our-esp8266}

For us to be able to do what we discussed above, there are certain software packages that are required in order to quickly get us started with the most fun part - MAKING!

### The uPyCraft IDE\(Integrated Development Environment\) {#the-upycraft-ide-integrated-development-environment}

The uPyCraft IDE is the official development software released by the MicroPython community to Edit, Verify and Upload our application\(python program\) to the ESP's memory. It also integrates all the other required development tools that are necessary to design a great IoT gadget.

Click here to download the latest version for your Windows PC.

### Setting up the IDE {#setting-up-the-ide}

After installing the uPyCraft IDE, double-click on the desktop icon and launch the program and there you go! It is a user-friendly software that allows us to write and upload our Python scripts to the NodeMCU development board

&lt;screen-shot&gt;

### Setting up PUTTY {#setting-up-putty}

Now at last, we require a tool that can communicate with the NodeMCU over the USB cable.

**Putty** has been the choice so far of the IoT community to talk with their devices over a serial port. Click [here](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html), to download it right away and proceed with the installation.

After the installation of Putty is done, we need to create a profile within. Launch Putty and select the Serial dot-box to create a serial-connection profile and enter the following in the given fields:

**COM port** - See My Computer &gt; Properties &gt; Device Manager &gt; Ports\(COM and LPT\) for your specific port number. **Baud rate** - 115200. It is default speed in bits-per-second that our ESP module uses, in order to communicate with the PC.![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LAUGfQDK6mUCt4gHqSq%2F-LDGAbUFNo9zQ1Pde5oy%2F-LDGUwoKL5nlnirx9SwZ%2FputtySerial.png?alt=media&token=b3899954-f4e5-4e73-aa1c-e502ab5da252)Follow --&gt; 1 --&gt; 2 --&gt; 3

Name this profile and save it to quickly load it the next time you use Putty. Finally, click on the "Open" button. A dialog-box with a black background will pop-up ; Press the `RESET` button on the NodeMCU dev board and watch that Window. You will see that the board has been successfully reset and the Python REPL prompt `>>>` is waiting for us to give instructions.

