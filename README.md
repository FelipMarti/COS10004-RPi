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


## RPi 4B SD card files
- [start4.elf](https://github.com/raspberrypi/firmware/blob/master/boot/start4.elf)
- [kernel.img](4B/kernel.img) - Writes 1 to the GPIO18 pin (Will turn on an LED correctly connected to GPIO18)

Note that bootcode.bin is not required for RPi 4 because it is included in the [EEPROM](https://www.raspberrypi.org/documentation/hardware/raspberrypi/booteeprom.md) 

## RPi 3B+ SD card files
- [start.elf](https://github.com/raspberrypi/firmware/blob/master/boot/start.elf)
- [bootcode.bin](https://github.com/raspberrypi/firmware/blob/master/boot/bootcode.bin)
- [kernel.img]() - Writes 1 to the GPIO18 pin (Will turn on an LED correctly connected to GPIO18)

## RPi 3B SD card files
- [start.elf](https://github.com/raspberrypi/firmware/blob/master/boot/start.elf)
- [bootcode.bin](https://github.com/raspberrypi/firmware/blob/master/boot/bootcode.bin)
- [kernel.img]() - Writes 1 to the GPIO18 pin (Will turn on an LED correctly connected to GPIO18)

## RPi 2B v1.2 SD card files
- [start.elf](https://github.com/raspberrypi/firmware/blob/master/boot/start.elf)
- [bootcode.bin](https://github.com/raspberrypi/firmware/blob/master/boot/bootcode.bin)
- [kernel.img]() - Writes 1 to the GPIO18 pin (Will turn on an LED correctly connected to GPIO18)


