<p align="center">
  <a href=""><img src="https://www.home-assistant.io/images/home-assistant-logo.svg" alt="logo" width="175"></a>
</p>

## Home Automation Philosophy
***You shouldn't have to work the room, the room should work you.*** True home automation is having your home anticipate what you want without needing any input from you. Using voice commands are nice and all, but that ends up being just another switch you have to use and is ultimately just a remote control, not automation.

I also made the popular dark theme [Slate](https://github.com/seangreen2/slate_theme).

## Presence Detection
To ensure detection in our home, we use the following integrations with 100% success:
- [NMap](https://www.home-assistant.io/integrations/nmap_tracker/)
- [Home Assistant Mobile App](https://www.home-assistant.io/integrations/mobile_app/)
- [Room Presence using BTLE](https://jptrsn.github.io/ESP32-mqtt-room/)

## Equipment
- [Home Assistant](https://www.home-assistant.io/) on a [HassOS](https://www.home-assistant.io/hassio/installation/) VM
- [Hue Bridge](https://amzn.to/30v9YND)
  - [A19 soft white bulbs](https://amzn.to/2LIFW4F)
  - [Hue Motion / Temperature Sensors](https://amzn.to/2JmF1FE)
- [Wyze Sense](https://wyze.com/wyze-sense.html) - Requires a [custom component](https://github.com/kevinvincent/ha-wyzesense) to function.
  - Motion Sensors
  - Door/Window Sensors
- [ESP32 Development Boards](https://amazon.com/gp/product/B086MLNH7N/) - Used to determine Room Presence using BTLE. [Docs and setup information](https://jptrsn.github.io/ESP32-mqtt-room/)
- [Nest Thermostats - 3rd / 2nd Gen](https://amzn.to/2YELTn2)
- [Nvidia Shield Pro](https://amazon.com/gp/product/B07YP94PBJ/ref=ppx_yo_dt_b_asin_title_o06_s00?ie=UTF8&psc=1)
- [Google Home - Minis / Show](https://store.google.com/product/google_home_mini)
- [TP Link Smart Plugs (HS 100)](https://amzn.to/2XAKm4J)
- [TP Link Smart Switches (HS 200)](https://amzn.to/2Xyo8vy)
- [Wemo Mini Smart Plug](https://amzn.to/2JmSkpw)
- [Roborock S6 Pure](https://smile.amazon.com/gp/product/B084Z5P2BX)
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
![1](https://i.imgur.com/LWlPtrm.png)
![2](https://i.imgur.com/B7JDq8C.png)
![3](https://i.imgur.com/f6s7VB0.png)
![4](https://i.imgur.com/uPXHERP.png)
![5](https://i.imgur.com/2dv9MO4.png)
![6](https://i.imgur.com/INLwMzW.png)
