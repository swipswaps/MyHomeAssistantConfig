# MyHomeAssistantConfig

'My Home Automation Setup'

***TL;DR***: Home Assistant, Node-Red, MQTT, Homeseer with mcsMQTT plugin based home automation configuration.



My journey with home automation started back in the Insteon days playing with a simple switch but I found it rather immature at the time.  About 5 years ago I implemented Z-wave and Vera in my home automating lights, switches and my garage door using a Fortezza Mimo Light contact switch before Wifi solutions were readily available.  I always 
found Vera rather clunky, software upgrades were prone to failure and automations were not very straighforward.  About 3 years ago I switched to Homeseer, and while the interface is clunky and it's made on top of a pretty legacy code base it was much more powerful (and expensive) than Vera.  Things got interesting once Homeseer started to 
play with Google Assistant.  

I've long held that voice is the key to "seemless" home automation - what's the point in pulling out your phone to turn on a light, when you can just speak it?  I quickly integrated cameras with Homeseer, Google Assistant, Hue Lights (my out switches don't have the depth for ZWave switches), Nest Thermostats, etc etc.  In the last few weeks I moved to Home Assistant to get a more modern platform, hoever having played with Home Assistant's Z-Wave implementation it left a GREAT DEAL to be desired.  So I implemented a HomeSeer plugin called mcsMQTT so that I can use Homeseer for what it's REALLLY good at (Z-Wave) and Home Assistant aand Node-Red for what they are good at.

# *My Current Home Automation Components*

 *  HomeSeer - For Purely Z-Wave with mcsMQTT Plugin
 *  Home Assistant - For modern code base, integration with 3rd party devices and services, modern front end (Lovelace) etc.
 *  Node-Red - For automation
 *  Mosquitto MQTT - For automation
 *  MariaDB - For HA Recorder History

 * Platform

    * Homeseer Hometroller Zee S2
    * Hass.io on Raspberry Pi 3B (Home Assistant and Node-Red)
    * Mosquitto an Maria run in Docker Containers on my QNAP NAS

# *Automation Hardware*

 *  Z-Wave (Homeseer)
    * 20+ Homeseer WD-100 & Evolve dimmers 
    * 5+ Aeon Labs and Dome smart switches
    * 1 Aeon Labs heavy duty smart switch (pool pump)
    * 3 Aeotec multi sensor 5 
    * 1 Fortezza Mimo Lite (garage door) 
    * 1 Ecolink Motorized Z-wave switch (for switches that don't have neutral wire)
    * 2 Schlage Connect dead bolts
    * various other sensors I'm forgetting about.
 
*  Nest (Home Assistant)
    * 2 Nest Thermostats 
    * 3 Nest CO2/Smoke Detectors
 
 * Ring (Home Assistant)
    * 1 Ring Pro Doorbell 
    * 1 Ring Floodlight Camera

 * Sonos (Home Assistant)   
    * 2 Play:1
    * 1 Play:5

 * Google Home (Home Assistant via Home Assistant Cloud)
    * 1 Google Home (original) with Rechargable battery base
    * 4 Google Home Mini   

 * Blind Control (Home Assistant)
    * MK Smart House ESP8266 Based Blind tilt - https://www.mksmarthouse.com/shop/Blinds-Control-p93393095

 * Presence Detection
   * 4 * Raspberry Pi W running Monitor https://github.com/andrewjfreyer/monitor/ for Bluetooth and BTLE presence detection
   * Node-Red Unifi integration for WiFi detection
 
 * Harmony Remote (Home Assistant)  

 * I'm sure I'm missing some other things.

# *Home Network*

  * Ubiquiti Unifi
    * 3 * UNifi AP Lite
      2 * Unifi AP Mesh
      1 * Cloud Key Controller (moving to a docker container)
      1 * 8 Port POE Switch
      1 * Unifi Security Gateway
  
  * Internet Connection
    * Bell Fibe Gigabit Fiber (1Gb Up, 100Mb down)
    * Rogers Cable (30Mb backup)