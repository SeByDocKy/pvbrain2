![Static Badge](https://img.shields.io/badge/Work_In_Progress-Project_still_in_development-red?logo=adblock&logoColor=red&style=plastic)
[![Static Badge](https://img.shields.io/badge/Realease-Beta-blue?style=plastic)](https://github.com/SeByDocKy/pvbrain2)

# PVbrainV2

> [!IMPORTANT]
> [![Static Badge](https://img.shields.io/badge/PvBrain-v2.0-black?style=social&logo=quasar)](https://github.com/SeByDocKy/pvbrain2) is an open source/openhardware project to monitor/control __`SIMULTANEOUSLY`__ multiple inverters (PIPsolar/Voltronic, Deye, Growatt, Sofar, Victron) and multiple BMS (JKBMS/AntBMS/DalyBMS). 
> 
> It also adds the possibility of controlling up to 32 relays allowing for example to control an Automatic Transfer Switch (ATS) (Offgrid<=>return to the network). 
> 
> The PCB uses only crossover components or pluggable components in order to have easy setup/maintenance. 
> 
> The MCU used is an [ESP32S3](https://s.click.aliexpress.com/e/_DCEPtOd) running [![Static Badge](https://img.shields.io/badge/ESPHome-_-black?logo=esphome&style=social)](https://esphome.io) allowing communication over WiFi to [![Static Badge](https://img.shields.io/badge/Home_Assistant-_-black?logo=homeassistant&style=social)](http://homeassistant.io) (HA) natively (but MQTT can be added easily). 
> 
> __The main features are :__
> - Direct communication and control with Voltronic/Pipsolar, DEYE, SOFAR, GROWATT inverters via direct Ethernet cable (pvbrain has a built-in [RS232](https://a.aliexpress.com/_EzMcqvP) and [RS485](https://a.aliexpress.com/_EzS7TkZ)  => TTL). 
> - The VEdirect for VICTRON models with an insulated adapter provided. 
> - Important settings can be set directly from HA (or the web server if enabled).
> - Monitor multiple BMS (tested with JKBMS but should work with antBMS or daly) with an insulated adapter provided.
> - Detect multiple AC sources  (solar/network/other) (in order for example to do soft switching for the ATS part).
> - Monitor _via_ a [JSY193](https://a.aliexpress.com/_EyMD1XJ), [JSY194T](https://a.aliexpress.com/_EHWOhZb) module (modbus) solar and network production.
> - Control up to 32x relays with two i2c extension [SX1509](https://esphome.io/components/sx1509), _that is_ for ATS control or the reversing mode of a modern inverter (Axpert max I & II for example).
> - The solar router function with [ROBOTDYN](https://a.aliexpress.com/_EwiP2jL) or [SSR](https://a.aliexpress.com/_EyikzBP) controlled in PWM.
> - Monitor your basement temperature/humidity/pressure with [BME280](https://esphome.io/components/sensor/bme280) (you can set up alarms just in case).
> - Free I2C ports available for plugging in additional I2C sensors.
> - SPI port is also available.

> [!NOTE]
> This PCB uses the excellent ESPhome integrations done by :
> - [![Static Badge](https://img.shields.io/badge/Syssi-black?logo=git&style=flat)](https://github.com/syssi) (Many BMS and inverter).
> - [![Static Badge](https://img.shields.io/badge/DrCoolZic-black?logo=git&style=flat)](https://github.com/DrCoolzic) (Expansion cards [WK2132](https://www.dfrobot.com/product-2001.html) and [WK2168](../main/hardware/module_wk_2168/wk2168_3d_view.png) ).
> 
> The __PVbrain__ represents a joint work between [![Static Badge](https://img.shields.io/badge/SeByDocKy-black?logo=git&style=flat)](https://github.com/SeByDocKy) of the [![Static Badge](https://img.shields.io/badge/Youtube-e--2--nomy-black?style=social&logo=youtube)](https://www.youtube.com/@e2nomy) and [![Static Badge](https://img.shields.io/badge/Bandit--17-black?logo=git&style=flat)](https://github.com/Bandit-17).
> - With the help of several members of the [![Static Badge](https://img.shields.io/badge/DISCORD-Reseautonome-black?style=social&logo=discord)](https://reseautono.me/).

# Main PCB Layout :

| Front                     | Back                      |
| :-----------------------: | :-----------------------: |
| <img src="../main/hardware/pvbrain_v2/pvbrain_v2_front.png" width="1068" /> | <img src="../main/hardware/pvbrain_v2/pvbrain_v2_back.png" width="1068" /> |
| 3D View                   | Circuit                   |
|<img src="../main/hardware/pvbrain_v2/pvbrain_v2_3d_view.png" width="1068" /> | <img src="../main/hardware/pvbrain_v2/pvbrain_v2_circuit.png" width="1068" /> |
| Schematic                 | Schematic                 |
|<img src="../main/hardware/pvbrain_v2/pvbrain_v2_schematic_sheet1.png" width="1068" /> | <img src="../main/hardware/pvbrain_v2/pvbrain_v2_schematic_sheet2.png" width="1068" /> |

## Gerber files :

Please find all Gerber files required for the PCB in the following folder : [__Hardware__](../main/hardware).

# DIY module :
Special clip-on modules were created by [![Static Badge](https://img.shields.io/badge/Bandit--17-black?logo=git&style=flat)](https://github.com/Bandit-17) for use (or not) with the PVbrain.

## [WK 2168 :](../main/hardware/module_wk_2168)
Module to extend the number of uarts on an esp32 (4 Uarts per card) possibility of communicating in I2C or SPI.
| 3D View                   | Schematic                 |
| :-----------------------: | :-----------------------: |
| <img src="../main/hardware/module_wk_2168/wk2168_3d_view.png" width="700" /> | <img src="../main/hardware/module_wk_2168/wk2168_schematic.png" width="1068" /> |

| Front                     | Back                      | Circuit                   |
| :-----------------------: | :-----------------------: | :-----------------------: |
|<img src="../main/hardware/module_wk_2168/wk2168_front.png" width="1068" /> | <img src="../main/hardware/module_wk_2168/wk2168_back.png" width="1068" /> | <img src="../main/hardware/module_wk_2168/wk2168_circuit.png" width="1068" /> |

## [WK 2132 :](../main/hardware/module_wk_2132)
Before discovering the WK2168 module which allowed the creation of the card above, a DIY version of the DFRobot [DFR0627](https://www.dfrobot.com/product-2001.html) had been designed. Its cost is a little lower than its big brother the WK2168, but it only allows 2 additional UARTs.
| 3D View                   |
| :-----------------------: |
|<img src="../main/hardware/module_wk_2132/wk2132_3d_view.png" width="280" /> |

## [UART Isolator :](../main/hardware/module_uart_isolator)
TTL isolator, originally designed for VictronVE direct.
- With the participation of [![Static Badge](https://img.shields.io/badge/Luc-black?logo=discord&style=flat)](https://reseautono.me/), [![Static Badge](https://img.shields.io/badge/Ju__Workshop-black?logo=discord&style=flat)](https://reseautono.me/) and [![Static Badge](https://img.shields.io/badge/Cristof48-black?logo=discord&style=flat)](https://reseautono.me/) of the [![Static Badge](https://img.shields.io/badge/DISCORD-Reseautonome-black?style=social&logo=discord)](https://reseautono.me/).

| 3D View                   | Schematic                 |
| :-----------------------: | :-----------------------: |
|<img src="../main/hardware/module_uart_isolator/uart_isolator_3d_view.png" width="780" /> | <img src="../main/hardware/module_uart_isolator/uart_isolator_schematic.png" width="480" /> |

| Front                     | Back                      | Circuit                   |
| :-----------------------: | :-----------------------: | :-----------------------: |
| <img src="../main/hardware/module_uart_isolator/uart_isolator_front.png" width="1068" /> | <img src="../main/hardware/module_uart_isolator/uart_isolator_back.png" width="1068" /> | <img src="../main/hardware/module_uart_isolator/uart_isolator_circuit.png" width="1068" /> |

## [Shunt TTL :](../main/hardware/module_shunt_ttl)
Simple Shunt for Direct UART output.
| Front                     | 3D View                   |
| :-----------------------: | :-----------------------: |
| <img src="../main/hardware/module_shunt_ttl/shunt_ttl_front.png" width="1068" /> | <img src="../main/hardware/module_shunt_ttl/shunt_ttl_3d_view.png" width="1068" /> |


# Additional daughter boards addons:

## [UART Extension Module :](../main/hardware/addon_carte_uart_extension)
An optional addon card can be plugged to allowing 4 additional UART outputs.
| Front                     | Back                      |
| :-----------------------: | :-----------------------: |
| <img src="../main/hardware/addon_carte_uart_extension/uart_extension_front.png" width="1068" /> | <img src="../main/hardware/addon_carte_uart_extension/uart_extension_back.png" width="1068" /> |
| 3D View                   | Circuit                   |
|<img src="../main/hardware/addon_carte_uart_extension/uart_extension_3d_view.png" width="1068" /> | <img src="../main/hardware/addon_carte_uart_extension/uart_extension_circuit.png" width="1068" /> |

## [PV Monitor :](../main/hardware/addon_carte_pv_monitor)
Addon card created for [PVbrain V1](https://github.com/Bandit-17/PVBRAIN) by [![Static Badge](https://img.shields.io/badge/Bandit--17-black?logo=git&style=flat)](https://github.com/Bandit-17) and re-designed by [![Static Badge](https://img.shields.io/badge/Dackara-black?logo=git&style=flat)](https://github.com/Dackara) in this V2.

The card offers the possibility of securely monitoring the voltage of two DC inputs.
| Front                     | Back                      |
| :-----------------------: | :-----------------------: |
| <img src="../main/hardware/addon_carte_pv_monitor/pv_monitor_front.png" width="1068" /> | <img src="../main/hardware/addon_carte_pv_monitor/pv_monitor_back.png" width="1068" /> |
| 3D View                   | Circuit                   |
|<img src="../main/hardware/addon_carte_pv_monitor/pv_monitor_3d_view.png" width="1068" /> | <img src="../main/hardware/addon_carte_pv_monitor/pv_monitor_circuit.png" width="1068" /> |

## [Fil_Pilote :](../main/hardware/addon_carte_fil_pilote)
A complementary card was created by [![Static Badge](https://img.shields.io/badge/Dackara-black?logo=git&style=flat)](https://github.com/Dackara) to allow the control of the heating radiator pilot wire and communication with Linky meters.

Link to the Github Page: [![Static Badge](https://img.shields.io/badge/Dackara-Fil__Pilote-black?style=social&logo=Github)](https://github.com/Dackara/Fil_Pilote)

| 3D View | Photography |
| :-----------------------: | :-----------------------: |
| <img src="https://github.com/Dackara/Fil_Pilote/blob/main/Image/3D_View.png" width="1068" /> | <img src="https://github.com/Dackara/Fil_Pilote/blob/main/Image/Photo/IMG_3848.JPG" width="1068" /> |

## [Clamp_Meter :](../main/hardware/addon_carte_clamp_meter)
Another option card created by [![Static Badge](https://img.shields.io/badge/Dackara-black?logo=git&style=flat)](https://github.com/Dackara) to monitor the passage of current through the clamps.
- 1 to 16 Clamp (2 mounting possible for each output : JST-XH for [2-strand clamp](https://s.click.aliexpress.com/e/_De0j7rx) or Jack for [SCT013](https://s.click.aliexpress.com/e/_DFRTWIN))
- 1 to 4 pre-addressed [ADS1115](https://s.click.aliexpress.com/e/_DF9geSz).
- 1 [TCA9548A](https://s.click.aliexpress.com/e/_DDACktb) (optional - bridging if not used) to multiplex the I2C (useful in the event of more than 4 ADS or I2C address conflict) with all its outputs remote for external use.
- 1 ESP possible at input for non-PVbrain users or other reasons... 6 assembly possible: (offset of all outputs and recovery of i2c via bridging).
  - [ESP8266 D1 Mini](https://s.click.aliexpress.com/e/_DmbvqH7)
  - [ESP32 D1 Mini](https://s.click.aliexpress.com/e/_DEU8tVB)
  - [ESP32 S2 Mini](https://s.click.aliexpress.com/e/_DdgwMVF)
  - [ESP32 C3](https://s.click.aliexpress.com/e/_DFystRx)
  - [ESP32 C3 Zero](https://s.click.aliexpress.com/e/_DeIlFtn)
  - [ESP32 S3 Zero](https://s.click.aliexpress.com/e/_DeIlFtn)
  
Link to the Github Page: [![Static Badge](https://img.shields.io/badge/Dackara-Clamp__Meter-black?style=social&logo=Github)](https://github.com/Dackara/Clamp_Meter) (Still in development)

| 3D View                   | Circuit                   |
| :-----------------------: | :-----------------------: |
|<img src="../main/hardware/addon_carte_clamp_meter/clamp_meter_3d_view.png" width="1068" /> | <img src="../main/hardware/addon_carte_clamp_meter/clamp_meter_circuit.png" width="1068" /> |

## [Protoboard :](../main/hardware/addon_carte_prototype)
Just a prototyping board with the same footprint as the other addon boards.
| Front                     |
| :-----------------------: |
|<img src="../main/hardware/addon_carte_prototype/carte_prototype_front.png" width="480" /> |

## [3D print DIN mount :](../main/hardware/printable_3d_din_mount)
[3D Files](https://github.com/Dackara/Fil_Pilote/blob/main/Hardware/3D_Print) to print, created by [![Static Badge](https://img.shields.io/badge/Dackara-black?logo=git&style=flat)](https://github.com/Dackara), for mounting addon cards on DIN rail (electrical panel).
| Front View                | Back View                 |
| :-----------------------: | :-----------------------: |
| <img src="../main/hardware/printable_3d_din_mount/3d_din_mount_front.png" width="880" /> | <img src="../main/hardware/printable_3d_din_mount/3d_din_mount_back.png" width="1068" /> |

## ["Carte Option 2" :](../main/hardware/addon_carte_old_option2)
The old "Option 2" card made by [![Static Badge](https://img.shields.io/badge/Luc-black?logo=discord&style=flat)](https://reseautono.me/) for the [PVbrain V1](https://github.com/Bandit-17/PVBRAIN) is also compatible with the PVbrain V2.
| 3D View                   |
| :-----------------------: |
|<img src="../main/hardware/addon_carte_old_option2/carte_option2_3d_view.png" width="480" /> |
