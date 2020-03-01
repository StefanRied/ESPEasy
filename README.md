This is a fork of the ESPEasy development repro at the mega branch: https://github.com/letscontrolit/ESPEasy
I use it to rebrand it a bit to my house.
I am also experimenting with new plugins and bug fixes to some pluging.
All work is public.
Please refer to the licence and copyright of the original work by Letscontrolit.
Thanks

I've just switched the plugin for DMX Lights on.
See #define USES_P054 is the ESPEasy.ino.

This is quite genius for example with home automation frameworks such as IOBroker or OpenHUB. You can simply use a tiny ESP8266 as a MQTT to DMX Bridge.
Simply connect a RS485 Device with its DI pin to the D4 of the ESP, as the D4 is recommended by the P054 Plugin. If you don't want to use a level shifter between the 3.3V ESP and the official 5V of the RS485 Bus, just connect the VCC of the RS485 with the 3.3V out pin of the ESP8266. This works extremely reliable for me if the Controller is close to the first DMX Lamp.

If you know how to compile the latest ESPEasy, I always recommend to get to the orgiginal repro. (And donate a few Euros to these great two developers.)
If you don't get it compiled, just download my binary from my built and push it to you ESP8266 Board.

Download https://github.com/StefanRied/ESPEasy/blob/mega/build/firmware.bin

Flash to the ESP8266

esptool.py --port /dev/cu.wchusbserial30 --baud 460800 write_flash -fs 4MB -ff 80m 0x00000 build/firmware.bin

Have gun
