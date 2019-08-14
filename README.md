# WiFi Doorbell Sensor
This is the source code for the WiFi Doorbell Sensor from Firefly Electronix. Visit our website for more information. https://www.fireflyelectronix.com/product/wifidoorbell

#### Software Roadmap
- [x] Support for OTA (Over-the-air) Updates - v1.2 Release
- [ ] Support for TLS/SSL Secure Client (Http port 443 and MQTT port 8883)

### Updating the firmware - OTA (Available in release v1.2 or newer)

1. Download the latest .bin file from our releases https://github.com/fireflyelectronix/wifidoorbell/releases
1. Press and hold SW1 within 10 seconds after installing the battery
1. Connect to the WiFi Network - Firefly-xxxxxx
1. Open your browser and navigate to 192.168.244.1 or 192.168.4.1 (Updating does not work throgh Apple's Captive Portal that pops up automatically)
1. Click on Update
1. Click on Choose File and Select the .bin file that was downloaded in step 1
1. Click on Update - It will automatically restart after update is completed. Settings will be kept after the update and not erased.


### Customizing and building your own firmware with Arduino

1. Download and install Arduino IDE (tested with version 1.8.8)

1.  Add ESP8266 to File -> Preferences -> Additional Boards Manager URLs: http://arduino.esp8266.com/stable/package_esp8266com_index.json

1.  Install ESP8266 Board Tools -> Board: -> Boards Manager... -> Search "ESP8266" -> click Install

1.  Install Libraries Tools -> Manage Libraries -> Search -> Select Version -> click Install
    1. Install ArduinoJson Library (tested with version 5.13.4)
    1. Install PubSubClient Library (tested with version 2.7.0)

### Programming the WiFi Doorbell Sensor - USB to Serial

1. Tools that you will need.
    1. Node MCU Py Flasher - Download it here https://github.com/marcelstoer/nodemcu-pyflasher/releases
    1. Download the latest .bin file from our releases. https://github.com/fireflyelectronix/wifidoorbell/releases
    1. FTDI programming tool - One that can switch to 3.3v logic and uses the FT232RL chip. https://www.amazon.com/gp/product/B07G2D34ZW

1. Conenct the FTDI to the J2 Header on the WiFi Doorbell Sensor.

    | FTDI Pin | WiFi Doorbell Pin |
    | -------- | ----------------- |
    | GND      | GND               |
    | RX       | TX                |
    | TX       | RX                |

1. Program the WiFi Doorbell Sensor
    1. Press and hold SW1 prior to installing the battery. This puts the ESP8266 module into UART Download mode.
    1. Open the Node MCU Py Flasher tool. Change Erase Flash to - yes. All other settings keep on default
    1. Select the COM port that your FTDI programmer is plugged into.
    1. Select the .bin file that you downloaded from our relases.
    1. Click on Flash NodeMCU

The 4 pin header J2 is used for progamming.

    1. Pin 1 - VCC
    1. Pin 2 - GND
    1. Pin 3 - TX
    1. Pin 4 - RX
