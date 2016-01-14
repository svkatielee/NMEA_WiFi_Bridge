# NMEA_WiFi_Bridge
An ESP8266-01 WiFi module to read NMEA serial data and UDP broadcast it to multiple openCPN instances as a Bridge.

<b>Warning: A work in progress</b>

I want to be able to run openCPN on both a laptop and a tablet at the same time. I would like the laptop down below deck, safe from the rain and salt water spray. I would like to have a mostly waterproof tablet in the cockpit to monitor progress. And I would like to be able to quickly check the ship's status from the captain's berth when off watch, maybe on a smart phone.

The plan is to implement a device to read the serial data from all the boat instruments and send that data to openCPN over a WiFI link so there are no physical wires attached. It will broadcast the data with UDP so that multiple devices can read the data at the same time.

The ESP8266 ESP-01 was chosen because it was on hand and it has adequate I/O for this project.

The rs-232 input signal voltage should work with -12 to +12 volts. It was tested with a Garmin 72H which puts out -5 to +5.

<h3>Setup</h3>
Connect power and input signal rs-232 line with ground.
Press and hold config button, press reset, 
     continue to hold config until the LED stays lit.
Connect to the AP "NMEA WiFi Bridge" with a system/phone/etc.
Connect your brower to 10.1.1.1 with password in code "nmeawifi".`
Configure the form for your network and click the "configure" button.
Verify the results page.
Press reset or cycle power for the module to connect to your network.

To verify it is working, there is a status page on the address on the NMEA WiFi Bridge. Type this address into your browser.



<h3>Credits</h3>
The ESP was programmed with the Arduino IDE for ESP 1.6.5 and the board manager version 1.6.5-947-g39819f0.

Also uses the pfodWebWiFiConfig and adapted schematic from http://www.forward.com.au/pfod/CheapWifiShield/ESP2866_01_WiFi_Shield/ESP8266_01_WiFi_Shield_R1/index.html for the dynamic web config of the ESP.

I used the version 1.9 of the library pfodWifiConfig.zip which is now included as Doc/pfodWifiConfig.zip

<quote>
/**
 *  Cheap and Simple Wifi Shield for Arduino and other micros
 * http://www.forward.com.au/pfod/CheapWifiSheild/index.html
 *
 * (c)2015 Forward Computing and Control Pty. Ltd.
 * This code may be freely used for both private and commerical use.
 * Provide this copyright is maintained.
 */
</quote>

Follow his instructions for setting up the library from above. 
(Also copied here from http://www.forward.com.au/ for the verison I used)

---------------------------
<quote>
<h4>Programming the WiFi Shield</h4>

The WiFi Shield needs to be programmed once, only, and never again, with the web page configuration and the Serial to WiFi Bridge code.

To program the shield follow the instructions given on https://github.com/esp8266/Arduino under Installing With Boards Manager. When opening the Boards Manager from the Tools → Board menu and select Type Contributed and install the esp8266 platform. This project was compiled using the ESP8266 version 1.6.4-673-g8cd3697. Later versions well be better but may have their own bugs as the platform is evolving rapidly.

Close and re-open the Arduino IDE and you can now select “Generic ESP8266 Module” from Tools → Board menu.

You also need to install the latest version of pfodWifiConfig.zip which handles the storing and retrieval of the settings in EEPROM

a) Download this pfodWifiConfig.zip file to your computer, move it to your desktop or some other folder you can easily find<br>
b) Then use Arduino 1.6.5 IDE menu option Sketch → Import Library → Add Library to install it.<br>
(If Arduino does not let you install it because the library already exists then find and delete the older pfodWifiConfig folder and then import this one)<br>
c) Stop and restart the Arduino IDE and under File->Examples you should now see pfodWifiConfig.<br>
</quote>
---------------------------

Also borrowed from http://www.scienceprog.com/alternatives-of-max232-in-low-budget-projects/ for the rs-232 to ttl translation for the input pin.

And last but not least some programming concepts from https://github.com/wa0uwh/ERB-EspWebServer.


