## 🏠 Home Assistant Automations Overview

Welcome to the brain of this smart home: an evolving network of deeply integrated automations designed to balance **comfort, efficiency, awareness, and resilience**. This system uses occupancy data, environmental sensors, smart devices, and adaptive logic to create a living space that thinks ahead and reacts in real-time.

This README serves as a documentation hub for each core domain of automation, outlining their purpose, logic, and any noteworthy design patterns.

---

### 📂 Categories

1. **🌡️ Climate Control & Comfort Optimization**  
   Keep the home comfortable and efficient with adaptive thermostat logic, fan control, and presence-aware adjustments. The system adjusts dynamically based on time of day, AQI, and who's actually home—minimizing energy waste while maximizing comfort.

2. **🔌 Smart Plug Management & Energy Monitoring**  
   Critical appliances like freezers, fridges, and radon mitigation systems are protected with auto-recovery logic. High-risk devices are constantly monitored, with power analytics helping to track trends and identify abnormalities.

3. **📍 Occupancy Detection & Room Awareness**  
   The house knows where you are—and where you aren’t. Room-based presence sensors let your automations react based on individual locations, enabling fine-grained control over HVAC, lighting, and more.

4. **🌀 Air Circulation & Quality**  
   Fans don’t just respond to temperature—they respond to the air itself. This logic circulates air based on AQI, runs on smart timers, and integrates seamlessly with other climate controls to keep the home fresh and healthy.

5. **📺 Media-Aware Environment**  
   Watching something? The system adapts accordingly—fans won’t blast you during a movie, HVAC holds steady, and lights stay put. It’s environmental automation with respect for immersion.

6. **🚪 Door & Window Safety Logic**  
   Open a patio door? HVAC knows to shut off. Future logic may tie in with windows and even alert routines. It’s about tying physical access into environmental control and energy protection.

7. **🛏️ Sleep-Aware Adjustments**  
   Bedtime isn’t just for humans. Automations respect when you're winding down, suppressing fan behavior, notifications, and other triggers that might interrupt your rest.

8. **🔔 Alerting & Notifications**  
   Built-in failsafes detect unplugged devices, automation issues, and environment changes—alerting you with targeted notifications. Future upgrades could tailor alerts based on who's home or awake.

9. **🧠 System Recovery & Edge Cases**  
   Not all automations are sexy—but these are smart. They ensure safe system behavior after reboots, prevent stuck fan states, and introduce cooldown periods so things don’t go haywire with too many triggers.

---

## 🌡️ Climate Control & Comfort Optimization

This section outlines the climate management philosophy powering the home. It balances comfort, energy savings, and hardware longevity by intelligently reacting to **room-level presence**, **external weather**, **air quality**, and **time of day**—all without compromising on luxury. Below is a breakdown of the system’s major climate automations.

---

### 🏠 Adaptive Nest Mode Switching
When the home is occupied, the system ensures both upstairs and downstairs Nest thermostats exit eco mode and shift into active climate management. A combination of **time patterns**, **patio door states**, and **outdoor temperature thresholds** determine whether cooling, heating, or a balanced heat/cool mode is needed. The logic uses an average of indoor temps from both zones to make smarter mode decisions. The automation also reloads the Nest configuration to ensure no sync issues arise.

**Highlights:**
- Automatically adjusts between `cool`, `heat`, and `heat_cool` based on both inside and outside temperature.
- Only triggers when the patio door is closed and everyone is home.
- Reloads the Nest config entry to avoid HA/Nest sync desyncs.

---

### 🧍 Room-Based HVAC Adjustments (Presence-Aware)
Using custom room presence sensors for both Sean and Emily, the system dynamically tunes the temperature targets for each floor based on occupancy.

#### Downstairs Logic:
- If someone is present, reduce cooling setpoint by 2°F for comfort.
- If no one is present for over 10 minutes, increase the setpoint to save energy.
- Automatically avoids conflict with media playback or bedtime states.

#### Upstairs Logic:
- Same dynamic as downstairs, but tuned with a slightly shorter timeout.
- Designed for frequent use of the office and bedrooms, especially during work hours.
- Avoids triggering when media is playing upstairs (e.g., Plex).

**Why it works:** Presence-based control allows cooling to be aggressive when needed and relaxed when not, without toggling HVAC modes constantly.

---

### 🌬️ Hourly Fan Circulation (Air Quality-Aware)
Rather than running HVAC just for temperature, this logic kicks on fans based on the local AQI (Air Quality Index). When air quality is moderate (AQI 50–100), fans run for 15 minutes. When AQI is poor (100+), circulation runs longer—30 minutes. The idea is to keep air fresh and moving without initiating cooling.

**Failsafe:** After every HA restart, fans are explicitly turned off to prevent getting stuck in an on state.

