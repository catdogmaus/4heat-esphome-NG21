# 4heat-esphome-NG21
4heat-esphome NG21 board YAML setup

This is a simple YAML file meant to use with https://github.com/leoshusar/4heat-esphome ESPHome integration specifically for Tiemme NG21 boards. There are added specific datapoints according NG21 specifications that differ from leoshusar initial setup.

### Usage

This is ESPHome yaml file. To use it you have to use ESP8266 or ESP32 board and additional hardware according to istructions. It is possible that it will work with some other board but it has been tested with this two.

### Hardware

You need a ESP8266 or ESP32 board, an RS232 to TTL board and some sort of rs232 connector/adapter. It is possible to use any appropriate board but then you have to change wiring on board side. Fireplace should allow you to use RS 232 pin 1-4 for communication.

![](hardware.png)

