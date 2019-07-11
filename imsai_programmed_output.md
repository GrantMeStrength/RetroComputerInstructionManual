# IMSAI 8080 Programmed Output

The IMSAI 8080 has a set of right LEDs in the top left of the panel that are under software control.

![IMSAI PO leds](images/imsai-PO-leds.png)

These make them very useful when writing code for testing and debugging - or for creating status lights, or a pretty blinkenlights display.

The LEDs are reached at port 255: writing a value to this port immediately changes which lights are on and off. You can write to this port directly in assembler, or from BASIC or other programming languages.

There is one quirk with the LEDs: when you send a "1" to an LED, it turns off, and sending a "0" turns then on. This inverted display is a result of the internal electronics on the IMSAI. It's easy to compensate in software though.

Here are some coding examples:


```BASIC
10 REM BASIC EXAMPLE
20 FOR A = 0 TO 255
30 OUT 255, A
40 FOR B = 1 TO 200
50 NEXT B
60 NEXT A
70 GOTO 20
```

or taking the inverted nature into account:

```BASIC
10 REM BASIC EXAMPLE WITH INVERTED
20 FOR A = 0 TO 255
30 OUT 255, 256-A
40 FOR B = 1 TO 200
50 NEXT B
60 NEXT A
70 GOTO 20
```

Here's a simple example in assembly language that just writes a value to the LEDs. Try changing the value the A register contains:

```asm
MVI A, F0h
CMA
OUT FFh
 ```

To enter this into the computer from the front panel, use the following pattern of switches. The binary number refers to the right most half of the 16 address switches.

* STOP
* Set all switches off
* RESET
* 0011 1110  DEPOSIT
* 1111 0000  DEPOSIT NEXT
* 0011 1111  DEPOSIT NEXT
* 1101 0011  DEPOSIT NEXT
* 1111 1111  DEPOSIT NEXT
* 1100 0011  DEPOSIT NEXT
* 0000 0000  DEPOSIT NEXT
* 0000 0000  DEPOSIT NEXT
* RESET
* RUN

You can combine using the LEDs at Port 255 with reading the Input value at port 255 - this value will be the state of the left most set of the 16 address switches.

For example, here's a BASIC program that will let you control the LEDs by flipping the switches.

```BASIC
10 REM BASIC EXAMPLE TO READ SWITCHES
20 A = INP(255)
30 OUT 255, A
40 GOTO 20
```