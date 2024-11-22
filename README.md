# 4heat-esphome-NG21
4heat-esphome NG21 board YAML setup

This is a simple YAML file meant to use with https://github.com/leoshusar/4heat-esphome ESPHome integration specifically for Tiemme NG21 boards. There are added specific datapoints according NG21 specifications that differ from leoshusar initial setup.

### Usage

This is ESPHome yaml file. To use it you have to use ESP8266 or ESP32 board and additional hardware according to istructions. It is possible that it will work with some other boards but it has been tested only with this two. You are fully responsible for any changes to your fireplace hardware or software that you intend to make herewith and for all risks involved.

### Hardware

You need a ESP8266 or ESP32 board, an RS232 to TTL board and some sort of rs232 connector/adapter. It is possible to use any appropriate board but then you have to change wiring on board side. Fireplace should allow you to use RS 232 pin 1-4 for communication.

![](hardware.png)

### Software

### buffer_thermostat_threshold and buffer_target_temperature

Threshold or also called hysteresis is regulating buffer temperature range when actually fireplace is switched back on. Need for that depends actually how big your buffer is. All NG21 boards have similar options but how the manufacturer uses them is different. When you dont use buffer you should remove those 2 options from yaml.

### Night Mode

When you already have night mode in the menu you do not need this part of yaml.
The way how this works is, you will have additional switch to turn night mode in menu on. When you use it you will have in your stove factory remote/menu settings new item “Night mode”. Find it there, and you can use it exactly like stove "Timer" menu. I also added under same switch power reduction to P3 level so this will as long as the switch is ON additionally reduce noise levels.
The way how I personally use this, is to create additional automation in HA to turn this switch on so, that in quiet time the stove is in addition to night mode also in half power.
Of course if someone does not like that you can always remove that part. 
Do not use Night Mode 24/7 all time! It switches off cleaning engine and some other noisy stuff so without no cleaning at all in long run, it would probably not be healthy for you stove.

### combi

This allows to switch between pellet and wood option. To use this uncomment "combi" block. Or if your freplace dont have this option, cleanup. 
!!! This function has not been tested!!!  My fireplace does not have this.

### Other datapoints

By the papers I have there is theoretically possible to add additional datapoints but those are mostly related to factory setup and do not add any additional user comfort. Unfortunately all passive sensors, (like temperature, pumps and motors) are possible to find only with communication sniffing. When somebody does that for NG21 those can be additionaly added to this yaml.

