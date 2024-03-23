# ecodan-esp32 example configurations
ESP32(S3) configuration files ecodan-ha-local and esphome

# required hardware
If you don't want to solder, use one of the boards that supports 5v on the GPIO ports.

Tested boards

| Board | Link | Notes |
|:---|:----:|:---|
| m5stack Atom (ESP32 variants) | https://docs.m5stack.com/en/core/AtomS3 | Grove ports on the m5stack boards have built in level shifters |
| m5stack AtomS3 (ESP32-S3 variants) | https://docs.m5stack.com/en/core/AtomS3 | Grove ports on the m5stack boards have built in level shifters |

Cable
* Get one of the grove female cable and a ST PAP-05V-S connector. Remove one end of the grove connector and replace it with a ST PAP-05V-S connector. Here's an example:
![image](https://github.com/gekkekoe/ecodan-esp32/blob/main/ecodan-ha-local/img/m5stack_cn105.jpg?raw=true)

Cable mapping (from left to right)
| grove | cn105 |
|:---|:---|
|pin 1 - black (gnd) | pin 4 - black (gnd) |
|pin 2 - red (5v) | pin 3 - red (5v) |
|pin 3 - white (GPIO 2) | pin 2 - white (Tx) |
|pin 4 - yellow (GPIO 1) | pin 1 - yellow (Rx) |

*Note: pin 5 (12v) on the cn105 is not used.*

# required firmware
One of the following
* https://github.com/rbroker/ecodan-ha-local
  > * Use https://github.com/gekkekoe/ecodan-esp32/blob/main/ecodan-ha-local/platform.ini to build with platformIO. Find your definition https://docs.platformio.org/en/latest//boards/ and set it in the platform.ini. Please note that the esp32-s3 is only supported in platformIO version >= 6.
  > * Flash the firmware to the esp32
  > * Power down (!) the heatpump and connect the grove-cn105 and esp32
  > * Power up the heatpump 
  > * find the ip assigned to the ecodan-ha-local and access the configuration via http
  > * configure Tx, Rx pins, mqtt and wifi. Once rebooted, it should be auto discovered in home assistant. For more details on how to configure ecodan-ha-local please read https://github.com/rbroker/ecodan-ha-local/blob/main/README.md

* https://github.com/tobias-93/esphome-ecodan-heatpump

Here's how it's connected inside my heatpump:

![image](https://github.com/gekkekoe/ecodan-esp32/blob/main/ecodan-ha-local/img/m5stack_installed.jpg?raw=true)