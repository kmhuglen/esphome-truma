# Readme

This repository documents my ESPHome-based integration for a Truma Combi 6E setup in my RV.

ESPHome YAML file: [esphome-supermini.yml](esphome-supermini.yml)

The configuration is based on https://github.com/havanti/esphome-truma and adapted for an ESP32-C6 SuperMini with a UART-to-LIN interface.


## Wiring Diagram

[esphome-truma-wiring.drawio](esphome-truma-wiring.drawio)
![ESPHome Truma wiring](images/esphome-truma-wiring.svg)

| PIN to PIN | Wire |
| --- | --- |
DC/DC Converter USB-C <-> ESP32 USB-C | USB Cable
DC/DC Converter - (Black) <-> LIN BUS GND | Black wire (screw)
DC/DC Converter + (Red) <-> LIN BUS 12V | Red wire (screw)
RV Power (Black) <-> LIN BUS GND | Black wire (screw)
RV Power (Red) <-> LIN BUS 12V | Red wire (screw)
Truma RJ12 PIN4 <-> LIN BUS LIN | Yellow wire (screw)
ESP32 GPIO-7 (TX) <-> LIN BUS RX | Blue wire (soldered on ESP32)
ESP32 GPIO-6 (RX) <-> LIN BUS TX | Green wire (soldered on ESP32)
ESP32 GND <-> LIN BUS GND | Black wire (soldered on ESP32)

## Hardware

| Device | Shop | Picture |
| --- | --- | --- |
ISDN T-Adapter RJ12 female (6P6C) | [BatteriOnline](https://www.batterionline.no/kabler-tilslutning/datakabler/internett-pc-stromkabler/isdn/isdn-t-adapter-rj12-hun-6p6c-1-pcs) | <img src="images/isdn-t-adapter-1.jpg" alt="ISDN T-Adapter image 1" width="500" /><br><img src="images/isdn-t-adapter-2.jpg" alt="ISDN T-Adapter image 2" width="500" />
RJ12 Cable 2x RJ12 male (6P6C) | [BatteriOnline](https://www.batterionline.no/kabler-tilslutning/diverse-kabler/telefonledninger/skjoteledning-6p6c/telefon-forlengerkabel-2x-rj12-han-6p6c-3m) | <img src="images/telefon-forlengerkabel.jpg" alt="RJ12 Cable" width="500" />
UART to LIN Bus Module | [AliExpress](https://www.aliexpress.com/item/1005008499687135.html) | <img src="images/usb-lin-module.avif" alt="USB to LIN Bus Module" width="500" />
ESP32-C6 SuperMini | [AliExpress](https://www.aliexpress.com/item/1005007676682081.html) | <img src="images/esp32-c6-supermini.avif" alt="ESP32-C6 SuperMini" width="500" />
12V/24V DC-DC Step Down Module USB-C | [AliExpress](https://www.aliexpress.com/item/1005007820939213.html) | <img src="images/dc-dc-adapter.avif" alt="12V/24V to 5V adapter" width="500" />
RJ12 6P6C Female Plug-In Terminal Connector | [AliExpress](https://www.aliexpress.com/item/1005009539648208.html) | <img src="images/rj12-adapter.avif" alt="RJ12 adapter" width="500" />

## Home Assistant Dashboard

The Home Assistant dashboard displays Truma room and water temperature sensors, along with an additional sensor for temperature, humidity, TVOC, and air quality at the top. Below this, the Truma controls are simplified to include only the functions I use most frequently. Using the Bluetooth proxy function of ESPHome, the dashboard also pulls in sensor data from a Skanbatt lithium battery and a Victron charger.

<img src="images/homeassistant-dashboard.png" alt="Home Assistant Dashboard" />