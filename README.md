## Black Magic Probe Firmware for STM32
It contains the pre-compiled Black Magic Probe firmware for [STM32f103 Boards](https://wiki.stm32duino.com/index.php?title=Blue_Pill) which can be easily uploaded with any USB-to-Serial converter. 

**The author assumes that Python is already installed in the user's system.**

## How to flash?
Just follow the simple steps:

### Step 1:
Connect USB-to-Serial Converter with the Blue-Pill board as show [here](http://grauonline.de/wordpress/wp-content/uploads/arduino_stm32f103c8t6.jpg) or [here](https://www.14core.com/wp-content/uploads/2016/02/Using-TTL-UART-ARM-STM32F-Flashing-Programming-Manual-Diagram-ARM.jpg). Set `BOOT0` jumper on the board to `1` and press **reset**.

Also, download this repository in the desired location.

### Step 2:
##### Linux
Open Terminal and run:`sudo python stm32loader.py -p /dev/ttyUSB0 -e -w -v -g 0x0 bmp.bin`

##### Windows
Open Command Window and run:`python stm32loader.py -p COM2 -e -w -v -g 0x0 bmp.bin`

The Ouput should look something like this:
```
Bootloader version 22
Chip id: 0x410 (STM32 Medium-density)
Write 256 bytes at 0x8000000
Write 256 bytes at 0x8000100
Write 256 bytes at 0x8000200
.
.
.
[snip]
Write 256 bytes at 0x8013500
Read 256 bytes at 0x8000000
Read 256 bytes at 0x8000100
Read 256 bytes at 0x8000200
.
.
.
[snip]
Read 256 bytes at 0x8013400
Read 256 bytes at 0x8013500
Verification OK

```
If you see this, you are done !! Cheers! :beers: :wink:

Plug out the Serial Converter and plug the Blue-Pill Board with the native USB.
