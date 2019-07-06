## Connecting a video display to your computer

IN PROGRESS

The early home computers such as the Altair and IMSAI did not have video cards. Likewise, the kits do not have HDMI or even VGA ports as standard (Note: the 'Pro' edtion of the Altair-Duino kit from AdWaterAndStir has a VGA port).

Out of the box, just like the real thing, the only way to interact with these computers was by using the switches on the front panels and by watching the LEDs. Although interesting, this can be quite limiting.

### Display options

Original users of these computers connected them via serial ports to either Teletypes (machines with keyboards and built-in printers for displaying text) or Terminals (machines with a display and a keyboard). In the 1970s both were expensive options, which is why the computers did not come with either.

Your choices are:

* Connect to a computer over USB
* Connect to a computer over BlueTooth
* Connect to a computer over serial
* Connect to a computer over Wi-Fi
* Connect to a terminal over serial
* Connect to a computer monitor and keyboard

Not all devices and configurations may be supported by your hardware.


### Connect to a computer over USB

The Altair and IMSAI kits both include USB ports, which can be used to both power and interface with the computer. A terminal emulation program (such as Serial on the Mac, or PuTTY on the PC) makes things a lot easier.

Plug the USB lead into your computer (Mac, PC or Linux), and the retro computer kit. The computer will recognize a new USB port.

On a Mac, if you launch an app such as Serial and select File / Open port, you will see an incoming port listed as, for example, **Arduino Due Prog. Port**. If you select this port, with a default speed of 115,200 you'll be connected.

On a PC, using an app like PuTTY, you can connect to a new COM port which will have appeared once you pluged in the USB cable.

Once connected, skip to **Communicating with the retro comptuter** below.

### Connect to a computer over BlueTooth

The Altair kit from AdWaterAndStir comes with a BlueTooth module. A terminal emulation program (such as Serial on the Mac, or PuTTY on the PC) will also make things a lot easier.

On a Mac, if you launch an app such as Serial and select File / Open port, you will see an incoming port listed as, for example, **JOY_20**. If you select this port, with a default speed of 115,200 you'll be connected.

On a PC, using an app like PuTTY, you can connect to a new COM port which will have appeared.

### Connect to a computer over serial

* Using a dumb terminal
* Using a PC
* Building your own terminal

### Using a built-in monitor and keyboard



## Communicating with the retro computer

Once a physical or wireless connection has been made, there is still work to do.
