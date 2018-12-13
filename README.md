# Grott
Growatt inverter monitor

The growatt inverter with shine wifi adapter sends log data to the growatt (website) at the internet. At this website you can see detailed information on how the inverter is performing. 

I was looking for a way the intercept this information and use it for my home domotica environment. 

Searching at the internet I find some site where people managed to intercept the data and send this information to pvoutput website. 
See: 

https://github.com/sciurius/Growatt-WiFi-Tools 

http://123zonne-energie.ning.com/profiles/blogs/growatt-wifi-module-via-raspberry-pi-automatische-upload-naar

Inspired by this solutions, I decided that I want a more generic solution. So I use the ideas and created an own solution based on routing the data (IP forwarding) via a Raspberry Pi and capture the growatt log data with a python (socket) sniffer that sends a JSON message to a MQTT broker (eg MOSQUITTO). With node red it is possible to connect to use the MQTT data and create dashboard or sent it to other receivers like pvoutput or Domoticz. 

The program is written in python and can be started from the command line or linux services. Because the progrom is using sockets to capature the data it is necessary to run it with SUDO rights. 

Since a couple of weeks I have the program running as a service and seem to work fine. I will published the program soon after doing some clean up. I will publish setup information in the wiki. 
