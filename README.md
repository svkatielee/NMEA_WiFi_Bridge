# NMEA_WiFi_Bridge
An ESP8266-01 WiFi to read NMEA serial data and broadcast UDP to multiple openCPN instances as a Bridge.

<b>Warning: A work in progress</b>

I want to be able to run openCPN on both a laptop and a tablet at the same time. I would like the laptop down below deck, safe from the rain and salt water spray. I would like to have a mostly waterproof tablet in the cockpit to monitor progress. And I would like to be able to quickly check the ship's status from the captain's berth when off watch, maybe on a smart phone.

The plan is to implement a device to read the serial data from all the boat instruments and send that data to openCPN over a WiFI link so there are no physical wires attached. It will broadcast the data with UDP so that multiple devices can read the data at the same time.

The ESP8266 ESP-01 was chosen because it was on hand. It has adequate I/O for this project.

<h3>Setup</h3>
Connect power and input signal rs-232 line w/ground.
Press and hold config button, press reset, 
     continue to hold config until the yellow LED stays lit.
Connect to the AP (NMEA WiFi Bridge) with a system/phone/etc.
Connect browere to 10.1.1.1 with password in code (nmeawifi)
configure the form for your network and click the "configure" button.
Verify the results page.
Press reset to connect to your network.

There is a status page at the default port on the address on the NMEA WiFi Bridge,



<h3>Credits</h3>
The ESP is programmed in the Arduino IDE for ESP 1.6.5 and the board manager version 1.6.5-947-g39819f0.

Also uses the pfodWebWiFiConfig and adapted schematice from http://www.forward.com.au/pfod/CheapWifiShield/ESP2866_01_WiFi_Shield/ESP8266_01_WiFi_Shield_R1/index.html for the dynamic web config of the ESP.

Also borrowed from http://www.scienceprog.com/alternatives-of-max232-in-low-budget-projects/ for the rs-232 to ttl translation for the input pin.

And last but not least some programming concepts from https://github.com/wa0uwh/ERB-EspWebServer.
