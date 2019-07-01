## Home Automation Philosophy

You shouldn't have to work the room, the room should work you. True home automation is having your home anticipate what you want without needing any input from you.

Using voice commands are nice and all, but that ends up being just another switch you have to use and is ultimately just a remote control, not automation.

[<img src="https://i.imgur.com/j7pTcmh.png">](https://www.buymeacoffee.com/gi2L3VGSo)

## Notable Automations [(Wiki)](https://github.com/seangreen2/home_assistant/wiki)
### [Media](https://github.com/seangreen2/home_assistant/blob/master/automations/media_living_room.yaml)
While these are simple automations, they do have some “wow” factor to them. Whenever watching any media on Plex after 5:00 p.m., the lights will automatically turn off until either paused or stopped. When paused, the lights will slowly brighten to 25% brightness. When media is stopped, the lights will slowly brighten to either 100% or to another brightness depending on the time of day. The later in the evening, the dimmer the lights will brighten to.

### [Automatic Brightness for Lighting](https://github.com/seangreen2/home_assistant/wiki/Automatic-Brightness-for-Lighting)
Due to renting and lack of any overhead lighting, we use Hue smart bulbs in standing lamps. We don’t have any of the expensive color bulbs, but I still wanted our normal white bulbs to slowly dim during the evening to encourage sleepiness. I developed two automations to take care of this problem and wanted to avoid using any custom components in the process. One automation for turning on the lights to the desired brightness, the other automation being a transitional one where it tracks the Sun and only dims the lights if they are already on.

The automations are highly customizable with each room having different light values attached to them. My only requirement for this was to avoid having the lights initially turn on to 100% brightness and then dim to the appropriate setting. Fortunately, these automations avoid that problem and turn on to the appropriate brightness depending on the Sun’s location. Another bonus of tracking the Sun for brightness is that these automations double for the morning and don’t blind you as you are still waking up.

### [Room Presence](https://github.com/seangreen2/home_assistant/wiki/Room-Presence-with-Google-Homes)
This is kind of like the Holy Grail for me. With accurate room presence, a lot of possibilities open up for more exciting automations. My system works via the Bluetooth on our Google Home Minis and they look for where our Android phones are in our home using RSSI values. This works out rather nicely for detection purposes as we typically take our phones with us to each room. Of course, you can use any BLE devices to accomplish this as well such as a smart watch.

So far this has been incredibly accurate with the automations taking roughly ten seconds or less to determine where we are located and displays it on my frontend. I have successfully been using the results of the room presence to affect my lighting automations without any problems.

### [Sleep Detection with Tasker](https://github.com/seangreen2/home_assistant/wiki/Turning-off-your-lights-with-Tasker)
Using a fantastic Android app called [Tasker](https://play.google.com/store/apps/details?id=net.dinglisch.android.taskerm&hl=en_US), whenever we plug in our phones to charge at night, a script is triggered to turn off all the lights and disable the automation that turns on the bedroom motion sensor. When unplugging our phones in the morning, another script is triggered to turn the automations back on. Before Tasker we used to use voice commands to accomplish this, but this is far more elegant and was surprisingly simple to accomplish.

## Equipment
- Home Assistant on a DietPi VM
- Hue Bridge
  - 11 A19 soft white bulbs
  - 2 Hue Motion Sensors
- Xiaomi Gateway
  - 3 Xiaomi Motion Sensors
  - Window/Door Sensor
  - Temperature and Humidity Sensor
- Nest Thermostat (Gen 2)
- 55" TCL Roku TV (2017)
- 2 Chromecasts (Gen 1 and Gen 2)
- 3 Google Home Minis
- 3 TP Link Smart Plugs (HS 100)
- 2 TP Link Smart Switches (HS 200)
- Wemo Mini Smart Plug
- Neato Botvac D3 Connected
- PiHole (Raspberry Pi Gen 1B)
- Plex Server

#### Custom Components
- Mini Graph Cards: https://github.com/kalkih/mini-graph-card
- Mini Media Player Cards: https://github.com/kalkih/mini-media-player
- Simple Weather Card: https://github.com/kalkih/simple-weather-card
- Simple Thermostat Card: https://github.com/nervetattoo/simple-thermostat
- Bar Cards: https://github.com/custom-cards/bar-card


## Dashboard
![1](https://i.imgur.com/e1VCcdB.jpg)
![2](https://i.imgur.com/WZpvUJY.jpg)
![3](https://i.imgur.com/QCODzIW.jpg)
![4](https://i.imgur.com/KzXU1cL.jpg)
![5](https://i.imgur.com/8dpqaTG.jpg)
