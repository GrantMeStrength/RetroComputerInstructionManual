## Introduction to system architecture


Conceptually, the Altair and IMSAI computers were a very straightforward design. Inside the box was a front panel with LEDs and switches, a power supply, and a "back plane" which was a circuit board with pretty much nothing but a set of interconnected 100 pin slots.

Into the slots would be placed the various cards that comprised the computer system: first the CPU card (with Intel 8080 or Zilog Z80 CPUs at 2Mh), and then a RAM card (initally composed of static RAM chips).

In theory that's all what was needed to make a working computer. In practice, users also installed floppy and hard drive controller cards, ROM cards, more RAM, serial cards (for driving terminals, printers and so on), parallel cards (for printers), and even graphic display cards and camera capture cards.

**Memory Map**

The 8080 and Z80 CPUs could address up to 64Kb of memory* and this would start at 0000h and (funds permitting) go all the way to FFFFh. Memory was used to store program code and data, and when the user set the front panel address switches to off and toggled RESET and then EXAMINE, the program counter was set to 0000h and the computer would display the contents of memory. Static memory chips would often contain random data, and so the data LEDs would display a random pattern.

| Description     | Address |
|-----------------|---------|
| Start of memory | 0000h |
| End of possible memory   | FFFFh |



**Memory Map using CP/M**

If CP/M was loaded, memory was arranged in a specific way. Again, it started at 0000h, but this time CP/M included some code there (so that the computer would always start doing something when RESET and START was toggled).

| Description                       | Address |
|-----------------------------------|---------|
| Start of memory                   | 0000h   |
| Free memory for program aka "TPA" | 0100h   |
| CCP - command line program        |         |
| BDOS                              |         |
| BIOS                              |         |
| End of possible memory space      | FFFFh   |

The exact address of the CCP, BDOS and BIOS components of CP/M would vary on your system. Depending on much memory you had installed, you would litterally build your own custom version of CP/M to make full use of it. Your bespoke CP/M would also include the necessary drives for the floppy and hard drives you added to the system.

However, the clever part is that the CP/M code from 0000h to 0100h would always know where the routines in the BDOS and BIOS where stored. Any application could call the CP/M "Print" routine by calling the code at address 00009h and would be redirected to the code in the BDOS that did the actual printing.

**ROMs***

ROMs could be installed into the system, and they would need to appear in the same memory map. For example, a floppy disk drive might come with a ROM of drivers, and that ROM would expect to be at a specific address - say F000h. The user could then start the code in the ROM from running by selecting F000h on the address switches, toggling EXAMINE and RUN.

*The 8080 could in theory address up to 128Kb, using the second 64Kb for stack memory.