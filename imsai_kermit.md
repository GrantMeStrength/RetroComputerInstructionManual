# Copying files to the IMSAI8080eps

## Using Kermit

There are many ways to copy files to the remote "disk" of the emulated computer. For example, you can create a virtual .dsk image using [CPMTools](http://www.moria.de/~michael/cpmtools/), and then drag-and-drop it into the LIBS: folder. Or you can try this - connecting the IMSAI to your computer (in this case a Mac) using the IMSAI's ability to fool itself into thinking it is dialing a remote BBS.


* On the Mac..

Install a version of Kermit. Here's what worked for me: 

1. [Install Brew](https://brew.sh/) (a tool for installing Linux apps under macOS)
2. Then enter: 
> brew install c-kermit
3. Launch Kermit once it has installed.

> C-Kermit>set host * 8080

This tells Kermit to launch and wait for a connection. You should see:

> Waiting to Accept a TCP/IP connection on port 8080 ...

* On the IMSAI..

Make sure you're using an up-to-date CP/M disk, and Udo's communications disk which comes with a version of Kermit ready to go.

1. Launch Kermit from the TTY: window.
2. From the Kermit prompt:

>Set port UC1 

>Connect

>ATD192.168.86.82:8080

Make sure to use capital A,T, and D. You will need to substitute the IP address of your Mac for "192.186.82.82". You can get this from the Mac's network settings.

At this point, your IMSAI thinks it's calling a BBS. Bless!

* On the Mac..

The IMSAI connection should be accepted.

 > Reverse DNS Lookup... (OK)

> espressif.lan connected on port 8080

Kermit on the Mac will revert to the Kermit command prompt.



* On the IMSAI..

Press Ctrl and \, followed by C to return to the Kermit command prompt.

At this point you could type CONNECT on both systems and type text messages. However, let's send a file. You need to specify the name you want the received file to be called.

> receive hello.txt

* On the Mac..

You need to send the file. The XMODEM protocol works, so let's use that:

> send /protocol:xmodem hello.txt


You should now see the file being copied over. 

You can use this technique to send any kind of file to the IMSAI without having to physically connect it to Mac, so it's handy for quickly installing an app or sending some text files. It works in the other direction too - sending files from the IMSAI to the Mac.

## Using a Windows PC

The easiest way to use Kermit is to install [WSL](https://docs.microsoft.com/en-us/windows/wsl/wsl2-install), the Windows Subsystem for Linux. There's no need for Brew, you can install Kermit from WSL like this:

> sudo apt install ckermit

You can then follow the instructions above.

Note: The first time I tried this on a PM I couldn't get this to work. Using "Connect" was fine - I could type messages - but sending a file from the PC did nothing. However, once I sent a file from the IMSAI to the PC, that seemded to unclog the blockage and everything worked as expected. YMMV.
