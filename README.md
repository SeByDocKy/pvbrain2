![Work_In_Progress](https://img.shields.io/badge/Work_In_Progress-Project_still_in_development-red?logo=adblock&logoColor=red&style=plastic)
[![Realease](https://img.shields.io/badge/Realease-v1.0.1-blue?style=plastic)](https://github.com/SeByDocKy/pvbrain2)

# PVbrainV2

![pvbrain_v2_logo](https://github.com/SeByDocKy/pvbrain2/assets/82636574/31fc03fe-0d92-4f01-9dd6-2457bfda07ad)

> [!IMPORTANT]
> <sub>[![PvBrain-v2.0](https://img.shields.io/badge/PvBrain-v2.0-black?style=social&logo=quasar)](https://github.com/SeByDocKy/pvbrain2)</sub> is an open source/openhardware project to monitor/control __`SIMULTANEOUSLY`__ :
> - Multiple inverters. <sup>`(PIPsolar/Voltronic, Deye, Growatt, Sofar, Victron, etc...)`</sup> 
> - And multiple BMS. <sup>`(JKBMS, AntBMS, DalyBMS, SeplosBMS, Pylontech, etc...)`</sup>
> 
> <sup>-> _In theory any inverter or BMS with ESPhome support can be used with the PVbrain2._</sup>
> 
> It also adds the possibility of controlling up to 32 relays allowing for example to control an **A**utomatic **T**ransfer **S**witch <sup>(ATS)</sup> _(Offgrid<=>return to the network)_. 
> 
> The PCB uses only crossover components or pluggable components in order to have easy setup/maintenance. 
> 
> The MCU used is an [ESP32S3](https://s.click.aliexpress.com/e/_DCEPtOd) running <sub>[![ESPHome](https://img.shields.io/badge/ESPHome-_-black?logo=esphome&style=social)](https://esphome.io)</sub> allowing communication over WiFi to <sub>[![Home_Assistant](https://img.shields.io/badge/Home_Assistant-_-black?logo=homeassistant&style=social)](http://homeassistant.io)</sub> <sup>(HA)</sup> natively.<br/>
> <sup>-> _But </sup>[![MQTT](https://img.shields.io/badge/MQTT-_-black?logo=mqtt&style=social)](https://esphome.io/components/mqtt)<sup> can be added easily._</sup>
> 
> __The main features are :__
> - [x] Direct communication and control with Voltronic/Pipsolar, DEYE, SOFAR, GROWATT inverters via direct Ethernet cable.<br/> <sup>_(pvbrain has a built-in [RS232](https://a.aliexpress.com/_EzMcqvP) and [RS485](https://a.aliexpress.com/_EzS7TkZ)  => TTL)_</sup>
> - [x] CANbus support. Possibility to translate informations from old generation BMS into modern CANbus protocols (Pylontech 1.2, Pylontech +, SMA, Victron)
> - [x] The VEdirect for <sub>![VICTRON](https://img.shields.io/badge/VICTRON-_-black?logo=victronenergy&style=social)</sub> models with an insulated adapter provided. 
> - [x] Important settings can be set directly from HA <sup>_(or the web server if enabled)_</sup>.
> - [x] Monitor multiple BMS <sup>_(tested with JKBMS but should work with antBMS, DalyBMS PaceBMS or SeplosBMS)_</sup> with an insulated adapter provided.
> - [x] Detect multiple AC sources <sup>_(solar/network/other)_</sup> (in order for example to do soft switching for the ATS part).
> - [x] Monitor _via_ a [JSY193](https://a.aliexpress.com/_EyMD1XJ), [JSY194T](https://a.aliexpress.com/_EHWOhZb) module <sup>_(modbus)_</sup> solar and network production.
> - [x] Control up to 32x relays with two i2c extension [SX1509](https://esphome.io/components/sx1509), _that is_ for ATS control or the reversing mode of a modern inverter.<br/> <sup>_(Axpert max I & II for example)_</sup>
> - [x] The solar power diverter thanks to [ROBOTDYN](https://a.aliexpress.com/_EwiP2jL) or [SSR](https://a.aliexpress.com/_EyikzBP) modules controlled in PWM.
> - [x] Monitor your basement temperature/humidity/pressure with [BME280](https://esphome.io/components/sensor/bme280) <sup>_(you can set up alarms just in case)_</sup>.
> - [x] Free I2C ports available for plugging in additional I2C sensors.
> - [x] SPI port is also available.

> [!NOTE]
> This PCB uses the excellent ESPhome integrations done by :
> - <sub>[![Syssi](https://img.shields.io/badge/Syssi-black?logo=git&style=flat)](https://github.com/syssi)</sub> (Many BMS and inverter).
> - <sub>[![DrCoolzic](https://img.shields.io/badge/DrCoolZic-black?logo=git&style=flat)](https://github.com/DrCoolzic)</sub> (Expansion cards [WK2132](https://www.dfrobot.com/product-2001.html) and [WK2168](../main/hardware/module_wk_2168/wk2168_3d_view.png) ).
> 
> The __PVbrain 2.0__ represents a joint work between <sub>[![SeByDocKy](https://img.shields.io/badge/SeByDocKy-black?logo=git&style=flat)](https://github.com/SeByDocKy)</sub> of the <sub>[![Youtube_e2nomy](https://img.shields.io/badge/Youtube-e--2--nomy-black?style=social&logo=youtube)](https://www.youtube.com/@e2nomy)</sub> and <sub>[![Bandit-17](https://img.shields.io/badge/Bandit--17-black?logo=git&style=flat)](https://github.com/Bandit-17)</sub>.
> - With the help of several members of the <sub>[![Reseautonome](https://img.shields.io/badge/DISCORD-Reseautonome-black?style=social&logo=discord)](https://reseautono.me/)</sub>.

# Release PVbrain 2 Youtube Live event:
[![youtube_live](https://github.com/SeByDocKy/pvbrain2/assets/82636574/b1cb5f1d-b5ad-48e0-927c-dcc7093ea610)](https://www.youtube.com/watch?v=e8uBhS54MFE)
<br/>_Video in French._

# Software (ESPhome) installation steps:
- __First of all be sure you have installed on your machine the ESP32 S3 driver from [Sillicon Labs](https://www.silabs.com/developers/usb-to-uart-bridge-vcp-drivers?tab=downloads).__

__Classic procedure :__

> <details>
><summary>Click here for show the Classic procedure. :arrow_heading_down:</summary>
> 
> :back:
> - :one: :heavy_minus_sign: Retrieve the [PVbrain 2.0](https://github.com/SeByDocKy/pvbrain2/archive/refs/heads/main.zip) zip (by right clicking) and save it into a new created folder, eg. /pvbrain2
> - :two: :heavy_minus_sign: Uncompress the zip file into your local folder (/pvbrain2) or into your/config/esphome folder of HASSIO (use samba share to transfer the uncompressed files).
> - :three: :heavy_minus_sign: Open your esphome's secrets.yaml file and check if wifi_ssid, wifi_password and ap_password variables are correctly corresponding with your local WiFi informations. 
> - :four: :heavy_minus_sign: Edit the PVbrain2.yaml and comment/uncomment each package according to your own solar setup. 
> - :five: :heavy_minus_sign: Compile and upload the code on your ESP32 S3 device.
> </details>

__Dummy procedure (for newbabies) :__

> <details>
><summary>Click here for show the Dummy procedure. :arrow_heading_down:</summary>
>
> :back:
> - :one: :heavy_minus_sign: Create/sign in a [Github](https://github.com/) accompt. You can create it faster with OAuth2 via your google account for example. 
> - :two: :heavy_minus_sign: Open the following [Gitpod](https://gitpod.io/#https://github.com/SeByDocKy/pvbrain2/tree/main) link. 
>   - The first time you will need also to sign in into gitpod framework for example with your previously created Github account.
> - :three: :heavy_minus_sign: When logged into Gitpod, you will see during the ESPhome installation, some log lines printed in the terminal. 
>   - Wait a couples of minutes to let finish the processus. 
>   - When done, press the "Open Browser" located at the botton right of the Gitpod page. 
>   - It should open a new webpage with the ESPhome Dashboard.
> - :four: :heavy_minus_sign: On the ESPhome Dashboard, click first on "secret" button located at the top right corner. 
>   - Replace "xxxxxxxx", "yyyyyyyy" and "zzzzzzzz" with your own WiFi SSID/password and AP informations (AP password will allow to access to your PVbrain2 if your WiFi/LAN is down). 
>   - Be aware, WiFi password must be a minimum of 8 caractars. 
>     - If not, you will need to change your WiFi password correspondly. 
>   - Click on "save" and quit the secret page by clicking on the top left cross.
> - :five: :heavy_minus_sign: Click on "Edit" for the PVbrain2 model. 
>   - Comment and/or uncomment each package according to your own solar setup and save the file. (Tip: you can comment/uncomment several lines simultaneously by selecting the lines and press on CTRL + /)
> - :six: :heavy_minus_sign: Plug your ESP32-S3 with a USB data cable first then the on top right corner, choose "Install" then on "Plug into this computer" to compile the firmware. It can be a long processus !!!. 
>   - Wait a couple of minutes (it first compile the code at background during 3-4min) then it starts the flashing part. 
>     - You should see a progression bar running when flashing.
> - :seven: :heavy_minus_sign: You finished the flashing procedure. 
>   - If you entered correctly your WiFi informations in the secrets.yaml file, you should see a notification in Home Assistant asking you to accept a new ESPhome device. 
>   - Accept it... __You finished!!!!__
> </details>

> <details>
><summary>Click here for show the French YouTube video of the Dummy procedure. :arrow_heading_down:</summary>
>
> :back:
>
> [![youtube_Dummy_procedure](https://github.com/SeByDocKy/pvbrain2/assets/82636574/12d9a2b0-adf0-412d-a7bb-ccc5b8956d41)](https://www.youtube.com/watch?v=R9PXNV0ayU4)
> <br/>_Video in French._
> </details>

# Main PCB Layout :

| 3D View                   | Copper Area               |
| :-----------------------: | :-----------------------: |
|<img src="../main/hardware/pvbrain_v2/pvbrain_v2_3d_view.png" width="1068" /> | <img src="../main/hardware/pvbrain_v2/pvbrain_v2_circuit_copper_area.png" width="490" /> |

<details>
<summary>Click here for show other views and schematic. :arrow_heading_down:</summary>

:back:
| Front                     | Back                      | Circuit                   |
| :-----------------------: | :-----------------------: | :-----------------------: |
| <img src="../main/hardware/pvbrain_v2/pvbrain_v2_front.png" width="1068" /> | <img src="../main/hardware/pvbrain_v2/pvbrain_v2_back.png" width="1068" /> | <img src="../main/hardware/pvbrain_v2/pvbrain_v2_circuit.png" width="1068" /> |

| Schematic 1               | Schematic 2               |
| :-----------------------: | :-----------------------: |
|<img src="../main/hardware/pvbrain_v2/pvbrain_v2_schematic_sheet1.png" width="1068" /> | <img src="../main/hardware/pvbrain_v2/pvbrain_v2_schematic_sheet2.png" width="1068" /> |
</details>

## [Gerber files and BOM :](../main/hardware)

Please find all Gerber files required for the PCB in the following folder : [__Hardware__](../main/hardware).<br/>
Also, find all BOM <sup>_(Aliexpress and Amzon links)_</sup> and some extra information in this <sub>[![Google Docs](https://img.shields.io/badge/Google_Docs-_-black?logo=google&style=social)](https://docs.google.com/spreadsheets/d/e/2PACX-1vQqTCFvosqLe3oL8kCYauC0Lip-PFoYXdSaXtiM5O0mfbqNR286LAmPG_ngkzn3vveCUbP-QugC6HAZ/pubhtml#)</sub> <sup>_(in French)_</sup>.

# DIY module :
Special clip-on modules were created by <sub>[![Static Badge](https://img.shields.io/badge/Bandit--17-black?logo=git&style=flat)](https://github.com/Bandit-17)</sub> for use <sup>_(or not)_</sup> with the PVbrain.

## [WK 2168 :](../main/hardware/module_wk_2168)
Module to extend the number of uarts on an esp32 <sup>_(4 Uarts per card)_</sup> an 8 GPIO, possibility of communicating in I2C or SPI.
| 3D View                   | Schematic                 |
| :-----------------------: | :-----------------------: |
| <img src="../main/hardware/module_wk_2168/wk2168_3d_view.png" width="700" /> | <img src="../main/hardware/module_wk_2168/wk2168_schematic.png" width="1068" /> |

<details>
<summary>Click here for show other views. :arrow_heading_down:</summary>

:back:
| Front                     | Back                      | Circuit                   |
| :-----------------------: | :-----------------------: | :-----------------------: |
|<img src="../main/hardware/module_wk_2168/wk2168_front.png" width="1068" /> | <img src="../main/hardware/module_wk_2168/wk2168_back.png" width="1068" /> | <img src="../main/hardware/module_wk_2168/wk2168_circuit.png" width="1068" /> |
</details>

## [WK 2132 :](../main/hardware/module_wk_2132)
Before discovering the WK2168 module which allowed the creation of the card above, a DIY version of the DFRobot [DFR0627](https://www.dfrobot.com/product-2001.html) had been designed.<br/>
Its cost is a little lower than its big brother the WK2168, but it only allows 2 additional UARTs.
| 3D View                   | Schematic                 |
| :-----------------------: | :-----------------------: |
|<img src="../main/hardware/module_wk_2132/wk2132_3d_view.png" width="650" /> | <img src="../main/hardware/module_wk_2132/wk2132_schematic.png" width="1068" /> |

## [UART Isolator :](../main/hardware/module_uart_isolator)
TTL isolator, originally designed for Victron VEdirect.
- With the participation of <sub>[![Luc](https://img.shields.io/badge/Luc-black?logo=discord&style=flat)](https://reseautono.me/)</sub>, <sub>[![Ju_Workshop](https://img.shields.io/badge/Ju__Workshop-black?logo=discord&style=flat)](https://reseautono.me/)</sub> and <sub>[![Cristof48](https://img.shields.io/badge/Cristof48-black?logo=discord&style=flat)](https://reseautono.me/)</sub> of the <sub>[![Reseautonome](https://img.shields.io/badge/DISCORD-Reseautonome-black?style=social&logo=discord)](https://reseautono.me/)</sub>.

| 3D View                   | Schematic                 |
| :-----------------------: | :-----------------------: |
|<img src="../main/hardware/module_uart_isolator/uart_isolator_3d_view.png" width="780" /> | <img src="../main/hardware/module_uart_isolator/uart_isolator_schematic.png" width="480" /> |

<details>
<summary>Click here for show other views. :arrow_heading_down:</summary>

:back:
| Front                     | Back                      | Circuit                   |
| :-----------------------: | :-----------------------: | :-----------------------: |
| <img src="../main/hardware/module_uart_isolator/uart_isolator_front.png" width="1068" /> | <img src="../main/hardware/module_uart_isolator/uart_isolator_back.png" width="1068" /> | <img src="../main/hardware/module_uart_isolator/uart_isolator_circuit.png" width="1068" /> |
</details>

## [Shunt TTL :](../main/hardware/module_shunt_ttl)
Simple Shunt for Direct UART output.
| Front                     | 3D View                   |
| :-----------------------: | :-----------------------: |
| <img src="../main/hardware/module_shunt_ttl/shunt_ttl_front.png" width="1068" /> | <img src="../main/hardware/module_shunt_ttl/shunt_ttl_3d_view.png" width="1068" /> |


# Additional daughter boards addons:

## [UART Extension Module :](../main/hardware/addon_carte_uart_extension)
An optional addon card can be plugged to allowing 4 additional UART outputs.

| 3D View                   | Schematic                 |
| :-----------------------: | :-----------------------: |
| <img src="../main/hardware/addon_carte_uart_extension/uart_extension_3d_view.png" width="1068" /> | <img src="../main/hardware/addon_carte_uart_extension/uart_extension_schematic.png" width="1068" /> |

<details>
<summary>Click here for show other views. :arrow_heading_down:</summary>

:back:
| Front                     | Back                      | Circuit                   |
| :-----------------------: | :-----------------------: | :-----------------------: |
| <img src="../main/hardware/addon_carte_uart_extension/uart_extension_front.png" width="1068" /> | <img src="../main/hardware/addon_carte_uart_extension/uart_extension_back.png" width="1068" /> | <img src="../main/hardware/addon_carte_uart_extension/uart_extension_circuit.png" width="1068" /> |

Also, find all BOM <sup>_(Aliexpress and Amzon links)_</sup> and some extra information in this <sub>[![Google Docs](https://img.shields.io/badge/Google_Docs-_-black?logo=google&style=social)](https://docs.google.com/spreadsheets/d/e/2PACX-1vQqTCFvosqLe3oL8kCYauC0Lip-PFoYXdSaXtiM5O0mfbqNR286LAmPG_ngkzn3vveCUbP-QugC6HAZ/pubhtml#)</sub> <sup>_(in French)_</sup>.
</details>

## [MULTI-CAN :](../main/hardware/addon_MULTI-CAN)
An optional addon card can be plugged to allowing 4 additional CAN MODULE SPI.
| 3D View                   | 
| :-----------------------: |
| <img src="../main/hardware/addon_MULTI-CAN/MULTICAN_3d.PNG" width="456" /> |

<details>
<summary>Click here for show other views. :arrow_heading_down:</summary>

:back:
| Front                     | Back                      |
| :-----------------------: | :-----------------------: |
| <img src="../main/hardware/addon_MULTI-CAN/MULTICAN_front.PNG" width="256" /> | <img src="../main/hardware/addon_MULTI-CAN/MULTICAN_back.PNG" width="256" /> |

Also, find all BOM <sup>_(Aliexpress and Amzon links)_</sup> and some extra information in this <sub>[![Google Docs](https://img.shields.io/badge/Google_Docs-_-black?logo=google&style=social)](https://docs.google.com/spreadsheets/d/e/2PACX-1vQqTCFvosqLe3oL8kCYauC0Lip-PFoYXdSaXtiM5O0mfbqNR286LAmPG_ngkzn3vveCUbP-QugC6HAZ/pubhtml#)</sub> <sup>_(in French)_</sup>.
</details>

## [PV Monitor :](../main/hardware/addon_carte_pv_monitor)
Addon card created for [PVbrain V1](https://github.com/Bandit-17/PVBRAIN) by <sub>[![Bandit-17](https://img.shields.io/badge/Bandit--17-black?logo=git&style=flat)](https://github.com/Bandit-17)</sub> and re-designed by <sub>[![Dackara](https://img.shields.io/badge/Dackara-black?logo=git&style=flat)](https://github.com/Dackara)</sub> in this __V2__.

The card offers the possibility of securely monitoring the voltage of two DC inputs.

| 3D View                   | Schematic                 |
| :-----------------------: | :-----------------------: |
|<img src="../main/hardware/addon_carte_pv_monitor/pv_monitor_3d_view.png" width="1068" /> | <img src="../main/hardware/addon_carte_pv_monitor/pv_monitor_schematic.png" width="980" /> |

<details>
<summary>Click here for show other views. :arrow_heading_down:</summary>

:back:
| Front                     | Back                      | Circuit                   |
| :-----------------------: | :-----------------------: | :-----------------------: |
| <img src="../main/hardware/addon_carte_pv_monitor/pv_monitor_front.png" width="1068" /> | <img src="../main/hardware/addon_carte_pv_monitor/pv_monitor_back.png" width="1068" /> | <img src="../main/hardware/addon_carte_pv_monitor/pv_monitor_circuit.png" width="1068" /> |

Also, find all BOM <sup>_(Aliexpress and Amzon links)_</sup> and some extra information in this <sub>[![Google Docs](https://img.shields.io/badge/Google_Docs-_-black?logo=google&style=social)](https://docs.google.com/spreadsheets/d/e/2PACX-1vQqTCFvosqLe3oL8kCYauC0Lip-PFoYXdSaXtiM5O0mfbqNR286LAmPG_ngkzn3vveCUbP-QugC6HAZ/pubhtml#)</sub> <sup>_(in French)_</sup>.
</details>

## [Fil_Pilote :](../main/hardware/addon_carte_fil_pilote)
An additional card was created by <sub>[![Dackara](https://img.shields.io/badge/Dackara-black?logo=git&style=flat)](https://github.com/Dackara)</sub> to allow control of the heating radiator pilot wire from the I2C port <sup>(4 output heating zones, control of 6 orders, possible to pair 2 cards and three-phase operation possible)</sup> and as an option , communication with Linky meters.

Link to the Github Page: <sub>[![Dackara-Fil_Pilote](https://img.shields.io/badge/Dackara-Fil__Pilote-black?style=social&logo=Github)](https://github.com/Dackara/Fil_Pilote)</sub>.

| 3D View | Photography |
| :-----------------------: | :-----------------------: |
| <img src="https://github.com/Dackara/Fil_Pilote/blob/main/Image/3D_View.png" width="1068" /> | <img src="https://github.com/Dackara/Fil_Pilote/blob/main/Image/Photo/IMG_3848.JPG" width="1068" /> |

## [Clamp_Meter :](../main/hardware/addon_carte_clamp_meter)
Another option card created by <sub>[![Dackara](https://img.shields.io/badge/Dackara-black?logo=git&style=flat)](https://github.com/Dackara)</sub> to monitor the passage of current through the clamps.
- 1 to 16 Clamp <sup>(2 mounting possible for each output : JST-XH for [2-strand clamp](https://s.click.aliexpress.com/e/_De0j7rx) or Jack for [SCT013](https://s.click.aliexpress.com/e/_DFRTWIN))</sup>
- 1 to 4 pre-addressed [ADS1115](https://s.click.aliexpress.com/e/_DF9geSz).
- 1 [TCA9548A](https://s.click.aliexpress.com/e/_DDACktb) <sup>(optional - bridging if not used)</sup> to multiplex the I2C <sup>(useful in the event of more than 4 ADS or I2C address conflict)</sup> with all its outputs remote for external use.
- 1 ESP possible at input for non-PVbrain users or other reasons... 6 assembly possible: <sup>(offset of all outputs and recovery of i2c via bridging)</sup>.

| [ESP8266 D1 Mini](https://s.click.aliexpress.com/e/_DmbvqH7) | [ESP32 D1 Mini](https://s.click.aliexpress.com/e/_DEU8tVB) | [ESP32 S2 Mini](https://s.click.aliexpress.com/e/_DdgwMVF) | [ESP32 C3](https://s.click.aliexpress.com/e/_DFystRx) | [ESP32 C3 Zero](https://s.click.aliexpress.com/e/_DeIlFtn) | [ESP32 S3 Zero](https://s.click.aliexpress.com/e/_DeIlFtn) |
| :---| :---: | :---: | :---: | :---: |---: |
  
Link to the Github Page: <sub>[![Dackara-Clamp_Meter](https://img.shields.io/badge/Dackara-Clamp__Meter-black?style=social&logo=Github)](https://github.com/Dackara/Clamp_Meter)</sub> <sup>(Still in development)</sup>

| 3D View                   | Circuit                   |
| :-----------------------: | :-----------------------: |
|<img src="../main/hardware/addon_carte_clamp_meter/clamp_meter_3d_view.png" width="1068" /> | <img src="../main/hardware/addon_carte_clamp_meter/clamp_meter_circuit.png" width="1068" /> |

## [Protoboard :](../main/hardware/addon_carte_prototype)
Just a prototyping board with the same footprint as the other addon boards.
| Front                     |
| :-----------------------: |
|<img src="../main/hardware/addon_carte_prototype/carte_prototype_front.png" width="480" /> |

## [3D print DIN mount :](../main/hardware/printable_3d_din_mount)
[3D Files](https://github.com/Dackara/Fil_Pilote/blob/main/Hardware/3D_Print) to print, created by <sub>[![Dackara](https://img.shields.io/badge/Dackara-black?logo=git&style=flat)](https://github.com/Dackara)</sub>, for mounting addon cards on DIN rail <sup>(electrical panel)</sup>.<br/>
A plastic card in the same format as the addon cards which can, for example, allow circuit isolation, is also available.
| Front View                | Back View                 |
| :-----------------------: | :-----------------------: |
| <img src="../main/hardware/printable_3d_din_mount/3d_din_mount_front.png" width="880" /> | <img src="../main/hardware/printable_3d_din_mount/3d_din_mount_back.png" width="1068" /> |

## ["Carte Option 2" :](../main/hardware/addon_carte_old_option2)
The old "Option 2" card made by <sub>[![Luc](https://img.shields.io/badge/Luc-black?logo=discord&style=flat)](https://reseautono.me/)</sub> for the [PVbrain V1](https://github.com/Bandit-17/PVBRAIN) is also compatible with the __PVbrain V2__.
| 3D View                   |
| :-----------------------: |
|<img src="../main/hardware/addon_carte_old_option2/carte_option2_3d_view.png" width="480" /> |
