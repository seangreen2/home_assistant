## Home Automation Philosophy

You shouldn't have to work the room, the room should work you. True home automation is having your home anticipate what you want without needing any input from you.

Using voice commands are nice and all, but that ends up being just another switch you have to use and is ultimately just a remote control, not automation.

[<img src="https://i.imgur.com/j7pTcmh.png">](https://www.buymeacoffee.com/gi2L3VGSo)

## Notable Automations [(Wiki)](https://github.com/seangreen2/home_assistant/wiki)
### [Room Presence with Google Homes](https://github.com/seangreen2/home_assistant/wiki/Room-Presence-with-Google-Homes)
This is kind of like the [Holy Grail](https://www.youtube.com/watch?v=momI9XSV3kM) for me. With accurate room presence, a lot of possibilities open up for more exciting automations. My system works via the Bluetooth on our Google Home Minis and they look for where our Android phones are in our home using RSSI values. This works out rather nicely for detection purposes as we typically take our phones with us to each room. Of course, you can use any BLE devices to accomplish this as well such as a smart watch.

So far this has been incredibly accurate with the automations taking roughly ten seconds or less to determine where we are located and displays it on my frontend. I have successfully been using the results of the room presence to affect my lighting automations without any problems.

### [Cool or Heat your Home Before you Arrive](https://github.com/seangreen2/home_assistant/wiki/Beat-the-Heat-and-Begin-Cooling-your-Home-before-you-Arrive)
It's never fun to come home to a hot and humid home just to have your AC kick on as soon as it detects you on your WiFi, or however else you have your local presence set up. Like you, I used to also come home and be miserable until the HVAC finally caught up to my comfortable temperatures. Depending on your preferences this could take TENS OF MINUTES! That simply will not do. This automation uses the Proximity Sensor to intelligently detect if you're on your way home and will begin making it comfortable before you arrive.

### [Automatic Brightness for Lighting](https://github.com/seangreen2/home_assistant/wiki/Automatic-Brightness-for-Lighting)
Due to renting and lack of any overhead lighting, we use Hue smart bulbs in standing lamps. We don’t have any of the expensive color bulbs, but I still wanted our normal white bulbs to slowly dim during the evening to encourage sleepiness. I developed two automations to take care of this problem and wanted to avoid using any custom components in the process. One automation for turning on the lights to the desired brightness, the other automation being a transitional one where it tracks the Sun and only dims the lights if they are already on.

The automations are highly customizable with each room having different light values attached to them. My only requirement for this was to avoid having the lights initially turn on to 100% brightness and then dim to the appropriate setting. Fortunately, these automations avoid that problem and turn on to the appropriate brightness depending on the Sun’s location. Another bonus of tracking the Sun for brightness is that these automations double for the morning and don’t blind you as you are still waking up.

### [Sleep Detection with Tasker](https://github.com/seangreen2/home_assistant/wiki/Turning-off-your-lights-with-Tasker)
Using a fantastic Android app called [Tasker](https://play.google.com/store/apps/details?id=net.dinglisch.android.taskerm&hl=en_US), whenever we plug in our phones to charge at night, a script is triggered to turn off all the lights and disable the automation that turns on the bedroom motion sensor. When unplugging our phones in the morning, another script is triggered to turn the automations back on. Before Tasker we used to use voice commands to accomplish this, but this is far more elegant and was surprisingly simple to accomplish.

## Equipment
- [Home Assistant](https://www.home-assistant.io/) on a [DietPi VM](https://dietpi.com/)
- [Hue Bridge](https://amzn.to/30v9YND)
  - [11 A19 soft white bulbs](https://amzn.to/2LIFW4F)
  - [2 Hue Motion Sensors](https://amzn.to/2JmF1FE)
- [Xiaomi Gateway](https://amzn.to/2LLrhG7)
  - [3 Xiaomi Motion Sensors](https://amzn.to/30ssu95)
  - [Window/Door Sensor](https://amzn.to/2Xyx0Go)
  - [Temperature and Humidity Sensor](https://amzn.to/2G4z3qI)
- [Nest Thermostat](https://amzn.to/2YELTn2)
- [55" TCL Roku TV](https://amzn.to/2XAYIlK)
- [2 Chromecasts](https://store.google.com/us/product/chromecast?hl=en-US)
- [3 Google Home Minis](https://store.google.com/product/google_home_mini)
- [3 TP Link Smart Plugs (HS 100)](https://amzn.to/2XAKm4J)
- [2 TP Link Smart Switches (HS 200)](https://amzn.to/2Xyo8vy)
- [Wemo Mini Smart Plug](https://amzn.to/2JmSkpw)
- [Neato Botvac D3 Connected](https://amzn.to/30oP7v8)
- [PiHole (Raspberry Pi Gen 1B)](https://amzn.to/2XAGUqJ)
- [Plex Server](https://www.plex.tv/)

#### Custom Components
- Mini Graph Cards: https://github.com/kalkih/mini-graph-card
- Mini Media Player Cards: https://github.com/kalkih/mini-media-player
- Simple Weather Card: https://github.com/kalkih/simple-weather-card
- Simple Thermostat Card: https://github.com/nervetattoo/simple-thermostat
- Bar Cards: https://github.com/custom-cards/bar-card

## Dashboard
![1](https://i.imgur.com/LRmZRzq.png)
![2](https://i.imgur.com/55zhHu6.png)
![3](https://i.imgur.com/vWPci9f.png)
![4](https://i.imgur.com/oToTiB2.png)
![5](https://i.imgur.com/hlKHTAa.png)
![6](https://i.imgur.com/SYsRTYW.png)

---
I use affiliate links to help continue my hobby. When used, I get a small commission if the product is purchased. Prices are exactly the same for you if your purchase is through an affiliate link or a non-affiliate link. You will not pay more by using an affiliate link.
