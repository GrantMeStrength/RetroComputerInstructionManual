# Disk management on the IMSAI 8080 Replica

**Changing disks**

Accessing disks - or more accurately, disk images stored on the SD card - is managed through the IMSAI Desktop UI. This is a web-based interface hosted on the IMSAI itself.

If you have yet to configure the IMSAI, when turned on it will create a local WiFi hotspot for your desktop computer to connect to directly (SSID: imsai8080, password: password). Once connected, open a web browser (Chrome is recommended), and go to http://imsai8080.local or http://192.168.4.1.

If you have configured the IMSAI to join your local home WiFi network, then you can open a browser and go to http://imsai8080.local. If that address doesn't resolve, you'll need to find a way of finding its IP address by listing devices on your home network - your WiFi router's configuration page for example. Or you can install **Bonjour** on your computer.

Once the desktop is open, all the floppy disks are stored in an online folder called LIB:. Open that, and drag them into the disk drive icons (ejecting any that are mounted there already). You'll need to type **CRTL C** at the terminal to warm CP/M that the disks have changed.

**Add new disk images to the LIB: folder**

**Adding hard disks to the emulator**

**Selecting ROMs at start time**