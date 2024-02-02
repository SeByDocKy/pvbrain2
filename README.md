# PVbrainV2

__PVbrainV2__ is an open source/openhardware project to monitor/control __simultaneously__ multiple inverters (PIPsolar/Voltronic, Deye, Growatt, Sofar, Victron)  and multiple BMS (JKBMS/AntBMS/DalyBMS). It also adds the possibility of controlling up to 32 relays allowing for example to control an Automatic Transfer Switch (ATS) (Offgrid<=>return to the network). The PCB uses only crossover components or pluggable components in order to have easy setup/maintenance. The MCU used is an ESP32S3 running ESPhome allowing communication over WiFi to Home Assistant (HA) natively (but MQTT can be added easily). The main features are:

- Direct communication and control with Voltronic/Pipsolar, DEYE, SOFAR, GROWATT inverters via direct Ethernet cable __ (pvbrain has a built-in RS232 and RS485  => TTL). The VEdirect for VICTRON models with an insulated adapter provided. . Important settings can be set directly from HA (or the web server if enabled)
- Monitor multiple BMS (tested with JKBMS but should work with antBMS or daly)
- Detect multiple AC sources  (solar/network/other) (in order for example to do soft switching for the ATS part)
- Monitor _via_ a JSY193,JSY194 module (modbus) solar and network production
- Control up to 32xrelays, _that is_ for ATS control or the reversing mode of a modern inverter (Axpert max I & II for example)
- Monitor your basement temperature/humidity/pressure (you can set up alarms just in case)
- Free I2C ports available for plugging in additional I2C sensors
- SPI port is also available

This PCB uses the excellent ESPhome integrations done by @syssi available at [https://github.com/syssi](https://github.com/syssi).
The PVbrain represents a joint work between e-2-nomy [https://www.youtube.com/c/e2nomy/](https://www.youtube.com/c/e2nomy/) and Bandit-17 with the help of several members of the DISCORD group [https://reseautono.me/](https://reseautono.me/).

## __Main PCB Layout__:

![alt text](https://github.com/SeByDocKy/pvbrain2/blob/main/pictures/top%20side%20with%20wk2168.png)
![alt text](https://github.com/SeByDocKy/pvbrain2/blob/main/pictures/bottom%20side%20with%20wk2168.png)
![alt text](https://github.com/SeByDocKy/pvbrain2/blob/main/pictures/3D%20view%20with%20wk2168.png)

__Gerber files__:

Please find all gerber files required for the PCB into the following zip file:
[https://github.com/SeByDocKy/pvbrain2/tree/main/Gerber](https://github.com/SeByDocKy/pvbrain2/tree/main/Gerber)

## __additional daughter board addons__:

An optional addon card can be plugged to added more uarts 

## __Additional Additions to Daughterboard #2__:

Another complementary card was created by Dackara to allow the control of the heating radiator pilot wire

[https://github.com/Dackara/Fil_Pilote?tab=readme-ov-file](https://github.com/Dackara/Fil_Pilote?tab=readme-ov-file)
![alt text](https://github.com/Dackara/Fil_Pilote/blob/main/Image/Photo/IMG_3848.JPG)
