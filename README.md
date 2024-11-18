# 4heat-esphome-NG21
4heat-esphome NG21 board YAML setup

This is a simple YAML file meant to use with https://github.com/leoshusar/4heat-esphome ESPHome integration specifically for Tiemme NG21 boards. There are added specific datapoints according NG21 specifications that differ from leoshusar initial setup.

### Usage

This is ESPHome yaml file. To use it you have to use ESP8266 or ESP32 board and additional hardware according to istructions. It is possible that it will work with some other board but it has been tested with this two.

### Hardware

You need a ESP8266 or ESP32 board, an RS232 to TTL board and some sort of rs232 connector/adapter. It is possible to use any appropriate board but then you have to change wiring on board side. Fireplace should allow you to use RS 232 pin 1-4 for communication.

![](hardware.png)

### Software

### buffer_thermostat_threshold and buffer_target_temperature

Threshold or also hysteresis is regulating buffer temperature range when actually fireplace is switched back on. All NG21 boards have similar options but how the manufacturer uses them is different. When you dont use buffer you should remove those 2 options from yaml.

### Night Mode

When u already have night mode in menu u do not need this part of yaml.
The way how this works is you will have additional switch to turn night mode in menu on. When you use it you will have in your stove factory remote/menu settings new item “Night mode”. Find it there, and you can use it exactly like stove Timer menu. I also added under same switch power reduction to P3 level so this will as long as the switch is ON additionally reduce noise levels.
The way how I personally use this, is to create additional automation in HA to turn this switch on so, that in quiet time the stove is in addition to night mode also in half power.
Of course if someone does not like that you can always remove that part. 
Do not use Night Mode 24/7 all time! It switches off cleaning engine and some other noisy stuff so without no cleaning at all in long run, it would probably not be healthy for you stove.

