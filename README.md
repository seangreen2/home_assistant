## Intro

I've been using HA for about a year now and it's been a great experience. I'm a graphic designer, not a coder, so I'm sure my YAML isn't as advanced, simple, or clean as it could be. I'm just happy that I can solve every problem that I want to so far.

#### Home Automation Philosophy

You shouldn't have to work the room, the room should work you. True home automation is having your home anticipate what you want without needing any input from you.

Using voice commands are nice and all, but that ends up being just another switch you have to use and is ultimately just a remote control, not automation.

## Current Goals
- My Hue lights have a strange issue of not coming at full brightness at random times despite what my YAML says. To fix this, I've added a one second delay on all lighting automations followed by another brightness command to ensure the lights always come on to the brightness they should. So far this fix has a 100% success rate on all lighting.
- (DONE) Have all lights turn on/off with motion and never have to use a physical switch or voice commands again. I have some Xiaomi equipment coming in which should finally complete this.

#### Custom Components
To use the Hue Motion Sensors in Home Assistant I used https://github.com/robmarkcole/Hue-sensors-HASS

## Equipment
- Home Assistant using Ubuntu on a VM
- Hue Bridge
  - 10 A19 soft white bulbs
  - 2 Hue Motion Sensors
- Xiaomi Gateway
  - 2 Xiaomi Motion Sensors
  - Window/Door Sensor
  - Temperature and Humidity Sensor
- Nest Thermostat (Gen 2)
- 55" TCL Roku TV (2017)
- Chromecasts (Gen 1 and Gen 2)
- 3 Google Home Minis
- 2 TP Link Smart Plugs (HS 100)
- Wemo Mini Smart Plug
- Neato Botvac D3
- PiHole (Raspberry Pi Gen 1B)
- Plex Server

## Dashboard (New Custom Theme!)
![1](https://i.imgur.com/p0VlC8e.jpg)
![2](https://i.imgur.com/Z1Cs4SC.jpg)
![3](https://i.imgur.com/49QStQb.jpg)
![4](https://i.imgur.com/RjEg0SL.jpg)
![5](https://i.imgur.com/pf8QbjK.jpg)
