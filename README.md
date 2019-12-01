# TinyAVR/ATtiny

### Information of this README and comments in this project may be incorrect. This project is not an official document of Microchip Technology Inc., Atmel Corporation, and other holders of any Intellectual Property (IP).

## Purpose

* To Develop Software of TinyAVR/ATtiny Using C Language and Assembler Language

**About TinyAVR/ATtiny**

* TinyAVR/ATtiny is a family of microcontrollers. Specially, I'm trying to make software of ATtiny13 which has 8 pins.

* ATtiny13 is the simplest one. Available interfaces are PWM, ADC, GPIO, and Comparator. It also has a 8-bit timer/counter, and has a unique 9.6MHz RC oscillator which allows to make a software UART Tx with the baud rate 9600, 19200, 38400, etc.

## Installation

* Install Packages to Raspbian Buster on Raspberry Pi

```bash
# Programmer
sudo apt-get install avrdude
sudo apt-get install avrdude-doc
# Binary Utilities including GNU Assmebler
sudo apt-get install binutils-avr
# Assembler Compatible with AVRASM32
sudo apt-get install avra
# Compiler and C Library
sudo apt-get install gcc-avr
sudo apt-get install avr-libc
```

* Open /etc/avrdude.conf

```bash
sudo nano /etc/avrdude.conf
```

* Uncomment and Modify "linuxgpio" Lines as Follows

```bash
programmer
  id    = "linuxgpio";
  desc  = "Use the Linux sysfs interface to bitbang GPIO lines";
  type  = "linuxgpio";
  reset = 22;
  sck   = 23;
  mosi  = 24;
  miso  = 25;
;
```

## Technical Notes

**December 1, 2019**

* `cat /proc/cpuinfo | grep 'Model'`: Raspberry Pi 3 Model B Rev 1.2
* `lsb_release -a | grep 'Description'`: Raspbian GNU/Linux 10 (buster)
* `git --version`: git version 2.20.1
* `make --version`: GNU Make 4.2.1 Built for arm-unknown-linux-gnueabihf
* `avr-gcc --version`: avr-gcc (GCC) 5.4.0
* `avr-as --version`: GNU assembler (GNU Binutils) 2.26.20160125
* `avra --version`: AVRA: advanced AVR macro assembler Version 1.3.0 Build 1 (8 May 2010)
* `avrdude -v`: Version 6.3-20171130
* `apt-cache show avr-libc | grep 'Version'`: 1:2.0.0+Atmel3.6.1-2
* Description: Take these commands at the terminal of Raspbian I use for this project.

## Links of References

* [AVR Libc Home Page](http://www.nongnu.org/avr-libc/)

* [AVR Libc Reference Manual](https://www.microchip.com/webdoc/AVRLibcReferenceManual/index.html)

* [AVR Assembler](https://www.microchip.com/webdoc/GUID-E06F3258-483F-4A7B-B1F8-69933E029363/index.html): Assembler with the original syntax, but not GNU Assembler's syntax. Obtain the documentation of the instruction set at the preface.
