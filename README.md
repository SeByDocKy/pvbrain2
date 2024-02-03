# PVbrainV2

__PVbrainV2__ is an open source/openhardware project to monitor/control __simultaneously__ multiple inverters (PIPsolar/Voltronic, Deye, Growatt, Sofar, Victron)  and multiple BMS (JKBMS/AntBMS/DalyBMS). It also adds the possibility of controlling up to 32 relays allowing for example to control an Automatic Transfer Switch (ATS) (Offgrid<=>return to the network). The PCB uses only crossover components or pluggable components in order to have easy setup/maintenance. The MCU used is an ESP32S3 running ESPhome allowing communication over WiFi to Home Assistant (HA) natively (but MQTT can be added easily). The main features are:

- Direct communication and control with Voltronic/Pipsolar, DEYE, SOFAR, GROWATT inverters via direct Ethernet cable __ (pvbrain has a built-in RS232 and RS485  => TTL). The VEdirect for VICTRON models with an insulated adapter provided. . Important settings can be set directly from HA (or the web server if enabled)
- Monitor multiple BMS (tested with JKBMS but should work with antBMS or daly) with an insulated adapter provided.
- Detect multiple AC sources  (solar/network/other) (in order for example to do soft switching for the ATS part)
- Monitor _via_ a [JSY193](https://fr.aliexpress.com/item/1005006220451517.html?spm=a2g0o.productlist.main.1.78731a7aFJMRab&algo_pvid=552f0790-5e87-49c8-8cc2-274276f6b2df&algo_exp_id=552f0790-5e87-49c8-8cc2-274276f6b2df-0&pdp_npi=4%40dis%21USD%2135.69%2132.68%21%21%2135.69%2132.68%21%402101ec1f17069201312747675eceea%2112000036341169137%21sea%21US%210%21AB&curPageLogUid=saUns3hFYlyz&utparam-url=scene%3Asearch%7Cquery_from%3A&gatewayAdapt=glo2fra4itemAdapt),[JSY194T](https://fr.aliexpress.com/item/4000382480848.html?spm=a2g0o.productlist.main.1.49ae3a38yMlTmz&algo_pvid=53b28988-3d2b-4d38-93da-d7b98b42a03f&algo_exp_id=53b28988-3d2b-4d38-93da-d7b98b42a03f-0&pdp_npi=4%40dis%21EUR%2123.38%2117.38%21%21%2124.83%2118.46%21%402103252e17069202002873876e2fef%2110000001562590000%21sea%21FR%210%21AB&curPageLogUid=WCEPp2SqOtZ3&utparam-url=scene%3Asearch%7Cquery_from%3A) module (modbus) solar and network production
- Control up to 32xrelays with two i2c extension [SX1509](https://esphome.io/components/sx1509), _that is_ for ATS control or the reversing mode of a modern inverter (Axpert max I & II for example)
- The solar router function with ROBOTDYN or SSR controlled in PWM
- Monitor your basement temperature/humidity/pressure with [BME280](https://esphome.io/components/sensor/bme280) (you can set up alarms just in case)
- Free I2C ports available for plugging in additional I2C sensors
- SPI port is also available

This PCB uses the excellent ESPhome integrations done by
- @syssi available at [https://github.com/syssi](https://github.com/syssi)
- @DrCoolZic. expansion cards (WK2132 and WK2168)  [https://github.com/DrCoolzic](https://github.com/DrCoolzic).

The PVbrain represents a joint work between e-2-nomy [https://www.youtube.com/c/e2nomy/](https://www.youtube.com/c/e2nomy/) and Bandit-17
- with the help of several members of the DISCORD group [https://reseautono.me/](https://reseautono.me/).

## __Main PCB Layout__:

![alt text](https://github.com/SeByDocKy/pvbrain2/blob/main/pictures/top%20side%20with%20wk2168.png)
![alt text](https://github.com/SeByDocKy/pvbrain2/blob/main/pictures/bottom%20side%20with%20wk2168.png)
![alt text](https://github.com/SeByDocKy/pvbrain2/blob/main/pictures/3D%20view%20with%20wk2168.png)

__Gerber files__:

Please find all gerber files required for the PCB into the following zip file:
[https://github.com/SeByDocKy/pvbrain2/tree/main/Gerber](https://github.com/SeByDocKy/pvbrain2/tree/main/Gerber)

## __additional daughter board addons__:

An optional addon card can be plugged to added more UARTs 
![alt text](https://github.com/SeByDocKy/pvbrain2/blob/main/pictures/UART%20EXTENSION%20MODULE.PNG)

## __Additional Additions to Daughterboard #2__:

Another complementary card was created by @Dackara to allow the control of the heating radiator pilot wire

[https://github.com/Dackara/Fil_Pilote](https://github.com/Dackara/Fil_Pilote)
![alt text](https://github.com/Dackara/Fil_Pilote/blob/main/Image/Photo/IMG_3848.JPG)
