# IdeaHacks IOT Whiteboard

Our project for the UCLA IdeaHacks 2020 Hackathon features an IoT Whiteboard. At UCLA, each room has a whiteboard outside for students to express themselves and put up notices. Now what if you could customize that further with lights, messages, and drawings? What if you could update it from any location on campus? That forms the core of our idea — a whiteboard device where you can draw and write messages from anywhere using your mobile device.

![alt text](https://github.com/Realises/ideahacks/blob/master/WebSocket.png)

Our presentation slides for our product contain images, technical details, and our pitch to industry judges during the hackathon: https://docs.google.com/presentation/d/1oXL-UVSUKEl8SZ1EFlXJt8-8BcVPcubrDTF5FJEsTZE/edit?usp=sharing 

We used the Adafruit_SSD1306 library to create graphic images and text on the OLED. To create a websocket server and integrate HTML and CSS, we used an Arduino ESP32 filesystem uploader titled SPIFFs. Both of the READMEs and their documentation can be found below.


# Adafruit_SSD1306 [![Build Status](https://travis-ci.org/adafruit/Adafruit_SSD1306.svg?branch=master)](https://travis-ci.org/adafruit/Adafruit_SSD1306)

This is a library for our Monochrome OLEDs based on SSD1306 drivers

  Pick one up today in the adafruit shop!
  ------> http://www.adafruit.com/category/63_98

These displays use I2C or SPI to communicate, 2 to 5 pins are required to interface.

Adafruit invests time and resources providing this open source code,
please support Adafruit and open-source hardware by purchasing
products from Adafruit!

Written by Limor Fried/Ladyada for Adafruit Industries, with contributions from the open source community. Scrolling code contributed by Michael Gregg. Dynamic buffer allocation based on work by Andrew Canaday.
BSD license, check license.txt for more information. All text above must be included in any redistribution

Preferred installation method is to use the Arduino IDE Library Manager. To download the source from Github instead, click "Clone or download" above, then "Download ZIP." After uncompressing, rename the resulting folder Adafruit_SSD1306. Check that the Adafruit_SSD1306 folder contains Adafruit_SSD1306.cpp and Adafruit_SSD1306.h.

You will also have to install the **Adafruit GFX library** which provides graphics primitves such as lines, circles, text, etc. This also can be found in the Arduino Library Manager, or you can get the source from https://github.com/adafruit/Adafruit-GFX-Library

## Changes
Pull Request:
   (September 2019) 
   * new #defines for SSD1306_BLACK, SSD1306_WHITE and SSD1306_INVERSE that match existing #define naming scheme and won't conflict with common color names
   * old #defines for BLACK, WHITE and INVERSE kept for backwards compat (opt-out with #define NO_ADAFRUIT_SSD1306_COLOR_COMPATIBILITY)

Version 1.2 (November 2018) introduces some significant changes:

  * Display dimensions are now specified in the constructor...you no longer need to edit the .h file for different screens (though old sketches can continue to work that way).
  * SPI transactions are used and SPI bitrate can be specified (both require Arduino 1.6 or later).
  * SPI and Wire (I2C) interfaces other than the defaults are supported.

<!-- START COMPATIBILITY TABLE -->

## Compatibility

MCU         |Tested Works|Doesn't Work|Not Tested|Notes
------------|:----------:|:----------:|:--------:|-----
Atmega328   |      X     |            |          |
Atmega32u4  |      X     |            |          |
Atmega2560  |      X     |            |          |
ESP8266     |      X     |            |          | Change OLED_RESET to different pin if using default I2C pins D4/D5.
ESP32       |      X     |            |          |
ATSAM3X8E   |      X     |            |          |
ATSAM21D    |      X     |            |          |
Intel Curie |      X     |            |          |
WICED       |      X     |            |          | No hardware SPI - bitbang only
ATtiny85    |            |      X     |          |

  * ATmega328 : Arduino UNO, Adafruit Pro Trinket, Adafruit Metro 328, Adafruit Metro Mini
  * ATmega32u4 : Arduino Leonardo, Arduino Micro, Arduino Yun, Teensy 2.0, Adafruit Flora, Bluefruit Micro
  * ATmega2560 : Arduino Mega
  * ESP8266 : Adafruit Huzzah
  * ATSAM3X8E : Arduino Due
  * ATSAM21D : Arduino Zero, M0 Pro, Adafruit Metro Express, Feather M0
  * ATtiny85 : Adafruit Gemma, Arduino Gemma, Adafruit Trinket

<!-- END COMPATIBILITY TABLE -->

# Arduino ESP32 filesystem uploader (SPIFFS)

Arduino plugin which packs sketch data folder into SPIFFS filesystem image,
and uploads the image to ESP32 flash memory.

## Installation

- Make sure you use one of the supported versions of Arduino IDE and have ESP32 core installed.
- Download the tool archive from [releases page](https://github.com/me-no-dev/arduino-esp32fs-plugin/releases/latest).
- In your Arduino sketchbook directory, create tools directory if it doesn't exist yet.
- Unpack the tool into tools directory (the path will look like ```<home_dir>/Arduino/tools/ESP32FS/tool/esp32fs.jar```).
- Restart Arduino IDE. 

On the OS X create the tools directory in ~/Documents/Arduino/ and unpack the files there

## Usage

- Open a sketch (or create a new one and save it).
- Go to sketch directory (choose Sketch > Show Sketch Folder).
- Create a directory named `data` and any files you want in the file system there.
- Make sure you have selected a board, port, and closed Serial Monitor.
- Select *Tools > ESP32 Sketch Data Upload* menu item. This should start uploading the files into ESP32 flash file system.

  When done, IDE status bar will display SPIFFS Image Uploaded message. Might take a few minutes for large file system sizes.

## Credits and license

- Copyright (c) 2015 Hristo Gochkov (hristo at espressif dot com)
- Licensed under GPL v2 ([text](LICENSE))
- Maintained by Hristo Gochkov (hristo at espressif dot com)

## Issues and suggestions

File issues here on github, or ask your questions on the [esp32.com forum](http://esp32.com).

