Overview
========

The enet_rxtx_ptp1588 example shows the way to use ENET driver to  
 receive and transmit frame in the 1588 feature required cases.

1. This example shows how to initialize the ENET MAC.
2. How to use ENET MAC to receive and transmit frame.
3. How to add to the multicast group to receive PTP 1588 message.
4. How to get the time stamp of the PTP 1588 timer.
4. How to use Get the ENET transmit and receive frame time stamp.

The example transmits 20 number PTP event frame, shows the timestamp of the transmitted frame.
The length, source MAC address and destination MAC address of the received frame will be print. 
The time stamp of the received timestamp will be print when the PTP message frame is received. 

Note, The RMII mode is used for default setting to initialize the ENET interface between MAC and the external PHY. you 
can change it to MII mode as you wish. Please make sure the MII Mode setting in the MAC is synchronize to the setting
in TWR-SERIAL board for the external PHY.

Toolchain supported
===================
- IAR embedded Workbench 7.80.4
- GCC ARM Embedded 2016-5.4-q3

Hardware requirements
=====================
- Network cable RJ45 standard
- Micro USB cable
- MCIMX6UL-EVK  board
- JLink Plus
- 5V power supply
- Personal Computer

Board settings
==============

Prepare the Demo
================
1.  Connect 5V power supply and JLink Plus to the board, switch SW2001 to power on the board.
2.  Connect a USB cable between the host PC and the J1901 USB port on the target board.
3.  Open a serial terminal with the following settings:
    - 115200 baud rate
    - 8 data bits
    - No parity
    - One stop bit
    - No flow control
4.  Insert Cable to Ethernet RJ45 port 1 and connect it to your PC.
5.  Download the program to the target board.
6.  Either press the reset button on your board or launch the debugger in your IDE to begin running the demo.

Running the demo
================
When the demo runs, the log would be seen on the terminal like:

ENET PTP 1588 example start.

Get the 1-th time xx second xx nanosecond
........
Get the 10-th time xx second xx nanosecond

The 1 frame transmitted success! the timestamp is xx second, xx nanosecond
The 2 frame transmitted success! the timestamp is xx second, xx nanosecond
The 3 frame transmitted success! the timestamp is xx second, xx nanosecond
The 4 frame transmitted success! the timestamp is xx second, xx nanosecond
......
The 20 frame transmitted success! the timestamp is xx second, xx nanosecond

Note: the xx second and xx nanosecond should not be zero and should be number with solid increment.

the transmitted frame is a 1000 length broadcast frame. the frame can be seen
when the PC is installed with wireshark.

when a 1000 length ptp event message frame is received, the log would be added to the terminal like:
A frame received. the length 1000 the timestamp is xx second, xx nanosecond
Dest Address xx:xx:xx:xx:xx:xx Src Address xx:xx:xx:xx:xx:xx
Customization options
=====================

