# 2732 EPROM Emulator

This EPROM Emulator dramatically speeds up the process of testing revisions to the firmware of my [4004 Single Board Computer](https://github.com/jim11662418/4004-SBC). Instead of burning a new EPROM every time I want to test a change to the firmware, I simply assemble the new firmware and upload the Intel HEX file output of the assembler to the EPROM Emulator's DS89C440 MCU serial port at 115200 bps. The MCU stores the data it receives from the serial port in the [IDT 7134 Dual Port RAM](https://www.idt.com/products/memory-logic/multi-port-memory/asynchronous-dual-port-rams/7134-4k-x-8-dual-port-ram) using one of the two ports. The second port of the RAM is connected to the SBC's EPROM socket through a ribbon cable. Press the reset button on the 4004 SBC, and the 4004 CPU uses the second port to fetch and then execute instructions from the Dual Port RAM just as it would from a 2732 EPROM.

The Emulator's firmware also allows the user to display and modify the Dual Port RAM contents over the serial connection.

The Emulator's [firmware](EPROM-Emulator.asm) is assembled using the [Macro Assembler AS](http://john.ccac.rwth-aachen.de:8000/as/).

The EPROM Emulator was constructed on a Vector Prototyping board using wire-wrap techniques.
<p align="center"><img src="/images/EPROM Emulator.JPEG"/>
<p align="center">EPROM Emulator</p>
<p align="center"><img src="/images/EPROM Emulator Schematic-1.png"/>
<p align="center">EPROM Emulator Schematic</p>
<p align="center"><img src="/images/EPROM Emulator.png"/>
<p align="center">EPROM Emulator</p>
