<p align="center">
  <a href=""><img src="https://www.home-assistant.io/images/home-assistant-logo.svg" alt="logo" width="175"></a>
</p>

## Home Automation Philosophy
You shouldn't have to work the room, the room should work you. True home automation is having your home anticipate what you want without needing any input from you. Using voice commands are nice and all, but that ends up being just another switch you have to use and is ultimately just a remote control, not automation.

My frontend may not be as fancy as some others, but this is because I'm trying to be as hands off as possible when it comes to my automations. Everything should run without me even thinking or interacting with Home Assistant and this is reflected in my display.

I also made the popular dark theme [Slate](https://github.com/seangreen2/slate_theme).

## Notable Automations [(Wiki)](https://github.com/seangreen2/home_assistant/wiki)

### [Determining Room Occupancy](https://github.com/seangreen2/home_assistant/wiki/Detecting-Room-Occupation)
Awhile back I wrote up a tutorial on getting your Google Home Minis to detect your phones for Room Presence Detection. Once Google removed that ability, I had to come up with a method of determining when a room was occupied or not. I developed a kind of "Room Occupation Logic" which has worked incredibly well so far and it's easy to implement and adapt to you needs.

### [Cool or Heat your Home Before you Arrive](https://github.com/seangreen2/home_assistant/wiki/Beat-the-Heat-and-Begin-Cooling-your-Home-before-you-Arrive)
It's never fun to come home to a hot and humid home just to have your AC kick on as soon as it detects you on your WiFi, or however else you have your local presence set up. Like you, I used to also come home and be miserable until the HVAC finally caught up to my comfortable temperatures. Depending on your preferences this could take TENS OF MINUTES! That simply will not do. This automation uses the Proximity Sensor to intelligently detect if you're on your way home and will begin making it comfortable before you arrive.

### [Easy Sleep Mode](https://github.com/seangreen2/home_assistant/wiki/Easy-Sleep-Mode-with-Home-Assistant)
Thanks to the official Home Assistant app, whenever we plug in our phones to charge at night, an automation is triggered to turn off all the lights and disable the automation that turns on the bedroom motion sensor. When unplugging our phones in the morning, another automation is triggered to turn other automations back on.

## Presence Detection
To ensure detection in our home, we use the following integrations with 100% success:
- [NMap](https://www.home-assistant.io/integrations/nmap_tracker/)
- [Home Assistant Mobile App](https://www.home-assistant.io/integrations/mobile_app/)

## Equipment
- [Home Assistant](https://www.home-assistant.io/) on a [HassOS](https://www.home-assistant.io/hassio/installation/) VM
- [Hue Bridge](https://amzn.to/30v9YND)
  - [11 A19 soft white bulbs](https://amzn.to/2LIFW4F)
  - [2 Hue Motion Sensors](https://amzn.to/2JmF1FE)
- [Wyze Sense](https://wyze.com/wyze-sense.html) - Requires a [custom component](https://github.com/kevinvincent/ha-wyzesense) to function.
  - Motion Sensors
  - Door/Window Sensors
- [4 ESP32 Development Boards](https://amazon.com/gp/product/B086MLNH7N/ref=ppx_yo_dt_b_asin_title_o04_s01?ie=UTF8&psc=1) - Used to determine Room Presence using BTLE. [Docs and setup information](https://jptrsn.github.io/ESP32-mqtt-room/)
- [Nest Thermostat](https://amzn.to/2YELTn2)
- [55" TCL Roku TV](https://amzn.to/2XAYIlK)
- [Nvidia Shield TV](https://amazon.com/gp/product/B07YP94PBJ/ref=ppx_yo_dt_b_asin_title_o06_s00?ie=UTF8&psc=1)
- [2 Chromecasts](https://store.google.com/us/product/chromecast?hl=en-US)
- [5 Google Home Minis](https://store.google.com/product/google_home_mini)
- [3 TP Link Smart Plugs (HS 100)](https://amzn.to/2XAKm4J)
- [2 TP Link Smart Switches (HS 200)](https://amzn.to/2Xyo8vy)
- [Wemo Mini Smart Plug](https://amzn.to/2JmSkpw)
- [Neato Botvac D3 Connected](https://amzn.to/30oP7v8)
- [PiHole (Network-Wide Ad Blocking)](https://pi-hole.net/)
- [Plex Server](https://www.plex.tv/)

#### Custom Lovelace Components
- Mini Graph Cards: https://github.com/kalkih/mini-graph-card
- Mini Media Player Cards: https://github.com/kalkih/mini-media-player
- Simple Weather Card: https://github.com/kalkih/simple-weather-card
- Simple Thermostat Card: https://github.com/nervetattoo/simple-thermostat
- Bar Cards: https://github.com/custom-cards/bar-card
- Vacuum Card: https://github.com/denysdovhan/vacuum-card

## Dashboard
![1](https://i.imgur.com/HmoTjg5.png)
![2](https://i.imgur.com/45RVpnr.png)
![3](https://i.imgur.com/3lttR9R.png)
![4](https://i.imgur.com/pJFWITl.png)
![5](https://i.imgur.com/leFmoYo.png)
![6](https://i.imgur.com/k4GEwLE.png)
