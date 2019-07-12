# Writing software using switches and LEDs

How on earth do you write software for a box with only LEDs and some switches? And the answer is "very carefully".

Of course no-one in their right mind would write a large application in this way, but it is possible to write simple games, or - more usefully back in the day - code that can talk to a peripheral floppy disk drive (for example) and load and run much larger programs.

**Code**

Using the switches, you can enter a byte at a time into memory. The hard part, of course, is knowing which bytes to use! 

The Altair and IMSAI use the Z80 or 8080 CPUs, which are very similar. They can perform simple instructions (adding, subtracting, comparing, logical operations) and with this list, you write software. Now that I write it out loud, it sounds crazy, but it works, honestly. 

The **instruction set** is a list of these operations and the numeric code that associated with each one. It's this numeric value that you store in memory - tedious code by tedious code.

You'll need to use the following switches to enter these "machine codes".

| Switch | Function |
|------------------------------------|------|
| Address switches | Select a memory address|
| DEPOSIT | Store a byte of memory into the current address|
| DEPOSIT NEXT | Move to the next address in memory and store a byte there|
| EXAMINE | Using the current position of the address switches to define a memory location, display the contents of the byte stored there |
| EXAMINE NEXT | Jump to the next memory location and display the contents of the byte stored there|


**Examples of some simple apps**




**Running, stopping and single-stepping**



**Saving and loading**

How would you save such a carefully entered piece of software? Well, unless you added some extra hardware, you couldn't save it. If you ever turned the computer off, the program would be lost forever.

Storage systems were therefore high on every computer owner's list. The cheapest was the humble cassette tape. Many expansion cards included support for saving and loading memory to tape as audio tones.

Floppy disks were considerably more convenient (but expensive), and eventually hard drives came along with literally megabytes of storage. 

Early adaptors may have used paper tape to store programs too - the first version of Microsoft BASIC was sold on paper tape. To load it, you needed a tape reader - a loud and expensive machine. 