# HomeAssistant

## Summary of my setup 

### [Video Demo](https://github.com/BakedBananas/HomeAssistant/blob/master/PXL_20220525_134711428.mp4)

When you enter the condo, a motion sensor hidden by the door triggers a Welcome automation which sets the thermostat according to the temperature outside, it opens the blinds, it auto sets the lights using a light sensor from my old phone, and of course Alexa says "Welcome". 

Right in the door, I have a tablet mounted on the wall, plugged into a smart outlet on 30-80% charging. The tablet contains a floorplan UI that allows you to touch a room to toggle the light in that room. It also has a counter using the OpenSky integration that counts flights in and out of a five mile radius (living near DCA this is a fair approximation of arrivals/departures), it has a counter that keeps track of the mail that's in our mailbox so we know when we forget it for too long. Also has buttons that will play music in all rooms for convenience. Lastly, it has a thermostat reading of actual temp and goal temp.

Throughout the day, as long as we are home, the blinds will open/close according to the position of the sun (our condo faces east so the morning sun is killer). Likewise, the lights automatically adjust based on the light sensor. The thermostat also auto adjusts based on the temperature AND pollen count, telling you to open the windows if it's nice out and the pollen count is low. I also installed a fan on our balcony that is flashed with Tasmota. This comes on and off based on the outside temperature as well.

The balcony happens to be at a great height for viewing planes in and out of DCA, so using openSky I can have Alexa give flight info for the flight that we can see from the balcony.

When we go to bed, a simple "Alexa, goodnight" triggers the goodnight routine, which sets the thermostat based on the low temp for the night. It also turns off all the lights, fans, and outlets (other than the tablet charger). 

In the mornings, the good morning routine is triggered by either an alarm, or the kitchen light switch turning ln (on weekends). This sets the thermostat based on the current outside/inside temps, turns on the auto light by light sensor, and Alexa gives us the weather for the day.

Lastly, my favorite, the goodbye routine. The goodbye routine runs when we leave (obviously), initiated by "Alexa, goodbye". The routine waits five minutes then turns off all the lights, closes the blinds, sets the thermostat to away mode, and runs the vacuum. The vacuum is integrated via Valetudo and thus can be sent to room specific cleanings by "Alexa, clean the [room name]. 

Feel free to ask any questions or give any suggestions. I stumbled upon HA in December of 2021, and have since been neck deep in it. I love everything about it, and it truly can make it feel like you're living in the future.

Parts list below (All prices are MSRP) Estimated total: $1339.57

### Balcony  

* Insignia 24-inch Class F20 Series Smart Fire TV - $149.99  

* Alexa Echo Dot 3rd Gen(Balcony Echo Dot) - $39.99  

* Fan w/ Sonoff iFan04 - $151.88  

* Tuya Recchargeable WiFi Smart Motorized Chain Roller x 4 - $92.99  

### Dining Room  

* Kasa Smart Dimmer Switch HS220 (Dining Room Light) - $17.99  

* Google Nest Thermostat - $126.95  

### Front Door  

* Kasa Smart Dimmer Switch HS220 (Front Door Light) - $17.99  

* SmartThings Smart Motion Sensor - $19.99  

### Hallway  

* Treatlife 2.4Ghz WiFi Smart 3 Way Switch (Hallway Light) - $20.99  

* Amazon Fire 7 Tablet - $49.99  

### Kitchen  

* Treatlife 2.4Ghz WiFi Smart 3 Way Switch (Kitchen Light) - $20.99  

* DAYBETTER Smart Wifi LED Lights x 2 (Cabinet Lights) - $19.99  

* ELEGRP Occupancy Motion Sensor Light Switch (Pantry) - $15.99  

* Alexa Echo Show 5 - $49.99  

### Living Room  

* Kasa Smart Wi-Fi Plug Mini x 2 - $9.99  

* Alexa Echo Dot 3rd Gen (Living Room Echo Dot) - $39.99  

### Master Bathroom  

* Treatlife 2.4Ghz WiFi Smart Single Pole Switch (Bathroom Light) - $16.99  

* Treatlife 2.4Ghz WiFi Smart Single Pole Switch (Bathroom Fan) - $16.99  

### Master Bedroom  

* Treatlife 2.4Ghz WiFi Smart Single Pole Switch (Wall Outlet) - $16.99  

* Treatlife 2.4Ghz WiFi Smart 3 Way Switch (Sink Light) - $20.99  

* Kasa Smart Dimmer Switch HS220 (Sconces) - $17.99  

* ELEGRP Occupancy Motion Sensor Light Switch (Closet) - $15.99  

* Alexa Echo Dot 4th Gen (Master Echo Dot) - $59.99  

### Second Bathroom  

* Treatlife 2.4Ghz WiFi Smart Single Pole Switch (Bathroom Light) - $16.99  

* Treatlife 2.4Ghz WiFi Smart Single Pole Switch (Bathroom Fan) - $16.99  

### Second Bedroom  

* Treatlife 2.4Ghz WiFi Smart Single Pole Switch (Wall Outlet) - $16.99  

* Kasa Smart Dimmer Switch HS220 (Sconces) - $17.99  

### Vacuum  

* Dreametech D9 Robot Vacuum and Mop Cleaner - $299.99

## Config files for my current build of Home Assistant

* automations.yaml - Contains automations for smart home, each needs a trigger
* configuration.yaml - The base config file run on startup
* drawing.svg - Vector drawing for tablet dashboard
* google_calendars.yaml - Calendar notification setup
* groups.yaml - Groups (Unused)
* scenes.yaml - Contains entity specific commands to control light brightness/color
scripts.yaml - Contains scripts for the smart home, they are run via automations.
