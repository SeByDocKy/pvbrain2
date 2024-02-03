[![Static Badge](https://img.shields.io/badge/Realease-Beta-blue?style=plastic)](https://github.com/SeByDocKy/pvbrain2)

# PVbrainV2

> [!IMPORTANT]
> [![Static Badge](https://img.shields.io/badge/PvBrain-v2.0-black?style=social&logo=quasar)](https://github.com/SeByDocKy/pvbrain2) is an open source/openhardware project to monitor/control __`SIMULTANEOUSLY`__ multiple inverters (PIPsolar/Voltronic, Deye, Growatt, Sofar, Victron) and multiple BMS (JKBMS/AntBMS/DalyBMS). 
> 
> It also adds the possibility of controlling up to 32 relays allowing for example to control an Automatic Transfer Switch (ATS) (Offgrid<=>return to the network). 
> 
> The PCB uses only crossover components or pluggable components in order to have easy setup/maintenance. 
> 
> The MCU used is an [ESP32S3](https://s.click.aliexpress.com/e/_DCEPtOd) running [![Static Badge](https://img.shields.io/badge/ESPHome-_-black?logo=esphome&style=social)](https://esphome.io) allowing communication over WiFi to [![Static Badge](https://img.shields.io/badge/Home_Assistant-_-black?logo=homeassistant&style=social)](http://homeassistant.io) (HA) natively (but MQTT can be added easily). The main features are:


> [!TIP]
> - Direct communication and control with Voltronic/Pipsolar, DEYE, SOFAR, GROWATT inverters via direct Ethernet cable __ (pvbrain has a built-in [RS232](https://a.aliexpress.com/_EzMcqvP) and [RS485](https://a.aliexpress.com/_EzS7TkZ)  => TTL). The VEdirect for VICTRON models with an insulated adapter provided. . Important settings can be set directly from HA (or the web server if enabled)
> - Monitor multiple BMS (tested with JKBMS but should work with antBMS or daly) with an insulated adapter provided.
> - Detect multiple AC sources  (solar/network/other) (in order for example to do soft switching for the ATS part)
> - Monitor _via_ a [JSY193](https://a.aliexpress.com/_EyMD1XJ), [JSY194T](https://a.aliexpress.com/_EHWOhZb) module (modbus) solar and network production
> - Control up to 32x relays with two i2c extension [SX1509](https://esphome.io/components/sx1509), _that is_ for ATS control or the reversing mode of a modern inverter (Axpert max I & II for example)
> - The solar router function with [ROBOTDYN](https://a.aliexpress.com/_EwiP2jL) or [SSR](https://a.aliexpress.com/_EyikzBP) controlled in PWM
> - Monitor your basement temperature/humidity/pressure with [BME280](https://esphome.io/components/sensor/bme280) (you can set up alarms just in case)
> - Free I2C ports available for plugging in additional I2C sensors
> - SPI port is also available

> [!NOTE]
> This PCB uses the excellent ESPhome integrations done by :
> - [![Static Badge](https://img.shields.io/badge/Syssi-black?logo=git&style=flat)](https://github.com/syssi)
> - [![Static Badge](https://img.shields.io/badge/DrCoolZic-black?logo=git&style=flat)](https://github.com/DrCoolzic) (Expansion cards [WK2132](https://www.dfrobot.com/product-2001.html) and [WK2168](https://github.com/SeByDocKy/pvbrain2/blob/main/pictures/top%20side%20WK2168.png) ).
> 
> The __PVbrain__ represents a joint work between [![Static Badge](https://img.shields.io/badge/SeByDocKy-black?logo=git&style=flat)](https://github.com/SeByDocKy) of the [![Static Badge](https://img.shields.io/badge/Youtube-e--2--nomy-black?style=social&logo=youtube)](https://www.youtube.com/@e2nomy) and [![Static Badge](https://img.shields.io/badge/Bandit--17-black?logo=git&style=flat)](https://github.com/Bandit-17).
> - With the help of several members of the [![Static Badge](https://img.shields.io/badge/DISCORD-Reseautonome-black?style=social&logo=discord)](https://reseautono.me/).

# Main PCB Layout:

| Front                     | Back                      |
| :-----------------------: | :-----------------------: |
| <img src="https://github.com/SeByDocKy/pvbrain2/blob/main/pictures/top%20side%20with%20wk2168.png" width="1068" /> | <img src="https://github.com/SeByDocKy/pvbrain2/blob/main/pictures/bottom%20side%20with%20wk2168.png" width="1068" /> |

| 3D View |
| :-----------------------: |
|<img src="https://github.com/SeByDocKy/pvbrain2/blob/main/pictures/3D%20view%20with%20wk2168.png" width="480" /> |

## Gerber files:

Please find all gerber files required for the PCB into the following zip file:
[Gerber](https://github.com/SeByDocKy/pvbrain2/tree/main/hardware/Gerber)

# Additional daughter boards addons:

## UART Extension Module:
An optional addon card can be plugged to added more UARTs 
| 3D View |
| :-----------------------: |
|<img src="https://github.com/SeByDocKy/pvbrain2/blob/main/pictures/UART%20EXTENSION%20MODULE.PNG" width="480" /> |

## Fil_Pilote:
Another complementary card was created by [![Static Badge](https://img.shields.io/badge/Dackara-black?logo=git&style=flat)](https://github.com/Dackara) to allow the control of the heating radiator pilot wire and communication with Linky meters.

Link to the Github Page: [![Static Badge](https://img.shields.io/badge/Dackara-Fil__Pilote-black?style=social&logo=quasar)](https://github.com/Dackara/Fil_Pilote)

| 3D View | Photography |
| :-----------------------: | :-----------------------: |
| <img src="https://github.com/Dackara/Fil_Pilote/blob/main/Image/3D_View.png" width="1068" /> | <img src="https://github.com/Dackara/Fil_Pilote/blob/main/Image/Photo/IMG_3848.JPG" width="1068" /> |