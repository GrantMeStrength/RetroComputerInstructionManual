# IMSAI8080esp

## Using the IMSAI8080esp to access BBS systems

The IMSAI8080esp web interface and firmware includes support for accessing BBS systems over the internet. It does this by emulating an old-school AT compatible MODEM, bridging it to a TELNET connection, and displaying ANSI compatible text in the terminal. 

Here's how to log into a remote BBS.

1. Make sure you are using the TTY: terminal, not the CRT:
2. Boot a recent CP/M disk, and make sure KERMIT is available.
3. A>KERMIT
4. KERMIT>SET PORT UC1
5. KERMIT>CONNECT
6. KERMIT>ATD<NAME OF BBS> e.g. ATDBBS.ABYSSNODE.NET
7. Click the "A" in the TTY: menu bar to switch to ANSI graphics
8. The AT command to hangup is ATH


## Who to call?

Try [Telnet BBS Guide](https://www.telnetbbsguide.com)

## AT Commands

In the olden days we used modems to dial up other computers. Modems were connected to serial ports, and controlled by sending specific commands - usually starting with "AT" and then another character or two. The IMSAI (and the VT132 card also from TheHighNibble) extends the AT set to include commands that will connect to a remote computer system over TELNET protocol. Here's a [list of commands](https://thehighnibble.com/vt132/operation/modem/#at-commands).

<pre>
AT COMMANDS:
AT  - 'AT' Test                 | A/  - (immediate) Repeat last
AT$ - Help                      | ATIn - Information 
ATZ - Reset modem               |
AT&F - Restore factory defaults | AT&W - Write settings to NVRAM
ATDhostname:port - Dial hostname, port optional (default:23)
+++ - Return to command mode    | ATO - Return Online
ATH - Hangup
AT&A - Enable Answer mode - listen for incoming calls
ATA - Answer
ATSn - Select register n
AT? - Query current register    | AT=r - Set current register to r
AT&K0 - Disable flow control    | AT&K1 - Enable RTS/CTS flow control
AT+W? - Query WiFi AP Join status
AT+W=ssid,password - Join WiFI AP
AT+W$ - Show WiFi IP adddress   | AT+W# - Show WiFi MAC adddress
AT+W+ - Reconnect WiFI AP       | AT+W- - Quit WiFi AP
AT+U? - Query OTA Update        | AT+U=url - Set custom URL for OTA update
AT+U^ - Upgrade to OTA Update   | AT+U! - Force Upgrade to OTA Update
AT+U$ - Show OTA Parition Status
AT+B? - Query Baud Rate         | AT+B=nnn - Set Baud Rate (4800..115200)
AT+T? - Query Telnet TERM       | AT+T=name - Set Telnet TERM
</pre>

