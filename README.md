# ha_display
Touch panel control for Home assistant 

Whole story for my touch panel control. Currently work in progress.. :-)

Hardware:
Nextion display (https://nextion.tech/datasheets/nx3224t024/ )
NodeMCU
2 addtional Jumpercables

Used tools and SW on OSX
- Arduino
- MQTT Explorer (to check if your messages come through)

Used tools on Windows
- Nextion editor to create the TFT file
(in case you copy the tft file from OSX to the SD card, you need to delete a OSX create file starting with a . from the card. (rm /Volumes/*SD*/.*YourFileName*)

Arduino:
Settings: File -> Preferences -> Additional board managers:
"https://dl.espressif.com/dl/package_esp32_index.json, http://arduino.esp8266.com/stable/package_esp8266com_index.json"

Add following librarys:
- Easy Nextion Library  https://github.com/Seithan/EasyNextionLibrary
- EspMQTTClient
- PubSubClient

To be able to compile, update below file:
~/Library/Arduino15/packages/esp8266/hardware/esp8266/2.7.4/tools/pyserial/serial/tools/list_ports_osx.py
Update lines 29 and 30 to:
   iokit = ctypes.cdll.LoadLibrary('/System/Library/Frameworks/IOKit.framework/IOKit')
   cf = ctypes.cdll.LoadLibrary('/System/Library/Frameworks/CoreFoundation.framework/CoreFoundation')

