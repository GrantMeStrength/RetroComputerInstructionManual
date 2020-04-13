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

