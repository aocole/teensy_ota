# teensy_ota
Teensy OTA update via Ethernet POC code. 

On boot the teensy will join the network via DHCP and print its address to the serial port. Static IP config available.
Visit the IP address via a web browser to see the firmare `.hex` file upload form. This builds on work from @ssaenger/FlasherX-Ethernet_Support
(who did a much better job encapsulating the code). However I couldn't get that code to work reliably - it would hang almost every time while
trying to reboot after copying the new firmware. Writing the new file to the SD card and then using FlasherX to copy from the SD card was 100%
reliable. This required modifying FlasherX to skip interactive confirmation of the update.

## URLs:

 - `GET /` - displays upload form
 - `POST /` - upload new firmware `.hex` file as multipart/form-data

## Required libraries

 - QNEthernet
 - AsyncWebServer_Teensy41 v1.7.0+