**Conditions Include:**
- System not currently heating or cooling.
- At least one person home.
- AQI-based run logic.

---

### 🚪 Patio Door + HVAC Mode Control
To prevent waste, if the patio door is open for more than 2 minutes, HVAC is shut off. Once the door is closed, it re-engages heating/cooling based on current conditions.

**Bonus Logic:** It uses outdoor temperature and indoor temperature to determine whether to cool, heat, or balance after the door closes—ensuring it doesn’t just default to one mode blindly.

---

### 🌀 Occupancy-Based Fan Control (Living Room, Bedroom, Office)
Instead of running ceiling and floor fans blindly, these automations tie directly into room presence, temperature thresholds, media playback, and bedtime state.

#### Examples:
- **Living Room Fan** turns on if the room is occupied, it’s after 7 a.m., and temps are above 72°F.
- **Bedroom Fan** uses both temperature and occupancy but won’t run during bedtime.
- **Office Fan** can be triggered by temperature or motion and will shut off if the room cools down or Sean logs off Steam.

---

### 🎬 Adaptive Lighting During Media Playback
To keep the viewing experience immersive and distraction-free, lights in media zones automatically adjust based on playback state. When content starts playing on the living room TV or Shield, select lights dim or shut off completely. When playback stops, lighting gracefully resumes its prior brightness or scene state.

This setup avoids harsh lighting during movies while ensuring you’re never left in the dark afterward. It's a subtle enhancement that makes entertainment feel deliberate and theater-like without lifting a finger.

**Logic Highlights:**
- Triggers on `media_player` state changes.
- Respects occupancy and bedtime flags.
- Stores light states before dimming, restoring them intelligently.
- Fully reversible without hard transitions.

---

### 📍 Room Presence Detection Logic
Room presence is the lifeblood of this smart home's intelligence. Rather than relying on basic motion sensors alone, presence is derived using a blend of device trackers, motion groups, and contextual flags like sleep or media playback. Each room is treated as its own behavioral zone, allowing automations to respond with precision.

**Key Methods:**
- **Custom Sensors:** Sensors like `sensor.sean_room_location` and `sensor.emily_room_location` track where each person is, using a combination of BLE, Wi-Fi, motion, and other signals.
- **Groups & Booleans:** Rooms are defined with grouped motion sensors and toggles like `input_boolean.office_occupied` to maintain context even after motion ends.
- **Location-Aware Automations:** Most logic—including HVAC, fan control, lighting, and notifications—is scoped to individual rooms and occupancy states.

**Why It Matters:**
- Keeps climate control hyper-targeted.
- Allows fans and lights to react naturally to real movement.
- Enables automations to layer logic, such as "Sean is in the office AND Steam is running."

Presence isn’t a binary—it's a living context system. That nuance is what elevates this setup from smart to sentient.

---

### 🛡️ Critical Appliance Watchdog Logic
Some devices are too important to fail quietly. This system watches key appliances like the **garage freezer**, **main fridge**, and **radon mitigator** using Zigbee smart plugs and automation safeguards. If any of them shut off or go offline for more than 30 minutes, the system immediately attempts recovery and sends a high-priority alert.

**Key Behaviors:**
- Detects `off` or `unavailable` states for 30+ minutes.
- Automatically attempts to turn the plug back on.
- Sends a persistent notification with alarm-level urgency.
- Repeats recovery attempts every 5 minutes until the issue is resolved.

These are mission-critical appliances, and the logic ensures you're never caught off guard by a failure that could result in food loss—or worse.

---

### 🔄 System Recovery & Auto-Heal Logic
Home Assistant reboots, device dropouts, and integration hiccups are inevitable. This system includes silent safety nets that repair critical states and reset components to avoid undesired behavior.

**Examples:**
- Turns HVAC fans off automatically after restart to prevent stuck states.
- Reloads Nest configuration entries periodically to fix desync issues.
- Ensures that AQI-based fan logic doesn’t leave fans running indefinitely.

These background tasks keep the automation core clean and sane, especially across Home Assistant updates or Wi-Fi disruptions.

---

### 🧠 Context Stacking: Smarter Than Events Alone
What makes this setup exceptional is that automations don’t react to a single thing—they respond to a **confluence of states**. Fans don’t just turn on because someone’s home; they turn on if the temperature’s right, motion is detected, media isn’t playing, and bedtime isn’t active.

**Why This Matters:**
- Eliminates false positives or unnecessary triggers.
- Allows automations to feel more human in behavior.
- Supports complex logic like "Emily is watching TV, it's after sunset, and the room is too warm—but don’t trigger if it's bedtime."

This layered context design is what gives the entire automation network its smooth, intelligent flow.

Want to see it in action? Check out the automation YAMLs in the `automations/` folder.
