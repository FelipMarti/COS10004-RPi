# Computer Systems (COS10004) - Raspberry Pi Labs

ARM assembly programming using RPi for Computer Systems (COS10004) at Swinburne University of Technology 

## Summary of RPi models

|        RPi Model        |     2B     |   2B v1.2  |     3B     |     3B+    |     4B     |
|:-----------------------:|:----------:|:----------:|:----------:|:----------:|:----------:|
|           SoC           |   BCM2836  |   BCM2837  |   BCM2837  |  BCM2837B0 |   BCM2711  |
|          Memory         |    512MB   |     1GB    |     1GB    |     1GB    |   1/2/4GB  |
| Peripheral Base address | 0x20000000 | 0x3F000000 | 0x3F000000 | 0x3F000000 | 0xFE000000 |
|       GPIO Offset       |  0x200000  |  0x200000  |  0x200000  |  0x200000  |  0x200000  |
|                         |            |            |            |            |            |


## RPi 4B
### RPi 4B Material
- USB Type-C (male) to USB Type-A (male) 5V/3.0A power supply. Important: not [e-marked](https://arstechnica.com/gadgets/2019/07/raspberry-pi-4-uses-incorrect-usb-c-design-wont-work-with-some-chargers/)
- micro SD card (8GB or more)
- micro SD card adapter for computer
- breadboard
- a few LEDs 
- a few resistors (47Ω or more)
- a few cables to connect from GPIO pins (female) to the breadboard (male)
- electronic buttons (for the I/O labs)
- micro HDMI (male) adapter to computer lab screens (normally DVI)

### RPi 4B micro SD card files
- [start4.elf](https://github.com/raspberrypi/firmware/blob/master/boot/start4.elf)
- [kernel.img](4B/kernel.img) - Writes 1 to GPIO18 pin (Will turn on an LED correctly connected to GPIO18)

Note that bootcode.bin is not required for RPi 4 because it is included in the [EEPROM](https://www.raspberrypi.org/documentation/hardware/raspberrypi/booteeprom.md) 


## RPi 3B+
### RPi 3B+ Material
- micro USB Type-B (male) to USB Type-A (male) 2.5A power supply
- micro SD card (8GB or more)
- micro SD card adapter for computer
- breadboard
- a few LEDs 
- a few resistors (47Ω or more)
- a few cables to connect from GPIO pins (female) to the breadboard (male)
- electronic buttons (for the I/O labs)
- HDMI (male) adapter to computer lab screens (normally DVI)

### RPi 3B+ micro SD card files
- [start.elf](https://github.com/raspberrypi/firmware/blob/master/boot/start.elf)
- [bootcode.bin](https://github.com/raspberrypi/firmware/blob/master/boot/bootcode.bin)
- [kernel.img](2B-3B-3Bplus/kernel.img) - Writes 1 to GPIO18 pin (Will turn on an LED correctly connected to GPIO18)


## RPi 3B
### RPi 3B Material
 - Same as RPi 3B+

### RPi 3B micro SD card files
- [start.elf](https://github.com/raspberrypi/firmware/blob/master/boot/start.elf)
- [bootcode.bin](https://github.com/raspberrypi/firmware/blob/master/boot/bootcode.bin)
- [kernel.img](2B-3B-3Bplus/kernel.img) - Writes 1 to GPIO18 pin (Will turn on an LED correctly connected to GPIO18)


## RPi 2B v1.2
### RPi 2B v1.2 Material
- micro USB Type-B (male) to USB Type-A (male) 1.8A power supply
- micro SD card (8GB or more)
- micro SD card adapter for computer
- breadboard
- a few LEDs 
- a few resistors (47Ω or more)
- a few cables to connect from GPIO pins (female) to the breadboard (male)
- electronic buttons (for the I/O labs)
- HDMI (male) adapter to computer lab screens (normally DVI)


### RPi 2B v1.2 SD card files
- [start.elf](https://github.com/raspberrypi/firmware/blob/master/boot/start.elf)
- [bootcode.bin](https://github.com/raspberrypi/firmware/blob/master/boot/bootcode.bin)
- [kernel.img](2B-3B-3Bplus/kernel.img) - Writes 1 to GPIO18 pin (Will turn on an LED correctly connected to GPIO18)


## First steps
The first step is to check that you circuit works. 
Wire your circuit, put the provided files in the SD card, and power your RPi.
If the LED connected to GPIO18 turns on, your can continue with the lab.
If not, check if you are doing some of the typical errors:

- Wrong format of the SD card
- Wrong files in the SD card
- LED wrong connection (reversed polarity)
- Wrong wiring
- Wrong GPIO connected

### SD card format
If the SD card doesn't have a FAT32 bootable partition, it won't work.

- 1 single partition
- FAT32
- Bootable partition


## Compiler

We will use the ARM assembly compiler [FASMARM](http://arm.flatassembler.net/) running under GNU/Linux, and windows.


### GNU/Linux
You can use the binary from the [full package](http://arm.flatassembler.net/FASMARM_full.ZIP) download, or use the binary provided in this [repo](Compiler/fasmarm). 
To compile your code execute the following command:

`./fasmarm test_RPI.asm `

It will generate a binary file if it compiles without any errors.
No compilation errors are indicated like this:

```
flat assembler for ARM  version 1.43 (built on fasm 1.73.02)  (16384 kilobytes memory)
1 passes, 36 bytes.
```

### macOS
[Wine](https://www.winehq.org/) is probably the best option.
